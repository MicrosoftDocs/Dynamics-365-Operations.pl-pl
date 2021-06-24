---
title: Magazyny
description: Lokalizacje w magazynach są używane w podstawowym module zarządzania magazynem (WMS I) do ustalania, gdzie towary będą przechowywane i skąd będą pobierane w magazynie zarządzanym w ramach WMS I.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSLocation, WMSBlockingCause, WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8d5459e37b5827b6a2ff07c892c2ff25b76ecd6
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187489"
---
# <a name="inventory-locations"></a><span data-ttu-id="52d38-103">Magazyny</span><span class="sxs-lookup"><span data-stu-id="52d38-103">Inventory locations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52d38-104">Lokalizacje w magazynach są używane w podstawowym module zarządzania magazynem (WMS I) do ustalania, gdzie towary będą przechowywane i skąd będą pobierane w magazynie zarządzanym w ramach WMS I.</span><span class="sxs-lookup"><span data-stu-id="52d38-104">Inventory locations are used with basic warehousing (WMS I) to determine where items are stored and where items are picked from in a WMS I warehouse.</span></span>

<span data-ttu-id="52d38-105">Ten temat dotyczy funkcji w module Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="52d38-105">This topic applies to features in the Inventory management module.</span></span> <span data-ttu-id="52d38-106">Nie ma zastosowania do funkcji w module Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="52d38-106">It does not apply to features in the Warehouse management module.</span></span>

<span data-ttu-id="52d38-107">Termin lokalizacja dotyczy miejsca, w którym towary są przechowywane i z którego są wyjmowane.</span><span class="sxs-lookup"><span data-stu-id="52d38-107">The term location refers to the place that items are stored and drawn from.</span></span>

<span data-ttu-id="52d38-108">Dla każdej lokalizacji można także określić miejsce, w którym jest wkładany towar.</span><span class="sxs-lookup"><span data-stu-id="52d38-108">For each location, the place where the item is inserted can also be specified.</span></span> <span data-ttu-id="52d38-109">Domyślnie te miejsca są identyczne.</span><span class="sxs-lookup"><span data-stu-id="52d38-109">By default, they are the same.</span></span> <span data-ttu-id="52d38-110">Zazwyczaj towary są wkładane i wyjmowane po tej samej stronie lokalizacji, jednak ta zasada nie zawsze obowiązuje.</span><span class="sxs-lookup"><span data-stu-id="52d38-110">Items are usually inserted and drawn from the same side of a location, but not always.</span></span> <span data-ttu-id="52d38-111">Na przykład towary przechowywane na ruchomych regałach są wkładane z jednego korytarza, a wyjmowane z drugiego.</span><span class="sxs-lookup"><span data-stu-id="52d38-111">For example, items that are stored in live storage racks are inserted from one aisle and drawn from another.</span></span> <span data-ttu-id="52d38-112">Głównego wprowadzenia dokonuje się przez nazwę lokalizacji, która jest zwykle określana na podstawie jej współrzędnych: magazyn, korytarz, regał, półka i pojemnik.</span><span class="sxs-lookup"><span data-stu-id="52d38-112">The main input is given by a location name, which is usually determined by its coordinates: warehouse, aisle, rack, shelf, and bin.</span></span> <span data-ttu-id="52d38-113">Tę nazwę lub identyfikator można wprowadzać ręcznie lub generować na podstawie współrzędnych lokalizacji — na przykład 01-02-03-4 oznacza korytarz 1, regał 2, półkę 3 i pojemnik 4 na stronie Magazyny.</span><span class="sxs-lookup"><span data-stu-id="52d38-113">This name or ID can be entered manually or generated from the location coordinates—for example, 01-02-03-4 for aisle 1, rack 2, shelf 3, bin 4 in the Inventory locations page.</span></span>
<span data-ttu-id="52d38-114">Właściwości lokalizacji</span><span class="sxs-lookup"><span data-stu-id="52d38-114">Location properties</span></span>

<span data-ttu-id="52d38-115">Lokalizacja ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="52d38-115">A location has the following characteristics:</span></span>
-   <span data-ttu-id="52d38-116">Rozmiar (wysokość, szerokość, głębokość, a przez to objętość)</span><span class="sxs-lookup"><span data-stu-id="52d38-116">Size (height, width, depth, and thereby volume)</span></span>
-   <span data-ttu-id="52d38-117">Magazyn, korytarz, regał, półka oraz pojemnik.</span><span class="sxs-lookup"><span data-stu-id="52d38-117">Warehouse, aisle, rack, shelf, and bin position</span></span>
-   <span data-ttu-id="52d38-118">Typ lokalizacji (lokalizacja zbiorcza, lokalizacji pobrania, dok rozładunkowy, dok załadunkowy, lokalizacja przyjęcia z produkcji, lokalizacja inspekcji lub supermarket kanban)</span><span class="sxs-lookup"><span data-stu-id="52d38-118">Location type (bulk location, picking location, inbound dock, outbound dock, production input location, inspection location, or kanban supermarket)</span></span>

<span data-ttu-id="52d38-119">W systemach online w celu sprawdzenia, czy operator wybrał prawidłową lokalizację dla określonego towaru, można użyć funkcji Tekst sprawdzania.</span><span class="sxs-lookup"><span data-stu-id="52d38-119">Check text can be used in online systems to verify that the operator has selected the correct location for a specific item.</span></span> <span data-ttu-id="52d38-120">Ten tekst sprawdzania można utworzyć ręcznie lub użyć domyślnego.</span><span class="sxs-lookup"><span data-stu-id="52d38-120">This check text can be created manually or by default.</span></span>

## <a name="sort-codes"></a><span data-ttu-id="52d38-121">Kody sortowania</span><span class="sxs-lookup"><span data-stu-id="52d38-121">Sort codes</span></span>
<span data-ttu-id="52d38-122">Kody sortowania umożliwiają optymalizację obsługi wierszy pobrań, które pozwalają uzyskać szczegółowe informacje wymagane do pobierania towarów z magazynu, w tym kolejność pobierania.</span><span class="sxs-lookup"><span data-stu-id="52d38-122">Use sort codes to optimize the handling of picking lines, which describe the information that is required for picking items from inventory, including the picking order.</span></span> <span data-ttu-id="52d38-123">Kody sortowania mogą być określane na podstawie korytarza lub innych współrzędnych, można je także przypisywać ręcznie do konkretnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="52d38-123">Sort codes can be specified by the aisle and other coordinates, or assigned manually for the location.</span></span>

## <a name="blocked-locations"></a><span data-ttu-id="52d38-124">Lokalizacje zablokowane</span><span class="sxs-lookup"><span data-stu-id="52d38-124">Blocked locations</span></span>
<span data-ttu-id="52d38-125">Sporadycznie konieczne może być wskazanie lokalizacji, która jest przez jakiś czas zablokowana, na przykład w celu dokonania napraw.</span><span class="sxs-lookup"><span data-stu-id="52d38-125">Occasionally, you might want to indicate that a location is blocked for a period of time, for example, to allow for repairs.</span></span> <span data-ttu-id="52d38-126">Innym razem może zaistnieć potrzeba zablokowania tylko wejścia lub tylko wyjścia.</span><span class="sxs-lookup"><span data-stu-id="52d38-126">At other times, you may want to indicate blocking of only the input or only output.</span></span>

## <a name="tree-structure"></a><span data-ttu-id="52d38-127">Struktura drzewa</span><span class="sxs-lookup"><span data-stu-id="52d38-127">Tree structure</span></span>

<span data-ttu-id="52d38-128">Na stronie Magazyny można wyświetlić układ magazynu w postaci struktury drzewa na podstawie współrzędnych lokalizacji magazynu, w zdefiniowanym formacie wyświetlania.</span><span class="sxs-lookup"><span data-stu-id="52d38-128">In the Inventory locations page, you can view the warehouse layout in a tree structure based on the coordinates of inventory locations, in a defined display format.</span></span>

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a><span data-ttu-id="52d38-129">Obsługa magazynów za pomocą formularza magazynu</span><span class="sxs-lookup"><span data-stu-id="52d38-129">Maintain inventory locations via the warehouse form</span></span>

<span data-ttu-id="52d38-130">Można skopiować lokalizacje z jednego magazynu do innego i tworzyć lokalizacje za pomocą kreatora.</span><span class="sxs-lookup"><span data-stu-id="52d38-130">It is possible to copy locations from one warehouse to another and to create locations via a wizard.</span></span> <span data-ttu-id="52d38-131">Przed uruchomieniem kreatora należy upewnić się, że masz zdefiniowane domyślne nazwy lokalizacji na stronie Magazyn.</span><span class="sxs-lookup"><span data-stu-id="52d38-131">Before you run the wizard you should make sure that you have defined the default location names on the Warehouse page.</span></span>



## <a name="additional-resources"></a><span data-ttu-id="52d38-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="52d38-132">Additional resources</span></span>

[<span data-ttu-id="52d38-133">Tworzenie nowego układu magazynu</span><span class="sxs-lookup"><span data-stu-id="52d38-133">Create a new warehouse layout</span></span>](tasks/create-new-warehouse-layout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]