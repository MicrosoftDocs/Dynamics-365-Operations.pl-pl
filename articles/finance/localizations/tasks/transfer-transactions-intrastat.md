---
title: Przesyłanie transakcji do systemu Intrastat
description: Ta procedura pokazuje, jak skonfigurować parametry systemu Intrastat i przesłać do niego transakcje.
author: Anasyash
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm, DeliveryReason, DeliveryTerms, DestinationCode
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c9a5037f9e5381c61b72947d85bf07d571fe094d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982101"
---
# <a name="transfer-transactions-to-the-intrastat"></a>Przesyłanie transakcji do systemu Intrastat

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak skonfigurować parametry systemu Intrastat i przesłać do niego transakcje. Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.


## <a name="create-new-and-update-existing-commodity-code"></a>Tworzenie nowego i aktualizowanie istniejącego kodu asortymentu
1. W okienku nawigacji otwórz **Moduły > Zarządzanie informacjami o produktach > Ustawienia > Kategorie i atrybuty > Hierarchie kategorii**.
2. Na liście znajdź lub zaznacz rekord **Kody asortymentu Intrastat**.
3. Na liście kliknij łącze w wybranym wierszu.
4. W drzewie zaznacz rekord. Na przykład wybierz **Intrastat\Głośnik**.  
5. Kliknij przycisk **Edytuj**.
6. Rozwiń skróconą kartę **Handel zagraniczny**.
7. W polu **Jednostki dodatkowe** wprowadź lub wybierz wartość. Na przykład wybierz opcję **szt.**.  
8. W polu **Waga nie ma zastosowania** zaznacz wartość **Tak**.
9. W drzewie zaznacz element **Intrastat**.
10. Kliknij węzeł kategorii **Nowy**.
11. W polu **Nazwa** wprowadź nazwę asortymentu. Na przykład wpisz **Inny towar**.  
12. W polu **Kod** wprowadź kod asortymentu. Na przykład wpisz **995 00 00**.  
13. W polu Przyjazna nazwa wpisz wartość. Na przykład wpisz **Inny**.  
14. Kliknij przycisk **Zapisz**.
15. Zamknij stronę.

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a>Przypisywanie kodu asortymentu do hierarchii produktów i zwolnionego produktu
1. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola **Nazwa** z wartością **sprzedaż**.
2. Na liście kliknij łącze w wybranym wierszu.
3. W drzewie rozwiń **węzeł kategorii**. Na przykład rozwiń węzeł **Hierarchia sprzedaży\Domowy zestaw audio**.  
4. W drzewie zaznacz **kategorię, którą chcesz przypisać do kodu asortymentu**. Na przykład zaznacz element **Hierarchia sprzedaży\Domowy zestaw audio\Głośniki.  
5. Rozwiń skróconą kartę **Kody asortymentu**.
6. Kliknij przycisk **Dodaj**.
7. W polu **Wybierz hierarchię** zaznacz opcję **Intrastat**.
8. Na liście znajdź i zaznacz kod asortymentu. Na przykład wybierz **920 20 34 Głośnik”**.  
9. Kliknij strzałkę w prawo, aby wybrać kod.
10. Kliknij przycisk **OK**.
11. W okienku nawigacji przejdź do opcji **Moduły > Zarządzanie informacjami o produktach > Produkty > Wydane produkty**.
12. Z listy wybierz zwolniony produkt, który przypiszesz do kodu asortymentu. Na przykład wybierz opcję **D0001**.  
13. Kliknij przycisk **Edytuj**.
14. Rozwiń skróconą kartę **Handel zagraniczny**.
15. W polu **Asortyment** wprowadź kod asortymentu. Na przykład wybierz wartość **920 20 34 Głośnik**.    
16. W polu **% opłat dodatkowych** wpisz liczbę. Na przykład wpisz **3**.  
17. W polu **Kraj/region** wprowadź lub wybierz kraj albo region pochodzenia. Na przykład zaznacz **AUT**.  
18. Rozwiń skróconą kartę **Zapasy**.
19. W polu **Waga netto** wpisz wagę w kg. Na przykład wpisz **2.5**.  
20. Kliknij przycisk **Zapisz**.

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a>Konfigurowanie kodów transakcji Intrastat i parametrów handlu zagranicznego
1. W okienku nawigacji otwórz **Moduły > Podatek > Ustawienia > Handel zagraniczny > Kody transakcji**.
2. Kliknij przycisk **Nowy**.
3. W polu **Kod transakcji** wpisz wartość. Na przykład wpisz **21** jako kod transakcji używanej do wykonania zwrotu.  
4. W polu **Nazwa** wpisz nazwę kodu transakcji. Na przykład wpisz **Zwrot**.  
5. W polu **Kwota statystyczna** wybierz opcję. Na przykład zaznacz opcję **Puste**, co wskaże, że wartości statystyczna, która ma być raportowana dla transakcji o kodzie transakcji **21**, zawsze będzie równa zero.  
6. W okienku nawigacji otwórz **Moduły > Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego**.
7. W polu **Kod transakcji** wpisz lub wybierz wartość. Na przykład zaznacz **11**.  
8. W polu **Faktura korygująca** wprowadź lub wybierz wartość. Ta wartość określa również fizyczny zwrot. Faktura korygująca na fizyczny zwrot zostanie przesłana do dziennika systemu Intrastat z zastosowaniem przeciwnego kierunku. Na przykład zwrot przyjęcia jest przenoszony jako wysyłka.   Natomiast faktura korygująca jest traktowana jako korekta i przenoszona z zastosowaniem tego samego kierunku, ale przeciwnego znaku. Na przykład korekta przyjęcia jest przenoszona jako przyjęcie z kwotą ujemną, a flaga aktywności jest ustawiana na **Korekta**.  
9. Rozwiń skróconą kartę **Przenoszenie**.
10. W polu **Pozycje z kodem asortymentu** zaznacz opcję **Tak**. Wybierz tę opcję, aby przenieść tylko transakcje z przypisanym kodem asortymentu. Transakcje bez kodu asortymentu nie będą przenoszone do systemu Intrastat.  
11. W polu **Przenieś, jeśli spełnione kryterium dla** wybierz opcję. Na przykład wybierz wartość **Jeden z wybranych**.  
12. Rozwiń sekcję **Hierarchia kodów asortymentu**.
13. Kliknij kartę **Właściwości kraju/regionu**.
14. Kliknij przycisk **Nowy**.
15. W polu **Kraj/region** wprowadź lub wybierz wartość. Na przykład wybierz wartość **FRA**.  
16. W polu **Kod Intrastat** wprowadź kod ISO kraju.  Na przykład wpisz **FR**.  
17. W polu **Typ kraju/regionu** wybierz opcję **UE**.
18. Kliknij kartę Sekwencje numerów.

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a>Konfigurowanie metod dostawy i reguł uwzględniania opłat w raportowaniu Intrastat
1. W okienku nawigacji otwórz **Moduły > Sprzedaż i Marketing > Ustawienia > Dystrybucja > Tryby dostawy**.
2. Na liście znajdź i zaznacz odpowiedni rekord. Na przykład wybierz wartość **20 Lotniczy**.  
3. Rozwiń skróconą kartę **Handel zagraniczny**.
4. Kliknij przycisk **Edytuj**.
5. W polu **Transport** wprowadź lub wybierz wartość. Na przykład zaznacz **02**.  
6. W okienku nawigacji otwórz **Moduły > Rozrachunki z odbiorcami > Ustawienia opłat > Kod opłat**.
7. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Kod opłat z wartością **fracht**.
8. Rozwiń skróconą kartę **Handel zagraniczny**.
9. Kliknij przycisk **Edytuj**.
10. W polu **Wartość faktury dla Intrastat** zaznacz opcję **Tak**. Kwota zostanie przeniesiona do pola **Opłaty faktury** i zsumowana z kwotą przeniesioną do pola Kwota faktury. W polu **Wartość statystyczna Intrastat** wybierz opcję **Tak**, jeśli kwota opłat musi zostać przeniesiona do pola **Opłaty statystyczne** i zsumowana z wartością pola **Kwota statystyczna**.  

## <a name="sell-products-for-eu-customers"></a>Sprzedaż produktów do odbiorców w UE
1. W okienku nawigacji otwórz **Moduły > Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia zakupu**.
2. Kliknij przycisk **Nowy**.
3. W polu **Konto odbiorcy** zaznacz odbiorcę z UE. Na przykład wybierz wartość **DE 012 Litware Retail**.  
4. Rozwiń skróconą kartę **Dostawa**.
5. W polu **Metoda dostawy** wprowadź lub wybierz wartość. Na przykład wybierz wartość **20 Lotniczy**.  
6. Kliknij przycisk **OK**.
7. Wybierz pierwszy wiersz wierszy zamówienia sprzedaży.
8. W polu **Kod towaru** wpisz lub wprowadź wartość. Na przykład zaznacz **D001**.  
9. Rozwiń skróconą kartę **Szczegóły wiersza**.
10. Kliknij kartę **Handel zagraniczny**. Pole transportu jest wypełniane automatycznie na podstawie wybranej metody dostawy.  
11. W polu **Port** wprowadź lub wybierz wartość.
12. Kliknij opcję **Finanse**. Zgodnie z ustawieniami ta kwota będzie dodana do pola **Wartość faktury dla Intrastat**.  
13. Kliknij opcję **Obsługuj opłaty**.
14. W polu **Kod opłat** wprowadź lub wybierz wartość. Na przykład wybierz wartość **FRACHT**.  
15. Zaznacz pole wyboru **Zachowaj**.
16. W polu **Wartość opłat** wprowadź liczbę. Na przykład wpisz **10**.  
17. Kliknij przycisk **Zapisz**.
18. Zamknij stronę.
19. W okienku akcji kliknij pozycję **Faktura**.
20. Kliknij opcję **Faktura**.
21. Rozwiń sekcję **Parametry**.
22. W polu **Ilość** zaznacz opcję **Wszystko**.
23. Rozwiń skróconą kartę **Konfiguracja**.
24. W polu **Data faktury** wprowadź datę. Na przykład wpisz **2015-01-31**.  
25. Kliknij przycisk **OK**.
26. Kliknij przycisk **OK**.
27. Zamknij stronę.
28. Kliknij przycisk **Nowy**.
29. W polu **Konto odbiorcy** zaznacz odbiorcę z UE. Na przykład wybierz wartość **DE-013 Trey Wholesales**.
30. Kliknij przycisk **OK**.
31. W polu **Kod towaru** wpisz lub wprowadź wartość. Na przykład zaznacz **D0001**.  
32. Kliknij przycisk **Zapisz**.
33. Kliknij opcję **Faktura**.
34. W polu **Data faktury** wprowadź datę. Na przykład wpisz datę **2015-01-31**.  
35. Kliknij przycisk **OK**.
36. Kliknij przycisk **OK**.

## <a name="transfer-transactions-to-the-intrastat"></a>Przesyłanie transakcji do systemu Intrastat
1. W okienku nawigacji otwórz **Moduły > Podatek > Deklaracje > Handel zagraniczny > Intrastat**.
2. Kliknij przycisk **Przeniesienie**.
3. W polu **Faktura dla odbiorcy** zaznacz opcję **Tak**.
4. Kliknij przycisk **Filtr**.
5. Na liście zaznacz wiersz z **datą**.
6. W polu **Kryteria** wpisz wartość. Na przykład wprowadzić filtru na okres stycznia 2015 r. (dokładna wartość zależy od formatu daty): 1.1.2015..31.1.2015  
7. Kliknij przycisk **OK**.
8. Kliknij przycisk **OK**.
9. Na liście znajdź i zaznacz przeniesiony rekord.
10. Kliknij kartę **Ogólne**.
    
Przejrzyj przeniesione dane, w tym kraj/region miejsca docelowego/wysyłki, kraj pochodzenia, wagę, ilość, ilość w jednostkach dodatkowych, oznaczenie asortymentu, kod transakcji, kwoty na fakturach i kwoty statystyczne. W razie potrzeby można zmodyfikować te dane.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]