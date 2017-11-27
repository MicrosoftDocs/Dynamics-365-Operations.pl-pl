--- 
title: "Tworzenie pakietów produktów dla zamówień zakupu"
description: "Ta procedura zawiera instruktaż tworzenia pakietu produktów i użycia go w zamówieniu zakupu."
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 9d3ea8702c79d8aa6bb7cf7caa922277697610fa
ms.contentlocale: pl-pl
ms.lasthandoff: 11/14/2017

---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="ca8e1-103">Tworzenie pakietów produktów dla zamówień zakupu</span><span class="sxs-lookup"><span data-stu-id="ca8e1-103">Create product packages for purchase orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="ca8e1-104">Ta procedura zawiera instruktaż tworzenia pakietu produktów i użycia go w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="ca8e1-105">Zamówienie zakupu zostanie użyte do utworzenia zamówienia na wstępnie zdefiniowany zestaw produktów.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="ca8e1-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="ca8e1-107">Tworzenie pakietu produktów</span><span class="sxs-lookup"><span data-stu-id="ca8e1-107">Create a product package</span></span>
1. <span data-ttu-id="ca8e1-108">Wybierz kolejno opcje Handel detaliczny i inny > Zarządzanie zapasami > Uzupełnienie > Pakiety produktów.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-108">Go to Retail and commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="ca8e1-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-109">Click New.</span></span>
3. <span data-ttu-id="ca8e1-110">W polu Numer paczki wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="ca8e1-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ca8e1-112">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ca8e1-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="ca8e1-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-114">Click Add.</span></span>
8. <span data-ttu-id="ca8e1-115">W polu Numer towaru wpisz wartość „0160”.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="ca8e1-116">W polu Rozmiar kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="ca8e1-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="ca8e1-118">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="ca8e1-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-119">Click Add.</span></span>
13. <span data-ttu-id="ca8e1-120">W polu Numer towaru wpisz wartość „0160”.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="ca8e1-121">W polu Numer wariantu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="ca8e1-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="ca8e1-123">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="ca8e1-124">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-124">Click Add.</span></span>
18. <span data-ttu-id="ca8e1-125">W polu Numer towaru wpisz wartość „0175”.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="ca8e1-126">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="ca8e1-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-127">Click Save.</span></span>
21. <span data-ttu-id="ca8e1-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-128">Close the page.</span></span>

## <a name="add-package-to-purchase-order"></a><span data-ttu-id="ca8e1-129">Dodawanie pakietu do zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="ca8e1-129">Add package to purchase order</span></span>
1. <span data-ttu-id="ca8e1-130">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="ca8e1-131">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-131">Click New.</span></span>
3. <span data-ttu-id="ca8e1-132">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ca8e1-133">Na liście zaznacz tego samego dostawcę, dla którego wcześniej utworzono pakiet produktów, jeśli dostawca był wybrany.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="ca8e1-134">Przełącz rozwinięcie sekcji Ogólne.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="ca8e1-135">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ca8e1-136">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ca8e1-137">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="ca8e1-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="ca8e1-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-139">Click OK.</span></span>
11. <span data-ttu-id="ca8e1-140">Przełącz rozwinięcie sekcji Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="ca8e1-141">Kliknij kartę Pakiety produktów.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="ca8e1-142">Kliknij opcję Wiersz zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="ca8e1-143">Kliknij opcję Utwórz wiersze na podstawie paczki.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="ca8e1-144">Na liście znajdź i zaznacz pakiet produktów utworzony w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="ca8e1-145">W polu Ilość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="ca8e1-146">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-146">Click Create.</span></span>
18. <span data-ttu-id="ca8e1-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ca8e1-147">Click Save.</span></span>


