---
title: Konfigurowanie kodów podatków
description: W tym temacie wyjaśniono sposób konfigurowania kodów podatków w usłudze obliczania podatku.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 8bdb194e7d8b704d1e58d3c25bf2e1f6bff1ba00
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883873"
---
# <a name="set-up-tax-codes"></a>Konfigurowanie kodów podatków

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania kodów podatków w usłudze obliczania podatku. Przedstawia on konfigurację prostego scenariusza włączania kodu podatku oraz informacje o niektórych funkcjach zaawansowanych kodów podatków w przypadku złożonych scenariuszy.

> [!IMPORTANT]
> Konfiguracja kodów podatków w usłudze obliczania podatku jest niezależna od osoby prawnej. Tę konfigurację można wykonać tylko jeden raz w usłudze RCS (Regulatory Configuration Service). Kody podatków są automatycznie synchronizowane z aplikacją Microsoft Dynamics 365 Finance po włączeniu usługi obliczania podatku dla wybranej osoby prawnej w aplikacji Finance.

## <a name="simple-setup"></a>Konfiguracja prosta

Wykonaj następujące kroki, aby użyć kodu podatku w prostym scenariuszu, na przykład w scenariuszu, w którym jest tylko jedna stawka podatku.

1. Zaloguj się do usługi [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Przejdź kolejno do pozycji **Obszary robocze** \> **Funkcje globalizacji** \> **Obliczanie podatku**.
3. Wybierz funkcję i wersję, które chcesz skonfigurować, i wybierz pozycję **Edytuj**.
4. Na karcie **Ogólne** wybierz pozycję **Wersja konfiguracji**.
5. Na karcie **Kody podatków** wybierz opcję **Dodaj**, a następnie wprowadź kod i opis podatku.
6. Wybierz opcję **Źródło obliczenia**. Źródło obliczenia to grupa metod, które są definiowane w wybranej wersji konfiguracji podatku. W tym prostym scenariuszu wybierz opcję **Według kwoty netto**.
7. Wybierz opcję **Zapisz**. Na podstawie wybranego źródła obliczenia staje się dostępnych więcej pól.
8. Na skróconej karcie **Stawki** wybierz opcję **Dodaj**, aby dodać jedną stawkę podatku dla tego kodu podatku.
9. Wybierz opcję **Zapisz**.

## <a name="calculation-origin"></a>Źródło obliczenia

Źródło obliczenia definiuje sposób obliczania kwoty wartości bazowej podatku i kwoty podatku. Jest ono konfigurowane przez konfigurację podatku w obszarze roboczym **Raportowanie elektroniczne**. W polu **Źródło obliczenia** są dostępne następujące wartości:

- Kwota netto 
- Według kwoty brutto
- Według ilości
- Według marży
- Podatek od podatku

### <a name="by-net-amount"></a>Kwota netto 

W przypadku wybrania opcji **Według kwoty netto** w polu **Źródło obliczenia** kwota podatku jest obliczana jako procent kwoty zakupu lub sprzedaży, z wyłączeniem wszelkich innych kodów podatków.

Na przykład stawka podatku wynosi 25 procent, wiersz faktury zawiera ilość wynoszącą 10 sztuk towaru po 1,00, a klient korzysta z rabatu wiersza o wartości 10 procent. W tym przypadku kwoty są obliczane następująco:

- **Kwota netto:** (10 × 1,00) – 10 procent = 9,00 
- **Podatek:** 9,00 × 25 procent = 2,25 
- **Łączna kwota faktury:** 9,00 + 2,25 = 11,25

### <a name="by-gross-amount"></a>Według kwoty brutto

Jeśli wybierzesz metodę **Według kwoty brutto** w polu **Źródło obliczenia**, kwota podatku jest obliczana jako procent kwoty sprzedaży brutto. Kwota brutto to kwota netto wiersza plus wszystkie podatki i opłaty dla wiersza, z wyjątkiem jednego podatku, dla którego pole **Źródło obliczenia** ustawiono na **Według kwoty brutto**.

Na przykład urząd skarbowy nałożył na daną pozycję specjalne cła. Kwoty ceł są dodawane do kwoty netto przed obliczeniem podatku. Są używane następujące kody podatków:

- **Cło 1** — stawka wynosi 10 procent i używana jest metoda obliczania **Według kwoty netto**.
- **Cło 2** — stawka wynosi 20 procent i używana jest metoda obliczania **Według kwoty netto**.
- **Stawka podatku** — stawka wynosi 25 procent i używana jest metoda obliczania **Według kwoty brutto**.

Jeśli kwota netto wynosi 10,00, kwota cła 1 wynosi 1,00 (10,00 × 10 procent), a kwota cła 2 to 2,00 (10,00 × 20 procent). W tym przypadku kwoty są obliczane następująco: 

- **Kwota brutto:** kwota netto + kwota cła 1 + kwota cła 2 = 10,00 + 1,00 + 2,00 = 13,00 
- **Kwota podatku:** 13,00 × 25 procent = 3,25 
- **Łączne cła i podatki:** 1,00 + 2,00 + 3,25 = 6,25 
- **Łączna kwota faktury:** 10,00 + 6,25 = 16,25

### <a name="by-quantity"></a>Według ilości

Po wybraniu opcji **Według ilości** w polu **Źródło obliczenia** kwota podatku jest obliczana jako stała kwota na jednostkę i mnożona przez ilość wprowadzoną w wierszu dokumentu. Kwota na jednostkę jest określona na skróconej karcie **Stawki**.

Na przykład kod podatku jest ustawiany jako 1,20 na jednostkę. Wiersz faktury sprzedaży pokazuje 25 sprzedanych jednostek pozycji. W takim przypadku kwota podatku jest obliczana jako 25 × 1,20 = 30,00.

### <a name="by-margin"></a>Według marży

Jeśli wybierzesz metodę **Według marży** w polu **Źródło obliczenia**, kwota podatku jest obliczana jako procent marży sprzedaży. Marża sprzedaży jest kwotą sprzedaży pomniejszoną o kwotę kosztu. Ta metoda obliczania ma zastosowanie tylko do transakcji sprzedaży.

Na przykład stawka podatku wynosi 25 procent, wiersz faktury zawiera ilość wynoszącą 10 sztuk towaru po 10,00, a koszt na pozycję wynosi 6. W tym przypadku kwoty są obliczane następująco:

- **Marża sprzedaży:** 10 × (10,00 – 6,00) = 40,00
- **Kwota podatku:** 40,00 × 25 procent = 10,00
- **Łączna kwota faktury:** 100,00 + 10,00 = 110,00

### <a name="tax-on-tax"></a>Podatek od podatku

W przypadku wybrania opcji **Podatek od podatku** w polu **Źródło obliczenia**, podatek będzie obliczany jako procent wszystkich innych kwot podatku w tym samym wierszu dokumentu.

Na przykład są używane następujące kody podatków:

- **Cło 1** — stawka wynosi 10 procent i używana jest metoda obliczania **Według kwoty netto**.
- **Cło 2** — stawka wynosi 20 procent i używana jest metoda obliczania **Według kwoty netto**.
- **Podatek od cła** — stawka wynosi 25 procent i używana jest metoda obliczania **Podatek od podatku**.

W tym przypadku kwoty są obliczane następująco:

- **Kwota netto:** 10,00 
- **Cło 1:** 10,00 × 10 procent = 1,00 
- **Cło 2:** 10,00 × 20 procent = 2,00 
- **Podatek od cła:** 3,00 × 25 procent = 0,75
- **Łączny podatek:** 1,00 + 2,00 + 0,75 = 3,75 
- **Łączna kwota faktury:** 10,00 + 3,75 = 13,75

## <a name="advanced-functionality"></a>Funkcje zaawansowane

W tej sekcji objaśniono niektóre zaawansowane funkcje konfiguracji kodów podatków w przypadku scenariuszy złożonych.

### <a name="tax-exemption"></a>Zwolnienie z podatku

W przypadku ustawienia opcji **Czy podlega zwolnieniu** na **Tak** na skróconej karcie **Ogólne** kwota podatku będzie zawsze zastępowana wartością 0 (zero) niezależnie od rzeczywistej stawki podatku.

W polu **Kod zwolnienia** można określić przyczynę zwolnienia. 

Można włączyć wyszukiwanie danych głównych dla pola **Kod zwolnienia**. W ten sposób można wybierać spośród wartości kodów zwolnienia, które są zdefiniowane w aplikacji Finanse. Aby uzyskać informacje o włączaniu wyszukiwania danych głównych, zobacz temat [Włączanie wyszukiwania danych głównych dla konfiguracji obliczania podatku](tax-service-set-up-environment-master-data-lookup.md).

Na przykład stawka podatku wynosi 25 procent, a opcja **Czy podlega zwolnieniu** jest ustawiona na **Tak** dla kodu podatku. Wiersz faktury zawiera 10 sztuk towaru po 1,00 USD, a odbiorca ma rabat wiersza w wysokości 10 procent. W tym przypadku kwoty są obliczane następująco:

- **Kwota netto:** (10 × 1,00) – 10 procent = 9,00 
- **Podatek:** 0,00 
- **Łączna kwota faktury:** 9,00 + 0,00 = 9,00

### <a name="use-tax"></a>Podatek nienaliczony

W przypadku ustawienia opcji **Czy jest podatkiem obrotowym** na **Tak** na skróconej karcie **Ogólne** kwota podatku zostanie zaksięgowana na koncie **Podatek nienaliczony należny**, zamiast na koncie **podsumowania dostawcy**.

Na przykład stawka podatku wynosi 25 procent, a opcja **Czy jest podatkiem obrotowym** jest ustawiona na **Tak** dla kodu podatku. Wiersz faktury zawiera 10 sztuk towaru po 1,00 USD, a odbiorca ma rabat wiersza w wysokości 10 procent. W tym przypadku kwoty są obliczane następująco:

- **Kwota netto:** (10 × 1,00) – 10 procent = 9,00 
- **Podatek nienaliczony należny:** 9,00 × 25 procent = 2,25
- **Łączna kwota faktury:** 9,00 + 0,00 = 9,00

> [!IMPORTANT]
> W przypadku ustawienia opcji **Czy podlega zwolnieniu** i opcji **Czy jest podatkiem obrotowym** na **Tak** dla kodu podatku kod będzie rozpoznawany jako zwolnienie z podatku w przypadku transakcji sprzedaży i ewentualny podatek obrotowy dla transakcji zakupu.

### <a name="reverse-charges"></a>Opłaty zwrotne

W przypadku ustawienia opcji **Czy jest opłatą zwrotną** na **Tak** na skróconej karcie **Ogólne** stawkę podatku można skonfigurować jako ujemną. W przypadku scenariusza z opłatą zwrotną zalecamy skonfigurowanie dwóch kodów podatków: jednego z dodatnią stawką podatku, a drugiego z ujemną stawką podatku. Oba kody podatków powinny mieć tę samą wartość stawki, a opcja **Czy jest opłatą zwrotną** powinna mieć wartość **Tak** w przypadku kodu podatku, który ma ujemną stawkę podatku. Aby uzyskać więcej informacji o rozwiązaniu opłaty zwrotnej w finansach, zobacz temat [Mechanizm opłaty zwrotnej dla schematu podatku VAT/GST](emea-reverse-charge.md).

Na przykład dwa kody podatków są określone w jednym wierszu faktury. Jedna stawka podatku wynosi 25 procent. Druga stawka podatku wynosi -25 procent, a opcja **Czy jest opłatą zwrotną** jest ustawiona na **Tak** dla drugiego kodu podatku. Wiersz faktury pokazuje 10 pozycji po 1,00 każda. W tym przypadku kwoty są obliczane następująco:

- **Kwota netto:** (10 × 1,00) = 10,00 
- **Kod podatku 1:** 10,00 × 25 procent = 2,50
- **Kod podatku 2:** 10 × -25 procent = -2,50
- **Łączna kwota faktury:** 10,00 + 2,50 -2,50 = 10,00

### <a name="exclusion-from-base-amount-calculations"></a>Wykluczenie z obliczeń kwoty bazowej

W przypadku ustawienia opcji **Wyklucz z obliczania kwoty bazowej** na **Tak** na skróconej karcie **Ogólne** obliczona kwota podatku dla kodu podatku zostanie wykluczona z kwoty podstawy podatku dla innych obliczeń kodu podatku w scenariuszu uwzględniającym cenę.

Aby uzyskać więcej informacji, zobacz temat [Obliczanie podatku od cen, gdy opcja Ceny zawierają podatki jest włączona](global-exclude-from-tax-base-amount-calculation.md).

### <a name="rates"></a>Stawki

Na skróconej karcie **Stawka** można definiować różne stawki podatku dla różnych zakresów kwot podstawy podatku. Aby obliczyć kwotę podatku, usługa obliczania podatku zawsze używa stawki, która odpowiada kwocie podstawy podatku.

Na przykład stawki podatku mogą być skonfigurowane tak, jak to przedstawiono w poniższej tabeli.

| Minimalna kwota | Liczba maksymalna | Stawka podatku   |
| -------------- | -------------- | ---------- |
| 0              | 1 000          | 10 procent |
| 1 000          | 5000          | 15 procent |
| 5000          | 10,000         | 20 procent |
| 10,000         | 0              | 30 procent |

W tym przypadku kwota podatku jest obliczana następująco:

- Jeśli kwota podstawy podatku wynosi 300,00, stawka podatku wynosi 10 procent, a kwota podatku wynosi 300,00 × 10 procent = 30,00.
- Jeśli kwota podstawy podatku wynosi 3000,00, stawka podatku wynosi 15 procent, a kwota podatku wynosi 3000,00 × 15 procent = 450,00.
- Jeśli kwota podstawy podatku wynosi 6000,00, stawka podatku wynosi 20 procent, a kwota podatku wynosi 6000,00 × 10 procent = 1200,00.
- Jeśli kwota podstawy podatku wynosi 20 000,00, stawka podatku wynosi 30 procent, a kwota podatku wynosi 20 000,00 × 30 procent = 6000,00.

> [!NOTE]
> Jeśli kwota podstawy podatku może odpowiadać kwocie maksymalnej w jednym wierszu i minimalnej kwocie w drugim wierszu, podstawa użyje stawki podatku zgodnej z minimalną kwotą podstawy. Na przykład jeśli kwota podstawy podatku wynosi 1000,00, stawka podatku wynosi 15 procent, a kwota podatku wynosi 1000,00 × 15 procent = 150,00.

### <a name="limits"></a>Limity

Na skróconej karcie **Limity** można zdefiniować limity podatkowe, które zastąpią obliczoną kwotę podatku, jeśli kwota podatku mieści się w zakresie minimum/maksimum.

- Jeśli obliczona kwota podatku jest większa niż maksymalna kwota podatku skonfigurowana na skróconej karcie **Limity**, końcowa kwota podatku jest równa maksymalnej kwocie podatku.
- Jeśli obliczona kwota podatku jest mniejsza niż minimalna kwota podatku skonfigurowana na skróconej karcie **Limity**, końcowa kwota podatku wynosi 0 (zero).

Limity podatkowe są na przykład konfigurowane w następujący sposób:

- **Minimalna kwota podatku:** 100 
- **Maksymalna kwota podatku:** 1000

Jeśli obliczona kwota podatku wynosi 2000, końcowa kwota podatku wynosi 1000.

Jeśli obliczona kwota podatku wynosi 500, końcowa kwota podatku wynosi 500.

Jeśli obliczona kwota podatku wynosi 80, końcowa kwota podatku wynosi 0 (zero).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
