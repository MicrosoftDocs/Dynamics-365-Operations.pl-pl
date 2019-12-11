---
title: Wdrażanie nowej dzierżawy e-commerce
description: W tym temacie opisano sposób wdrażania nowej dzierżawy e-Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS).
author: psimolin
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c2632632b9b21dd3a88e9a4df0e65cfd28e579d2
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697458"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Wdrażanie nowej dzierżawy e-commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano sposób wdrażania nowej witryny e-Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS).

## <a name="overview"></a>Omówienie
    
Microsoft Dynamics Lifecycle Services (usługi LCS) to oparty na chmurze obszar roboczy, za pomocą którego partnerzy i klienci mogą zarządzać swoimi projektami i środowiskami, wyświetlać najnowsze informacje o produktach i funkcjach Microsoft Dynamics oraz tworzyć, śledzić i przeglądać zdarzenia pomocy technicznej. Funkcje zarządzania e-Commerce są zintegrowane z usługi LCS.

Aby dowiedzieć się więcej o usługi LCS, zobacz [Przewodnik użytkownika usługi Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Wprowadzenie

Aby można było zainicjować e-Commerce, należy zainicjować projekt, środowisko i Retail Cloud Scale Unit (RCSU). Aby wykonać inicjalizację w usługi LCS, trzeba mieć uprawnienia do roli Właściciel projektu lub Menedżer środowiska. Topologie środowiska produkcyjnego i piaskownicy są obsługiwane.

Aby uzyskać więcej informacji o środowiskach, należy zapoznać się z tematem [Planowanie środowiska](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). Aby uzyskać więcej informacji na temat dzienników RCSU, zobacz temat [Inicjowanie Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Inicjalizowanie e-Commerce

Ta procedura służy do inicjowania funkcji e-Commerce w istniejącym środowisku.

Przed rozpoczęciem należy upewnić się, że istnieją następujące wymagane informacje:

- RCSU, który będzie używany.
- Grupa zabezpieczeń Azure Active Directory Microsoft, która będzie używana dla administratorów systemu w e-Commerce.
- Grupa zabezpieczeń Azure Active Directory Microsoft, która będzie używana dla moderatorów ocen i recenzji.
- Domeny, które będą skojarzone ze środowiskiem.

Ponadto można zebrać następujące informacje opcjonalne:

- Azure AD informacje o relacji od firmy do konsumenta (B2C):

    - Nazwa dzierżawy.
    - Identyfikator klienta.
    - Niestandardowa domena logowania.
    - Odpowiedź URL.
    - Identyfikator zasad logowania i rejestracji.
    - Identyfikator zasad resetowania haseł.
    - Edytuj identyfikator zasad profilu.

[!NOTE]
Te informacje można dodać później za pośrednictwem zlecenia usługi.

Po zebraniu wymaganych informacji należy wykonać poniższe kroki w celu zainicjowania e-Commerce.

1. Zaloguj się w [LCS](https://lcs.dynamics.com).
1. Otwórz projekt zawierający środowisko, w którym chcesz zainicjować e-Commerce.
1. W sekcji **środowiska** wybierz środowisko.
1. W obszarze **Funkcje środowiska** wybierz łącze **zarządzanie detaliczne**.
1. Na karcie **e-Commerce** wybierz opcję **ustawienia**. Zostanie wyświetlone okno dialogowe, w którym należy wprowadzić informacje wymagane do zainicjowania obsługi administracyjnej.
1. Wprowadź wymagane informacje, a następnie przejdź do następnej strony.
1. Na następnej stronie wpisz wymagane informacje, a następnie prześlij formularz. Powrócisz na kartę **e-Commerce**, w której powinny być widoczne informacje o uruchomieniu inicjalizacji.
1. Aby wyświetlić stan inicjalizacji, należy **odświeżyć** lub wrócić na kartę **e-Commerce** później.
    
Gdy e-Commerce jest inicjowany z usługi LCS, system Inicjuje obsługę kilku składników wymaganych w e-Commerce i kojarzy je ze środowiskiem. Po zakończeniu obsługi administracyjnej karta **e-Commerce** na stronie **zarządzania detalicznego** jest aktualizowana w celu uwzględnienia tej zmiany. Na stronie są wyświetlane najnowsze wdrożenia dostosowań oraz stan wszystkich innych trwających wdrożeń. Zawiera także łącza do witryny e-Commerce oraz narzędzia do zarządzania oddziałem e-Commerce (narzędzie autorskie).

## <a name="access-the-authoring-environment"></a>Dostęp do środowiska autorskiego

Aby uzyskać dostęp do środowiska projektowego, przejdź do karty **e-Commerce** na stronie **Zarządzanie detalicznymi**. W tym miejscu znajdują się łącza do witryny e-Commerce oraz narzędzia do zarządzania oddziałem.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie sklepu internetowego](online-store-overview.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny online z kanałem](associate-site-online-store.md)

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Dodaj obsługę dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)
