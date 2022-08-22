---
title: Zarejestruj się i zainstaluj usługę fakturowania elektronicznego
description: Ten artykuł zawiera informacje dotyczące sposobu rejestracji i instalacji usługi fakturowania elektronicznego.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 99f484e5ab8821c78fde776a9d3195dade2a09d5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283966"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>Zarejestruj się i zainstaluj usługę fakturowania elektronicznego

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje dotyczące sposobu rejestracji i instalacji usługi fakturowania elektronicznego. Ten proces składa się z czterech kroków. Kroki 1–3 są wymagane, a krok 4 jest opcjonalny.

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>Krok 1: Zarejestruj się w usłudze Regulatory Configuration Service

Usługa Regulatory Configuration Service (RCS) zapewnia konfigurację i środowisko projektowe używane do konfigurowania fakturowania elektronicznego. Zasoby takie jak środowiska i funkcje fakturowania elektronicznego są tworzone, utrzymywane i zarządzane w RCS. Gdy zasoby są gotowe, są publikowane w usłudze Fakturowanie elektroniczne.

Aby uzyskać więcej informacji na temat RCS, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md).

By zalogować się do RCS ze [strony Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>Krok 2: Zainstaluj dodatek dla mikrousług w Microsoft Dynamics Lifecycle Services

Usługa fakturowania elektronicznego to zestaw mikrousług hostowanych w centrum danych firmy Microsoft. Domyślnie klienci aplikacji Dynamics 365 Finance i Dynamics 365 Supply Chain Management nie mają dostępu do usługi fakturowania elektronicznego. Musisz zainstalować ją jako dodatek w u usługach Microsoft Dynamics Lifecycle Services (LCS). Podczas instalowania tego dodatku środowisko zarządzania finansami lub Supply Chain Management jest rejestrowane w rejestrze aplikacji, które mogą łączyć się z usługą fakturowania elektronicznego.

Aby zakończyć ten krok, zobacz [Instalacja dodatku dla mikrousług w usłudze Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md).

### <a name="step-3-set-up-rcs"></a>Krok 3: Konfigurowanie RCS

Musisz skonfigurować integrację między RCS a usługą fakturowania elektronicznego. Należy także skonfigurować główne składniki.

Aby zakończyć ten krok, zobacz [temat Konfiguracja usługi Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md)

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>Krok 4: Wtyczka plug-in Microsoft Power Platform — odwołanie dla administratora

Niektóre scenariusze wymagają integracji Dataverse z zakresem Microsoft Power Platform.

Obecnie te ustawienia są obowiązkowe, jeśli w scenariuszach fakturowania elektronicznego będą używać rozwiązań elektronicznych do fakturowania elektronicznego. Jednak w przypadku scenariuszy fakturowania elektronicznego w Arabii Saudyjskiej jest to opcjonalne. Aby uzyskać więcej informacji, zobacz temat [Dostępność funkcji fakturowania elektronicznego według kraju lub regionu](e-invoicing-country-specific-availability.md).

Aby wykonać ten krok, zobacz odwołanie [do administratora dodatku Microsoft Power Platform](e-invoicing-power-platform-plug-in.md).
