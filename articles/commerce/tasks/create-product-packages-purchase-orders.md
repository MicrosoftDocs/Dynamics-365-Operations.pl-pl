---
title: Tworzenie pakietów produktów dla zamówień zakupu
description: Ta procedura zawiera instruktaż tworzenia pakietu produktów i użycia go w zamówieniu zakupu.
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d16c5c576ce6b35687fb7edab835d52f6f58e6a0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256980"
---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="9c31b-103">Tworzenie pakietów produktów dla zamówień zakupu</span><span class="sxs-lookup"><span data-stu-id="9c31b-103">Create product packages for purchase orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c31b-104">Ta procedura zawiera instruktaż tworzenia pakietu produktów i użycia go w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="9c31b-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="9c31b-105">Zamówienie zakupu zostanie użyte do utworzenia zamówienia na wstępnie zdefiniowany zestaw produktów.</span><span class="sxs-lookup"><span data-stu-id="9c31b-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="9c31b-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="9c31b-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="9c31b-107">Tworzenie pakietu produktów</span><span class="sxs-lookup"><span data-stu-id="9c31b-107">Create a product package</span></span>
1. <span data-ttu-id="9c31b-108">Wybierz kolejno opcje Retail i Commerce > Zarządzanie zapasami > Uzupełnienie > Pakiety produktów.</span><span class="sxs-lookup"><span data-stu-id="9c31b-108">Go to Retail and Commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="9c31b-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="9c31b-109">Click New.</span></span>
3. <span data-ttu-id="9c31b-110">W polu Numer paczki wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9c31b-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="9c31b-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="9c31b-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9c31b-112">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9c31b-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="9c31b-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9c31b-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="9c31b-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9c31b-114">Click Add.</span></span>
8. <span data-ttu-id="9c31b-115">W polu Numer towaru wpisz wartość „0160”.</span><span class="sxs-lookup"><span data-stu-id="9c31b-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="9c31b-116">W polu Rozmiar kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9c31b-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="9c31b-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9c31b-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="9c31b-118">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="9c31b-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="9c31b-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9c31b-119">Click Add.</span></span>
13. <span data-ttu-id="9c31b-120">W polu Numer towaru wpisz wartość „0160”.</span><span class="sxs-lookup"><span data-stu-id="9c31b-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="9c31b-121">W polu Numer wariantu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9c31b-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="9c31b-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9c31b-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="9c31b-123">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="9c31b-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="9c31b-124">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9c31b-124">Click Add.</span></span>
18. <span data-ttu-id="9c31b-125">W polu Numer towaru wpisz wartość „0175”.</span><span class="sxs-lookup"><span data-stu-id="9c31b-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="9c31b-126">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="9c31b-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="9c31b-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9c31b-127">Click Save.</span></span>
21. <span data-ttu-id="9c31b-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9c31b-128">Close the page.</span></span>

## <a name="add-package-to-purchase-order"></a><span data-ttu-id="9c31b-129">Dodawanie pakietu do zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="9c31b-129">Add package to purchase order</span></span>
1. <span data-ttu-id="9c31b-130">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="9c31b-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="9c31b-131">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="9c31b-131">Click New.</span></span>
3. <span data-ttu-id="9c31b-132">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9c31b-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9c31b-133">Na liście zaznacz tego samego dostawcę, dla którego wcześniej utworzono pakiet produktów, jeśli dostawca był wybrany.</span><span class="sxs-lookup"><span data-stu-id="9c31b-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="9c31b-134">Przełącz rozwinięcie sekcji Ogólne.</span><span class="sxs-lookup"><span data-stu-id="9c31b-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="9c31b-135">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9c31b-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="9c31b-136">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9c31b-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="9c31b-137">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9c31b-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="9c31b-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9c31b-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="9c31b-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9c31b-139">Click OK.</span></span>
11. <span data-ttu-id="9c31b-140">Przełącz rozwinięcie sekcji Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="9c31b-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="9c31b-141">Kliknij kartę Pakiety produktów.</span><span class="sxs-lookup"><span data-stu-id="9c31b-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="9c31b-142">Kliknij opcję Wiersz zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="9c31b-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="9c31b-143">Kliknij opcję Utwórz wiersze na podstawie paczki.</span><span class="sxs-lookup"><span data-stu-id="9c31b-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="9c31b-144">Na liście znajdź i zaznacz pakiet produktów utworzony w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="9c31b-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="9c31b-145">W polu Ilość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="9c31b-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="9c31b-146">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="9c31b-146">Click Create.</span></span>
18. <span data-ttu-id="9c31b-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9c31b-147">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]