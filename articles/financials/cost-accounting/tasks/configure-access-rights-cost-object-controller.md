--- 
title: "Konfigurowanie praw dostępu kontrolera obiektów kosztów"
description: "Ta procedura umożliwia skonfigurowanie uprawnień dostępu kontrolerowi obiektów kosztów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b0647e1ec55d23607d07f38105e42af498ad1174
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="9c54a-103">Konfigurowanie praw dostępu kontrolera obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="9c54a-103">Configure access rights for a cost object controller</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9c54a-104">Ta procedura umożliwia skonfigurowanie uprawnień dostępu kontrolerowi obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c54a-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="9c54a-105">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="9c54a-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="9c54a-106">Przypisywanie roli kontrolera obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="9c54a-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="9c54a-107">Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="9c54a-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="9c54a-108">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="9c54a-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="9c54a-109">Na przykład wyfiltruj według pola Nazwa użytkownika z wartością „alicia”.</span><span class="sxs-lookup"><span data-stu-id="9c54a-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="9c54a-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9c54a-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9c54a-111">Kliknij opcję Przypisz role.</span><span class="sxs-lookup"><span data-stu-id="9c54a-111">Click Assign roles.</span></span>
5. <span data-ttu-id="9c54a-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9c54a-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="9c54a-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9c54a-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="9c54a-114">Włączanie zabezpieczeń listy dostępu</span><span class="sxs-lookup"><span data-stu-id="9c54a-114">Enable access list security</span></span>
1. <span data-ttu-id="9c54a-115">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.</span><span class="sxs-lookup"><span data-stu-id="9c54a-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="9c54a-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9c54a-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9c54a-117">Wybierz opcję Organizacja.</span><span class="sxs-lookup"><span data-stu-id="9c54a-117">Select Organization.</span></span>  
3. <span data-ttu-id="9c54a-118">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="9c54a-118">Click Edit.</span></span>
4. <span data-ttu-id="9c54a-119">W polu Hierarchia list dostępu wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="9c54a-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="9c54a-120">Kliknij opcję Wyświetl hierarchię.</span><span class="sxs-lookup"><span data-stu-id="9c54a-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="9c54a-121">Przypisywanie praw dostępu użytkownikowi</span><span class="sxs-lookup"><span data-stu-id="9c54a-121">Assign access rights to user</span></span>
1. <span data-ttu-id="9c54a-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="9c54a-122">Click New.</span></span>
2. <span data-ttu-id="9c54a-123">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="9c54a-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="9c54a-124">W polu Identyfikator użytkownika wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9c54a-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="9c54a-125">Wybierz opcję Administrator.</span><span class="sxs-lookup"><span data-stu-id="9c54a-125">Select Admin.</span></span>  
4. <span data-ttu-id="9c54a-126">W drzewie zaznacz element „Organizacja\Dyrektor generalny\Dyrektor finansowy\FIM”.</span><span class="sxs-lookup"><span data-stu-id="9c54a-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="9c54a-127">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="9c54a-127">Click New.</span></span>
6. <span data-ttu-id="9c54a-128">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="9c54a-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="9c54a-129">W polu Identyfikator użytkownika wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9c54a-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="9c54a-130">Wybierz opcję Alicia.</span><span class="sxs-lookup"><span data-stu-id="9c54a-130">Select Alicia.</span></span>  
8. <span data-ttu-id="9c54a-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9c54a-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="9c54a-132">Włączanie praw dostępu w module Rachunek kosztów</span><span class="sxs-lookup"><span data-stu-id="9c54a-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="9c54a-133">Wybierz kolejno opcje Rachunek kosztów > Ustawienia > Parametry.</span><span class="sxs-lookup"><span data-stu-id="9c54a-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="9c54a-134">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="9c54a-134">Click the General tab.</span></span>
3. <span data-ttu-id="9c54a-135">Zaznacz opcję Tak w polu Włącz dostęp z prawem do wyświetlania elementów członkowskich wymiaru obiektu kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c54a-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="9c54a-136">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9c54a-136">Click Save.</span></span>
5. <span data-ttu-id="9c54a-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9c54a-137">Close the page.</span></span>
6. <span data-ttu-id="9c54a-138">Wybierz kolejno opcje Rachunek kosztów > Ustawienia > Konfiguracja obszaru roboczego Kontrola kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c54a-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="9c54a-139">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="9c54a-139">Click Edit.</span></span>
8. <span data-ttu-id="9c54a-140">W polu Opublikowane wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="9c54a-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="9c54a-141">Jeśli wybierzesz opcję Tak, raporty w obszarze roboczym Kontrola kosztów będą mogły być wyświetlane przez użytkownika przypisanego do jednej z następujących czterech ról: Menedżer rachunku kosztów, Księgowy kosztów, Księgowy rachunku kosztów i Kontroler obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c54a-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="9c54a-142">Jeśli wybierzesz opcję Nie, raporty będą mogły być wyświetlane tylko przez użytkowników przypisanych do jednej z następujących czterech ról: Menedżer rachunku kosztów, Księgowy kosztów i Księgowy rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c54a-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="9c54a-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9c54a-143">Click Save.</span></span>


