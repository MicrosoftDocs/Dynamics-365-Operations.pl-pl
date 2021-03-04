---
title: Moduł wyboru sklepu
description: W tym temacie opisano moduł wyboru sklepu i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5400a2e743a78124dca4bf9be3ccaf7870ea8b7d
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665279"
---
# <a name="store-selector-module"></a>Moduł wyboru sklepu

[!include [banner](includes/banner.md)]

W tym temacie opisano moduł wyboru sklepu i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Za pomocą modułu wyboru sklepu można pobrać produkt z wybranego sklepu po zakupieniu online. W module Commerce 10.0.13 moduł wyboru zawiera także dodatkowe funkcje, które mogą zawierać stronę **Znajdź sklep**, która przedstawia sklepy w pobliżu.

Moduł wyboru sklepów umożliwia użytkownikom wprowadzenie lokalizacji (miasto, województwo, adres itd.) w celu wyszukania sklepów w promieniu wyszukiwania. Gdy moduł jest otwierany po raz pierwszy, system używa lokalizacji przeglądarki odbiorcy w celu znalezienia sklepów (jeśli wyrażono zgodę).

## <a name="store-selector-module-usage-in-e-commerce"></a>Użycie modułu wyboru sklepu w e-commerce

- Moduł wyboru sklepu może być używany na stronie Szczegóły produktu (PDP) w celu wybrania sklepu do pobrania.
- Moduł wyboru sklepu może być używany na stronie koszyka w celu wybrania sklepu do pobrania.
- Moduł wyboru sklepu może być używany na autonomicznej stronie, na której są wyświetlane wszystkie dostępne sklepy.

## <a name="bing-maps-integration"></a>Integracja z mapami Bing

Moduł wyboru sklepów jest zintegrowany z [interfejsami API usługi mapy Bing](https://docs.microsoft.com/bingmaps/rest-services/), co umożliwia korzystanie z funkcji automatycznego kodowania i autosugerowania usługi Bing. Klucz interfejsu API map usługi Bing jest wymagany i należy go dodać do strony udostępnione parametry Commerce headquarters. Interfejs API geokodowania służy do konwertowania lokalizacji na wartości szerokości i długości geograficznej. Integracja z interfejsem API automatycznego sugerowania jest używana do pokazywania sugestii wyszukiwania, gdy użytkownicy wprowadzają lokalizacje w polu wyszukiwania.

W przypadku interfejsu API REST z automatyczną sugestią musisz upewnić się, że poniższe adresy URL są dozwolone zgodnie z polityką bezpieczeństwa treści (CSP) Twojej witryny. Ta konfiguracja jest wykonywana w narzędziu do tworzenia witryn Commerce przez dodanie dozwolonych adresów URL do różnych dyrektyw CSP dla witryny (na przykład **img-src**). Aby uzyskać więcej informacji, zajrzyj do [zasad zabezpieczeń dotyczących zawartości](manage-csp.md). 

- Do dyrektywy **connect-src** dodaj **&#42;.bing.com**.
- Do dyrektywy **img-src**, dodaj **&#42;.virtualearth.net**.
- Do dyrektywy **script-src**, **dodaj &#42;.bing.com, &#42;.virtualearth.net**.
- Do dyrektywy **script style-src**, dodaj **&#42;.bing.com**.
 
## <a name="pickup-in-store-mode"></a>Tryb odbioru w sklepie

Moduł wyboru sklepów obsługuje tryb **Odbioru w sklepie**, w którym jest wyświetlana lista sklepów, w których produkt jest dostępny do pobrania. Pokazuje również godziny otwarcia i zapasy produktów dla każdego sklepu na liście. Moduł selektora sklepu wymaga kontekstu produktu, aby zapewnić dostępność produktu i umożliwić użytkownikowi dodanie produktu do koszyka, jeśli tryb dostawy produktu jest ustawiony na **odbiór** w wybranym sklepie. Aby uzyskać więcej informacji, zobacz [Ustawienia zapasów](inventory-settings.md). 

Moduł wyboru sklepu można dodać do modułu skrzynki zakupów na PDP, aby pokazać sklepy, w których produkt jest dostępny do odbioru. Można go również dodać do modułu koszyka. W tym przypadku moduł wyboru sklepów pokazuje opcje odbioru dla poszczególnych pozycji w koszyku. Moduł selektora sklepu można również dodać do innych stron lub modułów za pomocą rozszerzeń i dostosowań.

Aby ten scenariusz zadziałał, produkty należy skonfigurować tak, aby był używany tryb **odbioru** z dostawą. W przeciwnym razie moduł nie będzie wyświetlany na stronach produktów. Aby uzyskać więcej informacji dotyczące konfigurowania metody dostawy, należy zapoznać się z tematem [Ustaw metody dostawy](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Poniższy obraz pokazuje przykład modułu wyboru sklepu używanego w PDP.

![Przykład modułu selektora sklepu używanego na PDP](./media/BOPIS.PNG)

> [!NOTE]
> W wersji 10.0.16 i nowszych można włączyć nową funkcję, która umożliwia organizacji definiowanie wielu trybów odbioru opcji dostawy dla klientów.  Jeśli ta funkcja jest włączona, selektor sklepu i inne moduły handlu elektronicznego zostaną ulepszone, aby umożliwić kupującemu wybór spośród potencjalnie wielu opcji odbioru, jeśli są skonfigurowane.  Aby dowiedzieć się więcej o tej funkcji, zapoznaj się z [tą dokumentacją](https://docs.microsoft.com/dynamics365/commerce/multiple-pickup-modes). 

## <a name="find-stores-mode"></a>Tryb znajdowania sklepu

Moduł Selector sklepów obsługuje także tryb **Znajdź sklepy**. W tym trybie można utworzyć stronę lokalizacji sklepów, która pokazuje dostępne sklepy i ich informacje. W tym trybie moduł selektora sklepu działa bez kontekstu produktu i może być używany jako samodzielny moduł na dowolnej stronie serwisu. Ponadto, jeśli odpowiednie ustawienia są włączone dla modułu, użytkownicy mogą wybrać sklep jako ich preferowany sklep. Jeśli sklep jest wybrany jako preferowany sklep użytkownika, identyfikator sklepu jest zachowywany w pliku cookie przeglądarki. Dlatego użytkownik musi zaakceptować wiadomość o zgodzie na pliki cookie.

Na poniższej ilustracji przedstawiono przykład modułu wyboru sklepu, który jest używany razem z modułem mapy na stronie lokalizacje sklepu.

![Przykład modułu selektora sklepów i modułu mapy na stronie lokalizacji sklepów](./media/ecommerce-Storelocator.PNG)

## <a name="render-a-map"></a>Renderowanie mapy

Moduł selektora sklepów może być używany razem z modułem mapy do pokazywania lokalizacji sklepów na mapie. Aby uzyskać więcej informacji dotyczących modułu mapy, przejdź do [Moduł mapy](map-module.md)

## <a name="store-selector-module-properties"></a>Właściwości Modułu wyboru sklepu

| Nazwa właściwości | Wartość | opis |
|---------------|-------|-------------|
| Nagłówek | Tekst | Nagłówek modułu. |
| Tryb | **Znajdź sklepy** lub **Odbierz w sklepie** | Tryb **Znajdź sklepy** pokazuje dostępne sklepy. Tryb **Odbierz w sklepie** umożliwia użytkownikom wybranie sklepu do pobrania. |
| Styl | **Okno dialogowe** lub **Wbudowane** | Moduł może być renderowany w tekście lub w oknie dialogowym. |
| Ustaw jako preferowany sklep | **Prawda** lub **Fałsz** | Jeśli właściwość ta ma wartość **Prawda**, użytkownicy mogą ustawiać preferowany sklep. Ta funkcja wymaga, aby użytkownicy zaakceptowali wiadomość o zgodzie na pliki cookie. |
| Pokaż wszystkie sklepy | **Prawda** lub **Fałsz** | Jeśli właściwość ta ma wartość **Prawda**, użytkownicy mogą pomijać właściwości **Promień wyszukiwania** i przeglądać wszystkie sklepy. |
| Opcje automatycznego sugerowania: maks. wyniki | Identyfikator | Ta właściwość określa maksymalną liczbę sugerowanych wyników, które mogą być wyświetlane za pośrednictwem interfejsu API automatycznego sugerowania usługi Bing. |
| Promień wyszukiwania | Identyfikator | Właściwość określa promień wyszukiwania dla sklepów w milach. Jeśli nie określono żadnej wartości, używany jest domyślny promień wyszukiwania, 50 mil. |
| Warunki świadczenia usług | Adres URL |  Właściwość ta określa warunki URL usługi wymagane do korzystania z usługi map Bing. |

## <a name="add-a-store-selector-module-to-a-page"></a>Dodawanie modułu wyboru sklepu do nowej strony

W trybie **Odbioru w sklepie** moduł może być używany tylko na stronach PDP i koszyka. W okienku właściwości modułu należy określić tryb **Odbiór w sklepie**.

- Aby uzyskać informacje o tym, jak dodać moduł wyboru sklepu do modułu pole zakupy, zajrzyj [Moduł pola zakupu](add-buy-box.md). 
- Aby uzyskać informacje o tym, jak dodać moduł wyboru sklepu do modułu koszyka, zajrzyj [Moduł koszyka](add-cart-module.md)

Aby skonfigurować moduł selektora sklepu, aby wyświetlał dostępne sklepy dla strony lokalizacji sklepów, jak na ilustracji, która pojawia się wcześniej w tym temacie, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon marketingowy**, a następnie wybierz **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz szablon **Szablon marketingowy**. W sekcji **Nazwa strony** przejdź do **Lokalizacje sklepów**, a następnie wybierz przycisk **OK**.
1. Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener z 2 modułami** i wybierz przycisk **OK**.
1. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.
1. Ustawienie wartości **Konfiguracja kolumny portu widoku X-Small** na **100%**.
1. Ustawienie wartości **Konfiguracja kolumny portu widoku Small** na **100%**.
1. Ustawienie wartości **Konfiguracja kolumny portu widoku Medium** na **33% 67%**.
1. Ustawienie wartości **Konfiguracja kolumny portu widoku Large** na **33% 67%**.
1. W gnieździe **Kontener z 2 kolumnami** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Selektor sklepu** i wybierz przycisk **OK**.
1. W okienku właściwości modułu określ wartość **Tryb** jako **Znajdź sklepy**.
1. Umożliwia ustawienie wartości **Promień wyszukiwania** w milach.
1. Określ inne właściwości, takie jak **Ustaw jako preferowany sklep**, **Wyświetl wszystkie sklepy** i **Włącz automatyczną sugestię**, jeśli jest to wymagane.
1. W gnieździe **Kontener z 2 kolumnami** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Mapa** i wybierz przycisk **OK**.
1. W okienku właściwości modułu określ dowolne dodatkowe właściwości, które są wymagane.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
 
## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Krótki przewodnik PDP](quick-tour-pdp.md)

[Krótki przewodnik po koszyku i realizacji transakcji](quick-tour-cart-checkout.md)

[Ustaw metody dostawy](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Zarządzanie Mapami Bing dla swojej organizacji](dev-itpro/manage-bing-maps.md)

[Interfejsy API REST Map Bing](https://docs.microsoft.com/bingmaps/rest-services/)

[Moduł map](map-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]