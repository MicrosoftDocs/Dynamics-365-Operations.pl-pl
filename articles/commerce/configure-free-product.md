---
title: Konfiguracja produktu, który ma być nabywany bezpłatnie
description: W tym artykule opisano sposób konfigurowania produktu w celu jego bezpłatnego zakupu w aplikacji Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 88370085de047a5e0be773dde218770cfa242d14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280372"
---
# <a name="configure-a-product-to-be-purchased-for-free"></a>Konfiguracja produktu, który ma być nabywany bezpłatnie

[!include [banner](includes/banner.md)]


W tym artykule opisano sposób konfigurowania produktu w celu jego bezpłatnego zakupu w aplikacji Microsoft Dynamics 365 Commerce.

## <a name="configure-the-product"></a>Konfigurowanie produktu

Aby sprzedać produkt bezpłatnie w aplikacji Dynamics 365 Commerce, należy ustawić jego cenę na 0 (zero). Ponadto musisz skonfigurować ustawienie produktu **Cena zerowa jest prawidłowa**.

Aby skonfigurować ustawienie **Cena zerowa jest prawidłowa** w programie Commerce Headquarters, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Produkty i kategorie \> Zwolnione produkty według kategorii**.
1. Przejdź do produktu, który chcesz sprzedawać bezpłatnie. 
1. W sekcji **Commerce** na stronie produktu ustaw opcję **Cena zerowa jest prawidłowa** na **Tak**.

Na poniższej ilustracji pokazano przykład produktu, w którym dla opcji **Cena zerowa jest prawidłowa** ustawiono wartość **Tak**.

![Przykład produktu, w którym dla opcji Cena zerowa jest prawidłowa ustawiono wartość Tak.](./media/Zero-price.png)

## <a name="configure-the-online-stores-functionality-profile"></a>Konfigurowanie profilu funkcji sklepu internetowego

Aby można było przetwarzać transakcje bezpłatne, należy skonfigurować ustawienie **Zezwalaj na realizację transakcji bez płatności** profilu funkcji sklepu internetowego, tak aby transakcje bez płatności były dozwolone. Aby uzyskać informacje dotyczące sposobu tworzenia profilów funkcji, zobacz temat [Tworzenie profilu funkcji online](online-functionality-profile.md).

Aby skonfigurować ustawienie **Zezwalaj na realizację transakcji bez płatności** w programie Commerce Headquarters, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Ustawienia sklepu online**.
1. Na stronie profilu funkcji sklepu w obszarze **Realizacja transakcji** ustaw opcję **Zezwalaj na realizację transakcji bez płatności** na wartość **Tak**.

Na poniższej ilustracji pokazano przykład profilu sklepu internetowego, w którym ustawienie **Zezwalaj na realizację transakcji bez płatności** ma wartość **Tak**.

![Przykład profilu sklepu internetowego, w którym ustawienie Zezwalaj na realizację transakcji bez płatności ma wartość Tak.](./media/Zero-price-profile.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zarządzanie cenami sprzedaży detalicznej](price-management.md)

[Tworzenie profilu funkcji online](online-functionality-profile.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
