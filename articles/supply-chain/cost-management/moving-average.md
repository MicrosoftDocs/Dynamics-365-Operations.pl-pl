---
title: Średnia ruchoma
description: Średnia ruchoma to metoda kosztów ciągłych oparta na zasadzie średniej, a w której koszty wydań z magazynu nie zmieniają się po zmianie kosztu zakupu. Różnica jest kapitalizowana i oparta na obliczeniu proporcjonalnym. Pozostała kwota jest zaliczana w koszty.
author: AndersGirke
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0befa0e31347c9ee15ac0426fa3314b151a0200d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558860"
---
# <a name="moving-average"></a>Średnia ruchoma

[!include [banner](../includes/banner.md)]

Średnia ruchoma to metoda kosztów ciągłych oparta na zasadzie średniej, a w której koszty wydań z magazynu nie zmieniają się po zmianie kosztu zakupu. Różnica jest kapitalizowana i oparta na obliczeniu proporcjonalnym. Pozostała kwota jest zaliczana w koszty. 

Jeżeli używasz średniej ruchomej, rozliczenia zapasów i oznaczanie zapasów nie jest obsługiwane. Zamknięcie magazynu nie wpływa na produkty, które mają średnią ruchomą jako grupę modeli magazynu i nie generuje żadnych uzgodnień między transakcjami.

Poniżej przedstawiono wymagania wstępne stosowania ruchomego kosztu średniego jako metody wyceny.

1.  Na stronie **Grupy modeli pozycji** ustaw grupę modeli pozycji z ruchomym kosztem średnim wybranym w polu **model magazynu**. **Uwaga:** Domyślnie po wybraniu opcji Średnia ruchoma zaznaczane są także pola **Księguj magazyn fizyczny** i **Księguj magazyn finansowy**. 

2.  Na stronie **Księgowanie** przypisz konta do kont **Różnica cen dla średniej ruchomej** i **Przeszacowanie kosztu dla średniej ruchomej** na karcie **Zapasy**. Konta **Przeszacowanie kosztu dla średniej ruchomej** należy użyć, gdy koszt ma być zaliczony proporcjonalnie. Dzieje się tak z powodu różnic w kosztach między paragonem zakupu a fakturą zakupu oraz z powodu różnic między pierwotną ilością zapasów i bieżącą dostępną ilością zapasów. Użyj konta **Przeszacowanie kosztu dla średniej ruchomej**, aby dostosować ruchomy średni koszt produktu dla nowej ceny jednostkowej.
3.  Na stronie **zwolnionych produktów** należy przypisać grupę modeli pozycji z ruchomym kosztem średnim do produktu. **Uwaga:** Proces zamknięcia zapasów powoduje zamknięcie tylko okresu obrachunkowego. Nie wpływa na produkty, które mają przypisany ruchomy kosz średni w grupie modeli pozycji.

## <a name="convert-to-the-moving-average-costing-method"></a>Metoda konwertowania na ruchomy koszt średni
Produkty można przekonwertować, tak aby można było używać metody ruchomego kosztu średniego. Ten rodzaj konwersji wykonuje się na koniec roku, po zamknięciu ostatniego miesiąca bieżącego roku. Wykorzystuje się przy tym model bieżącego kosztu produktu. Metodę wyceny magazynu można zmienić z metody wyceny opartej na koszcie średnim lub standardowym na metodę opartą na średniej ruchomej. 

W przypadku zmiany metody wyceny ze standardowej na średnią ruchomą, należy wykonać następujące zadania:

1.  Wprowadzić korekty, aby sprowadzić ilości i wartości w magazynie do 0 (zera).
2.  Po sprowadzeniu wartości i ilości zapasów do 0 (zera), zmienić grupę modeli towarów na średnią ruchomą.
3.  Wprowadzić korekty, by przywrócić poprzednie wartości i ilości magazynie.

Nie możesz zmienić metody wyceny magazynu ze średniej ruchomej na FIFO, LIFO albo średnią ważoną.

**Uwaga:** Konwersja z kosztu standardowego na ruchomą średnią ważoną jest procesem ręcznym.

Poniższy przykład przedstawia wpływ zastosowania metody wyceny za pomocą średniej ruchomej. Dostępne są cztery konfiguracje:
-   Zamówienie zakupu i proporcjonalnie zaliczona różnica kosztów
-   Korekta produktu i zapasów dla średniej ruchomej
-   Średnia ruchoma z produkcją
-   Średnia ruchoma z transakcją przesunięcia

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>Zamówienie zakupu i proporcjonalnie zaliczona różnica kosztów
Za pomocą średniej ruchomej koszt produktu jest określany przez odbiór zakupu. Po zaksięgowaniu faktury zakupu, jeśli występuje różnica w kosztach między przyjęciem zakupu i fakturą zakupu, różnica proporcjonalnie korygowana do dla bieżących produktów w magazynie i wszelkie pozostałe kwoty są zaliczane w koszta. 

W tym przykładzie tworzy się i odbiera zamówienie zakupu z jednym kosztem, a fakturę zakupu księguje się z innym kosztem.

1.  Tworzenie zamówienia zakupu dla ilości równej 2 i ceny jednostkowej 10,00.
2.  Tworzenie przyjęcia zakupu produktu.
3.  Tworzenie zamówienia sprzedaży dla ilości równej 1 i ceny jednostkowej 10,00.
4.  Tworzenie faktury zakupu dla ilości równej 2 i ceny jednostkowej 12,00.

Różnica w cenie jednostkowej (2,00) jest księgowana jako Różnica cen dla konta średniej ruchomej, gdy faktura zakupu jest księgowana. Powodem jest to, że dwa produkty zostały kupione z kosztem 20,00. Jeden z produktów został sprzedany z ceną jednostkową 10,00. Faktura zakupu została zaksięgowana z kosztem jednostkowym 12 i ilością 2. Cena jednostkowa produktu nie może być zaksięgowana na poziomie 14,00.

## <a name="moving-average-product-and-inventory-adjustment"></a>Korekta produktu i zapasów dla średniej ruchomej
Jeśli musisz skorygować ruchomą średnią kosztu produktu, korekty magazynowe są dopuszczalne z dzisiejszą datą. Nie można postdatować korekty magazynowej w celu poprawienia ruchomej średniej kosztu produktu. Nie można mieć przepływu kosztu przez kolejne transakcje. 

W tym przykładzie ruchomy średni koszt jest korygowany dla produktu.

1.  Wybierz produkt, dla którego chcesz skorygować ruchomą średnią. **Uwaga:** Strona **Przeszacowanie średniej ruchomej** sprawdza dostępne zapasy produktu. Zaznaczony produkt ma zaksięgowana ilość 1, zaksięgowaną wartość 12,00, zaksięgowany koszt jednostkowy 12,00 i koszt jednostkowy 12,00.
2.  Zaktualizuj pole **Koszt jednostkowy** do wartości 16,00. System oblicza pozostałe pola.
3.  Korekta jest księgowana.

**Uwaga:** Można tylko skorygować ruchomy średni koszt z dzisiejszą datą.

Na stronie **Rozliczenia załącznika** widać korektę 4,00 zaksięgowaną dla konta Przeszacowanie kosztu dla średniej ruchomej.

## <a name="moving-average-with-production"></a>Średnia ruchoma z produkcją
Ruchoma średnia obsługuje produkowane towary. Jeśli planujesz używać ruchomej średniej w środowisku produkcyjnym, suwak **Użyj szacowanego kosztu własnego** na stronie **Parametry kontroli produkcji** musi być zaznaczony. To znaczy, że używana jest cena kosztu obliczona podczas oszacowania zamiast ceny kosztu z rzeczywistymi obliczeniami BOM.

## <a name="moving-average-with-a-backdated-transaction"></a>Średnia ruchoma z transakcją przesunięcia
Do postdatowanych transakcji przypisywany jest bieżący ruchomy średni koszt, fizyczna ilość produktu jest aktualizowana, ale ruchomy średni koszt produktu nie zmienia się. W tym przykładzie ruchomej średniej księgowana jest postdatowana transakcja dla średniego ruchomego produktu.

1.  Utwórz korektę zapasów dla ruchomego średniego produktu dla ilości 1 i kosztu 20,00.
2.  Historia transakcji magazynowych dla produktu będzie wyglądała następująco:
    -   Transakcja magazynowa 1, koszt 16,00, data księgowania 15 stycznia i data transakcji 15 stycznia.
    -   Korekta magazynowa 1, koszt 20,00, data księgowania 1 stycznia i data transakcji 15 stycznia.
3.  Zaksięguj korektę.

Na stronie **transakcje magazynowe** widać, że wartość 4,00 jest zaliczana w koszty, ponieważ bieżąca średnia ruchoma dla produktu wynosi 16,00. Można zaksięgować w przeszłości, ale różnica w koszcie jest zaliczana w koszty, więc ruchomy średni koszt pozostaje bez zmian.

## <a name="inventory-value-report"></a>Raport wartości zapasów
W tym przykładzie ruchomej średniej raport wartości zapasów jest drukowany w celu obsługi bieżącego obliczania ruchomej średniej dla produktu Raport Wartość zapasów może drukować transakcje w kolejności chronologicznej wraz z kosztem obsługi obliczania ruchomej średniej produktu. Raport wyświetla koszt ruchomej średniej dla produktu. W oknie dialogowym **Raporty wartości zapasów** opcja Zakres dat pozwala posortować raport według wartości **Godzina transakcji** lub **Data księgowania**. Tryb **Data księgowania** jest tradycyjnym wzorem drukowania raportu. Opcja **Czas transakcji** jest rzeczywistą datą zgłoszenia transakcji i ruchoma średnia kosztu dla produktu jest aktualizowana. Można wydrukować raport Wartości zapasów za pomocą opcji**Sortowania czasu transakcji**, jeśli ma być wyświetlone obliczanie ruchomego średniego kosztu na osi czasu. Poniższa tabela pokazuje transakcje dla produktu, dla których drukowany jest raport, gdy używana jest opcja **Sortowanie czasu transakcji**.

| Godzina transakcji | Data         | Typ transakcji           | Ilość | Kwota | Średni koszt jednostkowy |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 1 października    | Saldo początkowe          | 0        | 0,00   | 0,00              |
| 8 października        | 28 września | Postdatowane przyjęcie          | 1 przypada na wpłatę z zysku na rzecz budżetu państwa        | 16.00  | 16.00             |
| 3 października        | 3 października    | Przyjęcie zakupu           | 2        | 20,00  | 12,00             |
| 5 października        | 5 października    | Zamówienie sprzedaży                | -1       | -10,00 | 13.00             |
| 7 października        | 7 października    | Faktura zakupu           |          | 2,00   | 14.00             |
| 8 października        | 8 października    | Przeszacowanie średniej ruchomej |          | 4,00   | 16.00             |
|                  | 31 października   | Razem                      | 2        | 32.00  | 16.00             |

 **Uwaga:** Nie można uzgodnić księgi głównej z zapasami za pomocą opcji **Sortowanie czasu transakcji**. Raport musi być wydrukowany za pomocą opcji **Data księgowania**.





