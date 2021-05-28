---
title: Strona wprowadzania karty kredytowej pokazuje błąd podczas realizacji zamówienia
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc, gdy sekcja Metoda płatności nie jest załadowana i wyświetlany jest komunikat o błędzie.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: ea9105481e6c5812565f0d3604906c905bcb5443
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018513"
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
