--- 
title: "Dezaktywowanie wersji przepływu produkcji"
description: "Gdy aktywna wersja przepływu produkcji nie jest już potrzebna, można ją dezaktywować."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8db4b2857e9a7c99ee6fa4ef397f7ed99335faba
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="92dda-103">Dezaktywowanie wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="92dda-103">Deactivate a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="92dda-104">Gdy aktywna wersja przepływu produkcji nie jest już potrzebna, można ją dezaktywować.</span><span class="sxs-lookup"><span data-stu-id="92dda-104">When an active production flow version is no longer needed, it can be deactivated.</span></span> <span data-ttu-id="92dda-105">Tej opcji należy używać tylko wtedy, jeśli wszystkie reguły i działania Kanban zakończyły się i nie będą ponownie uaktywniane.</span><span class="sxs-lookup"><span data-stu-id="92dda-105">You should only use this option if all kanban rules and activities have ended and will not be activated again.</span></span> <span data-ttu-id="92dda-106">Należy zauważyć, że data ważności wszystkich reguł Kanban odnoszących się do tej wersji przepływu produkcji będzie aktualizowana o bieżącą datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="92dda-106">Note that the expiry date of all kanban rules related to this production flow version will be updated with the current date and time.</span></span> 

<span data-ttu-id="92dda-107">Aby zmodyfikować aktywną wersję przepływu produkcji, należy rozważyć ustawienie daty ważności dla aktywnej wersji i utworzenie nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="92dda-107">To modify an active production flow version, consider setting an expiry date for the active version and create a new version.</span></span> <span data-ttu-id="92dda-108">To pozwoli kontynuować operacje produkcyjne, jednocześnie przygotowując nową wersję i powiązane reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="92dda-108">This will allow you to continue your production operations while preparing the new version and related kanban rules.</span></span> 

<span data-ttu-id="92dda-109">Aby aktywna wersja przepływu produkcji wygasała, należy ustawić datę ważności.</span><span class="sxs-lookup"><span data-stu-id="92dda-109">To expire an active production flow version, you need to set an expiry date.</span></span> <span data-ttu-id="92dda-110">W tym sensie dezaktywacja jest raczej wyjątkiem niż regułą.</span><span class="sxs-lookup"><span data-stu-id="92dda-110">In that sense, deactivation is more like an exception than a rule.</span></span> 

<span data-ttu-id="92dda-111">Do wykonania tej procedury jest potrzebny przepływ produkcji o wersji, która może być dezaktywowana.</span><span class="sxs-lookup"><span data-stu-id="92dda-111">For this procedure you need a production flow with a version that can be deactivated.</span></span> <span data-ttu-id="92dda-112">Nie próbuj tego w środowisku produkcyjnym, chyba że masz 100-procentową pewność, że wersja jest w pełni przestarzała.</span><span class="sxs-lookup"><span data-stu-id="92dda-112">Do not try this in a production environment unless you are 100% positive that the version is fully obsolete.</span></span>


## <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="92dda-113">Dezaktywowanie wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="92dda-113">Deactivate a production flow version</span></span>
1. <span data-ttu-id="92dda-114">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="92dda-114">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="92dda-115">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="92dda-115">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="92dda-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="92dda-116">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="92dda-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="92dda-117">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="92dda-118">Kliknij przycisk Dezaktywuj.</span><span class="sxs-lookup"><span data-stu-id="92dda-118">Click Deactivate.</span></span>
    * <span data-ttu-id="92dda-119">Nie kontynuuj, jeśli nie masz 100-procentowej pewności, że ta wersja przepływu produkcji jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="92dda-119">Do not proceed if you are not 100% positive that this production flow version is obsolete.</span></span> <span data-ttu-id="92dda-120">Kliknięcie przycisku Ok spowoduje unieważnienie wszystkich aktywnych reguł Kanban oraz natychmiastowe zatrzymanie wszystkich działań produkcji i uzupełniania w tej wersji przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="92dda-120">Clicking Ok will expire all active kanban rules and put an immediate stop to all production and replenishment activities of this production flow version.</span></span>  
6. <span data-ttu-id="92dda-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="92dda-121">Click OK.</span></span>


