---
title: Moduł nagłówka
description: W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2707173eb4d5525437c22a2f236c7d5c588ea7c3
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780317"
---
# <a name="header-module"></a>Moduł nagłówka

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.

W systemie Dynamics 365 Commerce nagłówek strony jest konfigurowany jako fragment strony, który zawiera moduły nagłówek, banner promocyjny i zgoda na wykorzystanie pliku cookie. 

Moduł nagłówka zawiera logo witryny, łącza do hierarchii nawigacji, łącza do innych stron w witrynie, ikonę koszyka, symbol Wishlist, opcje logowania i pasek wyszukiwania. Moduł nagłówka jest automatycznie optymalizowany dla urządzenia, na którym jest oglądana witryna (czyli inaczej urządzenie stacjonarne lub urządzenie przenośne). Na przykład na urządzeniu przenośnym pasek nawigacji jest zwinięty do przycisku **Menu** (który jest czasami nazywany *menu hamburgerowym*).

Poniższy obraz pokazuje przykład modułu nagłówka na stronie głównej.

![Przykład modułu nagłówka.](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Moduł właściwości nagłówka

Moduł nagłówka obsługuje **Logo**, **Łącze logo** i właściwości **Łącza do Moje konto**. 

Właściwości **Logo** i **Łącze logo** są używane do definiowania logo na stronie. Aby uzyskać więcej informacji, zobacz [Dodawanie logo](add-logo.md). 

Za pomocą **Łącza do Moje konto** można zdefiniować strony kont, które właściciel witryny chce wyświetlić szybkie łącza w nagłówku.

## <a name="modules-that-are-available-within-a-header-module"></a>Moduły dostępne w module nagłówka

W module nagłówka mogą być używane następujące moduły:

- **Menu nawigacji** — menu nawigacji reprezentuje hierarchię nawigacji kanału i inne statyczne łącza nawigacji. Aby uzyskać więcej informacji, zobacz [Nawigacja modułu menu](nav-menu-module.md).

- **Pasek wyszukiwania** — moduł wyszukiwania umożliwia użytkownikom wprowadzanie kryteriów wyszukiwania, co pozwala na wyszukiwanie produktów. Adres URL domyślnej strony wyszukiwania oraz parametry kwerendy wyszukiwania muszą być podane w **Ustawienia witryny \> Rozszerzenia**. Moduł wyszukiwania ma właściwości pozwalające pominąć przycisk Wyszukaj lub etykieta w razie konieczności. Moduł wyszukiwania obsługuje także opcje automatycznego sugerowania, takie jak produkt, słowo kluczowe i wyniki wyszukiwania kategorii.

- **Ikona koszyka** — moduł ikony koszyka reprezentuje ikonę koszyka, w której w danym momencie jest wyświetlana liczba pozycji w koszyku. Aby uzyskać więcej informacji, zajrzyj do [Moduł ikony koszyka](cart-icon-module.md).

- **Wybór witryn** — moduł wyboru witryny umożliwia przeglądanie przez użytkowników różnych wstępnie zdefiniowanych witryn na podstawie rynku, regionów i ustawień regionalnych. Aby uzyskać więcej informacji, zajrzyj do [Moduł wyboru witryn](site-selector.md).

- **Wybór sklepów** — moduł wyboru sklepu może być uwzględniony w gnieździe wyboru sklepu w module nagłówka. Umożliwia on przeglądanie i znajdowanie pobliskich sklepów. Użytkownicy mogą również określić preferowany sklep. Ten sklep zostanie następnie wyświetlony w nagłówku. Gdy moduł Selector magazynu jest uwzględniony w module nagłówka, jego właściwość **Tryb** musi mieć ustawioną wartość **Znajdź sklepy**. Aby uzyskać więcej informacji, zajrzyj do [Moduł wyboru sklepów](store-selector.md).

> [!NOTE]
> - Obsługa korzystania z modułu ikon koszyka w modułach nagłówków jest dostępna w Dynamics 365 Commerce w wersji w wydaniu 10.0.11.
> - Obsługa korzystania z modułu wyboru witryny w modułach nagłówków jest dostępna w Dynamics 365 Commerce w wersji w wydaniu 10.0.14.
> - Obsługa korzystania z modułu wyboru sklepu w modułach nagłówków jest dostępna w Dynamics 365 Commerce w wersji w wydaniu 10.0.15.

## <a name="header-module-in-the-adventure-works-theme"></a>Moduł Nagłówek w motywie Adventure Works

W motywie firmy Adventure Works moduł nagłówka obsługuje właściwość **Logo mobilne**. Ta właściwość umożliwia określenie logo dla mobilnych rzutni. Właściwość **Logo mobilne** jest dostępna jako rozszerzenie definicji modułu.

> [!IMPORTANT]
> Kompozycja Adventure Works jest dostępna w Dynamics 365 Commerce w wersji 10.0.20.

## <a name="create-a-header-fragment-for-a-page"></a>Utwórz fragment nagłówka dla strony

Aby utworzyć fragment nagłówka, należy wykonać następujące czynności.

1. Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.
1. W oknie dialogowym **Wybierz fragment** wybierz moduł **Kontener**, wprowadź nazwę dla fragmentu, a następnie kliknij przycisk **OK**.
1. Wybierz gniazdo **Domyślny kontener**, a następnie w okienku właściwości po prawej stronie określ właściwość **Szerokość** na **Wypełnij ekran**.
1. W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduły **Baner promocyjny**, **Nagłówek** i **Zgoda na pliki cookie** i wybierz przycisk **OK**.
1. W okienku właściwości modułu **Banner promocyjny** wybierz opcję **Dodaj wiadomość**, a następnie wybierz opcję **Wiadomość**.
1. W oknie dialogowym **Wiadomość** dodaj tekst łącza oraz łącza do materiałów promocyjnych, a następnie kliknij przycisk **OK**.
1. W okienku właściwości modułu **Zgody na wykorzystanie plików cookie** dodaj i skonfiguruj tekst oraz łącze do strony opisującej politykę prywatności witryny.
1. W gnieździe **Menu nawigacji** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Menu nawigacji** i wybierz przycisk **OK**.
1. W okienku właściwości modułu menu nawigacji, w obszarze **Źródło menu nawigacji** wybierz opcję **Retail Server**.
1. W okienku właściwości modułu menu nawigacji, w obszarze **Elementy menu statycznego** wybierz opcję **Dodaj element menu**, a następnie wybierz pozycję **Element menu**. 
1. W oknie dialogowym **Elementu menu**, w obszarze **Tekst elementu menu** wprowadź wartość „kontakt”.
1. W oknie dialogowym **Element menu**, w obszarze **Cel łącza w elemencie menu** wybierz opcję **Dodaj łącze**.
1. W oknie dialogowym **Dodaj łącze** wybierz łącze do strony „Kontakt”, a następnie kliknij przycisk **OK**.  
1. W oknie dialogowym **Element menu** wybierz przycisk **OK**.
1. W gnieździe **Wyszukiwanie** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Wybierz moduły**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Wyszukaj** i wybierz przycisk **OK**.
1. W okienku właściwości modułu wyszukiwania skonfiguruj właściwości wedle potrzeby.
1. W gnieździe **Ikona koszyka** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Ikona koszyka** i wybierz przycisk **OK**.
1. W okienku właściwości modułu ikony koszyka skonfiguruj właściwości wedle potrzeby. Jeśli ikona koszyka ma wyświetlać podsumowanie koszyka (zwanego również „koszykiem mini”), zaznaczając opcję **Wyświetlanie koszyka mini**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.

1. W gnieździe **Nagłówek** w module **Strona domyślna** dodaj fragment stopki, który został utworzony.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł transparentu promocyjnego](add-alert.md)

[Moduł Menu nawigacji](nav-menu-module.md) 

[Zgoda na plik cookie](cookie-consent-module.md)

[Moduł stopki](author-footer-module.md)

[Moduł wyboru witryny](site-selector.md)

[Moduł wyboru sklepu](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
