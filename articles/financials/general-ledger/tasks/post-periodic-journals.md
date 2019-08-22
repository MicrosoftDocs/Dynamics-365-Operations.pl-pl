---
title: Księgowanie arkuszy okresowych
description: Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas pobierania arkusza.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 241023c36723fa2dba5646e997b649741142c0ad
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834957"
---
# <a name="post-periodic-journals"></a>Księgowanie arkuszy okresowych

[!include [task guide banner](../../includes/task-guide-banner.md)]

Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas pobierania arkusza. Podczas tworzenia arkusza okresowego należy określić interwał okresu dla cyklu, taki jak dni lub miesiące. W tym przewodniku po zadaniach zostanie utworzony arkusz okresowy o cyklu miesięcznym.



1. Wybierz kolejno opcje Księga główna > Zadania okresowe > Arkusze okresowe.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wprowadź lub wybierz wartość.
4. Na liście kliknij łącze w wybranym wierszu.
5. Wypełnij pole Opis.
    * Opisem po późniejszym pobraniu będzie nazwa arkusza okresowego, dlatego nadaj mu nazwę charakterystyczną.  
6. Kliknij przycisk Wiersze.
    * Arkusz okresowy zazwyczaj będzie zawierał kilka wierszy arkusza. W tym przewodniku po zadaniach będzie jednak dodany tylko jeden wiersz.  
7. W polu Data wprowadź datę.
    * Pole Data zawiera datę księgowania następnego przeniesienia do arkusza dziennego. Dla arkuszy, które będą pobierane każdego miesiąca, zaleca się używanie daty w miesiącu księgowania, czyli zazwyczaj pierwszej lub ostatniej daty w okresie. Istnieje możliwość pozostawienia pola Data pustego i podania daty w trakcie pobierania arkusza przy użyciu pola Pusta data.    To pole jest automatycznie aktualizowane o następną datę wynikającą z cyklu w trakcie pobierania transakcji.  
8. W polu Konto podaj żądane wartości.
9. Wypełnij pole Opis.
10. Zamknij stronę.
11. W polu Debet wpisz liczbę.
12. W polu Konto przeciwstawne podaj żądane wartości.
13. W polu Jednostka zaznacz opcję „Miesiące”.
14. W polu Liczba jednostek wpisz wartość „1”.
15. W polu Ostatnia data wprowadź datę.
    * Wprowadzanie ostatniego dnia z poprzedniego okresu zapobiegnie omyłkowemu tworzeniu arkusza cyklicznego w nieprawidłowym okresie początkowym. Ostatni dzień będzie później aktualizowany każdorazowo podczas pobierania arkusza okresowego.  
16. Kliknij przycisk Zapisz.
17. Przejdź do domyślnego pulpitu nawigacyjnego.
18. Wybierz kolejno opcje Księga główna > Wpisy w arkuszu > Arkusze finansowe.
19. Kliknij przycisk Nowy.
20. W polu Nazwa wprowadź lub wybierz wartość.
21. Na liście znajdź i zaznacz odpowiedni rekord.
22. Na liście kliknij łącze w wybranym wierszu.
23. Wypełnij pole Opis.
24. Kliknij przycisk Wiersze.
25. Kliknij opcję Arkusz okresowy.
26. Kliknij opcję Wczytanie z arkusza okresowego.
27. Wprowadź datę w polu Do dnia.
    * Pole Do dnia jest używane jako data graniczna dla okresowych wierszy załącznika. Zależnie od ustawienia cyklu wartości Ostatnia data i Do dnia dotyczące tego samego wiersza można umieścić więcej niż jeden raz w powstałym arkuszu. Pole Do dnia jest automatycznie aktualizowane na podstawie daty sesji z ostatniego razu, gdy wiersz okresowy był przenoszony do arkusza.  
28. W polu Numer arkusza okresowego wprowadź lub wybierz wartość.
29. Na liście kliknij łącze w wybranym wierszu.
30. Kliknij przycisk OK.
    * Arkusz okresowy może teraz zostać przejrzany, zatwierdzony lub zaksięgowany, w zależności od wymagań i konfiguracji.  

