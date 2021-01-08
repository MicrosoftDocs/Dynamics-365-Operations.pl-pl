---
title: Tworzenie witryny handlu elektronicznego
description: W tym temacie opisano kroki i informacje wymagane do utworzenia nowej witryny e-Commerce w konstruktorze witryn Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
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
ms.openlocfilehash: 7d552f29fd8f52b512a7c21b36b0a814cac50646
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517191"
---
# <a name="create-an-e-commerce-site"></a>Tworzenie witryny handlu elektronicznego

[!include [banner](includes/banner.md)]

W tym temacie opisano kroki i informacje wymagane do utworzenia nowej witryny e-Commerce w konstruktorze witryn Dynamics 365 Commerce.

Po nadaniu licencji na funkcje Dynamics 365 Commerce, funkcja konstruktora witryn zostanie wdrożona wraz z witryną startową, którą można wykorzystać jako podstawę dla własnego oddziału. Jeśli jednak użytkownik chce rozpocząć od zera lub chce stworzyć drugą witrynę, musi utworzyć nową witrynę w środowisku tworzenia witryn. 

## <a name="set-up-your-site"></a>Konfigurowanie witryny

Aby skonfigurować witrynę, wykonaj następujące czynności.

1. Otwórz środowisko budowania witryn. Łącze do kreatora witryn w usłudze Microsoft Lifecycle Services (LCS) można znaleźć na stronie Funkcje środowiska w Commerce.
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

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
