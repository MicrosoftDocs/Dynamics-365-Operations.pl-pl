---
title: Otwieranie adresu URL w punkcie sprzedaży
description: Ten artykuł zawiera omówienie ulepszeń wprowadzonych w produkcie i funkcji wyszukiwania klientów w rozwiązaniu Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 529908df866c71ea84d90bbb5d46b23311ed74d1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853969"
---
# <a name="open-url-in-pos"></a>Otwieranie adresu URL w punkcie sprzedaży

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak można skonfigurować przycisk w punkcie sprzedaży (POS) Dynamics 365 Commerce, aby otworzyć adres URL. Ta funkcja nie wymaga dostosowania kodu i może być skonfigurowana przez dowolną osobę, która nie ma roli dewelopera. 

Ta funkcja umożliwia konfigurację przycisku w punkcie sprzedaży, otwieranie adresu URL przy użyciu projektanta siatki przycisków. Obecnie jest to obsługiwane w następujących konfiguracjach:

- Otwórz w nowym oknie.
- Otwórz w punkcie sprzedaży.
- Otwórz aplikację macierzystą.

## <a name="open-in-new-window"></a>Otwórz w nowym oknie

Ta konfiguracja określa, czy należy otworzyć adres URL w nowym oknie lub w ramach aplikacji. W przypadku skonfigurowania, aby otworzyć adres URL sieci web w aplikacji, panel nawigacji z boku i górny pasek punktu sprzedaży są widoczne i dostępne do interakcji z użytkownikiem. W przypadku konfiguracji otwierania w nowym oknie adres URL zostanie otwarty w nowym oknie aplikacji w Modern POS for Windows i na nowej karcie przeglądarki we wszystkich innych klientach punktu sprzedaży. Aby włączyć tę opcję, należy skonfigurować adres URL z zaznaczoną opcją **Otwórz w nowym oknie**.

## <a name="open-within-pos"></a>Otwórz w punkcie sprzedaży.

Otwieranie adresu URL sieci web w punkcie sprzedaży jest obecnie obsługiwane tylko w systemie Windows Modern POS. Trwa opracowywanie tej funkcji dla innych klientów; będzie dostępna później. Aby włączyć tę opcję, należy skonfigurować adres URL z niezaznaczoną opcją **Otwórz w nowym oknie**.

## <a name="open-a-native-app"></a>Otwórz aplikację macierzystą.

Ta funkcja umożliwia określenie URL innych niż sieci web, aby otworzyć aplikację macierzystą. Na przykład można określić protokoły, takie jak MailTo, SIP, IM lub MSTEAMS, które następnie są obsługiwane przez odpowiednie aplikacje natywne na urządzeniu hostującym. Aby włączyć tę opcję, należy skonfigurować adres URL z zaznaczoną opcją **Otwórz w nowym oknie**.

- Na komputerach z systemem Windows, zobacz [eksport lub import domyślnych skojarzeń aplikacji](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations), aby ustawić domyślne powiązania protokołu, jeśli konfigurujesz komputer przy użyciu Deployment Image Servicing and Management (DISM).
- Jeśli używasz MDM, takich jak Intune do zarządzania na komputerach z systemem Windows, zobacz [CSP zasad - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults).
- Jeśli jesteś programistą i tworzysz niestandardową witrynę sieci Web, zobacz [uruchamianie aplikacji domyślnej dla identyfikatora URI](/windows/uwp/launch-resume/launch-default-app).

## <a name="open-a-native-app-seamlessly"></a>Otwórz aplikację macierzystą bez problemów.

Windows, iOS i Android także umożliwiają łatwiejsze otwarcie aplikacji na podstawie powiązania protokołu aplikacji. Jeśli aplikacji nie jest jeszcze skonfigurowana do obsługi otwarcia w przeglądarce sieci web, może być konieczne ustawienie tej opcji.

- Dla systemu Windows, zobacz [Włączanie aplikacji dla witryny sieci Web przy użyciu programów obsługi URI](/windows/uwp/launch-resume/web-to-app-linking).
- W przypadku iOS zobacz [uniwersalne łącza dla deweloperów](https://developer.apple.com/ios/universal-links/).
- W przypadku systemu Android zobacz [obsługa łączy aplikacji Android](https://developer.android.com/training/app-links/).

| Klient                | Otwórz w nowym oknie | Otwórz aplikację macierzystą | Otwórz w punkcie sprzedaży. | Szczegóły                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| Nowoczesny punkt sprzedaży w Windows | ✓\*                | ✓               | ✓              | \* Otwiera w nowym oknie nowoczesnego punktu sprzedaży |
| Cloud POS             | ✓\*                | ✓               | X              | \* Otwiera się na nowej karcie przeglądarki        |
| Nowoczesny punkt sprzedaży w iOS     | ✓\*                | ✓               | X              | \* Otwiera się na nowej karcie przeglądarki        |
| Modern POS w systemie Android | ✓\*                | ✓               | X              | \* Otwiera się na nowej karcie przeglądarki        |

## <a name="before-you-begin"></a>Przed rozpoczęciem

Przed rozpoczęciem zobacz jak skonfigurować [układy ekranu dla punktu sprzedaży (POS)](pos-screen-layouts.md).

## <a name="open-url-in-pos"></a>Otwieranie adresu URL w aplikacji punktu sprzedaży

Aby skonfigurować adres URL, który można otworzyć w punkcie sprzedaży, wykonaj następujące kroki.

1. W centrali przejdź do **Sprzedaż detaliczna i inna \> Konfiguracja kanału \> Konfiguracja punktu sprzedaży \> Punkt sprzedaży \> Układy ekranu**.
2. Wybierz **Siatki przycisków \> Konstruktor**.
3. Utwórz nowy przycisk.
4. Wybierz Właściwości **przycisku**.
5. Wybierz akcję **Otwórz URL**.
6. Wprowadź URL, którego chcesz użyć.
7. Skonfiguruj, czy należy otworzyć adres URL w nowym oknie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
