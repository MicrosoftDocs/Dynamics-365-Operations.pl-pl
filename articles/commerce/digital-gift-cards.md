---
title: Cyfrowe karty upominkowe w handlu elektronicznym
description: W tym temacie opisano, jak działają cyfrowe karty upominkowe w implementacji handlu elektronicznego Microsoft Dynamics 365 Commerce. Zawiera także przegląd ważnych kroków konfiguracji.
author: anupamar-ms
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 212f425dc3603f838ce030d9ed86f2e418bef29a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019940"
---
# <a name="e-commerce-digital-gift-cards"></a>Cyfrowe karty upominkowe w handlu elektronicznym

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano, jak działają cyfrowe karty upominkowe w implementacji handlu elektronicznego Microsoft Dynamics 365 Commerce. Zawiera także przegląd ważnych kroków konfiguracji.

W Dynamics 365 Commerce zakup cyfrowych kart podarunkowych przebiega tak samo, jak zakup innych produktów w systemie. Nie trzeba konfigurować żadnych dodatkowych modułów. Jeśli do koszyka dodano wiele kart podarunkowych, pozycje karty podarunkowej nie są agregowane w jednym wierszu sprzedaży. To zachowanie jest wymagane, ponieważ każdy wiersz sprzedaży jest fakturowany przy użyciu oddzielnego numeru karty upominkowej.

Zakup cyfrowych kart upominkowych jest obsługiwany w Dynamics 365 Commerce w wersji 10.0.16 lub nowszej.

Na poniższej ilustracji pokazano przykład strony szczegółów produktu (PDP) dotyczącej cyfrowych kart upominkowych w witrynie Fabrikam-e-commerce.

![Przykład cyfrowej karty upominkowej PDP w witrynie handlu elektronicznego firmy Fabrikam](./media/GiftcardPDP.PNG)

## <a name="turn-on-the-digital-gift-card-feature-in-commerce-headquarters"></a>Włączanie funkcji cyfrowych kart upominkowych w programie Commerce Headquarters

Aby przepływ zakupów cyfrowych bonów upominkowych działał w Dynamics 365 Commerce, funkcja **Kupowanie bonów upominkowych w handlu elektronicznym** musi być włączona w centrali Commerce. Funkcję można znaleźć w obszarze roboczym **Zarządzania funkcjami** w Commerce headquarters, jak pokazano na poniższej ilustracji.

![Obszar roboczy zarządzania funkcjami w Commerce headquarters](./media/Featureflag.PNG)

## <a name="configure-a-digital-gift-card-in-commerce-headquarters"></a>Skonfiguruj cyfrową kartę upominkową w siedzibie Commerce

Produkty z cyfrowymi kartami upominkowymi należy skonfigurować w centrali Commerce. Proces przypomina proces dla innych produktów. Jednak poniższe ważne kroki są specyficzne dla konfiguracji kart podarunkowych do zakupu. Aby uzyskać więcej informacji o tworzeniu i konfigurowaniu produktów, należy zapoznać się z tematem [Tworzenie nowego produktu w programie Commerce](create-new-product-commerce.md).

- Podczas konfigurowania produktów cyfrowych kart upominkowych w oknie dialogowym **Nowy produkt** ustaw w polu **Typ produktu** wartość **Usługa**. (Aby otworzyć okno dialogowe, przejdź do **Handel detaliczny i inny \> Produkty i kategorie \> Produkty według kategorii** i wybierz opcję **Nowy**.) Produkty typu **Usługa** nie są sprawdzane pod kątem dostępnych zapasów przed złożonem zamówieniem. Aby uzyskać więcej informacji, zobacz temat [Tworzenie nowego produktu](create-new-product-commerce.md#create-a-new-product).
- Na stronie **Parametry commerce**, na karcie **Księgowanie** w polu **Produkt karty upominkowej** należy ustawić **Cyfrową kartę upominkową**, tak jak pokazano na poniższej ilustracji. Jeśli produkt jest zewnętrzną kartą upominkową, zobacz [Pomoc techniczna dla zewnętrznych kart upominkowych](./dev-itpro/gift-card.md), aby uzyskać więcej informacji.

    ![Pole produktu karty upominkowej w programie Commerce Headquarters](./media/PostGiftcard.png)

- Jeśli karta upominkowa musi obsługiwać wiele wstępnie zdefiniowanych kwot (na przykład $25, $50, i $100), do skonfigurowania tych wstępnie zdefiniowanych kwot należy użyć wymiaru **Rozmiar**. Każda wstępnie zdefiniowana kwota będzie wariantem. Aby uzyskać więcej informacji, zobacz temat [Wymiary produktów](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json).
- Jeśli klienci muszą mieć możliwość określenia niestandardowej kwoty karty podarunkowej, najpierw skonfiguruj wariant, który pozwala na niestandardową kwotę. Następnie otwórz produkt ze strony **Kategorii Zwolnione produkty**, a następnie na skróconej karcie **Commerce** ustaw w polu **Klucz w cenie** wartość **Musi być wejściowa nowa cena**, tak jak pokazano na poniższej ilustracji. To ustawienie zapewnia klientom możliwość wprowadzenia ceny podczas przeglądania produktu na PDP.

    ![Klucz w polu ceny w Commerce headquarters](./media/KeyInPrice.png)

- Jako tryb dostawy cyfrowych kart upominkowych należy ustawić wartość **Elektroniczna**. Na stronie **Tryby dostawy** (**Handel detaliczny i inny \> Ustawienia kanału \> Metody dostawy**) wybierz **Elektroniczną** tryb dostawy w okienku listy, a następnie dodaj do siatki produkt cyfrowych kart upominkowych na skróconej karcie **Produkty**, tak jak pokazano na poniższej ilustracji. Aby uzyskać więcej informacji, zobacz temat [Ustaw metody dostawy](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

    ![Cyfrowe karty upominkowe na stronie Tryb dostawy w Commerce headquarters](./media/ElectronicMode.PNG)

- Upewnij się, że w programie Commerce Headquarters utworzono profil funkcji online i skojarzono go z jego sklepem internetowym. W profilu funkcji dla opcji **Agregacja produktów** ustaw wartość **Tak**. To ustawienie zapewnia agregację wszystkich pozycji z wyjątkiem kart podarunkowych. Aby uzyskać więcej informacji, zobacz temat [Tworzenie profilu funkcji online](online-functionality-profile.md).
- Aby zapewnić, że odbiorcy otrzymają wiadomość e-mail po zafaktureniu karty upominkowej, utwórz nowy typ powiadomienia pocztą e-mail na stronie **Profile powiadomień pocztą e-mail** i ustaw w polu **Typ powiadomienia pocztą e-mail** wartość **Wystaw kartę upominkową**. Więcej informacji jest dostępnych w artykule [Konfigurowanie profilu powiadomienia](email-notification-profiles.md).

## <a name="add-product-images-to-the-commerce-site-builder-media-library"></a>Dodawanie obrazów produktów do biblioteki multimediów konstruktora witryn Commerce

Musisz dodać obrazy produktów dla produktów cyfrowych kart upominkowych do biblioteki multimediów konstruktora witryn Commerce. Upewnij się, że nazwy plików obrazów kart podarunkowych są zgodne z konwencją nazewnictwa zdjęć produktów w Twojej witrynie. Aby uzyskać więcej informacji, zobacz [Przekazanie obrazów](dam-upload-images.md).

## <a name="configure-a-custom-amount-for-a-digital-gift-card-in-commerce-site-builder"></a>Skonfiguruj niestandardową kwotę dla cyfrowej karty upominkowej w narzędziu do tworzenia witryn Commerce

Jeśli cyfrowa karta podarunkowa jest skonfigurowana tak, aby zezwalała na niestandardową kwotę, to zachowanie musi być również włączone w [module pola zakupu](add-buy-box.md) używanym w PDP Twojej witryny. Moduł pola zakupu obsługuje konfigurację modułu, która pozwala na kwoty niestandardowe. Możesz także zdefiniować minimalne i maksymalne kwoty, które są dozwolone dla kwot niestandardowych.

Aby skonfigurować niestandardową kwotę dla cyfrowej karty upominkowej w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do modułu pola zakupu, który jest używany w PDP Twojej witryny. Ten moduł pola zakupu może być zaimplementowany we fragmencie, w szablonie lub na stronie.
1. Wybierz opcję **Edycja**.
1. W okienku właściwości po prawej stronie zaznacz pole wyboru **Zezwalaj na cenę niestandardową**.
1. Opcjonalnie: Aby zdefiniować kwoty minimalne i maksymalne dla kwot niestandardowych, wprowadź kwoty w polach **Cena minimalna** i **Cena maksymalna**.
1. Wybierz **Zakończ edycję** i następnie wybierz **Publikuj**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł pola zakupu](add-buy-box.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł koszyka](add-cart-module.md)

[Tworzenie nowego produktu w programie Commerce](create-new-product-commerce.md)

[Ustaw metody dostawy](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Wymiary produktu](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json)

[Konfigurowanie profilu powiadomienia](email-notification-profiles.md)

[Tworzenie profilu funkcji online](online-functionality-profile.md)

[Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]