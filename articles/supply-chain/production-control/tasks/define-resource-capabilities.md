---
title: Definiowanie możliwości zasobu
description: Możliwości zasobu opisują, jakie operacje może wykonywać zasób.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 072991e7b3844ad3583b7d0c575d426299f74e9f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828713"
---
# <a name="define-resource-capabilities"></a><span data-ttu-id="01b85-103">Definiowanie możliwości zasobu</span><span class="sxs-lookup"><span data-stu-id="01b85-103">Define resource capabilities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01b85-104">Możliwości zasobu opisują, jakie operacje może wykonywać zasób.</span><span class="sxs-lookup"><span data-stu-id="01b85-104">Resource capabilities describe what operations resources can do.</span></span> <span data-ttu-id="01b85-105">Podczas planowania wymagania poszczególnych zadań i operacji są dopasowywane do możliwości dostępnych zasobów.</span><span class="sxs-lookup"><span data-stu-id="01b85-105">During scheduling, the requirements of each job and operation are matched against the capabilities of the available resources.</span></span> <span data-ttu-id="01b85-106">Ten przewodnik po zadaniach pomoże Ci utworzyć możliwość zasobu i przypisać ją do zasobu.</span><span class="sxs-lookup"><span data-stu-id="01b85-106">This task guide will help you create a resource capability and assign it to a resource.</span></span> <span data-ttu-id="01b85-107">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="01b85-107">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-resource-capability"></a><span data-ttu-id="01b85-108">Tworzenie możliwości zasobu</span><span class="sxs-lookup"><span data-stu-id="01b85-108">Create a resource capability</span></span>
1. <span data-ttu-id="01b85-109">Przejdź do okna Możliwości zasobu.</span><span class="sxs-lookup"><span data-stu-id="01b85-109">Go to Resource capabilities.</span></span>
2. <span data-ttu-id="01b85-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="01b85-110">Click New.</span></span>
3. <span data-ttu-id="01b85-111">W polu Możliwość wpisz identyfikator możliwości zasobu.</span><span class="sxs-lookup"><span data-stu-id="01b85-111">In the Capability field, type the ID of the resource capability.</span></span>
    * <span data-ttu-id="01b85-112">Dla danej operacji można użyć identyfikatora możliwości w celu określenia, że zasoby muszą używać tej możliwości do wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="01b85-112">For a given operation, you use the capability ID to specify that resources must have this capability to perform the operation.</span></span>  
4. <span data-ttu-id="01b85-113">W polu Opis wprowadź opis możliwości.</span><span class="sxs-lookup"><span data-stu-id="01b85-113">In the Description field, enter a description of the capability.</span></span>

## <a name="assign-capability-to-a-resource"></a><span data-ttu-id="01b85-114">Przypisywanie możliwości do zasobu</span><span class="sxs-lookup"><span data-stu-id="01b85-114">Assign capability to a resource</span></span>
1. <span data-ttu-id="01b85-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="01b85-115">Click Add.</span></span>
2. <span data-ttu-id="01b85-116">W polu Zasób wpisz identyfikator zasobu.</span><span class="sxs-lookup"><span data-stu-id="01b85-116">In the Resource field, type the ID of the resource.</span></span>
    * <span data-ttu-id="01b85-117">Możliwość zasobu można przypisać do jednego lub więcej zasobów.</span><span class="sxs-lookup"><span data-stu-id="01b85-117">A resource capability can be assigned to one or more resources.</span></span>  
3. <span data-ttu-id="01b85-118">W polu Data wygaśnięcia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="01b85-118">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="01b85-119">W tym polu można określić, że zasób posiada możliwość tylko przez określony czas.</span><span class="sxs-lookup"><span data-stu-id="01b85-119">You can use this field to specify that a resource has the capability for only a limited time.</span></span>  
4. <span data-ttu-id="01b85-120">W polu Priorytet wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="01b85-120">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="01b85-121">Podczas planowania zadań i operacji można określić, czy zasoby będą wybierane według priorytetu.</span><span class="sxs-lookup"><span data-stu-id="01b85-121">When you schedule jobs and operations, you can specify whether to select resources by priority.</span></span> <span data-ttu-id="01b85-122">Jeśli wybierzesz tę opcję, a do wskazanego dnia zadanie lub operacja może być wykonywana przez więcej niż jeden zasób, zostanie wybrany zasób, który ma najniższy priorytet w odniesieniu do wymaganej możliwości.</span><span class="sxs-lookup"><span data-stu-id="01b85-122">If you choose to do this, and more than one resource can perform the job or operation by the requested date, the resource that has the lowest priority with respect to the required capability is selected.</span></span>  
5. <span data-ttu-id="01b85-123">W polu Poziom wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="01b85-123">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="01b85-124">Po określeniu, że zadanie lub operacja wymaga określonej możliwości, można także określić minimalny wymagany poziom.</span><span class="sxs-lookup"><span data-stu-id="01b85-124">When you specify that a job or operation requires a particular capability, you can also specify the minimum level that is required.</span></span> <span data-ttu-id="01b85-125">Użyj poziomu możliwości w celu odróżnienia zasobów, które mogą wykonać to samo zadanie, ale z różną szybkością, siłą, rozmiarami itd.</span><span class="sxs-lookup"><span data-stu-id="01b85-125">Use the capability level to differentiate resources that can perform the same job, but at different speeds, strengths, sizes, and so on.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]