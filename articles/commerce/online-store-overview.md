---
title: Omówienie witryny handlu elektronicznego
description: Ten temat stanowi omówienie pomocy technicznej dotyczącej witryn handlu elektronicznego w usłudze Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 11/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 55c40029082e49c1fbc9d9d5e9361218e5ddc5a0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022479"
---
# <a name="e-commerce-site-overview"></a>Omówienie witryny handlu elektronicznego

[!include [banner](includes/banner.md)]

Ten temat stanowi omówienie pomocy technicznej dotyczącej witryn handlu elektronicznego w usłudze Microsoft Dynamics 365 Commerce. W witrynie dostępne są informacje o sposobach inicjowania sklepów e-commerce online i zarządzania nimi w Dynamics 365 Commerce. Zawiera też linki do dalszych informacji o sklepach internetowych i sposobie konfigurowania witryny handlu elektronicznego. Mimo że ten temat opisuje wiele podstawowych informacji, nie obejmuje wszystkich danych, które są wymagane do konfiguracji witryny produkcyjnej handlu elektronicznego. W dokumentacji Dynamics 365 Commerce są dostępne informacje o bardziej zaawansowanych zagadnieniach.

## <a name="online-store-channel"></a>Kanał sklepu internetowego

Aby można było skompilować witrynę w aplikacji Dynamics 365 Commerce, należy skonfigurować co najmniej jeden kanał sklepu internetowego. Więcej informacji jest dostępnych w artykule [Konfigurowanie kanału internetowego](channel-setup-online.md). 

W aplikacji Dynamics 365 Commerce używasz kanału sklepu internetowego w celu ustalenia produktów, cen, języków, metod płatności, trybów dostarczania, centrów realizacji i innych aspektów środowiska online, które powinny być dostępne dla klientów.

Aby rozpocząć pracę w aplikacji Dynamics 365 Commerce, wystarczy skonfigurować tylko jeden kanał sklepu internetowego. Jednak pojedyncza witryna handlu elektronicznego może zapewnić środowisko online dla wielu sklepów internetowych. Na przykład jeśli wiele sklepów internetowych skonfigurowano do obsługi różnych regionów geograficznych, pojedynczy zestaw stron handlu elektronicznego może służyć do zapewnienia unikatowych środowisk definiowanych przez poszczególne sklepy. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania witryny do obsługi wielu sklepów internetowych, zobacz [Kojarzenie witryny online z kanałem](associate-site-online-store.md).

Po skonfigurowaniu sklepu internetowego można go skojarzyć z witryną Dynamics 365 Commerce, która będzie służyć jako witryna sklepowa. Aby uzyskać więcej informacji o sklepach internetowych i sposobie ich konfigurowania, zobacz [Konfigurowanie sklepów internetowych](/dynamics365/unified-operations/retail/online-stores).

## <a name="deploy-a-new-e-commerce-tenant"></a>Wdrażanie nowej dzierżawy handlu elektronicznego

Podczas inicjowania witryny handlu elektronicznego wyświetlany jest monit o podanie nazwy domeny. Więcej informacji o domenach w Commerce znajduje się w artykułach [Konfigurowanie nazwy domeny](configure-your-domain-name.md) i [Domeny w Dynamics 365 Commerce](domains-commerce.md). Aby wdrożyć nową dzierżawę handlu elektronicznego przez używanie [Microsoft Dynamics Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide), wykonaj kroki w artykule [Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md). Po skonfigurowaniu dzierżawy handlu elektronicznego w LCS zostanie podanych link do konstruktora witryn Commerce. Możesz użyć konstruktora witryn Commerce do inicjalizacji i konfigurowania witryn handlu elektronicznego.

## <a name="initialize-your-e-commerce-site"></a>Inicjalizacja witryny handlu elektronicznego

Po uruchomieniu kreatora witryny Commerce w LCS, wyświetli się strona **Witryny**. Ta strona zawiera dwie wstępnie skonfigurowane witryny, **domyślną** i **fabrikam**, jak pokazano na przykładzie na poniższej ilustracji.

![Strona witryny w module konstruktora witryn Commerce](media/e-commerce-site-01.png)

Po wybraniu jednej z tych witryn wyświetli się monit o wybranie nazwy domeny, domyślnego kanału sklepu internetowego, obsługiwanego języka dla wybranego kanału i ścieżki. Jeśli jest używany tylko jeden kanał, można pozostawić ścieżkę pustą. Więcej kanałów sklepu internetowego lub języków można skonfigurować później w module konstruktora witryn Commerce. Każdy dodatkowy kanał lub język wymaga unikatowej ścieżki. Na przykład istnieją dwa kanały online, które są skojarzone z jedną witryną, a nazwa domeny witryny to `www.fabrikam.com`. W takim przypadku ścieżką dla jednego kanału może być wartość domyślna bez ścieżki (`https://www.fabrikam.com`), a drugim kanałem może być nowa ścieżka, taka jak **site2** z adresem URL `https://www.fabrikam.com/site2`. Na poniższej ilustracji znajduje się przykładowe okno dialogowe inicjalizacji witryny w module konstruktora witryn Commerce.

![Okno dialogowe inicjalizacji witryny w module konstruktora witryn Commerce](media/e-commerce-site-02.png)

Na stronie **Witryny** znajduje się przycisk **Nowa witryna**. Okno dialogowe wyświetlane po wybraniu tego przycisku przypomina okno dialogowe inicjalizacji witryny, ale służy do tworzenia nowej witryny. Nowe witryny są puste. Nie obejmują one tych samych domyślnych szablonów, fragmentów, stron i obrazów dostarczanych z witrynami **domyślnymi** i **fabrikam**. W razie konieczności można otworzyć bilet pomocy technicznej i zwrócić się o dodanie kopii domyślnej zawartości do nowej pustej witryny. Aby uzyskać więcej informacji, przejrzyj temat [Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md).

Po inicjacji nowej witryny wyświetli się **Strona główna** w module konstruktora witryn Commerce. Na tej stronie znajdują się linki do typowych akcji i treści związanych ze wskazówkami, jak to pokazano w przykładzie na poniższej ilustracji.

![Linki na stronie głównej modułu konstruktora witryn Commerce](media/e-commerce-site-03.png)

## <a name="modify-online-store-channels-or-add-online-store-channels-to-an-e-commerce-site"></a>Modyfikowanie kanałów sklepu internetowego lub dodawanie kanałów sklepów internetowych do witryny handlu elektronicznego

Po utworzeniu witryny handlu elektronicznego można zmienić kanał, z którym jest skojarzona, poprzez wykonanie kroków opisanych w artykule [Kojarzenie witryny handlu elektronicznego z kanałem online](associate-site-online-store.md). Przykład w poniższej ilustracji pokazuje, jak można zmienić numer jednostki operacyjnej kanału na stronie **Kanały** (**Ustawienia witryny \> Kanały**). Po zakończeniu wprowadzania zmian wybierz opcję **Zapisz i opublikuj**. W ten sposób masz pewność, że zmiana zostanie opublikowana.

![Strona kanały w module konstruktora witryn Commerce](media/e-commerce-site-04.png)

Aby dodać nowe kanały, należy wybrać opcję **Dodaj kanał**. Aby dodać nowe języki do kanału, wybierz kanał, a następnie wybierz opcję **Dodaj ustawienia regionalne** w wyświetlonym oknie dialogowym kanału. Aby w oknie dialogowym wyświetliły się ustawienia regionalne, należy wstępnie skonfigurować kanał sklepu internetowego w centrali Commerce.

![Okno dialogowe w module konstruktora witryn Commerce](media/e-commerce-site-05.png)

## <a name="set-up-an-azure-b2c-tenant"></a>Skonfiguruj nazwę dzierżawcy B2C Azure

Dynamics 365 Commerce korzysta z usługi Azure Active Directory (Azure AD) dla klientów indywidualnych (B2C) w zakresie poświadczeń i przepływów uwierzytelniania użytkowników. Informacje o konfigurowaniu dzierżawcy Azure B2C są dostępne w artykułach [Konfigurowanie dzierżawy B2C w module Commerce](set-up-b2c-tenant.md), [Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md) i [Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-b2c-tenants.md).

## <a name="overview-of-the-default-site-pages"></a>Omówienie domyślnych stron witryny

Witryny **domyślna** i **fabrikam** zawierają wstępnie skonfigurowane szablony, fragmenty i strony, aby ułatwić rozpoczęcie pracy. Aby uzyskać więcej informacji, zobacz następujące tematy:

- [Omówienie strony głównej](quick-tour-home-page.md)
- [Omówienie stron szczegółów produktów](quick-tour-pdp.md)
- [Omówienie stron koszyka i realizacji zamówienia](quick-tour-cart-checkout.md)
- [Omówienie stron zarządzania kontem](quick-tour-account-management.md)

## <a name="manage-site-settings"></a>Zarządzanie ustawieniami witryny

Aby uzyskać więcej informacji dotyczących zarządzania ustawieniami witryny, zobacz następujące tematy:

- [Zarządzanie użytkownikami i rolami e-Commerce](manage-ecommerce-users-roles.md)
- [Zagadnienia optymalizacji aparatu wyszukiwania (SEO) dla witryny](/search-engine-optimization-considerations.md)
- [Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md)
- [Wybór motywu witryny](select-site-theme.md)

## <a name="manage-site-content"></a>Zarządzanie zawartością witryny

Aby uzyskać więcej informacji dotyczących zarządzania zawartością witryny, zobacz następujące tematy:

- [Słownik terminów dotyczących modelu strony](page-elements-overview.md)
- [Dokumentowanie stanów i cyklów życia](document-states-overview.md)
- [Szablony i układy](templates-layouts-overview.md)
- [Praca z fragmentami](work-with-fragments.md)
- [Praca z modułami](work-with-modules.md)
- [Omówienie zarządzania cyfrowymi składnikami majątku](dam-overview.md)
- [Przegląd biblioteki modułów](starter-kit-overview.md)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md)

[Kojarzenie witryny online z kanałem](associate-site-online-store.md)

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Dodaj obsługę dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]