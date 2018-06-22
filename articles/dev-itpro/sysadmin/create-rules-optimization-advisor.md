---
title: "Tworzenie reguł dla Doradcy optymalizacji"
description: "W tym temacie omówiono sposób dodawania nowych reguł do obszaru roboczego Doradca optymalizacji."
author: roxanadiaconu
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 83648a93f367510d7b04bbd04a9f37689ecfaa59
ms.openlocfilehash: a18fac31b5acb7d2a1ec40203122d4eb9d94a439
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2018

---

# <a name="create-rules-for-optimization-advisor"></a><span data-ttu-id="c4f68-103">Tworzenie reguł dla Doradcy optymalizacji</span><span class="sxs-lookup"><span data-stu-id="c4f68-103">Create rules for Optimization advisor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4f68-104">W tym temacie wyjaśniono sposób tworzenia nowych reguł dla obszaru roboczego **Doradca optymalizacji**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-104">This topic explains how to create new rules for **Optimization advisor**.</span></span> <span data-ttu-id="c4f68-105">Na przykład można utworzyć nową regułę określającą, które sprawy dotyczące zapytań ofertowych (ZO) mają puste tytuły.</span><span class="sxs-lookup"><span data-stu-id="c4f68-105">For example, you can create a new rule that identifies which Request for Quotations (RFQ) cases have an empty title.</span></span> <span data-ttu-id="c4f68-106">Stosowanie tytułów do spraw ułatwia ich rozpoznawanie i wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c4f68-106">Using titles on cases makes them easily identifiable and searchable.</span></span> <span data-ttu-id="c4f68-107">Choć poniższy przykład jest dość prosty, pokazuje, co można osiągnąć za pomocą reguł optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4f68-107">While quite simple, this example shows what can be achieved with optimization rules.</span></span> 

<span data-ttu-id="c4f68-108">*Reguła* sprawdza dane aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c4f68-108">A *rule* is a check on application data.</span></span> <span data-ttu-id="c4f68-109">Jeśli warunek reguły jest spełniony, są tworzone możliwości optymalizowania procesów lub poprawiania danych.</span><span class="sxs-lookup"><span data-stu-id="c4f68-109">If the condition that the rule evaluates is met, opportunities to optimize processes or improve data are created.</span></span> <span data-ttu-id="c4f68-110">Wobec możliwości można podjąć działania, a opcjonalnie również mierzyć skutki tych działań.</span><span class="sxs-lookup"><span data-stu-id="c4f68-110">The opportunities can be acted upon and, optionally, the impact of the actions can be measured.</span></span> 

<span data-ttu-id="c4f68-111">Aby utworzyć nową regułę dla obszaru roboczego **Doradca optymalizacji**, dodaj nową klasę, która rozszerza klasę abstrakcyjną **SelfHealingRule**, implementuje interfejs **IDiagnosticsRule** i jest uzupełniona przez atrybut **DiagnosticRule**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-111">To create a new rule for the **Optimization advisor**, add a new class that extends the **SelfHealingRule** abstract class, implements the **IDiagnosticsRule** interface, and is decorated by the **DiagnosticRule** attribute.</span></span> <span data-ttu-id="c4f68-112">Klasa musi również zawierać metodę z atrybutem **DiagnosticsRuleSubscription**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-112">The class must also have a method decorated with the **DiagnosticsRuleSubscription** attribute.</span></span> <span data-ttu-id="c4f68-113">Zgodnie z konwencją dokonuje się tego w metodzie **opportunityTitle**, która zostanie omówiona później.</span><span class="sxs-lookup"><span data-stu-id="c4f68-113">By convention, that is done on the **opportunityTitle** method, which will be discussed later.</span></span> <span data-ttu-id="c4f68-114">Tę nową klasę można dodać do niestandardowego modelu zależnego od modelu **SelfHealingRules**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-114">This new class can be added to a custom model with a dependency on the **SelfHealingRules** model.</span></span> <span data-ttu-id="c4f68-115">W poniższym przykładzie implementowana reguła jest zatytułowana **RFQTitleSelfHealingRule**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-115">In the following example, the rule being implemented is called **RFQTitleSelfHealingRule**.</span></span>

```
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

<span data-ttu-id="c4f68-116">Klasa abstrakcyjna **SelfHealingRule** zawiera metody abstrakcyjne, które należy zaimplementować w klasach dziedziczenia.</span><span class="sxs-lookup"><span data-stu-id="c4f68-116">The **SelfHealingRule** abstract class has abstract methods that must be implemented in inheriting classes.</span></span> <span data-ttu-id="c4f68-117">Rdzeniem jest metoda **evaluate**, która zwraca listę możliwości zidentyfikowanych przez regułę.</span><span class="sxs-lookup"><span data-stu-id="c4f68-117">The core is the **evaluate** method, which returns a list of the opportunities identified by the rule.</span></span> <span data-ttu-id="c4f68-118">Możliwości mogą dotyczyć konkretnych firm lub mieć zastosowanie do całego systemu.</span><span class="sxs-lookup"><span data-stu-id="c4f68-118">Opportunities can be per legal entity or can apply to the whole system.</span></span>

```
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

<span data-ttu-id="c4f68-119">Metoda opisana powyżej powoduje analizowanie firm w układzie pętli i wybieranie spraw ZO z pustymi tytułami w metodzie **findRFQCasesWithEmptyTitle**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-119">The method shown above loops over companies and selects RFQ cases with empty titles in the **findRFQCasesWithEmptyTitle** method.</span></span> <span data-ttu-id="c4f68-120">Jeśli zostanie znaleziony co najmniej jeden taki przypadek, za pomocą metody **getOpportunityForCompany** jest tworzona możliwość związana z konkretną firmą.</span><span class="sxs-lookup"><span data-stu-id="c4f68-120">If at least one such case is found, then a company-specific opportunity is created with the **getOpportunityForCompany** method.</span></span> <span data-ttu-id="c4f68-121">Należy zauważyć, że pole **Dane** w tabeli **SelfHealingOpportunity** jest typu **Kontener** i z tego względu może zawierać dowolne dane pasujące do logiki właściwej dla tej reguły.</span><span class="sxs-lookup"><span data-stu-id="c4f68-121">Notice that the field **Data** in the **SelfHealingOpportunity** table is of type **Container**, and can therefore contain any data relevant to the logic specific to this rule.</span></span> <span data-ttu-id="c4f68-122">Jeśli w atrybucie **OpportunityDate** zostanie ustawiona bieżąca sygnatura czasowa, system będzie rejestrował czas ostatniego sprawdzania możliwości.</span><span class="sxs-lookup"><span data-stu-id="c4f68-122">Setting **OpportunityDate** with the current timestamp registers the time of the latest evaluation of the opportunity.</span></span>  

<span data-ttu-id="c4f68-123">Możliwości mogą mieć także charakter międzyfirmowy.</span><span class="sxs-lookup"><span data-stu-id="c4f68-123">Opportunities can also be cross-company.</span></span> <span data-ttu-id="c4f68-124">W takim przypadku pętla analizy firmy nie jest konieczna i możliwość należy utworzyć za pomocą metody **getOpportunityAcrossCompanies**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-124">In this case, the loop over companies is not necessary and the opportunity must be created with the **getOpportunityAcrossCompanies** method.</span></span> 

<span data-ttu-id="c4f68-125">Poniższy kod przedstawia metodę **findRFQCasesWithEmptyTitle**, która zwraca identyfikatory spraw ZO mających puste tytuły.</span><span class="sxs-lookup"><span data-stu-id="c4f68-125">The following code shows the **findRFQCasesWithEmptyTitle** method, which returns the IDs of the RFQ cases that have empty titles.</span></span>

```
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

<span data-ttu-id="c4f68-126">Dwie inne metody, które należy zaimplementować, to **opportunityTitle** i **opportunityDetails**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-126">Two more methods that must be implemented are **opportunityTitle** and **opportunityDetails**.</span></span> <span data-ttu-id="c4f68-127">Pierwsza zwraca krótki tytuł możliwości, a druga szczegółowy opis możliwości, mogący także zawierać dane.</span><span class="sxs-lookup"><span data-stu-id="c4f68-127">The former returns a short title for the opportunity, the latter returns a detailed description of the opportunity, which can also include data.</span></span>

<span data-ttu-id="c4f68-128">Tytuł zwracany przez metodę **opportunityTitle** jest wyświetlany w kolumnie **Możliwość optymalizacji** w obszarze roboczym **Doradca optymalizacji**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-128">The title returned by **opportunityTitle** appears under the **Optimization opportunity** column in the **Optimization advisor** workspace.</span></span> <span data-ttu-id="c4f68-129">Pojawia się również jako nagłówek bocznego okienka zawierającego więcej informacji na temat możliwości.</span><span class="sxs-lookup"><span data-stu-id="c4f68-129">It also appears as the header of the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="c4f68-130">Zgodnie z konwencją ta metoda jest uzupełniana o atrybut **DiagnosticRuleSubscription**, który ma następujące argumenty:</span><span class="sxs-lookup"><span data-stu-id="c4f68-130">By convention, this method is decorated with the **DiagnosticRuleSubscription** attribute, which takes the following arguments:</span></span> 

* <span data-ttu-id="c4f68-131">**Obszar diagnostyczni** — wartość stałotekstowa typu **DiagnosticArea**, która opisuje, do którego obszaru aplikacji należy reguła, np. **DiagnosticArea::SCM**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-131">**Diagnostic area** – An enum of type **DiagnosticArea** that describes what area of the application the rule belongs to, such as **DiagnosticArea::SCM**.</span></span> 

* <span data-ttu-id="c4f68-132">**Nazwa reguły** — ciąg z nazwą reguły.</span><span class="sxs-lookup"><span data-stu-id="c4f68-132">**Rule name** – A string with the rule name.</span></span> <span data-ttu-id="c4f68-133">Ta wartość będzie wyświetlana w kolumnie **Nazwa reguły** w formularzu **Reguła weryfikacji diagnostyki** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="c4f68-133">This will appear under the **Rule name** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

* <span data-ttu-id="c4f68-134">**Częstotliwość uruchamiania** — wartość stałotekstowa typu **DiagnosticRunFrequency**, który opisuje, jak często reguła powinna być wykonywane, np. **DiagnosticRunFrequency::Codziennie**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-134">**Run frequency** – An enum of type **DiagnosticRunFrequency** that describes how often the rule should be run, such as **DiagnosticRunFrequency::Daily**.</span></span> 

* <span data-ttu-id="c4f68-135">**Opis reguły** — ciąg znaków z bardziej szczegółowym opisem reguły.</span><span class="sxs-lookup"><span data-stu-id="c4f68-135">**Rule description** – A string with a more detailed description of the rule.</span></span> <span data-ttu-id="c4f68-136">Ta wartość będzie wyświetlana w kolumnie **Opis reguły** w formularzu **Reguła weryfikacji diagnostyki** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="c4f68-136">This will appear under the **Rule description** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

> [!NOTE]
> <span data-ttu-id="c4f68-137">Atrybut **DiagnosticRuleSubscription** jest wymagany, aby reguła mogła działać.</span><span class="sxs-lookup"><span data-stu-id="c4f68-137">The **DiagnosticRuleSubscription** attribute is required for the rule to work.</span></span> <span data-ttu-id="c4f68-138">Zazwyczaj jest używany w metodzie **opportunityTitle**, ale można go stosować w dowolnej metodzie tej klasy.</span><span class="sxs-lookup"><span data-stu-id="c4f68-138">Typically, it is used on **opportunityTitle**, but it can decorate any method of the class.</span></span>

<span data-ttu-id="c4f68-139">Poniżej przedstawiono przykład implementacji.</span><span class="sxs-lookup"><span data-stu-id="c4f68-139">The following is an example implementation.</span></span> <span data-ttu-id="c4f68-140">Dla uproszczenia są wykorzystywane wstępne ciągi , ale poprawna implementacja wymaga etykiet.</span><span class="sxs-lookup"><span data-stu-id="c4f68-140">Raw strings are used for simplicity, but a correct implementation requires labels.</span></span> 

```
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

<span data-ttu-id="c4f68-141">Opis zwracany przez metodę **opportunityDetails** pojawia się w okienku bocznym, pokazując więcej informacji na temat możliwości.</span><span class="sxs-lookup"><span data-stu-id="c4f68-141">The description returned by **opportunityDetails** appears on the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="c4f68-142">Wykorzystuje on argument **SelfHealingOpportunity**, który odpowiada polu **Dane** mogącemu dostarczać bardziej szczegółowych informacji o możliwości.</span><span class="sxs-lookup"><span data-stu-id="c4f68-142">This takes the **SelfHealingOpportunity** argument, which is **Data** field that can be used to provide more details about the opportunity.</span></span> <span data-ttu-id="c4f68-143">W tym przykładzie metoda zwraca identyfikatory spraw ZO z pustymi tytułami.</span><span class="sxs-lookup"><span data-stu-id="c4f68-143">In the example, the method returns the IDs of the RFQ cases with an empty title.</span></span> 

```
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

<span data-ttu-id="c4f68-144">Dwie pozostałe metody abstrakcyjne, które trzeba zaimplementować, to **provideHealingAction** i **securityMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-144">The two remaining abstract methods to implement are **provideHealingAction** and **securityMenuItem**.</span></span> 

<span data-ttu-id="c4f68-145">**provideHealingAction** zwraca wartość true, jeśli określono akcję naprawiania. W przeciwnym razie zwraca wartość false.</span><span class="sxs-lookup"><span data-stu-id="c4f68-145">**provideHealingAction** returns true if a healing action is provided, otherwise, it returns false.</span></span> <span data-ttu-id="c4f68-146">Jeśli jest zwracana wartość true, metoda **performAction** musi być zaimplementowana. W przeciwnym razie będzie zgłaszany błąd.</span><span class="sxs-lookup"><span data-stu-id="c4f68-146">If true is returned, the method **performAction** must be implemented, or an error will be thrown.</span></span> <span data-ttu-id="c4f68-147">Metoda **PerformAction** wykorzystuje argument **SelfHealingOpportunity**, w którym dla akcji można użyć danych.</span><span class="sxs-lookup"><span data-stu-id="c4f68-147">The **performAction** method takes a **SelfHealingOpportunity** argument, in which the data can be used for the action.</span></span> <span data-ttu-id="c4f68-148">W przykładzie akcja powoduje otwarcie strony **PurchRFQCaseTableListPage** w celu wprowadzenia ręcznej korekty.</span><span class="sxs-lookup"><span data-stu-id="c4f68-148">In the example, the action opens the **PurchRFQCaseTableListPage**, for manual correction.</span></span> 

```
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

<span data-ttu-id="c4f68-149">W zależności od szczegółów reguły może istnieć możliwość wykonywania automatycznej akcji przy użyciu danych możliwości.</span><span class="sxs-lookup"><span data-stu-id="c4f68-149">Depending on the specifics of the rule, it might be possible to take an automatic action using the opportunity data.</span></span> <span data-ttu-id="c4f68-150">W tym przykładzie system może automatycznie generować tytuły spraw ZO.</span><span class="sxs-lookup"><span data-stu-id="c4f68-150">In this example, the system could generate titles for RFQ cases automatically.</span></span> 

<span data-ttu-id="c4f68-151">Metoda **securityMenuItem** zwraca nazwę elementu menu akcji, tak aby reguła była widoczna tylko dla użytkowników mających dostęp do elementu menu akcji.</span><span class="sxs-lookup"><span data-stu-id="c4f68-151">**securityMenuItem** returns the name of an action menu item such that the rule is only visible to users who can access the action menu item.</span></span> <span data-ttu-id="c4f68-152">Bezpieczeństwo może wymagać, aby określone reguły i możliwości były dostępne tylko dla autoryzowanych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="c4f68-152">Security might require that specific rules and opportunities are accessible only to authorized users.</span></span> <span data-ttu-id="c4f68-153">W przykładzie tylko użytkownicy mający dostęp do atrybutu **PurchRFQCaseTitleAction** mogą wyświetlać możliwość.</span><span class="sxs-lookup"><span data-stu-id="c4f68-153">In the example, only users with access to **PurchRFQCaseTitleAction** can view the opportunity.</span></span> <span data-ttu-id="c4f68-154">Należy zauważyć, że ten element menu akcji został utworzony dla tego przykładu oraz dodany jako punkt wejścia dla uprawnienia zabezpieczeń **PurchRFQCaseTableMaintain**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-154">Notice that this action menu item was created for this example, and was added as an entry point for the **PurchRFQCaseTableMaintain** security privilege.</span></span> 

> [!NOTE]
> <span data-ttu-id="c4f68-155">Aby zabezpieczenia działały poprawnie, element menu musi być elementem menu akcji.</span><span class="sxs-lookup"><span data-stu-id="c4f68-155">The menu item must be an action menu item for security to work correctly.</span></span> <span data-ttu-id="c4f68-156">Inne typy elementów menu, takie jak **Elementy menu wyświetlania**, nie będą działać poprawnie.</span><span class="sxs-lookup"><span data-stu-id="c4f68-156">Other menu item types, such as **Display menu items** will not work correctly.</span></span>

```
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

<span data-ttu-id="c4f68-157">Po skompilowaniu reguły należy wykonać następujące zadania, aby reguła była wyświetlana w interfejsie użytkownika (UI).</span><span class="sxs-lookup"><span data-stu-id="c4f68-157">After the rule has compiled, execute the following job to have it display in the user interface (UI).</span></span>

```
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

<span data-ttu-id="c4f68-158">Reguła będzie wyświetlana w formularzu **Reguła weryfikacji diagnostyki**, do którego można przejść po wybraniu kolejno opcji **Administrowanie systemem** > **Zadania okresowe** > **Obsługa reguły weryfikacji diagnostyki**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-158">The rule will display in the **Diagnostics validation rule** form, available from **System administration** > **Periodic tasks** > **Maintain diagnostics validation rule**.</span></span> <span data-ttu-id="c4f68-159">Aby włączyć egzekwowanie reguły, wybierz kolejno opcje **Administrowanie systemem** > **Zadania okresowe** > **Planowanie reguły weryfikacji diagnostyki** wybierz częstotliwość, z jaką ma być sprawdzane przestrzeganie reguły, np. **Codziennie**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-159">To have it evaluated, go to **System administration** > **Periodic tasks** > **Schedule diagnostics validation rule**, select the frequency of the rule, such as **Daily**.</span></span> <span data-ttu-id="c4f68-160">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f68-160">Click **OK**.</span></span> <span data-ttu-id="c4f68-161">Wybierz kolejno opcje **Administrowanie systemem** > **Doradca optymalizacji** i przeczytaj nową możliwość.</span><span class="sxs-lookup"><span data-stu-id="c4f68-161">Go to **System administration** > **Optimization advisor** to view the new opportunity.</span></span> 

<span data-ttu-id="c4f68-162">Poniższy przykład zawiera fragment kodu źródłowego ze szkieletem reguły, w tym ze wszystkimi wymaganymi metodami i atrybutami.</span><span class="sxs-lookup"><span data-stu-id="c4f68-162">The following example is a code snippet with the skeleton of a rule including all the required methods and attributes.</span></span> <span data-ttu-id="c4f68-163">Pomoże on rozpocząć pisanie nowych reguł.</span><span class="sxs-lookup"><span data-stu-id="c4f68-163">It helps you get started with writing new rules.</span></span> <span data-ttu-id="c4f68-164">Etykiety i elementy menu akcji używane w przykładzie służą wyłącznie celom demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="c4f68-164">The labels and action menu items that are used in the example are only used for demonstration purpose.</span></span>

```
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

<span data-ttu-id="c4f68-165">Aby uzyskać więcej informacji, obejrzyj krótki film na YouTube: [Doradca optymalizacji w programie Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ).</span><span class="sxs-lookup"><span data-stu-id="c4f68-165">For more information, watch the short YouTube video: [Optimization advisor in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span></span>

