---
title: Definiowanie grup harmonogramów produkcji oszczędnej
description: Grupy harmonogramów produkcji oszczędnej tworzy się w celu grupowania i odróżniania produktów w planowaniu w systemie Kanban.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b972327a0a4bf8f5f35340b83236d5053aaa7e40
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146820"
---
# <a name="define-lean-schedule-groups"></a><span data-ttu-id="48a06-103">Definiowanie grup harmonogramów produkcji oszczędnej</span><span class="sxs-lookup"><span data-stu-id="48a06-103">Define lean schedule groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="48a06-104">Grupy harmonogramów produkcji oszczędnej tworzy się w celu grupowania i odróżniania produktów w planowaniu w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="48a06-104">Lean schedule groups are defined to group and distinguish products in kanban scheduling.</span></span> <span data-ttu-id="48a06-105">Grupowanie jest możliwe jako ogólne skojarzenie dla każdej firmy lub specyficzne dla komórki roboczej.</span><span class="sxs-lookup"><span data-stu-id="48a06-105">The grouping can be done as generic association per company or specific to a work cell.</span></span> <span data-ttu-id="48a06-106">Każda grupa ma przypisany osobny kolor do wizualnej identyfikacji na stronie z listą planowania w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="48a06-106">Each group has a color code assigned for visual indication in the kanban scheduling listpage.</span></span> <span data-ttu-id="48a06-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="48a06-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-lean-scheduling-group"></a><span data-ttu-id="48a06-108">Definiowanie grupy harmonogramów produkcji oszczędnej</span><span class="sxs-lookup"><span data-stu-id="48a06-108">Define lean scheduling group</span></span>
1. <span data-ttu-id="48a06-109">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Grupy harmonogramów produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="48a06-109">Go to Product information management > Lean manufacturing > Lean schedule groups.</span></span>
2. <span data-ttu-id="48a06-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="48a06-110">Click New.</span></span>
3. <span data-ttu-id="48a06-111">W polu Grupa harmonogramów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a06-111">In the Schedule group field, type a value.</span></span>
    * <span data-ttu-id="48a06-112">Grupa harmonogramów może być zdefiniowana jako grupa globalna lub specyficzna dla komórki roboczej.</span><span class="sxs-lookup"><span data-stu-id="48a06-112">A schedule group can be defined as global group or specific to a work cell.</span></span> <span data-ttu-id="48a06-113">W tym prostym przykładzie zdefiniujemy grupę globalną, a komórka robocza pozostaje pusta.</span><span class="sxs-lookup"><span data-stu-id="48a06-113">In this simple example, we define a global group, and the work cell is kept empty.</span></span> <span data-ttu-id="48a06-114">Ustawienia tej grupy mają zastosowanie do wszystkich komórek roboczych, którym nie przypisano konkretnych grup harmonogramów.</span><span class="sxs-lookup"><span data-stu-id="48a06-114">The settings of this group apply to all work cells that do not have specific schedule groups.</span></span>  
4. <span data-ttu-id="48a06-115">Wybierz kolor z palety kolorów.</span><span class="sxs-lookup"><span data-stu-id="48a06-115">Select a color from the color selection.</span></span>
    * <span data-ttu-id="48a06-116">Kolory służą do wyróżniania zadań na stronie listy harmonogramu Kanban lub tablicy procesów w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="48a06-116">The colors are used to highlight the jobs on the kanban schedule list page or the kanban process board.</span></span>  
5. <span data-ttu-id="48a06-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="48a06-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="48a06-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="48a06-118">In the list, click the link in the selected row.</span></span>

## <a name="associate-product"></a><span data-ttu-id="48a06-119">Kojarzenie produktu</span><span class="sxs-lookup"><span data-stu-id="48a06-119">Associate product</span></span>
1. <span data-ttu-id="48a06-120">Skojarz określony produkt.</span><span class="sxs-lookup"><span data-stu-id="48a06-120">Associate a specific product</span></span>
    * <span data-ttu-id="48a06-121">Istnieją dwa sposoby kojarzenia produktów do grupami harmonogramów produkcji oszczędnej: jako określonego produktu (Typ relacji towaru = Towar) lub jako część klucza alokacji towaru (Typ relacji towaru = Grupa).</span><span class="sxs-lookup"><span data-stu-id="48a06-121">There are two ways to associate products to lean schedule groups, either as a specific product (Item relation type = Item) or as part of an item allocation key (item relation type = group).</span></span>    
2. <span data-ttu-id="48a06-122">W polu Typ relacji produktu wybierz opcję Towar.</span><span class="sxs-lookup"><span data-stu-id="48a06-122">In the Item relation type field, select Item</span></span>
3. <span data-ttu-id="48a06-123">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a06-123">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="48a06-124">W polu Wskaźnik produktywności wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="48a06-124">In the Throughput ratio field, enter a number.</span></span>
    * <span data-ttu-id="48a06-125">Domyślny wskaźnik produktywności wynosi 1, co oznacza, że powiązane produkty zużywają dokładnie zdolności produkcyjne określone w działaniach procesów przepływów produkcji.</span><span class="sxs-lookup"><span data-stu-id="48a06-125">The default Throughput ratio is 1, which means that the related products consume exactly the capacity specified in the process activites of the production flows.</span></span> <span data-ttu-id="48a06-126">Wskaźnik produktywności > 1 określa wyższe, a wskaźnik produktywności < 1 niższe zużycie zasobów.</span><span class="sxs-lookup"><span data-stu-id="48a06-126">Throughput ratio > 1 defines a higher resource consumption, Throughput ratio < 1 defines a lower resource consumption.</span></span> <span data-ttu-id="48a06-127">Współczynnik jest używany w obliczeniach kosztów i w obliczaniu zużycia w ramach zadania w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="48a06-127">The ratio is used in the cost calculation and in the calculation of the kanban job consumption.</span></span>  

## <a name="associate-item-allocation-key"></a><span data-ttu-id="48a06-128">Kojarzenie klucza alokacji towaru</span><span class="sxs-lookup"><span data-stu-id="48a06-128">Associate item allocation key</span></span>
1. <span data-ttu-id="48a06-129">Powiąż klucz alokacji towaru.</span><span class="sxs-lookup"><span data-stu-id="48a06-129">Associate an item allocation key</span></span>
    * <span data-ttu-id="48a06-130">Dodaj skojarzenie do klucza alokacji towaru przy użyciu typu relacji towaru Grupa.</span><span class="sxs-lookup"><span data-stu-id="48a06-130">Add an association to an item allocation key by using the Item relation type Group.</span></span>   <span data-ttu-id="48a06-131">Należy zauważyć, że w przypadku tego procesu w danych musi być zdefiniowany klucz alokacji prognozy towaru.</span><span class="sxs-lookup"><span data-stu-id="48a06-131">Note that for this process, you need a forecast item alllocation key defined in your data.</span></span>  
2. <span data-ttu-id="48a06-132">W polu Typ relacji produktu wybierz opcję Grupa.</span><span class="sxs-lookup"><span data-stu-id="48a06-132">In the Item relation type field, select Group</span></span>
3. <span data-ttu-id="48a06-133">W polu Klucz alokacji towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="48a06-133">In the Item allocation key field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="48a06-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="48a06-134">In the list, click the link in the selected row.</span></span>

