---
title: Konfigurowanie praw dostępu kontrolera obiektów kosztów
description: Ta procedura umożliwia skonfigurowanie uprawnień dostępu kontrolerowi obiektów kosztów.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b7356706ea80c97fdf5b73faf32134a4aebacbb
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179412"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="25db8-103">Konfigurowanie praw dostępu kontrolera obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="25db8-103">Configure access rights for a cost object controller</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25db8-104">Ta procedura umożliwia skonfigurowanie uprawnień dostępu kontrolerowi obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="25db8-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="25db8-105">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="25db8-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="25db8-106">Przypisywanie roli kontrolera obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="25db8-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="25db8-107">Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="25db8-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="25db8-108">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="25db8-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="25db8-109">Na przykład wyfiltruj według pola Nazwa użytkownika z wartością „alicia”.</span><span class="sxs-lookup"><span data-stu-id="25db8-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="25db8-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="25db8-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="25db8-111">Kliknij opcję Przypisz role.</span><span class="sxs-lookup"><span data-stu-id="25db8-111">Click Assign roles.</span></span>
5. <span data-ttu-id="25db8-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="25db8-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="25db8-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="25db8-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="25db8-114">Włączanie zabezpieczeń listy dostępu</span><span class="sxs-lookup"><span data-stu-id="25db8-114">Enable access list security</span></span>
1. <span data-ttu-id="25db8-115">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.</span><span class="sxs-lookup"><span data-stu-id="25db8-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="25db8-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="25db8-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="25db8-117">Wybierz opcję Organizacja.</span><span class="sxs-lookup"><span data-stu-id="25db8-117">Select Organization.</span></span>  
3. <span data-ttu-id="25db8-118">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="25db8-118">Click Edit.</span></span>
4. <span data-ttu-id="25db8-119">W polu Hierarchia list dostępu wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="25db8-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="25db8-120">Kliknij opcję Wyświetl hierarchię.</span><span class="sxs-lookup"><span data-stu-id="25db8-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="25db8-121">Przypisywanie praw dostępu użytkownikowi</span><span class="sxs-lookup"><span data-stu-id="25db8-121">Assign access rights to user</span></span>
1. <span data-ttu-id="25db8-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="25db8-122">Click New.</span></span>
2. <span data-ttu-id="25db8-123">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="25db8-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="25db8-124">W polu Identyfikator użytkownika wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="25db8-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="25db8-125">Wybierz opcję Administrator.</span><span class="sxs-lookup"><span data-stu-id="25db8-125">Select Admin.</span></span>  
4. <span data-ttu-id="25db8-126">W drzewie zaznacz element „Organizacja\Dyrektor generalny\Dyrektor finansowy\FIM”.</span><span class="sxs-lookup"><span data-stu-id="25db8-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="25db8-127">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="25db8-127">Click New.</span></span>
6. <span data-ttu-id="25db8-128">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="25db8-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="25db8-129">W polu Identyfikator użytkownika wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="25db8-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="25db8-130">Wybierz opcję Alicia.</span><span class="sxs-lookup"><span data-stu-id="25db8-130">Select Alicia.</span></span>  
8. <span data-ttu-id="25db8-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="25db8-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="25db8-132">Włączanie praw dostępu w module Rachunek kosztów</span><span class="sxs-lookup"><span data-stu-id="25db8-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="25db8-133">Wybierz kolejno opcje Rachunek kosztów > Ustawienia > Parametry.</span><span class="sxs-lookup"><span data-stu-id="25db8-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="25db8-134">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="25db8-134">Click the General tab.</span></span>
3. <span data-ttu-id="25db8-135">Zaznacz opcję Tak w polu Włącz dostęp z prawem do wyświetlania elementów członkowskich wymiaru obiektu kosztów.</span><span class="sxs-lookup"><span data-stu-id="25db8-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="25db8-136">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="25db8-136">Click Save.</span></span>
5. <span data-ttu-id="25db8-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="25db8-137">Close the page.</span></span>
6. <span data-ttu-id="25db8-138">Wybierz kolejno opcje Rachunek kosztów > Ustawienia > Konfiguracja obszaru roboczego Kontrola kosztów.</span><span class="sxs-lookup"><span data-stu-id="25db8-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="25db8-139">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="25db8-139">Click Edit.</span></span>
8. <span data-ttu-id="25db8-140">W polu Opublikowane wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="25db8-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="25db8-141">Jeśli wybierzesz opcję Tak, raporty w obszarze roboczym Kontrola kosztów będą mogły być wyświetlane przez użytkownika przypisanego do jednej z następujących czterech ról: Menedżer rachunku kosztów, Księgowy kosztów, Księgowy rachunku kosztów i Kontroler obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="25db8-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="25db8-142">Jeśli wybierzesz opcję Nie, raporty będą mogły być wyświetlane tylko przez użytkowników przypisanych do jednej z następujących czterech ról: Menedżer rachunku kosztów, Księgowy kosztów i Księgowy rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="25db8-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="25db8-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="25db8-143">Click Save.</span></span>

