---
title: Tworzenie witryny handlu elektronicznego
description: W tym temacie opisano zadania związane z tworzeniem nowej witryny e-Commerce w Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fd87a51b73deae64867b0420c00db9fce7c79336
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697136"
---
# <a name="create-an-e-commerce-site"></a>Tworzenie witryny handlu elektronicznego

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano zadania związane z tworzeniem nowej witryny e-Commerce w Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Aby rozpocząć opracowywanie witryny e-Commerce, najpierw należy utworzyć nową witrynę w środowisku tworzenia witryn. Aby można było utworzyć nową witrynę, w Dynamics 365 Retail musi być utworzony co najmniej jeden sklep internetowy. 

## <a name="set-up-your-site"></a>Konfigurowanie witryny

Aby skonfigurować witrynę, wykonaj następujące czynności.

1. W usłudze Microsoft Lifecycle Services (usługi LCS) wybierz łącze do środowiska tworzenia witryn. 
1. Następnie na stronie głównej dla środowiska tworzenia witryn wybierz opcję **Nowa witryna**.
1. W oknie dialogowym **Nowa witryna** wprowadź następujące informacje.

| Pole                               | Opis |
|-------------------------------------|-------------|
| Nazwa witryny                           | Umożliwia wprowadzenie nazwy wyświetlanej, która powinna być używana w odniesieniu do danej witryny w środowisku tworzenia witryn. Ta nazwa jest widoczna tylko w środowisku autorskim i nie będzie wyświetlana klientom. |
| Grupa zabezpieczeń administratora witryny | Określ grupę zabezpieczeń Microsoft Azure Active Directory (Azure AD), która zarządza użytkownikami dysponującymi rolą administratora witryny w tej witrynie. |
| Kanał domyślny (numer jednostki operacyjnej) | Wybierz sklep internetowy, który będzie pełnić tę witrynę jako sklep sieci Web. Jeśli chcesz, aby witryna e-Commerce obsługiwała wiele sklepów internetowych, musisz skojarzyć te sklepy z serwisem w **Ustawieniach witryny** po skonfigurowaniu witryny. |
| Język domyślny                            | Umożliwia określenie domyślnego języka dla tego sklepu i rynku online. Sklep internetowy może obsługiwać wiele języków. Jeśli chcesz obsługiwać wiele języków dla tego sklepu internetowego lub innego sklepu internetowego, możesz skonfigurować tę obsługę w **Ustawieniach witryny** po skonfigurowaniu witryny.  |
| Domena                              | Wybierz nazwę domeny, która będzie służyć jako domena dla tego sklepu internetowego. Jeśli nie skonfigurowano żadnych domen w usłudze LCS, to pole można pozostawić puste. Po skonfigurowaniu domeny w usługi LCS, należy ją dodać do swojego sklepu internetowego w **Ustawieniach witryny**.  |
| Ścieżka                              | Jeśli witryna obsługuje więcej niż jeden język dla danej nazwy domeny, użyj pola ścieżki, aby utworzyć unikalny adres URL witryny dla tej kombinacji domeny i języka. Jeśli język określony w polu **Język domyślny** jest jedynym językiem, który będzie obsługiwany dla tej domeny, lub będzie używany domyślny język po zlokalizowaniu witryny w dodatkowych językach, zaleca się pozostawienie tego pola pustego. |


Po utworzeniu witryny można sprawdzić, czy jest skojarzona ze swoim sklepem internetowym, wybierając kartę **Produkty**. Powinien być widoczny asortyment produktów, które zostały przypisane do sklepu internetowego. Możesz także użyć menu rozwijanego w lewym górnym rogu strony, aby uzyskać dostęp do przydzielonych produktów według kategorii.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie sklepu internetowego](online-store-overview.md)

[Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md)

[Kojarzenie witryny online z kanałem](associate-site-online-store.md)

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Dodaj obsługę dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Przegląd strony głównej tworzenia](authoring-home-overview.md)

[Dodawanie nowej strony witryny](add-new-page.md)