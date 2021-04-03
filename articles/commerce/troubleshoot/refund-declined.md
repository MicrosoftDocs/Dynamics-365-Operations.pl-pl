---
title: Zwrot za zamówienie zwrotu został odrzucony
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku odrzucenia zwrotu za zamówienie zwrotu, ponieważ karta kredytowa używana do fakturowania różni się od karty użytej podczas oryginalnej autoryzacji płatności.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: e202c6b4b9e025d5af1cd5eb6235884aab6444e6
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585489"
---
# <a name="refund-on-a-return-order-is-declined"></a><span data-ttu-id="612a3-103">Zwrot za zamówienie zwrotu został odrzucony</span><span class="sxs-lookup"><span data-stu-id="612a3-103">Refund on a return order is declined</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="612a3-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku odrzucenia zwrotu za zamówienie zwrotu, ponieważ karta kredytowa używana do fakturowania różni się od karty użytej podczas oryginalnej autoryzacji płatności.</span><span class="sxs-lookup"><span data-stu-id="612a3-104">This topic provides troubleshooting guidance that can help when a refund on a return order is declined because the credit card that is used for invoicing differs from the card that was used during the original payment authorization.</span></span>

## <a name="description"></a><span data-ttu-id="612a3-105">opis</span><span class="sxs-lookup"><span data-stu-id="612a3-105">Description</span></span>

<span data-ttu-id="612a3-106">Zwrot jest odrzucany, jeśli karta kredytowa użyta do zafakturowana zamówienia zwrotu różni się od karty użytej podczas oryginalnej autoryzacji płatności.</span><span class="sxs-lookup"><span data-stu-id="612a3-106">A refund is declined when the credit card that is used to invoice a return order differs from the card that was used during the original payment authorization.</span></span> <span data-ttu-id="612a3-107">Zostanie wyświetlony następujący komunikat o błędzie: „Niektóre płatności mają błędny stan księgowania.</span><span class="sxs-lookup"><span data-stu-id="612a3-107">You receive the following error message: "Some payments are not in the correct status for posting.</span></span> <span data-ttu-id="612a3-108">Przed zafakturowaniem sprawdź ponownie stan wszystkich płatności.”</span><span class="sxs-lookup"><span data-stu-id="612a3-108">Please re-validate the status of all payments prior to invoicing."</span></span>

<span data-ttu-id="612a3-109">Szczegóły autoryzacji płatności będą zawierać następujący komunikat o błędzie: „Brama Adyen SendRequest () nie powiodła się ze statusem„ InternalServerError ”. 22144; Adyen zwróciła pustą odpowiedź. (22001);”</span><span class="sxs-lookup"><span data-stu-id="612a3-109">The payment authorization details will include the following error message: "Adyen gateway SendRequest() failed with status 'InternalServerError'.22144; Empty response returned from Adyen.(22001);"</span></span>

![Odrzucony zwrot pieniędzy z powodu błędu zamówienia zwrotu](media/refund-order-decline.jpg)

## <a name="resolution"></a><span data-ttu-id="612a3-111">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="612a3-111">Resolution</span></span>

### <a name="enable-blind-returns-in-adyen"></a><span data-ttu-id="612a3-112">Włącz zwroty w ciemno w Adyen</span><span class="sxs-lookup"><span data-stu-id="612a3-112">Enable blind returns in Adyen</span></span>

<span data-ttu-id="612a3-113">Aby włączyć zwroty w ciemno, wykonaj czynności opisane w [Rozwiązywanie problemów z Dynamics 365 Payment Connector w przypadku problemów z Adyen](adyen-support.md), aby skontaktować się z zespołem pomocy technicznej Adyen i poprosić o włączenie na konta handlowego Ayden.</span><span class="sxs-lookup"><span data-stu-id="612a3-113">To enable blind returns, follow the steps in [Troubleshoot Dynamics 365 Payment Connector for Adyen issues](adyen-support.md) to contact the Adyen support team and request that blind returns be enabled on your Adyen merchant account.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="612a3-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="612a3-114">Additional resources</span></span>

[<span data-ttu-id="612a3-115">Łącznik płatności usługi Dynamics 365 dla Adyen</span><span class="sxs-lookup"><span data-stu-id="612a3-115">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="612a3-116">Skonfiguruj łącznik płatności Adyen dla Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="612a3-116">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
