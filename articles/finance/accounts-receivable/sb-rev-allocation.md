---
title: Alokacja przychodu
description: Ten temat wyjaśnia, jak używać alokacji przychodów w rozliczeniach subskrypcji.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 09d3e9295f1fb753156aa603b00372316173721e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695254"
---
# <a name="revenue-allocation"></a>Alokacja przychodu

Ten temat wyjaśnia, jak skonfigurować parametry alokacji przychodów dla harmonogramu rozliczeń. Możesz ustawić lub edytować alokację przychodów podczas tworzenia harmonogramu rozliczeń. Kiedy otwierasz stronę **Alokacja dochodu** dla aktywnego lub zakończonego harmonogramu rozliczeniowego, pola są tylko do odczytu.

## <a name="specify-the-revenue-allocation-for-a-billing-schedule"></a>Określenie alokacji dochodu dla harmonogramu rozliczeń

Aby określić alokację przychodów dla harmonogramu rozliczeń, wykonaj poniższe kroki.

1. Na stronie listy **Wszystkie/Aktywne harmonogramy fakturowania** wybierz harmonogram fakturowania lub wiersz harmonogramu rozliczeń.
2. W zakładce **Przydzielanie dochodów** na górze strony wybierz **Przydzielanie dochodów**.
3. W polu **Typ rozmieszczenia wielu elementów** wybierz typ rozmieszczenia wielu elementów (MEA).
4. W polu **Numer układu wielu elementów** podaj numer MEA. Następnie w polu **Konto przychodów z umów odroczonych** podaj konto przychodów z umów odroczonych.

    Jeśli ustawisz pole **Typ układu wieloelementowego** na **Pojedynczy**, w każdym wierszu zostaną zastosowane te same wartości **Numer układu wieloelementowego** i **Konto odroczonego przychodu z umowy**. Jeśli ustawisz pole **Typ układu wieloelementowego** na **Wielokrotny**, możesz określić różne zastosowane wartości **Numer układu wieloelementowego** i **Konto odroczonego przychodu z umowy**.
    
    Numer MEA może być przypisany tylko do dwóch lub więcej elementów. Pojedyncza linia nie może mieć własnego numeru MEA.

5. Wybierz opcję **Zapisz**.

### <a name="fields"></a>Pola

Strona **Układ wieloelementowy** zawiera następujące pola.

| Pole | Opis |
|---|---| 
| Typ układu wielu elementów | <p>Wybierz typ MEA dla transakcji:</p><ul><li>**Wielokrotne** – pozycje w transakcji są częścią MEA lub istnieje więcej niż jedno porozumienie.</li><li>**Brak** – transakcja jest transakcją standardową, która nie ma przypisanych żadnych przychodów.</li><li>**Pojedyncze** – wszystkie pozycje w transakcji są częścią jednego MEA.</li></ul> |
| Numer układu wielu elementów | <p>Numer MEA dla wiersza. Ta opcja jest dostępna tylko w przypadku, gdy w polu **Typ rozmieszczenia wielu elementów** jest ustawione na **Wielokrotne**.</p><p>Jeśli to pole jest puste, a ty przypisujesz numer MEA, pola **Pochodzenie** i **Standaliczna cena sprzedaży** są automatycznie aktualizowane na podstawie wartości ze strony **Samodzielna cena sprzedaży**. Dostępne są tylko te numery MEA, które są przypisane do innych linii na zamówieniu sprzedaży.</p> |
| Konto przychodu z odroczonej umowy | Określa konto, które ma być używane do wpisów w dzienniku, gdy tworzona jest faktura kontraktowa MEA. To pole jest dostępne tylko wtedy, gdy stosowane jest cykliczne rozliczanie umów. |
| **Wiersze** | |
| Numer wariantu | Numer wariantu z zamówienia sprzedaży. |
| Numer towaru | Numer pozycji z zamówienia sprzedaży. |
| Częstotliwość rozliczania | Częstotliwość przydzielania dochodów: **Dziennie**, **Miesięcznie**, **Kwartalne**, **Półroczne** lub **Rocznie**. |
| Ilość | Wartość z zamówienia sprzedaży. |
| Wartość umowy | Wartość kontraktu. |
| Numer układu wielu elementów | <p>Numer MEA dla wiersza. Ta opcja jest dostępna tylko w przypadku, gdy w polu **Typ rozmieszczenia wielu elementów** jest ustawione na **Wielokrotne**.</p><p>Jeśli to pole jest puste, a ty przypisujesz numer MEA, pola **Pochodzenie** i **Standaliczna cena sprzedaży** są automatycznie aktualizowane na podstawie wartości ze strony **Samodzielna cena sprzedaży**. Dostępne są tylko te numery MEA, które są przypisane do innych linii na zamówieniu sprzedaży. Jeśli te wartości nie są ustawione dla danego elementu, zostaną użyte wartości ze strony **Parametry alokacji dochodu dla wielu elementów**.</p> | 
| Źródło autonomicznej ceny sprzedaży | <p>Pochodzenie samodzielnej ceny sprzedaży:</p><ul><li>**Kwota** – Autonomiczna cena sprzedaży to kwota, która jest większa niż 0 (zero). Kwota jest w razie potrzeby konwertowana między walutami funkcjonalnymi a walutami inicjatorami.</li><li>**Podstawowa cena sprzedaży** – Autonomiczna cena sprzedaży odpowiada podstawowej cenie sprzedaży towaru.</li><li>**Cena na fakturze** – Jednostkowa cena sprzedaży jest zgodna z ceną fakturową danej pozycji.</li><li>**Odsetek pozycji** – Autonomiczna cena sprzedaży jest określona jako wartość procentowa i jest obliczana na podstawie ceny towaru. Jeśli ta opcja jest zaznaczona, określ domyślną wartość procentową.</li><li>**Zaalokuj pozostałą kwotę zgodnie z wymaganymi wartościami** – Pochodzenie autonomicznej ceny sprzedaży oblicza się jako *Całkowita wartość umowna pozycji nadrzędnej* - *Całkowita autonomiczna cena sprzedaży pozycji podrzędnych*:</p><ul><li>*Łączna wartość kontraktu pozycji nadrzędnej* to kwota netto lub kwota rachunku.</li><li>*Całkowita autonomiczna cena sprzedaży towarów podrzędnych* jest sumą autonomicznej ceny sprzedaży rozszerzonej lub kontraktowej wszystkich towarów podrzędnych, z wyjątkiem towaru podrzędnego, który używa tej autonomicznej ceny sprzedaży.</li></ul><p>Jeśli obliczona kwota jest wartością ujemną, jest ona ustawiana na 0 (zero).</p><p>**Uwaga:** tę opcję można wybrać tylko dla jednego towaru podrzędnego w podziale przychodów.</p></li><li>**Brak** – Pochodzenie autonomicznej ceny sprzedaży jest oparte na pozycjach podrzędnych. Ta opcja dotyczy towarów zdefiniowanych jako towary nadrzędne w szablonie podziału przychodów. Jeśli zaznaczono pole wyboru **Podział przychodów**, ta opcja jest zaznaczona automatycznie i ustawienia nie można zmienić.</li><li>**Procent nadrzędnej ceny faktury** – Pochodzenie autonomicznej ceny sprzedaży jest procentem ceny faktury towaru nadrzędnego. Ta opcja jest dostępna tylko dla pozycji podrzędnych w szablonie podziału przychodów.</li><li>**Procent standardowej ceny rodzica** – Źródłem autonomicznej ceny sprzedaży jest procent ceny standardowej pozycji macierzystej. Ta opcja jest dostępna tylko dla pozycji podrzędnych w szablonie podziału przychodów. Gdy opcja dla elementu podrzędnego zostanie zmieniona z **Procent standardowej ceny elementu nadrzędnego** na **Procent ceny faktury nadrzędnej** lub z **Procent ceny faktury nadrzędnej** na **Procent standardowej ceny nadrzędnej**, obliczone wartości są również aktualizowane.</li></ul> |
| Autonomiczna cena sprzedaży | <p>Jednostkowa cena sprzedaży za linię w walucie transakcji.</p><p>Wartość w polu **Kwota** jest wprowadzana lub obliczana.</p> |
| Autonomiczna cena sprzedaży z umowy | Jednostkowa cena sprzedaży kontraktu. |
| Pozostały przychód z umowy | Pozostała kwota przychodu dla kontraktu. Kwota ta jest sumą wszystkich wierszy, dla których nie zostały jeszcze utworzone faktury. |
| Suma przychodów z umowy | Całkowita kwota przychodu z kontraktu dla danego wiersza. Kwota ta jest sumą wszystkich linii, niezależnie od tego, czy zostały dla nich utworzone faktury. |
| Konto przychodu z odroczonej umowy | <p>Określa konto, które ma być używane do wpisów w dzienniku, gdy tworzona jest faktura kontraktowa MEA.</p><p>To pole jest dostępne tylko wtedy, gdy stosowane jest cykliczne rozliczanie umów.</p> |
| Błąd | Wszelkie błędy, które wystąpiły w przydziale dochodu. |

## <a name="use-revenue-allocation-on-a-sales-order"></a>Użyj alokacji przychodów na zleceniu sprzedaży

Aby skorzystać z funkcji alokacji przychodów na zlecenie sprzedaży, wykonaj poniższe kroki.

1. Na stronie **Wszystkie zamówienia sprzedaży** utwórz zlecenie sprzedaży, które zawiera pozycje.
2. W zakładce **Faktura**, w sekcji **Przydział dochodu**, wybierz **Przydział dochodu**.
3. W polu **Typ układu wieloelementowego** wybierz typ MEA.
4. W polu **Numer układu wielu elementów** podaj numer MEA.
5. Jeśli pole **Typ rozmieszczenia wielu elementów** jest ustawione na **Wielokrotne**, zaznacz linie, które chcesz, a następnie wybierz **Zastosuj do wybranych**.
6. Wybierz opcję **Zapisz**.

Jeśli korzystasz z odroczeń przychodów i kosztów, harmonogram odroczeń jest tworzony automatycznie. Możesz je zobaczyć na stronie **Wszystkie harmonogramy odroczeń**.
