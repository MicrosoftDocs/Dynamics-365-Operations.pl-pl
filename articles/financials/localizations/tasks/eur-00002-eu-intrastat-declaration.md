---
title: EUR-00002 Generowanie unijnej deklaracji Intrastat
description: Ta procedura przeprowadzi przez kolejne czynności, które należy wykonać, aby wyeksportować deklarację Intrastat w formacie pliku elektronicznego i przejrzeć dane deklaracji w formacie programu Excel.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, IntrastatParameters, IntrastatCommodityLookup, IntrastatCompressParameters, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1236f27a3a5c208ffec41374a6593d1f0e7c4433
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "371495"
---
# <a name="eur-00002-generate-an-eu-intrastat-declaration"></a>EUR-00002 Generowanie unijnej deklaracji Intrastat

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przeprowadzi przez kolejne czynności, które należy wykonać, aby wyeksportować deklarację Intrastat w formacie pliku elektronicznego i przejrzeć dane deklaracji w formacie programu Excel. 

Aby można było wykonać tę procedurę, należy przenieść transakcje do systemu Intrastat. 

Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.


## <a name="import-configurations-with-settings"></a>Importowanie konfiguracji z ustawieniami
1. Wybierz kolejno opcje Obszary robocze > Raportowanie elektroniczne
2. Kliknij opcję Ustaw jako aktywny.
3. Kliknij Repozytoria.
4. Kliknij przycisk Otwórz.
5. Otwórz filtr kolumny Nazwa konfiguracji.
6. Zastosuj filtr w polu „Nazwa konfiguracji” z wartości „Intrastat (DE)”, używając operatora filtru „zaczyna się od”.
    * Wybierz nazwę konfiguracji mającą zastosowanie do kraju firmy. Ta procedura wykorzystuje przykładową firmę niemiecką (DEMF), dlatego należy wybrać opcję „Intrastat (DE)”.  
    * Kliknij kolejno przyciski Importuj i Tak.  
7. Otwórz filtr kolumny Nazwa konfiguracji.
8. Zastosuj filtr w polu „Nazwa konfiguracji” z wartości „raport intrastat”, używając operatora filtru „zaczyna się od”.
    * Kliknij kolejno przyciski Importuj i Tak.  

## <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego
1. Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego
2. Rozwiń sekcję Raportowanie elektroniczne.
3. W polu Mapowanie formatu plików wprowadź lub wybierz wartość Intrastat (DE).
4. W polu Mapowanie formatu raportów wprowadź lub wybierz wartość Raport Intrastat.
5. Rozwiń sekcję Reguły zaokrąglania.
    * Należy skonfigurować reguły zaokrąglania, które mają zastosowanie w danym kraju/regionie na potrzeby raportowania Intrastat.  
6. W polu Reguła zaokrąglania wprowadź liczbę.
    * Wprowadź dokładność zaokrąglania, na przykład „0,01”.  
7. W polu Liczba miejsc dziesiętnych kwoty wpisz liczbę.
    * Na przykład wpisz „2”.  
8. W polu Zaokrąglanie poniżej 1 kg wybierz opcję.
    * Na przykład wybierz opcję „Zaokrąglanie do 1 kg”.  
9. W polu Reguła zaokrąglania wprowadź liczbę.
    * Na przykład wpisz „1”, aby zaokrąglać wagę do liczby całkowitej.  
10. Rozwiń sekcję Dolny limit.
11. W polu Waga wprowadź liczbę.
    * Na przykład wpisz „10” jako minimalną wagę.  
12. W polu Kwota wpisz liczbę.
    * Na przykład wpisz „200” jako minimalną kwotę.  
13. W polu Asortyment wprowadź lub wybierz wartość.

## <a name="set-up-compression-of-intrastat"></a>Ustawianie kompresji Intrastat
1. Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Kompresja Intrastat.
2. Kliknij przycisk Usuń.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * Na przykład w sekcji Dostępne wybierz asortyment.  
4. Kliknij przycisk Dodaj.

## <a name="generate-intrastat-declaration"></a>Generowanie deklaracji Intrastat
1. Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat
2. Kliknij przycisk Sprawdź poprawność.
    * Sprawdzanie poprawności odbywa się zgodnie z zawartością pola Sprawdzenie ustawień na stronie Parametry handlu zagranicznego.  
3. Kliknij przycisk OK.
4. Kliknij przycisk Aktualizuj.
5. Kliknij opcję Dolny limit.
6. W polu Data początkowa wprowadź datę.
    * Na przykład wpisz 1 stycznia 2015 r.  
7. W polu Kompresuj wybierz opcję Tak.
8. W polu Data końcowa wprowadź datę.
    * Na przykład wpisz 31 stycznia 2015 r.  
9. Kliknij przycisk OK.
10. Kliknij przycisk Aktualizuj.
11. Kliknij opcję Kompresuj.
    * Ta kompresja odbywa się zgodnie z konfiguracją kompresji ustawień raportowania Intrastat.  
12. W polu Data początkowa wprowadź datę.
    * Na przykład wpisz 1 stycznia 2015 r.  
13. W polu Data końcowa wprowadź datę.
    * Na przykład wpisz 31 stycznia 2015 r.  
14. Kliknij przycisk OK.
15. Kliknij przycisk Aktualizuj.
16. Kliknij opcję Ponowne generowanie numerów sekwencyjnych.
17. Kliknij przycisk OK.
18. Kliknij opcję Dane wyjściowe.
19. Kliknij przycisk Raport.
20. W polu Od dnia wprowadź pierwszy dzień okresu raportowania.
    * Na przykład ustaw datę 1 stycznia 2015 r.  
21. Wprowadź datę w polu Do dnia.
    * Na przykład wpisz 31 stycznia 2015 r.  
22. W polu Generuj plik zaznacz opcję Tak.
23. W polu Nazwa pliku wpisz wartość.
24. W polu Generuj raport zaznacz opcję Tak.
25. W polu Nazwa pliku raportu wpisz wartość.
26. W polu Kierunek wybierz opcję.
    * Na przykład wybierz opcję „Wysyłki”.  
27. Kliknij przycisk OK.

