---
title: "Rezerwowanie ilości zapasów"
description: "W tym temacie opisano różne dostępne opcje rezerwowania zapasów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 207264
ms.assetid: 47537e4f-cdf6-4813-96fd-c945b2dfe9d4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 942a1e9ddcf6e0952da66b239e1884cb83369175
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="reserve-inventory-quantities"></a>Rezerwowanie ilości zapasów

[!include[banner](../includes/banner.md)]


W tym temacie opisano różne dostępne opcje rezerwowania zapasów.

Istnieje możliwość automatycznego rezerwowania ilości zapasów dla określonego zamówienia sprzedaży. Oznacza to, że zarezerwowane zapasy nie mogą być wycofywane z magazynu dla innych zamówień, chyba że rezerwacja lub część rezerwacji zostanie anulowana.

Istnieje kilka przyczyn rezerwowania zapasów:
-   Pierwszy zamówiony — pierwszy dostarczony: oznacza to, że odbiorcy otrzymują dostępne towary w tej samej kolejności, w jakiej składali zamówienia.
-   Niedobory towarów na skutek długiego lub nieznanego czasu dostawy od dostawcy. Rezerwując towar, zapewniasz, że określeni odbiorcy otrzymają dostawę, gdy tylko towary będą dostępne.
-   Określeni odbiorcy i określone typy zamówień mają wyższy priorytet dostawy.
-   Towary z numerami seryjnymi i numerami partii. Można oznaczyć określone towary, które zostały lub zostaną dostarczone na określone zamówienia.
-   Towary specjalnie zamawiane, które są rezerwowane na specjalne zamówienia.
-   Zlecenia produkcyjne. Można na przykład oznaczyć towary, które są produkowane i dostosowywane do określonych zamówień.

Zapasy można rezerwować automatycznie, gdy tworzony jest nowy wiersz zamówienia, lub towary można rezerwować ręcznie w poszczególnych zamówieniach. Istnieje również możliwość rezerwowania zapasów na różnych etapach procesu produkcji. Rezerwować można tylko produkty magazynowane. Usług nie można rezerwować, ponieważ nie istnieją dostępne zapasy. Można rezerwować towary fizycznie dostępne oraz już zamówione, ale jeszcze nie odebrane. W przypadku rezerwowania ilości przekraczającej ilość towarów dostępnych pojawia się komunikat informujący o tym, że nie jest możliwe zarezerwowanie tak dużej ilości. Można wtedy zarezerwować tę ilości mimo ostrzeżenia lub zmienić zamawianą ilość. Ilość można zarezerwować lub zmienić. Jeżeli rezerwowana jest większa liczba towarów niż dostępna, niedobory zostaną pokryte, gdy towary będą dostępne dla dostaw.

## <a name="inventory-reservation-policies"></a>Zasady rezerwacji zapasów
Zasady rezerwacji zapasów są ustawiane na stronach **Grupy modeli pozycji**, **Parametry modułu Zarządzanie zapasami i magazynem** i **Parametry produkcji**.
### <a name="policies-on-the-item-model-groups-page"></a>Zasady na stronie Grupy modeli pozycji

Sekcja **Zasady zapasów** zawiera następujące zasady rezerwacji.
|                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Zasada rezerwacji**  | **Opis**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| FIFO z kontrolą daty    | Wybranie opcji **FIFO z kontrolą daty** spowoduje, że rezerwacja zapasów jest kontrolowana przez datę sortowania zgodnie z regułą FIFO. Partie są rezerwowane na podstawie najwcześniejszej daty przyjęcia towarów zgodnie z zasadą „pierwszy na wejściu, pierwszy na wyjściu” FIFO.                                                                                                                                                                                                                                                                       |
| Wstecz od daty wysyłki | Ta opcja staje się dostępna po wybraniu opcji **FIFO z kontrolą daty**. Wybranie opcji **Wstecz od daty wysyłki** spowoduje, że zapasy są rezerwowane wstecz od żądanej daty wysyłki zgodnie z zasadą „ostatni na wejściu, pierwszy na wyjściu” (LIFO). Jeśli nie nastąpiły żadne przyjęcia przed datą wysyłki, stosowana jest rezerwacja FIFO.                                                                                                                                                                                                           |
| Rezerwacja sprzedaży pozycji  | Określa, czy rezerwacja towarów odbywa się ręcznie, czy automatycznie. W rezerwacji automatycznej zapasy są rezerwowane podczas tworzenia wierszy zamówień. Istnieje możliwość dokonywania rezerwacji na poziomie numeru towaru dla list składowych (opcja **Automatycznie**) lub dla poszczególnych elementów listy składowej (opcja **Rozłożenie**). Wartość domyślna zasady **Rezerwacja sprzedaży pozycji** może być dziedziczona ze strony **Parametry modułu rozrachunków z odbiorcami**. Na tej stronie wartość ustawia się w polu Rezerwacja w sekcji **Wartości domyślne sprzedaży** **na** karcie **Ogólne**. |
| Wybór tej samej partii    | Rezerwacja tej samej partii umożliwia rezerwowanie zapasu dla wiersza zamówienia sprzedaży z jednej partii zapasów. Jeśli chcesz użyć tej opcji, należy także w opcji **Konsoliduj zapotrzebowanie** ustawić wartość **Tak**. Istnieją dodatkowe ustawienia, które są wymagane dla grup wymiarów śledzenia i wymiarów magazynowania. Aby uzyskać więcej informacji, zobacz [Rezerwowanie takiej samej partii na potrzeby zamówienia sprzedaży](../sales-marketing/reserve-same-batch-sales-order.md).                                                          |
| Konsoliduj zapotrzebowanie | Ta opcja jest podobna do opcji **Wybór tej samej partii**. Konsoliduje zapasy zarezerwowane dla wierszy zamówienia sprzedaży w jedno zapotrzebowanie.                                                                                                                                                                                                                                                                                                                                                                                      |
| FEFO z kontrolą daty    | Ta opcja umożliwia rezerwowanie partii będących blisko daty ważności lub przydatności. Należy także w polu **Kryteria pobierania** wybrać wartość **Data ważności** lub **Data przydatności**.                                                                                                                                                                                                                                                                                                                              |

#### <a name="example-for-fifo-date-controlled-and-backward-from-ship-date"></a>Przykład dla opcji FIFO z kontrolą daty i Wstecz od daty wysyłki

W tym przykładzie dostępne zapasy towaru o numerze A istnieją dla trzech różnych numerów partii.
| Numer towaru | Numer partii | Ilość | Data             |
|-------------|--------------|----------|------------------|
| A           | 1000         | 5        | 2 lutego 2016 |
| A           | 1001         | 3        | 1 stycznia 2016  |
| A           | 1002         | 7        | 3 marca 2016    |

Zamówienie sprzedaży, które powinno być automatycznie zarezerwowane i dostarczone w dniu 4 kwietnia 2016 r., rezerwuje następującą partię:
-   Jeśli są wyczyszczone oba pola wyboru **FIFO z kontrolą daty** i **Wstecz od daty wysyłki**, jest rezerwowana partia 1000, ponieważ jest to partia z najniższym numerem.
-   Jeśli pole wyboru **FIFO z kontrolą daty** jest zaznaczone, a pole **Wstecz od daty wysyłki** wyczyszczone, jest rezerwowana partia 1001, ponieważ jest to partia z pierwszą datą przyjęcia (FIFO).
-   Jeśli są zaznaczone oba pola wyboru **FIFO z kontrolą daty** i **Wstecz od daty wysyłki**, jest rezerwowana partia 1002, ponieważ jest to partia z datą przyjęcia najbliższą dacie wysyłki zamówienia sprzedaży.

### <a name="policies-on-the-inventory-and-warehouse-management-parameter-page"></a>Zasady na stronie Parametry modułu Zarządzanie zapasami i magazynem

Na stronie **Parametry modułu Zarządzanie zapasami i magazynem** są dwie opcje związane z rezerwacjami:
-   Opcja **Rezerwacja zamówionych pozycji** na karcie **Ogólne** umożliwia rezerwowanie przyjęć towarów, które zostały zamówione na podstawie wydań towarów w modułach Rozrachunki z odbiorcami, Zarządzanie projektami i ich księgowanie oraz Kontrola produkcji. Jeśli ta opcja jest wyczyszczona, można rezerwować tylko te towary, które zostały fizycznie przyjęte. Jeśli dla określonego towaru ustawiono opcję akceptowania ujemnego poziomu zapasów, to pole nie ma znaczenia.
-   Opcja **Rezerwuj pozycje automatycznie** na karcie **Transport** określa domyślne ustawienie, jeśli towary są automatycznie rezerwowane dla zamówień przeniesienia. Ustawienie domyślne można zastąpić w poszczególnych zamówieniach przeniesienia.

### <a name="inventory-reservation-policies-on-the-production-parameters-page"></a>Zasady rezerwacji zapasów na stronie Parametry produkcji

Wartość pola **Rezerwacja** na karcie **Ogólne** na stronie **Parametry produkcji** określa domyślny punkt w procesie produkcji, gdzie powinny być rezerwowane zapasy. Na przykład zapasy mogą być rezerwowane podczas planowania lub rozpoczynania pracy.




