---
title: Kończenie zlecenia produkcyjnego
description: W tej procedurze pokazano sposób kończenia zlecenia produkcyjnego.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 577b026c950885524b726b09eb4df1ee7cf06837
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828689"
---
# <a name="end-a-production-order"></a><span data-ttu-id="23a7d-103">Kończenie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="23a7d-103">End a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="23a7d-104">W tej procedurze pokazano sposób kończenia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="23a7d-104">This procedure shows how to end a production order.</span></span> <span data-ttu-id="23a7d-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="23a7d-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="23a7d-106">Jest to ostatnia z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="23a7d-106">This is the final procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="end-a-production-order"></a><span data-ttu-id="23a7d-107">Kończenie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="23a7d-107">End a production order</span></span>
1. <span data-ttu-id="23a7d-108">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="23a7d-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="23a7d-109">Zaznacz zlecenie produkcyjne o stanie Zgłoszone jako gotowe.</span><span class="sxs-lookup"><span data-stu-id="23a7d-109">Select a production order that has the status Reported as finished.</span></span>  
2. <span data-ttu-id="23a7d-110">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="23a7d-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="23a7d-111">Kliknij opcję Koniec.</span><span class="sxs-lookup"><span data-stu-id="23a7d-111">Click End.</span></span>
    * <span data-ttu-id="23a7d-112">Na tej stronie możesz potwierdzić, że chcesz zakończyć zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="23a7d-112">On this page, you can confirm that you want to end the production order.</span></span>  
4. <span data-ttu-id="23a7d-113">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="23a7d-113">Click the General tab.</span></span>
5. <span data-ttu-id="23a7d-114">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="23a7d-114">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="23a7d-115">W polu Metoda odpadków wybierz opcję „Alokacja”.</span><span class="sxs-lookup"><span data-stu-id="23a7d-115">In the Scrap method field, select 'Allocation'.</span></span>
    * <span data-ttu-id="23a7d-116">Po wybraniu metody alokacji koszty z materiałów uznanych za odpadki są dodawane do wyrobów gotowych.</span><span class="sxs-lookup"><span data-stu-id="23a7d-116">When you select the Allocation method, costs from the scrapped materials are added to the finished goods.</span></span>  
7. <span data-ttu-id="23a7d-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="23a7d-117">Click OK.</span></span>

## <a name="validate-calculation-results"></a><span data-ttu-id="23a7d-118">Sprawdzanie poprawności wyników obliczeń</span><span class="sxs-lookup"><span data-stu-id="23a7d-118">Validate calculation results</span></span>
1. <span data-ttu-id="23a7d-119">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="23a7d-119">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="23a7d-120">Kliknij przycisk Wyświetl porównanie kosztów.</span><span class="sxs-lookup"><span data-stu-id="23a7d-120">Click View cost comparison.</span></span>
    * <span data-ttu-id="23a7d-121">Po zakończeniu zlecenia produkcyjnego można porównywać szacowany koszt własny ze zrealizowanym kosztem własnym w celu uzyskania obrazu odchyleń względem kosztów produkcji.</span><span class="sxs-lookup"><span data-stu-id="23a7d-121">After you have ended the production order, you can compare the estimated cost price against the realized cost price to get an overview of the production variances.</span></span>  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]