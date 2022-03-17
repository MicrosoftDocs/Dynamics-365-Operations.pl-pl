---
title: Projektowanie interfejsu wykonania hal produkcyjnych
description: W tym temacie opisano sposób projektowania zawartości interfejsu użytkownika dla każdej konfiguracji.
author: johanhoffmann
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration, JmgProductionFloorExecutionConfigurationTab
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ee206ced76dbdd356c77d34a4b8f197879e9a3f0
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384779"
---
# <a name="design-the-production-floor-execution-interface"></a>Projektowanie interfejsu wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]

Zawartość interfejsu użytkownika można zaprojektować dla każdej konfiguracji używanej przez interfejs wykonywania hali produkcyjnej. Na przykład pracownicy w jednej komórce roboczej mogą potrzebować możliwości otwierania instrukcji pracy na hali produkcyjnej, podczas gdy w innej komórce instrukcje nie są potrzebne. W takim przypadku należy utworzyć dwie konfiguracje, jedną z przyciskiem do otwierania załączników do dokumentów, a drugą bez tego przycisku.

## <a name="design-a-tab"></a>Projektowanie karty

Na stronie **Konfigurowanie interfejsu wykonania hal produkcyjnych** można tworzyć i konfigurować karty, wybierając **Projektuj karty** w okienku akcji.

Każda karta jest podzielona na cztery sekcje, jak to pokazano na poniższej ilustracji.

![Układ karty.](media/pfe-tab-layout.png "Układ karty")

Na ilustracji pokazano następujące elementy:

1. Podstawowy pasek narzędzi
1. Dodatkowy pasek narzędzi
1. Widok główny
1. Widok szczegółowy

Aby utworzyć i skonfigurować nową kartę, wykonaj następujące kroki:

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Wykonywanie produkcji \> Konfigurowanie interfejsu wykonania hal produkcyjnych**.

1. Wybierz opcję **Projektuj karty** w okienku akcji, aby otworzyć stronę **Projektuj karty**.

    ![Strona Projektuj karty.](media/pfe-design-tabs.png "Strona Projektuj karty")

1. Wybierz pozycję **Nowy** w okienku akcji.

1. W nagłówku strony wprowadź następujące ustawienia:

    - **Nazwa karty** - umożliwia określenie nazwy karty.
    - **Widok główny** — Wybierz spośród wstępnie zdefiniowanych list zadań (*Aktywne zadania*,  *Wszystkie zadania*, *Moje zadania* lub *Moje urządzenie*).
    - **Widok szczegółów** – umożliwia wybór pustej wartości lub **Szczegółów zadania**. Jeśli wybierzesz pustą wartość, na karcie nie będzie widoku szczegółowego. Jeśli wybierzesz **Szczegóły zadania**, widok szczegółowy będzie zawierał szczegółowy opis oferty pracy wybranej na liście ofert pracy w widoku głównym.

1. W sekcji **Główny pasek narzędzi** wybierz przyciski, które mają być dostępne na głównym pasku narzędzi. W kolumnie **Dostępne akcje** jest wyświetlana lista wszystkich przycisków, które można dodać. Kolumna **Wybrane akcje** zawiera listę wszystkich przycisków zawartych w bieżącej konfiguracji. Użyj przycisków między kolumnami, aby w razie potrzeby przenieść wybrane elementy między kolumnami. Użyj przycisków w górę iw dół obok kolumny **Wybrane akcje**, aby kontrolować kolejność, w jakiej przyciski są prezentowane w interfejsie użytkownika.

1. W sekcji **pomocniczy pasek narzędzi** wybierz przyciski, które mają być dostępne na pomocniczym pasku narzędzi. W kolumnie **Dostępne akcje** jest wyświetlana lista wszystkich przycisków, które można dodać. Kolumna **Wybrane akcje** zawiera listę wszystkich przycisków zawartych w bieżącej konfiguracji. Użyj przycisków między kolumnami, aby w razie potrzeby przenieść wybrane elementy między kolumnami. Użyj przycisków w górę iw dół obok kolumny **Wybrane akcje**, aby kontrolować kolejność, w jakiej przyciski są prezentowane w interfejsie użytkownika.

## <a name="associate-a-tab-with-a-configuration"></a>Umożliwia skojarzenie karty z konfiguracją

Po zaprojektowaniu wszystkich potrzebnych kart można je skojarzyć z konfiguracją.

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Wykonywanie produkcji \> Konfigurowanie interfejsu wykonania hal produkcyjnych**.

    ![Konfigurowanie wykonania produkcji.](media/pfe-config-prod-floor-execution.png "Konfigurowanie wykonania produkcji")

1. Na karcie skróconej **Wybór karty** wybierz pozycję **Dodaj**.

1. Nowy wiersz zostanie dodany do siatki. W przypadku nowego wiersza należy wybrać nazwę karty, która ma zostać dodana do konfiguracji.

1. W razie potrzeby dodaj kolejne karty.

1. Przyciski **Przenieś w górę** i **Przenieś w dół** na pasku narzędzi służą do rozmieszczania kart według potrzeb. Zakładki będą wyświetlane od lewej do prawej w kolejności pokazanej na powyższym zrzucie ekranu (zakładka u góry jest pokazana po lewej stronie).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
