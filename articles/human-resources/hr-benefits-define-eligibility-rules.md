---
title: Definiowanie zasad i reguł uprawnień do świadczenia
description: W tych tematach wyjaśniono sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.
author: twheeloc
ms.date: 08/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: c2595e40f6f9d1f75a94a3339735cc06bdabd14a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067661"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Definiowanie zasad i reguł uprawnień do świadczenia


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie wyjaśniono sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.  

## <a name="create-benefit-eligibility-policy-rule-type"></a>Tworzenie typu reguły uprawnienia do świadczenia

1. Wybierz kolejno opcje **Zasoby ludzkie > Świadczenia > Uprawnienie > Typy reguł uprawnień do świadczenia**.
2. Wybierz pozycję **Nowy**.
3. Wprowadź wartość w polu **Nazwa reguły**.
4. W polu **Opis** wprowadź lub wybierz wartość.
5. W polu **Nazwa kwerendy** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście wybierz łącze w wybranym wierszu.
7. Wybierz opcję **Zapisz**.
8. Zamknij stronę.

## <a name="benefit-eligibility-policy"></a>Zasady uprawnienia do świadczenia

1. Wybierz kolejno opcje **Zasoby ludzkie > Świadczenia > Uprawnienie > Zasady uprawnienia do świadczenia**.
2. Wybierz istniejącą zasadę świadczenia.
3. Na liście wybierz łącze w wybranym wierszu.
4. Przełącz rozwinięcie sekcji **Organizacje zasad**. Można dodać lub usunąć wszelkie organizacje, które mają zostać uwzględnione w zasadach.
5. Rozwiń lub zwiń sekcję **Reguły zasad**.
6. Na liście odszukaj utworzoną wcześniej regułę.
7. Wybierz pozycję **Utwórz regułę**.
8. W polu **Data obowiązywania** wprowadź dzień, od którego zasada ma obowiązywać.
    * Ustawienie dat zakończenia umożliwi wprowadzanie w przyszłości zmian w regułach i wyeliminowanie potrzeby wracania do zasad, jeśli zechcesz, aby te zmiany zaczęły obowiązywać.  
9. W razie potrzeby dodaj klauzulę where do pola **Dodaj warunek**.
    * Na przykład jeżeli chcesz, aby reguła była stosowana tylko do menedżerów sprzedaży, można utworzyć klauzulę Where o treści: Gdzie opis stanowiska równa się Menedżer sprzedaży. W regule można dodać wiele instrukcji Where.  
10. Kliknij przycisk **OK**.
11. Zamknij stronę.

## <a name="assign-rule-to-benefit"></a>Przypisywanie reguły do świadczenia

1. Wybierz kolejno opcje **Zasoby ludzkie > Świadczenia > Świadczenia**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście wybierz łącze w wybranym wierszu.
4. Rozwiń lub zwiń sekcję **Reguły uprawnienia**.
5. Wybierz opcję **Edycja**.
6. W polu **Uprawnienie** zaznacz regułę.
7. W polu **Typ reguły** zaznacz regułę, która została wcześniej utworzona.
9. Na liście wybierz łącze w wybranym wierszu.
10. Wybierz opcję **Zapisz**.
11. Zamknij formularz.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
