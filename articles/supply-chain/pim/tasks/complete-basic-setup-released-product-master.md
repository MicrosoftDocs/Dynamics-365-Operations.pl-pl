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
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "354789"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="ea01a-103">Wypełnianie podstawowych ustawień zrealizowanego produktu głównego</span><span class="sxs-lookup"><span data-stu-id="ea01a-103">Complete basic setup of a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ea01a-104">Ta procedura pokazuje wykonywanie minimalnej konfiguracji, która jest wymagana, zanim produktu głównego będzie można używać w wersjach BOM.</span><span class="sxs-lookup"><span data-stu-id="ea01a-104">This procedure shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="ea01a-105">Jest to trzecia z ośmiu procedur opisujących sposób tworzenia kombinacji dla konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="ea01a-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="ea01a-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ea01a-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="ea01a-107">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="ea01a-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="ea01a-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea01a-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ea01a-109">Wybierz produkt główny, który został zwolniony w drugiej procedurze.</span><span class="sxs-lookup"><span data-stu-id="ea01a-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="ea01a-110">Ten produkt główny został utworzona przy użyciu technologii konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="ea01a-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="ea01a-111">W okienku akcji kliknij pozycję Produkt.</span><span class="sxs-lookup"><span data-stu-id="ea01a-111">On the Action Pane, click Product.</span></span>
4. <span data-ttu-id="ea01a-112">Kliknij przycisk Grupy wymiarów, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ea01a-112">Click Dimension groups to open the drop dialog.</span></span>
5. <span data-ttu-id="ea01a-113">W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea01a-113">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ea01a-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea01a-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ea01a-115">Grupa wymiarów magazynowania określa wymiary magazynowania, które są używane dla transakcji produktu.</span><span class="sxs-lookup"><span data-stu-id="ea01a-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="ea01a-116">W tej procedurze wybierz opcję Oddział.</span><span class="sxs-lookup"><span data-stu-id="ea01a-116">Select Site for this procedure.</span></span>  
7. <span data-ttu-id="ea01a-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea01a-117">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ea01a-118">W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea01a-118">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="ea01a-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea01a-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ea01a-120">Grupa wymiarów śledzenia określa wymiary śledzenia, które są używane dla transakcji produktu.</span><span class="sxs-lookup"><span data-stu-id="ea01a-120">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="ea01a-121">W tej procedurze wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="ea01a-121">Select None for this procedure.</span></span>  
10. <span data-ttu-id="ea01a-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea01a-122">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="ea01a-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ea01a-123">Click OK.</span></span>
12. <span data-ttu-id="ea01a-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea01a-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="ea01a-125">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="ea01a-125">Click Edit.</span></span>
    * <span data-ttu-id="ea01a-126">Otwórz formularz Szczegóły zwolnionego produktu, aby kontynuować zadanie konfigurowania.</span><span class="sxs-lookup"><span data-stu-id="ea01a-126">Open the Released product details form to continue the setup task.</span></span>  
14. <span data-ttu-id="ea01a-127">W polu Grupa modeli towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea01a-127">In the Item model group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="ea01a-128">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea01a-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ea01a-129">Grupy modeli towarów zawierają ustawienia określające sposób kontroli i obsługi towarów przy ich przyjmowaniu i wydawaniu.</span><span class="sxs-lookup"><span data-stu-id="ea01a-129">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="ea01a-130">Określają one także sposób obliczania zużycia towarów.</span><span class="sxs-lookup"><span data-stu-id="ea01a-130">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="ea01a-131">W tej procedurze wybierz opcję FIFO.</span><span class="sxs-lookup"><span data-stu-id="ea01a-131">Select   FIFO for this procedure.</span></span>  
16. <span data-ttu-id="ea01a-132">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea01a-132">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="ea01a-133">Rozwiń lub zwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ea01a-133">Expand or collapse the Manage costs section.</span></span>
18. <span data-ttu-id="ea01a-134">W polu Grupa towarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea01a-134">In the Item group field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="ea01a-135">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea01a-135">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ea01a-136">Grupy towarów służą do zarządzania zapasami przez dzielenie towarów magazynowych na grupy.</span><span class="sxs-lookup"><span data-stu-id="ea01a-136">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="ea01a-137">W tej procedurze wybierz opcję CarAudio.</span><span class="sxs-lookup"><span data-stu-id="ea01a-137">Select   CarAudio for this procedure.</span></span>  
20. <span data-ttu-id="ea01a-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea01a-138">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="ea01a-139">W okienku akcji kliknij opcję Plan.</span><span class="sxs-lookup"><span data-stu-id="ea01a-139">On the Action Pane, click Plan.</span></span>
22. <span data-ttu-id="ea01a-140">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="ea01a-140">Click Default order settings.</span></span>
23. <span data-ttu-id="ea01a-141">W polu Domyślny typ zamówienia wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="ea01a-141">In the Default order type field, select an option.</span></span>
    * <span data-ttu-id="ea01a-142">Wybierz opcję Produkcja, aby określić, że domyślną opcja dostaw tego produktu głównego jest jego wytwarzanie.</span><span class="sxs-lookup"><span data-stu-id="ea01a-142">Select Production to specify that the default supply option for this product master is to produce it.</span></span>  
24. <span data-ttu-id="ea01a-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ea01a-143">Close the page.</span></span>
25. <span data-ttu-id="ea01a-144">Zamknij formularz Szczegóły zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="ea01a-144">Close the Released product details form.</span></span>

