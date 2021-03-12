---
title: Monitorowanie analizy Internetu rzeczy (IoT) i zarządzanie nią
description: W tym temacie wyjaśniono, jak monitorować analizę Internetu rzeczy (IoT) i zarządzać nią.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7082f9e7640e8ef1b2873a954327b61a440e8ad0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000013"
---
# <a name="monitor-and-manage-iot-intelligence"></a>Monitorowanie analizy Internetu rzeczy (IoT) i zarządzanie nią

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono, jak monitorować analizę Internetu rzeczy (IoT) i zarządzać nią.

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a>Monitorowanie scenariuszy w aplikacji Microsoft Dynamics 365 Supply Chain Management

Przetwarzanie analizy Internetu (IoT) można monitorować w kilku miejscach:

+ **Moduły \> Kontrola produkcji \> Zapytania i raporty \> Analiza Internetu rzeczy (IoT) \> Powiadomienia** — wyświetla listę nierozwiązanych powiadomień.
+ **Moduły \> Kontrola produkcji \> Zapytania i raporty \> Analiza Internetu rzeczy (IoT) \> Powiadomienia zamknięte** — wyświetla listę powiadomień rozwiązanych lub odrzuconych.
+ **Moduły \> Kontrola produkcji \> Zapytania i raporty \> Analiza Internetu rzeczy (IoT) \> Klucze metryk** — wyświetla klucze metryk dla wykresów szeregu czasowego **Stan zasobu**.
+ **Moduły \> Kontrola produkcji \> Wykonywanie produkcji \> Stan zasobu** — śledzi określone metryki przy użyciu okna dialogowego **Konfigurowanie**. Jeśli scenariusz wykryje wyjątek, w powiadomieniu zostaną wyświetlone szczegóły wyjątku.
+ **Obszary robocze \> Zarządzanie halą produkcyjną \> Powiadomienia** — wyświetla listę nierozwiązanych powiadomień.

## <a name="modify-a-running-iot-intelligence-scenario"></a>Modyfikowanie działającego scenariusza analizy Internetu rzeczy (IoT)

Po uruchomieniu scenariusza można wprowadzić następujące zmiany:

+ Dodanie nowych definicji schematów czujników.
+ Wybranie nowych wartości danych sygnału.
+ Anulowanie wyboru istniejących wartości danych sygnału.
+ Dodanie i zmapowanie nowych wartości danych sygnału.
+ Zaktualizowanie wartości progowych.

Po uruchomieniu scenariusza nie można wprowadzać następujących zmian:

+ Usunięcie lub zmodyfikowanie definicji schematu, które są obecnie używane przez włączony scenariusz.
+ Zmiana wybranych ścieżek schematu dla włączonego scenariusza.

## <a name="simulation-options"></a>Opcje symulacji

Istnieje możliwość symulowania sygnałów urządzeń w fabryce. Aby uzyskać więcej informacji, zapoznaj się z tymi tematami.

+ [Łączenie zestawu IoT DevKit AZ3166 z usługą Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Łączenie symulatora online Raspberry Pi z Azure IoT Hub (Node.js)](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Omówienie akceleratora rozwiązania do symulacji urządzenia](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)
