---
title: Księgowanie arkuszy okresowych
description: Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas pobierania arkusza.
author: aprilolson
ms.date: 11/21/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bdc1d9f67a515e3cdc45e173b88982feceb0ebfd
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799394"
---
# <a name="post-periodic-journals"></a>Księgowanie arkuszy okresowych

[!include [banner](../../includes/banner.md)]

Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas pobierania arkusza. Podczas tworzenia arkusza okresowego należy określić interwał okresu dla cyklu, taki jak dni lub miesiące. W Okienku nawigacji otwórz Moduły > Księga główna > Zadania okresowe > Generowanie arkuszy.

1. W Okienku nawigacji otwórz **Moduły > Księga główna > Zadania okresowe > Arkusze okresowe**.
2. Kliknij przycisk **Nowy**.
3. W polu **Nazwa** wprowadź lub wybierz wartość.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu **Opis** wpisz wartość. Opisem po późniejszym pobraniu będzie nazwa arkusza okresowego, dlatego nadaj mu nazwę charakterystyczną.
6. W **okienku akcji** kliknij pozycję **Wiersze**. Arkusz okresowy zazwyczaj będzie zawierał kilka wierszy arkusza. W tym przewodniku po zadaniach będzie jednak dodany tylko jeden wiersz.
7. W polu **Data** wprowadź datę. Pole **Data** zawiera datę księgowania następnego przeniesienia do arkusza dziennego. Dla arkuszy, które będą pobierane każdego miesiąca, zaleca się używanie daty w miesiącu księgowania. Zazwyczaj jest to pierwsza lub ostatnia data w okresie. Wykorzystując pole **Data pusta**, można pozostawić pole **Data** puste i podać datę pobrania dziennika. To pole jest aktualizowane o następną datę wynikającą z cyklu w trakcie pobierania transakcji. 
8. W polu **Konto** podaj żądane wartości.
9. Wprowadź lub wybierz wartość w polu **Opis**.
10. Zamknij stronę.
11. W polu **Debet** wpisz liczbę.
12. W polu **Konto przeciwstawne** podaj żądane wartości.
13. W polu **Jednostka** zaznacz opcję **Miesiące**.
14. W polu **Liczba jednostek** wpisz wartość **1**.
15. W polu **Ostatnia data** wprowadź datę. Wprowadzanie ostatniego dnia z poprzedniego okresu zapobiegnie omyłkowemu tworzeniu arkusza cyklicznego w nieprawidłowym okresie początkowym. Ostatni dzień będzie później aktualizowany każdorazowo podczas pobierania arkusza okresowego. 
16. Kliknij przycisk **Zapisz**.
17. Otwórz **Okienko nawigacji > Moduły > Księga główna > Wpisy w arkuszu > Arkusze finansowe**.
18. Kliknij przycisk **Nowy**.
19. W polu **Nazwa** wprowadź lub wybierz wartość.
20. Na liście znajdź i zaznacz odpowiedni rekord.
21. Na liście kliknij łącze w wybranym wierszu.
22. W polu **Opis** wpisz wartość.
23. W **okienku akcji** kliknij pozycję **Wiersze**.
24. W **Okienku akcji** kliknij **Arkusze okresowe**.
25. Kliknij opcję **Wczytanie z arkusza okresowego**.
26. Wprowadź datę w polu **Do dnia**. Pole **Do dnia** jest używane jako data graniczna dla okresowych wierszy załącznika. Zależnie od ustawienia cyklu wartości **Ostatnia data** i **Do dnia** dotyczące tego samego wiersza można umieścić więcej niż jeden raz w powstałym arkuszu. Pole **Do dnia** jest automatycznie aktualizowane na podstawie daty sesji z ostatniego razu, gdy wiersz okresowy był przenoszony do arkusza. 
27. W polu **Numer arkusza okresowego** wprowadź lub wybierz wartość.
28. Na liście kliknij łącze w wybranym wierszu.
29. Kliknij przycisk **OK**. Arkusz okresowy może teraz zostać przejrzany, zatwierdzony lub zaksięgowany, w zależności od wymagań i konfiguracji.   


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
