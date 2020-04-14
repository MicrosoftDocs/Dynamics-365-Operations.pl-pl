---
title: Moduł nagłówka
description: W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 34e543e807ac8790597f522fe3b4f0266cf4ee56
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "3025692"
---
# <a name="header-module"></a>Moduł nagłówka


[!include [banner](includes/banner.md)]

W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

W Dynamics 365 Commerce nagłówek strony składa się z wielu modułów, takich jak nagłówek, menu nawigacji, wyszukiwanie, transparent i pole zgody na pliki cookie. 

Moduł nagłówka zawiera logo witryny, łącza do hierarchii nawigacji, łącza do innych stron w witrynie, symbol koszyka, symbol Wishlist, opcje logowania i pasek wyszukiwania. Moduł nagłówka jest automatycznie optymalizowany dla urządzenia, na którym jest oglądana witryna (czyli inaczej urządzenie stacjonarne lub urządzenie przenośne). Na przykład na urządzeniu przenośnym pasek nawigacji jest zwinięty do przycisku **Menu** (który jest czasami nazywany *menu hamburgerowym*).

## <a name="properties-of-a-header-module"></a>Moduł właściwości nagłówka

Moduł nagłówka obsługuje **Logo**, **Łącze logo** i właściwości **Łącza do Moje konto**. 

Właściwości **Logo** i **Łącze logo** są używane do definiowania logo na stronie. Aby uzyskać więcej informacji, zobacz [Dodawanie logo](add-logo.md). 

Za pomocą **Łącza do Moje konto** można zdefiniować strony kont, które właściciel witryny chce wyświetlić szybkie łącza w nagłówku.

## <a name="modules-that-are-available-in-a-header-module"></a>Moduły dostępne w module nagłówka

W module nagłówka mogą być używane następujące moduły:

- **Menu nawigacji** — menu nawigacji reprezentuje hierarchię nawigacji kanału i inne statyczne łącza nawigacji. Hierarchię nawigacji kanału można skonfigurować w Dynamics 365 Commerce. Menu nawigacji zawiera właściwość **Źródło nawigacji**, która służy do określania elementów menu nawigacji serwera sieci sprzedaży i statycznych elementów menu jako źródła. Jeśli statyczne elementy menu są określone jako źródło, można podać łącza względne do innych stron w witrynie. Skonfigurowane elementy zostaną wyświetlone jako nawigacja w nagłówkach. 
- **Pasek wyszukiwania** — moduł wyszukiwania umożliwia użytkownikom wprowadzanie kryteriów wyszukiwania, co pozwala na wyszukiwanie produktów. Adres URL domyślnej strony wyszukiwania oraz parametry kwerendy wyszukiwania muszą być podane w **Ustawienia witryny \> Rozszerzenia**. Moduł wyszukiwania ma właściwości pozwalające pominąć przycisk Wyszukaj lub etykieta w razie konieczności. Moduł wyszukiwania obsługuje także opcje automatycznego sugerowania, takie jak produkt, słowo kluczowe i wyniki wyszukiwania kategorii.

## <a name="create-a-header-module-for-a-page"></a>Utwórz moduł nagłówka dla strony

Aby utworzyć moduł nagłówka, należy wykonać następujące czynności.

1. Utwórz fragment o nazwie **Fragment nagłówka** i dodaj do niego moduł kontenera.
1. W okienku właściwości modułu kontenerów określ właściwość **Szerokość** na **Wypełnij kontener**.
1. Dodaj moduły zgody na transparent i plik cookie dotyczące awansowania do modułu kontenerów.
1. Dodaj kolejny moduł kontenera do fragmentu i ustaw wartosć **Szerokość** na **Wypełnij kontener**.
1. Dodaj moduł nagłówka do drugiego modułu kontenera.
1. Dodaj moduł **menu nawigacji** w gnieździe menu nawigacji modułu nagłówka. 
1. W okienku właściwości modułu menu nawigacji skonfiguruj właściwości modułu menu nawigacji.
1. W gnieździe **wyszukiwania** modułu nagłówka dodaj moduł wyszukiwania. 
1. W okienku właściwości modułu wyszukiwania skonfiguruj właściwości modułu wyszukiwania. 
1. Zapisz fragment strony, zakończ jego edycję, a następnie go opublikuj. 

Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.

1. W gnieździe **Grupa główna** strony domyślnej dodaj fragment nagłówka zawierający moduł nagłówka do nagłówka.
1. Zapisz szablon, zakończ jego edycję, a następnie go opublikuj.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
