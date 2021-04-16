---
title: Karty lojalnościowe odbiorców i punkty lojalnościowe
description: W tym temacie opisano integrację danych o kartach lojalnościowych odbiorców i punktach wynagrodzenia w konfiguracjach z podwójnym zapisem.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d2c3845c1a7371d9e992495246e8dd0eb8631020
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747994"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="f453e-103">Karty lojalnościowe odbiorców i punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="f453e-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f453e-104">Firmy klasyfikują odbiorców i świadczą zaawansowane usługi w oparciu o zakupy i wydatki klientów.</span><span class="sxs-lookup"><span data-stu-id="f453e-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="f453e-105">Na przykład w rozwiązaniu Dynamics 365 Commerce istnieje infrastruktura i funkcje ułatwiające i obsługujące karty lojalnościowe odbiorców, punkty wynagrodzenia, ceny na podstawie lojalności i zakupy na podstawie nagród.</span><span class="sxs-lookup"><span data-stu-id="f453e-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="f453e-106">Gdy dane o kartach lojalnościowych odbiorców i punktach sprzedaży w module Commerce są synchronizowane z Dataverse, aplikacje do zakontraktowania odbiorcy mogą wykorzystywać te dane.</span><span class="sxs-lookup"><span data-stu-id="f453e-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="f453e-107">Na przykład użytkownicy Dynamics 365 Customer Service mogą skorzystać z danych, aby dostarczać te same zaawansowane usługi za pośrednictwem pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="f453e-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="f453e-108">Szablony</span><span class="sxs-lookup"><span data-stu-id="f453e-108">Templates</span></span>

| <span data-ttu-id="f453e-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f453e-109">Finance and Operations apps</span></span> | <span data-ttu-id="f453e-110">Aplikacje oparte na modelu w systemie Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f453e-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="f453e-111">opis</span><span class="sxs-lookup"><span data-stu-id="f453e-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="f453e-112">Karta lojalnościowa</span><span class="sxs-lookup"><span data-stu-id="f453e-112">Loyalty card</span></span>                | <span data-ttu-id="f453e-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="f453e-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="f453e-114">Ten szablon powoduje zsynchronizowanie informacji o kartach lojalnościowych klienta.</span><span class="sxs-lookup"><span data-stu-id="f453e-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="f453e-115">Punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="f453e-115">Loyalty reward points</span></span>       | <span data-ttu-id="f453e-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="f453e-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="f453e-117">Ten szablon powoduje zsynchronizowanie informacji o punktach nagród klienta.</span><span class="sxs-lookup"><span data-stu-id="f453e-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]