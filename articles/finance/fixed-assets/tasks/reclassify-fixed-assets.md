---
title: Zmień klasyfikację środków trwałych
description: Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie.
author: saraschi2
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbfb754459fad1f3b1509f4f9c65c20e0385b013
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944721"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="364b4-103">Zmień klasyfikację środków trwałych</span><span class="sxs-lookup"><span data-stu-id="364b4-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="364b4-104">Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie.</span><span class="sxs-lookup"><span data-stu-id="364b4-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="364b4-105">Po przeklasyfikowaniu środka trwałego:</span><span class="sxs-lookup"><span data-stu-id="364b4-105">When a fixed asset is reclassified:</span></span>

- <span data-ttu-id="364b4-106">Wszystkie księgi dla istniejącego środka trwałego zostają utworzone dla nowego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="364b4-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="364b4-107">Wszystkie informacje skonfigurowane dla oryginalnego środka trwałego zostają skopiowane do nowego środka stałego.</span><span class="sxs-lookup"><span data-stu-id="364b4-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="364b4-108">Stan ksiąg oryginalnego środka trwałego zostaje ustawiony na Zamknięte.</span><span class="sxs-lookup"><span data-stu-id="364b4-108">The status of the books for the original fixed asset is Closed.</span></span> 

- <span data-ttu-id="364b4-109">Nowe księgi nowego środka stałego zawierają datę przeklasyfikowania w polu **Data nabycia**.</span><span class="sxs-lookup"><span data-stu-id="364b4-109">The new books for the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="364b4-110">Data w polu **Data rozpoczęcia amortyzacji** jest kopiowana z oryginalnych informacji o środku trwałym.</span><span class="sxs-lookup"><span data-stu-id="364b4-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="364b4-111">Jeśli amortyzacja jest już rozpoczęta, to w polu **Data ostatniego uruchomienia amortyzacji** zostaje wyświetlona data przeklasyfikowania.</span><span class="sxs-lookup"><span data-stu-id="364b4-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

- <span data-ttu-id="364b4-112">Transakcje istniejącego środka trwałego zostają anulowane i wygenerowane ponownie dla nowego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="364b4-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

- <span data-ttu-id="364b4-113">W przypadku przeklasyfikowania środka trwałego z transakcją przeniesienia w **centrum akcji** zostanie wyświetlony komunikat informujący, że transakcja przeniesienia nie została zakończona w trakcie procesu przeklasyfikowania.</span><span class="sxs-lookup"><span data-stu-id="364b4-113">When an asset that has a transfer transaction has been reclassified, the system will display a message in the **Action center** to indicate that a transfer transaction wasn't completed during the reclassification process.</span></span> <span data-ttu-id="364b4-114">Konieczne jest zakończenie transakcji przeniesienia w celu przeniesienia istniejących transakcji przeklasyfikowania do odpowiednich wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="364b4-114">It's necessary to complete a transfer transaction to move the existing reclassification transactions to the appropriate financial dimensions.</span></span> 

   <span data-ttu-id="364b4-115">W procesie przeklasyfikowania system uruchamia następujące akcje w celu przeklasyfikowania salda środków trwałych z oryginalnego środka trwałego do nowego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="364b4-115">During the reclassification process, the system runs the following actions to reclassify the asset balance from the original asset to the new asset.</span></span> 
   
   - <span data-ttu-id="364b4-116">Proces przeklasyfikowania kopiuje dane z oryginalnej księgi środków trwałych do nowej księgi środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="364b4-116">The reclassification process copies the data from the original fixed asset book to the new fixed asset book.</span></span>

   - <span data-ttu-id="364b4-117">Transakcja przeklasyfikowania wykorzystuje informacje z oryginalnego zaksięgowanego nabycia, które zawiera informacje o wymiarach finansowych zawartych w transakcji nabycia.</span><span class="sxs-lookup"><span data-stu-id="364b4-117">The reclassification transaction uses information from the original posted acquisition that includes financial dimension information that is included in the acquisition transaction.</span></span>  
   
   - <span data-ttu-id="364b4-118">Jednocześnie proces przeklasyfikowania wycofuje oryginalną transakcję nabycia i przeniesienia środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="364b4-118">At the same time, the reclassification process reverses the original asset acquisition and asset transfer transaction.</span></span> 

<span data-ttu-id="364b4-119">Poniższy diagram i procedura stanowią przykład procesu przeklasyfikowania.</span><span class="sxs-lookup"><span data-stu-id="364b4-119">The following diagram and procedure provide an example of the reclassification process.</span></span> 

<span data-ttu-id="364b4-120">[![Diagram pokazujący proces przeklasyfikowania](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span><span class="sxs-lookup"><span data-stu-id="364b4-120">[![Diagram showing the reclassicification process](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span></span>

<span data-ttu-id="364b4-121">Aby przeklasyfikować środek trwały, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="364b4-121">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="364b4-122">Wybierz kolejno opcje **Środki trwałe > Zadania okresowe > Przeklasyfikowanie**.</span><span class="sxs-lookup"><span data-stu-id="364b4-122">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="364b4-123">W polu **Grupa środków trwałych** zaznacz grupę, którą chcesz przeklasyfikować.</span><span class="sxs-lookup"><span data-stu-id="364b4-123">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="364b4-124">W polu **Numer środka trwałego** zaznacz środek trwały, który chcesz przeklasyfikować.</span><span class="sxs-lookup"><span data-stu-id="364b4-124">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="364b4-125">W polu **Nowa grupa środków trwałych** wybierz grupę, do której ma zostać przeniesiony środek trwały.</span><span class="sxs-lookup"><span data-stu-id="364b4-125">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="364b4-126">Jeśli nowa grupa środków trwałych jest przypisana do numeracji, pole **Nowy numer środka trwałego** zostanie zaktualizowane o numer z nowej numeracji grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="364b4-126">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="364b4-127">W przeciwnym razie pole **Nowy numer środka trwałego** jest aktualizowane o numer z numeracji ustawionej na stronie **Parametry środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="364b4-127">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="364b4-128">Jeśli na stronie **Parametry środków trwałych** nie skonfigurowano numeracji, wpisz numer w polu **Nowy numer środka trwałego**.</span><span class="sxs-lookup"><span data-stu-id="364b4-128">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="364b4-129">W polu **Data przeklasyfikowania** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="364b4-129">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="364b4-130">W polu **Seria załączników** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="364b4-130">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="364b4-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="364b4-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
