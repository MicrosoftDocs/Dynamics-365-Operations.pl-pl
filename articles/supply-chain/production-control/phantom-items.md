---
title: Towary fantomowe
description: "W tym temacie szczegółowo opisano, jak typ wiersza Fantom może być wykorzystywany w wierszach listy składowej (BOM) i formule w programie Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 06/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: shylaw
ms.search.validfrom: 
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: a92dd82f309867586f047e0dfc36e452a44a0f9c
ms.contentlocale: pl-pl
ms.lasthandoff: 10/01/2018

---

# <a name="phantom-items"></a><span data-ttu-id="99a78-103">Towary fantomowe</span><span class="sxs-lookup"><span data-stu-id="99a78-103">Phantom items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99a78-104">W tym temacie szczegółowo opisano, jak typ wiersza Fantom może być wykorzystywany w wierszach listy składowej (BOM) i formule.</span><span class="sxs-lookup"><span data-stu-id="99a78-104">This topic describes, in detail, how the Phantom line type can be used for the lines of a bill of materials (BOM) and a formula.</span></span> <span data-ttu-id="99a78-105">Na ilustracji poniżej (a) to BOM produktu H oraz części F i G, a (b) to arkusz marszruty dla produktu H i części F.</span><span class="sxs-lookup"><span data-stu-id="99a78-105">In the following illustration, (a) is the BOM for product H and parts F and G, and (b) is the route sheet for products H and part F.</span></span>

![Produkt H i część F](media/product-H-part-F.png)


<span data-ttu-id="99a78-107">Na tej ilustracji pokazano przykład struktury BOM na dwóch poziomach.</span><span class="sxs-lookup"><span data-stu-id="99a78-107">This illustration shows an example of a BOM structure in two levels.</span></span> <span data-ttu-id="99a78-108">Produkt gotowy H reprezentuje produkt dla zespołu maszyny.</span><span class="sxs-lookup"><span data-stu-id="99a78-108">Finished product H represents a product for a machine assembly.</span></span> <span data-ttu-id="99a78-109">Zespół maszyny składa się z dwóch części: jednostki elektrycznej (F) zawierającej dwa materiały (A i B) oraz grupy materiałów opakowaniowych (G), która również zawiera dwa materiały (C i D).</span><span class="sxs-lookup"><span data-stu-id="99a78-109">The machine assembly consists of two parts, an electrical unit (F) that has two materials (A and B) and a group of packaging materials (G) that also has two materials (C and D).</span></span> <span data-ttu-id="99a78-110">Inny materiał (E) jest używany podczas ogólnego składania maszyny.</span><span class="sxs-lookup"><span data-stu-id="99a78-110">Another material (E) is used during the general assembly of the machine.</span></span>

![Produkt H i część F](media/product-H-part-B.png)

<span data-ttu-id="99a78-112">Poprzednia ilustracja reprezentuje inżynieryjną listę składową produktu H. Ta struktura dobrze pokazuje ogólny obraz części i składników tworzących cały zespół maszyny.</span><span class="sxs-lookup"><span data-stu-id="99a78-112">The preceding illustration represents the Engineering BOM for product H. This structure provides a good overview of the parts and components of the overall machine assembly.</span></span> <span data-ttu-id="99a78-113">Projektanci produktu mogą preferować przedstawianie BOM w ten sposób, ale ta struktura może nie odzwierciedlać prawidłowo sposobu, w jaki maszyna jest składana na wydziale produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="99a78-113">However, although product designers might prefer to see the BOM represented in this way, this structure might not correctly represent the way that the machine is built on the shop floor.</span></span> 

<span data-ttu-id="99a78-114">Na przykład inżynieryjna lista składowa na powyższej ilustracji wskazuje, że jednostka elektryczna F jest składana jako oddzielna część w ramach osobnego zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="99a78-114">For example, the Engineering BOM in the preceding illustration indicates that electrical unit F is assembled as a separate part on a separate work order.</span></span> <span data-ttu-id="99a78-115">Jednak na wydziale produkcyjnym może się okazać, że bardziej optymalne będzie składanie jednostki elektrycznej w ramach montażu całego zespołu, a nie oddzielnego zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="99a78-115">However, on the shop floor, it might be judged more optimal to assemble the electrical unit as part of the overall machine assembly, not as a separate work order.</span></span>

<span data-ttu-id="99a78-116">Ta inżynieryjna lista składowa również wskazuje, że część G jest osobną częścią.</span><span class="sxs-lookup"><span data-stu-id="99a78-116">This Engineering BOM also indicates that part G is a separate part.</span></span> <span data-ttu-id="99a78-117">Jednak w tej strukturze część G nie reprezentuje fizycznej części, ale zbiór materiałów opakowaniowych.</span><span class="sxs-lookup"><span data-stu-id="99a78-117">However, in this structure, part G doesn’t represent a physical part but a collection of packaging materials.</span></span> 

<span data-ttu-id="99a78-118">W związku z tym mimo iż inżynieryjna lista składowa jest bardzo przydatna w projektowaniu produktu i bieżącym zarządzaniu projektem, może nie być najbardziej logicznym sposobem wspierania procesu wytwarzania produktu.</span><span class="sxs-lookup"><span data-stu-id="99a78-118">Therefore, although an Engineering BOM provides great value for the design of a product and maintenance of that design, it might not be the most logical way to support the manufacturing execution process of the product.</span></span> <span data-ttu-id="99a78-119">Z drugiej strony produkcyjna lista składowa przedstawia najlepszy sposób na wytworzenie produktu.</span><span class="sxs-lookup"><span data-stu-id="99a78-119">By contrast, a Manufacturing BOM represents the best way to build a product.</span></span>

<span data-ttu-id="99a78-120">Na poniższej ilustracji pokazano, jak inżynieryjna lista BOM przekształca się w produkcyjną listę BOM.</span><span class="sxs-lookup"><span data-stu-id="99a78-120">The following illustration shows how the preceding Engineering BOM is transitioned into a Manufacturing BOM.</span></span> <span data-ttu-id="99a78-121">Na tej ilustracji (a) to BOM dla produktu H, a (b) to arkusz marszruty dla produktu H.</span><span class="sxs-lookup"><span data-stu-id="99a78-121">In this illustration, (a) is the BOM for product H, and b is the route sheet for product H.</span></span>

<span data-ttu-id="99a78-122">W tej strukturze widać, że nie występują części F i G, a materiały, z których składają się te części, zostały przeniesione na następny wyższy poziom w BOM.</span><span class="sxs-lookup"><span data-stu-id="99a78-122">In this structure, you can see that there is no notion of parts F and G, and the materials that these parts consist of have been elevated to the next BOM level.</span></span> 

<span data-ttu-id="99a78-123">W przeciwieństwie do inżynieryjnej listy składowej, w której istniały dwa arkusze operacji, produkcyjna lista składowa ma tylko jeden arkusz operacji.</span><span class="sxs-lookup"><span data-stu-id="99a78-123">Unlike the Engineering BOM, which had two operations sheets, the Manufacturing BOM has only one operations sheet.</span></span> <span data-ttu-id="99a78-124">Operacja pakowania, która była połączona z częścią G, również została przeniesiona na wyższy poziom i teraz wchodzi w skład arkusza operacji dla produktu H. Zmontowanie jednostki elektrycznej jest pierwszą operacją.</span><span class="sxs-lookup"><span data-stu-id="99a78-124">The packaging operation that was linked to part G has also been elevated and is now part of the operations sheet for product H. The assembly of the electrical unit is the first operation.</span></span> <span data-ttu-id="99a78-125">Taka kolejność ma duży sens, ponieważ ta jednostka jest używana w następnej operacji, czyli zmontowaniu maszyny.</span><span class="sxs-lookup"><span data-stu-id="99a78-125">This order makes good sense, because this unit is used in the next operation, which is the machine assembly.</span></span> <span data-ttu-id="99a78-126">Ostatnią operacją jest operacja pakowania, która zużywa dwa materiały opakowaniowe (C i D).</span><span class="sxs-lookup"><span data-stu-id="99a78-126">The last operation is the packaging operation, which consumes two packing materials (C and D).</span></span>

<span data-ttu-id="99a78-127">W programie Microsoft Dynamics 365 for Finance and Operations przejście od inżynieryjnej listy składowej do produkcyjnej listy składowej jest realizowane za pomocą typu wiersza BOM Fantom.</span><span class="sxs-lookup"><span data-stu-id="99a78-127">In Microsoft Dynamics 365 for Finance and Operations, the transition between the Engineering BOM and the Manufacturing BOM is enabled through the Phantom BOM line type.</span></span> <span data-ttu-id="99a78-128">Jak sugeruje określenie „fantom”, części F i G znikają w trakcie przekształcania typu BOM.</span><span class="sxs-lookup"><span data-stu-id="99a78-128">As the term “phantom” indicates, parts F and G have disappeared during the transition between the two BOM types.</span></span> <span data-ttu-id="99a78-129">W tym przykładzie wiersz typu Fantom jest stosowany do wierszy BOM dla części F i G w inżynieryjnej liście składowej.</span><span class="sxs-lookup"><span data-stu-id="99a78-129">In this example, the Phantom line type is applied to the BOM lines for parts F and G in the Engineering BOM.</span></span> <span data-ttu-id="99a78-130">Podczas tworzenia zlecenia produkcyjnego lub szarży produkcyjnej inżynieryjna lista składowa jest kopiowana do tego zlecenia/szarży.</span><span class="sxs-lookup"><span data-stu-id="99a78-130">When a production or batch order is created, the Engineering BOM is copied to the production or batch order.</span></span> <span data-ttu-id="99a78-131">Następnie podczas szacowania zlecenia następuje przejście od inżynieryjnej listy składowej do produkcyjnej listy składowej, jak pokazano na poprzedniej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="99a78-131">Then, when the order is estimated, the transition from the Engineering BOM to the Manufacturing BOM occurs, as shown in the preceding illustrations.</span></span> <span data-ttu-id="99a78-132">Z arkusza operacji na drugiej ilustracji materiały opakowaniowe C i D są wprowadzane dla operacji.</span><span class="sxs-lookup"><span data-stu-id="99a78-132">From the operations sheet in the second illustration, packaging materials C and D are input for the operation.</span></span> 

## <a name="multilevel-phantom-bom-structures"></a><span data-ttu-id="99a78-133">Wielopoziomowy fantomowe struktury BOM</span><span class="sxs-lookup"><span data-stu-id="99a78-133">Multilevel phantom BOM structures</span></span>
<span data-ttu-id="99a78-134">Typ wiersza Fantom może być wykorzystywany w wielopoziomowych strukturach BOM, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="99a78-134">The Phantom line type can be used in multilevel BOM structures, as shown in the following illustration.</span></span> <span data-ttu-id="99a78-135">Na tej ilustracji (a) to BOM dla produktu G, a (b) to arkusz marszruty dla części E i F oraz produktu G.</span><span class="sxs-lookup"><span data-stu-id="99a78-135">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for parts E and F and product G.</span></span> 

![Produkt G i część F z arkuszami marszruty](media/product-G-route-sheet-G.png)


<span data-ttu-id="99a78-137">Poniższa ilustracja pokazuje powstałą produkcyjną listę składową i arkusz marszruty, jeśli w wierszach BOM dla części E i F skonfigurowano typ wiersza Fantom.</span><span class="sxs-lookup"><span data-stu-id="99a78-137">The following illustration shows the resulting Manufacturing BOM and route sheet if the BOM lines for parts E and F are configured so that the line type is Phantom.</span></span> <span data-ttu-id="99a78-138">Na tej ilustracji (a) to BOM dla produktu G, a (b) to arkusz marszruty dla produktu G.</span><span class="sxs-lookup"><span data-stu-id="99a78-138">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for product G.</span></span>

![Produkt G](media/product-G.png)


## <a name="phantom-and-route-network"></a><span data-ttu-id="99a78-140">Fantom i sieć marszrut</span><span class="sxs-lookup"><span data-stu-id="99a78-140">Phantom and route network</span></span>
<span data-ttu-id="99a78-141">Fantomowych BOM można również używać dla list składowych zawierających sieć marszrut.</span><span class="sxs-lookup"><span data-stu-id="99a78-141">Phantom BOMs can also be used for a BOM that has a route network.</span></span> <span data-ttu-id="99a78-142">W sieci marszrut następuje równoległe wykonywanie jednej lub więcej operacji.</span><span class="sxs-lookup"><span data-stu-id="99a78-142">In a route network, one or more operations run in parallel.</span></span> <span data-ttu-id="99a78-143">Ilustracja poniżej przedstawia przykład sieci marszrut używanej w wielopoziomowym BOM.</span><span class="sxs-lookup"><span data-stu-id="99a78-143">The following illustration shows an example of a route network that is used in a multilevel BOM.</span></span> <span data-ttu-id="99a78-144">Na tej ilustracji (a) to BOM dla produktów G i F, a (b) to arkusz marszruty dla produktu G oraz części E i F zawierającej sieć marszrut.</span><span class="sxs-lookup"><span data-stu-id="99a78-144">In this illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F, which has a route network.</span></span>

![Produkt G i część F](media/product-G-part-F.png)


<span data-ttu-id="99a78-146">Na ilustracji poniżej (a) to BOM produktu G i części F, a (b) to arkusz marszruty dla produktu G i części F.</span><span class="sxs-lookup"><span data-stu-id="99a78-146">In the following illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F.</span></span>

![Produkt G i część F z arkuszami marszruty](media/product-G-part-F-with-route-sheet.png)

