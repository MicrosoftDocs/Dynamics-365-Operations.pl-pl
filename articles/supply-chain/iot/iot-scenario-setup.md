---
title: Ustawienia scenariusza dla analizy Internetu rzeczy (IoT)
description: W tym temacie wyjaśniono, jak skonfigurować scenariusze dla analizy IoT w Microsoft Dynamics 365 Supply Chain Management.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d1deaa2130b63272da39a42315c6a1bc4b7ccb8a
ms.sourcegitcommit: 8adc65e26d78e229271eb427659a87ee5f371319
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "3814066"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Ustawienia scenariusza dla analizy Internetu rzeczy (IoT)

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować scenariusze dla analizy IoT w Microsoft Dynamics 365 Supply Chain Management. Przed skonfigurowaniem scenariusza trzeba ustawić [Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).

W tym temacie skonfigurujesz scenariusz **przestoju sprzętu** w celu wygenerowania powiadomienia w aplikacji Supply Chain Management w przypadku awarii urządzenia. W tym temacie przedstawiono również sposób konfigurowania scenariusza **Jakości produktu** w taki sposób, aby było generowane powiadomienie, jeśli atrybut towaru wykracza poza określony zakres i jak skonfigurować scenariusz **opóźnienia produkcji**, aby było generowane powiadomienie, jeśli przepływność produkcji spadnie poniżej wartości ustalonego progu.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Konfigurowanie scenariusza przestoju sprzętu w aplikacji Supply Chain Management

Scenariusz **przestoju sprzętu** mapuje sygnał oznaczający **uszkodzenie części** na próg alertu urządzenia. Urządzenie jest monitorowane tylko wtedy, gdy zostanie wybrane dla scenariusza i ustawione do **uruchamiania** w aplikacji Supply Chain Management. Jeśli czas, który upłynął od ostatniego odebrania sygnału oznaczającego **uszkodzenie części** od maszyny jest większy niż próg alertu, zostanie wyzwolone powiadomienie informujące o tym, że **urządzenie nie działa**. Jeśli urządzenie nadal działa, po odebraniu następnego sygnału **PartOut** zostanie wyzwolone powiadomienie informujące o tym, że **urządzenie działa**. Jeśli urządzeni nie działa przez 30 minut, jest wyzwalane nowe powiadomienie o tym, że **urządzenie nie działa**.

Scenariusz **przestoju sprzętu** obejmuje następujące zależności:

+ Alertu na mapowanym urządzeniu może zostać uruchomiony tylko, jeśli uruchomione jest zlecenie produkcyjne na zamapowanej maszynie.
+ Sygnał reprezentujący **uszkodzenie części** mapowanego urządzenia musi zostać wysłany do usługi IoT Hub i musi być zastosowana unikatowa nazwa właściwości.
+ **Sygnatura czasowa** UNIX, gdzie wartość jest wyrażona w milisekundach (MS), musi być obecna w komunikacie Azure IoT Hub.

Aby skonfigurować scenariusz, wykonaj następujące kroki.

1. Zaloguj się do modułu Supply Chain Management.
2. Włącz flagę funkcji analizy Internetu rzeczy (IoT). Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
3. Skonfiguruj metryki. Aby uzyskać więcej informacji, zobacz temat [.Jak skonfigurować metryki](iot-metrics-setup.md#configure-metrics).
4. Przejdź do **Kontroli produkcji \> Konfiguracji \> Analizy IoT \> Zarządzanie scenariuszami**.
6. Na kafelku **Przestój sprzętu** wybierz opcję **Konfiguruj**, aby otworzyć Kreator konfiguracji.

   Jego pierwsza strona to **Definicja schematu czujnika sprzętu**. Na tej stronie należy skonfigurować schemat w ramach Supply Chain Management, tak aby odpowiadał on formatowi notacji języka JavaScript (kod JSON) komunikatów Centrum IoT. Można zdefiniować wiele schematów wiadomości. Aby uzyskać więcej informacji, zapoznaj się z tematem [Wiadomości schematów dla centrum IoT](iot-schema-format.md). W tym przykładzie ładunek wiadomości zawiera partię wiadomości o następującym formacie.

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. Dodaj wiersz do tabeli i określ następujące wartości:

    1. Ustaw pole **nazwa schematu** na **identyfikator**.
    2. Ustaw pole **ścieżka schematu** na **/payload\[\*\]/id**.
    3. Ustaw pole **opis** na **identyfikator wiadomości**.

8. Dodaj kolejny wiersz do tabeli i określ następujące wartości:

    1. Ustaw pole **nazwa schematu** na **znacznik czasu**.
    2. Ustaw pole **ścieżka schematu** na **/payload\[\*\]/timestamp**.
    3. Ustaw pole **opis** na **znacznik czasu wiadomości**.

9. Dodaj kolejny wiersz do tabeli i określ następujące wartości:

    1. Ustaw pole **nazwa schematu** na **Wartość**.
    2. Ustaw pole **ścieżka schematu** na **/payload\[\*\]/value**.
    3. Ustaw pole **opis** na **Wartość wiadomości**.

    > [!NOTE]
    > Nie trzeba definiować wszystkich właściwości w wiadomości. Zdefiniuj tylko wymagane właściwości. W poprzednich krokach nie utworzono wiersza dla **głównego znacznika czasowego**. Ścieżką **głównego znacznika czasu** byłaby ścieżka **/timestamp**.

10. Wybierz pozycję **Dalej**, aby przejść do strony **Mapa schematów czujnika sprzętu**.
11. W wierszu **identyfikatora zasobu sprzętu** w polu **nazwa schematu** wybierz **identyfikator**.
12. W wierszu **czasu UTC** w polu **nazwę schematu** wybierz **znacznik czasu**.
13. W wierszu **sygnału wygenerowanego przez sprzęt** w polu **nazwa schematu** wybierz **wartość**.
14. Wybierz **Dalej**, aby przejść do strony **Konfiguracja identyfikatora zasobu sprzętowego**.
15. Skorzystaj z następujących kroków, aby zamapować wartości w centrum komunikatów IoT na zasoby aplikacji Supply Chain Management:

    1. W tabeli **Wartości danych sygnału** dodaj nowy wiersz. W polu **Wartość** wprowadź **IoTInt.Machine1225.PartOut**. Wartość ta pochodzi z JSON **identyfikator** we właściwości centrum wiadomości IoT.
    2. Wybierz opcję **Zapisz**.
    3. W tabeli **Mapowanie rekordów biznesowych** wybierz pozycję **Nowe**. Domyślna wartość **typu rekordu biznesowego** jest wypełniana automatycznie i nie trzeba jej zmieniać.
    4. W polu **Rekord biznesowy** wybierz zasób urządzenia aplikacji Supply Chain Management, z którego jest wysyłana ta wartość sygnału.
    5. Wybierz opcję **Zapisz**.
    6. Powtórz te kroki, aby dodać nowe mapowanie rekordu biznesowego dla urządzenia **Machine1226**. Można mapować wiele wartości danych sygnałów na pojedynczy rekord w aplikacji Supply Chain Management.

16. Użyj kolumny **Wybrane**, aby wybrać urządzenia do przetworzenia. Nie trzeba definiować wszystkich wartości sygnałów i nie trzeba wybierać wszystkich urządzeń.
17. Wybierz **Dalej**, aby przejść na stronę **Konfiguracja sygnału wygenerowanego przez część**.
18. W tabeli **Wartości danych sygnału** dodaj wiersz i ustaw pole **wartość** na **Prawda**. Wartość ta pochodzi z JSON **wartość** we właściwości centrum wiadomości IoT. Można dodać dowolną liczbę wartości wymaganych w danym scenariuszu.
19. Wybierz opcję **Zapisz**.
20. Wybierz pozycję **Dalej**, aby przejść do strony **Próg przestoju sprzętu**. Wymienione urządzenia to urządzenia uprzednio zamapowane do wartości sygnałów. Na tej stronie zdefiniujesz próg określający, czy urządzenie działa, czy nie. Jeśli na przykład wartość progu zostanie ustawiona na **10**, aplikacja Supply Chain Management wygeneruje powiadomienie, jeśli przez 10 minut urządzenie nie wyśle komunikatu o **niedziałającej części**.
21. Wybierz pozycję **Dalej**, aby przejść na stronę **Włączanie scenariusza**. Ustaw wartość, aby uruchomić scenariusz.
22. Wybierz **Zakończ**.

Konfiguracja scenariusza została zakończona. W ramach analizy Internetu rzeczy (IoT) automatycznie rozpocznie się przetwarzanie komunikatów usługi IoT Hub.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Konfigurowanie scenariusza Jakość produktu w aplikacji Supply Chain Management

Scenariusz **Jakość produktu** generuje powiadomienie, jeśli atrybut pozycji znajduje się poza określonym zakresem. Na przykład czujnik wyśle wagę każdej pozycji do usługi IoT Hub. W aplikacji Supply Chain Management powiadomienie zostanie wygenerowane, jeśli pozycja była zbyt ciężka lub zbyt lekka.

Scenariusz **jakości produktu** obejmuje następujące zależności:

+ Aby alert został wyzwolony, na mapowanym urządzeniu musi być uruchomione zlecenie produkcyjne, które powoduje tworzenie produktu z mapowanym atrybutem partii.
+ Sygnał reprezentujący atrybut partii musi zostać wysłany do centrum IoT Hub i musi zawierać unikatową nazwę właściwości.
+ **Sygnatura czasowa** UNIX, gdzie wartość jest wyrażona w milisekundach (ms), musi być obecna w komunikacie Azure IoT Hub.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Konfigurowanie scenariusza Opóźnienia produkcji w aplikacji Supply Chain Management

Scenariusz **opóźnień produkcji** generuje powiadomienie, jeśli przepływność produkcji spadnie poniżej wartości progowej. W tym scenariuszu sygnał **PartOut** jest wysyłany do usługi IoT Hub dla każdej produkowanej pozycji. W Supply Chain Management opóźnienie jest obliczane na podstawie czasu, w jakim ma być uruchomione zlecenia produkcyjne, liczby towarów, które powinny zostać wyprodukowane, ilości czasu, przez jaki zadanie jest wykonywane oraz liczby odebranych sygnałów **uszkodzenia części**. Powiadomienie o opóźnieniu jest generowane, jeśli liczba sygnałów **PartOut** dla zadania spadnie poniżej wartości progowej.

Scenariusz **Opóźnienia produktu** obejmuje następujące zależności:

+ Alertu na mapowanym urządzeniu może zostać uruchomiony tylko, jeśli uruchomione jest zlecenie produkcyjne na zamapowanej maszynie.
+ Sygnał reprezentujący **uszkodzenie części** mapowanego urządzenia musi zostać wysłany do usługi Azure IoT Hub i musi być zastosowana unikatowa nazwa właściwości.
+ **Sygnatura czasowa** UNIX, gdzie wartość jest wyrażona w milisekundach (ms), musi być obecna w komunikacie Azure IoT Hub.

## <a name="disable-a-scenario"></a>Wyłączenie scenariusza

Aby wyłączyć scenariusz, wykonaj następujące kroki.

1. W aplikacji Supply Chain Management przejdź do pozycji **Kontrola produkcji \> Ustawienia \> Analiza Internetu rzeczy (IoT) \> Zarządzanie scenariuszami**.
2. Na kafelku dla scenariusza wybierz opcję **Konfiguruj**.
3. Wybierz pozycję **Dalej**, aby przejść na ostatnia stronę kreatora.
4. Wybierz opcję wyłączenia scenariusza.
