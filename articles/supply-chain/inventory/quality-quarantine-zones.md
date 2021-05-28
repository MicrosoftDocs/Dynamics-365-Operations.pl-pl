---
title: Strefy kwarantanny niezgodności
description: W tym temacie opisano sposób tworzenia i używania stref kwarantanny w niezgodnościach.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80f4b9dfc7882af4570bf1908784b8d114396402
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021811"
---
# <a name="quarantine-zones-for-nonconformances"></a><span data-ttu-id="7c950-103">Strefy kwarantanny niezgodności</span><span class="sxs-lookup"><span data-stu-id="7c950-103">Quarantine zones for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c950-104">W tym temacie opisano sposób tworzenia i używania stref kwarantanny w niezgodnościach.</span><span class="sxs-lookup"><span data-stu-id="7c950-104">This topic describes how to create and use quarantine zones for nonconformances.</span></span>

<span data-ttu-id="7c950-105">Strona **Strefy kwarantanny** służy do definiowania stref, które można przypisać do niezgodności.</span><span class="sxs-lookup"><span data-stu-id="7c950-105">You use the **Quarantine zones** page to define zones that can be assigned to nonconformances.</span></span> <span data-ttu-id="7c950-106">Podczas tworzenia niezgodności można ustawić pola **Strefa kwarantanny** i **Typ kwarantanny** na karcie **Ogólne** na stronie **Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="7c950-106">When you create a nonconformance, you can set the **Quarantine zone** and **Quarantine type** fields on the **General** tab of the **Non conformances** page.</span></span> <span data-ttu-id="7c950-107">Pole **Strefa kwarantanny** zazwyczaj wskazuje obszar lub lokalizację, w której znajduje się towar.</span><span class="sxs-lookup"><span data-stu-id="7c950-107">The **Quarantine zone** field typically indicates the area or location where the item is located.</span></span> <span data-ttu-id="7c950-108">Pole **Typ kwarantanny** definiuje towar jako *Ograniczone użycie* lub *Nienadający się do użytku*.</span><span class="sxs-lookup"><span data-stu-id="7c950-108">The **Quarantine type** field defines the item as either *Restricted usage* or *Unusable*.</span></span>

<span data-ttu-id="7c950-109">Podczas drukowania raportu o niezgodności lub korektach dla niezgodności można wyświetlić strefę kwarantanny, w której znajduje się towar.</span><span class="sxs-lookup"><span data-stu-id="7c950-109">When you print a nonconformance or corrections report for a nonconformance, you can view the quarantine zone where the item is located.</span></span>

<span data-ttu-id="7c950-110">Dla niezgodności można również wydrukować znacznik niezgodności.</span><span class="sxs-lookup"><span data-stu-id="7c950-110">You can also print a nonconformance tag for a nonconformance.</span></span> <span data-ttu-id="7c950-111">W tym raporcie jest pokazana przypisana strefa kwarantanny wraz ze wskazówkami postępowania z wadliwymi materiałami.</span><span class="sxs-lookup"><span data-stu-id="7c950-111">This report shows the assigned quarantine zone and information about usage to provide guidance about how defective material should be handled.</span></span> <span data-ttu-id="7c950-112">Strefy kwarantanny mogą odpowiadać lokalizacjom magazynowym lub zasobom operacyjnym.</span><span class="sxs-lookup"><span data-stu-id="7c950-112">The quarantine zones might correspond to inventory locations or operations resources.</span></span>

## <a name="examples-of-quarantine-zones"></a><span data-ttu-id="7c950-113">Przykładowe strefy kwarantanny</span><span class="sxs-lookup"><span data-stu-id="7c950-113">Examples of quarantine zones</span></span>

### <a name="example-1"></a><span data-ttu-id="7c950-114">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="7c950-114">Example 1</span></span>

<span data-ttu-id="7c950-115">Pracujesz w firmie, która produkuje i rozprowadza telewizory, głośniki i odtwarzacze multimedialne.</span><span class="sxs-lookup"><span data-stu-id="7c950-115">You work at an electronics manufacturing company that produces and distributes televisions, speakers, and media players.</span></span> <span data-ttu-id="7c950-116">W takim przypadku można skonfigurować strefy kwarantanny reprezentujące poszczególne typy produktu.</span><span class="sxs-lookup"><span data-stu-id="7c950-116">In this case, you can configure a quarantine zone to represent each type of product.</span></span>

### <a name="example-2"></a><span data-ttu-id="7c950-117">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="7c950-117">Example 2</span></span>

<span data-ttu-id="7c950-118">Trzy pojemniki i dwa regały służą do przechowywania towarów, które wykazują niezgodności.</span><span class="sxs-lookup"><span data-stu-id="7c950-118">Three bins and two racks are used to store items that are nonconforming.</span></span> <span data-ttu-id="7c950-119">W takim przypadku można skonfigurować pięć stref kwarantanny, po jednej dla każdego pojemnika i każdego regału.</span><span class="sxs-lookup"><span data-stu-id="7c950-119">In this case, you can configure five quarantine zones, one for each bin and each rack.</span></span>

## <a name="create-a-quarantine-zone"></a><span data-ttu-id="7c950-120">Tworzenie strefy kwarantanny</span><span class="sxs-lookup"><span data-stu-id="7c950-120">Create a quarantine zone</span></span>

1. <span data-ttu-id="7c950-121">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Strefy kwarantanny**.</span><span class="sxs-lookup"><span data-stu-id="7c950-121">Go to **Inventory management \> Setup \> Quality management \> Quarantine zones**.</span></span>
1. <span data-ttu-id="7c950-122">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="7c950-122">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="7c950-123">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="7c950-123">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="7c950-124">**Strefa kwarantanny** — służy do wprowadzania unikatowego identyfikatora lub nazwy strefy kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="7c950-124">**Quarantine zone** – Enter a unique ID or name for the quarantine zone.</span></span>
    - <span data-ttu-id="7c950-125">**Opis** – wprowadź szczegółowy opis strefy kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="7c950-125">**Description** – Enter a detailed description of the quarantine zone.</span></span>

1. <span data-ttu-id="7c950-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7c950-126">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c950-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7c950-127">Additional resources</span></span>

- [<span data-ttu-id="7c950-128">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="7c950-128">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="7c950-129">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="7c950-129">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="7c950-130">Pracownicy odpowiedzialni za zatwierdzanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="7c950-130">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="7c950-131">Typy problemów w niezgodnościach</span><span class="sxs-lookup"><span data-stu-id="7c950-131">Problem types for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="7c950-132">Typy diagnostyki niezgodności</span><span class="sxs-lookup"><span data-stu-id="7c950-132">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="7c950-133">Opłaty związane z kontrolą jakości dla niezgodności</span><span class="sxs-lookup"><span data-stu-id="7c950-133">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="7c950-134">Operacje dotyczące niezgodności</span><span class="sxs-lookup"><span data-stu-id="7c950-134">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="7c950-135">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="7c950-135">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
