---
title: Analiza Internetu rzeczy (IoT) — strona główna
description: Ten artykuł zawiera linki do informacji dotyczących analizy IoT.
author: johanhoffmann
ms.date: 08/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d8b2be25abaeff7404d7f4ef3cd825a50147fef
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228366"
---
# <a name="iot-intelligence-home-page"></a>Analiza Internetu rzeczy (IoT) — strona główna

[!include [banner](../../includes/banner.md)]
[!INCLUDE [iot-sdi-announcement](../../includes/iot-sdi-announcement.md)]

> [!IMPORTANT]
> Ta funkcja jest obecnie dostępna tylko w następujących krajach/regionach:
>
> - US (Stany Zjednoczone Ameryki)
> - EU (Unia Europejska)
> - AU (Australia)
> - CA (Kanada)
> - UK (Wielka Brytania)

Analiza IoT to dodatek do aplikacji Microsoft Dynamics 365 Supply Chain Management. Integruje on sygnały Internetu rzeczy (IoT) z danymi w aplikacji Supply Chain Management w celu tworzenia szczegółowych informacji do zastosowania w praktyce.

Analiza IoT obsługuje następujące scenariusze:

- **Opóźnienia produkcji** — w tym scenariuszu jest porównywany rzeczywisty czas cyklu z planowanym czasem cyklu. Supply Chain Management powiadamia Cię, gdy produkcja nie jest zaplanowana, więc możesz maksymalizować efektywność operacyjną i uniknąć opóźnień zamówień.
- **Przestój sprzętu** — ten scenariusz porównuje mierzony czas pracy z parametrami zdefiniowanymi przez użytkownika. Supply Chain Management powiadamia Cię o przekroczeniu progu przestoju, co umożliwia takie akcje, jak ponowne tworzenie zlecenia produkcyjnego lub tworzenie zlecenia pracy dotyczącego konserwacji.
- **Jakość produktu** — w tym scenariuszu są porównywane odczyty czujników (np. wilgotność i temperatura) z miernikami jakości zdefiniowanymi przez użytkownika. Supply Chain Management powiadamia Cię o odchyleniach, dzięki czemu można zachować standardy jakości i zminimalizować odpady.

Na poniższej ilustracji przedstawiono interakcję między usługami Azure IoT Hub, Analiza IoT i Supply Chain Management.

![IoT Hub, Analiza IoT i Supply Chain Management.](media/iot_intelligence.png)

<!-- KFM: hide setup info for now

## Setup

You can set up and configure IoT Intelligence without writing any code. Here are the basic steps.

1. [Set up Azure resources](iot-azure-setup.md) – Create an IoT hub, a Redis cache, and a key vault that can be accessed from Supply Chain Management.
2. [Message schema formats for IoT Hub](iot-schema-format.md) – Configure your devices to send messages to IoT Hub, and define the JavaScript Object Notation (JSON) message format.
3. In Feature Management, enable the IoT Intelligence feature flag. 
4. [Install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) – Install the add-in in LCS, and configure the Azure secrets.
5. [Set up metrics](iot-metrics-setup.md) – Set up metrics in Supply Chain Management.
6. [Scenario setup](iot-scenario-setup.md) – Set up the scenarios in Supply Chain Management.

-->

## <a name="tracking-and-maintenance"></a>Śledzenie i konserwacja

- [Monitorowanie scenariuszy w aplikacji Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
- [Wyłączenie scenariusza](iot-scenario-setup.md#disable-a-scenario)
- [Modyfikowanie działającego scenariusza analizy Internetu rzeczy (IoT)](iot-management.md#modify-a-running-iot-intelligence-scenario)
- [Opcje symulacji](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]