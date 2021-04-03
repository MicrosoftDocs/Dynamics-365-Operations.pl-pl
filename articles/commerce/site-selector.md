---
title: Moduł wyboru witryny
description: W tym temacie opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: e24590d4a8f172809704aab0d761f6db0fb0e11b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234348"
---
# <a name="site-selector-module"></a>Moduł wyboru witryny

[!include [banner](includes/banner.md)]

W tym temacie opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

Jeśli firma ma różne oddziały między rynkami, regionami i lokalizacjami, użytkownicy witryny muszą w prosty sposób przełączać się między witrynami i wybierać ich preferowaną witrynę w zakresie zakupów. Aby można było uwzględnić ten scenariusz, moduł selektor witryn umożliwia przeglądanie użytkowników w wielu witrynach.

Dla modułu wyboru witryn należy skonfigurować listę witryn (rynków, regionów lub ustawień regionalnych), które użytkownicy witryny mogą przeglądać.

> [!NOTE]
> Moduł wyboru witryny do stron nadrzędnych jest dostępny w wydaniu Dynamics 365 Commerce 10.0.14.

Na poniższej ilustracji przedstawiono przykład modułu wyboru witryny, który jest proponowany w nagłówku strony witryny.

![Przykład modułu wyboru witryn w nagłówku strony witryny](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a>Właściwości Modułu wyboru witryny

| Nazwa właściwości | Wartość                 | opis |
|---------------|-----------------------|-------------|
| Nagłówek       | Tekst                  | Nagłówek modułu. |
| Opcje witryny  | Nazwa, obraz, adres URL      | Ta właściwość określa nazwę, łącze do strony głównej witryny oraz opcjonalny obraz, który ma być wyświetlany dla każdej witryny uwzględnionej w module. Obraz może być flagą lub pewną reprezentacją rynku, regionu lub ustawień regionalnych. |

## <a name="add-a-site-selector-module-to-a-page"></a>Dodawanie modułu wyboru witryny do nowej strony

Moduł selektor witryn można dodać do [modułu nagłówka](author-header-module.md) w ramach gniazda selektora witryn. Po dodaniu możesz zdefiniować nagłówek modułu i opcje witryny.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł nagłówka](author-header-module.md)

[Moduł szlaków nawigacyjnych](add-breadcrumb.md)

[Moduł menu nawigacji](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]