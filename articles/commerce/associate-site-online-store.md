---
title: Kojarzenie witryny e-Commerce z kanałem online
description: W tym temacie opisano sposób powiązania witryny firmy Microsoft Dynamics 365 Commerce z co najmniej jednym sklepem internetowym.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b7c393ec2f716c7057a77d0f3c3c1a9f79ee8c68
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975375"
---
# <a name="associate-an-e-commerce-site-with-an-online-channel"></a>Kojarzenie witryny e-Commerce z kanałem online

[!include [banner](includes/banner.md)]


W tym temacie opisano sposób powiązania witryny firmy Microsoft Dynamics 365 Commerce z co najmniej jednym sklepem internetowym. 

Po zainicjowaniu obsługi handlu elektronicznego za pomocą portalu Microsoft Dynamics Lifecycle Services (usługi LCS) można przystąpić do utworzenia pierwszej witryny e-Commerce. W ramach początkowego tworzenia witryny skojarz witrynę z wcześniej utworzonym sklepem internetowym. Ten krok wiąże witrynę ze kanałem online i umożliwia wyświetlanie w witrynie hierarchii nawigacji, produktów, kategorii, cen, opcji wysyłki i wszystkich innych zdefiniowanych w sklepie internetowym.

Aby utworzyć nową witrynę i skojarzyć z nią sklep internetowy, w usługi LCS wybierz łącze do środowiska tworzenia witryn. Następnie na stronie dla środowiska tworzenia witryn wybierz opcję **Nowa witryna**. W oknie dialogowym **Nowa witryna** należy podać podstawowe informacje o witrynie. Aby zapoznać się z kompletnymi informacjami na temat, które należy podać, zawiera sekcja [Tworzenie nowej witryny e-Commerce](create-ecommerce-site.md).

Po utworzeniu witryny można sprawdzić, czy jest skojarzona ze swoim sklepem internetowym, wybierając kartę **produkty.** Powinien być widoczny asortyment produktów, które zostały przypisane do sklepu internetowego. Aby uzyskać dostęp do produktów według kategorii, można również skorzystać z pola rozwijanego znajdującego się w lewej górnej części strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
