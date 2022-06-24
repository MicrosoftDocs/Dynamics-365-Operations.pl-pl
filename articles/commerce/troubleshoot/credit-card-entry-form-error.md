---
title: Strona wprowadzania karty kredytowej pokazuje błąd podczas realizacji zamówienia
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc, gdy sekcja Metoda płatności nie jest załadowana i wyświetlany jest komunikat o błędzie.
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
ms.openlocfilehash: 6d1f7ba2d1a63430431af94ed4bed3222c85f14d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910450"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>Strona wprowadzania karty kredytowej pokazuje błąd podczas realizacji zamówienia

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc, gdy sekcja **Metoda płatności** nie jest załadowana i wyświetlany jest komunikat o błędzie.

## <a name="description"></a>opis

Po otwarciu strony realizacji zamówienia dla sklepu internetowego sekcja **Metoda płatności** nie jest załadowana i wyświetlany jest następujący komunikat o błędzie: „Wystąpił błąd. Spróbuj ponownie później”.

![Błąd Moduł płatności.](media/payment-module-error.jpg)

## <a name="resolution"></a>Rozwiązanie

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Oczekiwanie na wygaśnięcie pamięci podręcznej jednostki Commerce Scale Unit

Ustawienia usługi płatności na stronie realizacji zamówienia sklepu internetowego są buforowane w jednostce skalowania Commerce Scale Unit i mogą potrwać do 15 minut, aby pojawić się w witrynie e-commerce. Te ustawienia usługi płatności obejmują zmiany identyfikatora konta handlowca, klucza interfejsu API w chmurze oraz różne ustawienia konfiguracji związane z metodą płatności.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie kanału online](../channel-setup-online.md)
