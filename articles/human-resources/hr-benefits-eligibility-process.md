---
title: Przetwarzanie uprawnień do świadczeń
description: Ta procedura pokazuje działanie procesu kwalifikowania do świadczeń.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 61818ad8d397fe2b61952003aa562818c4bad2f5
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687709"
---
# <a name="benefit-eligibility-process"></a>Przetwarzanie uprawnień do świadczeń


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ta procedura pokazuje działanie procesu kwalifikowania do świadczeń. Po zakończeniu procesu można wyświetlić wyniki. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje **Zasoby ludzkie \> Świadczenia \> Świadczenia**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście wybierz łącze w wybranym wierszu.
4. Wybierz opcję **Edycja**.
5. W polu **Uprawnienie** zaznacz opcję **Oparte na regułach**.
6. W polu **Typ reguły** zaznacz regułę świadczeń, którą chcesz zastosować do świadczenia.
7. W okienku akcji kliknij pozycję **Świadczenie**.
8. Wybierz **Tworzenie zdarzenia dotyczącego uprawnień**.
9. W rozwijanym menu w polu **Wydarzenie** wpisz wartość.
10. W polu **Opis** wprowadź lub wybierz wartość.
11. W polu **Typ zdarzenia** wybierz opcję **Otwarcie rejestracji**.
12. W polu **Data początkowa okresu obowiązywania** wprowadź datę i godzinę.
13. W polu **Data początkowa okresu rejestracji** wprowadź datę i godzinę.
14. W polu **Dni okresu rejestracji** wpisz liczbę.
15. Wybierz **Tworzenie zdarzenia**.
16. Na skróconej karcie **Pracownicy** wybierz pozycję **Dodaj**.
17. W polu **Wyświetlanie według typów** zaznacz opcję **Pracownicy**.
18. W polu **Wyświetlanie według firm** wybierz opcję **Bieżąca firma**.
19. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.
20. Kliknij przycisk **OK**.
21. Wybierz **Proces**.
22. Kliknij przycisk **OK**.
23. Odśwież stronę.
24. Wybierz opcję **Pokaż wyniki**.
25. Otwórz filtr kolumn **Stan**.
26. Sortuj kolumny od A do Z.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
