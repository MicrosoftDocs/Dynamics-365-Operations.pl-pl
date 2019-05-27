---
title: Konfigurowanie pracownika
description: Ta procedura ilustruje sposób konfigurowania pracownika sieci sprzedaży jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży.
author: jblucher
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 797640b487884fc487582addea274007e4ba7a7d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563627"
---
# <a name="configure-a-worker"></a><span data-ttu-id="815ac-103">Konfigurowanie pracownika</span><span class="sxs-lookup"><span data-stu-id="815ac-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="815ac-104">Ta procedura ilustruje sposób konfigurowania pracownika sieci sprzedaży jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="815ac-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="815ac-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="815ac-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="815ac-106">Tworzenie grupy sprzedaży prowizyjnej dla pracownika</span><span class="sxs-lookup"><span data-stu-id="815ac-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="815ac-107">Wybierz kolejno opcje Sprzedaż i marketing > Prowizje > Grupy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="815ac-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="815ac-108">Pracowników można przypisać do jednej lub więcej grup sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="815ac-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="815ac-109">W punkcie sprzedaży można wybierać dowolne grupy sprzedaży zawierające pracowników z książki adresowej sklepu.</span><span class="sxs-lookup"><span data-stu-id="815ac-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="815ac-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="815ac-110">Click New.</span></span>
3. <span data-ttu-id="815ac-111">W polu Grupa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="815ac-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="815ac-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="815ac-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="815ac-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="815ac-113">Click Save.</span></span>
6. <span data-ttu-id="815ac-114">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="815ac-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="815ac-115">Kliknij opcję Przedstawiciel handlowy.</span><span class="sxs-lookup"><span data-stu-id="815ac-115">Click Sales rep.</span></span>
    * <span data-ttu-id="815ac-116">Grupa sprzedaży może zawierać więcej niż jednego pracownika.</span><span class="sxs-lookup"><span data-stu-id="815ac-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="815ac-117">Prowizje można dzielić między pracowników na podstawie tego, jak zdefiniowano udział w prowizji.</span><span class="sxs-lookup"><span data-stu-id="815ac-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="815ac-118">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="815ac-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="815ac-119">W polu Wielkość prowizji wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="815ac-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="815ac-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="815ac-120">Click Save.</span></span>
11. <span data-ttu-id="815ac-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="815ac-121">Close the page.</span></span>
12. <span data-ttu-id="815ac-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="815ac-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="815ac-123">Przypisywanie pracowników do domyślnej grupy sprzedaży</span><span class="sxs-lookup"><span data-stu-id="815ac-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="815ac-124">Wybierz kolejno opcje Handel detaliczny i inny > Pracownicy > Wszyscy pracownicy.</span><span class="sxs-lookup"><span data-stu-id="815ac-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="815ac-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="815ac-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="815ac-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="815ac-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="815ac-127">Kliknij kartę Detal.</span><span class="sxs-lookup"><span data-stu-id="815ac-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="815ac-128">Pracownika można przypisać do domyślnej grupy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="815ac-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="815ac-129">Domyślna grupa sprzedaży zostanie automatycznie dodana do wierszy sprzedaży w punkcie sprzedaży, jeśli ta opcja jest włączona w profilu funkcji sklepu.</span><span class="sxs-lookup"><span data-stu-id="815ac-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="815ac-130">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="815ac-130">Click Edit.</span></span>
6. <span data-ttu-id="815ac-131">W polu Grupa domyślna wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="815ac-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="815ac-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="815ac-132">Click Save.</span></span>

