---
title: Zwrot za zamówienie zwrotu został odrzucony
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku odrzucenia zwrotu za zamówienie zwrotu, ponieważ karta kredytowa używana do fakturowania różni się od karty użytej podczas oryginalnej autoryzacji płatności.
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
ms.openlocfilehash: 5961e77de1de5dc23454fc1a6e16f8c0b4e7cc6a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801562"
---
# <a name="refund-on-a-return-order-is-declined"></a>Zwrot za zamówienie zwrotu został odrzucony

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku odrzucenia zwrotu za zamówienie zwrotu, ponieważ karta kredytowa używana do fakturowania różni się od karty użytej podczas oryginalnej autoryzacji płatności.

## <a name="description"></a>opis

Zwrot jest odrzucany, jeśli karta kredytowa użyta do zafakturowana zamówienia zwrotu różni się od karty użytej podczas oryginalnej autoryzacji płatności. Zostanie wyświetlony następujący komunikat o błędzie: „Niektóre płatności mają błędny stan księgowania. Przed zafakturowaniem sprawdź ponownie stan wszystkich płatności.”

Szczegóły autoryzacji płatności będą zawierać następujący komunikat o błędzie: „Brama Adyen SendRequest () nie powiodła się ze statusem„ InternalServerError ”. 22144; Adyen zwróciła pustą odpowiedź. (22001);”

![Odrzucony zwrot pieniędzy z powodu błędu zamówienia zwrotu](media/refund-order-decline.jpg)

## <a name="resolution"></a>Rozdzielczość

### <a name="enable-blind-returns-in-adyen"></a>Włącz zwroty w ciemno w Adyen

Aby włączyć zwroty w ciemno, wykonaj czynności opisane w [Rozwiązywanie problemów z Dynamics 365 Payment Connector w przypadku problemów z Adyen](adyen-support.md), aby skontaktować się z zespołem pomocy technicznej Adyen i poprosić o włączenie na konta handlowego Ayden.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Łącznik płatności usługi Dynamics 365 dla Adyen](../dev-itpro/adyen-connector.md)

[Skonfiguruj łącznik płatności Adyen dla Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
