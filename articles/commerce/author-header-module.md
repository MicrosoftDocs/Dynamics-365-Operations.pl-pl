---
title: Moduł nagłówka
description: W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: e7dde3ba1ad375b309ae66cc6d31ccad85615e45
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686629"
---
# <a name="header-module"></a>Moduł nagłówka

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

W Dynamics 365 Commerce nagłówek strony składa się z wielu modułów, takich jak nagłówek, menu nawigacji, wyszukiwanie, transparent i pole zgody na pliki cookie. 

Moduł nagłówka zawiera logo witryny, łącza do hierarchii nawigacji, łącza do innych stron w witrynie, symbol koszyka, symbol Wishlist, opcje logowania i pasek wyszukiwania. Moduł nagłówka jest automatycznie optymalizowany dla urządzenia, na którym jest oglądana witryna (czyli inaczej urządzenie stacjonarne lub urządzenie przenośne). Na przykład na urządzeniu przenośnym pasek nawigacji jest zwinięty do przycisku **Menu** (który jest czasami nazywany *menu hamburgerowym*).

Poniższy obraz pokazuje przykład modułu nagłówka na stronie głównej.

![Przykład modułu nagłówka](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Moduł właściwości nagłówka

Moduł nagłówka obsługuje **Logo**, **Łącze logo** i właściwości **Łącza do Moje konto**. 

Właściwości **Logo** i **Łącze logo** są używane do definiowania logo na stronie. Aby uzyskać więcej informacji, zobacz [Dodawanie logo](add-logo.md). 

Za pomocą **Łącza do Moje konto** można zdefiniować strony kont, które właściciel witryny chce wyświetlić szybkie łącza w nagłówku.

## <a name="modules-that-are-available-in-a-header-module"></a>Moduły dostępne w module nagłówka

W module nagłówka mogą być używane następujące moduły:

- **Menu nawigacji** — menu nawigacji reprezentuje hierarchię nawigacji kanału i inne statyczne łącza nawigacji. Hierarchię nawigacji kanału można skonfigurować w Dynamics 365 Commerce. Menu nawigacji zawiera właściwość **Źródło nawigacji**, która służy do określania elementów menu nawigacji serwera sieci sprzedaży i statycznych elementów menu jako źródła. Jeśli statyczne elementy menu są określone jako źródło, można podać łącza względne do innych stron w witrynie. Skonfigurowane elementy zostaną wyświetlone jako nawigacja w nagłówkach. 

- **Pasek wyszukiwania** — moduł wyszukiwania umożliwia użytkownikom wprowadzanie kryteriów wyszukiwania, co pozwala na wyszukiwanie produktów. Adres URL domyślnej strony wyszukiwania oraz parametry kwerendy wyszukiwania muszą być podane w **Ustawienia witryny \> Rozszerzenia**. Moduł wyszukiwania ma właściwości pozwalające pominąć przycisk Wyszukaj lub etykieta w razie konieczności. Moduł wyszukiwania obsługuje także opcje automatycznego sugerowania, takie jak produkt, słowo kluczowe i wyniki wyszukiwania kategorii.

- **Ikona koszyka** — moduł ikony koszyka reprezentuje ikonę koszyka, w której w danym momencie jest wyświetlana liczba pozycji w koszyku. Aby uzyskać więcej informacji, zajrzyj do [Moduł ikony koszyka](cart-icon-module.md).

## <a name="create-a-header-module-for-a-page"></a>Utwórz moduł nagłówka dla strony

Aby utworzyć moduł nagłówka, należy wykonać następujące czynności.

1. Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.
1. W oknie dialogowym **Nowy fragment strony** wybierz moduł **Kontener**, wprowadź nazwę dla fragmentu strony, a następnie kliknij przycisk **OK**.
1. Wybierz gniazdo **Domyślny kontener**, a następnie w okienku właściwości po prawej stronie określ właściwość **Szerokość** na **Wypełnij kontener**.
1. W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduły **Baner promocyjny** i **Zgoda na pliki cookie** i wybierz przycisk **OK**.
1. W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. Wybierz gniazdo **Kontener**, a następnie w okienku właściwości po prawej stronie określ właściwość **Szerokość** na **Wypełnij kontener**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Nagłówek** i wybierz przycisk **OK**.
1. W gnieździe **Menu nawigacji** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Menu nawigacji** i wybierz przycisk **OK**.
1. W okienku właściwości modułu menu nawigacji skonfiguruj właściwości wedle potrzeby.
1. W gnieździe **Wyszukiwanie** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Wyszukiwanie** i wybierz przycisk **OK**.
1. W okienku właściwości modułu wyszukiwania skonfiguruj właściwości wedle potrzeby.
1. W gnieździe **Ikona koszyka** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Ikona koszyka** i wybierz przycisk **OK**.
1. W okienku właściwości modułu ikony koszyka skonfiguruj właściwości wedle potrzeby. Jeśli ikona koszyka ma wyświetlać podsumowanie koszyka (zwanego również „koszykiem mini”), zaznaczając opcję **Wyświetlanie koszyka mini**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.

1. W gnieździe **Nagłówek** w module **Strona domyślna** dodaj fragment stopki, który został utworzony.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
