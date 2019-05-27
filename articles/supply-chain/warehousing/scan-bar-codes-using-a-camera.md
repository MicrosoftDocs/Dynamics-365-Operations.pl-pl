---
title: Skanowanie kodów kreskowych za pomocą aparatu w programie Dynamics 365 for Finance and Operations — Magazynowanie
description: W tym temacie opisano, jak w programie Dynamics 365 for Finance and Operations — Magazynowanie skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym.
author: MarkusFogelberg
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: e78d0a82d3ca66a6912ea1a9517296ca241edf1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559053"
---
# <a name="scan-bar-codes-using-a-camera-in-dynamics-365-for-finance-and-operations--warehousing"></a>Skanowanie kodów kreskowych za pomocą aparatu w programie Dynamics 365 for Finance and Operations — Magazynowanie

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak w programie Dynamics 365 for Finance and Operations — Magazynowanie skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym. 

## <a name="prerequisites"></a>Wymagania wstępne
Aby można było używać tej funkcji, trzeba mieć zainstalowaną wersję 1.2.0.0 modułu Magazynowanie, a urządzenie musi być wyposażone w aparat. Gdy otworzysz aplikację po zaktualizowaniu, pojawi się monit o pozwolenie aplikacji Dynamics 365 for Finance and Operations — Magazynowanie na używanie aparatu. Jeśli urządzenie nie ma aparatu, monit nie będzie wyświetlany i nie będzie można używać aparatu jako skanera. 

## <a name="setup"></a>Konfiguracja
W aplikacji Magazynowanie w ustawieniach wyświetlania można określić, czy aparat ma być używany do skanowania kodów kreskowych. Po włączeniu opcji **Używaj aparatu jako skanera** można używać aparatu do każdego pola wejściowego, które ma ustawiony preferowany tryb wprowadzania **Skanowanie**. 

Aby określić, czy pole wejściowe powinno obsługiwać skanowanie, w programie Dynamics 365 for Finance and Operations na stronie **Nazwy pól w aplikacji magazynowej** w ustawieniu **Preferowany tryb wprowadzania** zaznacz wartość **Skanowanie**. Gdy ta opcja jest zaznaczona, aparat może służyć do skanowania w aplikacji Magazynowanie. Aby uzyskać informacje dotyczące sposobu konfigurowania nazw pól w aplikacji Magazynowanie, zobacz [Konfigurowanie nazw pól aplikacji w aplikacji Magazynowanie](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).

## <a name="supported-bar-code-formats"></a>Obsługiwane formaty kodów kreskowych
Obsługiwane są najpopularniejsze formaty kodów kreskowych, w tym Kod 128, Kod 39, Kod 93, EAN-8, EAN-13, UPC-E, UPC-A i kody QR. 

## <a name="navigation"></a>Nawigacja
Strona Aparat będzie inicjowana z każdej strony, w której pole wejściowe ma ustawiony preferowany tryb wprowadzania Skanowanie. Na stronie Aparat poniższe opcje służą do nawigowania:
- Kliknij przycisk Wstecz, aby powrócić do strony Zadanie i szczegóły. 
- Kliknij ikonę ołówka na stronie Zadanie i szczegóły, aby przejść do strony, gdzie można wpisać dane wejściowe ręcznie.
- Kliknij ikonę aparatu na stronie Zadanie i szczegóły, aby wrócić do strony Aparat. 

| Strona Zadanie i szczegóły | Strona Aparat | 
| :---------------------: | :--------------------: |
| ![camera-scanning-example-task-detail-page](./media/camera-scanning-example-task-detail-page50.png)          | ![camera-scanning-example-camera-page-smaller](./media/camera-scanning-example-camera-page50.png)          |

Na stronie Aparat po kliknięciu przycisku Aparat będzie on wyszarzony podczas próby zidentyfikowania kodu kreskowego. Jeśli kod kreskowy nie zostanie zidentyfikowany w ciągu 5 sekund, upłynie limit czasu procesu, a przycisk aparatu znów stanie się dostępny. Wtedy będzie można ponownie spróbować zeskanować kod kreskowy.

Kierując aparat na kod kreskowy, w celu uzyskania najlepszego wyniku utrzymuj kod kreskowy w granicach nawiasów kwadratowych. Jeśli kod kreskowy zostanie zeskanowany pomyślnie, rezultat zostanie przetworzony, po czym nastąpi przejście do następnego kroku. Jeśli następny krok zawiera kolejne pole wejściowe z ustawionym preferowanym trybem wprowadzania Skanowanie, strona Aparat zostanie ponownie uruchomiona. Jeśli w następnym kroku nie występuje pole obsługujące skanowanie, strona Aparat nie zostanie zainicjowana.

