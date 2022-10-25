---
title: Instalowanie rozwiązania Invoice Capture
description: Ten artykuł zawiera informacje dotyczące sposobu instalowania rozwiązania Invoice Capture i integrowania go z aplikacją Microsoft Dynamics 365 Finance.
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
ms.openlocfilehash: d853e347c833345f34b65760fd7ee35cbb38c9a3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691228"
---
# <a name="install-the-invoice-capture-solution"></a>Instalowanie rozwiązania Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Jeśli rozwiązanie zostało zainstalowane w prywatnej wersji zapoznawczej, należy odinstalować stare rozwiązanie przed kontynuowaniem.

## <a name="prerequisites"></a>Wymagania wstępne

Aby umożliwić zainstalowanie rozwiązania Invoice Capture należy najpierw spełnić następujące wymagania wstępne:

1. Zarejestruj aplikację i dodaj klucz tajny klienta do usługi Microsoft Azure Active Directory (Azure AD) w swojej subskrypcji Azure. Aby uzyskać więcej informacji, zobacz [Rejestrowanie aplikacji internetowej przy użyciu usługi AAD](../../dev-itpro/data-entities/services-home-page.md#register-a-web-application-with-aad).

    > [!NOTE]
    > Zanotuj wartości pól **Identyfikator aplikacji (klienta)**, **Klucz tajny klienta** i **Identyfikator dzierżawcy**, ponieważ będą potrzebne później.

2. Zarejestruj aplikację Azure w środowisku aplikacji Dynamics 365 Finance. Aby uzyskać więcej informacji, zobacz [Rejestrowanie aplikacji zewnętrznej](../../dev-itpro/data-entities/services-home-page.md#register-your-external-application).

## <a name="install-and-set-up-the-solution"></a>Instalowanie i konfigurowanie rozwiązania

Aby zainstalować rozwiązanie Invoice Capture, przejdź do witryny AppSource i wybierz link do wersji zapoznawczej [rozwiązania Dynamics 365 Invoice Capture](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics365-invoice-capture-preview?flightCodes=invoicecapture). Po zakończeniu instalacji zobaczysz rozwiązanie zainstalowane w wybranym środowisku w usłudze Power Apps.

Aby zakończyć konfigurację, należy wykonać następujące czynności.

1. Pobierz [rozwiązanie asystenta](https://github.com/InvoiceCapture/InstallationTools/releases/download/latest/msdyn_InvoiceCaptureIntallationTools.zip), aby skonfigurować następujące szczegóły:

    - Komunikacja między platformą Microsoft Power Platform i środowiskiem aplikacji Finance
    - Odwołanie do połączenia dla usługi Dataverse i programu Office 365 Outlook, które będzie używane przez kanał

2. W witrynie Power Apps przejdź do swojego środowiska i wybierz opcję **Importuj rozwiązanie**.
3. Wybierz przycisk **Przeglądaj**, wybierz pobrany pakiet rozwiązania asystenta, a następnie wybierz pozycję **Dalej**.
4. Wybierz pozycję **Następny**.
5. Przypisz istniejące połączenie lub utwórz nowe, wybierając pozycję **Nowe połączenie**.
6. Po pomyślnym zaimportowaniu pakietu otwórz obszar **Dynamics 365 Invoice Capture — narzędzia do instalacji**.
7. Uruchom przepływ w chmurze, aby skonfigurować połączenie między rozwiązaniem Invoice Capture na platformie Microsoft Power Platform i aplikacją Finance.
8. Wybierz przycisk **Uruchom** i określ następujące parametry:

    - **Adres URL aplikacji Dynamics 365 Finance** — adres URL środowiska aplikacji Finance, z którym chcesz się zintegrować.
    - **Identyfikator dzierżawcy** — identyfikator dzierżawcy w środowisku aplikacji Finance.
    - **Identyfikator klienta** — zarejestrowany identyfikator aplikacji platformy Azure.
    - **Klucz tajny klienta** — klucz tajny klienta, który został wygenerowany dla aplikacji platformy Azure.
