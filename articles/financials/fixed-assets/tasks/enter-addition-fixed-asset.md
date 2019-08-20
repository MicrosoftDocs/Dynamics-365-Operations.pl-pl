---
title: Wprowadzanie środka komplementarnego dla środka trwałego
description: W tej procedurze pokazano, jak dodać środek komplementarny do istniejącego środka trwałego.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe1a1d4db696ac013afee05b697b301383232134
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839960"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="9b105-103">Wprowadzanie środka komplementarnego dla środka trwałego</span><span class="sxs-lookup"><span data-stu-id="9b105-103">Enter an addition to a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9b105-104">W tej procedurze pokazano, jak dodać środek komplementarny do istniejącego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="9b105-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="9b105-105">Celem komplementarnych środków trwałych jest śledzenie wzbogacania, konserwacji lub ulepszeń składników aktywów. Służą one wyłącznie do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="9b105-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="9b105-106">Wszelkie zmiany wartości lub okresu użytkowania środka trwałego należy wprowadzać osobno.</span><span class="sxs-lookup"><span data-stu-id="9b105-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   

<span data-ttu-id="9b105-107">Procedura korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="9b105-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="9b105-108">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Środki trwałe > Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="9b105-108">In the Navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="9b105-109">Na liście odszukaj i zaznacz środek trwały, do którego ma zostać dodany środek komplementarny.</span><span class="sxs-lookup"><span data-stu-id="9b105-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="9b105-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9b105-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9b105-111">W okienku akcji kliknij pozycję **Środek trwały**.</span><span class="sxs-lookup"><span data-stu-id="9b105-111">On the Action Pane, click **Fixed asset**.</span></span>
5. <span data-ttu-id="9b105-112">Kliknij opcję **Komplementarne środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="9b105-112">Click **Fixed asset additions**.</span></span>
6. <span data-ttu-id="9b105-113">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="9b105-113">Click **New**.</span></span>
7. <span data-ttu-id="9b105-114">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9b105-114">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="9b105-115">W polu **Data nabycia** ustaw datę zakupu dodatku lub usługi.</span><span class="sxs-lookup"><span data-stu-id="9b105-115">In the **Acquisition date** field, set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="9b105-116">W polu **Koszt jednostkowy** wprowadź koszt towaru albo informacje o jego konserwacji lub ulepszeniach.</span><span class="sxs-lookup"><span data-stu-id="9b105-116">In the **Unit cost** field, enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="9b105-117">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="9b105-117">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="9b105-118">Łączny koszt nie ma wpływu na wartość środka trwałego i służy tylko do celów śledzenia i informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="9b105-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="9b105-119">Jeśli koszt będzie kapitalizowany, należy osobno zaksięgować transakcję zwiększenia wartości.</span><span class="sxs-lookup"><span data-stu-id="9b105-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="9b105-120">Kliknij kartę **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="9b105-120">Click the **General** tab.</span></span>

    * <span data-ttu-id="9b105-121">Zaznacz opcję **Zwiększa okres użytkowania** na **Tak**, jeśli środek komplementarny wydłuża okres użytkowania składnika aktywów.</span><span class="sxs-lookup"><span data-stu-id="9b105-121">Set **Increases service life** to **Yes** if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="9b105-122">To pole służy wyłącznie do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="9b105-122">This field is informational only.</span></span> <span data-ttu-id="9b105-123">W celu przedłużenia okresu użytkowania zmodyfikuj go w modelach ewidencji i/lub księgach amortyzacji składnika aktywów.</span><span class="sxs-lookup"><span data-stu-id="9b105-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  

