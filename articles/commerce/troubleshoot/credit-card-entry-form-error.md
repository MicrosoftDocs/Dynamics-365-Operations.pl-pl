---
title: Strona wprowadzania karty kredytowej pokazuje błąd podczas realizacji zamówienia
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc, gdy sekcja Metoda płatności nie jest załadowana i wyświetlany jest komunikat o błędzie.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d2c5f01d17df79c9b23fd513aaeb5c0605d657e9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801778"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>Strona wprowadzania karty kredytowej pokazuje błąd podczas realizacji zamówienia

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc, gdy sekcja **Metoda płatności** nie jest załadowana i wyświetlany jest komunikat o błędzie.

## <a name="description"></a>opis

Po otwarciu strony realizacji zamówienia dla sklepu internetowego sekcja **Metoda płatności** nie jest załadowana i wyświetlany jest następujący komunikat o błędzie: „Wystąpił błąd. Spróbuj ponownie później”.

![Błąd Moduł płatności](media/payment-module-error.jpg)

## <a name="resolution"></a>Rozdzielczość

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Oczekiwanie na wygaśnięcie pamięci podręcznej jednostki Commerce Scale Unit

Ustawienia usługi płatności na stronie realizacji zamówienia sklepu internetowego są buforowane w jednostce skalowania Commerce Scale Unit i mogą potrwać do 15 minut, aby pojawić się w witrynie e-commerce. Te ustawienia usługi płatności obejmują zmiany identyfikatora konta handlowca, klucza interfejsu API w chmurze oraz różne ustawienia konfiguracji związane z metodą płatności.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie kanału online](../channel-setup-online.md)
