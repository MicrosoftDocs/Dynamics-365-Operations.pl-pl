---
title: Tworzenie gotowego produktu (tylko luty 2016)
description: To zadanie koncentruje się na tworzeniu wyrobu gotowego.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44f9693e04160ffe9307de5e454d8269ca883679
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570864"
---
# <a name="create-a-finished-product-february-2016-only"></a><span data-ttu-id="59675-103">Tworzenie gotowego produktu (tylko luty 2016)</span><span class="sxs-lookup"><span data-stu-id="59675-103">Create a finished product (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="59675-104">To zadanie koncentruje się na tworzeniu wyrobu gotowego.</span><span class="sxs-lookup"><span data-stu-id="59675-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="59675-105">Jest to pierwsze zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="59675-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="59675-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="59675-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="59675-107">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="59675-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="59675-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="59675-108">Click New.</span></span>
3. <span data-ttu-id="59675-109">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="59675-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="59675-110">Dla demonstracji wpisz BOM_1.</span><span class="sxs-lookup"><span data-stu-id="59675-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="59675-111">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="59675-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="59675-112">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="59675-112">Select STD.</span></span> <span data-ttu-id="59675-113">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="59675-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="59675-114">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="59675-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="59675-115">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="59675-115">For example, select Audio.</span></span> <span data-ttu-id="59675-116">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="59675-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="59675-117">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="59675-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="59675-118">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="59675-118">Select SiteWH.</span></span> <span data-ttu-id="59675-119">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="59675-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="59675-120">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="59675-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="59675-121">Wymiary śledzenia nie będą używane w tym przykładzie. Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="59675-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="59675-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="59675-122">Click OK.</span></span>
9. <span data-ttu-id="59675-123">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="59675-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="59675-124">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="59675-124">Click Default order settings.</span></span>
11. <span data-ttu-id="59675-125">W polu Domyślny typ zamówienia wybierz opcję „Produkcja”.</span><span class="sxs-lookup"><span data-stu-id="59675-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="59675-126">Ponieważ jest to wyrób gotowy, który zostanie wytworzony, wybierz opcję Produkcja.</span><span class="sxs-lookup"><span data-stu-id="59675-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="59675-127">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="59675-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="59675-128">Dla demonstracji zaznacz wartość Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="59675-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="59675-129">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="59675-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="59675-130">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="59675-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="59675-131">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="59675-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="59675-132">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="59675-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="59675-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="59675-133">Close the page.</span></span>

