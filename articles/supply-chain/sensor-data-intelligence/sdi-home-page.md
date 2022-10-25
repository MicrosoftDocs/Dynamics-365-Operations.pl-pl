---
title: Sensor Data Intelligence — strona główna
description: Ten artykuł zawiera omówienie Sensor Data Intelligence. Organizacje mogą używać tej funkcji do prowadzenia procesów biznesowych w Microsoft Dynamics 365 Supply Chain Management, w oparciu o sygnały Internetu rzeczy (IoT) wysyłanych przez maszyny i urządzenia na hali produkcyjnej.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: ba030364056db8b0524de22aacbc6528ef77813b
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689865"
---
# <a name="sensor-data-intelligence-home-page"></a>Sensor Data Intelligence — strona główna

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Sensor Data Intelligence dla Microsoft Dynamics 365 Supply Chain Management umożliwia organizacjom napędzanie procesów biznesowych w Supply Chain Management w oparciu o sygnały Internetu rzeczy (IoT) wysyłanych przez maszyny i urządzenia na hali produkcyjnej. Jest to zaktualizowana, zmieniona nazwa wersji *Analiza Internetu rzeczy (IoT)*, która była poprzednio dostępna w części Supply Chain Management.

Sensor Data Intelligence umożliwia wykonywanie następujących zadań:

- Zbieranie szczegółów dotyczących maszyn i urządzeń w celu aktualizacji wartości liczników konserwacji składnika majątku w ramach Supply Chain Management i prowadzenia prewencyjnej konserwacji.
- Skonfiguruj to rozwiązanie za pomocą prostego kreatora dołączania zamiast ręcznego instalowania i konfigurowania składników w rozwiązaniu Microsoft Dynamics Lifecycle Services (LCS).
- Wdrażaj składniki we własnej subskrypcji, aby mieć większą elastyczność zarządzania składnikami systemu Azure.
- Skonfiguruj, skaluj i rozszerz rozwiązanie jako logikę biznesową, która działa na komponentach systemu Azure. Składniki te są teraz zarządzane we własnej subskrypcji. W związku z tym można je dostosowywać zgodnie z unikatowymi potrzebami biznesowymi.

## <a name="business-scenarios"></a>Scenariusze biznesowe

Funkcja Sensor Data Intelligence umożliwia korzystanie z kilku typów funkcji, z których każda jest reprezentowana przez określony *scenariusz* w systemie. Każdy scenariusz zawiera wyspecjalizowany zestaw opcji konfiguracji w systemie, zgodnie z następującą tabelą.

| Scenariusz | Opis |
|---|---|
| [Przestój składnika majątku](sdi-scenario-asset-downtime.md) | Dokładne śledzenie wydajności składników majątku maszyn przy użyciu danych czujnika do śledzenia przestoju maszyny. |
| [Konserwacja składnika majątku](sdi-scenario-asset-maintenance.md) | Minimalizuj koszty konserwacji i wydłużaj okres użytkowania składników majątku, zwiększając plany konserwacji w oparciu o odczyty czujników o znaczeniu krytycznym dla składników majątku maszyn. |
| [Stan komputera](sdi-scenario-equipment-downtime.md) | Zapewnij efektywność operacji, korzystając z odczytów czujników w celu powiadomienia osób planujących o przestoju maszyn i zapewnienia opcji unikania potencjalnego opóźnienia. |
| [Jakość produktu](sdi-scenario-product-quality.md) | Aby zapewnić jakość partii produktów, porównując odczyty czujników pod względem rzeczywistych właściwości każdej partii produktów, takich jak wilgotność, temperatura czy miary i jakości zdefiniowane na podstawie niestandardowych ustawień. System powiadomi użytkowników o wystąpieniach odchyleń. |
| [Opóźnienia w produkcji](sdi-scenario-production-delays.md) | Użyj odczytów czujników do porównania rzeczywistego czasu cyklu z planowanym czasem cyklu i powiadamiania kierowników, gdy produkcja nie jest zgodna z harmonogramem. Dzięki temu przełożeni mogą zgodnie z potrzebą zainterweniować i zapewnić maksymalną efektywność operacji. |

## <a name="architecture"></a>Architektura

Poniższy diagram architektury zawiera omówienie rozwiązania i jego składników.

![Diagram architektury Sensor Data Intelligence.](media/sdi-architecture.png "Diagram architektury Sensor Data Intelligence")
