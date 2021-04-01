---
title: Tworzenie nowej reguły Kanban przez duplikację istniejącej reguły Kanban
description: Ta procedura skupia się na tworzeniu duplikatu istniejącej reguły Kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b89fca4e55aa852bd127eb9b1bda07c0e5bcdc0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255140"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="27da4-103">Tworzenie nowej reguły Kanban przez duplikację istniejącej reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="27da4-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27da4-104">Ta procedura skupia się na tworzeniu duplikatu istniejącej reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="27da4-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="27da4-105">Jest to przydatne, jeśli chcesz utworzyć nowe reguły Kanban na podstawie istniejących reguł Kanban.</span><span class="sxs-lookup"><span data-stu-id="27da4-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="27da4-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="27da4-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="27da4-107">Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni produkcję z nowym przepływem lub regułą uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="27da4-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="27da4-108">Wybór reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="27da4-108">Select a kanban rule</span></span>
1. <span data-ttu-id="27da4-109">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="27da4-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="27da4-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="27da4-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="27da4-111">Wybierz regułę kanban 000017 dla produktu M0006.</span><span class="sxs-lookup"><span data-stu-id="27da4-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="27da4-112">Duplikowanie reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="27da4-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="27da4-113">Kliknij opcję Duplikuj regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="27da4-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="27da4-114">Podczas duplikowania reguły Kanban jest możliwość zmiany typu, dat, działań i wyboru produktu.</span><span class="sxs-lookup"><span data-stu-id="27da4-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="27da4-115">W kolejnym kroku zmienisz produkt w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="27da4-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="27da4-116">W polu Produkt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="27da4-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="27da4-117">Wybierz opcję M0007.</span><span class="sxs-lookup"><span data-stu-id="27da4-117">Select M0007.</span></span>  
3. <span data-ttu-id="27da4-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="27da4-118">Click OK.</span></span>
    * <span data-ttu-id="27da4-119">Należy zwrócić uwagę, że został utworzony duplikat reguły Kanban 000017.</span><span class="sxs-lookup"><span data-stu-id="27da4-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]