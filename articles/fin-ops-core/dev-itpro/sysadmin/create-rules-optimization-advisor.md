---
title: Tworzenie reguł dla Doradcy optymalizacji
description: W tym temacie omówiono sposób dodawania nowych reguł do obszaru roboczego Doradca optymalizacji.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: e14949b871534868c42d2b26a116e10ff9f05179
ms.sourcegitcommit: 8ff2413b6cb504d2b36fce2bb50441b2e690330e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2020
ms.locfileid: "3082003"
---
# <a name="create-rules-for-optimization-advisor"></a>Tworzenie reguł dla Doradcy optymalizacji

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób tworzenia nowych reguł dla obszaru roboczego **Doradca optymalizacji**. Na przykład można utworzyć nową regułę określającą, które sprawy dotyczące zapytań ofertowych (ZO) mają puste tytuły. Stosowanie tytułów do spraw ułatwia ich rozpoznawanie i wyszukiwanie. Choć poniższy przykład jest dość prosty, pokazuje, co można osiągnąć za pomocą reguł optymalizacji. 

*Reguła* sprawdza dane aplikacji. Jeśli warunek reguły jest spełniony, są tworzone możliwości optymalizowania procesów lub poprawiania danych. Wobec możliwości można podjąć działania, a opcjonalnie również mierzyć skutki tych działań. 

Aby utworzyć nową regułę dla obszaru roboczego **Doradca optymalizacji**, dodaj nową klasę, która rozszerza klasę abstrakcyjną **SelfHealingRule**, implementuje interfejs **IDiagnosticsRule** i jest uzupełniona przez atrybut **DiagnosticRule**. Klasa musi również zawierać metodę z atrybutem **DiagnosticsRuleSubscription**. Zgodnie z konwencją dokonuje się tego w metodzie **opportunityTitle**, która zostanie omówiona później. Tę nową klasę można dodać do niestandardowego modelu zależnego od modelu **SelfHealingRules**. W poniższym przykładzie implementowana reguła jest zatytułowana **RFQTitleSelfHealingRule**.

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

Klasa abstrakcyjna **SelfHealingRule** zawiera metody abstrakcyjne, które należy zaimplementować w klasach dziedziczenia. Rdzeniem jest metoda **evaluate**, która zwraca listę możliwości zidentyfikowanych przez regułę. Możliwości mogą dotyczyć konkretnych firm lub mieć zastosowanie do całego systemu.

```xpp
protected List evaluate() 
{ 
    List results = new List(Types::Record); 
    
    DataArea dataArea; 

    while select id from dataArea 
        where !dataArea.isVirtual 
    { 
        changecompany(dataArea.id) 
        { 
            container result = this.findRFQCasesWithEmptyTitle(); 

            if (conLen(result) > 0) 
            { 
                SelfHealingOpportunity opportunity = this.getOpportunityForCompany(dataArea.Id); 
                opportunity.EvaluationState = SelfHealingEvaluationState::Evaluated; 
                opportunity.Data = result; 
                opportunity.OpportunityDate = DateTimeUtil::utcNow(); 
                
                results.addEnd(opportunity); 
            } 
        } 
    } 
    
    return results; 
} 
```

Metoda opisana powyżej powoduje analizowanie firm w układzie pętli i wybieranie spraw ZO z pustymi tytułami w metodzie **findRFQCasesWithEmptyTitle**. Jeśli zostanie znaleziony co najmniej jeden taki przypadek, za pomocą metody **getOpportunityForCompany** jest tworzona możliwość związana z konkretną firmą. Należy zauważyć, że pole **Dane** w tabeli **SelfHealingOpportunity** jest typu **Kontener** i z tego względu może zawierać dowolne dane pasujące do logiki właściwej dla tej reguły. Jeśli w atrybucie **OpportunityDate** zostanie ustawiona bieżąca sygnatura czasowa, system będzie rejestrował czas ostatniego sprawdzania możliwości.  

Możliwości mogą mieć także charakter międzyfirmowy. W takim przypadku pętla analizy firmy nie jest konieczna i możliwość należy utworzyć za pomocą metody **getOpportunityAcrossCompanies**. 

Poniższy kod przedstawia metodę **findRFQCasesWithEmptyTitle**, która zwraca identyfikatory spraw ZO mających puste tytuły.

```xpp
private container findRFQCasesWithEmptyTitle() 
{ 
    container result; 

    PurchRFQCaseTable rfqCase; 
    while select RFQCaseId from rfqCase 
        where rfqCase.Name == '' 
    { 
        result += rfqCase.RFQCaseId; 
    } 
    
    return result; 
} 
```

Dwie inne metody, które należy zaimplementować, to **opportunityTitle** i **opportunityDetails**. Pierwsza zwraca krótki tytuł możliwości, a druga szczegółowy opis możliwości, mogący także zawierać dane.

Tytuł zwracany przez metodę **opportunityTitle** jest wyświetlany w kolumnie **Możliwość optymalizacji** w obszarze roboczym **Doradca optymalizacji**. Pojawia się również jako nagłówek bocznego okienka zawierającego więcej informacji na temat możliwości. Zgodnie z konwencją ta metoda jest uzupełniana o atrybut **DiagnosticRuleSubscription**, który ma następujące argumenty: 

* **Obszar diagnostyczni** — wartość stałotekstowa typu **DiagnosticArea**, która opisuje, do którego obszaru aplikacji należy reguła, np. **DiagnosticArea::SCM**. 

* **Nazwa reguły** — ciąg z nazwą reguły. Ta wartość będzie wyświetlana w kolumnie **Nazwa reguły** w formularzu **Reguła weryfikacji diagnostyki** (**DiagnosticsValidationRuleMaintain**). 

* **Częstotliwość uruchamiania** — wartość stałotekstowa typu **DiagnosticRunFrequency**, który opisuje, jak często reguła powinna być wykonywane, np. **DiagnosticRunFrequency::Codziennie**. 

* **Opis reguły** — ciąg znaków z bardziej szczegółowym opisem reguły. Ta wartość będzie wyświetlana w kolumnie **Opis reguły** w formularzu **Reguła weryfikacji diagnostyki** (**DiagnosticsValidationRuleMaintain**). 

> [!NOTE]
> Atrybut **DiagnosticRuleSubscription** jest wymagany, aby reguła mogła działać. Zazwyczaj jest używany w metodzie **opportunityTitle**, ale można go stosować w dowolnej metodzie tej klasy.

Poniżej przedstawiono przykład implementacji. Dla uproszczenia są wykorzystywane wstępne ciągi , ale poprawna implementacja wymaga etykiet. 

```xpp
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

Opis zwracany przez metodę **opportunityDetails** pojawia się w okienku bocznym, pokazując więcej informacji na temat możliwości. Wykorzystuje on argument **SelfHealingOpportunity**, który odpowiada polu **Dane** mogącemu dostarczać bardziej szczegółowych informacji o możliwości. W tym przykładzie metoda zwraca identyfikatory spraw ZO z pustymi tytułami. 

```xpp
public str opportunityDetails(SelfHealingOpportunity _opportunity) 
{ 
    str details = ''; 
    container opportunityData = _opportunity.Data; 
    int affectedRFQCasesCount = conLen(opportunityData); 

    if (affectedRFQCasesCount != 0) 
    { 
        details = 'The following Request for Quotation cases have an empty title:\n'; 
        for (int i = 1; i <= affectedRFQCasesCount ; i++) 
        { 
            PurchRFQCaseId rfqCaseId = conPeek(opportunityData, i); 
            details += rfqCaseId + '\n'; 
        } 
    } 

    return details; 
}
```

Dwie pozostałe metody abstrakcyjne, które trzeba zaimplementować, to **provideHealingAction** i **securityMenuItem**. 

**provideHealingAction** zwraca wartość true, jeśli określono akcję naprawiania. W przeciwnym razie zwraca wartość false. Jeśli jest zwracana wartość true, metoda **performAction** musi być zaimplementowana. W przeciwnym razie będzie zgłaszany błąd. Metoda **PerformAction** wykorzystuje argument **SelfHealingOpportunity**, w którym dla akcji można użyć danych. W przykładzie akcja powoduje otwarcie strony **PurchRFQCaseTableListPage** w celu wprowadzenia ręcznej korekty. 

```xpp
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

W zależności od szczegółów reguły może istnieć możliwość wykonywania automatycznej akcji przy użyciu danych możliwości. W tym przykładzie system może automatycznie generować tytuły spraw ZO. 

Metoda **securityMenuItem** zwraca nazwę elementu menu akcji, tak aby reguła była widoczna tylko dla użytkowników mających dostęp do elementu menu akcji. Bezpieczeństwo może wymagać, aby określone reguły i możliwości były dostępne tylko dla autoryzowanych użytkowników. W przykładzie tylko użytkownicy mający dostęp do atrybutu **PurchRFQCaseTitleAction** mogą wyświetlać możliwość. Należy zauważyć, że ten element menu akcji został utworzony dla tego przykładu oraz dodany jako punkt wejścia dla uprawnienia zabezpieczeń **PurchRFQCaseTableMaintain**. 

> [!NOTE]
> Aby zabezpieczenia działały poprawnie, element menu musi być elementem menu akcji. Inne typy elementów menu, takie jak **Elementy menu wyświetlania**, nie będą działać poprawnie.

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

Po skompilowaniu reguły należy wykonać następujące zadania, aby reguła była wyświetlana w interfejsie użytkownika (UI).

```xpp
class ScanNewRulesJob 
{         
    public static void main(Args _args) 
    {         
        SysExtensionCache::clearAllScopes(); 
        var controller = new DiagnosticsRuleController(); 
        controller.runOperation(); 
    } 
} 
```

Reguła będzie wyświetlana w formularzu **Reguła weryfikacji diagnostyki**, do którego można przejść po wybraniu kolejno opcji **Administrowanie systemem** > **Zadania okresowe** > **Obsługa reguły weryfikacji diagnostyki**. Aby włączyć egzekwowanie reguły, wybierz kolejno opcje **Administrowanie systemem** > **Zadania okresowe** > **Planowanie reguły weryfikacji diagnostyki** wybierz częstotliwość, z jaką ma być sprawdzane przestrzeganie reguły, np. **Codziennie**. Kliknij przycisk **OK**. Wybierz kolejno opcje **Administrowanie systemem** > **Doradca optymalizacji** i przeczytaj nową możliwość. 

Poniższy przykład zawiera fragment kodu źródłowego ze szkieletem reguły, w tym ze wszystkimi wymaganymi metodami i atrybutami. Pomoże on rozpocząć pisanie nowych reguł. Etykiety i elementy menu akcji używane w przykładzie służą wyłącznie celom demonstracyjnych.

```xpp
[DiagnosticsRuleAttribute]
public final class SkeletonSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule
{
    [DiagnosticsRuleSubscription(DiagnosticsArea::SCM,
                                 "@SkeletonRuleLabels:SkeletonRuleTitle", // Label with the title of the rule
                                 DiagnosticsRunFrequency::Monthly,
                                 "@SkeletonRuleLabels:SkeletonRuleDescription")] // Label with a description of the rule
    public str opportunityTitle()
    {
        // Return a label with the title of the opportunity
        return "@SkeletonRuleLabels:SkeletonOpportunityTitle";
    }

    public str opportunityDetails(SelfHealingOpportunity _opportunity)
    {
        str details = "";

        // Use _opportunity.data to provide details on the opportunity

        return details;
    }

    protected List evaluate()
    {
        List results = new List(Types::Record);

        // Write here the core logic of the rule

        // When creating an opportunity, use:
        //     * this.getOpportunityForCompany() for company specific opportunities
        //     * this.getOpportunityAcrossCompanies() for cross-company opportunities

        return results;
    }

    public boolean providesHealingAction()
    {
        return true;
    }

    protected void performAction(SelfHealingOpportunity _opportunity)
    {
        // Place here the code that performs the healing action

        // To open a form, use the following:
        // new MenuFunction(menuItemDisplayStr(SkeletonRuleDisplayMenuItem), MenuItemType::Display).run();
    }

    public MenuName securityMenuItem()
    {
        return menuItemActionStr(SkeletonRuleActionMenuItem);
    }

}
```

Aby uzyskać więcej informacji, obejrzyj krótki film w portalu YouTube: [Doradca optymalizacji w Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)
