---
title: Zwrot za zamówienie zwrotu został odrzucony
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku odrzucenia zwrotu za zamówienie zwrotu, ponieważ karta kredytowa używana do fakturowania różni się od karty użytej podczas oryginalnej autoryzacji płatności.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: d8d1c40673d4b159a7b7bf00bf6011ba45f47edd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268240"
---
# <a name="refund-on-a-return-order-is-declined"></a>Zwrot za zamówienie zwrotu został odrzucony

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku odrzucenia zwrotu za zamówienie zwrotu, ponieważ karta kredytowa używana do fakturowania różni się od karty użytej podczas oryginalnej autoryzacji płatności.

## <a name="description"></a>opis

Zwrot jest odrzucany, jeśli karta kredytowa użyta do zafakturowana zamówienia zwrotu różni się od karty użytej podczas oryginalnej autoryzacji płatności. Zostanie wyświetlony następujący komunikat o błędzie: „Niektóre płatności mają błędny stan księgowania. Przed zafakturowaniem sprawdź ponownie stan wszystkich płatności.”

Szczegóły autoryzacji płatności będą zawierać następujący komunikat o błędzie: „Brama Adyen SendRequest () nie powiodła się ze statusem„ InternalServerError ”. 22144; Adyen zwróciła pustą odpowiedź. (22001);”

![Odrzucony zwrot pieniędzy z powodu błędu zamówienia zwrotu.](media/refund-order-decline.jpg)

## <a name="resolution"></a>Rozwiązanie

### <a name="enable-blind-returns-in-adyen"></a>Włącz zwroty w ciemno w Adyen

Aby włączyć zwroty w ciemno, wykonaj czynności opisane w [Rozwiązywanie problemów z Dynamics 365 Payment Connector w przypadku problemów z Adyen](adyen-support.md), aby skontaktować się z zespołem pomocy technicznej Adyen i poprosić o włączenie na konta handlowego Ayden.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Łącznik płatności usługi Dynamics 365 dla Adyen](../dev-itpro/adyen-connector.md)

[Skonfiguruj łącznik płatności Adyen dla Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
