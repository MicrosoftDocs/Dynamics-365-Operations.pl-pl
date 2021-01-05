---
title: Karty lojalnościowe odbiorców i punkty lojalnościowe
description: W tym temacie opisano integrację danych o kartach lojalnościowych odbiorców i punktach wynagrodzenia w konfiguracjach z podwójnym zapisem.
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
ms.openlocfilehash: 28872e9510394cf3d5cee151798d4130b8b6fe27
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683505"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="b6c92-103">Karty lojalnościowe odbiorców i punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="b6c92-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b6c92-104">Firmy klasyfikują odbiorców i świadczą zaawansowane usługi w oparciu o zakupy i wydatki klientów.</span><span class="sxs-lookup"><span data-stu-id="b6c92-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="b6c92-105">Na przykład w rozwiązaniu Dynamics 365 Commerce istnieje infrastruktura i funkcje ułatwiające i obsługujące karty lojalnościowe odbiorców, punkty wynagrodzenia, ceny na podstawie lojalności i zakupy na podstawie nagród.</span><span class="sxs-lookup"><span data-stu-id="b6c92-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="b6c92-106">Gdy dane o kartach lojalnościowych odbiorców i punktach sprzedaży w module Commerce są synchronizowane z Dataverse, aplikacje do zakontraktowania odbiorcy mogą wykorzystywać te dane.</span><span class="sxs-lookup"><span data-stu-id="b6c92-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="b6c92-107">Na przykład użytkownicy Dynamics 365 Customer Service mogą skorzystać z danych, aby dostarczać te same zaawansowane usługi za pośrednictwem pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="b6c92-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="b6c92-108">Szablony</span><span class="sxs-lookup"><span data-stu-id="b6c92-108">Templates</span></span>

| <span data-ttu-id="b6c92-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b6c92-109">Finance and Operations apps</span></span> | <span data-ttu-id="b6c92-110">Aplikacje oparte na modelu w systemie Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b6c92-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="b6c92-111">opis</span><span class="sxs-lookup"><span data-stu-id="b6c92-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="b6c92-112">Karta lojalnościowa</span><span class="sxs-lookup"><span data-stu-id="b6c92-112">Loyalty card</span></span>                | <span data-ttu-id="b6c92-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="b6c92-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="b6c92-114">Ten szablon powoduje zsynchronizowanie informacji o kartach lojalnościowych klienta.</span><span class="sxs-lookup"><span data-stu-id="b6c92-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="b6c92-115">Punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="b6c92-115">Loyalty reward points</span></span>       | <span data-ttu-id="b6c92-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="b6c92-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="b6c92-117">Ten szablon powoduje zsynchronizowanie informacji o punktach nagród klienta.</span><span class="sxs-lookup"><span data-stu-id="b6c92-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
