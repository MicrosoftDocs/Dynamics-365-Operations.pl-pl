---
title: Moduł wyboru sklepu
description: W tym temacie opisano moduł wyboru sklepu i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.openlocfilehash: 460d05ca29d5b8da70a971a649d9edd786f7260d
ms.sourcegitcommit: 15c5ec742d648c5f3506d031a2ab6150dcbae348
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378215"
---
# <a name="store-selector-module"></a>Moduł wyboru sklepu

[!include [banner](includes/banner.md)]

W tym temacie opisano moduł wyboru sklepu i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł wyboru sklepu jest używany dla scenariusza odbiorcy „kupowanie w trybie online” (BOPIS). Wyświetla listę sklepów, w których produkt jest dostępny do odbioru, a także godziny przechowywania i zapasy produktów dla każdego sklepu.

Moduł wyboru sklepu wymaga kontekstu produktu i lokalizacji wyszukiwania, aby znaleźć sklepy. W przypadku braku lokalizacji wyszukiwania domyślna jest lokalizacja przeglądarki klienta, pod warunkiem, że klient wyrazi zgodę. Moduł ma pole wprowadzania, które pozwala klientowi wprowadzić lokalizację (kod pocztowy lub miasto i stan), aby znaleźć sklepy w pobliżu.

Moduł wyboru sklepu jest zintegrowany z aplikacją do geokodowania Bing Maps Geocoding (API) służy do konwersji lokalizacji na szerokość i długość geograficzną. Klucz interfejsu API map usługi Bing jest wymagany i należy go dodać do strony udostępnione parametry Commerce w Dynamics 365 Commerce.

Moduł wyboru sklepu można dodać do modułu pola zakupu na stronie szczegółów produktu (PDP), aby wyświetlić sklepy, w których produkt jest dostępny do odbioru. Można go również dodać do modułu koszyka. W przypadku dodania do modułu koszyka w module wyboru sklepów są wyświetlane opcje pobrania dla każdego towaru w wierszu koszyka. Ponadto, z kodowaniem niestandardowym, ten moduł można dodać do innych stron lub modułów za pomocą rozszerzeń i dostosowań.

Aby scenariusz BOPIS działał, w produktach należy skonfigurować tryb dostawy „odbiór klienta”. W przeciwnym razie moduł nie będzie wyświetlany na odpowiednich stronach. Aby uzyskać szczegółowe informacje dotyczące konfigurowania metody dostawy, należy zapoznać się z tematem [Ustaw metody dostawy](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Poniższy obraz pokazuje przykład modułu wyboru sklepu używanego w PDP.

![Przykład modułu wyboru sklepu](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a>Użycie modułu wyboru sklepu w e-commerce

- Moduł wyboru sklepu można wykorzystać na stronie szczegółów produktu (PDP), aby znaleźć pobliskie sklepy, w których produkt jest dostępny do odbioru.
- Moduł wyboru sklepu można wykorzystać na stronie koszyka, aby znaleźć pobliskie sklepy, w których produkt w koszyku jest dostępny do odbioru.

## <a name="store-selector-module-properties"></a>Właściwości Modułu wyboru sklepu

| Nazwa właściwości             | Wartość                 | opis |
|---------------------------|-----------------------|-------------|
| Promień wyszukiwania | Identyfikator | Określa promień wyszukiwania dla sklepów w milach. Jeśli nie określono żadnej wartości, używany jest domyślny promień wyszukiwania, 50 mil.|
|Warunki świadczenia usług | Adres URL    |  Dla usługi Bing Maps jest wymagane łącze URL Warunki świadczenia usługi. |

## <a name="add-a-store-selector-module-to-a-page"></a>Dodawanie modułu wyboru sklepu do nowej strony

Moduł wyboru sklepu wymaga kontekstu produktu, więc można go używać tylko w polu zakupu i module koszyka. Moduły wyboru sklepów nie działają poza tymi modułami.

- Aby uzyskać informacje o tym, jak dodać moduł wyboru sklepu do modułu pole zakupy, zajrzyj [Moduł pola zakupu](add-buy-box.md). 
- Aby uzyskać informacje o tym, jak dodać moduł wyboru sklepu do modułu koszyka, zajrzyj [Moduł koszyka](add-cart-module.md)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Krótki przewodnik PDP](quick-tour-pdp.md)

[Krótki przewodnik po Koszyku i realizacji transakcji](quick-tour-cart-checkout.md)

[Ustaw metody dostawy](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Zarządzanie mapami Bing dla organizacji](dev-itpro/manage-bing-maps.md)
