---
title: "Lokalizacja wyjściowa produkcji"
description: "W tym temacie opisano hierarchię używaną do identyfikowania lokalizacji wyjściowej produkcji."
author: johanhoffmann
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e53c8e96579dba3b47bef0c00e55b8fa786fc55c
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="production-output-location"></a><span data-ttu-id="5f67c-103">Lokalizacja wyjściowa produkcji</span><span class="sxs-lookup"><span data-stu-id="5f67c-103">Production output location</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5f67c-104">W tym temacie opisano hierarchię używaną do identyfikowania lokalizacji wyjściowej produkcji.</span><span class="sxs-lookup"><span data-stu-id="5f67c-104">This topic describes the hierarchy that is used to identify the production output location.</span></span>

<span data-ttu-id="5f67c-105">Lokalizacja wyjściowa produkcji to lokalizacja, w której najpierw umieszcza się wyrób gotowy bezpośrednio po ukończeniu produkcji.</span><span class="sxs-lookup"><span data-stu-id="5f67c-105">The production output location is the location where a finished good is first stored after it's produced.</span></span> <span data-ttu-id="5f67c-106">Zazwyczaj znajduje się blisko miejsca wytwarzania.</span><span class="sxs-lookup"><span data-stu-id="5f67c-106">Usually, this location is close to the production process that produces the finished good.</span></span> <span data-ttu-id="5f67c-107">Lokalizacja wyjściowa produkcji jest wykorzystywana jako pośredni magazyn materiału, zanim zostanie on przeniesiony do obszaru wysyłki, miejsca składowania, lokalizacji wejściowej produkcji następnego procesu produkcji, itd.</span><span class="sxs-lookup"><span data-stu-id="5f67c-107">The production output location is used as intermediate storage for the material before it's moved on to the shipment area, a storage location, a production input location for a downstream production process, and so on.</span></span> 

<span data-ttu-id="5f67c-108">Domyślną lokalizację wyjściową produkcji ustawia się podczas zgłaszania wyrobów gotowych względem zlecenia produkcyjnego lub szarży produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="5f67c-108">A default production output location is set when finished goods are reported on a production order or batch order.</span></span> <span data-ttu-id="5f67c-109">Do identyfikowania tej lokalizacji wyjściowej jest używana hierarchii przedstawiona poniżej:</span><span class="sxs-lookup"><span data-stu-id="5f67c-109">The following hierarchy is used to identify this output location:</span></span>

1. <span data-ttu-id="5f67c-110">Używanie lokalizacji wyjściowej zdefiniowanej w nagłówku zlecenia produkcyjnego lub szarży produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="5f67c-110">Use the output location that is defined on the production order or batch order header.</span></span>
2. <span data-ttu-id="5f67c-111">Jeśli lokalizacja nie zostanie tam znaleziona — używanie lokalizacji wyjściowej zdefiniowanej w zasobie wykorzystywanym przez ostatnią operację zdefiniowaną w marszrucie produkcji.</span><span class="sxs-lookup"><span data-stu-id="5f67c-111">If no location is found there, use the output location that is defined on the resource that is used by the last operation that is defined in the production route.</span></span>
3. <span data-ttu-id="5f67c-112">Jeśli lokalizacja nie zostanie tam znaleziona — używanie lokalizacji wyjściowej zdefiniowanej w grupie zasobów wykorzystywanej przez zasób w ostatniej operacji zdefiniowanej w marszrucie produkcji.</span><span class="sxs-lookup"><span data-stu-id="5f67c-112">If no location is found there, use the output location that is defined on the resource group that is used by the resource for the last operation that is defined in the production route.</span></span>
4. <span data-ttu-id="5f67c-113">Jeśli lokalizacja nie zostanie tam znaleziona — używanie lokalizacji wyjściowej zdefiniowanej w magazynie zdefiniowanym dla zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="5f67c-113">If no location is found there, use the output location that is defined on the warehouse that is defined for the production order.</span></span>

<span data-ttu-id="5f67c-114">Domyślna lokalizacja wyjściowa produkcji jest ustawiana tylko dla produktów skonfigurowanych przy użyciu funkcjonalności zaawansowanych procesów magazynowych.</span><span class="sxs-lookup"><span data-stu-id="5f67c-114">A default production output location is set only for products that are set up by using advanced warehouse processes.</span></span> <span data-ttu-id="5f67c-115">Gdy towar tego typu jest zgłaszany jako gotowy, jest tworzona praca magazynowa typu **Ukończono odkładanie wyrobów** lub **Odłożenie produktu ubocznego i produktu towarzyszącego**.</span><span class="sxs-lookup"><span data-stu-id="5f67c-115">When this type of item is reported as finished, warehouse work of the **Finished goods put away** or **Co-product and by-product put away** type is created.</span></span> <span data-ttu-id="5f67c-116">W tym typie pracy lokalizacja wyjściowa produkcji jest wykorzystywana jako lokalizacja pobrania.</span><span class="sxs-lookup"><span data-stu-id="5f67c-116">This type of work uses the production output location as the pick location.</span></span> <span data-ttu-id="5f67c-117">Lokalizacja odłożenia jest określana przez dyrektywy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="5f67c-117">The put-away location is determined by the location directives.</span></span>

