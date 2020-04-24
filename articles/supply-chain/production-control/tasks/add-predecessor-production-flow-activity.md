---
title: Dodawanie działania poprzedzającego do działania przepływu produkcji
description: W wersji przepływu produkcji wszystkie działania muszą być ustawione kolejno.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a373a251569f0bbd10a69a4ccd63db3ea030f49
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212418"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a><span data-ttu-id="59159-103">Dodawanie działania poprzedzającego do działania przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="59159-103">Add a predecessor to a production flow activity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="59159-104">W wersji przepływu produkcji wszystkie działania muszą być ustawione kolejno.</span><span class="sxs-lookup"><span data-stu-id="59159-104">In a production flow version, all activities must be sequenced.</span></span> <span data-ttu-id="59159-105">Działanie może mieć jeden lub wiele zdarzeń poprzedzających lub następujących.</span><span class="sxs-lookup"><span data-stu-id="59159-105">An activity can have one or multiple predecessors or successors.</span></span> 

<span data-ttu-id="59159-106">Ta procedura pokazuje, jak skojarzyć zdarzenie poprzedzające z działaniem.</span><span class="sxs-lookup"><span data-stu-id="59159-106">This procedure shows how to associate a predecessor to an activity.</span></span> 

<span data-ttu-id="59159-107">Do wykonania zadania potrzebujesz przepływ produkcji, który ma wersję roboczą z co najmniej dwoma działaniami, które mogą być połączone.</span><span class="sxs-lookup"><span data-stu-id="59159-107">To perform this task, you need a production flow that has the Draft version with at least two activities that can be connected.</span></span> 

<span data-ttu-id="59159-108">Aby uzyskać więcej informacji, zobacz oficjalny dokument „Przepływy produkcji i działania w produkcji oszczędnej”.</span><span class="sxs-lookup"><span data-stu-id="59159-108">To learn more, read the white paper "Production flows and activities in lean manufacturing."</span></span>


## <a name="find-the-production-flow-and-version"></a><span data-ttu-id="59159-109">Znajdowanie przepływu produkcji i wersji</span><span class="sxs-lookup"><span data-stu-id="59159-109">Find the production flow and version</span></span>
1. <span data-ttu-id="59159-110">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="59159-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="59159-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="59159-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="59159-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="59159-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="59159-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="59159-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="59159-114">Kliknij opcję Działania.</span><span class="sxs-lookup"><span data-stu-id="59159-114">Click Activities.</span></span>

## <a name="select-an-activity-and-add-a-predecessor"></a><span data-ttu-id="59159-115">Wybór działania i dodawanie zdarzenia poprzedzającego</span><span class="sxs-lookup"><span data-stu-id="59159-115">Select an activity and add a predecessor</span></span>
1. <span data-ttu-id="59159-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="59159-116">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="59159-117">Kliknij opcję Dodaj zdarzenie poprzedzające.</span><span class="sxs-lookup"><span data-stu-id="59159-117">Click Add predecessor.</span></span>
3. <span data-ttu-id="59159-118">Wprowadź lub wybierz wartość w polu Działanie.</span><span class="sxs-lookup"><span data-stu-id="59159-118">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="59159-119">W polu Wskaźnik czasu cyklu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="59159-119">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="59159-120">Domyślny współczynnik czasu cyklu dla relacji działań wynosi 1.</span><span class="sxs-lookup"><span data-stu-id="59159-120">The default cycle time ratio of an activity relation is 1.</span></span> <span data-ttu-id="59159-121">Zakłada on, że oba działania są wykonywane w tym samym tempie lub czasie taktu.</span><span class="sxs-lookup"><span data-stu-id="59159-121">This assumes that both activities run at the same pace or takt time.</span></span> <span data-ttu-id="59159-122">Jeżeli zdarzenie poprzedzające jest wykonywane w szybszym tempie (niższym czasie taktu), współczynnik powinien być niższe niż 1. Jeżeli zdarzenie poprzedzające odbywa się w wolniejszym tempie (wyższy czas taktu), współczynnik czasu cyklu jest większy niż 1.</span><span class="sxs-lookup"><span data-stu-id="59159-122">If the predecessor runs at a higher pace (lower takt time), the ratio should be lower than 1, if the predecessor runs at a slower pace (higher takt time) the cycle time ratio is greater than 1.</span></span>  
5. <span data-ttu-id="59159-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="59159-123">Click OK.</span></span>

