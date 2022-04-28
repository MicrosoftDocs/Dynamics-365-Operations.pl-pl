---
title: Moduł selektora witryn
description: W tym temacie opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ad4d4d5f950d0631059d8f509e9e808a9106eb98
ms.sourcegitcommit: 4861ec2d3ae24cc9dd4ad3ac748fd05be3d80c70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/06/2022
ms.locfileid: "8551701"
---
# <a name="site-picker-module"></a>Moduł selektora witryn

[!include [banner](includes/banner.md)]

W tym temacie opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

Jeśli firma ma różne oddziały między rynkami, regionami i lokalizacjami, użytkownicy witryny muszą w prosty sposób przełączać się między witrynami i wybierać ich preferowaną witrynę w zakresie zakupów. Aby można było uwzględnić ten scenariusz, moduł wyboru witryn umożliwia przeglądanie użytkowników w wielu witrynach. Selektor witryn jest również zalecany w przypadku, gdy w witrynie sklepu internetowego zaimplementowano [funkcję wykrywania i przekierowania geograficznego](geo-detection-redirection.md), aby klienci mieli możliwość pominięcia preferencji witryny wskazanych przez nich za pomocą modułu [wyboru kraju/regionu](country-region-picker-module.md). 

Moduł selektora witryn musi być skonfigurowany z listą witryn (rynków, regionów lub ustawień regionalnych), które mogą przeglądać użytkownicy witryny. Na poniższej ilustracji przedstawiono przykład modułu wyboru witryny, który jest proponowany w nagłówku strony witryny.

![Przykład modułu wyboru witryn w nagłówku strony witryny.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Właściwości Modułu wyboru witryny

| Nazwa właściwości | Wartość                 | Opis |
|---------------|-----------------------|-------------|
| Nagłówek       | Tekst                  | Nagłówek modułu. |
| Opcje witryny  | Nazwa, obraz, adres URL      | Ta właściwość określa nazwę, łącze do strony głównej witryny oraz opcjonalny obraz, który ma być wyświetlany dla każdej witryny uwzględnionej w module. Obraz może być flagą lub pewną reprezentacją rynku, regionu lub ustawień regionalnych. |

## <a name="add-a-site-picker-module-to-a-page"></a>Dodawanie modułu wyboru witryny do nowej strony

Moduł selektora witryn można dodać do miejsca **selektora witryn** [modułu nagłówka](author-header-module.md). Po dodaniu modułu selektora witryn można zdefiniować nagłówek modułu i opcje witryny. Zazwyczaj moduł nagłówka znajduje się w fragmencie nagłówka, który można udostępnić na stronach portalu e-commerce dla witryny. W poniższym przykładzie moduł skonseratora witryny został dodany do gniazda **Selektor witryny** modułu nagłówka zawartego w fragmencie nagłówka o nazwie **HeaderContainer**.

![Przykład modułu selektora witryn we fragmencie nagłówka.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł nagłówka](author-header-module.md)

[Moduł szlaków nawigacyjnych](add-breadcrumb.md)

[Moduł menu nawigacji](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
