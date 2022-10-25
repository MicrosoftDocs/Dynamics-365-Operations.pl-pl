---
title: Umożliwia skonfigurowanie symulowanego czujnika do testowania
description: W tym artykule opisano sposób skonfigurowania symulatora, który pozwala przetestować Sensor Data Intelligence bez instalowania fizycznych czujników.
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
ms.openlocfilehash: f12d6e1d417a260477b1eb4e027b850d1862f51f
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689812"
---
# <a name="set-up-a-simulated-sensor-for-testing"></a>Umożliwia skonfigurowanie symulowanego czujnika do testowania

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Jeśli użytkownik chce przetestować Sensor Data Intelligence bez instalacji fizycznych czujników, możesz użyć usługi *symulatora online Raspberry Pi z Azure IoT* do emulowania sygnałów czujnika i wysyłania ich do swojego rozwiązania Internetu rzeczy (IoT) w Microsoft Azure. Aby uzyskać więcej informacji o symulatorze, zobacz temat [Łączenie symulatora online Raspberry Pi z Azure IoT Hub (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started).

## <a name="video-instructions"></a>Instrukcje wideo

Poniższy film przedstawia sposób skonfigurowania symulowanego czujnika do testowania. Pozostałe sekcje tego artykułu zawierają te same instrukcje w formacie tekstowym.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE588g6]

## <a name="create-a-device-in-azure-iot-hub"></a>Utwórz urządzenie w Azure IoT Hub

Najpierw musisz skonfigurować urządzenie do uwierzytelniania sygnałów czujnika w usłudze Azure IoT Hub.

1. W systemie Azure przejdź do listy zasobów dla grupy zasobów utworzonej w celu użycia z Sensor Data Intelligence. (Aby uzyskać więcej informacji, zobacz temat [Wdrożenie rozwiązania IoT na platformie Azure](sdi-deploy-iot-solution-on-azure.md)).
1. Na liście zasobów znajdź rekord, w którym pole **Typ** jest ustawione na centrum *IoT Hub*. Wybierz wartość w kolumnie **Nazwa**, wybierz nazwę, aby otworzyć stronę szczegółów dla zasobu.
1. W okienku nawigacji po lewej stronie wybierz pozycję **Urządzenia**.
1. Na stronie **Urządzenia** wybierz pozycję **Dodaj urządzenie**.
1. Na stronie **Utwórz urządzenie** ustaw poniższe pola:

    - **Identyfikator urządzenia** — umożliwia wprowadzenie nazwy nowego urządzenia (na przykład *Moje-urządzenie-IoT*).
    - **Typ uwierzytelniania** — należy wybrać *Klucze symetryczne*.
    - **Automatycznie generuj klucze** — to pole wyboru należy zaznaczyć.
    - **Połącz to urządzenie z centrum IoT Hub** — wybierz opcję *Włącz*.

1. Wybierz przycisk **Zapisz**, aby powrócić do strony **Urządzenia**.
1. Znajdź nowe urządzenie na liście. Wybierz wartość w kolumnie **Identyfikator kolumny**, wybierz nazwę, aby otworzyć stronę szczegółów dla urządzenia. Jeśli na liście nie ma nowego urządzenia, odśwież stronę.
1. Kopiowanie wartości **Ciąg połączenia podstawowego** (na przykład przez wybranie przycisku **Kopiuj do Schowka**). Ta wartość będzie potrzebna później podczas skonfigurowania symulatora interfejsu IoT Raspberry Pi w celu emulowania sygnałów czujnika. Rozważ teraz wklejenie go na razie do pliku tekstowego.

## <a name="add-the-azure-connection-string-to-the-raspberry-pi-iot-simulator"></a>Dodaj ciąg połączenia systemu Azure do symulatora IoT Raspberry Pi

Aby dodać ciąg połączenia z urządzenia w centrum Azure IoT Hub do skryptu w usłudze Raspberry Pi, należy wykonać następujące kroki.

1. Otwórz [symulator Raspberry Pi z IoT](https://azure-samples.github.io/raspberry-pi-web-simulator/).
1. W okienku edytora kodu znajdź wiersz zawierający następujące polecenie.

    `const connectionString = '[Your IoT hub device connection string]';`

1. Umożliwia zastąpienie tekstu pomocy, w tym nawiasów, wartością **ciągu połączenia podstawowego** skopiowaną w poprzedniej sekcji. Nowy raport powinien przypominać następujący przykład.

    `const connectionString = 'HostName=XXX;DeviceId=YYY;SharedAccessKey=ZZZ';`

## <a name="add-sensor-ids-and-values-to-the-payload-in-the-raspberry-pi-iot-simulator"></a>Do symulatora Raspberry Pi z IoT dodaj identyfikatory czujników i wartości ładunku

Należy teraz skonfigurować symulator Raspberry Pi z IoT z symulowanymi czujnikami oraz wartości, które będą wysyłane jako ładunki.

- W edytorze kodu symulatora Raspberry Pi z IoT znajdź funkcję `getMessage` i edytuj ją tak, aby była taka, jak następujący kod. (Czujniki są ustawiane w wierszach `cb()`).

    ```cpp
    function getMessage(cb) {
        messageId++;
        sensor.readSensorData()
        .then(function (data) {
            cb(JSON.stringify({ value: 1, sensorId: 'MachineStatus' }), false);
            cb(JSON.stringify({ value: 70, sensorId: 'Quality' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'AssetMaintenance' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'ProductionDelay' }), false);
            cb(JSON.stringify({ value: 20, sensorId: 'AssetDowntime' }), false);
        })
        .catch(function (err) {
            console.error('Failed to read out sensor data: ' + err);
        });
    }
    ```

    > [!IMPORTANT]
    > Identyfikatory czujników zdefiniowane w edytorze kodów symulatora Raspberry Pi z IoT muszą być identyczne z identyfikatorami czujników, które zostaną określone później dla scenariuszy w Supply Chain Management. W poprzednim przykładzie kod używa identyfikatorów czujników, które mogą odczytywać ludzie. Jednak w rzeczywistym scenariuszu identyfikatory czujników będą globalnie unikatowymi identyfikatorami (GUID) dostarczanymi przez producenta czujnika. Identyfikatory czujników, które mogą odczytywać osoby, użyte w tym przykładowym kodzie w przykładach w [scenariuszu jakości produktu](sdi-scenario-product-quality.md), [scenariuszu konserwacji sjkładnika majątku](sdi-scenario-asset-maintenance.md), [scenariuszu opóźnień produkcji](sdi-scenario-production-delays.md) i [scenariuszu stanu maszyny](sdi-scenario-equipment-downtime.md)). W związku z tym należy używać tego kodu w przypadku pracy nad tymi scenariuszami.

## <a name="edit-the-interval-for-sending-sensor-signals"></a>Edytuj interwał wysyłania sygnałów czujnika

Należy teraz ustawić interwał, z jakim symulator Raspbbery Pi z IoT powinien wysyłać emulowane sygnały czujnika.

1. W edytorze kodu symulatora Raspberry Pi z IoT można znaleźć następujące wywołania funkcji.

    `setInterval(sendMessage, 2000);`

2. Domyślnie symulator Raspberry Pi z IoT wysyła sygnał czujnika co 2000 milisekund (dwie sekundy). Można jednak dostosować wartość zgodnie z wymaganiem.

## <a name="run-the-raspberry-pi-iot-simulator"></a>Uruchom symulator Raspberry Pi z IoT

- Wybierz opcję **Uruchom**, aby uruchomić symulator i rozpocząć wysyłanie symulowanych danych czujnika.
