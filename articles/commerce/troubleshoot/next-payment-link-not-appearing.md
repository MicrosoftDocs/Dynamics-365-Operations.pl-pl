---
title: Zapisz dla mojej następnej opcji płatności nie jest wyświetlany
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy pole wyboru Zapisz dla mojej następnej płatności nie jest wyświetlane w obszarze Metoda płatności na stronie realizacji zamówienia w witrynie e-commerce.
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
ms.openlocfilehash: 4887cde3e4243ae7a4da6402782e69e780ae20331ed80df63ba1239ef5187e41
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769278"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>Opcja „Zapisz do następnej płatności” nie pojawia się

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy pole wyboru **Zapisz dla mojej następnej płatności** nie jest wyświetlane w obszarze **Metoda płatności na stronie realizacji zamówienia** w witrynie e-commerce.

## <a name="description"></a>opis

Pole wyboru **Zapisz dla mojej następnej płatności** nie jest widoczne w sekcji **Metoda płatności** na stronie realizacji zamówienia w witrynie e-commerce.

Na poniższej ilustracji pokazano przykład strony realizacji zamówienia, która zawiera pole wyboru **Zapisz dla następnej płatności**.

![Zapisz dla pola wyboru Następna płatność w module Płatność.](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Rozwiązanie

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Sprawdź, czy program Dynamics 365 Payment Connector dla Adyen jest poprawnie skonfigurowany w programie Commerce Headquarters

Aby sprawdzić, czy Dynamics 365 Payment Connector dla Adyen jest poprawnie skonfigurowany w centrali Commerce, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Commerce \> Kanały \> Sklepy internetowe**.
1. Wybierz sklep internetowy.
1. Na skróconej karcie **Konta płatności** upewnij się, że ustawienie **Zezwalaj na zapisywanie informacji o płatności w polu e-commerce** ma wartość **Prawda**.

![Zezwalaj na zapisywanie informacji o płatności w polu e-commerce w programie Commerce Headquarters.](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł płatności](../payment-module.md)

[Zapisywanie instrumentów płatniczych online za pomocą łącznika Adyen](../dev-itpro/adyen-connector-listPI.md)
