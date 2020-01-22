---
title: Kojarzenie witryny e-Commerce z kanałem online
description: W tym temacie opisano sposób powiązania witryny firmy Microsoft Dynamics 365 Commerce z co najmniej jednym sklepem internetowym.
author: stuharg
manager: AnnBe
ms.date: 10/31/2019
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
ms.author: bicyclingfool
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 62d3c168967bd680b3ded56e627730324f2a5ec6
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945589"
---
# <a name="associate-an-e-commerce-site-with-an-online-channel"></a>Kojarzenie witryny e-Commerce z kanałem online

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano sposób powiązania witryny firmy Microsoft Dynamics 365 Commerce z co najmniej jednym sklepem internetowym. 

Po zainicjowaniu obsługi handlu elektronicznego za pomocą portalu Microsoft Dynamics Lifecycle Services (usługi LCS) można przystąpić do utworzenia pierwszej witryny e-Commerce. W ramach początkowego tworzenia witryny skojarz witrynę z wcześniej utworzonym sklepem internetowym. Ten krok wiąże witrynę ze kanałem online i umożliwia wyświetlanie w witrynie hierarchii nawigacji, produktów, kategorii, cen, opcji wysyłki i wszystkich innych zdefiniowanych w sklepie internetowym.

Aby utworzyć nową witrynę i skojarzyć z nią sklep internetowy, w usługi LCS wybierz łącze do środowiska tworzenia witryn. Następnie na stronie dla środowiska tworzenia witryn wybierz opcję **Nowa witryna**. W oknie dialogowym **Nowa witryna** należy podać podstawowe informacje o witrynie. Aby zapoznać się z kompletnymi informacjami na temat, które należy podać, zawiera sekcja [Tworzenie nowej witryny e-Commerce](create-ecommerce-site.md).

Po utworzeniu witryny można sprawdzić, czy jest skojarzona ze swoim sklepem internetowym, wybierając kartę **produkty.** Powinien być widoczny asortyment produktów, które zostały przypisane do sklepu internetowego. Aby uzyskać dostęp do produktów według kategorii, można również skorzystać z pola rozwijanego znajdującego się w lewej górnej części strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
