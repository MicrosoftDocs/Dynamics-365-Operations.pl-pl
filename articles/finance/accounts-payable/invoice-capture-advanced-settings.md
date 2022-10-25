---
title: Zaawansowane ustawienia rozwiązania Invoice Capture
description: Ten artykuł zawiera informacje o zaawansowanych ustawieniach w rozwiązaniu Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: a1e24b700d0f30fd90f2619dd6e6687736a86774
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691201"
---
# <a name="invoice-capture-solution-advanced-settings"></a>Zaawansowane ustawienia rozwiązania Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ten artykuł zawiera informacje o zaawansowanych ustawieniach w rozwiązaniu Invoice Capture.

## <a name="create-additional-connections-for-channels"></a>Tworzenie dodatkowych połączeń dla kanałów

Aby można było monitorować przychodzące faktury z różnych kanałów, należy utworzyć połączenia z magazynem poczty e-mail lub plików. Najpierw trzeba zarejestrować połączenia, aby przyznać dostęp do zautomatyzowanych przepływów używanych w rozwiązaniu.

Następujące typy połączeń są używane do importowania faktur:

- Office 365 Outlook
- Outlook.com
- OneDrive
- SharePoint

Kanał importowania faktur będzie korzystać z połączeń w kolejnych krokach konfiguracji. Aby użytkownicy mieli możliwość tworzenia kanału określonego połączenia, trzeba im przyznać rolę zabezpieczeń **Administrator** i muszą oni utworzyć połączenia.

Aby utworzyć połączenie z usługą Microsoft Dataverse, wykonaj poniższe kroki.

1. Przejdź do pozycji **Administrowanie systemem \> Rozwiązanie domyślne**.
2. Wybierz pozycję **Nowy**, a następnie **Odwołanie do połączenia**.
3. W polu **Nazwa wyświetlana** wprowadź nazwę.
4. Wybierz **Microsoft Dataverse** jako konektor.
5. Jeśli połączenie jest konfigurowane po raz pierwszy, wybierz opcję **Nowe połączenie**.
6. W wyświetlonym oknie dialogowym utwórz połączenie usługi Dataverse, a następnie wybierz przycisk **Utwórz**.
7. Wprowadź konto i hasło usługi Dataverse.
8. Po pomyślnym zakończeniu weryfikacji przejdź na stronę połączenia, wybierz opcję **Odśwież**, wybierz konto, a następnie wybierz przycisk **Utwórz**.

Aby utworzyć połączenie magazynu poczty e-mail lub plików, wykonaj następujące kroki.

1. Na stronie **Tworzenie połączenia** w polu **Typ połączenia** wybierz pozycję **Office 365 Outlook**.
2. W przypadku połączenia z pocztą e-mail można wybrać konektor **Outlook.com** lub **Office 365 Outlook**. Dla połączenia magazynu plików można wybrać jedną z opcji: **OneDrive** lub **SharePoint**.

Aby przejrzeć istniejące połączenia, przejdź do pozycji **Rozwiązanie domyślne \> Obiekty \> Odwołania do połączeń**. Użytkownik tworzący kanały powinien mieć co najmniej jedno połączenie usługi Dataverse oprócz określonych połączeń magazynu poczty e-mail lub plików. Twórca nowego kanału powinien być właścicielem połączenia.
