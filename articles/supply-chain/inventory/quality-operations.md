---
title: Operacje dotyczące niezgodności
description: W tym temacie opisano sposób tworzenia i używania operacji dotyczących niezgodności.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6454a56323ea66369696dd6e3310a41b4eb9ee58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956795"
---
# <a name="operations-for-nonconformances"></a><span data-ttu-id="c918a-103">Operacje dotyczące niezgodności</span><span class="sxs-lookup"><span data-stu-id="c918a-103">Operations for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c918a-104">W tym temacie opisano sposób tworzenia i używania operacji dotyczących niezgodności.</span><span class="sxs-lookup"><span data-stu-id="c918a-104">This topic describes how to create and use operations for nonconformances.</span></span>

<span data-ttu-id="c918a-105">Za pomocą strony **Operacje** można zdefiniować klasyfikacje pracy, którą można wykonać dla zatwierdzonej niezgodności.</span><span class="sxs-lookup"><span data-stu-id="c918a-105">You can use the **Operations** page to define classifications of the work that can be performed for an approved nonconformance.</span></span> <span data-ttu-id="c918a-106">Przypisując operację pokrewną do niezgodności, można również zdefiniować szczegóły, jak powiązany materiał, godziny robocizny i opłaty wymagane do wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="c918a-106">When you assign a related operation to a nonconformance, you can provide details such as the associated material, labor hours, and charges that are required to do the operation.</span></span> <span data-ttu-id="c918a-107">Ta informacja służy systemowi do obliczania szacowanego kosztu operacji.</span><span class="sxs-lookup"><span data-stu-id="c918a-107">The system uses this information to calculate an estimated cost for the operation.</span></span> <span data-ttu-id="c918a-108">Informacje szczegółowe i szacowane koszty mają charakter odnośnikowy.</span><span class="sxs-lookup"><span data-stu-id="c918a-108">The detailed information and estimated costs are for reference.</span></span> <span data-ttu-id="c918a-109">Operacje pokrewne dla jakości różnią się od operacji, które można zdefiniować dla marszruty produkcji.</span><span class="sxs-lookup"><span data-stu-id="c918a-109">The related operations for quality differ from the operations that can be defined for a production route.</span></span>

> [!NOTE]
> <span data-ttu-id="c918a-110">Chociaż można śledzić koszty, czas i towary używane w operacji związanej z niezgodnością, wprowadzone dane mają wyłącznie informacyjny charakter.</span><span class="sxs-lookup"><span data-stu-id="c918a-110">Although you can track costs, time, and the items that are used in an operation that is related to a nonconformance, the data that you enter is only informational.</span></span> <span data-ttu-id="c918a-111">Nie są automatycznie integrowane z księgą główną, księgą podrzędną zapasów lub modułem **Czas i frekwencja**.</span><span class="sxs-lookup"><span data-stu-id="c918a-111">It isn't automatically integrated with the general ledger, inventory subledger, or the **Time and attendance** module.</span></span>

## <a name="examples-of-operations"></a><span data-ttu-id="c918a-112">Przykłady operacji</span><span class="sxs-lookup"><span data-stu-id="c918a-112">Examples of operations</span></span>

<span data-ttu-id="c918a-113">Pracujesz dla firmy produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="c918a-113">You work for a manufacturing company.</span></span> <span data-ttu-id="c918a-114">Utworzono i zatwierdzono niezgodność dla towarów, które nie przeszły testu jakości.</span><span class="sxs-lookup"><span data-stu-id="c918a-114">A nonconformance was created and approved for items that failed a quality test.</span></span> <span data-ttu-id="c918a-115">Utworzono korektę wskazującą, że problem był związany z wadliwym łożyskiem w maszynie.</span><span class="sxs-lookup"><span data-stu-id="c918a-115">A correction was created to indicate that the problem was related to a bad bearing on a machine.</span></span> <span data-ttu-id="c918a-116">Wymiana łożyska wymaga wykonania kilku czynności, a odpowiedzialność za każdą operację jest śledzona.</span><span class="sxs-lookup"><span data-stu-id="c918a-116">Several steps are required to replace the bearing, and the responsibility for each operation is tracked.</span></span> <span data-ttu-id="c918a-117">Mogą być na przykład wymagane następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="c918a-117">For example, the following steps might be required:</span></span>

1. <span data-ttu-id="c918a-118">Zatrzymanie linii produkcyjnej i przeprowadzenie procedury czyszczenia.</span><span class="sxs-lookup"><span data-stu-id="c918a-118">The production line is stopped, and the clean-out routine is performed.</span></span>
1. <span data-ttu-id="c918a-119">Wymiana łożyska przez serwis.</span><span class="sxs-lookup"><span data-stu-id="c918a-119">Maintenance personnel replace the bearing.</span></span>
1. <span data-ttu-id="c918a-120">Inspekcja maszyny przez personel zapewnienia jakości przed włączeniem z powrotem maszyny.</span><span class="sxs-lookup"><span data-stu-id="c918a-120">Quality assurance personnel inspect the machine before it's turned back on.</span></span>

<span data-ttu-id="c918a-121">W tym przykładzie można utworzyć następujące operacje reprezentujące pracę, która musi zostać wykonana:</span><span class="sxs-lookup"><span data-stu-id="c918a-121">For this example, the following operations can be created to represent the work that must be done:</span></span>

- <span data-ttu-id="c918a-122">Zatrzymaj linię produkcyjną.</span><span class="sxs-lookup"><span data-stu-id="c918a-122">Stop the production line.</span></span>
- <span data-ttu-id="c918a-123">Oczyść linię produkcyjną.</span><span class="sxs-lookup"><span data-stu-id="c918a-123">Clean out the production line.</span></span>
- <span data-ttu-id="c918a-124">Wykonaj konserwację maszyny.</span><span class="sxs-lookup"><span data-stu-id="c918a-124">Perform machine maintenance.</span></span>
- <span data-ttu-id="c918a-125">Skontroluj maszynę.</span><span class="sxs-lookup"><span data-stu-id="c918a-125">Inspect the machine.</span></span>

## <a name="create-an-operation"></a><span data-ttu-id="c918a-126">Tworzenie operacji</span><span class="sxs-lookup"><span data-stu-id="c918a-126">Create an operation</span></span>

1. <span data-ttu-id="c918a-127">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Operacje**.</span><span class="sxs-lookup"><span data-stu-id="c918a-127">Go to **Inventory management \> Setup \> Quality management \> Operations**.</span></span>
1. <span data-ttu-id="c918a-128">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="c918a-128">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="c918a-129">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="c918a-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="c918a-130">**Operacja** — umożliwia wprowadzenie unikatowego identyfikatora lub nazwy operacji.</span><span class="sxs-lookup"><span data-stu-id="c918a-130">**Operation** – Enter a unique ID or name for the operation.</span></span>
    - <span data-ttu-id="c918a-131">**Opis** – wprowadź szczegółowy opis operacji.</span><span class="sxs-lookup"><span data-stu-id="c918a-131">**Description** – Enter a detailed description of the operation.</span></span>
    - <span data-ttu-id="c918a-132">**Typ** — jeśli operacja może być używana tylko z niezgodnościami związanymi z określonym typem zamówienia, należy wybrać typ zamówienia (*Zamówienie zakupu* lub *Zamówienie sprzedaży)*.</span><span class="sxs-lookup"><span data-stu-id="c918a-132">**Type** – If the operation can be used only with nonconformances that are related to a specific type of order, select the order type (*Purchase order* or *Sales order*).</span></span>

1. <span data-ttu-id="c918a-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c918a-133">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c918a-134">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c918a-134">Additional resources</span></span>

- [<span data-ttu-id="c918a-135">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="c918a-135">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="c918a-136">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="c918a-136">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="c918a-137">Tworzenie i przetwarzanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="c918a-137">Create and process nonconformances</span></span>](tasks/create-process-non-conformance.md)
- [<span data-ttu-id="c918a-138">Pracownicy odpowiedzialni za zatwierdzanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="c918a-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="c918a-139">Strefy kwarantanny niezgodności</span><span class="sxs-lookup"><span data-stu-id="c918a-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="c918a-140">Typy diagnostyki niezgodności</span><span class="sxs-lookup"><span data-stu-id="c918a-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="c918a-141">Opłaty związane z kontrolą jakości dla niezgodności</span><span class="sxs-lookup"><span data-stu-id="c918a-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="c918a-142">Typy problemów w niezgodnościach</span><span class="sxs-lookup"><span data-stu-id="c918a-142">Problem types for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="c918a-143">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="c918a-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
