---
title: Karty lojalnościowe odbiorców i punkty lojalnościowe
description: W tym temacie opisano integrację danych o kartach lojalnościowych odbiorców i punktach wynagrodzenia między aplikacjami Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 24ce08bb6cba9c74075151bafe0b07509fbdf73d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3998021"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="4cd59-103">Karty lojalnościowe odbiorców i punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="4cd59-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="4cd59-104">Firmy klasyfikują odbiorców i świadczą zaawansowane usługi w oparciu o zakupy i wydatki klientów.</span><span class="sxs-lookup"><span data-stu-id="4cd59-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="4cd59-105">W pakiecie aplikacji Microsoft Dynamics 365 Dynamics 365 Commerce istnieje infrastruktura i funkcje ułatwiające i obsługujące karty lojalnościowe odbiorców, punkty wynagrodzenia, ceny na podstawie lojalności i zakupy na podstawie nagród.</span><span class="sxs-lookup"><span data-stu-id="4cd59-105">In the Microsoft Dynamics 365 suite of applications, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="4cd59-106">Gdy dane o kartach lojalnościowych odbiorców i punktach sprzedaży w module Commerce są synchronizowane z Common Data service, aplikacje oparte na modelach w Dynamics 365 mogą wykorzystywać te dane.</span><span class="sxs-lookup"><span data-stu-id="4cd59-106">When data about customer loyalty cards and reward points in Commerce is synced to Common Data service, model-driven apps in Dynamics 365 can use that data.</span></span> <span data-ttu-id="4cd59-107">Na przykład użytkownicy Dynamics 365 Customer Service mogą skorzystać z danych, aby dostarczać te same zaawansowane usługi za pośrednictwem pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="4cd59-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="4cd59-108">Szablony</span><span class="sxs-lookup"><span data-stu-id="4cd59-108">Templates</span></span>

| <span data-ttu-id="4cd59-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4cd59-109">Finance and Operations apps</span></span> | <span data-ttu-id="4cd59-110">Aplikacje oparte na modelu w systemie Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4cd59-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="4cd59-111">opis</span><span class="sxs-lookup"><span data-stu-id="4cd59-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="4cd59-112">Karta lojalnościowa</span><span class="sxs-lookup"><span data-stu-id="4cd59-112">Loyalty card</span></span>                | <span data-ttu-id="4cd59-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="4cd59-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="4cd59-114">Ten szablon powoduje zsynchronizowanie informacji o kartach lojalnościowych klienta.</span><span class="sxs-lookup"><span data-stu-id="4cd59-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="4cd59-115">Punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="4cd59-115">Loyalty reward points</span></span>       | <span data-ttu-id="4cd59-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="4cd59-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="4cd59-117">Ten szablon powoduje zsynchronizowanie informacji o punktach nagród klienta.</span><span class="sxs-lookup"><span data-stu-id="4cd59-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
