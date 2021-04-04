---
title: Konfigurowanie pracownika
description: Ta procedura ilustruje sposób konfigurowania pracownika jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży.
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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 120705200f223e31c72290059e8634e7db6f9fdd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232624"
---
# <a name="configure-a-worker"></a><span data-ttu-id="6a821-103">Konfigurowanie pracownika</span><span class="sxs-lookup"><span data-stu-id="6a821-103">Configure a worker</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6a821-104">Ta procedura ilustruje sposób konfigurowania pracownika jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6a821-104">This procedure demonstrates how to configure a worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="6a821-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="6a821-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="6a821-106">Tworzenie grupy sprzedaży prowizyjnej dla pracownika</span><span class="sxs-lookup"><span data-stu-id="6a821-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="6a821-107">Wybierz kolejno opcje Sprzedaż i marketing > Prowizje > Grupy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6a821-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="6a821-108">Pracowników można przypisać do jednej lub więcej grup sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6a821-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="6a821-109">W punkcie sprzedaży można wybierać dowolne grupy sprzedaży zawierające pracowników z książki adresowej sklepu.</span><span class="sxs-lookup"><span data-stu-id="6a821-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="6a821-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6a821-110">Click New.</span></span>
3. <span data-ttu-id="6a821-111">W polu Grupa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a821-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="6a821-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a821-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="6a821-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6a821-113">Click Save.</span></span>
6. <span data-ttu-id="6a821-114">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="6a821-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="6a821-115">Kliknij opcję Przedstawiciel handlowy.</span><span class="sxs-lookup"><span data-stu-id="6a821-115">Click Sales rep.</span></span>
    * <span data-ttu-id="6a821-116">Grupa sprzedaży może zawierać więcej niż jednego pracownika.</span><span class="sxs-lookup"><span data-stu-id="6a821-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="6a821-117">Prowizje można dzielić między pracowników na podstawie tego, jak zdefiniowano udział w prowizji.</span><span class="sxs-lookup"><span data-stu-id="6a821-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="6a821-118">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a821-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="6a821-119">W polu Wielkość prowizji wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="6a821-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="6a821-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6a821-120">Click Save.</span></span>
11. <span data-ttu-id="6a821-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6a821-121">Close the page.</span></span>
12. <span data-ttu-id="6a821-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6a821-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="6a821-123">Przypisywanie pracowników do domyślnej grupy sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6a821-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="6a821-124">Wybierz kolejno opcje Handel detaliczny i inny > Pracownicy > Wszyscy pracownicy.</span><span class="sxs-lookup"><span data-stu-id="6a821-124">Go to Retail and Commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="6a821-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6a821-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="6a821-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6a821-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="6a821-127">Kliknij kartę Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a821-127">Click the Commerce tab.</span></span>
    * <span data-ttu-id="6a821-128">Pracownika można przypisać do domyślnej grupy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6a821-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="6a821-129">Domyślna grupa sprzedaży zostanie automatycznie dodana do wierszy sprzedaży w punkcie sprzedaży, jeśli ta opcja jest włączona w profilu funkcji sklepu.</span><span class="sxs-lookup"><span data-stu-id="6a821-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="6a821-130">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="6a821-130">Click Edit.</span></span>
6. <span data-ttu-id="6a821-131">W polu Grupa domyślna wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a821-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="6a821-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6a821-132">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]