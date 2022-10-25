---
title: Parametry usługi Sensor Data Intelligence
description: Ten artykuł zawiera informacje o ustawieniach konfiguracji dostępnych na stronie Parametry Sensor Data Intelligence.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreServiceParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 5240537e3a6526ceb35253b9e68f46b1753c6a37
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689381"
---
# <a name="sensor-data-intelligence-parameters"></a>Parametry usługi Sensor Data Intelligence

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Strona **Parametry Sensor Data Intelligence** zawiera kilka ustawień, których można użyć do skonfigurowania tej funkcji. Te ustawienia obejmują parametry połączenia systemu Azure i parametr dla okresu istnienia komunikatów alertów, które są wysyłane do użytkowników w odpowiedzi na miary pomiary obrazu obrazu.

## <a name="read-and-change-connection-details-for-your-azure-iot-solution"></a>Odczytaj i zmień szczegóły połączenia dla rozwiązania Azure IoT

Zazwyczaj rozwiązanie Azure IoT jest ustawiane i łączy się z rozwiązaniem Microsoft Dynamics 365 Supply Chain Management, za pomocą strony **Wdróż i połącz zasoby Azure**, która przeprowadzi użytkownika przez obie te procedury. (Aby uzyskać więcej informacji, zobacz temat [Wdrażanie rozwiązania IoT w Azure](sdi-deploy-iot-solution-on-azure.md)). W dowolnym momencie można także wyświetlać i edytować szczegóły połączenia w Supply Chain Management.

1. Przejdź do **Administracja systemu \> Konfiguracja \> Sensor Data Intelligence \> Parametry Sensor Data Intelligence**.
1. Na karcie **Szereg czasowy** w polu **Ciąg połączenia sklepu metryk Redis** wprowadź wartość **Podstawowy ciąg połączenia (StackExchange.Redis)** dla rozwiązania Azure IoT, z którym chcesz nawiązać połączenie. Aby uzyskać więcej informacji dotyczących sposobu znalezienia tej wartości, zobacz [Wdrażanie rozwiązania IoT w Azure](sdi-deploy-iot-solution-on-azure.md).
1. Na karcie **Integracje** w polu **Identyfikator klienta aplikacji Azure AD** wprowadź wartość **Identyfikator klienta** dla rozwiązania Azure IoT, z którym chcesz nawiązać połączenie. Aby uzyskać więcej informacji dotyczących sposobu znalezienia tej wartości, zobacz [Wdrażanie rozwiązania IoT w Azure](sdi-deploy-iot-solution-on-azure.md).

## <a name="set-the-lifetime-of-alert-messages"></a>Ustawianie okresu istnienia komunikatów alertów

Za każdym razem, gdy Sensor Data Intelligence wykryje sytuację wymagającą uwagi użytkownika, z wysyła on powiadomienie do odpowiedniego użytkownika. Aby zapobiec ich nagromadzeniu w systemie, należy je ustawić jako wygasające po kilku dniach.

1. Przejdź do **Administracja systemu \> Konfiguracja \> Sensor Data Intelligence \> Parametry Sensor Data Intelligence**.
1. Na karcie **Powiadomienia** w polu **Czas do usunięcia powiadomień** wprowadź liczbę dni, przez które ma być wyświetlane powiadomienie. Po upływie określonego czasu powiadomienie zostanie usunięte.
