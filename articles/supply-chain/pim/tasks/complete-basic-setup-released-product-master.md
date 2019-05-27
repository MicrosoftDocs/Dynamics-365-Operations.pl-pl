---
title: Wypełnianie podstawowych ustawień zrealizowanego produktu głównego
description: Ta procedura pokazuje wykonywanie minimalnej konfiguracji, która jest wymagana, zanim produktu głównego będzie można używać w wersjach BOM.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d3a91977c38c0ce0f9fe114bec943c7cb32a5d4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568781"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="e56fc-103">Wypełnianie podstawowych ustawień zrealizowanego produktu głównego</span><span class="sxs-lookup"><span data-stu-id="e56fc-103">Complete basic setup of a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e56fc-104">Ta procedura pokazuje wykonywanie minimalnej konfiguracji, która jest wymagana, zanim produktu głównego będzie można używać w wersjach BOM.</span><span class="sxs-lookup"><span data-stu-id="e56fc-104">This procedure shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="e56fc-105">Jest to trzecia z ośmiu procedur opisujących sposób tworzenia kombinacji dla konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="e56fc-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="e56fc-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e56fc-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="e56fc-107">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="e56fc-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="e56fc-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e56fc-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e56fc-109">Wybierz produkt główny, który został zwolniony w drugiej procedurze.</span><span class="sxs-lookup"><span data-stu-id="e56fc-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="e56fc-110">Ten produkt główny został utworzona przy użyciu technologii konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="e56fc-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="e56fc-111">W okienku akcji kliknij pozycję Produkt.</span><span class="sxs-lookup"><span data-stu-id="e56fc-111">On the Action Pane, click Product.</span></span>
4. <span data-ttu-id="e56fc-112">Kliknij przycisk Grupy wymiarów, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="e56fc-112">Click Dimension groups to open the drop dialog.</span></span>
5. <span data-ttu-id="e56fc-113">W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e56fc-113">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="e56fc-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e56fc-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e56fc-115">Grupa wymiarów magazynowania określa wymiary magazynowania, które są używane dla transakcji produktu.</span><span class="sxs-lookup"><span data-stu-id="e56fc-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="e56fc-116">W tej procedurze wybierz opcję Oddział.</span><span class="sxs-lookup"><span data-stu-id="e56fc-116">Select Site for this procedure.</span></span>  
7. <span data-ttu-id="e56fc-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e56fc-117">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="e56fc-118">W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e56fc-118">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="e56fc-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e56fc-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e56fc-120">Grupa wymiarów śledzenia określa wymiary śledzenia, które są używane dla transakcji produktu.</span><span class="sxs-lookup"><span data-stu-id="e56fc-120">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="e56fc-121">W tej procedurze wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="e56fc-121">Select None for this procedure.</span></span>  
10. <span data-ttu-id="e56fc-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e56fc-122">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="e56fc-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e56fc-123">Click OK.</span></span>
12. <span data-ttu-id="e56fc-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e56fc-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="e56fc-125">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="e56fc-125">Click Edit.</span></span>
    * <span data-ttu-id="e56fc-126">Otwórz formularz Szczegóły zwolnionego produktu, aby kontynuować zadanie konfigurowania.</span><span class="sxs-lookup"><span data-stu-id="e56fc-126">Open the Released product details form to continue the setup task.</span></span>  
14. <span data-ttu-id="e56fc-127">W polu Grupa modeli towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e56fc-127">In the Item model group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="e56fc-128">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e56fc-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e56fc-129">Grupy modeli towarów zawierają ustawienia określające sposób kontroli i obsługi towarów przy ich przyjmowaniu i wydawaniu.</span><span class="sxs-lookup"><span data-stu-id="e56fc-129">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="e56fc-130">Określają one także sposób obliczania zużycia towarów.</span><span class="sxs-lookup"><span data-stu-id="e56fc-130">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="e56fc-131">W tej procedurze wybierz opcję FIFO.</span><span class="sxs-lookup"><span data-stu-id="e56fc-131">Select   FIFO for this procedure.</span></span>  
16. <span data-ttu-id="e56fc-132">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e56fc-132">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="e56fc-133">Rozwiń lub zwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e56fc-133">Expand or collapse the Manage costs section.</span></span>
18. <span data-ttu-id="e56fc-134">W polu Grupa towarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e56fc-134">In the Item group field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="e56fc-135">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e56fc-135">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e56fc-136">Grupy towarów służą do zarządzania zapasami przez dzielenie towarów magazynowych na grupy.</span><span class="sxs-lookup"><span data-stu-id="e56fc-136">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="e56fc-137">W tej procedurze wybierz opcję CarAudio.</span><span class="sxs-lookup"><span data-stu-id="e56fc-137">Select   CarAudio for this procedure.</span></span>  
20. <span data-ttu-id="e56fc-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e56fc-138">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="e56fc-139">W okienku akcji kliknij opcję Plan.</span><span class="sxs-lookup"><span data-stu-id="e56fc-139">On the Action Pane, click Plan.</span></span>
22. <span data-ttu-id="e56fc-140">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="e56fc-140">Click Default order settings.</span></span>
23. <span data-ttu-id="e56fc-141">W polu Domyślny typ zamówienia wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="e56fc-141">In the Default order type field, select an option.</span></span>
    * <span data-ttu-id="e56fc-142">Wybierz opcję Produkcja, aby określić, że domyślną opcja dostaw tego produktu głównego jest jego wytwarzanie.</span><span class="sxs-lookup"><span data-stu-id="e56fc-142">Select Production to specify that the default supply option for this product master is to produce it.</span></span>  
24. <span data-ttu-id="e56fc-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e56fc-143">Close the page.</span></span>
25. <span data-ttu-id="e56fc-144">Zamknij formularz Szczegóły zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="e56fc-144">Close the Released product details form.</span></span>

