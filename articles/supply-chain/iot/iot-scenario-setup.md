---
title: Ustawienia scenariusza dla analizy Internetu rzeczy (IoT)
description: W tym temacie opisano sposób konfigurowania scenariusza w aplikacji Supply Chain Management dla analizy Internetu rzeczy (IoT).
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b87a9b73f49e73fe13b98fb11da939c9b30e0f6e
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386550"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Ustawienia scenariusza dla analizy Internetu rzeczy (IoT)

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób konfigurowania scenariusza w aplikacji Supply Chain Management dla analizy Internetu rzeczy (IoT). Aby można było skonfigurować scenariusze, musisz [skonfigurować usługi LCS](iot-lcs-setup.md).

W tym temacie skonfigurujesz scenariusz **przestoju sprzętu** w celu wygenerowania powiadomienia w aplikacji Supply Chain Management w przypadku awarii urządzenia.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Konfigurowanie scenariusza **przestoju sprzętu** w aplikacji Supply Chain Management

Scenariusz **przestoju sprzętu** mapuje sygnał oznaczający uszkodzenie części na próg alertu urządzenia. Urządzenie jest monitorowane tylko wtedy, gdy zostanie wybrane dla scenariusza i ustawione do uruchamiania w aplikacji Supply Chain Management. Jeśli czas, który upłynął od ostatniego odebrania sygnału oznaczającego uszkodzenie części, jest większy niż próg alertu, zostanie wyzwolone powiadomienie informujące o tym, że **urządzenie nie działa**. Jeśli urządzenie nadal działa, po odebraniu następnego sygnału **PartOut** zostanie wyzwolone powiadomienie informujące o tym, że **urządzenie działa**. Jeśli urządzeni nie działa przez 30 minut, jest wyzwalane nowe powiadomienie o tym, że **urządzenie nie działa**.

Scenariusz **przestoju sprzętu** obejmuje następujące zależności:

+ W celu wyzwolenia alertu na mapowanym urządzeniu musi zostać uruchomione zlecenie produkcyjne.
+ Sygnał reprezentujący uszkodzenie części mapowanego urządzenia musi zostać wysłany do usługi IoT Hub o unikatowej nazwie właściwości.
+ Komunikat usługi IoT Hub musi zawierać właściwość znacznika czasu systemu UNIX w milisekundach.

Aby skonfigurować scenariusz, wykonaj następujące kroki:

1. Zaloguj się do aplikacji Supply Chain Management.
2. Włącz flagę funkcji analizy Internetu rzeczy (IoT). Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Skonfiguruj metryki. Aby uzyskać więcej informacji, zobacz temat [.Jak skonfigurować metryki](iot-metrics-setup.md#configure-metrics).
4. Przejdź do obszaru **Kontrola produkcji**.
5. Przejdź do pozycji **Ustawienia \> Analiza Internetu rzeczy (IoT) \> Zarządzanie scenariuszami**.
6. Kliknij pozycję **Konfiguruj** na kafelku **przestoju sprzętu**. Kreator konfiguracji rozpoczyna się od strony **Definicja schematu czujnika sprzętu**. Celem jest skonfigurowanie schematu w aplikacji Supply Chain Management w celu dopasowania go do formatu JSON wiadomości usługi IoT. Można zdefiniować wiele schematów wiadomości. Aby uzyskać więcej informacji, zapoznaj się z tematem [Formaty schematów wiadomości dla centrum IoT](iot-schema-format.md). W tym przykładzie ładunek wiadomości zawiera partię wiadomości o następującym formacie:

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

7. Dodaj wiersz do tabeli.

    1. Ustaw **nazwę schematu** na **identyfikator**.
    2. Ustaw **ścieżkę schematu** na **/payload[\*]/id**.
    3. Ustaw **opis** na **identyfikator wiadomości**.

8. Dodaj wiersz do tabeli.

    1. Ustaw **nazwę schematu** na **znacznik czasu**.
    2. Ustaw **ścieżkę schematu** na **/payload[\*]/timestamp**.
    3. Ustaw **opis** na **znacznik czasu wiadomości**.

9. Dodaj wiersz do tabeli.

    1. Ustaw **nazwę schematu** na **wartość**.
    2. Ustaw **ścieżkę schematu** na **/payload[\*]/value**.
    3. Ustaw **opis** na **wartość wiadomości**.

    Nie trzeba definiować wszystkich właściwości w wiadomości, tylko te, których potrzebujesz. W tym przykładzie nie utworzono wiersza dla **głównego znacznika czasu**. Ścieżką **głównego znacznika czasu** byłaby ścieżka **/timestamp**.
  
10. Kliknij pozycję **Dalej**, aby przejść do strony **Mapa schematów czujnika sprzętu**.
11. W wierszu **identyfikatora zasobu sprzętu** ustaw **nazwę schematu** na **identyfikator**. Prawidłowe wartości są wyświetlane w tabeli rozwijanej.
12. W wierszu **czasu UTC** ustaw **nazwę schematu** na **znacznik czasu**. Prawidłowe wartości są wyświetlane w tabeli rozwijanej.
13. W wierszu **sygnału wygenerowanego przez sprzęt** ustaw **nazwę schematu** na **wartość**. Prawidłowe wartości są wyświetlane w tabeli rozwijanej.
14. Kliknij pozycję **Dalej**, aby otworzyć stronę **Konfiguracja identyfikatora zasobu sprzętowego**.
15. W tym kroku wartości komunikatów centrum IoT są mapowane na zasoby aplikacji Supply Chain Management.

    1. W tabeli **Wartości danych sygnału** dodaj nowy wiersz i wprowadź ciąg **IoTInt.Machine1225.PartOut** w kolumnie **Wartość**. Wartość **IoTInt.Machine1225.PartOut** pochodzi z właściwości **id** notacji JSON w komunikacie centrum IoT.
    2. Kliknij przycisk **Zapisz**.
    3. W tabeli **Mapowanie rekordów biznesowych** kliknij pozycję **Nowe**. Domyślna wartość **typu rekordu biznesowego** jest wypełniana automatycznie i nie trzeba jej zmieniać.
    4. W kolumnie **Rekord biznesowy** wybierz zasób urządzenia aplikacji Supply Chain Management, z którego jest wysyłana ta wartość sygnału.
    5. Kliknij przycisk **Zapisz**.
    6. Powtórz te kroki, dodając nowe mapowanie rekordu biznesowego dla urządzenia **Machine1226**. Można mapować wiele wartości danych sygnałów na pojedynczy rekord w aplikacji Supply Chain Management.

16. Użyj kolumny **Wybrane**, aby wybrać urządzenia do przetworzenia. Nie trzeba definiować wszystkich wartości sygnałów i nie trzeba wybierać wszystkich urządzeń.
17. Kliknij pozycję **Dalej**, aby przejść na stronę **Konfiguracja sygnału wygenerowanego przez część**.
18. W tabeli **Wartości danych sygnału** dodaj wiersz i ustaw **wartość** na **Prawda**. Wartość **Prawda** pochodzi z właściwości **value** notacji JSON w komunikacie centrum IoT. Można dodać dowolną liczbę wartości potrzebnych w danym scenariuszu.
19. Kliknij przycisk **Zapisz**.
20. Kliknij pozycję **Dalej**, aby przejść do strony **Próg przestoju sprzętu**. Wymienione urządzenia to urządzenia uprzednio mapowane do wartości sygnałów. W tym kroku zdefiniujesz próg określający, czy urządzenie nie działa. Jeśli na przykład wartość progu zostanie ustawiona na 10, aplikacja Supply Chain Management wygeneruje powiadomienie, jeśli przez 10 minut urządzenie nie wyśle komunikatu o niedziałającej części.
21. Kliknij pozycję **Dalej**, aby przejść na stronę **Włączanie scenariusza**. Przełącz suwak, aby włączyć scenariusz.
22. Kliknij przycisk **Zakończ**.

Konfiguracja scenariusza została zakończona. W ramach analizy Internetu rzeczy (IoT) automatycznie rozpocznie się przetwarzanie komunikatów usługi IoT Hub.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Konfigurowanie scenariusza **Jakość produktu** w aplikacji Supply Chain Management

Scenariusz **Jakość produktu** generuje powiadomienie, jeśli atrybut pozycji znajduje się poza określonym zakresem. Na przykład czujnik może wysłać wagę każdej pozycji do usługi IoT Hub. W aplikacji Supply Chain Management powiadomienie zostanie wygenerowane, jeśli pozycja była zbyt ciężka lub zbyt lekka.

Scenariusz obejmuje następujące zależności:

+ Na mapowanym urządzeniu musi być uruchomione zlecenie produkcyjne, które powoduje tworzenie produktu z mapowanym atrybutem partii, aby alert został wyzwolony.
+ Sygnał reprezentujący atrybut partii musi zostać wysłany do usługi IoT Hub o unikatowej nazwie właściwości.
+ Komunikat usługi IoT Hub musi zawierać właściwość znacznika czasu systemu UNIX w milisekundach.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Konfigurowanie scenariusza **Opóźnienia produkcji** w aplikacji Supply Chain Management

Scenariusz **opóźnień produkcji** generuje powiadomienie, jeśli przepływność produkcji spadnie poniżej wartości progowej. W tym scenariuszu sygnał **PartOut** jest wysyłany do usługi IoT Hub dla każdej wyprodukowanej pozycji. W aplikacji Supply Chain Management opóźnienie zamówienia jest obliczane na podstawie czasu, przez jaki jest planowane działanie zlecenia produkcyjnego, liczby pozycji do wyprodukowania, czasu trwania zadania oraz liczby odebranych sygnałów **PartOut**. Powiadomienie o opóźnieniu zostanie wygenerowane, jeśli liczba sygnałów **PartOut** dla zadania spadnie poniżej wartości progowej oczekiwanej wartości.

Scenariusz obejmuje następujące zależności:

+ W celu wyzwolenia alertu na mapowanym urządzeniu musi zostać uruchomione zlecenie produkcyjne.
+ Sygnał reprezentujący uszkodzenie części mapowanego urządzenia musi zostać wysłany do usługi IoT Hub o unikatowej nazwie właściwości.
+ Komunikat usługi IoT Hub musi zawierać właściwość znacznika czasu systemu UNIX w milisekundach.

## <a name="how-to-disable-a-scenario"></a>Jak wyłączyć scenariusz

Aby wyłączyć scenariusz, wykonaj następujące kroki:

1. W aplikacji Supply Chain Management przejdź do pozycji **Kontrola produkcji \> Ustawienia \> Analiza Internetu rzeczy (IoT) \> Zarządzanie scenariuszami**.
2. Kliknij pozycję **Konfiguruj** w scenariuszu.
3. Kliknij pozycję **Dalej**, aby przejść do ostatniej karty kreatora.
4. Przełącz suwak, aby wyłączyć scenariusz.
