---
title: Rozwiązywanie problemów z Dynamics 365 Payment Connector w przypadku problemów z Adyen
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w uzyskania pomocy technicznej w przypadku problemów z łącznikiem płatności Microsoft Dynamics 365 dla Adyen.
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
ms.openlocfilehash: c779997d530d60f945bee19ee09bdabbff121fa6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801826"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a><span data-ttu-id="ebc7c-103">Rozwiązywanie problemów z Dynamics 365 Payment Connector w przypadku problemów z Adyen</span><span class="sxs-lookup"><span data-stu-id="ebc7c-103">Troubleshoot Dynamics 365 Payment Connector for Adyen issues</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ebc7c-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w uzyskania pomocy technicznej w przypadku problemów z łącznikiem płatności Microsoft Dynamics 365 dla Adyen.</span><span class="sxs-lookup"><span data-stu-id="ebc7c-104">This topic provides troubleshooting guidance that can help you get support when you have issues with the Microsoft Dynamics 365 Payment Connector for Adyen.</span></span>

## <a name="description"></a><span data-ttu-id="ebc7c-105">opis</span><span class="sxs-lookup"><span data-stu-id="ebc7c-105">Description</span></span>

<span data-ttu-id="ebc7c-106">Masz problemy z łącznikiem płatności Dynamics 365 dla Adyen w następujących obszarach, a musisz uzyskać pomoc od zespołu Adyen:</span><span class="sxs-lookup"><span data-stu-id="ebc7c-106">You have issues with the Dynamics 365 Payment Connector for Adyen in the following areas, and you require support from the Adyen team:</span></span>

- <span data-ttu-id="ebc7c-107">Konfiguracja punktu sprzedaży (POS), nowoczesnego punktu sprzedaży (MPOS), centrum obsługi lub Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ebc7c-107">Configuration of Point of sale (POS), Modern point of sale (MPOS), call center, or Dynamics 365 Commerce</span></span>
- <span data-ttu-id="ebc7c-108">Numer odwołania dostawcy usług płatności Adyen (NA PRZYKŁAD: jeśli użytkownik ma pytania dotyczące odmów, w tym ręcznego wprowadzania klawisza \[MKE\])</span><span class="sxs-lookup"><span data-stu-id="ebc7c-108">The Adyen payment service provider (PSP) reference number (for example, if you have questions about refusals, including manual key entry \[MKE\] refusals)</span></span>
- <span data-ttu-id="ebc7c-109">Wszystko, co nie działa w środowisku handlowym testowym lub na żywo</span><span class="sxs-lookup"><span data-stu-id="ebc7c-109">Anything that isn't working in test or live merchant environments</span></span>

## <a name="resolution"></a><span data-ttu-id="ebc7c-110">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="ebc7c-110">Resolution</span></span>

<span data-ttu-id="ebc7c-111">Użyj poniższego szablonu wiadomości e-mail, aby rozpocząć proces pomocy technicznej z zespołem Adyen.</span><span class="sxs-lookup"><span data-stu-id="ebc7c-111">Use the following email template to start the support process with the Adyen team.</span></span> <span data-ttu-id="ebc7c-112">Aby przyspieszyć rozwiązywanie problemów, upewnij się, że wiadomość e-mail zawiera wszystkie wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="ebc7c-112">To expedite troubleshooting, make sure that the email contains all the required details.</span></span>

| <span data-ttu-id="ebc7c-113">Pole</span><span class="sxs-lookup"><span data-stu-id="ebc7c-113">Field</span></span>        | <span data-ttu-id="ebc7c-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="ebc7c-114">Value</span></span> |
|--------------|-------|
| <span data-ttu-id="ebc7c-115">do</span><span class="sxs-lookup"><span data-stu-id="ebc7c-115">To</span></span>           | `support@adyen.com` |
| <span data-ttu-id="ebc7c-116">DW</span><span class="sxs-lookup"><span data-stu-id="ebc7c-116">Cc</span></span>           | |
| <span data-ttu-id="ebc7c-117">Wiersz tematu</span><span class="sxs-lookup"><span data-stu-id="ebc7c-117">Subject line</span></span> | <span data-ttu-id="ebc7c-118">Żądanie pomocy technicznej Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="ebc7c-118">Microsoft Dynamics Support Request</span></span> |
| <span data-ttu-id="ebc7c-119">Treść</span><span class="sxs-lookup"><span data-stu-id="ebc7c-119">Body</span></span>         | <p><span data-ttu-id="ebc7c-120">Dzień dobry przedstawicielu pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="ebc7c-120">Hi Support,</span></span></p><p><span data-ttu-id="ebc7c-121">Proszę podać pomoc techniczną dla następującego problemu:</span><span class="sxs-lookup"><span data-stu-id="ebc7c-121">Please provide support for the following issue:</span></span></p><ul><li><span data-ttu-id="ebc7c-122">Konto handlowca</span><span class="sxs-lookup"><span data-stu-id="ebc7c-122">Merchant account</span></span></li><li><span data-ttu-id="ebc7c-123">Środowisko (Test/Prod)</span><span class="sxs-lookup"><span data-stu-id="ebc7c-123">Environment (Test/Prod)</span></span></li><li><span data-ttu-id="ebc7c-124">Kanał sprzedaży (POS/call center/Commerce handel elektroniczny)</span><span class="sxs-lookup"><span data-stu-id="ebc7c-124">Channel (POS/call center/Commerce e-commerce)</span></span></li><li><span data-ttu-id="ebc7c-125">Numer referencyjny PSP, jeśli sprawa dotyczyła konkretnej transakcji (Numer referencyjny PSP można znaleźć na pokwitowaniu, w strefie klienta Adyen lub w menu transakcji na terminalu POS).</span><span class="sxs-lookup"><span data-stu-id="ebc7c-125">PSP reference number, if the issue involved a specific transaction (You can find the PSP reference number on the receipt, in the Adyen Customer Area, or on the transactions menu on the POS terminal.)</span></span></li><li><span data-ttu-id="ebc7c-126">Zrzut ekranu lub zdjęcie komunikatu o błędzie (jeśli ma zastosowanie)</span><span class="sxs-lookup"><span data-stu-id="ebc7c-126">Screenshot or photo of the error message, if applicable</span></span></li><li><span data-ttu-id="ebc7c-127">Dzienniki podglądu zdarzeń (w formacie txt)</span><span class="sxs-lookup"><span data-stu-id="ebc7c-127">Event Viewer logs (in .txt format)</span></span></li><li><span data-ttu-id="ebc7c-128">Opis prób rozwiązania problemu i jego rozwiązania</span><span class="sxs-lookup"><span data-stu-id="ebc7c-128">Description of the issue and troubleshooting steps that you've tried</span></span></li></ul> |

## <a name="additional-resources"></a><span data-ttu-id="ebc7c-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ebc7c-129">Additional resources</span></span>

[<span data-ttu-id="ebc7c-130">Akceptuj płatności za pomocą łącznika Adyen dla Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ebc7c-130">Accept payments with the Adyen connector for Dynamics 365 Commerce</span></span>](https://www.adyen.com/partners/dynamics-365-commerce)

[<span data-ttu-id="ebc7c-131">Łącznik płatności usługi Dynamics 365 dla Adyen</span><span class="sxs-lookup"><span data-stu-id="ebc7c-131">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="ebc7c-132">Skonfiguruj łącznik płatności Adyen dla Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ebc7c-132">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
