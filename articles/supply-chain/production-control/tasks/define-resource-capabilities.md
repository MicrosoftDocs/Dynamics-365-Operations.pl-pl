--- 
title: "Definiowanie możliwości zasobu"
description: "Możliwości zasobu opisują, jakie operacje może wykonywać zasób."
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0940883d0e9edf56e61b5ecd817062aac5e0f8a6
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="define-resource-capabilities"></a><span data-ttu-id="8d787-103">Definiowanie możliwości zasobu</span><span class="sxs-lookup"><span data-stu-id="8d787-103">Define resource capabilities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8d787-104">Możliwości zasobu opisują, jakie operacje może wykonywać zasób.</span><span class="sxs-lookup"><span data-stu-id="8d787-104">Resource capabilities describe what operations resources can do.</span></span> <span data-ttu-id="8d787-105">Podczas planowania wymagania poszczególnych zadań i operacji są dopasowywane do możliwości dostępnych zasobów.</span><span class="sxs-lookup"><span data-stu-id="8d787-105">During scheduling, the requirements of each job and operation are matched against the capabilities of the available resources.</span></span> <span data-ttu-id="8d787-106">Ten przewodnik po zadaniach pomoże Ci utworzyć możliwość zasobu i przypisać ją do zasobu.</span><span class="sxs-lookup"><span data-stu-id="8d787-106">This task guide will help you create a resource capability and assign it to a resource.</span></span> <span data-ttu-id="8d787-107">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="8d787-107">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-resource-capability"></a><span data-ttu-id="8d787-108">Tworzenie możliwości zasobu</span><span class="sxs-lookup"><span data-stu-id="8d787-108">Create a resource capability</span></span>
1. <span data-ttu-id="8d787-109">Przejdź do okna Możliwości zasobu.</span><span class="sxs-lookup"><span data-stu-id="8d787-109">Go to Resource capabilities.</span></span>
2. <span data-ttu-id="8d787-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8d787-110">Click New.</span></span>
3. <span data-ttu-id="8d787-111">W polu Możliwość wpisz identyfikator możliwości zasobu.</span><span class="sxs-lookup"><span data-stu-id="8d787-111">In the Capability field, type the ID of the resource capability.</span></span>
    * <span data-ttu-id="8d787-112">Dla danej operacji można użyć identyfikatora możliwości w celu określenia, że zasoby muszą używać tej możliwości do wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="8d787-112">For a given operation, you use the capability ID to specify that resources must have this capability to perform the operation.</span></span>  
4. <span data-ttu-id="8d787-113">W polu Opis wprowadź opis możliwości.</span><span class="sxs-lookup"><span data-stu-id="8d787-113">In the Description field, enter a description of the capability.</span></span>

## <a name="assign-capability-to-a-resource"></a><span data-ttu-id="8d787-114">Przypisywanie możliwości do zasobu</span><span class="sxs-lookup"><span data-stu-id="8d787-114">Assign capability to a resource</span></span>
1. <span data-ttu-id="8d787-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8d787-115">Click Add.</span></span>
2. <span data-ttu-id="8d787-116">W polu Zasób wpisz identyfikator zasobu.</span><span class="sxs-lookup"><span data-stu-id="8d787-116">In the Resource field, type the ID of the resource.</span></span>
    * <span data-ttu-id="8d787-117">Możliwość zasobu można przypisać do jednego lub więcej zasobów.</span><span class="sxs-lookup"><span data-stu-id="8d787-117">A resource capability can be assigned to one or more resources.</span></span>  
3. <span data-ttu-id="8d787-118">W polu Data wygaśnięcia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="8d787-118">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="8d787-119">W tym polu można określić, że zasób posiada możliwość tylko przez określony czas.</span><span class="sxs-lookup"><span data-stu-id="8d787-119">You can use this field to specify that a resource has the capability for only a limited time.</span></span>  
4. <span data-ttu-id="8d787-120">W polu Priorytet wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="8d787-120">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="8d787-121">Podczas planowania zadań i operacji można określić, czy zasoby będą wybierane według priorytetu.</span><span class="sxs-lookup"><span data-stu-id="8d787-121">When you schedule jobs and operations, you can specify whether to select resources by priority.</span></span> <span data-ttu-id="8d787-122">Jeśli wybierzesz tę opcję, a do wskazanego dnia zadanie lub operacja może być wykonywana przez więcej niż jeden zasób, zostanie wybrany zasób, który ma najniższy priorytet w odniesieniu do wymaganej możliwości.</span><span class="sxs-lookup"><span data-stu-id="8d787-122">If you choose to do this, and more than one resource can perform the job or operation by the requested date, the resource that has the lowest priority with respect to the required capability is selected.</span></span>  
5. <span data-ttu-id="8d787-123">W polu Poziom wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="8d787-123">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="8d787-124">Po określeniu, że zadanie lub operacja wymaga określonej możliwości, można także określić minimalny wymagany poziom.</span><span class="sxs-lookup"><span data-stu-id="8d787-124">When you specify that a job or operation requires a particular capability, you can also specify the minimum level that is required.</span></span> <span data-ttu-id="8d787-125">Użyj poziomu możliwości w celu odróżnienia zasobów, które mogą wykonać to samo zadanie, ale z różną szybkością, siłą, rozmiarami itd.</span><span class="sxs-lookup"><span data-stu-id="8d787-125">Use the capability level to differentiate resources that can perform the same job, but at different speeds, strengths, sizes, and so on.</span></span>  


