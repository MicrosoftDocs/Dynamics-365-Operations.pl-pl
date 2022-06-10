---
title: Księgowanie zamówienia zakupu
description: Ten temat opisuje zakładkę Zamówienia na stronie Profile księgowania zapasów.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 4b36ab9da22da7d4f3e62bd2d2aba2a2ec80e60f
ms.sourcegitcommit: 5b55f2913e736d12e40c227bf3ce3a9abec815bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/24/2022
ms.locfileid: "8803029"
---
# <a name="purchase-order-posting"></a>Księgowanie zamówienia zakupu

Zakładka **Zamówienia** na stronie **Profili księgowania zapasów** służy do kontrolowania sposobu księgowania zamówień zakupu w księdze głównej. W przypadku zamówienia zakupu w księdze głównej księgowane są dwie główne czynności: 

- Dokument przyjęcia produktów
- Faktura

Aby fizyczna transakcja (odbiór produktu) została zaksięgowana w księdze głównej w ramach zamówienia zakupu, muszą być zaznaczone następujące pola wyboru:

- Pole wyboru **Postaw przyjęcie produktu w księdze** na stronie **Parametry inwentaryzacji i zarządzania magazynem**.
- Pola wyboru **Sporządzenie spisu zapasów fizycznych** i **Określenie zobowiązania przy odbiorze produktu** na stronie **Grupy modeli przedmiotów**.

Konta główne muszą być określone na stronie na stronie **Profil księgowania zapasów** dla następujących typów księgowania:

- Koszty zakupu materiałów otrzymanych
- Wydatki na zakupy, niezafakturowane
- Zakup, naliczenie

Aby transakcja finansowa (faktura) została zaksięgowana w księdze głównej na podstawie zamówienia zakupu, muszą być spełnione następujące warunki:

- Pole wyboru **Przeprowadzenie inwentaryzacji finansowej** musi być zaznaczone na stronie **Grupy modeli przedmiotów** dla pozycji wybranej w linii zamówienia zakupu.
- Konta główne muszą być określone na stronie na stronie **Profil księgowania zapasów** dla następujących typów księgowania:
  - Koszt zafakturowanych kupionych materiałów
  - Koszty zakupu produktów
  - Koszty zakupu
  - Rabat (opcjonalny)

## <a name="fixed-receipt-price-posting"></a>Księgowanie stałej ceny przyjęcia

Możesz użyć stałej ceny odbioru jako kosztu standardowego produktu alternatywnie do wybrania opcji **Koszt standardowy** w polu **Model zapasów** na stronie **Grupy modeli przedmiotów** dla danego artykułu. Główna różnica polega na tym, że gdy użyta jest **stała cena odbioru**, to podczas księgowania odbioru dla danej pozycji zostanie użyta aktualna cena kosztu. Nie ma procesu przeszacowania kosztów w przypadku **stałej ceny otrzymania**; kiedy aktualizacje finansowe są wprowadzane, używana jest cena kosztów aktualna w momencie wprowadzania aktualizacji. Jeśli wystąpi różnica między ceną nabycia stosowaną przy odbiorze a ceną na fakturze, różnica zostanie zaksięgowana na kontach zysków i strat według stałej ceny nabycia.

Aby używać stałej ceny odbioru dla produktu, musisz skonfigurować następujące elementy:

- Na stronie **Grupy modeli przedmiotów** zaznacz pole wyboru **Księgowanie zapasów fizycznych** i **Stała cena odbioru**. 
- Na stronie **Parametry zarządzania zapasami i magazynem** zaznacz pole wyboru **Postaw kartę opakowania w księdze**.
- Na stronie **Profil księgowania zapasów** określ konta główne dla następujących typów księgowań:
  - Dodatnie odchylenia od ceny ewidencyjnej
  - Ujemne odchylenia od ceny ewidencyjnej
  - Konto przeciwstawne dla odchyleń od ceny ewidencyjnej

Aby uzyskać więcej informacji, przejdź na stronę [Stała cena odbioru](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="purchase-charges-and-stock-variation-posting"></a>Opłaty za zakupy i księgowanie zmian w zapasach

Jeśli planujesz rozliczać koszty zakupu i zmiany zapasów, wykonaj następujące czynności:

- Na stronie **Parametry zobowiązań** w zakładce **Faktura** zaznacz pole wyboru **Umieść na koncie obciążeniowym w księdze**.
- Na stronie **Grupy modelu jednostki** dla pozycji wybranej w linii zamówienia zakupu zaznacz pola wyboru **Księgowanie zapasów fizycznych**, **Księgowanie zapasów finansowych** i **Zaliczenie zobowiązania przy odbiorze produktu**.
- Na stronie **Parametry zamówień i zaopatrzenia** zaznacz pole wyboru **Generuj opłaty przy odbiorze produktu**.
- Na stronie **Parametry zarządzania zapasami i magazynem** zaznacz pole wyboru **Postaw kartę opakowania w księdze**.

Na stronie **Profilu księgowania zapasów** musisz określić konta główne dla następujących typów księgowań:

- Wydatki na zakupy, niezafakturowane
- Koszty zakupu produktów
- Odchylenie magazynu

> [!NOTE]
> Typ księgowania **Obciążenie** nie jest używany, gdy zaznaczony jest parametr **Umieść na koncie obciążeniowym w księdze**.

Aby uzyskać więcej informacji, przejdź na stronę [Zasada księgowania na koncie obciążeniowym](/supply-chain/cost-management/post-to-charge-account-accounting-principle.md).

## <a name="sample-posting-profile-configuration"></a>Przykładowa konfiguracja profilu księgowania

Poniższa tabela pokazuje przykłady domyślnych typów księgowań wraz z przykładowymi kontami głównymi i opisami:

- Kolumna **Konto rozliczeniowe** wskazuje typ księgowania jako konto rozliczeniowe. Kwota zaksięgowana na tym koncie jest automatycznie odwracana w momencie zaksięgowania późniejszej transakcji. 
- Kolumna **P/F** wskazuje **P** dla księgowania fizycznego i **F** dla księgowania finansowego. 
- Kolumna **Wykonaj** wskazuje, czy konto główne określonego typu księgowania jest zazwyczaj takie samo jak inny typ księgowania. Wartość w kolumnie wskazuje typ typowo stosowanego księgowania.

> [!NOTE]
> Te konta główne i nazwy kont głównych są tylko sugestiami. Zalecamy<!--note from editor: Via Writing Style Guide.--> abyś wspólnie z księgowym ustalił, jaka konfiguracja będzie najlepsza dla twoich potrzeb biznesowych.


| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | P/F | Śledzenie | Opis |
|--------------|---------------------|-------------------------|----------------|----------------|--------------------|----|----------|-----------|
| Koszt odebranych kupionych materiałów | 140100</br>140101 | Zapasy materiałów</br>Materiały wysłane bez faktury | Element zawartości | Uznanie | Tak | P | Koszt zafakturowanych kupionych materiałów | Używane, gdy księgowany jest rachunek za produkt z zamówienia zakupu. Kompensatą dla konta są wydatki na zakup, które nie zostały zafakturowane. Kwota na tym koncie jest odwracana po zaksięgowaniu faktury za zamówienie zakupu. |
| Wydatki na zakupy, niezafakturowane | 600180 | Potwierdzenia odbioru materiałów | Wydatek | Uznanie | Tak | P | |Używane, gdy księgowany jest rachunek za produkt z zamówienia zakupu. Do odbioru tworzone są dwa vouchery, aby śledzić odchylenia w cenie zakupu, gdy stosowany jest koszt standardowy. Kompensata na koncie pierwszego kuponu to rozliczenie międzyokresowe zakupów. Kompensata na drugim kuponie jest sumą kont odchylenia kosztu zakupionych materiałów i ceny zakupu. Kwoty zaksięgowane na tym koncie są odwracane po zaksięgowaniu faktury za zamówienie zakupu. |
| Koszt zafakturowanych kupionych materiałów | 140100 | Zapasy materiałów | Element zawartości | Uznanie | Nie | P  |Koszt odebranych kupionych materiałów | Używane, gdy faktura z zamówienia zakupu jest księgowana. Kompensatą dla tego konta są wydatki na zakup produktów. To konto reprezentuje zapasy w bilansie. Używane konto jest zazwyczaj tym samym kontem, które jest używane w przypadku Koszt jednostek dostarczonych i Koszt jednostek zafakturowanych dla zamówień sprzedaży. |
| Koszty zakupu produktów | 600180 | Odbiór materiałów | Wydatek | Środki | Nie | P  | |Używane, gdy faktura z zamówienia zakupu jest księgowana. Kompensatą dla tego konta jest Koszt zakupionych materiałów. To konto reprezentuje zapasy w bilansie. |
| Zysk ze stałej ceny zakupu (Zakup, zysk ze stałej ceny odbioru*) | 510310 | Odchylenie cen zakupu | Wydatek | Środki | Nie | P | Ujemne odchylenia od ceny ewidencyjnej | Używane, gdy faktura za zamówienie zakupu jest zaksięgowana i występuje różnica między ceną na fakturze a domyślnym kosztem pozycji. To konto jest używane, gdy różnica jest większa. Kompensatą dla tego konta jest kompensata stałej ceny wpływów. |
| Stała strata w cenie odbioru (Zakup, stała strata w cenie odbioru*) | 510310 | Odchylenie cen zakupu | Wydatek | Uznanie | Nie | P | Dodatnie odchylenia od ceny ewidencyjnej | Używane, gdy faktura za zamówienie zakupu jest zaksięgowana i występuje różnica między ceną na fakturze a domyślnym kosztem pozycji. To konto jest używane, gdy różnica jest mniejsza. Kompensatą dla tego konta jest kompensata stałej ceny wpływów. |
| Kompensacja stałej ceny odbioru (Zakup, kompensacja stałej ceny odbioru*) | 140900 | Odchylenie magazynu | Element zawartości | Obie | Nie | P  | |Używane, gdy faktura za zamówienie zakupu jest zaksięgowana i występuje różnica między ceną na fakturze a domyślnym kosztem pozycji. Konto to stanowi kompensatę dla rachunków zysków i strat z tytułu Ustalonej ceny wpływów. |
| Opłata | ND | ND | ND | ND | ND | ND | ND | To konto nie jest już używane. Zamiast tego użyj odmiany Stock. |
| Odchylenie magazynu | 600170 | Odchylenie magazynu | Wydatek | Środki | Nie | Obie | | To konto jest używane, gdy: <ul><li>Jest różnica w cenie jednostkowej między rachunkiem za produkt a fakturą.</li><li>Opłaty są księgowane do przedmiotu.</li><li>Koszty pośrednie zostały<!--note from editor: Edit okay?--> dodane do zakupionych przedmiotów. </li><li>Kompensatą dla tego konta jest konto Wydatki na zakup, niezafakturowane.</li></ul> |
| Zakup, naliczenie | 200140 | Naliczone zakupy | Pasywa | Środki | Y | P | |Używane, gdy księgowane jest potwierdzenie przyjęcia produktu zamówienia zakupu i włączona jest opcja naliczania kwot zakupu. |
| Naliczony podatek na dokumencie przyjęcia | 250500 | Naliczony podatek od sprzedaży | Pasywa | Środki | Y | Obie  | |To konto jest używane, gdy wybierzesz opcję **Księgowanie podatku fizycznego** w **Parametrach zarządzania zapasami i magazynem** i masz zamówienie zakupu z podatkiem. Kwota ta jest księgowana w momencie fizycznej aktualizacji zamówienia zakupu (pokwitowania odbioru produktu), a odwracana w momencie finansowego zaksięgowania zamówienia zakupu (faktury). |
| Wpływ środków trwałych (Obciążenie środków trwałych*) | 180100 | Rzeczowe aktywa trwałe | Element zawartości | Uznanie | N | Obie | Obie | To konto jest używane, gdy w linii zamówienia zakupu wybierzesz opcję Środki trwałe. Integracja z zamówieniem zakupu została skonfigurowana tak, aby nabyć środek trwały po otrzymaniu produktu lub faktury. Aby uzyskać więcej informacji na temat integracji zamówień zakupu środków trwałych, przejdź do [Pozyskiwanie środków poprzez zamówienia](/fixed-assets/acquire-assets-procurement). |
| Koszty zakupu | 618900 | Inne wydatki | Wydatek | Uznanie | N | Obie | |Używane podczas księgowania odbioru lub faktury za zamówienie zakupu, w którym produkty nie są magazynowane lub używana jest kategoria zamówienia. |
| Zaliczka | 132190 | Przedpłacone koszty | Element zawartości | Uznanie | N | Obie | | Używane podczas przetwarzania faktury zaliczkowej na zlecenie zakupu. |


\*Wartości podane w nawiasach reprezentują wartość, która jest używana w polu **Typ księgowania** na stronie **Transakcji bonowych**. **Typ księgowania** możesz wyświetlić na stronie **Transakcje z voucherami** na karcie **Ogólne**.

## <a name="fixed-asset-posting-with-purchase-orders"></a>Księgowanie środków trwałych za pomocą zamówień zakupu

Jeśli korzystasz z modułu **Środki trwałe** i planujesz zakup środków trwałych poprzez zamówienia zakupu, musisz skonfigurować typ księgowania **Przyjmowanie środków trwałych** w zakładce **Zamówienia zakupu** na stronie **Profilu księgowania zapasów**. Aby uzyskać więcej informacji, przejdź do [Integracja środków trwałych](/fixed-assets/fixed-asset-integration.md) i [Tworzenie i nabywanie aktywów z kont zobowiązań](/fixed-assets/tasks/create-acquire-assets-accounts-payable.md).

## <a name="prepayment-purchase-order-invoice-posting"></a>Księgowanie faktur z zamówień zakupu z przedpłatą

Jeśli planujesz używać funkcji **Faktury zaliczkowej** do zamówień zakupu, musisz wybrać **Typ księgowania zaliczkowego** w zakładce **Zamówienie zakupu** na stronie **Profilu księgowania zapasów**. Aby uzyskać więcej informacji, przejdź do strony [Faktury zaliczkowe a przedpłaty](/accounts-payable/prepayments-invoices-vs-prepayments.md).

## <a name="purchase-requisition-and-purchase-order-confirmation-posting"></a>Księgowanie zamówień zakupu i potwierdzeń zamówień zakupu

Propozycje zakupów i potwierdzenia zamówień można również skonfigurować tak, by księgowały w księdze głównej kwoty wstępne i kwoty obciążające. Te posty są kontrolowane przez definicję postu. Aby uzyskać więcej informacji, przejdź do strony [O obciążeniach zamówienia zakupu](/dynamicsax-2012/appuser-itpro/about-purchase-order-encumbrances).

## <a name="procurement-category-posting"></a>Postawienie kategorii zamówień

Alternatywnie do ustawiania księgowania inwentaryzacji dla wszystkich pozycji, grupy pozycji lub pojedynczej pozycji, możesz ustawić kategorie i kontrolować księgowanie księgi przez kategorie zamówień. Aby uzyskać więcej informacji na temat tworzenia kategorii i przypisywania ich do produktów, przejdź do [Przykładowa konfiguracja profilu wysyłania](#sample-posting-profile-configuration) wcześniej w tym temacie.

Kiedy używasz kategorii z zamówieniami zakupu lub fakturami od sprzedawców, hierarchia kategorii musi być przypisana do typu **Hierarchia kategorii zamówień publicznych** na stronie **Przypisania ról hierarchii kategorii**.

### <a name="vendor-invoices-with-procurement-categories"></a>Faktury dostawców z kategoriami zamówień

Jeśli twoja organizacja używa zamówień zakupu dla niektórych zakupów, a dla innych nie, możesz przetwarzać faktury niezwiązane z zamówieniami zakupu na różne sposoby. Dotyczy to także używania dzienników w **Kontach do zapłacenia** lub na stronie **Oczekujące faktury dostawców**, która służy do generowania faktur do zamówień zakupu. Podczas tworzenia faktur niezwiązanych z zamówieniami zakupu musisz utworzyć kategorie zamówień dla każdego typu wydatków. Będziesz musiał zmapować kategorię do odpowiedniego konta wydatków na stronie **Profile księgowania zapasów**.

Dokładna liczba kategorii będzie zależała od liczby kont kosztowych, których używasz do księgowania faktur. Będziesz potrzebował przynajmniej jednej kategorii zakupów dla każdego konta głównego, na które wystawiasz faktury bez zamówień. Wiele kategorii może być używanych dla jednego konta głównego. Może to być przydatne dla użyteczności, łatwości wyszukiwania i raportowania typów wydatków, z których korzystasz.

### <a name="benefits-of-using-procurement-categories-for-vendor-invoices"></a>Korzyści z używania kategorii zamówień dla faktur sprzedawców

Niektóre korzyści z używania kategorii zamówień dla faktur od dostawców to:

- Spójne doświadczenie użytkownika: Kiedy skonfigurujesz kategorie zamówień dla wszystkich wydatków niezwiązanych z zamówieniami, użytkownicy mogą zostać przeszkoleni w zakresie jednego procesu fakturowania za pomocą strony **Oczekujące faktury dostawców**.
- Ulepszone raportowanie: Po skonfigurowaniu kategorii zamówień dla wszystkich pozycji i wszystkich wydatków niezwiązanych z zamówieniami zakupu, raport wydatków na zamówienia będzie analizował wydatki według dostawców, kategorii i nie tylko.
- Spójny przepływ pracy: Kiedy używasz **Oczekujących faktur dostawcy** do przetwarzania wszystkich faktur, możesz stworzyć spójny przepływ pracy i proces zatwierdzania, używając jednego przepływu pracy.

## <a name="consignment-inventory-posting"></a>Księgowanie zapasów konsygnacyjnych

Zapasy konsygnacyjne są księgowane w ten sam sposób, co inne zakupione produkty. Kluczowa różnica polega na tym, że gdy zapasy jest otrzymywany, nie są rejestrowane żadne transakcje w księdze. Aby przenieść własność na organizację, gdy księgowany jest arkusz **Zmiany własności zapasów**, generowany jest bon, który rejestruje koszt pozycji. Aby uzyskać więcej informacji, przejdź do [Ustawianie przesyłki](/supply-chain/inventory/consignment.md).
