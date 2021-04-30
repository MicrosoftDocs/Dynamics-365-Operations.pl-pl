---
title: Monitorowanie analizy Internetu rzeczy (IoT) i zarządzanie nią
description: W tym temacie wyjaśniono, jak monitorować analizę Internetu rzeczy (IoT) i zarządzać nią.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86e20b9e60e890833c0eb8573e92c0fbb27f8c9a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908426"
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

+ [Łączenie zestawu IoT DevKit AZ3166 z usługą Azure IoT Hub](/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Łączenie symulatora online Raspberry Pi z Azure IoT Hub (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Omówienie akceleratora rozwiązania do symulacji urządzenia](/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]