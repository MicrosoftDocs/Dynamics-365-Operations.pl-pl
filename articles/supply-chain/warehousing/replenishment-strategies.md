---
title: Strategie uzupełniania zapasów
description: Ten temat zawiera informacje o strategiach uzupełniania zapasów i objaśnieniach, w jaki sposób można skorzystać z pola Strategia uzupełnienia zapasów w wierszach szablonu uzupełnienia grupy popytu w celu wybrania sposobu uzupełniania zapasów.
author: Mirzaab
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-29
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 1aa48f231c5d98a22fa989fb6e6996b972be9089
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669888"
---
# <a name="replenishment-strategies"></a>Strategie uzupełniania zapasów

[!include [banner](../includes/banner.md)]

Szablony zdefiniowane na stronie **Szablony uzupełnienia zapasów** zawierają wiersze szablonu uzupełnienia zapasów na żądanie grupy, które umożliwiają wybranie sposobu uzupełniania zapasów. Każdy wiersz zawiera teraz pole **Strategia uzupełniania zapasów**.

Strategia *Ilość dla popytu grupy czynności* jest domyślną strategią. Jest to strategia uzupełniania zapasów użyta przed wprowadzeniem pola **Strategia uzupełniania zapasów**. W celu znalezienia lokalizacji, które mogą być uzupełniane, używa dyrektywy lokalizacji uzupełnienia zapasów. Następnie uzupełnia te lokalizacje, dopóki popyt nie zostanie zaspokojony.

W ramach strategii *Maksymalna pojemność lokalizacji* wprowadzono nowe funkcje. Podobnie jak strategia *Ilość dla popytu grupy czynności*, ta strategia używa dyrektyw lokalizacji uzupełnienia w celu znalezienia lokalizacji, które można uzupełnić, a następnie uzupełnia te lokalizacje do momentu, gdy popyt zostanie zaspokojony. Jest ona różna odstrategii *Ilość dla popytu grupy czynności*, ponieważ wszystkie lokalizacje uzupełniania są uzupełniane o maksymalne zdolności produkcyjne określone w lokalizacjach magazynowych. Strategia *Maksymalna pojemność lokalizacji* polega na próbie utworzenia pracy w celu przeniesienia żądanej ilości, powiększonej o część dodatkowej ilości, w celu wypełnienia uzupełniających lokalizacji. Jednak w niektórych przypadkach ta próba może się nie powieść. Na przykład lokalizacje zbiorcze mogą mieć za mało zapasów, aby pokryć dodatkową ilość. W takich przypadkach system wykrywa błąd i próbuje go naprawić.

Pora szczytu jest jednym z przykładów sytuacji, kiedy strategia *Maksymalna pojemność lokalizacji* jest preferowana od strategii *Ilość dla popytu grupy czynności*. W sezonie szczytu niektóre przedmioty mogą być sprzedawane w dużej ilości. Dzięki temu można z wyprzedzeniem uzupełnić odpowiednie lokalizacje pobrania, aby ograniczyć liczbę identyfikatorów pracy utworzonych na potrzeby uzupełnienia zapasów.

> [!IMPORTANT]
> Aby w pełni wykorzystać strategię *Maksymalna pojemność lokalizacji*, należy ponownie zdefiniować limity składowania dla odpowiednich lokalizacji. W przeciwnym razie strategia ta będzie działać podobnie do strategii *Ilość dla popytu grupy czynności*.

## <a name="turn-on-the-replenish-to-max-based-on-stocking-limits-feature"></a>Włącz opcję Uzupełnij do wartości maksymalnej na podstawie funkcji limitów składowania

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Uzupełnij do wartości maksymalnej na podstawie limitów składowania*

## <a name="set-up-replenishment-strategies"></a>Konfiguracja strategii uzupełniania zapasów

Aby uzyskać dostęp do szablonów, przejdź do **Zarządzanie magazynem \> Konfiguracja \> Uzupełnianie zapasów \> Szablony uzupełniania zapasów**. W sekcji **Omówienie** wybierz lub utwórz szablon grupy czynności do uzupełnienia (uzupełnienie), w którym pole **Typ uzupełnienia** ma wartość *Popyt grupy czynności*. Następnie skonfiguruj wiersze szablonu uzupełnienia w sekcji **Szczegóły szablonu uzupełniania zapasów**. W przypadku każdego wiersza w polu **Strategia uzupełniania zapasów** wybierz strategię uzupełniania zapasów, która ma zostać użyta.

![Strona szablonów uzupełniania zapasów.](media/ReplenTempWaveDmdMaxLocCap.png "Strony szablonów uzupełniania zapasów")

Jeśli kolumna **Strategia uzupełniania zapasów** nie jest wyświetlana w siatce w sekcji **Szczegóły szablonu uzupełniania zapasów**, upewnij się, że funkcja została włączona i że wybrany szablon uzupełnienia zapasów ma typ uzupełnienia zapasów ustawiony na *Popyt grupy czynności*.

> [!NOTE]
> Strategia *Ilość dla popytu grupy czynności* jest domyślną strategią. W związku z tym wystarczy zaktualizować wiersze szablonu uzupełnienia, w którym ma być używana strategia *Maksymalna pojemność lokalizacji*.

## <a name="example-scenarios"></a>Przykładowe scenariusze

### <a name="example-1"></a>Przykład 1

W tym przykładzie istnieje tylko jeden szablon uzupełnienia zapasów, który ma tylko jeden wiersz szablonu uzupełnienia zapasów.

Tworzone jest zamówienie sprzedaży na 130 sztuk (szt.) pozycji A0001. Aby można było zwolnić zamówienie do magazynu, magazyn jest ustawiany w następujący sposób:

- Istnieje tylko jedna lokalizacja zbiorcza i ma 500 szt. dostępnych zapasów.
- Istnieją trzy lokalizacje pobrania, z których każda ma limit składowania wynoszący 100 szt. (Należy pamiętać, że limity składowania są wymagane w odniesieniu do strategii *Maksymalna pojemność lokalizacji*.)
- Lokalizacje odkładania zapasów są takie same, jak lokalizacje pobierania sprzedaży.
- Jednostka uzupełnienia to puddełko (1 pudełko = 20 szt.).

W momencie zamówienia w lokalizacjach pobrania sprzedaży dostępne są następujące zapasy:

- **Pobranie-001:** 20 szt. (1 pudełko)
- **Pobranie-002:** 0 szt.
- **Pobranie-003:** 0 szt.

Początkowo strategia uzupełniania jest ustawiona na *Ilość dla popytu grupy czynności*.

Po zwolnieniu zamówienia sprzedaży do magazynu i uruchomieniu przetwarzania grupy czynności dla grupy czynności, otrzymasz następującą pracę uzupełniania:

- **Praca uzupełniania zapasów 1:** Pobierz 4 pudełka z lokalizacji zbiorczej i umieść je w lokalizacji Pobranie-001.
- **Praca uzupełniania zapasów 2:** Pobierz 2 pudełka z lokalizacji zbiorczej i umieść je w lokalizacji Pobranie-002.

Otrzymujesz dwa identyfikatory pracy uzupełniania, ponieważ musisz uzupełnić dwie lokalizacje, a zadania wielkokrotnego odkładania nie są obsługiwane.

W przypadku ustawienia strategii uzupełniania zapasów na *Maksymalna pojemność lokalizacji*, otrzymasz następującą pracę uzupełniania zapasów:

- **Praca uzupełniania zapasów 1:** Pobierz 4 pudełka z lokalizacji zbiorczej i umieść je w lokalizacji Pobranie-001.
- **Praca uzupełniania zapasów 2:** Pobierz 5 pudełka z lokalizacji zbiorczej i umieść je w lokalizacji Pobranie-002.

[![Przykład 1.](media/ReplenTemp_example_1.png "Przykład 1")](media/ReplenTemp_example_1_large.png)

### <a name="example-2"></a>Przykład 2

W tym przykładzie pokazano, co się dzieje w przypadku, gdy lokalizacja zbiorcza nie ma wystarczającej ilości zapasów, aby pokryć ilość dodatkową. W tym samym scenariuszu jest używany przykład 1, ale w lokalizacji zbiorczej jest 160 szt. (8 pudełek).

Strategia *Ilość dla popytu grupy czynności* tworzy tę samą pracę jak w przykładzie 1.

Jednak, ponieważ strategia *Maksymalna pojemność lokalizacji* powoduje próbę utworzenia identyfikatorów pracy jak w przykładzie 1, może to zakończyć się niepowodzeniem. W tym momencie system próbuje odzyskać.

W zależności od ustawienia opcji **Zezwalaj na podział** w dyrektywach lokalizacji dla pobrania uzupełnienia zapasów, możliwe są dwa wyniki:

- Jeśli opcja **Zezwalaj na podział** jest ustawiona na wartość *Tak*, tworzona jest następująca praca uzupełniania zapasów:

    - **Praca uzupełniania zapasów 1:** Pobierz 4 pudełka z lokalizacji zbiorczej i umieść je w lokalizacji Pobranie-001.
    - **Praca uzupełniania zapasów 2:** Pobierz 4 pudełka z lokalizacji zbiorczej i umieść je w lokalizacji Pobranie-002.

- Jeśli opcja **Zezwalaj na podział** jest ustawiona na wartość *Nie*, tworzona jest następująca praca uzupełniania zapasów:

    - **Praca uzupełniania zapasów 1:** Pobierz 4 pudełka z lokalizacji zbiorczej i umieść je w lokalizacji Pobranie-001.
    - **Praca uzupełniania zapasów 2:** Pobierz 2 pudełka z lokalizacji zbiorczej i umieść je w lokalizacji Pobranie-002.

Wyniki różnią się ze względu na informacje, które są dostępne podczas tworzenia pracy. Jeśli pole **Zezwalaj na podział** jest ustawione na wartość *Tak* w dyrektywach dotyczących pobrania uzupełnienia zapasów, wiadomo, że znaleziono 160 sztuk. Można więc utworzyć pracę dla tej ilości. Jeśli jednak opcja **Zezwalaj na podział** jest ustawiona na *Nie*, nie wiadomo o istnieniu 160 sztuk. Ponieważ dodatkowa ilość, którą zdecydowałeś się uzupełnić, wynosiła 3 pudełka, odrzucasz tę dodatkową ilość i ponownie próbujesz użyć oryginalnej ilości.

[![Przykład 2.](media/ReplenTemp_example_2.png "Przykład 2")](media/ReplenTemp_example_2_large.png)

Dlatego, aby uzyskać maksymalną ilość w uzupełnianych lokalizacjach, należy ustawić opcję **Zezwalaj na podział** na *Tak* w dyrektywach lokalizacji dotyczących pobierania do uzupełnienia zapasów.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]