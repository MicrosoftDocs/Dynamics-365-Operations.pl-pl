--- 
title: "Tworzenie zasad zakupów"
description: "W tej procedurze pokazano sposób tworzenia zasad zakupów dopasowanych do procesów biznesowych w obszarze zakupów."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b3a66443394f5bfbe51b6685513281025d68fd
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-purchasing-policies"></a><span data-ttu-id="662f8-103">Tworzenie zasad zakupów</span><span class="sxs-lookup"><span data-stu-id="662f8-103">Create purchasing policies</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="662f8-104">W tej procedurze pokazano sposób tworzenia zasad zakupów dopasowanych do procesów biznesowych w obszarze zakupów.</span><span class="sxs-lookup"><span data-stu-id="662f8-104">This procedure shows you how to create purchasing policies to align with your business processes for purchasing.</span></span> <span data-ttu-id="662f8-105">Zanim będzie można utworzyć zasady dotyczące zakupów, należy skonfigurować parametry zasad zakupów, .</span><span class="sxs-lookup"><span data-stu-id="662f8-105">Before you can create purchasing policies, you must set up the purchasing policy parameters.</span></span> <span data-ttu-id="662f8-106">Można tworzyć, modyfikować i wycofywać zasady zakupów, ale nie można usunąć zasady zakupów.</span><span class="sxs-lookup"><span data-stu-id="662f8-106">It’s possible to create, modify, and retire a purchasing policy, but you can’t delete a purchasing policy.</span></span> <span data-ttu-id="662f8-107">Tę procedurę zazwyczaj wykonuje kierownik ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="662f8-107">This procedure would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="662f8-108">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="662f8-108">You can use this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-policy-parameters"></a><span data-ttu-id="662f8-109">Ustawianie parametrów zasad</span><span class="sxs-lookup"><span data-stu-id="662f8-109">Set up policy parameters</span></span>
1. <span data-ttu-id="662f8-110">Przejdź do okna Zasady zakupów.</span><span class="sxs-lookup"><span data-stu-id="662f8-110">Go to Purchasing policies.</span></span>
2. <span data-ttu-id="662f8-111">Kliknij opcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="662f8-111">Click Parameters.</span></span>
    * <span data-ttu-id="662f8-112">Reguły pierwszeństwa zasad dotyczą różnych poziomów w organizacji.</span><span class="sxs-lookup"><span data-stu-id="662f8-112">Policy precedence rules apply to different levels in your organization.</span></span> <span data-ttu-id="662f8-113">Wyświetlane jednostki organizacyjne zależą od hierarchii organizacyjnej oraz od tego, na których poziomach w hierarchii przypisano cel Wewnętrzna kontrola zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="662f8-113">The organizational units that are shown depend on your organizational hierarchy, and on which levels in the hierarchy have been assigned the purpose of Procurement internal control.</span></span> <span data-ttu-id="662f8-114">Na przykład w organizacji mogą istnieć firmy, centra kosztów, regiony i działy, ale tylko niektóre z nich mogą mieć w hierarchii cel Wewnętrzna kontrola zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="662f8-114">For example, your organization might have legal entities, cost centers, regions, and departments, but it may be that only some of these have a hierarchy purpose of Procurement internal control.</span></span> <span data-ttu-id="662f8-115">Domyślnie jest dostępna organizacja typu Firma.</span><span class="sxs-lookup"><span data-stu-id="662f8-115">As a default, the organization of type Company is available.</span></span>  
3. <span data-ttu-id="662f8-116">Kliknij kartę Parametry typu reguły.</span><span class="sxs-lookup"><span data-stu-id="662f8-116">Click the Policy rule type parameters tab.</span></span>
4. <span data-ttu-id="662f8-117">W drzewie zaznacz element „Zasady zakupów\Reguła kontroli zapotrzebowania na zakup”.</span><span class="sxs-lookup"><span data-stu-id="662f8-117">In the tree, select 'Purchasing policy\Purchase requisition control rule'.</span></span>
    * <span data-ttu-id="662f8-118">Należy zdefiniować kolejność pierwszeństwa dla stosowania zasad na poziomie zasad.</span><span class="sxs-lookup"><span data-stu-id="662f8-118">You define the order of precedence for policy resolution at the policy level.</span></span> <span data-ttu-id="662f8-119">Jednak w przypadku niektórych typów zasad, można zastąpić kolejność pierwszeństwa dla poszczególnych typów reguł dotyczących zasad.</span><span class="sxs-lookup"><span data-stu-id="662f8-119">However, for some policy types, you can override the order of precedence for individual policy rule types.</span></span> <span data-ttu-id="662f8-120">Na przykład można zdefiniować pierwszeństwo zasad zakupów w następującej kolejności: centrum kosztów, dział, firma.</span><span class="sxs-lookup"><span data-stu-id="662f8-120">For example, you might define the order of precedence for purchasing policies to be: cost center, department, company.</span></span> <span data-ttu-id="662f8-121">Jednak dla reguły dotyczącej katalogów chcesz, aby pierwszeństwo było następujące: dział, centrum kosztów, firma.</span><span class="sxs-lookup"><span data-stu-id="662f8-121">For the catalog policy rule, you might want the order of precedence to be: department, cost center, company.</span></span> <span data-ttu-id="662f8-122">Istnieje możliwość zmiany pierwszeństwa dla reguły dotyczącej katalogu.</span><span class="sxs-lookup"><span data-stu-id="662f8-122">You can change the order of precedence for the Catalog policy rule.</span></span> <span data-ttu-id="662f8-123">Gdy pracownik tworzy zapotrzebowanie, wyświetlany katalog zależy od zasad, które są skojarzone najpierw z działem pracownika, następnie z centrum kosztów, a na końcu z firmą.</span><span class="sxs-lookup"><span data-stu-id="662f8-123">When a worker creates a requisition, the catalog that is displayed is determined by the policies that are associated with the worker’s department, then their cost center, and then their company.</span></span>  
    * <span data-ttu-id="662f8-124">Jeśli jest wyświetlany więcej niż jeden poziom organizacyjny, można strzałkami w górę/w dół ustawić pierwszeństwo dla reguły kontroli zapotrzebowania na zakup.</span><span class="sxs-lookup"><span data-stu-id="662f8-124">If there’s more than one organizational level listed, you can use the Up/Down arrows to set the order of precedence for the Purchase requisition control rule.</span></span>  
5. <span data-ttu-id="662f8-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="662f8-125">Close the page.</span></span>

## <a name="create-a-new-policy"></a><span data-ttu-id="662f8-126">Utwórz nowe zasady</span><span class="sxs-lookup"><span data-stu-id="662f8-126">Create a new policy</span></span>
1. <span data-ttu-id="662f8-127">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="662f8-127">Click New.</span></span>
2. <span data-ttu-id="662f8-128">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="662f8-128">In the Name field, type a value.</span></span>
3. <span data-ttu-id="662f8-129">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="662f8-129">In the Description field, type a value.</span></span>
    * <span data-ttu-id="662f8-130">Pojedyncza zasada zakupów może stosować się tylko dla jednej hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="662f8-130">A single purchasing policy can only apply to one organization hierarchy.</span></span> <span data-ttu-id="662f8-131">Na przykład możesz mieć jedną hierarchię o nazwie „Położenie geograficzne” i jedną o nazwie „dział” i dla każdej ustawić inną zasadę zakupów.</span><span class="sxs-lookup"><span data-stu-id="662f8-131">For example, you could have one hierarchy called “Geographic” and one called “Department”, and have a different purchasing policy for each.</span></span>  
    * <span data-ttu-id="662f8-132">Wybierz organizację, do której ma być stosowana zasada.</span><span class="sxs-lookup"><span data-stu-id="662f8-132">Select an organization that the policy should apply to.</span></span>  
4. <span data-ttu-id="662f8-133">Kliknij strzałkę, aby dodać wybraną organizację.</span><span class="sxs-lookup"><span data-stu-id="662f8-133">Click the arrow to add the selected organization.</span></span>
    * <span data-ttu-id="662f8-134">Można powtórzyć ten proces, aby dodać więcej organizacji.</span><span class="sxs-lookup"><span data-stu-id="662f8-134">You can repeat this process to add more organizations.</span></span>  

## <a name="add-a-policy-rule"></a><span data-ttu-id="662f8-135">Dodawanie reguły</span><span class="sxs-lookup"><span data-stu-id="662f8-135">Add a policy rule</span></span>
1. <span data-ttu-id="662f8-136">Na liście Typ reguły zaznacz element Reguła celu zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="662f8-136">In the Policy rule type list, select Requisition purpose rule.</span></span>
    * <span data-ttu-id="662f8-137">Utworzysz regułę, która ustawia domyślny cel zapotrzebowania na typ Zużycie, ale za to pozwala wybrać typ uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="662f8-137">You’ll create a rule that sets the default requisition purpose to type Consumption but allows the Replenishment type to be selected instead.</span></span>  
2. <span data-ttu-id="662f8-138">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="662f8-138">Click Create policy rule.</span></span>
3. <span data-ttu-id="662f8-139">W polu Zezwalaj na zastępowanie ręczne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="662f8-139">Select Yes in the Allow manual override field.</span></span>
4. <span data-ttu-id="662f8-140">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="662f8-140">Click Close.</span></span>
    * <span data-ttu-id="662f8-141">Teraz można skonfigurować inne reguły dla zasady zakupów.</span><span class="sxs-lookup"><span data-stu-id="662f8-141">Now you can set up other policy rules for the purchasing policy.</span></span>   <span data-ttu-id="662f8-142">Należy zauważyć, że typ reguły nie może określać nakładających się reguł, które są aktywne w tym samym czasie w jednej zasadzie zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="662f8-142">Note that a Policy rule type cannot have overlapping rules that are active at the same time within a single procurement policy.</span></span>  
5. <span data-ttu-id="662f8-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="662f8-143">Close the page.</span></span>
6. <span data-ttu-id="662f8-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="662f8-144">Close the page.</span></span>


