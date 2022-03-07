---
title: Analiza Internetu rzeczy (IoT) — strona główna
description: Ten temat zawiera linki do informacji dotyczących analizy IoT.
author: robinarh
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: intro-internal
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f32cb5578f3c15a10f863980491a687f64312cd
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652062"
---
# <a name="iot-intelligence-home-page"></a>Analiza Internetu rzeczy (IoT) — strona główna

[!include [banner](../../includes/banner.md)]

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

+ **Opóźnienia produkcji** — w tym scenariuszu jest porównywany rzeczywisty czas cyklu z planowanym czasem cyklu. Supply Chain Management powiadamia Cię, gdy produkcja nie jest zaplanowana, więc możesz maksymalizować efektywność operacyjną i uniknąć opóźnień zamówień.
+ **Przestój sprzętu** — ten scenariusz porównuje mierzony czas pracy z parametrami zdefiniowanymi przez użytkownika. Supply Chain Management powiadamia Cię o przekroczeniu progu przestoju, co umożliwia takie akcje, jak ponowne tworzenie zlecenia produkcyjnego lub tworzenie zlecenia pracy dotyczącego konserwacji.
+ **Jakość produktu** — w tym scenariuszu są porównywane odczyty czujników (np. wilgotność i temperatura) z miernikami jakości zdefiniowanymi przez użytkownika. Supply Chain Management powiadamia Cię o odchyleniach, dzięki czemu można zachować standardy jakości i zminimalizować odpady.

Na poniższej ilustracji przedstawiono interakcję między usługami Azure IoT Hub, Analiza IoT i Supply Chain Management.

![IoT Hub, Analiza IoT i Supply Chain Management.](media/iot_intelligence.png)

## <a name="setup"></a>Konfiguracja

Analizę IoT można konfigurować bez pisania kodu. Oto podstawowe kroki.

1. [Skonfiguruj zasoby platformy Azure](iot-azure-setup.md) — utwórz centrum IoT, pamięć podręczną Redis i magazyn kluczy, które będą dostępny z poziomu aplikacji Supply Chain Management.
2. [Formaty schematu wiadomości dla usługi IoT Hub](iot-schema-format.md) — skonfiguruj urządzenia do wysyłania wiadomości do usługi IoT Hub oraz zdefiniuj format komunikatu JSON (JavaScript Object Notation).
3. W zarządzaniu funkcjami włącz flagę funkcji analizy IoT. 
4. [Zainstaluj dodatek analizy IoT w usłudze Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) — zainstaluj ten dodatek w usłudze LCS i skonfiguruj wpisy tajne platformy Azure.
5. [Skonfiguruj metryki](iot-metrics-setup.md) — skonfiguruj metryki w aplikacji Supply Chain Management.
6. [Skonfiguruj scenariusz](iot-scenario-setup.md) — skonfiguruj scenariusze w aplikacji Supply Chain Management.

## <a name="tracking-and-maintenance"></a>Śledzenie i konserwacja

+ [Monitorowanie scenariuszy w aplikacji Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
+ [Wyłączenie scenariusza](iot-scenario-setup.md#disable-a-scenario)
+ [Odinstalowywanie dodatku](iot-lcs-setup.md#uninstall-addin)
+ [Modyfikowanie działającego scenariusza analizy Internetu rzeczy (IoT)](iot-management.md#modify-a-running-iot-intelligence-scenario)
+ [Opcje symulacji](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]