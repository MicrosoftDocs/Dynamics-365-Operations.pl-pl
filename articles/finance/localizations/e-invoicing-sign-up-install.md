---
title: Zarejestruj się i zainstaluj usługę fakturowania elektronicznego
description: Ten temat zawiera informacje dotyczące sposobu rejestracji i instalacji usługi fakturowania elektronicznego.
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4ab16652e4a50dd71a5d0b2b49b4dd79e327f7a8
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371768"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>Zarejestruj się i zainstaluj usługę fakturowania elektronicznego

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące sposobu rejestracji i instalacji usługi fakturowania elektronicznego. Ten proces składa się z czterech kroków. Kroki 1–3 są wymagane, a krok 4 jest opcjonalny.

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>Krok 1: Zarejestruj się w usłudze Regulatory Configuration Service

Usługa Regulatory Configuration Service (RCS) zapewnia konfigurację i środowisko projektowe używane do konfigurowania fakturowania elektronicznego. Zasoby takie jak środowiska i funkcje fakturowania elektronicznego są tworzone, utrzymywane i zarządzane w RCS. Gdy zasoby są gotowe, są publikowane w usłudze Fakturowanie elektroniczne.

Aby uzyskać więcej informacji na temat RCS, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md).

By zalogować się do RCS ze [strony Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>Krok 2: Zainstaluj dodatek dla mikrousług w Microsoft Dynamics Lifecycle Services

Usługa fakturowania elektronicznego to zestaw mikrousług hostowanych w centrum danych firmy Microsoft. Domyślnie klienci Dynamics 365 Finance i Dynamics 365 Supply Chain Management nie mają dostępu do usługi fakturowania elektronicznego. Musisz zainstalować ją jako dodatek w u usługach Microsoft Dynamics Lifecycle Services (LCS). Podczas instalowania tego dodatku środowisko zarządzania finansami lub Supply Chain Management jest rejestrowane w rejestrze aplikacji, które mogą łączyć się z usługą fakturowania elektronicznego.

Aby zakończyć ten krok, zobacz [Instalacja dodatku dla mikrousług w usłudze Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md).

### <a name="step-3-set-up-rcs"></a>Krok 3: Konfigurowanie RCS

Musisz skonfigurować integrację między RCS a usługą fakturowania elektronicznego. Należy także skonfigurować główne składniki.

Aby zakończyć ten krok, zobacz [temat Konfiguracja usługi Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md)

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>Krok 4: Wtyczka plug-in Microsoft Power Platform — odwołanie dla administratora

Niektóre scenariusze wymagają integracji Dataverse z zakresem Microsoft Power Platform.

Obecnie te ustawienia są obowiązkowe, jeśli w scenariuszach fakturowania elektronicznego będą używać rozwiązań elektronicznych do fakturowania elektronicznego. Jednak w przypadku scenariuszy fakturowania elektronicznego w Arabii Saudyjskiej jest to opcjonalne. Aby uzyskać więcej informacji, zobacz temat [Dostępność funkcji fakturowania elektronicznego według kraju lub regionu](e-invoicing-country-specific-availability.md).

Aby wykonać ten krok, zobacz odwołanie [do administratora dodatku Microsoft Power Platform](e-invoicing-power-platform-plug-in.md).
