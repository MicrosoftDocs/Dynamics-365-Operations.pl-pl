---
title: Moduł kart upominkowych
description: W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 70047376cec44523cc9cfe4df792bde23c776d8c
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261585"
---
# <a name="gift-card-module"></a><span data-ttu-id="c1d9e-103">Moduł kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="c1d9e-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c1d9e-104">W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c1d9e-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="c1d9e-105">Overview</span></span>

<span data-ttu-id="c1d9e-106">Karty upominkowe są powszechną formą płatności, a moduł kart upominkowych może być używany w module realizacji transakcji w celu przyjmowania kart upominkowych.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-106">Gift cards are a common form of payment, and the gift card module can be used in a checkout module to accept gift cards.</span></span> <span data-ttu-id="c1d9e-107">Moduł kart upominkowych wspiera Dynamics 365, SVS i karty upominkowe Givex.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="c1d9e-108">Karty upominkowe SVS i Givex są realizowane przez dostawcę płatności Adyen.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span>

<span data-ttu-id="c1d9e-109">Aby uzyskać więcej informacji na temat obsługi zewnętrznych kart upominkowych, takich jak SVS i Givex, zajrzyj do [Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md)</span><span class="sxs-lookup"><span data-stu-id="c1d9e-109">For more information on support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md)</span></span>

## <a name="module-properties"></a><span data-ttu-id="c1d9e-110">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="c1d9e-110">Module properties</span></span>

- <span data-ttu-id="c1d9e-111">**Pokaż dodatkowe pola** — ta właściwość określa pola, które mają być wyświetlane w przypadku kart upominkowych, oprócz numeru karty upominkowej, który jest zawsze domyślnie wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-111">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="c1d9e-112">Na przykład niektóre karty upominkowe umożliwiają wyświetlanie osobistego numeru identyfikacyjnego (PIN), a inne umożliwiają wyświetlanie numeru PIN i daty ważności.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-112">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="c1d9e-113">Można również ustawić tę właściwość na „Brak”, co spowoduje wyświetlenie numeru karty upominkowej bez dodatkowych pól.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-113">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="c1d9e-114">Obsługiwane wartości:</span><span class="sxs-lookup"><span data-stu-id="c1d9e-114">Supported values:</span></span>
-   <span data-ttu-id="c1d9e-115">PIN</span><span class="sxs-lookup"><span data-stu-id="c1d9e-115">PIN</span></span>
-   <span data-ttu-id="c1d9e-116">Data ważności</span><span class="sxs-lookup"><span data-stu-id="c1d9e-116">Expiration date</span></span>
-   <span data-ttu-id="c1d9e-117">Numer PIN i data ważności</span><span class="sxs-lookup"><span data-stu-id="c1d9e-117">PIN and expiration date</span></span> 
-   <span data-ttu-id="c1d9e-118">None</span><span class="sxs-lookup"><span data-stu-id="c1d9e-118">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="c1d9e-119">Ustawienia witryny dla modułów kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="c1d9e-119">Site settings for gift card modules</span></span>

<span data-ttu-id="c1d9e-120">W konstruktorze witryn Commerce w **Ustawienia witryny \> Rozszerzenia** istnieje ustawienie modułu kart upominkowych o nazwie **Obsługiwany typ karty upominkowej**.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-120">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="c1d9e-121">To ustawienie obsługuje trzy wartości:</span><span class="sxs-lookup"><span data-stu-id="c1d9e-121">This setting supports three values:</span></span>
- <span data-ttu-id="c1d9e-122">**Dynamics 365 — karta upominkowa** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-122">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="c1d9e-123">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-123">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="c1d9e-124">**Karty upominkowe SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-124">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="c1d9e-125">To ustawienie jest obsługiwane dla użytkowników anonimowych oraz zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-125">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="c1d9e-126">**Karty upominkowe Dynamics 365, SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365, SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-126">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="c1d9e-127">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="c1d9e-127">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="c1d9e-128">Dodawanie modułu kart upominkowych do strony</span><span class="sxs-lookup"><span data-stu-id="c1d9e-128">Add a gift card module to a page</span></span>

<span data-ttu-id="c1d9e-129">Aby uzyskać instrukcje dotyczące dodawania modułu kart upominkowych do strony realizacji transakcji i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="c1d9e-129">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c1d9e-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c1d9e-130">Additional resources</span></span>

[<span data-ttu-id="c1d9e-131">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="c1d9e-131">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c1d9e-132">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="c1d9e-132">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c1d9e-133">Obsługa zewnętrznych kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="c1d9e-133">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
