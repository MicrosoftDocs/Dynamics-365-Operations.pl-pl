---
title: Wypełnianie podstawowych ustawień zwolnionego produktu głównego
description: Ten temat opisuje wykonywanie minimalnej konfiguracji, która jest wymagana, zanim produktu głównego będzie można używać w wersjach BOM.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 668b60efa55fa553cf308d5bfc5da7e23f460366
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987036"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="2d636-103">Wypełnianie podstawowych ustawień zwolnionego produktu głównego</span><span class="sxs-lookup"><span data-stu-id="2d636-103">Complete basic setup of a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d636-104">Ten temat opisuje wykonywanie minimalnej konfiguracji, która jest wymagana, zanim produktu głównego będzie można używać w wersjach BOM.</span><span class="sxs-lookup"><span data-stu-id="2d636-104">This topic shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="2d636-105">Jest to trzecia z ośmiu procedur opisujących sposób tworzenia kombinacji dla konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="2d636-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="2d636-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2d636-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="2d636-107">Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.</span><span class="sxs-lookup"><span data-stu-id="2d636-107">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="2d636-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2d636-108">In the list, find and select the desired record.</span></span> <span data-ttu-id="2d636-109">Wybierz produkt główny, który został zwolniony w drugiej procedurze.</span><span class="sxs-lookup"><span data-stu-id="2d636-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="2d636-110">Ten produkt główny został utworzona przy użyciu technologii konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="2d636-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="2d636-111">W okienku akcji wybierz pozycję **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="2d636-111">On the Action Pane, select **Product**.</span></span>
4. <span data-ttu-id="2d636-112">Wybierz **Grupy wymiarów**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="2d636-112">Select **Dimension groups** to open the drop dialog.</span></span>
5. <span data-ttu-id="2d636-113">W polu **Grupa wymiarów magazynowania** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2d636-113">In the **Storage dimension group** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="2d636-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2d636-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="2d636-115">Grupa wymiarów magazynowania określa wymiary magazynowania, które są używane dla transakcji produktu.</span><span class="sxs-lookup"><span data-stu-id="2d636-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="2d636-116">W tej procedurze wybierz opcję **Oddział**.</span><span class="sxs-lookup"><span data-stu-id="2d636-116">Select **Site** for this procedure.</span></span>  
7. <span data-ttu-id="2d636-117">W polu **Grupa wymiarów śledzenia** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2d636-117">In the **Tracking dimension group** field, select the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="2d636-118">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2d636-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="2d636-119">Grupa wymiarów śledzenia określa wymiary śledzenia, które są używane dla transakcji produktu.</span><span class="sxs-lookup"><span data-stu-id="2d636-119">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="2d636-120">W tej procedurze wybierz opcję **Brak**.</span><span class="sxs-lookup"><span data-stu-id="2d636-120">Select **None** for this procedure.</span></span>  
9. <span data-ttu-id="2d636-121">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d636-121">Click **OK**.</span></span>
10. <span data-ttu-id="2d636-122">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2d636-122">Click **Edit**.</span></span>
11. <span data-ttu-id="2d636-123">W polu **Grupa modeli towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2d636-123">In the **Item model group** field, select the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="2d636-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2d636-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="2d636-125">Grupy modeli towarów zawierają ustawienia określające sposób kontroli i obsługi towarów przy ich przyjmowaniu i wydawaniu.</span><span class="sxs-lookup"><span data-stu-id="2d636-125">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="2d636-126">Określają one także sposób obliczania zużycia towarów.</span><span class="sxs-lookup"><span data-stu-id="2d636-126">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="2d636-127">W tej procedurze wybierz opcję **FIFO**.</span><span class="sxs-lookup"><span data-stu-id="2d636-127">Select **FIFO** for this procedure.</span></span>  
13. <span data-ttu-id="2d636-128">Rozwiń sekcję **Zarządzanie kosztami**.</span><span class="sxs-lookup"><span data-stu-id="2d636-128">Expand the **Manage costs** section.</span></span>
14. <span data-ttu-id="2d636-129">W polu **Grupa towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2d636-129">In the **Item group** field, select the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="2d636-130">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2d636-130">In the list, find and select the desired record.</span></span> <span data-ttu-id="2d636-131">Grupy towarów służą do zarządzania zapasami przez dzielenie towarów magazynowych na grupy.</span><span class="sxs-lookup"><span data-stu-id="2d636-131">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="2d636-132">W tej procedurze wybierz opcję **CarAudio**.</span><span class="sxs-lookup"><span data-stu-id="2d636-132">Select **CarAudio** for this procedure.</span></span>  
16. <span data-ttu-id="2d636-133">W okienku akcji wybierz opcję **Plan**.</span><span class="sxs-lookup"><span data-stu-id="2d636-133">On the Action Pane, select **Plan**.</span></span>
17. <span data-ttu-id="2d636-134">Wybierz **Ustawienia domyślne zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="2d636-134">Select **Default order settings**.</span></span>
18. <span data-ttu-id="2d636-135">W polu **Domyślny typ zamówienia** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="2d636-135">In the **Default order type field**, select an option.</span></span> <span data-ttu-id="2d636-136">Wybierz opcję **Produkcja**, aby określić, że domyślną opcja dostaw tego produktu głównego jest jego wytwarzanie.</span><span class="sxs-lookup"><span data-stu-id="2d636-136">Select **Production** to specify that the default supply option for this product master is to produce it.</span></span>  
19. <span data-ttu-id="2d636-137">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2d636-137">Select **Save**.</span></span>
20. <span data-ttu-id="2d636-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2d636-138">Close the page.</span></span>
21. <span data-ttu-id="2d636-139">Zamknij formularz **Szczegóły zwolnionego produktu**.</span><span class="sxs-lookup"><span data-stu-id="2d636-139">Close the **Released product details** form.</span></span>

