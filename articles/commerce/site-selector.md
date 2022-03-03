---
title: Moduł selektora witryn
description: W tym temacie opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/11/2022
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
ms.openlocfilehash: 381163fdd6180a76def2e1bfb733f597b611c517
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109713"
---
# <a name="site-picker-module"></a>Moduł selektora witryn

[!include [banner](includes/banner.md)]

W tym temacie opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

Jeśli firma ma różne oddziały między rynkami, regionami i lokalizacjami, użytkownicy witryny muszą w prosty sposób przełączać się między witrynami i wybierać ich preferowaną witrynę w zakresie zakupów. Aby można było uwzględnić ten scenariusz, moduł wyboru witryn umożliwia przeglądanie użytkowników w wielu witrynach.

Moduł selektora witryn musi być skonfigurowany z listą witryn (rynków, regionów lub ustawień regionalnych), które mogą przeglądać użytkownicy witryny.

> [!NOTE]
> Moduł wyboru witryny do stron nadrzędnych jest dostępny w wydaniu Dynamics 365 Commerce 10.0.14.

Na poniższej ilustracji przedstawiono przykład modułu wyboru witryny, który jest proponowany w nagłówku strony witryny.

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
