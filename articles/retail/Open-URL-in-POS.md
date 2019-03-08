---
title: Otwieranie adresu URL w aplikacji punktu sprzedaży
description: Ten temat zawiera omówienie ulepszeń wprowadzonych w produkcie i funkcji wyszukiwania klientów w rozwiązaniu Microsoft Dynamics 365 for Retail.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: b07406b4e218b45bdde87c4a579814fe0edbc286
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "327097"
---
# <a name="open-url-in-pos"></a>Otwieranie adresu URL w aplikacji punktu sprzedaży

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak można skonfigurować przycisk w punkcie sprzedaży (POS), aby otworzyć adres URL. Ta funkcja nie wymaga dostosowania kodu i może być skonfigurowana przez dowolną osobę, która nie ma roli dewelopera. Ta funkcja jest dostępna jako część Dynamics 365 for Finance and Operations wersji 8.1.3 (kompilacja 8.1.227.10014) lub nowszej. 

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

- Na komputerach z systemem Windows, zobacz [eksport lub import domyślnych skojarzeń aplikacji](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations), aby ustawić domyślne powiązania protokołu, jeśli konfigurujesz komputer przy użyciu Deployment Image Servicing and Management (DISM).
- Jeśli używasz MDM, takich jak Intune do zarządzania na komputerach z systemem Windows, zobacz [CSP zasad - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).
- Jeśli jesteś programistą i tworzysz niestandardową witrynę sieci Web, zobacz [uruchamianie aplikacji domyślnej dla identyfikatora URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).

## <a name="open-a-native-app-seamlessly"></a>Otwórz aplikację macierzystą bez problemów.

Windows, iOS i Android także umożliwiają łatwiejsze otwarcie aplikacji na podstawie powiązania protokołu aplikacji. Jeśli aplikacji nie jest jeszcze skonfigurowana do obsługi otwarcia w przeglądarce sieci web, może być konieczne ustawienie tej opcji.

- Dla systemu Windows, zobacz [Włączanie aplikacji dla witryny sieci Web przy użyciu programów obsługi URI](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).
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

1. W centrali przejdź do **Sprzedaż detaliczna \> Konfiguracja kanału \> Konfiguracja punktu sprzedaży \> Punkt sprzedaży \> Układy ekranu**.
2. Wybierz **Siatki przycisków \> Konstruktor**.
3. Utwórz nowy przycisk.
4. Wybierz Właściwości **przycisku**.
5. Wybierz akcję **Otwórz URL**.
6. Wprowadź URL, którego chcesz użyć.
7. Skonfiguruj, czy należy otworzyć adres URL w nowym oknie.
