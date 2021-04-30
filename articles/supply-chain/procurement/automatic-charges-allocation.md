---
title: Automatyczna alokacja opłat
description: Funkcja opłaty w Microsoft Dynamics 365 Supply Chain Management pomaga automatycznie przydzielić opłaty do zamówień zakupu lub zamówień sprzedaży.
author: dasani-madipalli
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e8d65cc1f946f921523607eff850b29f9ff9bf1
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910168"
---
# <a name="automatic-allocation-of-charges"></a>Automatyczna alokacja opłat

[!include [banner](../includes/banner.md)]

W zależności od klienta, z którym pracujesz, lub przedmiotu, który sprzedajesz, możesz zastosować określone dodatkowe opłaty. Funkcja *opłaty* w Microsoft Dynamics 365 Supply Chain Management pomaga automatycznie przydzielić opłaty do zamówień zakupu lub zamówień sprzedaży.

Opłaty automatyczne są stosowane automatycznie podczas tworzenia zamówienia sprzedaży lub zamówienia zakupu. Automatyczne opłaty można definiować dla określonych dostawców, grup odbiorców lub towarów. Można też definiować automatyczne opłaty mające zastosowanie do wszystkich dostawców klientów lub towarów.

## <a name="set-up-charges-codes"></a>Konfigurowanie kodów opłat

Aby alokować opłaty, należy najpierw zdefiniować kody opłat.

1. Wykonaj jeden z następujących kroków:

    - Dla zamówień zakupu: Przejdź do **Rozrachunki z dostawcami \> Ustawienia opłat \> Kod opłat**.
    - Dla zamówień sprzedaży: Przejdź do **Rozrachunki z odbiorcami \> Ustawienia opłat \> Kod opłat**.

1. W okienku akcji wybierz opcję **Nowa**, aby utworzyć kod opłaty.
1. W nagłówku nowego zapisu określ następujące pola:

    - **Kod opłat** — umożliwia wprowadzenie kodu opłat.
    - **Opis** – wprowadź opis opłat.
    - **Grupa podatków dla towaru** — umożliwia wybór grupy podatków dla towaru (jeśli ma to zastosowanie).
    - **Naliczanie proporcjonalne** — w tej opcji należy wybrać *Tak*, jeśli opłaty mają być klasyfikowane proporcjonalnie. Opcja jest dostępna wyłącznie dla zamówień sprzedaży.
    - **Maksymalną ilość** – Wprowadź maksymalną kwotę dozwoloną dla kodu opłat. To pole służy do sprawdzania poprawności opłat dla faktur od dostawców. Jest ona dostępna tylko w zamówienia zakupu.

        > [!NOTE]
        > Aby włączyć funkcję sprawdzania poprawności opłat dla zamówień zakupu, należy przejść do **Rozrachunki z dostawcami \> Konfiguracja \> Parametry modułu rozrachunków z dostawcami**. Na skróconej karcie **Sprawdzania poprawności faktury** w sekcji **Weryfikacja faktury** określ opcję **Włącz sprawdzanie poprawności faktur** na *Tak*.

1. Na skróconej karcie **Księgowanie** obejmuje sekcje **Debetowe** i **Kredytowe**. W zależności od księgi, w której mają być księgowane opłaty, należy określić następujące pola:

    - **Typ** — umożliwia wybór typu konta, na którym dokonywane jest księgowanie (*Księga*, *Odbiorca* lub *Towar*).
    - **Księgowanie** — umożliwia wybranie typu księgowania, które ma zostać utworzone (takie jak *Opłata maklerska* lub *Rozliczenia z odbiorcami*).
    - **Konto** — umożliwia wybranie konta, dla którego zostanie zaksięgowana opłata.

1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="create-charge-groups"></a>Tworzenie grup opłat

Grupy opłat automatycznie przydzielają określone opłaty do grupy odbiorców lub dostawców. Poniższe podsekcje opisują sposób tworzenia i przypisywania tych grup opłat.

### <a name="charge-groups-for-purchase-orders"></a>Grupy opłat do zamówień zakupu

Aby utworzyć grupy opłat dla zamówień zakupu, należy wykonać następujące kroki.

1. Przejdź do **Rozrachunki z dostawcami \> Ustawienia opłat \> Grupa opłat dla dostawcy**.
1. W okienku akcji wybierz opcję **Nowy** w okienku akcji, aby dodać wiersz do siatki, a następnie ustaw następujące pola:

    - **Grupa opłat** — umożliwia wprowadzenie nazwy grupy opłat.
    - **Opis** – wprowadź opis grup opłat.

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Przejdź do **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**, a następnie otwórz istniejącego dostawcę lub Utwórz nowego dostawcę.
1. Na skróconej karcie **Ustawienia domyślne zamówienia zakupu** w sekcji **Zamówienie zakupu**, w polu **Grupa opłat** należy określić utworzoną właśnie grupę opłat.

### <a name="charge-groups-for-sales-orders"></a>Grupy opłat do zamówień sprzedaż

Aby utworzyć grupy opłat dla zamówień sprzedaży, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia opłat \> Grupy opłat klienta**.
1. W okienku akcji wybierz opcję **Nowy** w okienku akcji, aby dodać wiersz do siatki, a następnie ustaw następujące pola:

    - **Grupa opłat** — umożliwia wprowadzenie nazwy grupy opłat.
    - **Opis** – wprowadź opis grup opłat.

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Umożliwia przejście do **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**, a następnie otwarcie istniejącego odbiorcy lub utworzenie nowego odbiorcy.
1. Na skróconej karcie **Ustawienia domyślne zamówienia zakupu** w sekcji **Zamówienie sprzedaży**, w polu **Grupa opłat** należy określić utworzoną właśnie grupę opłat.

## <a name="define-auto-charges"></a>Określanie opłat automatycznych

Po skonfigurowaniu kodów opłat automatyczne należy wykonać poniższe kroki w celu zdefiniowania opłat automatycznych.

1. Wykonaj jeden z następujących kroków:

    - Dla zamówień zakupu: Przejdź do **Zaopatrzenie i sourcing \> Konfiguracja \> Opłaty \> Opłaty automatyczne**.
    - Dla zamówień sprzedaży: Przejdź do **Rozrachunki z odbiorcami \> Konfiguracja \> Ustawienia opłat \> Opłaty automatyczne**.

1. W okienku listy w polu **Poziom** wybierz poziom, na którym ma zastosowanie opłata automatyczna:

    - *Główny* — zastosuj opłaty w nagłówku zamówienia.
    - *Wiersz* — zastosuj opłaty w wierszach zamówienia.

1. Wybierz istniejącą opłatę automatyczną, aby ją edytować, lub wybierz opcję **Nowy**, aby zdefiniować nową opłatę automatyczną.
1. Na liście **Kod konta** wybierz jedną z następujących wartości, aby określić zakres kont, które będą miały wpływ:

    - *Tabela* — przypisz opłaty do określonego odbiorcy lub dostawcy.
    - *Grupa* — przypisz opłaty do grupy opłat dodatkowych.
    - *Wszystkie* — przypisz opłaty do wszystkich odbiorców lub dostawców.

1. Jeśli w polu **Relacja odbiorcy** lub **Relacja z dostawcą** wybierz konkretnego klienta lub dostawcę, jeśli w polu **Kod konta** na *Tabela*. Jeśli wybrano pole **Grupa w polu** na *Grupa*, wybierz grupę opłat odbiorcy lub dostawcy.
1. W polu **Kod pozycji** wybierz jedną z następujących wartości, aby określić zakres pozycji, które będą miały wpływ. Kod towaru można wybrać tylko wtedy, gdy są zdefiniowane opłaty automatyczne na poziomie wiersza.

    - *Tabela* — przypisz opłaty do określonego towaru.
    - *Grupa* — przypisz opłaty do grupy opłat dodatkowych dla towaru.
    - *Wszystkie* — przypisz opłaty do wszystkich towarów.

1. W polu **Relacja produktu** wybierz konkretny element, jeśli w polu **Kod towaru** ustawisz wartość *Tabela*. Jeśli w polu **Kod towaru** wybrano opcję *Grupa*, należy wybrać grupę opłat za towar.
1. **Tylko dla zamówień sprzedaży:** w polu **Metoda metody dostawy** wybierz jedną z następujących wartości, aby określić zakres trybów dostawy, które mają być uwzględnione:

    - *Tabela* — przypisz opłaty określonej metody dostawy.
    - *Grupa* — przypisz opłaty do grupy trybów dostawy.
    - *Wszystkie* — przypisz opłaty do wszystkich trybów dostawy.

1. **Tylko dla zamówień sprzedaży:** W polu **Tryb relacji dostawy** wybierz konkretny sposób dostawy, jeżeli w polu **Kod trybu dostawy** ustawisz wartość *Tabela*. Jeśli ustawisz pole **Kod trybu dostawy** na *Grupa*, wybierz tryb grupy dostaw.
1. Rozwiń skróconą kartę **Wiersze**, aby zdefiniować opłaty i stawki opłat, które mają być używane podczas stosowania bieżącej automatycznej opłaty. Na pasku narzędzi na tej skróconej karcie można dodać dowolną liczbę wierszy. Dla każdego wiersza ustaw następujące pola:

    - **Waluta** — umożliwia wybór waluty, która powinna być używana do obliczania opłaty.
    - **Kod opłat** – wybierz kod opłaty.
    - **Kategoria** – Należy wybrać jedną z następujących opcji:

        - *Stała* — opłata jest wprowadzana jako stała kwota w wierszu. Opłaty stałe mogą być używane w przypadku opłat zarówno w nagłówku zamówienia i w wierszach zamówienia.
        - *Szt.* — opłata jest oparta na jednostce. Te opłaty mogą być używane tylko w wierszach zamówienia. Będą one widoczne podczas obliczania sumy zamówienia.
        - *Procent* — opłata jest wprowadzana jako wartość procentowa w wierszu. Opłaty procentowe mogą być stosowane do opłat zarówno w nagłówku zamówienia, jak iw wierszach zamówienia.
        - *Procent międzyfirmowy* — opłata jest wprowadzana jako wartość procentowa w wierszu dla zamówień międzyfirmowych. Opłaty procentowe międzyfirmowe mogą być stosowane tylko w wierszach zamówienia.
        - *Zewnętrzny* — opłata jest obliczana za pomocą usługi innej firmy, która jest skojarzona z co najmniej jednym przewoźnikiem wysyłki.

    - **Wartość opłat** — umożliwia wprowadzenie wartości opłaty na podstawie wybranej kategorii.
    - **Kod waluty opłat** — umożliwia określenie waluty opłaty, jeśli ma być używana waluta inna niż waluta określona w polu **Waluta**. Możesz użyć innej waluty tylko wtedy, gdy pole **Typ debetu** lub **Typ kredytu** jest ustawione na *Konto księgowe* lub *Towar* dla wybranego kodu opłat.
    - **Od kwoty** – Określ kwotę początkową, która ma być stosowana w przypadku automatycznej opłaty. W tym kontekście kwota odnosi się do całości zamówienia.
    - **Do kwoty** – Określ kwotę końcową, która ma być stosowana w przypadku automatycznej opłaty. W tym kontekście kwota odnosi się do całości zamówienia.
    - **Grupa podatków** — umożliwia określenie grupy podatków.
    - **Oddział** i **Magazyn** — umożliwia określenie oddziału i magazynu, jeśli opłaty mają być stosowane tylko do określonego oddziału i magazynu.
    - **Zachowaj** – Zaznacz ro pole wyboru, aby zachować transakcje opłat po zafakturowaniu, żeby opłata była stosowana po każdym utworzeniu nowej faktury dla wybranego konta odbiorcy.

1. **Tylko dla zamówień sprzedaży:** Jeśli chcesz obliczyć opłaty warstwowe, zajrzyj do [Opłaty warstwowe w zamówieniach sprzedaży](/dynamicsax-2012/appuser-itpro/about-tiered-charges-on-sales-orders).

## <a name="allocate-charges-from-the-header-to-a-line"></a>Alokuj opłaty z nagłówka do wiersza

Poniżej przedstawiono procedurę alokowania opłat na poziomie nagłówka w wierszu. Przed rozpoczęciem tej procedury należy mieć już opłatę na poziomie nagłówka typu *stałej kwoty* oraz zamówienie, na którym nałożona jest opłata. Ponadto w zamówieniu powinno być już co najmniej jeden wiersz towaru.

1. Otwórz zamówienie zakupu lub zamówienie opłaty.
1. W okienku akcji wykonaj jeden z następujących kroków:

    - W przypadku zamówień zakupu: na karcie **Zakup** w grupie **Opłaty** wybierz opcję **Alokuj opłaty**.
    - W przypadku zamówień sprzedaży: na karcie **Sprzedaż** w grupie **Opłaty** wybierz opcję **Alokuj opłaty**.

1. W oknie dialogowym **Alokuj opłaty do wierszy zamówienia** należy określić następujące pola:

    - **Alokacja opłat** — umożliwia wybór jednej z następujących wartości w celu określenia sposobu alokacji opłat:

        - *Kwota netto* — alokuje opłaty zgodnie z każdą kwotą wiersza w odniesieniu do łącznej kwoty netto.
        - *Ilość* — przydziela opłaty zgodnie z liczbą jednostek każdego wiersza w odniesieniu do łącznej liczby jednostek.
        - *Na wiersz* — Rozłóż opłaty równo na łączną liczbę wierszy.

    - **Przydziel opłaty do wierszy** — umożliwia wybór wartości określającej, czy opłaty powinny być alokowane do wszystkich wierszy, tylko do wierszy dodatnich, czy tylko do wierszy ujemnych.
    - **Przydziel wszystkie** – Zaznacz to pole wyboru, aby przypisać opłaty do linii zamówienia, nawet jeśli kod opłat ma typ obciążenia inny niż *Towar*.
    - **Odebrane** – Zaznaczenie tego pola wyboru spowoduje alokowanie opłat tylko do wierszy otrzymanego zamówienia.
    - **Magazynowany** – Zaznacz to pole wyboru, aby alokować opłaty tylko do linii zamówienia zinwentaryzowanych.
    - **Umożliwia wyświetlenie opcji i wyczyszczenie określonych wierszy** — zaznaczenie tego pola wyboru spowoduje wykluczenie określonych wierszy z tej alokacji. Po zaznaczeniu tego pola wyboru zostanie otwarta siatka **Wybierz linie do wykluczenia z alokacji**. Siatka zawiera tylko te wiersze, które spełniają kryteria zdefiniowane w ustawieniach **Przydziel opłaty do wierszy** i **Magazynowane**. Na przykład po wybraniu w polu **Alokuj opłaty do wierszy** opcji *Wiersze dodatnie* i wybraniu okienka wyboru **Magazynowane**, na siatce będą tylko wiersze dodatnie i zinwentaryzowane. Ponadto siatka automatycznie filtruje wszystkie wiersze, dla których została już odebrana pełna ilość. Gdy siatka jest otwarta, wyczyść pole wyboru **Uwzględnij** dla każdego wiersza, który ma być wykluczony z alokacji. 

        > [!IMPORTANT]
        > Podczas pracy z siatką **Wybierz linie do wykluczenia z alokacji**, należy pamiętać, aby pozostawić siatkę otwartą do momentu wybrania opcji **Alokacja**. Jeśli zamkniesz siatkę przed wybraniem opcji **Alokacja**, ustawienia w siatce zostaną utracone. Z tego względu opłaty będą alokowane na podstawie poprzednio zdefiniowanych kryteriów.

1. Wybierz przycisk **Alokacja**, aby zastosować ustawienia i zamknąć okienko dialogowe.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]