--- 
title: "Wprowadzanie środka komplementarnego dla środka trwałego"
description: "W tej procedurze pokazano, jak dodać środek komplementarny do istniejącego środka trwałego."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4c22fb105d0deedda1b7dbfdd919d1745ad0ca2f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="ed518-103">Wprowadzanie środka komplementarnego dla środka trwałego</span><span class="sxs-lookup"><span data-stu-id="ed518-103">Enter an addition to a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ed518-104">W tej procedurze pokazano, jak dodać środek komplementarny do istniejącego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="ed518-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="ed518-105">Celem komplementarnych środków trwałych jest śledzenie wzbogacania, konserwacji lub ulepszeń składników aktywów. Służą one wyłącznie do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="ed518-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="ed518-106">Wszelkie zmiany wartości lub okresu użytkowania środka trwałego należy wprowadzać osobno.</span><span class="sxs-lookup"><span data-stu-id="ed518-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   



<span data-ttu-id="ed518-107">Procedura korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ed518-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="ed518-108">Przejdź do Środki trwałe > Środki trwałe > Środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="ed518-108">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="ed518-109">Na liście odszukaj i zaznacz środek trwały, do którego ma zostać dodany środek komplementarny.</span><span class="sxs-lookup"><span data-stu-id="ed518-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="ed518-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ed518-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ed518-111">W okienku akcji kliknij pozycję Środek trwały.</span><span class="sxs-lookup"><span data-stu-id="ed518-111">On the Action Pane, click Fixed asset.</span></span>
5. <span data-ttu-id="ed518-112">Kliknij opcję Komplementarne środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="ed518-112">Click Fixed asset additions.</span></span>
6. <span data-ttu-id="ed518-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ed518-113">Click New.</span></span>
7. <span data-ttu-id="ed518-114">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ed518-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="ed518-115">Ustaw datę zakupu środka komplementarnego lub rozpoczęcia jego użytkowania.</span><span class="sxs-lookup"><span data-stu-id="ed518-115">Set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="ed518-116">Wprowadź koszt towaru albo informacje o jego konserwacji lub ulepszeniach.</span><span class="sxs-lookup"><span data-stu-id="ed518-116">Enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="ed518-117">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="ed518-117">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="ed518-118">Łączny koszt nie ma wpływu na wartość środka trwałego i służy tylko do celów śledzenia i informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="ed518-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="ed518-119">Jeśli koszt będzie kapitalizowany, należy osobno zaksięgować transakcję zwiększenia wartości.</span><span class="sxs-lookup"><span data-stu-id="ed518-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="ed518-120">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="ed518-120">Click the General tab.</span></span>
    * <span data-ttu-id="ed518-121">Zaznacz opcję Zwiększa okres użytkowania, jeśli środek komplementarny wydłuża okres użytkowania składnika aktywów.</span><span class="sxs-lookup"><span data-stu-id="ed518-121">Set Increases service life if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="ed518-122">To pole służy wyłącznie do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="ed518-122">This field is informational only.</span></span> <span data-ttu-id="ed518-123">W celu przedłużenia okresu użytkowania zmodyfikuj go w modelach ewidencji i/lub księgach amortyzacji składnika aktywów.</span><span class="sxs-lookup"><span data-stu-id="ed518-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  


