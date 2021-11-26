---
title: Formaty schematów komunikatów centrum IoT
description: W tym temacie wyjaśniono, jak należy zaprojektować schemat komunikatu, który może być wyświetlany w analizie IoT.
author: tonyafehr
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b24a6e14182baa91299abad0da2987b2dca92601
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781619"
---
# <a name="schema-formats-for-iot-hub-messages"></a>Formaty schematów komunikatów centrum IoT

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono, jak należy zaprojektować schemat komunikatu, który może być wyświetlany w analizie IoT.

## <a name="message-requirements"></a>Wymagania komunikatu

Poniższe reguły mają zastosowanie do monitorowania komunikatów w analizie IoT:

+ Schematy komunikatów muszą być w formacie JSON (JavaScript Object Notation).
+ Właściwość **sygnatury czasowej** UNIX, gdzie wartość jest wyrażona w milisekundach (MS), musi być obecna w komunikacie Microsoft Azure IoT Hub.
+ Komunikat jest śledzony tylko wtedy, gdy zawiera wszystkie właściwości zdefiniowane w konfiguracji scenariusza. Na przykład po zdefiniowaniu właściwości **identyfikatora**, **sygnatury czasowej** i **wartości** zostanie monitorowany następujący komunikat.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    }
    ```

    Ten komunikat nie jest monitorowany, ponieważ brakuje właściwości **wartość**.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
    }
    ```

+ Usługa analizy IoT ignoruje właściwości w komunikacie, które nie są zdefiniowane w konfiguracji scenariusza. Na przykład po zdefiniowaniu właściwości **identyfikatora**, **sygnatury czasowej** i **wartości** analiza IoT będzie monitorować wszystkie poniższe komunikaty.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
        "machine" : "Machine1225",
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
         "activity": "PartOut"
    },
    ```

+ Analizy IoT w trybie dyskretnym ignorują komunikaty, które nie spełniają kryteriów konfiguracji scenariusza.
+ Istnieje możliwość definiowania i używania wielu typów schematów komunikatów.
+ Nie każdy typ schematu komunikatu musi być zdefiniowany. Należy zdefiniować tylko schematy, które będą używane w scenariuszach analizy IoT.

## <a name="id-value-pair-schema"></a>Schemat pary identyfikator-wartość

Para identyfikator-wartość jest wspólnym wzorcem schematów komunikatów analizy IoT. Używając pary identyfikator-wartość, można upewnić się, że schemat komunikatu jest taki sam we wszystkich scenariuszach. Poniżej znajduje się na przykład komunikat o scenariuszu **przestoju sprzętu** lub **opóźnień produkcji**.

```json
{
    "id": "IoTInt.Machine1225.PartOut",
    "timestamp": 1576016821614,
    "value": True
}
```

Oto komunikat dla scenariusza **jakości produktu**.

```json
{
    "id": "IoTInt.Machine1225.Temperature",
    "timestamp": 1576016821614,
    "value": 105
}
```

Oba poprzednie komunikaty zawierają właściwości **identyfikatora** i **wartości**. Podczas konfigurowania scenariusza wartości **identyfikatora** mogą być mapowane w tabeli **Wartości danych sygnału**. W scenariuszu **przestoju sprzętu** zostanie zamapowana wartość **IoTInt.Machine1225.PartOut**. W scenariuszu **Jakość produktu** zostanie zamapowana wartość **IoTInt.Machine1225.Temperature**.

Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją centrum IoT Azure](/azure/iot-hub/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]