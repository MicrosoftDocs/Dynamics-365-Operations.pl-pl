---
title: Zmień klasyfikację środków trwałych
description: Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47d8cf2ff1e275df0466a7fe327a3180c0399e49
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839936"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="9aef2-103">Zmień klasyfikację środków trwałych</span><span class="sxs-lookup"><span data-stu-id="9aef2-103">Reclassify fixed assets</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9aef2-104">Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie.</span><span class="sxs-lookup"><span data-stu-id="9aef2-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="9aef2-105">Po przeklasyfikowaniu środka trwałego:</span><span class="sxs-lookup"><span data-stu-id="9aef2-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="9aef2-106">• Wszystkie księgi dla istniejącego środka trwałego zostają utworzone dla nowego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="9aef2-106">• All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="9aef2-107">Wszystkie informacje skonfigurowane dla oryginalnego środka trwałego zostają skopiowane do nowego środka stałego.</span><span class="sxs-lookup"><span data-stu-id="9aef2-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="9aef2-108">Stan ksiąg oryginalnego środka trwałego zostaje ustawiony na Zamknięte.</span><span class="sxs-lookup"><span data-stu-id="9aef2-108">The status of the books for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="9aef2-109">• Nowe księgi nowego środka stałego zawierają datę przeklasyfikowania w polu **Data nabycia**.</span><span class="sxs-lookup"><span data-stu-id="9aef2-109">• The new books of the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="9aef2-110">Data w polu **Data rozpoczęcia amortyzacji** jest kopiowana z oryginalnych informacji o środku trwałym.</span><span class="sxs-lookup"><span data-stu-id="9aef2-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="9aef2-111">Jeśli amortyzacja jest już rozpoczęta, to w polu **Data ostatniego uruchomienia amortyzacji** zostaje wyświetlona data przeklasyfikowania.</span><span class="sxs-lookup"><span data-stu-id="9aef2-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

<span data-ttu-id="9aef2-112">• Transakcje istniejącego środka trwałego zostają anulowane i wygenerowane ponownie dla nowego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="9aef2-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

<span data-ttu-id="9aef2-113">Aby przeklasyfikować środek trwały, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="9aef2-113">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="9aef2-114">Wybierz kolejno opcje **Środki trwałe > Zadania okresowe > Przeklasyfikowanie**.</span><span class="sxs-lookup"><span data-stu-id="9aef2-114">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="9aef2-115">W polu **Grupa środków trwałych** zaznacz grupę, którą chcesz przeklasyfikować.</span><span class="sxs-lookup"><span data-stu-id="9aef2-115">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="9aef2-116">W polu **Numer środka trwałego** zaznacz środek trwały, który chcesz przeklasyfikować.</span><span class="sxs-lookup"><span data-stu-id="9aef2-116">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="9aef2-117">W polu **Nowa grupa środków trwałych** wybierz grupę, do której ma zostać przeniesiony środek trwały.</span><span class="sxs-lookup"><span data-stu-id="9aef2-117">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="9aef2-118">Jeśli nowa grupa środków trwałych jest przypisana do numeracji, pole **Nowy numer środka trwałego** zostanie zaktualizowane o numer z nowej numeracji grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="9aef2-118">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="9aef2-119">W przeciwnym razie pole **Nowy numer środka trwałego** jest aktualizowane o numer z numeracji ustawionej na stronie **Parametry środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="9aef2-119">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="9aef2-120">Jeśli na stronie **Parametry środków trwałych** nie skonfigurowano numeracji, wpisz numer w polu **Nowy numer środka trwałego**.</span><span class="sxs-lookup"><span data-stu-id="9aef2-120">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="9aef2-121">W polu **Data przeklasyfikowania** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="9aef2-121">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="9aef2-122">W polu **Seria załączników** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9aef2-122">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="9aef2-123">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9aef2-123">Click **OK**.</span></span>
