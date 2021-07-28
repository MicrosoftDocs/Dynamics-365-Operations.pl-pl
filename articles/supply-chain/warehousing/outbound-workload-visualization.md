---
title: Wychodzące wizualizacje obciążenia pracą
description: Ten temat zawiera informacje o wychodzących wizualizacjach obciążenia pracą. Ta funkcja umożliwia kierownikom i kierownikom magazynów tworzenie niestandardowych wykresów obciążenia, które można wykorzystać do monitorowania postępu bieżącej pracy i jej pozostałej ilości. Kierownicy magazynów mogą tworzyć wiele widoków i konfigurować automatyczne odświeżanie, gdy tego potrzebują.
author: Mirzaab
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-08-28
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: acfde5961f481f5d939f0c6388b80edfd65ee339
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351424"
---
# <a name="outbound-workload-visualization"></a>Wychodzące wizualizacje obciążenia pracą

[!include [banner](../includes/banner.md)]

Zaawansowane możliwości konfiguracji dostępne na stronie **Wizualizacja obciążenia wychodzącego** pozwalają kierownikom magazynu i przełożonym tworzyć niestandardowe wykresy obciążenia, które można wykorzystać do monitorowania postępu bieżącej pracy i jej pozostałej ilości. Kierownicy magazynów mogą tworzyć wiele widoków i konfigurować automatyczne odświeżanie, gdy tego potrzebują. Wizualizacje obciążenia wychodzącego są odpowiednie do wyświetlania na stronach wydajności magazynu.

Ta funkcja może służyć do śledzenia postępu pracy pobierania. Ta funkcja jest zintegrowana z zarządzaniem pracą, a jeśli jest skonfigurowane zarządzanie pracą, wizualizacje wychodzących obciążeń mogą przedstawiać obliczenie liczby godzin pozostałych do pobrania pracy, która jest wyświetlana (przefiltrowana).

## <a name="turn-on-the-outbound-workload-visualization-feature"></a>Włącz funkcję wizualizacji obciążenia wychodzącego

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [Zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Wizualizacja obciążenia wychodzącego*

## <a name="set-up-outbound-workload-visualizations"></a>Skonfiguruj wizualizacje wychodzących obciążeń

Aby skonfigurować wizualizacje, należy utworzyć zbiór filtrów (widoków) i zaprojektować każdy filtr tak, aby przedstawiał inny typ analizy. Aby zaprojektować filtry, należy skorzystać ze strony **Konfiguracja filtrów**.

Aby skonfigurować wizualizację obciążenia pracą wychodzącą, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie magazynem \> Raporty z monitoringu magazynu \> Wizualizacja obciążenia pracą wychodzącą**.

    Zostanie wyświetlona strona **Wizualizacja obciążenia pracą wychodzącą**. Po utworzeniu filtrów ta strona pokaże Twoją wizualizację. Można utworzyć dowolną liczbę filtrów. Wszystkie utworzone przez Ciebie filtry są zapisywane na Twoim koncie użytkownika, dzięki czemu możesz ich później użyć. Innymi słowy, każdy użytkownik będzie miał własny zestaw filtrów, które utworzył. Te filtry nie będą współużytkowane z innymi użytkownikami.

1. Na stronie **Wizualizacja obciążenia wychodzącego**, w okienku akcji, na karcie **Filtry** wybierz opcję **Konfiguruj Filtry**.
1. Na stronie **Konfigurowanie filtrów** w okienku akcji wybierz opcję **Nowy**, aby dodać filtr, a następnie określ dla niego następujące pola:

    - **Tabela grupy osi X** — Wybierz tabelę zawierającą pole, które ma być używane do grupowania wartości na osi X.
    - **Pole grupy osi X** — spośród pól tabeli wybranej w polu **Tabela grupy osi X** wybierz pole, które ma być używane do grupowania wartości osi X.
    - **Tabela wartości osi X** — Wybierz tabelę zawierającą pole, którego chcesz użyć do dalszej analizy grup.
    - **Pole grupy osi X** — spośród pól tabeli wybranej w polu **X-axis value field** wybierz pole zawierające wartości, które mają być analizowane dla każdej grupy.
    - **Automatyczne odświeżanie** — umożliwia określenie, czy wizualizacja powinna być automatycznie odświeżana.
    - **Interwał odświeżania (minuty)** — Wprowadź liczbę minut między automatycznymi odświeżeniami.
    - **Poziom wyświetlania** — Wybierz, czy wykres ma pokazywać otwarte linie, czy liczbę otwartych nagłówków.
    - **Typ pobrania** — Jeśli w polu **Poziom wyświetlania** ustawiono opcję _otwarte_ wiersze, należy określić, czy na wykresie ma być uwzględniana początkowa ilość wierszy pracy, pobrań etapowych czy zarówno odbiorów wstępnych, jak i odbiorów etapowych.
    - **Oddział** — umożliwia wybór oddziału, dla którego ma zostać załadowany wykres.
    - **Magazyn** — umożliwia wybór magazynu, dla którego ma zostać załadowany wykres.
    - **Dni do uwzględnienia** — umożliwia wprowadzenie liczby dni w przeszłości, dla których ma zostać wygenerowany wykres.
    - **Typ zlecenia pracy** — umożliwia wybór typów wychodzących zleceń pracy, według których ma być wykonywane filtrowanie.

    ![Skonfiguruj stronę filtrów.](media/work-viz-filters-1.png "Skonfiguruj stronę filtrów")

1. Zamknij stronę **Konfigurowanie filtrów** w celu powrotu do strony **Wizualizacje wychodzących obciążeń**.

    Na stronie **Wizualizacje wychodzących obciążeń** są teraz wyświetlane dane oparte na nowych ustawieniach filtru. Nowy filtr jest teraz dostępny i zostanie wybrany w polu **Filtr**. Na górze wykresu są dostępne następujące pola:

    - **Filtr** — to pole zawiera wszystkie utworzone dotychczas filtry. Wybierz filtr, aby wyświetlić jego dane na wykresie.
    - **Ostatnie odświeżenie** — to pole zawiera datę i godzinę ostatniej aktualizacji informacji na wykresie.
    - **Szacowany/rzeczywisty czas** — Jeśli w systemie skonfigurowano standardy pracy, ustaw tę opcję na *Tak*, aby wyświetlić skumulowane szacowane czasy kompletacji u góry każdej kolumny na wykresie. Jeśli nie są używane standardy pracy, ta opcja jest niedostępna.

    ![Przykładowa wizualizacja.](media/work-viz-chart.png "Przykładowa wizualizacja")

1. Wybierz dowolny słupek na wykresie, aby wyświetlić szczegóły skojarzonego wiersza pracy.

    ![Szczegóły wiersza pracy.](media/work-viz-work-details.png "Szczegóły wiersza pracy")

## <a name="example-outbound-workload-visualization-for-zones"></a>Przykład: Wychodzące wizualizacje obciążenia pracą dla stref

W tym przykładzie zachodzi potrzeba skonfigurowania wizualizacji pokazującego wiersze pracy dla każdej strefy oraz stan każdego wiersza pracy (_Otwarty_, _Zamknięty_ lub _Anulowany_). W takim przypadku można skonfigurować filtr, który ma następujące ustawienia:

- **Nazwa filtru** — umożliwia wprowadzenie nazwy tego filtru (np. _Stan strefy a pracy_).
- **Opis** — umożliwia wprowadzenie krótkiego opisu tego filtru (np. _Stan strefy a pracy_).
- **Tabela grupy osi X** — umożliwia wybór _Lokalizacji._
- **Grupa osi X** — umożliwia wybór _Identyfikatora strefy_.
- **Tabela wartości na osi X** — Wybierz opcję _Praca_, ponieważ chcesz wyświetlać pracę według strefy.
- **Pole wartości na osi X** — Wybierz opcję _Stan pracy_, ponieważ chcesz wyświetlać stan pracy.
- **Automatyczne odświeżanie** — umożliwia określenie, czy wizualizacja powinna być automatycznie odświeżana.
- **Typ pobrania** — Wybierz opcję _Początkowe i etapowe pobrania_, ponieważ chcesz uwzględnić zarówno początkowe pobrania, jak i pobrania z lokalizacji przemieszczania. Innymi słowy, użytkownik chce uwzględnić wszystkie posiadane wiersze pracy pobrania.
- **Poziom wyświetlania** — Wybierz _Otwarte wiersze_, ponieważ informacje mają być wyświetlane według wierszy, a nie w nagłówku pracy.

Na poniższej ilustracji pokazano przykład otrzymanego wykresu.

![Wizualizacja stanu strefy a pracy.](media/work-viz-chart.png "Wizualizacja stanu strefy a pracy")

Ten wykres zawiera dwie strefy o nazwach **FLOOR** i **BULK** oraz strefę o nazwie **Puste**. Strefa **Puste** reprezentuje wszystkie wiersze pracy, które nie są członkami żadnej strefy. Na wykresie zawsze są wyświetlane wszystkie niepowiązane filtrowane dane jako **Puste**, co zapewnia możliwie największą widoczność. W strefie **FLOOR** wykres przedstawia trzy zamknięte linie i cztery otwarte linie. W strefie **BULK** wykres przedstawia cztery zamknięte linie, jedną otwartą linię i 24 anulowane linie. Na koniec wykres pokazuje osiem zamkniętych linii, które nie są częścią żadnej strefy i dlatego są wymienione jako **Puste**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]