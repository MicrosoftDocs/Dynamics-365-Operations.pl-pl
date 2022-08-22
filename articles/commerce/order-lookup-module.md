---
title: Moduł wyszukiwania zamówień
description: W tym artykule omówiono moduł wyszukiwania zamówień i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 8c60ed0c334bf09916dd633302c6d813ea6f16b6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281462"
---
# <a name="order-lookup-module"></a>Moduł wyszukiwania zamówień

[!include [banner](includes/banner.md)]

W tym artykule omówiono moduł wyszukiwania zamówień i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.

Moduł wyszukiwania zamówień umożliwia klientom używanie formularza do wyszukiwania zamówień, które składali w witrynie e-commerce. Jest on używany jako część funkcji [Włączanie wyszukiwania zamówień dla realizacji transakcji gościa](order-lookup-guest.md). Moduł wyszukiwania zamówień może służyć do wyszukiwania zamówień przesłanych za pośrednictwem witryny e-commerce, punktu sprzedaży w sklepie (POS) lub centrum obsługi. Formularz może pobierać zamówienia przesłane zarówno przez użytkowników gości, jak i przez zarejestrowanych użytkowników.

Na poniższej ilustracji pokazano przykład formularza renderowanego przez moduł wyszukiwania zamówień. Gdy odbiorcy wypełnią formularz i wybiorą opcję **Znajdź zamówienie**, nastąpi przekierowanie do strony szczegółów zamówienia.

![Formularz modułu wyszukiwania zamówień na stronie.](./media/OrderLookup_module.PNG)

## <a name="order-lookup-module-properties"></a>Właściwości modułu wyszukiwania zamówień

| Nazwa właściwości     | Wartość     | opis |
|-------------------|-----------|-------------|
| Nagłówek           | Tekst      | Nagłówek wyświetlany u góry formularza (na przykład „Znajdź zamówienie”). |
| Tekst sformatowany         | Tekst sformatowany | Opcjonalny tekst z uzasadnieniem wyświetlany pod nagłówkiem. |
| Typ stanu zamówienia | Tekst stały      | <p>Wybierz typ informacji o kliencie, które (oprócz identyfikatora potwierdzenia zamówienia) będą żądane w formularzu. Obecnie obsługiwane są następujące wartości:</p><ul><li><b>Adres e-mail</b> — formularz będzie zawierał pole, w którym odbiorcy mogą wprowadzić adres e-mail używany przez nich podczas zamawiania.</li><li><b>Brak</b> — formularz nie będzie żądał informacji oprócz identyfikatora potwierdzenia zamówienia.</li></ul> |

## <a name="add-an-order-lookup-module-to-a-page"></a>Dodawanie modułu wyszukiwania zamówień do strony

Moduł wyszukiwania zamówień można dodawać do treści dowolnej strony witryny e-commerce. Jeśli chcesz włączyć funkcję wyszukiwania zamówień dla realizacji zamówień gościa, pamiętaj o dodaniu jej do strony, która nie wymaga logowania użytkownika. Aby znaleźć ustawienie **Wymaga zalogowania?** strony w widoku drzewa konstruktora witryn rozwiązania Commerce, zaznacz miejsce **Strona domyślna (wymagana)** i przejrzyj dolną część prawego okienka.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Włączanie wyszukiwania zamówień dla realizacji transakcji gościa](order-lookup-guest.md)

[Przegląd biblioteki modułów](starter-kit-overview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
