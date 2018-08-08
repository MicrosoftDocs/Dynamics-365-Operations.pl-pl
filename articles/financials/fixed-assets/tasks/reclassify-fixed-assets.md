--- 
title: "Zmień klasyfikację środków trwałych"
description: "Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie."
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: d8e289e2c18fd28829fb4b749933ae1d84e0b631
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="fec40-103">Zmień klasyfikację środków trwałych</span><span class="sxs-lookup"><span data-stu-id="fec40-103">Reclassify fixed assets</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fec40-104">Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie.</span><span class="sxs-lookup"><span data-stu-id="fec40-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="fec40-105">Po przeklasyfikowaniu środka trwałego:</span><span class="sxs-lookup"><span data-stu-id="fec40-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="fec40-106">• Wszystkie modele ewidencji istniejącego środka trwałego zostają utworzone dla nowego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="fec40-106">• All value models for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="fec40-107">Wszystkie informacje skonfigurowane dla oryginalnego środka trwałego zostają skopiowane do nowego środka stałego.</span><span class="sxs-lookup"><span data-stu-id="fec40-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="fec40-108">Stan modeli ewidencji oryginalnego środka trwałego zostaje ustawiony na Zamknięte.</span><span class="sxs-lookup"><span data-stu-id="fec40-108">The status of the value models for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="fec40-109">• Nowe modele ewidencji nowego środka stałego zawierają datę przeklasyfikowania w polu Data nabycia.</span><span class="sxs-lookup"><span data-stu-id="fec40-109">• The new value models of the new fixed asset contain the date of the reclassification in the Acquisition date field.</span></span> <span data-ttu-id="fec40-110">Data w polu Data rozpoczęcia amortyzacji jest kopiowana z oryginalnych informacji o środku trwałym.</span><span class="sxs-lookup"><span data-stu-id="fec40-110">The date in the Depreciation run date field is copied from the original asset information.</span></span> <span data-ttu-id="fec40-111">Jeśli amortyzacja jest już rozpoczęta, to w polu Data ostatniego uruchomienia amortyzacji zostaje wyświetlona data przeklasyfikowania.</span><span class="sxs-lookup"><span data-stu-id="fec40-111">If the depreciation has already started, the Date when depreciation was last run field displays the date of the reclassification.</span></span> 

<span data-ttu-id="fec40-112">• Transakcje istniejącego środka trwałego zostają anulowane i wygenerowane ponownie dla nowego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="fec40-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

1. <span data-ttu-id="fec40-113">Wybierz kolejno opcje Środki trwałe > Zadania okresowe > Przeklasyfikowanie.</span><span class="sxs-lookup"><span data-stu-id="fec40-113">Go to Fixed assets > Periodic tasks > Reclassification.</span></span>
2. <span data-ttu-id="fec40-114">W polu Grupa środków trwałych zaznacz grupę, którą chcesz przeklasyfikować.</span><span class="sxs-lookup"><span data-stu-id="fec40-114">In the Fixed asset group field, select the group to reclassify.</span></span>
3. <span data-ttu-id="fec40-115">W polu Numer środka trwałego zaznacz środek trwały, który chcesz przeklasyfikować.</span><span class="sxs-lookup"><span data-stu-id="fec40-115">In the Fixed asset number field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="fec40-116">W polu Nowa grupa środków trwałych wybierz grupę, do której ma zostać przeniesiony środek trwały.</span><span class="sxs-lookup"><span data-stu-id="fec40-116">In the New fixed asset group field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="fec40-117">Jeśli nowa grupa środków trwałych jest przypisana do numeracji, pole Nowy numer środka trwałego zostanie zaktualizowane o numer z nowej numeracji grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="fec40-117">If the new fixed asset group is attached to a number sequence, the New fixed asset number field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="fec40-118">W przeciwnym razie pole Nowy numer środka trwałego jest aktualizowane o numer z numeracji ustawionej na stronie Parametry środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="fec40-118">Otherwise, the New fixed asset number field is updated with the number from the number sequence that is set up in the Fixed asset parameters page.</span></span> <span data-ttu-id="fec40-119">Jeśli na stronie Parametry środków trwałych nie skonfigurowano numeracji, wpisz numer w polu Nowy numer środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="fec40-119">If a number sequence is not set up in the Fixed asset parameters page, enter a number in the New fixed asset number field.</span></span>  
5. <span data-ttu-id="fec40-120">W polu Data przeklasyfikowania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="fec40-120">In the Reclassification date field, enter a date.</span></span>
6. <span data-ttu-id="fec40-121">W polu Seria załączników wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fec40-121">In the Voucher series field, enter or select a value.</span></span>
7. <span data-ttu-id="fec40-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="fec40-122">Click OK.</span></span>


