--- 
title: "Tworzenie produktu głównego"
description: "Utwórz produkt główny dla wstępnie zdefiniowanych wariantów."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 6e34f7c630e872468d888938e0f1aa57f3f0d4c4
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-product-master"></a><span data-ttu-id="7ea2f-103">Tworzenie produktu głównego</span><span class="sxs-lookup"><span data-stu-id="7ea2f-103">Create a product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7ea2f-104">Utwórz produkt główny dla wstępnie zdefiniowanych wariantów.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="7ea2f-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7ea2f-106">Ta procedura jest przeznaczona dla projektanta produktów.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="7ea2f-107">Tworzenie nowego produktu głównego</span><span class="sxs-lookup"><span data-stu-id="7ea2f-107">Create a new product master</span></span>
1. <span data-ttu-id="7ea2f-108">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkty > Produkty główne.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-108">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="7ea2f-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-109">Click New.</span></span>
3. <span data-ttu-id="7ea2f-110">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="7ea2f-111">Numer musi być unikatowy.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-111">The number must be unique.</span></span> <span data-ttu-id="7ea2f-112">Dla pola Numer produktu można określić sekwencję numeracji.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-112">A number sequence can be set for the Product number field.</span></span> <span data-ttu-id="7ea2f-113">W takim przypadku użytkownik nie musi wprowadzać wartość.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-113">In this case, the user doesn't have to enter a value.</span></span>  
4. <span data-ttu-id="7ea2f-114">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="7ea2f-115">Wprowadź opisową nazwę produktu.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-115">Enter a descriptive product name.</span></span> <span data-ttu-id="7ea2f-116">Domyślna jest to nazwa wyszukiwania, ale użytkownik może to zmienić.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-116">The value defaults to the search name, but this can be changed by the user.</span></span>  
5. <span data-ttu-id="7ea2f-117">W polu Grupa wymiarów produktu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-117">In the Product dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7ea2f-118">Grupa wymiarów produktu określa, który z 4 wymiarów produktu może być używane do tworzenia wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="7ea2f-119">W tym przykładzie użyto grupy z kolorem i rozmiarem.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-119">This example uses a group with color and size.</span></span>  
6. <span data-ttu-id="7ea2f-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="7ea2f-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7ea2f-122">Domyślną technologią konfiguracji jest Wstępnie zdefiniowany wariant.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-122">The default configuration technology is Predefined variant.</span></span> <span data-ttu-id="7ea2f-123">Będzie ona używana w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-123">This will be used for this example.</span></span>  
8. <span data-ttu-id="7ea2f-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-124">Click OK.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="7ea2f-125">Wybór grup wymiarów produktów</span><span class="sxs-lookup"><span data-stu-id="7ea2f-125">Select product dimension groups</span></span>
1. <span data-ttu-id="7ea2f-126">W polu Grupa kolorów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-126">In the Color group field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="7ea2f-127">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7ea2f-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7ea2f-129">W polu Grupa rozmiarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-129">In the Size group field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7ea2f-130">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="7ea2f-131">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="7ea2f-132">Dodawanie grup wymiarów</span><span class="sxs-lookup"><span data-stu-id="7ea2f-132">Add dimension groups</span></span>
1. <span data-ttu-id="7ea2f-133">W okienku akcji kliknij pozycję Produkt.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-133">On the Action Pane, click Product.</span></span>
2. <span data-ttu-id="7ea2f-134">Kliknij przycisk Grupy wymiarów, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-134">Click Dimension groups to open the drop dialog.</span></span>
3. <span data-ttu-id="7ea2f-135">W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-135">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7ea2f-136">Wymiary magazynowania umożliwiają sterowanie sposobem przechowywania towarów w magazynie i sposobem ich pobierania.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="7ea2f-137">Na przykład wymiar magazynowania może obejmować oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-137">For example, a storage dimension can include Site and Warehouse.</span></span>  
4. <span data-ttu-id="7ea2f-138">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="7ea2f-139">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7ea2f-140">W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-140">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7ea2f-141">Grupa wymiarów śledzenia określa wymiary śledzenia, które można dodawać do produktu.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="7ea2f-142">Na przykład numer partii i numer seryjny mogą służyć do śledzenia pozycji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-142">For example, the batch number and serial number are used to track inventory items.</span></span>  
7. <span data-ttu-id="7ea2f-143">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="7ea2f-144">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7ea2f-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-145">Click OK.</span></span>
10. <span data-ttu-id="7ea2f-146">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-146">Click Save.</span></span>
11. <span data-ttu-id="7ea2f-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-147">Close the page.</span></span>


