---
title: Skanowanie kodów kreskowych za pomocą aparatu w aplikacji mobilnej Warehouse Management
description: W tym temacie opisano, jak w rozwiązaniu aplikacja Warehouse Management skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym.
author: Mirzaab
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: cc58d88865fea17e0e27463b25e2ba815ee1a5b1
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2021
ms.locfileid: "7901994"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a>Skanowanie kodów kreskowych za pomocą aparatu w aplikacji mobilnej Warehouse Management

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak w rozwiązaniu aplikacja Warehouse Management skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym.

## <a name="setup"></a>Konfiguracja

W aplikacji Warehouse Management w ustawieniach wyświetlania można określić, czy aparat ma być używany do skanowania kodów kreskowych. Po włączeniu opcji **Używaj aparatu jako skanera** można używać aparatu do każdego pola wejściowego, które ma ustawiony preferowany tryb wprowadzania **Skanowanie**.

Aby określić, czy pole wejściowe powinno obsługiwać skanowanie, na stronie **Nazwy pól w aplikacji Magazynowanie** w ustawieniu **Preferowany tryb wprowadzania** zaznacz wartość **Skanowanie**. Gdy ta opcja jest zaznaczona, aparat może służyć do skanowania w aplikacji Warehouse Management. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie pól aplikacji mobilnej Warehouse Management](configure-app-field-names-priorities-warehouse.md).

## <a name="supported-bar-code-formats"></a>Obsługiwane formaty kodów kreskowych

Obsługiwane są najpopularniejsze formaty kodów kreskowych, w tym Kod 128, Kod 39, Kod 93, EAN-8, EAN-13, UPC-E, UPC-A i kody QR.

## <a name="navigation"></a>Nawigacja

Strona Aparat będzie inicjowana z każdej strony, w której pole wejściowe ma ustawiony **Preferowany tryb wprowadzania** *Skanowanie*. Na stronie aparatu poniższe opcje służą do nawigowania:

- Wybierz przycisk Wstecz, aby powrócić do strony **Zadanie i szczegóły**.
- Wybierz ikonę ołówka na stronie **Zadanie i szczegóły**, aby przejść do strony, gdzie można wpisać dane wejściowe ręcznie.
- Wybierz ikonę aparatu na stronie **Zadanie i szczegóły**, aby wrócić do strony Aparat.

Na stronie Aparat po kliknięciu przycisku aparatu będzie on wyszarzony podczas próby zidentyfikowania kodu kreskowego. Jeśli kod kreskowy nie zostanie zidentyfikowany w ciągu 5 sekund, upłynie limit czasu procesu, a przycisk aparatu znów stanie się dostępny. Wtedy będzie można ponownie spróbować zeskanować kod kreskowy.

Kierując aparat na kod kreskowy, w celu uzyskania najlepszego wyniku utrzymuj kod kreskowy w granicach nawiasów kwadratowych. Jeśli kod kreskowy zostanie zeskanowany pomyślnie, rezultat zostanie przetworzony, po czym nastąpi przejście do następnego kroku. Jeśli następny krok zawiera kolejne pole wejściowe z ustawionym preferowanym trybem wprowadzania Skanowanie, strona Aparat zostanie ponownie uruchomiona. Jeśli w następnym kroku nie występuje pole obsługujące skanowanie, strona Aparat nie zostanie zainicjowana.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]