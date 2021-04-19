---
title: Określona proporcjonalnie do opłat dodatkowych z nagłówka do wierszy sprzedaży uzgadniania
description: W tym temacie opisano dodatkowe funkcje obliczania i stosowania opłat automatycznych dla zamówień kanału Commerce przy użyciu funkcji zaawansowanych opłat automatycznych.
author: hhaines
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 22939e8fd63a355effecf0c16fecd20377faa3a6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791061"
---
# <a name="prorate-header-charges-to-matching-sales-lines"></a>Określona proporcjonalnie do opłat dodatkowych z nagłówka do wierszy sprzedaży uzgadniania


[!include [banner](includes/banner.md)]

W tym temacie opisano funkcje grupowania automatycznych opłat na poziomie nagłówka i określenia ich proporcji do wierszy sprzedaży handlu. Ta funkcja jest dostępna dla transakcji, które zostały utworzone w punkcie sprzedaży (POS) w Retail wersji 10.0.1 i sprzedaży, które zostały utworzone w biurze obsługi w Retail wersji 10.0.2.

Ta funkcja jest dostępna tylko wtedy, gdy [zaawansowane automatyczne opłaty](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges) włączono za pomocą opcji na stronie **Parametry handlu**. Ponadto rozszerzona metoda obliczania automatycznych opłat może być stosowana tylko w przypadku zamówień sprzedaży utworzonych przez kanały handlu (punkt sprzedaży, biuro obsługi, platforma Dynamics e-Commerce).

Ta nowa funkcja daje organizacjom większą elastyczność w taki sposób, że automatyczne opłaty poziomu nagłówka są obliczane i dodawane do transakcji sprzedaży.

W wersjach aplikacji, które są starsze niż wersja 10.0.1, opłaty automatyczne na poziomie nagłówka, które mają określoną relację metody dostawy, są obliczane tylko, kiedy jest zgodność z metodą dostawy zdefiniowaną na nagłówku zamówienia sprzedaży.

Na przykład automatyczne opłaty na poziomie nagłówka są zdefiniowane dla metody dostawy **99** i metody dostawy **11**. Zamówienie sprzedaży jest tworzone i metoda dostawy **99** jest zdefiniowana w nagłówku zamówienia. Jednak niektóre wiersze sprzedaży ustawiono tak, że są one wysłane przy użyciu metody dostawy **11**. W takim przypadku tylko opłaty poziomu nagłówka odnoszące się do metody dostawy **99** są brane pod uwagę oraz stosowane do zamówienia sprzedaży.

W Commerce opłaty na poziomie nagłówka mają dodatkową funkcję, która pozwala zdefiniować [konfigurację opłat warstwowych](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery) na podstawie wartości zamówienia. Na przykład jeśli wartość zamówienia wynosi między $50.00 i $200.00, organizacja może chcieć naliczyć opłatę transportową $5.00. Jeśli jednak wartość zamówienia wynosi między $200.01 i $500.00, koszt transportu może wynosić $4.00.

Niektóre organizacje chcą mieć korzyści z warstwowego naliczania opłat w przypadku opłat na poziomie nagłówka. Jednak w scenariuszach obejmujących mieszane metody dostawy, również chcą mieć pewność, że opłaty są obliczane na podstawie dopasowania do metody dostawy określonej w każdym wierszu sprzedaży.

Teraz możesz skonfigurować automatyczne opłaty na poziomie nagłówka, tak aby wszystkie metody dostawy w zamówieniu były brane pod uwagę przy naliczaniu opłat. Ta funkcja wymaga bardziej złożonej metody obliczania opłat na poziomie nagłówka. Metoda grupuje razem wszystkie jednostki, które są wysyłane przy użyciu tej samej metody dostawy i traktuje tę grupę jako grupę obliczeniową dla jednostek, gdy oblicza automatyczne opłaty na poziomie nagłówka. W przypadku jednostek, które mają tę samą metodę dostawy, automatyczne opłaty są obliczane na podstawie łącznej wartości sprzedaży jednostek. W ten sposób jest określana odpowiednia warstwa automatycznej opłaty.

Po uzyskaniu odpowiednich opłat na poziomie nagłówka dla wierszy sprzedaży wysyłanych tą samą metodą opbliczone opłaty są naliczane proporcjonalnie na poziomie wiersza sprzedaży. Ze względu na to, że te opłaty są na poziomie wiersza, a nie nagłówka, zostaje utworzone bardziej konkretne powiązanie między jednostką a obliczoną dla niej wartością opłaty. Zachowanie to może być przydatne w przypadku częściowego zwrotu, gdy organizacja chce zwrócić tylko część opłaty zamiast całej kwoty, kiedy klient zwraca tylko część towaru.

## <a name="scenarios"></a>Scenariusze

Następujące dwa przykładowe scenariusze pokazują, jak te opłaty są naliczane zarówno przy użyciu nowej funkcjonalności, jak i bez niej.

### <a name="scenario-1"></a>Scenariusz 1

W tym scenariuszu opisano zachowanie, gdy opcja **Proporcjonalnie do wierszy sprzedaży** jest ustawiona jako **Nie** w ustawieniach automatycznych opłat. (To zachowanie jest odpowiednikiem zachowania opłat na poziomie nagłówka w wersjach aplikacji, które są starsze niż wersja 10.0.1)

W tym scenariuszu organizacja zdefiniowała opłaty na poziomie nagłówka dla relacji metod dostawy **99** i **11**. Dla metody dostawy **21** nie skonfigurowano automatycznych opłat.

![Automatyczne opłaty dodatkowe dla metody dostawy 99, gdy jest wyłączona funkcja proporcjonalnego dopasowywania wartości wierszy](media/99_disabled.png)

![Automatyczne opłaty dodatkowe dla metody dostawy 11, gdy jest wyłączona funkcja proporcjonalnego dopasowywania wartości wierszy](media/11_disabled.png)

Zamówienie sprzedaży jest tworzone w Centrum obsługi z metodą dostawy **99**. To zamówienie zawiera pięć elementów. Dwa wiersze zamówienia zostały skonfigurowane do używania metody dostawy **99**, dwa wiersze zostały skonfigurowane do używania metody dostawy **11** i jeden wiersz został skonfigurowany do używania metody dostawy **21**, jak to pokazano w tabeli poniżej.

| Element  | Ilość w wierszu | Metoda dostawy | Cena jednostkowa |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | $10            |
| 81332 | 1             | 99            | 50 USD            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | $10            |
| 81334 | 3             | 21            | $5             |

W tym scenariuszu całe zamówienie jest obliczana na podstawie tabeli automatycznych opłat dla metody dostawy **99**. Pełna suma wszystkich wierszy sprzedaży służy do określania warstwy dopasowania w konfiguracji automatycznych opłat, a ta opłata jest stosowana na poziomie nagłówka zamówienia. W tym przykładzie suma zamówienia wynosi $165,00, a opłata transportowa $15,00 jest uwzględniona w nagłówku zamówienia. Automatyczne opłaty ustawione dla metody dostawy **11** nie zostały zastosowane.

W tym scenariuszu jeśli klient zwraca niektóre towary z zamówienia, i [kod opłaty został skonfigurowany tak, aby można było zwrócić pieniądze](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges#setup-and-configuration-2), całkowita kwota opłaty na poziomie nagłówka jest systematycznie stosowana do zwrotu, nawet jeśli klient zwraca tylko niektóre kupione przedmioty.

### <a name="scenario-2"></a>Scenariusz 2

W tym scenariuszu opłaty na poziomie nagłówka są zdefiniowane dla relacji metod dostawy **99** i **11**. Jednak opcja **Proporcjonalnie do wierszy sprzedaży** jest ustawiona jako **Tak** dla tych tabel automatycznych opłat.

![Automatyczne opłaty dodatkowe dla metody dostawy 99, gdy jest włączona funkcja proporcjonalnego dopasowywania wartości wierszy](media/99_enabled.png)

![Automatyczne opłaty dodatkowe dla metody dostawy 11, gdy jest włączona funkcja proporcjonalnego dopasowywania wartości wierszy](media/11_enabled.png)

Ten scenariusz używa tego samego zamówienia sprzedaży zawierającego pięć wierszy. Metoda dostawy w nagłówku zamówienia jest ustawiona jako **99**, ale metody dostawy dla poszczególnych towarów w zamówieniu sprzedaży są ustawione, jak pokazano w poniższej tabeli.

| Element  | Ilość w wierszu | Metoda dostawy | Cena jednostkowa |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | $10            |
| 81332 | 1             | 99            | 50 USD            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | $10            |
| 81334 | 3             | 21            | $5             |

Ponieważ konfiguracja automatycznej opłaty jest ustawiona tak, aby proporcjonalnie rozkładać wartości na wiersze sprzedaży, system wykonuje następujące obliczenia.

1. Wszystkie pozycje z tą samą metodą dostawy są grupowane razem, a system oblicza łączną wartość produktu pozycji w tej grupie.

    **Metoda dostawy 11**

    - Pozycja 81331, ilość 1 = $10
    - Pozycja 81333, ilość 2 = $60 netto ($30 za jednostkę)
    - **Całkowita wartość produktu dla metody dostawy 11 = $70**

    **Metoda dostawy 99**

    - Pozycja 81332, ilość 1 = $50
    - Pozycja 81334, ilość 3 = $30 netto
    - **Całkowita wartość produktu dla metody dostawy 99 = $80**

    **Metoda dostawy 21**

    - Pozycja 81334, ilość 3 = $15 netto
    - **Całkowita wartość produktu dla metody dostawy 21 = $15**

2. System wyszukuje konfiguracji dla automatycznych opłat na poziomie nagłówka odpowiadających odbiorcy i metodzie dostawy dla każdej grupy towarów. Jeśli konfiguracja zostanie znaleziona, system przeszukuje warstwową konfigurację, aby znaleźć opłatę, którą należy zastosować na podstawie łącznej wartości produktów z grupy danej metody dostawy.

    **Metoda dostawy 11**

    - Łączna wartość produktu = 70 USD
    - **Wysokość opłaty = $7**

    **Metoda dostawy 99**

    - Łączna wartość produktu = 80 USD
    - **Wysokość opłaty = $15**

    **Metoda dostawy 21**

    - Łączna wartość produktu = 15 USD
    - **Wysokość opłaty = $0** (nie skonfigurowano automatycznych opłat dla tej kombinacji odbiorcy i metody dostawy.)

    ![Opłaty za metodę dostawy 11 mieszczą się w podkreślonej warstwie](media/step2mode11.png)

    ![Opłaty za metodę dostawy 99 mieszczą się w podkreślonej warstwie](media/step2mode99.png)

3. System oblicza wartość opłaty, która ma być stosowana dla każdego wiersza, na podstawie mechanizmu proporcji, który uwzględnia proporcjonalną wartość wiersza w odniesieniu do łącznej wartości produktu w grupie.

    **Metoda dostawy 11**

    - Wysokość opłaty = $7
    - Wartość produktu w grupie = $70
    - Wiersz 1 wartość = $10 (= 14.2857 % wartości grupy)
    - Wiersz 3 wartość = $60 (= 85.7143 % wartości grupy)
    - **Opłata dla wiersza 1 = $1**
    - **Opłata dla wiersza 3 = $6**

    **Metoda dostawy 99**

    - Wysokość opłaty = $15
    - Wartość produktu w grupie = $80
    - Wiersz 2 wartość = $50 (= 62.5 % wartości grupy)
    - Wiersz 4 wartość = $30 (= 37.5 % wartości grupy)
    - **Opłata dla wiersza 2 = $9.38**
    - **Opłata dla wiersza 4 = $5.62**

    **Metoda dostawy 21**

    - Wysokość opłaty = $0
    - Wartość produktu w grupie = $15
    - Wiersz 5 wartość = $15 (= 100 % wartości grupy)
    - **Opłata dla wiersza 5 = $0**

W związku z tym na przykład do elementu 81334 zostanie przypisana opłata transportowa $5.62. Opłaty te można wyświetlać na stronie **Obsługa opłat** w wierszu sprzedaży. Na poniższej ilustracji przedstawiono, jak wygląda ta strona dla elementu 81334.

![Proporcjonalne opłaty w wierszu sprzedaży dla elementu 81334](media/proratedlinecharge.png)

W przypadku używania tej metody obliczania w sytuacji zwrotu części zamówienia, jeżeli kod opłaty kwalifikuje do zwrotu, tylko część opłaty przypisanej do tego wiersza zostanie zwrócona, gdy klient odda towar.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wielokanałowe zaawansowane opłaty automatyczne](omni-auto-charges.md)

[Włączanie i konfigurowanie opłat automatycznych według kanałów](auto-charges-by-channel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]