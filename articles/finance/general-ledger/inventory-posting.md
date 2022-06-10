---
title: Księgowanie zapasów
description: W tym temacie omówiono zakładkę Umieszczanie zapasów na stronie profilu Umieszczanie zapasów.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 464ffccd658003271b517038f430914fd5d8d50e
ms.sourcegitcommit: 6744cc2971047e3e568100eae338885104c38294
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/20/2022
ms.locfileid: "8783374"
---
# <a name="inventory-posting"></a>Księgowanie zapasów

Zakładka **Zapassy** na stronie **Profile księgowania zapasów** służy do kontrolowania sposobu księgowania transakcji inwentaryzacyjnych w księdze głównej. Transakcje inwentaryzacyjne to transakcje, które nie są tworzone na podstawie zleceń sprzedaży, zamówień zakupu czy zleceń produkcyjnych. Automatycznie umieszczają one w inwentarzu jednocześnie aktualizacje fizyczne i finansowe. Jednym z wyjątków są zlecenia transferowe, które oddzielają aktualizacje fizyczne i finansowe w momencie wysyłki i odbioru zapasów.

Poniższa tabela przedstawia kilka przykładów transakcji inwentaryzacyjnych.

| Typ transakcji | Odbiór lub wydanie | Delegowanie fizyczne, delegowanie finansowe lub oba | Opis |
|---|---|---|---|
| Transakcje | Obie | Obie | <p>arkusz ruchów jest arkuszem zapasów, którego możesz używać do dodawania i usuwania zapasów. Działa to podobnie jak arkusz korekty stanów magazynowych. Kluczową różnicą jest jednak to, że określane jest główne konto, które kompensuje wpis.</p><p>W dzienniku ruchów wprowadza się salda początkowe oraz jednorazowe korekty, które muszą być ujęte w kosztach. Używa się go na przykład, gdy usuwane są zapasy dla próbki sprzedaży.</p><p>Gdy arkusz jest księgowany, aktualizacje fizyczne i finansowe następują jednocześnie.</p><p>Ilości dodatnie w wierszach arkusza oznaczają wpływy, a ilości ujemne – wydania.</p> |
| Korekta zapasów | Obie | Obie | arkusz korekt inwentaryzacji służy do dodawania lub usuwania zapasów. Nie pozwala wybrać konta offsetowego. Do aktualizacji wpisu do księgi głównej używane są tylko konta, które zostały określone na stronie **Profil księgowania zapasów**. |
| Przelew (dziennik) | Obie | Obie | <p>arkusz transferowy jest używany do przenoszenia zapasów z jednej lokalizacji do drugiej (przy użyciu wymiarów magazynowych). Aktualizuje informacje o produkcie podczas transakcji magazynowej, podając nowe wymiary produktu lub wymiary śledzenia.</p><p>arkusz transferowy tworzy jeden wiersz dla ruchu pozycji. Ten wiersz zawiera pola "od" i "do" dla wymiarów zapasów. Każdy wiersz w dzienniku transferowym tworzy dwie transakcje inwentaryzacyjne. Dla wymiarów zapasów "od" tworzona jest jedna transakcja. Reprezentuje problem i ma wartość ujemną. Druga transakcja jest tworzona dla wymiarów zapasów "do". Reprezentuje on wpływy i ma wartość dodatnią.</p><p>arkusze przeniesienia mogą nie tworzyć kuponów, jeśli przeniesienie zapasów jest traktowane jako przeniesienie niefinansowe. Wymiary inwentaryzacji, które różnią się wartościami "od" i "do", nie są oznaczone opcją **Inwentaryzacja finansowa** na stronie **Grupy wymiarów magazynowania** lub **Grupy wymiarów śledzenia**. Na przykład, jeśli opcja **Zapasy finansowe** nie jest zaznaczona na wymiarze **Miejsce**, a przenosisz zapasy z jednej lokalizacji do innej w tym samym miejscu i magazynie, nie zostanie utworzony żaden voucher.</p><p>arkusze transferowe różnią się od zleceń transferowych tym, że nie ma w nich dokumentów potwierdzających ruch. Aktualizacji dokonuje się w ramach jednej transakcji poprzez zaksięgowanie arkusza. Natomiast polecenie przelewu może generować dokumenty kompletacji i wysyłki, a do przetworzenia transakcji wymaga dwóch aktualizacji.</p> |
| Wysyłka zamówienia przeniesienia | Problem | Obie | <p>Kiedy tworzysz nowe zlecenie transferu, każda kombinacja wiersza i wymiaru inwentaryzacji ma dwie transakcje inwentaryzacyjne: jedną dla wysyłki zlecenia transferu i jedną dla odbioru zlecenia transferu. Kiedy wysyłasz zlecenie transferu, dwie transakcje inwentaryzacyjne są aktualizowane i tworzone są dwie dodatkowe transakcje inwentaryzacyjne dla tranzytu towarów, co daje w sumie cztery transakcje inwentaryzacyjne.</p><ol><li>Pierwsza transakcja inwentaryzacyjna jest używana do usunięcia elementu z magazynu źródłowego i lokalizacji. Stan wydania transakcji to **Sprzedano**, wskazując, że towar nie jest już dostępny w magazynie.</li><li>Druga transakcja inwentaryzacyjna jest używana do dodania pozycji do magazynu tranzytowego, który jest wybrany dla magazynu, z którego przenoszona jest pozycja. Stan przychodu dla tej transakcji to **Zakupione**.</li><li>Trzecia transakcja inwentaryzacyjna dotyczy przeniesienia z magazynu tranzytowego do magazynu docelowego. Stan wydania tej transakcji to **Zarezerwowane fizyczne**. Ten status zapewnia, że element nie może zostać zużyty przez inny proces, gdy jest jeszcze w drodze.</li><li>Czwarta transakcja inwentaryzacyjna dotyczy przyjęcia towarów do magazynu docelowego. Stan przychodu dla tej transakcji to **Zamówione**.</li></ol> |
| Przyjęcie zamówienia przeniesienia | Pokwitowanie | Obie | Kiedy zlecenie transferu jest odbierane w magazynie docelowym, stan zapasów transakcji magazynowej, która znajduje się w magazynie tranzytowym (numer 3 w poprzednim przykładzie) jest uaktualniany do **Sprzedane**, a stan zapasów transakcji magazynowej dla magazynu docelowego jest uaktualniany do **Zakupione**. |
| BOM | Obie | Obie | Możesz użyć arkusza listy składowej (BOM), aby zgłosić produkt jako gotowy i zużyć surowce, które zostały zużyte podczas procesu bez użycia zlecenia produkcyjnego. arkusz BOM zazwyczaj zawiera przynajmniej jeden wiersz dodatni dla wyrobu gotowego oraz jeden lub więcej wierszy ujemnych dla surowców, które są zużywane. Wiersz z wyrobami gotowymi jest przyjęciem do magazynu, natomiast wiersze ujemne są wydaniem z magazynu surowców. Kiedy tworzysz arkusz BOM, pierwszy wiersz jest nagłówkiem BOM, a kolejne dodawane wiersze są wierszami BOM. |
| Zmiana własności zapasów | Obie | Obie | arkusz zmiany własności zapasów służy do zmiany własności wysyłanych zapasów ze sprzedawcy na twoją organizację. arkusze zmiany własności zapasów przypominają arkusze przeniesienia zapasów, ponieważ z każdą kombinacją wiersza i wymiaru zapasów związane są dwie transakcje inwentaryzacyjne. Jedna transakcja inwentaryzacyjna usuwa zapasy od sprzedawcy w wymiarze **Własność**, a druga dodaje pozycję do osoby prawnej w wymiarze **Własność**. |
| Przyjęcie pozycji | Pokwitowanie | Fizyczne | arkusz przybycia pozycji jest używany do aktualizacji statusu przyjęcia zapasów na **Zarejestrowany**. Zazwyczaj używa się go do przyjmowania towarów z zamówień zakupu i zwrotów z zamówień sprzedaży. |
| Przyjęcie z produkcji | Pokwitowanie | Fizyczne | arkusz wejścia na produkcję przypomina arkusz przybycia przedmiotów. Wejście produkcyjne jest używane do przyjmowania gotowych towarów ze zlecenia produkcyjnego do magazynu. Po zaksięgowaniu arkusza status transakcji magazynowej jest aktualizowany do **Zarejestrowano**. |
| Inwentaryzacja | Obie | Obie | arkusz liczenia służy do zapisywania ilości sztuk, które zostały policzone dla określonej kombinacji wymiarów zapasów. Transakcje zapasów są tworzone, gdy w wierszu arkusza występuje różnica w liczeniu. Wiersz, który ma wyższą zliczoną ilość, powoduje przyjęcie do zapasów. Linia, która ma niższą zliczoną ilość, powoduje problem z zapasami. Wiersze, w których policzona ilość odpowiada ilości oczekiwanej, nie mają żadnych transakcji magazynowych. |
| Zliczanie znaczników | Nie dotyczy | Nie dotyczy | arkusz zliczania znaczników służy do śledzenia znaczników inwentaryzacyjnych, które są przypisywane i wykorzystywane podczas pełnego liczenia zapasów. Możesz użyć arkusza, by przypisać numer znacznika do konkretnej kombinacji pozycji i wymiaru inwentaryzacji oraz by śledzić status tego znacznika podczas pełnej inwentaryzacji. arkusze zliczania znaczników nie tworzą transakcji inwentaryzacyjnych. |
| Zlecenia kontroli jakości | Problem | Fizyczne | <p>Zlecenie jakości służy do rejestrowania wyników testów dla danej partii w magazynie. Każde zlecenie jakościowe jest związane z istniejącą transakcją inwentaryzacyjną lub częścią transakcji magazynowej.</p><p>Zlecenie kontroli jakości wygeneruje nową transakcję inwentaryzacyjną w dwóch sytuacjach:</p><ul><li>Zlecenie jakości jest oznaczone jako **Test destrukcyjny** w zakładce **Ogólne**.</li><li>Zlecenie jakości jest oznaczone jako **Kwarantanna po niepowodzeniu walidacji** w zakładce **Ogólne**, a test nie przeszedł walidacji. W tym przypadku tworzone są dwie transakcje magazynowe. Jedna transakcja magazynowa usuwa pozycję z oryginalnej kombinacji wymiarów i lokalizacji, a druga dodaje ją do magazynu kwarantanny.</li></ul> |
| Zlecenia kwarantanny | Obie | Obie | <p>Transakcje magazynowe w ramach zleceń kwarantanny są jak zlecenia transferu. Magazyn kwarantanny służy do śledzenia zapasów. Istnieją dwie transakcje otrzymania i dwie transakcje wydania.</p><p>Kiedy tworzysz zamówienie, tworzone są dwie transakcje. Transakcja przyjęcia ma status **Zamówione** dla magazynu kwarantanny, który jest powiązany z magazynem, w którym znajduje się artykuł. Transakcja wydania ma status **Zamówione** dla magazynu, w którym znajduje się element.</p><p>Kiedy rozpoczynasz zlecenie kwarantanny, tworzone są dwie dodatkowe transakcje, a istniejące są aktualizowane. Status transakcji przyjęcia do magazynu kwarantanny jest uaktualniony do **Przyjęte**, a status transakcji wydania do magazynu przechowywania jest uaktualniony do **Odjęty**.</p><p>Dwie nowe transakcje są używane, by wskazać ewentualny ruch powrotny do magazynu. Transakcja przyjęcia ma status **Zamówione** dla magazynu składowego, a transakcja wydania ma status **Zarezerwowane fizycznie** dla magazynu kwarantanny.</p><p>Kiedy zgłaszasz zlecenie kwarantanny jako zakończone, operacja ta stanowi fizyczną aktualizację zlecenia kwarantanny. Status przyjęcia w magazynie jest aktualizowany do **Odebrane**.</p><p>Kiedy kończysz zlecenie kwarantanny, ta operacja stanowi finansową aktualizację zlecenia kwarantanny. Status transakcji wydania jest uaktualniany do **Sprzedane**, a status transakcji otrzymania jest uaktualniany do **Zakupione**.</p><p>Możesz też anulować nakaz kwarantanny. Operacja ta powoduje usunięcie towaru z magazynu. Kiedy złomujesz zlecenie kwarantanny, pozostają tylko trzy transakcje. Transakcja przyjęcia do magazynu zostaje usunięta, a status pozostałej transakcji przyjęcia zostaje zaktualizowany do **Zakupiono**. Status dwóch transakcji wydania został zaktualizowany do **Sprzedane**. Ta operacja jest fizyczną i finansową aktualizacją zamówienia.</p> |

## <a name="fixed-receipt-price-posting"></a>Księgowanie stałej ceny przyjęcia

Stała cena odbioru pozwala na użycie standardowego kosztu produktu. Jest to alternatywa dla wybrania opcji **Koszt standardowy** na stronie **Grupy modeli przedmiotów** dla danego przedmiotu. Główną różnicą w stosowaniu stałej ceny odbioru jest to, że podczas księgowania przyjęcia na stan zapasów dla danej pozycji zostanie użyta aktualnie skonfigurowana cena nabycia. Nie ma procesu przeszacowania kosztów w przypadku stałej ceny odbioru. Kiedy aktualizacja finansowa jest księgowana, używana jest cena aktualna w momencie księgowania. Jeśli cena nabycia, która jest stosowana przy odbiorze, i faktura różnią się, różnica zostanie zaksięgowana na kontach zysków i strat według stałej ceny nabycia.

Aby opcjonalnie używać stałej ceny odbioru dla produktu, musisz przeprowadzić następującą konfigurację:

- Zaznacz pole wyboru **Księgowanie zapasów fizycznych** na stronie **Grupy modeli przedmiotów** dla przedmiotu, który jest wybrany w linii transakcji inwentaryzacyjnej.
- Zaznacz pole wyboru **Stała cena odbioru** na stronie **Grupa modelu artykułu**.
- Określ konta główne dla następujących typów księgowań na stronie **Profil księgowań zapasów**:

    - Dodatnie odchylenia od ceny ewidencyjnej
    - Ujemne odchylenia od ceny ewidencyjnej

Aby uzyskać więcej informacji, przejdź na stronę [Stała cena odbioru](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="catch-weight-posting"></a>Księgowanie ilości efektywnej

Produkty w ilości efektywnej są często używane w branżach takich jak przemysł spożywczy, gdzie produkty mogą się nieznacznie różnić wagą, rozmiarem lub obiema tymi cechami. Produkty w ilości efektywnej używają dwóch jednostek miary: jednostki inwentarzowej i jednostki ilości efektywnej. Waga zapasów przychodzących do magazynu może się różnić od wagi zapasów wydawanych z magazynu. Przetwarzanie produktów według ilości efektywnej dostosowuje zapasy.

Jeśli występuje odchylenie w ilości efektywnej, różnice są księgowane na kontach, które są określone w polach **Strata ilości efektywnej** i **Zysk ilości efektywnej** na stronie **Profilu księgowania zapasów**. Zazwyczaj w obu polach podaje się to samo konto główne.

Poniższa tabela pokazuje przykłady domyślnych typów księgowań oraz zawiera przykładowe konta główne i ich opisy.

- „Uznanie/kredyt?” kolumna wskazuje, czy transakcja jest obciążająca czy uznaniowa. W niektórych przypadkach transakcje mogą być zarówno obciążające, jak i uznaniowe.
- Kolumna Konto rozliczeniowe wskazuje typ księgowania jako konto rozliczeniowe. Innymi słowy, kwota zaksięgowana na tym koncie jest automatycznie odwracana w momencie zaksięgowania późniejszej transakcji.
- Kolumna "P/F" wskazuje typ księgowania. „P” oznacza księgowanie fizyczne, a „F” oznacza księgowanie finansowe.
- Kolumna "Wykonaj" wskazuje, czy konto główne dla danego typu postu jest zazwyczaj takie samo jak konto główne dla innego typu postu. W szczególności wskazuje typ delegowania, który jest zwykle używany dla danego księgowania.

> [!NOTE]
> Główne konta i nazwy głównych kont w tabeli są propozycjami. Zaleca się, aby współpracować z księgowym, aby ustalić najlepszą konfigurację dla potrzeb firmy.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | P/F | Śledzenie | Opis |
|---|---|---|---|---|---|---|---|---|
| Konto strat ilości efektywnej | 510520 | Korekta zapasów | Wydatek | | Nie | Obie | Konto zysków dla ilości efektywnej | To konto jest używane, gdy księgujesz transakcję magazynową, ilość efektywna jest niższa. |
| Konto zysków dla ilości efektywnej | 510520 | Korekta zapasów | Wydatek | | Nie | Obie | Konto strat ilości efektywnej | To konto jest używane, gdy księgujesz transakcję magazynową, ilość efektywna jest wyższa. |

Więcej informacji na temat ilości efektywnej można znaleźć w dokumentach [O ilości efektywnej](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.md) oraz [Przetwarzanie produktów z ilością efektywną w zarządzaniu magazynem](/supply-chain/warehousing/catch-weight-processing.md).

## <a name="inventory-to-fixed-asset-transfer-posting"></a>Księgowanie przeniesienia zapasów na środki trwałe

arkusz "Inwentaryzacja na środki trwałe" (**Aktywa trwałe** \> **arkusze** \> **Inwentaryzacja na środki trwałe**) służy do przenoszenia pozycji z inwentaryzacji i przekształcania ich w środki trwałe. Aby uzyskać więcej informacji, zobacz [Integracja środków trwałych](/fixed-assets/fixed-asset-integration.md).

Poniższa tabela pokazuje przykłady domyślnych typów księgowań oraz zawiera przykładowe konta główne i ich opisy.

- „Uznanie/kredyt?” kolumna wskazuje, czy transakcja jest obciążająca czy uznaniowa. W niektórych przypadkach transakcje mogą być zarówno obciążające, jak i uznaniowe.
- Kolumna Konto rozliczeniowe wskazuje typ księgowania jako konto rozliczeniowe. Innymi słowy, kwota zaksięgowana na tym koncie jest automatycznie odwracana w momencie zaksięgowania późniejszej transakcji.
- Kolumna "P/F" wskazuje typ księgowania. „P” oznacza księgowanie fizyczne, a „F” oznacza księgowanie finansowe.
- Kolumna "Wykonaj" wskazuje, czy konto główne dla danego typu postu jest zazwyczaj takie samo jak konto główne dla innego typu postu. W szczególności wskazuje typ delegowania, który jest zwykle używany dla danego księgowania.

> [!NOTE]
> Główne konta i nazwy głównych kont w tabeli są propozycjami. Zaleca się, aby współpracować z księgowym, aby ustalić najlepszą konfigurację dla potrzeb firmy.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | P/F | Śledzenie | Opis |
|---|---|---|---|---|---|---|---|---|
| Rozchód środków trwałych | 180100 | Rzeczowe aktywa trwałe | Element zawartości | Środki | Nie | Obie | Nie dotyczy | To konto jest używane, gdy publikujesz arkusz przeniesienia inwentarza na środek trwały, aby usunąć pozycję z inwentarza i przekształcić ją w środek trwały. |

## <a name="moving-average-posting"></a>Księgowanie średniej kroczącej

Średnia krocząca to metoda kalkulacji kosztów wieczystych, która opiera się na zasadzie średniej. Koszty wydania zapasów nie zmieniają się, gdy zmienia się koszt zakupu. Różnica jest kapitalizowana i oparta na obliczeniu proporcjonalnym. Pozostała kwota jest zaliczana w koszty.

Poniższa tabela pokazuje przykłady domyślnych typów księgowań wraz z przykładowymi kontami głównymi i opisami.

- „Uznanie/kredyt?” kolumna wskazuje, czy transakcja jest obciążająca czy uznaniowa. W niektórych przypadkach transakcje mogą być zarówno obciążające, jak i uznaniowe.
- Kolumna Konto rozliczeniowe wskazuje typ księgowania jako konto rozliczeniowe. Innymi słowy, kwota zaksięgowana na tym koncie jest automatycznie odwracana w momencie zaksięgowania późniejszej transakcji.
- Kolumna "P/F" wskazuje typ księgowania. „P” oznacza księgowanie fizyczne, a „F” oznacza księgowanie finansowe.
- Kolumna "Wykonaj" wskazuje, czy konto główne dla danego typu postu jest zazwyczaj takie samo jak konto główne dla innego typu postu. W szczególności wskazuje typ delegowania, który jest zwykle używany dla danego księgowania.

> [!NOTE]
> Główne konta i nazwy głównych kont w tabeli są propozycjami. Zaleca się, aby współpracować z księgowym, aby ustalić najlepszą konfigurację dla potrzeb firmy.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | P/F | Śledzenie | Opis |
|---|---|---|---|---|---|---|---|---|
| Różnica cen dla średniej ruchomej | 510600 | Średnia krocząca – różnica cen | Wydatek | Obie | Nie | Obie | Nie dotyczy | To konto jest używane, gdy występuje różnica w koszcie pomiędzy odbiorem a fakturą. |
| Przeszacowanie średniej ruchomej | 510610 | Przeszacowanie średniej ruchomej | Wydatek | Obie | Nie | Obie | Nie dotyczy | To konto jest używane, gdy korygujesz średni ruchomy koszt produktu |

## <a name="sample-posting-profile-configuration"></a>Przykładowa konfiguracja profilu księgowania

Poniższa tabela pokazuje przykłady domyślnych typów księgowań wraz z przykładowymi kontami głównymi i opisami.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | P/F | Śledzenie | Opis |
|---|---|---|---|---|---|---|---|---|
| Wydanie z magazynu | 140100 | Zapasy materiałów | Element zawartości | Środki | Nie | Obie | Przyjęcie do magazynu | To konto jest używane, gdy transakcja inwentaryzacyjna, która jest księgowana, jest wydaniem (ilość ujemna) i nie jest związana ze sprzedażą, zakupami lub produkcją. Kompensatą dla tego konta jest rachunek wydatków i strat z tytułu zapasów. To konto zazwyczaj reprezentuje zapasy w bilansie. |
| Rozchód zapasów, strata | 510100 | Zysk i strata na zapasach | Wydatek | Uznanie | Nie | Obie | Rozchód zapasów, zysk | To konto jest używane, gdy transakcja inwentaryzacyjna, która jest księgowana, jest wydaniem (ilość ujemna) i nie jest związana ze sprzedażą, zakupami lub produkcją. Kompensatą dla tego konta jest konto wydania zapasów. |
| Przyjęcie do magazynu | 140100 | Zapasy materiałów | Element zawartości | Uznanie | Nie | Obie | Wydanie z magazynu | To konto jest używane, gdy transakcja inwentaryzacyjna, która jest księgowana, jest odbiorem (ilość dodatnia) i nie jest związana ze sprzedażą, zakupami lub produkcją. Kompensatą dla tego konta są wydatki na zapasy, rachunek zysków. To konto zazwyczaj reprezentuje zapasy w bilansie. |
| Rozchód zapasów, zysk | 510100 | Zysk i strata na zapasach | Wydatek | Środki | Nie | Obie | Rozchód zapasów, strata | To konto jest używane, gdy transakcja inwentaryzacyjna, która jest księgowana, jest odbiorem (ilość dodatnia) i nie jest związana ze sprzedażą, zakupami lub produkcją. Kompensatą dla tego konta jest konto odbioru zapasów. |
| Zobowiązania międzyjednostkowe | 231500 | Zobowiązania międzyjednostkowe | Pasywa | Uznanie | Nie | Obie | | To konto jest używane, gdy zapasy są przenoszone pomiędzy wymiarami inwentarza, takimi jak placówki, a koszt danej pozycji różni się pomiędzy placówkami. |
| Należności międzyjednostkowe | 131500 | Należności międzyjednostkowe | Element zawartości | Środki | Nie | Obie | | To konto jest używane, gdy zapasy są przenoszone pomiędzy wymiarami inwentarza, takimi jak placówki, a koszt danej pozycji różni się pomiędzy placówkami. |
