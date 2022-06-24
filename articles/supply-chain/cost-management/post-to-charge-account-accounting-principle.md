---
title: Księgowanie na koncie obciążeniowym zasada księgowania
description: Ten artykuł zawiera omówienie zasady księgowania na koncie opłat.
author: rachel-profitt
ms.date: 05/02/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-02
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 998a30786b3f457b24b6e3c755b2c00967adbd4b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879171"
---
# <a name="post-to-charge-account-accounting-principle"></a>Księgowanie na koncie obciążeniowym zasada księgowania

*Dzięki zasadzie* księgowania na koncie opłat można rozliczać i łatwiej uzgadniać wszelkie różnice cen jednostkowych między księgami fizycznymi a finansowymi, kosztami pośrednimi dla zakupionych towarów lub opłatami w zamówieniu zakupu. 

Dwie konfiguracje kodów opłat dla zobowiązań na stronie **Kod opłat** (**Konta płatne \> Konfiguracja opłat \> Kod opłat**) mogą spowodować, że zlecenie zakupu będzie miało wpływ na wycenę aktywów w magazynie:

- W przypadku kodów opłat, dla których w polu **Typ obciążenia** ustawiono wartość *Element*, a w polu **Typ kredytu** ustawiono wartość *Konto księgi*, konto księgi wybrane jako konto absorpcji pełni funkcję konta różnicowego zapasów.
- W przypadku kodów opłat, dla których w polu **Typ obciążenia** ustawiono wartość *Element*, a w polu **Typ kredytu** ustawiono wartość *Klient/sprzedawca*, opłata zostanie zaksięgowana jako koszt materiałowy i zostanie zastosowane konto zmiany stanu magazynowego danej pozycji.

## <a name="european-special-accounting-rule"></a>Zasady księgowania specjalnego w Unii Europejskiej

W Europie reguła *księgowania opłat* księgowych jest często używana do wywłaszowania specjalnej reguły księgowania. Na przykład jedna z następujących metod jest zwykle używana do uwzględnienia zmian w zapasach:

- **Metoda koszt sprzedaży** — obsługuje ją standardowa konfiguracja profilu księgowania zapasów. Księgowanie *na koncie opłat* nie jest wymagane.
- **Charakter metody wydatków** — z tej metody często korzystają mniejsze organizacje. Zazwyczaj składa się ona z następujących etapów:

    1. Towary lub usługi są w pełni wydatkowane w momencie ich przyjęcia.
    2. Na koniec okresu jest wykonywana liczba cykli.
    3. Ręczna korekta ilości i wartości jest księgowana w magazynie. (Konto przeciwstawne jest kontem odchylenia magazynu, które jest przeciwstawne do wydatku zaksięgowanego w kroku 1. W związku z tym różnicę wartości zapasów widać tylko na tym koncie).

Dzięki *zasadzie księgowania na koncie* opłat można w pełni zautomatyzować te dwa księgowania. W ten sposób można wyeliminować ręczne księgowanie korekt zamknięcia na koniec okresu.

## <a name="enable-the-post-to-charge-account-accounting-principle"></a>Włącz zasadę rozliczania konta przez pocztę

Aby włączyć księgowanie *do reguły księgowania opłat*, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Parametry modułu rozrachunków z dostawcami**.
2. Na karcie **Faktura**, w zakładce **Faktura** Szybka zakładka, ustaw opcję **Prześlij na konto obciążeniowe w księdze** na *Tak*.
3. Zamknij stronę.

## <a name="prerequisites-and-recommended-parameters-for-the-post-to-charge-account-accounting-principle"></a>Wymagania wstępne i zalecane parametry zasady księgowania na koncie opłat

Jeśli użytkownik planuje uwzględniać opłaty związane z zakupem i odchylenia dotyczące zapasów, muszą spełnić następujące warunki wstępne:

- W zakładce **Faktura** na stronie **Parametry zobowiązań** (**Zobowiązania \> Ustawienia \> Parametry zobowiązań**) opcja **Księguj na koncie opłat w finansach** musi być ustawiona na *Tak*.
- Na stronie **Grupy modeli pozycji** (**Zarządzanie kosztami \> Konfiguracja zasad rachunkowości zapasów \> Grupy modeli pozycji**) wszystkie poniższe opcje muszą być ustawione na *Tak* dla każdego odpowiedniego modelu grupa zawierająca pozycje uwzględnione w zamówieniu zakupu:

    - Księguj magazyn fizyczny
    - Księguj magazyn finansowy
    - Naliczone zobowiązanie w dokumencie przyjęcia produktów

- Na karcie **Dostawa** strony **Parametry zaopatrzenia i pozyskiwania** (**Zaopatrzenie i zaopatrzenie \> Konfiguracja \> Parametry zaopatrzenia i pozyskiwania**) **Generuj opłaty za produkt paragon** opcja musi być ustawiona na *Tak*.
- Na karcie **Rachunkowość zapasów** strony **Parametry zarządzania zapasami i magazynem** (**Zarządzanie zapasami \> Konfiguracja \> Parametry zarządzania zapasami i magazynem**) **Po pakowaniu opcja poślizgu w księdze** musi być ustawiona na *Tak*.
- Na karcie **Zamówienie zakupu** strony **Księgowanie** (**Zarządzanie zapasami \> Konfiguracja \> Księgowanie \> Księgowanie**) konta główne, które mają zastosowanie do każdego odpowiedniego elementu, muszą należy określić dla każdego z następujących typów księgowania:

    - Koszty zakupu, niezafakturowane
    - Koszty zakupu produktów
    - Odchylenie magazynu

## <a name="example-scenario-1-change-in-unit-cost-price"></a>Przykładowy scenariusz 1. Zmiana w jednostkowym kosztie kosztu

Ten przykładowy scenariusz ma następujące wymagania wstępne:

- Model wyceny FIFO

Następująca procedura zawiera przykład, który pokazuje, co się dzieje po zmianie jednostkowego kosztu zakupu w zamówieniu zakupu.

1. Utwórz zamówienie zakupu dla ilości 1 towaru o cenie jednostkowej 100,00.
2. Potwierdź zamówienie zakupu.
3. Zaksięguj paragon produktu dla zamówienia zakupu.
4. Sprawdź poprawność załącznika na paragonie produktu. Poniższa tabela przedstawia przykładowy kupon.

    | Typ księgowania | Konto główne | Nazwa konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Fizyczne/Finansowe? | Ilość |
    |---|---|---|---|---|---|---|---|
    | Zakup, odchylenia magazynu | 600170 | Materiały zmienności zapasów | Wydatek | Środki | Nie | Fizyczne | -100,00 |
    | Koszt odebranych kupionych materiałów | 140100 | Zapasy materiałów | Element zawartości | Uznanie | Tak | Fizyczne | 100.00 |
    | Koszty zakupu, niezafakturowane | 600180 | Przychody materiałów | Wydatek | Uznanie | Tak | Fizyczne | 100.00 |
    | Zakup, naliczenie | 200140 | Naliczone zakupy | Pasywa | Środki | Tak | Fizyczne | -100,00 |

5. Księguj fakturę dla zamówienia zakupu, które ma zaktualizowaną cenę jednostkową 110,00.
6. Zweryfikuj voucher na fakturze. Poniższa tabela przedstawia przykładowy kupon.

    | Typ księgowania | Konto główne | Nazwa konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Fizyczne/Finansowe? | Ilość |
    |---|---|---|---|---|---|---|---|
    | Zakup, odchylenia magazynu | 600170 | Materiały zmienności zapasów | Wydatek | Środki | Nie | Finansowy | -10,00 |
    | Koszt odebranych kupionych materiałów | 140100 | Zapasy materiałów | Element zawartości | Uznanie | Tak | Finansowy | -100,00 |
    | Koszty zakupu, niezafakturowane | 600180 | Przychody materiałów | Wydatek | Uznanie | Tak | Finansowy | -100,00 |
    | Zakup, naliczenie | 200140 | Naliczone zakupy | Pasywa | Środki | Tak | Finansowy | 100.00 |
    | Koszt zafakturowanych kupionych materiałów | 140100 | Zapasy materiałów | Element zawartości | Uznanie | Nie | Finansowy | 110.00 |
    | Koszty zakupu produktów | 600180 | Przychód materiałów | Wydatek | Środki | Nie | Finansowy | 110.00 |
    | Saldo dostawcy | 211000 | Handel rozrachunkami z dostawcami | Pasywa | Środki | Nie | Finansowy | -110,00 |

## <a name="example-2-charges-and-indirect-costs-on-the-purchase-order"></a>Przykład 2: Opłaty i koszty pośrednie na zamówieniu zakupu

Ten przykładowy scenariusz ma następujące wymagania wstępne:

- Model wyceny FIFO
- **Kod opłat 1:** Konto księgowe pozycji po stronie debetowej i kredytowej dla 10%
- **Kod opłat 2:** Pozycja debetowa i kredytowa klienta/dostawcy za 10,00 proporcjonalnie
- **Koszt pośredni:** 2,00% dodano do ceny zakupu

Poniższa procedura przedstawia przykład, który pokazuje, co się dzieje po uwzględnieniu opłat i kosztów pośrednich w zamówieniu zakupu.

1. Utwórz zamówienie zakupu dla ilości 1 towaru o cenie jednostkowej 100,00.
2. Dodaj jeden kod opłat dla 10 procent debetu pozycji i uznania księgi.
3. Dodaj jeden kod obciążenia na 10,00, który obciąża towar i kredytuje klienta/dostawcę.
4. Przydziel opłaty do wierszy zamówienia zakupu.
5. Potwierdź zamówienie zakupu.
6. Zaksięguj paragon produktu dla zamówienia zakupu.
7. Sprawdź poprawność załącznika na paragonie produktu. Poniższa tabela przedstawia przykładowy kupon.

    | Typ księgowania | Konto główne | Nazwa konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Fizyczne czy Finansowe | Ilość |
    |---|---|---|---|---|---|---|---|
    | Zakup, odchylenia magazynu | 600170 | Materiały zmienności zapasów | Wydatek | Środki | Nie | Fizyczne | -110,00 |
    | Szacowany zaabsorbowany koszt pośredni | 600520 | Pochłonięte koszty pośrednie | Wydatek | Środki | Tak | Fizyczne | -2,40 |
    | Transport przy zakupie | 600120 | Koszty frachtu/transportu | Wydatek | Środki | Nie | Fizyczne | -10,00 |
    | Koszt odebranych kupionych materiałów | 140100 | Zapasy materiałów | Element zawartości | Uznanie | Tak | Fizyczne | 122.40 |
    | Koszty zakupu, niezafakturowane | 600180 | Przychody materiałów | Wydatek | Uznanie | Tak | Fizyczne | 110.00 |
    | Zakup, naliczenie | 200140 | Naliczone zakupy | Pasywa | Środki | Tak | Fizyczne | -110,00 |

8. Zaksięguj fakturę za zamówienie zakupu.
9. Zweryfikuj voucher na fakturze. Poniższa tabela przedstawia przykładowy kupon.

    | Typ księgowania | Konto główne | Nazwa konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Fizyczne/Finansowe? | Ilość |
    |---|---|---|---|---|---|---|---|
    | Zakup, odchylenia magazynu | 600170 | Materiały zmienności zapasów | Wydatek | Środki | Nie | Finansowy | 0,00 |
    | Szacowany zaabsorbowany koszt pośredni | 600520 | Pochłonięte koszty pośrednie | Wydatek | Uznanie | Tak | Finansowy | 2.40 |
    | Zaabsorbowany koszt pośredni | 600520 | Pochłonięte koszty pośrednie | Wydatek | Uznanie | Nie | Finansowy | -2,40 |
    | Koszt odebranych kupionych materiałów | 140100 | Zapasy materiałów | Element zawartości | Środki | Tak | Finansowy | -110,00 |
    | Koszty zakupu, niezafakturowane | 600180 | Przychody materiałów | Wydatek | Środki | Tak | Finansowy | -110,00 |
    | Zakup, naliczenie | 200140 | Naliczone zakupy | Pasywa | Uznanie | Tak | Finansowy | 110.00 |
    | Koszt zafakturowanych kupionych materiałów | 140100 | Zapasy materiałów | Element zawartości | Uznanie | Nie | Finansowy | 110.00 |
    | Koszty zakupu produktów | 600180 | Przychód materiałów | Wydatek | Środki | Nie | Finansowy | 110.00 |
    | Saldo dostawcy | 211000 | Handel rozrachunkami z dostawcami | Pasywa | Środki | Nie | Finansowy | -110,00 |
