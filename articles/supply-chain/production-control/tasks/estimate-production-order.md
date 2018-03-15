---
title: Szacowanie zlecenia produkcyjnego
description: "Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnego zestawu danych."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 862281adac67757e1ce0e9ddd1e96483363abb9a
ms.contentlocale: pl-pl
ms.lasthandoff: 02/06/2018

---
# <a name="estimate-a-production-order"></a><span data-ttu-id="6cef4-103">Szacowanie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="6cef4-103">Estimate a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6cef4-104">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnego zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="6cef4-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="6cef4-105">W obu przypadkach należy mieć otwarte zlecenie produkcyjne o stanie Utworzono.</span><span class="sxs-lookup"><span data-stu-id="6cef4-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="6cef4-106">Jest to druga z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="6cef4-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="6cef4-107">Szacowanie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="6cef4-107">Estimate a production order</span></span>
1. <span data-ttu-id="6cef4-108">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="6cef4-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="6cef4-109">W siatce zaznacz zlecenie, które ma stan Utworzono.</span><span class="sxs-lookup"><span data-stu-id="6cef4-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="6cef4-110">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="6cef4-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="6cef4-111">Kliknij przycisk Szacuj.</span><span class="sxs-lookup"><span data-stu-id="6cef4-111">Click Estimate.</span></span>
    * <span data-ttu-id="6cef4-112">W tym kroku jest obliczany szacowany koszt jednego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="6cef4-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="6cef4-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6cef4-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="6cef4-114">Wyświetlanie szczegółów obliczeń</span><span class="sxs-lookup"><span data-stu-id="6cef4-114">View the calculation details</span></span>
1. <span data-ttu-id="6cef4-115">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="6cef4-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="6cef4-116">Kliknij opcję Wyświetl szczegóły obliczeń.</span><span class="sxs-lookup"><span data-stu-id="6cef4-116">Click View calculation details.</span></span>
    * <span data-ttu-id="6cef4-117">Na tej stronie jest wyświetlany podział kosztów.</span><span class="sxs-lookup"><span data-stu-id="6cef4-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="6cef4-118">Na przykład można wyświetlić całkowity koszt własny na jednostkę wyrobu gotowego w pierwszym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6cef4-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="6cef4-119">Kolejne wiersze zawierają koszty według listy składowej, marszruty produkcji i kosztów pośrednich.</span><span class="sxs-lookup"><span data-stu-id="6cef4-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  

