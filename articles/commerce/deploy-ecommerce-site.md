---
title: Wdrażanie nowej dzierżawy e-commerce
description: W tym temacie opisano sposób wdrażania nowej dzierżawy e-Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS).
author: psimolin
manager: annbe
ms.date: 03/02/2020
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
ms.openlocfilehash: d5cf2804c44e81ad135a3248d38c228148b530cc
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096685"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Wdrażanie nowej dzierżawy e-commerce


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
    
Gdy e-Commerce jest inicjowany z usługi LCS, system Inicjuje obsługę kilku składników wymaganych w e-Commerce i kojarzy je ze środowiskiem. Po zakończeniu obsługi administracyjnej karta **e-Commerce** na stronie **Zarządzanie Retail** jest aktualizowana w celu uwzględnienia tej zmiany. Na stronie są wyświetlane najnowsze wdrożenia dostosowań oraz stan wszystkich innych trwających wdrożeń. Zawiera także łącza do witryny e-Commerce oraz narzędzia do zarządzania witryną e-Commerce, gdzie tworzone są witryny.

## <a name="access-site-builder"></a>Dostęp do konstruktora witryn

Aby uzyskać dostęp do konstruktora witryn, przejdź na kartę **e-Commerce** na stronie **Zarządzanie Retail** w usłudze LCS i wybierz **narzędzia zarządzania witryny e-Commerce**. Strona docelowa konstruktora witryn umożliwia wyświetlenie widoku na poziomie dzierżawy. Z poziomu tej strony można:

- Modyfikować ustawienia na poziomie dzierżawy.
- Przechodzić do dowolnych utworzonych witryn i mających uprawnienia do wyświetlania. 
- Uzyskać dostęp do funkcji ocen, takich jak moderowania i reportowania.
- Stworzyć nową witrynę. Aby uzyskać więcej informacji dotyczących sposobu tworzenia nowej witryny, zobacz [Tworzenie nowej witryny e-Commerce](create-ecommerce-site.md). 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Konfigurowanie kanału sklepu internetowego](online-stores.md)

[Kojarzenie witryny online z kanałem](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Przekaż adresy URL przekierowań luzem](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
