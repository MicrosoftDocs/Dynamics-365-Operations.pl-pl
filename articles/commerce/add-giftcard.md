---
title: Moduł kart upominkowych
description: W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b7d28e041b8adc828a2447ab09a0c1d28cc2aec0
ms.sourcegitcommit: 69075e001d1fb4ef69282667052cd8d082273094
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022012"
---
# <a name="gift-card-module"></a>Moduł kart upominkowych

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduły kart upominkowych można używać w module realizacji transakcji w celu przyjmowania kart upominkowych, bardzo popularnej metody płatności w transakcjach handlu elektronicznego. Moduł kart upominkowych wspiera Dynamics 365, SVS i karty upominkowe Givex. Karty upominkowe SVS i Givex są realizowane przez dostawcę płatności Adyen. Aby uzyskać więcej informacji na temat obsługi zewnętrznych kart upominkowych, takich jak SVS i Givex, zajrzyj do [Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md).

> [!NOTE]
> Obsługa realizowania kart upominkowych SVS i Givex w procesie realizacji transakcji jest dostępna w wydaniu Dynamics 365 Commerce 10.0.11. 

Dostępne są dwa moduły karty upominkowej:

- **Karta upominkowa** — ten moduł może być używany na stronie realizacji transakcji, aby zrealizować kartę upominkową jako ofertę płatności. 
- **Sprawdzanie salda karty upominkowej** — ten moduł może być używany na dowolnej stronie w celu sprawdzenia salda na karcie upominkowej. Ten moduł jest dostępny w Commerce w wersji 10.0.14 i nowszej.

> [!NOTE]
> Obsługa modułu kontroli salda kart upominkowych jest dostępna w wydaniu Dynamics 365 Commerce 10.0.14.

Poniższy obraz pokazuje przykład modułu karty podarunkowej na stronie realizacji zamówienia.

![Przykład modułu na karty upominkowej](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Właściwości modułu

- **Pokaż dodatkowe pola** — ta właściwość określa pola, które mają być wyświetlane w przypadku kart upominkowych, oprócz numeru karty upominkowej, który jest zawsze domyślnie wyświetlany. Na przykład niektóre karty upominkowe umożliwiają wyświetlanie osobistego numeru identyfikacyjnego (PIN), a inne umożliwiają wyświetlanie numeru PIN i daty ważności. Można również ustawić tę właściwość na „Brak”, co spowoduje wyświetlenie numeru karty upominkowej bez dodatkowych pól.

Obsługiwane wartości:
-   PIN
-   Data ważności
-   Numer PIN i data ważności 
-   None

## <a name="site-settings-for-gift-card-modules"></a>Ustawienia witryny dla modułów kart upominkowych

W konstruktorze witryn Commerce w **Ustawienia witryny \> Rozszerzenia** istnieje ustawienie modułu kart upominkowych o nazwie **Obsługiwany typ karty upominkowej**. To ustawienie obsługuje trzy wartości:
- **Dynamics 365 — karta upominkowa** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365. To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.
- **Karty upominkowe SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych SVS i Givex. To ustawienie jest obsługiwane dla użytkowników anonimowych oraz zalogowanych w witrynie handlu elektronicznego.
- **Karty upominkowe Dynamics 365, SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365, SVS i Givex. To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.

> [!IMPORTANT]
> Te ustawienia są dostępne w wydaniu Dynamics 365 Commerce 10.0.11 i są wymagane tylko wtedy, gdy potrzebna jest pomoc techniczna dla kart upominkowych SVS i Givex. W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json. Aby uzyskać instrukcje dotyczące aktualizowania pliku appsettings.json, zajrzyj do [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="add-a-gift-card-module-to-a-page"></a>Dodawanie modułu kart upominkowych do strony

Aby uzyskać instrukcje dotyczące dodawania modułu kart upominkowych do strony realizacji transakcji i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł płatności](payment-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł opcji dostawy](delivery-options-module.md)

[Moduł szczegółów zamówienia](order-confirmation-module.md)

[Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md)

[Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md)
