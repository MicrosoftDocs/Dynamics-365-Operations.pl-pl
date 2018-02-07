--- 
title: Konfigurowanie pracownika
description: "Ta procedura ilustruje sposób konfigurowania pracownika sieci sprzedaży jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży."
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 27b075cf1152f16fc4726b224e877eacb2f2572c
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---
# <a name="configure-a-worker"></a><span data-ttu-id="d2a02-103">Konfigurowanie pracownika</span><span class="sxs-lookup"><span data-stu-id="d2a02-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d2a02-104">Ta procedura ilustruje sposób konfigurowania pracownika sieci sprzedaży jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d2a02-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="d2a02-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="d2a02-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="d2a02-106">Tworzenie grupy sprzedaży prowizyjnej dla pracownika</span><span class="sxs-lookup"><span data-stu-id="d2a02-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="d2a02-107">Wybierz kolejno opcje Sprzedaż i marketing > Prowizje > Grupy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d2a02-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="d2a02-108">Pracowników można przypisać do jednej lub więcej grup sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d2a02-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="d2a02-109">W punkcie sprzedaży można wybierać dowolne grupy sprzedaży zawierające pracowników z książki adresowej sklepu.</span><span class="sxs-lookup"><span data-stu-id="d2a02-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="d2a02-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d2a02-110">Click New.</span></span>
3. <span data-ttu-id="d2a02-111">W polu Grupa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2a02-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="d2a02-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2a02-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d2a02-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d2a02-113">Click Save.</span></span>
6. <span data-ttu-id="d2a02-114">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="d2a02-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="d2a02-115">Kliknij opcję Przedstawiciel handlowy.</span><span class="sxs-lookup"><span data-stu-id="d2a02-115">Click Sales rep.</span></span>
    * <span data-ttu-id="d2a02-116">Grupa sprzedaży może zawierać więcej niż jednego pracownika.</span><span class="sxs-lookup"><span data-stu-id="d2a02-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="d2a02-117">Prowizje można dzielić między pracowników na podstawie tego, jak zdefiniowano udział w prowizji.</span><span class="sxs-lookup"><span data-stu-id="d2a02-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="d2a02-118">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2a02-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="d2a02-119">W polu Wielkość prowizji wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="d2a02-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="d2a02-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d2a02-120">Click Save.</span></span>
11. <span data-ttu-id="d2a02-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2a02-121">Close the page.</span></span>
12. <span data-ttu-id="d2a02-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2a02-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="d2a02-123">Przypisywanie pracowników do domyślnej grupy sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d2a02-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="d2a02-124">Wybierz kolejno opcje Handel detaliczny i inny > Pracownicy > Wszyscy pracownicy.</span><span class="sxs-lookup"><span data-stu-id="d2a02-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="d2a02-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d2a02-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d2a02-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d2a02-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d2a02-127">Kliknij kartę Detal.</span><span class="sxs-lookup"><span data-stu-id="d2a02-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="d2a02-128">Pracownika można przypisać do domyślnej grupy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d2a02-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="d2a02-129">Domyślna grupa sprzedaży zostanie automatycznie dodana do wierszy sprzedaży w punkcie sprzedaży, jeśli ta opcja jest włączona w profilu funkcji sklepu.</span><span class="sxs-lookup"><span data-stu-id="d2a02-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="d2a02-130">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="d2a02-130">Click Edit.</span></span>
6. <span data-ttu-id="d2a02-131">W polu Grupa domyślna wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2a02-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="d2a02-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d2a02-132">Click Save.</span></span>


