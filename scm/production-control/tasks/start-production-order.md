--- 
title: Rozpoczynanie zlecenia produkcyjnego
description: "Ta procedura pokazuje sposób rozpoczynania zlecenia produkcyjnego na wydziale produkcji."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: a88968072b28ab468af97a875bd76d4d6abecfde
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="start-a-production-order"></a>Rozpoczynanie zlecenia produkcyjnego

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje sposób rozpoczynania zlecenia produkcyjnego na wydziale produkcji. W tym procesie jest zgłaszane zużycie materiału i czasu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Jest to piąta z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.


## <a name="start-a-production-order"></a>Rozpoczynanie zlecenia produkcyjnego
1. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
    * Zaznacz zlecenie produkcyjne, które ma stan Zwolniono.  
2. W okienku akcji kliknij opcję Zlecenie produkcyjne.
3. Kliknij przycisk Rozpocznij.
    * Na tej stronie można potwierdzić rozpoczęcie zlecenia produkcyjnego.  
4. Kliknij kartę Ogólne.
5. W polu Od nr operacji Nr wpisz „10”.
6. W polu Automatyczne zużycie marszruty zaznacz opcję „Zawsze”.
7. Zaznacz pole wyboru Księguj kartę marszruty teraz.
8. W polu Automatyczne zużycie BOM zaznacz opcję „Zawsze”.
9. Zaznacz pole wyboru Księgowanie listy pobrania.
10. Zaznacz pole wyboru Drukowanie listy pobrania.
11. Kliknij przycisk OK.
    * Jest to wydrukowana lista pobrania, która pokazuje materiały użyte w zleceniu produkcyjnym.  
12. Zamknij stronę.

## <a name="validate-the-picking-list"></a>Sprawdzanie poprawności listy pobrania
1. W okienku akcji kliknij pozycję Widok.
2. Kliknij opcję Lista pobrania.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. Kliknij przycisk Edytuj.
6. W polu Zużycie wprowadź liczbę.
7. Kliknij przycisk Księguj.
8. Kliknij przycisk OK.
    * W arkuszu listy pobrania są księgowane materiały zużyte przez zlecenie produkcyjne. Przed zaksięgowaniem arkusza można dokonać korekt, jeśli występuje różnica między oszacowaną ilością a rzeczywiście zużytą ilością.  
9. Kliknij kartę GridPanel.
10. Zamknij stronę.

## <a name="verify-the-route-card-journal"></a>Weryfikacja arkusza karty marszruty
1. W okienku akcji kliknij pozycję Widok.
2. Kliknij opcję Karta marszruty.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. Kliknij przycisk Edytuj.
6. W polu Godziny wpisz liczbę.
7. Kliknij przycisk Księguj.
8. Kliknij przycisk OK.
    * W arkuszu karty marszruty jest rejestrowany czas spędzony na poszczególnych operacjach. Mogą być również podawane ilości towarów prawidłowych i błędnych.  


