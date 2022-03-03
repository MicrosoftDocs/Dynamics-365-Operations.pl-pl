---
title: Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego
description: W tym temacie opisano, jak ustawić limity ilości produktów w witrynach handlu elektronicznego typu business-to-business (B2B).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2c8adaad2afee3b735c69a501d7949a807f4e770
ms.sourcegitcommit: 68114cc54af88be9a3a1a368d5964876e68e8c60
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2022
ms.locfileid: "8323387"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a>Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego

[!include [banner](../../includes/banner.md)]

W tym temacie opisano, jak ustawić limity ilości produktów w witrynach handlu elektronicznego typu business-to-business (B2B).

Większość produktów ma jednostkę miary, która definiuje ich grupowanie. Grupowanie wpływa na sposób sprzedaży produktów. Niektóre produkty mogą mieć dodatkowe grupowanie według ilości. To grupowanie określa, czy produkty mogą być sprzedawane jako pojedyncze jednostki, czy jako wielokrotności oraz czy istnieje minimalny lub maksymalny limit ilości zamówienia, którego należy przestrzegać.

Funkcja ograniczania ilości zapewnia, że minimalne, maksymalne, wielokrotne i standardowe ilości skonfigurowane w Microsoft Dynamics 365 Commerce (w domyślnych ustawieniach zamówienia lub w ustawieniach witryny do tworzenia witryn handlowych) są stosowane do zamówień klientów składanych na witryna handlowa. Limity ilości produktów nie są obecnie obsługiwane w punkcie sprzedaży (POS) i centrach obsługi telefonicznej.

Wielu sprzedawców detalicznych oferuje możliwość składania zamówień klientów (zwanych również zamówieniami specjalnymi) w celu spełnienia różnych wymagań dotyczących produktów i spełnienia. Poniżej przedstawiono niektóre typowe scenariusze:

- Klient chce, aby produkty w określonych wariantach były sprzedawane w wielokrotności kilku.
- Klient chce odebrać produkty ze sklepu lub lokalizacji innej niż ta, w której kupił produkty. Jednak standardy pakowania w sklepach różnią się od standardów pakowania w przypadku dystrybucji sprzedaży internetowej.
- Klient chce kupić produkt w limitowanej edycji, w którym obowiązuje maksymalny limit ilościowy dla przedmiotów, które można kupić.

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a>Włącz funkcję domyślnych ustawień zamówień w Commerce headquarters

Aby można było ustawić limity ilości produktów, w Commerce headquarters musi być włączona funkcja domyślnych ustawień zamówienia.

Aby włączyć funkcję domyślnych ustawień kolejności, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.
1. Znajdź i wybierz opcję **Obsługuj witrynę i domyślne ustawienia zamówienia w zamówieniu klienta**.
1. W dolnej części prawego okienka wybierz opcję **Włącz teraz**. 

## <a name="define-quantity-settings"></a>Określ ustawienia ilości 

Na stronie **Ustawienia domyślne zamówień** można wprowadzić parametry zamówień.

Aby zdefiniować ustawienia ilości, należy wykonać następujące czynności. 

1. Wybierz Produkt **Retail i Commerce \> Produkty i kategorie \> Zwolnione produkty według kategorii**.
1. Wybór zwalnianego produktu.
1. W okienku akcji na karcie **Zarządzaj zapasami** w grupie **Ustawienia zamówienia** wybierz opcję **Ustawienia domyślne zamówień**. 
1. Na stronie **Ustawienia domyślne zamówień**, na skróconej karcie **Zamówienie sprzedaży**, w sekcji **Ilość sprzedaży** skonfiguruj ilości sprzedaży produktów:

    - **Wielokrotność** — ilość, w wielokrotnościach, w których produkt może być kupowany.
    - **Minimalna ilość zamówienia** — minimalna liczba produktów, które muszą zostać zakupione.
    - **Maksymalna ilość zamówienia** — maksymalna liczba produktów, które mogą zostać zakupione.
    - **Standardowa ilość zamówienia** — domyślna ilość wprowadzana automatycznie po wybraniu produktu.

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a>Włącz funkcję limitów ilości zamówienia B2B w Konstruktorze witryn Commerce

Aby włączyć funkcję limitów ilości zamówień B2B w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do **Ustawień witryny \> Rozszerzenia**
1. W obszarze **Włącz limity ilości zamówienia** wybierz z menu rozwijanego opcję **Włącz dla odbiorców B2B**. 

> [!NOTE] 
> Zaktualizowane ustawienia narzędzia do tworzenia witryn zaczną obowiązywać dopiero po zaktualizowaniu pliku app.settings.json. Aby uzyskać więcej informacji, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie witryny wykorzystywanej na potrzeby handlu elektronicznego B2B](set-up-b2b-site.md)

[Zarządzanie partnerami biznesowymi B2B przy użyciu hierarchii klientów](partners-customer-hierarchies.md)

[Zarządzanie użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B](manage-b2b-users.md)

[Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
