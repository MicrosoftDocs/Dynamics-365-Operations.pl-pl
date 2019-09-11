---
title: Omówienie zasad pracy magazynowej
description: Zasady kontroli pracy magazynowej określają, czy praca magazynowa jest tworzona przez procesy magazynowe na produkcji w oparciu o typ zlecenia pracy, lokalizację zapasów i produkt.
author: johanhoffmann
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0a9e05fd2a08921d2718fc239afd56a957f80915
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865119"
---
# <a name="warehouse-work-policies-overview"></a><span data-ttu-id="12c43-103">Omówienie zasad pracy magazynowej</span><span class="sxs-lookup"><span data-stu-id="12c43-103">Warehouse work policies overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12c43-104">Zasady kontroli pracy magazynowej w programie Microsoft Dynamics 365 for Finance and Operations określają, czy praca magazynowa jest tworzona przez procesy magazynowe na produkcji w oparciu o typ zlecenia pracy, lokalizację zapasów i produkt.</span><span class="sxs-lookup"><span data-stu-id="12c43-104">Warehouse work policies in Microsoft Dynamics 365 for Finance and Operations control whether warehouse work is created by warehouse processes in manufacturing, based on work order type, inventory location, and product.</span></span>

<span data-ttu-id="12c43-105">Ta zasada pracy kontroluje, czy praca magazynowa jest tworzona dla procesów magazynu w produkcji.</span><span class="sxs-lookup"><span data-stu-id="12c43-105">This work policy controls whether warehouse work is created for warehouse processes in manufacturing.</span></span> <span data-ttu-id="12c43-106">Zasadę pracy można skonfigurować przy użyciu kombinacji **typów zleceń**, **lokalizacji zapasów** i **produktu**.</span><span class="sxs-lookup"><span data-stu-id="12c43-106">You can set up the work policy by using a combination of **work order types**, an **inventory location**, and a **product**.</span></span> <span data-ttu-id="12c43-107">Na przykład produkt L0101 jest zgłoszony jako ukończony do lokalizacji wyjściowej 001.</span><span class="sxs-lookup"><span data-stu-id="12c43-107">For example, product L0101 is reported as finished to output location 001.</span></span> <span data-ttu-id="12c43-108">Gotowy produkt jest później zużywany na podstawie innego zlecenia produkcyjnego w lokalizacji wyjściowej 001.</span><span class="sxs-lookup"><span data-stu-id="12c43-108">The finished good is later consumed in another production order at output location 001.</span></span> <span data-ttu-id="12c43-109">W takim przypadku można skonfigurować zasadę pracy, która uniemożliwi tworzenie pracy odkładania wyrobów gotowych, gdy produkt L0101 zostanie zgłoszony jako gotowy do lokalizacji wyjściowej 001.</span><span class="sxs-lookup"><span data-stu-id="12c43-109">In this case, you can set up a work policy to prevent the work for finished goods put-away from being created when you report product L0101 as finished to output location 001.</span></span> <span data-ttu-id="12c43-110">Zasada pracy jest osobną jednostką, którą można opisać za pomocą następujących informacji:</span><span class="sxs-lookup"><span data-stu-id="12c43-110">The work policy is an individual entity that can be described through the following information:</span></span>

-   <span data-ttu-id="12c43-111">**Nazwa zasady pracy**(unikatowy identyfikator zasady pracy)</span><span class="sxs-lookup"><span data-stu-id="12c43-111">**Work policy name** (the unique identifier of the work policy)</span></span>
-   <span data-ttu-id="12c43-112">**Typy zleceń** i **Metoda tworzenia pracy**</span><span class="sxs-lookup"><span data-stu-id="12c43-112">**Work order types** and **Work creation method**</span></span>
-   <span data-ttu-id="12c43-113">**Magazyny**</span><span class="sxs-lookup"><span data-stu-id="12c43-113">**Inventory locations**</span></span>
-   <span data-ttu-id="12c43-114">**Produkty**</span><span class="sxs-lookup"><span data-stu-id="12c43-114">**Products**</span></span>

## <a name="work-order-types"></a><span data-ttu-id="12c43-115">Typy zleceń</span><span class="sxs-lookup"><span data-stu-id="12c43-115">Work order types</span></span>
<span data-ttu-id="12c43-116">Możesz wybrać spośród następujących typów zleceń:</span><span class="sxs-lookup"><span data-stu-id="12c43-116">You can select the following work order types:</span></span>

-   <span data-ttu-id="12c43-117">Ukończono odkładanie wyrobów</span><span class="sxs-lookup"><span data-stu-id="12c43-117">Finished goods put away</span></span>
-   <span data-ttu-id="12c43-118">Odłożenie produktu ubocznego i produktu towarzyszącego</span><span class="sxs-lookup"><span data-stu-id="12c43-118">Co-product and by-product put away</span></span>
-   <span data-ttu-id="12c43-119">Pobranie surowca</span><span class="sxs-lookup"><span data-stu-id="12c43-119">Raw material picking</span></span>

<span data-ttu-id="12c43-120">Pole **Metoda tworzenia pracy** ma wartość **Nigdy**.</span><span class="sxs-lookup"><span data-stu-id="12c43-120">The **Work creation method** field has the value **Never**.</span></span> <span data-ttu-id="12c43-121">Ta wartość wskazuje, że zasada pracy uniemożliwi tworzenie pracy magazynowej dla wybranego typu zlecenia.</span><span class="sxs-lookup"><span data-stu-id="12c43-121">This value indicates that the work policy will prevent warehouse work from being created for the selected work order type.</span></span>

## <a name="inventory-locations"></a><span data-ttu-id="12c43-122">Magazyny</span><span class="sxs-lookup"><span data-stu-id="12c43-122">Inventory locations</span></span>
<span data-ttu-id="12c43-123">Można wybrać lokalizację, do której ma zastosowanie zasada pracy.</span><span class="sxs-lookup"><span data-stu-id="12c43-123">You can select a location that the work policy applies to.</span></span> <span data-ttu-id="12c43-124">Jeśli z zasadą pracy nie zostanie skojarzona żadna lokalizacja, zasada nie ma zastosowania do żadnych procesów.</span><span class="sxs-lookup"><span data-stu-id="12c43-124">If no location is associated with a work policy, the work policy doesn’t apply to any processes.</span></span> <span data-ttu-id="12c43-125">Na stronie **Lokalizacje** można również zaznaczyć lub usunąć zaznaczenie zasady pracy dla określonej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="12c43-125">On the **Locations** page, you can also select or cancel the selection of the work policy for a specific location.</span></span>

## <a name="products"></a><span data-ttu-id="12c43-126">Produkty</span><span class="sxs-lookup"><span data-stu-id="12c43-126">Products</span></span>
<span data-ttu-id="12c43-127">Można wybrać produkt, do którego ma zastosowanie zasada pracy.</span><span class="sxs-lookup"><span data-stu-id="12c43-127">You can select a product that the work policy applies to.</span></span> <span data-ttu-id="12c43-128">Zasada pracy może dotyczyć wszystkich produktów lub wybranych produktów.</span><span class="sxs-lookup"><span data-stu-id="12c43-128">You can apply the work policy to either all products or selected products.</span></span>

## <a name="example"></a><span data-ttu-id="12c43-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="12c43-129">Example</span></span>
<span data-ttu-id="12c43-130">W poniższym przykładzie istnieją dwa zlecenia produkcyjne, PRD-001 i PRD 00*2*.</span><span class="sxs-lookup"><span data-stu-id="12c43-130">In the following example, there are two production orders, PRD-001 and PRD-00*2*.</span></span> <span data-ttu-id="12c43-131">Zlecenie produkcyjne PRD-001 zawiera operację o nazwie **Montaż**, z której produkt SC1 jest zgłaszany jako gotowy do lokalizacji O1.</span><span class="sxs-lookup"><span data-stu-id="12c43-131">Production order PRD-001 has an operation that is named **Assembly**, where product SC1 is being reported as finished to location O1.</span></span> <span data-ttu-id="12c43-132">Zlecenie produkcyjne PRD-002 ma operację o nazwie **Malowanie** i zużywa produkt SC1 z lokalizacji O1.</span><span class="sxs-lookup"><span data-stu-id="12c43-132">Production order PRD-002 has an operation that is named **Painting** and consumes product SC1 from location O1.</span></span> <span data-ttu-id="12c43-133">Zlecenie produkcyjne PRD-002 zużywa także surowiec RM1 z lokalizacji O1.</span><span class="sxs-lookup"><span data-stu-id="12c43-133">Production order PRD-002 also consumes raw material RM1 from location O1.</span></span> <span data-ttu-id="12c43-134">Surowiec RM1 jest przechowywany w lokalizacji magazynowej BULK-001 i zostanie pobrany do lokalizacji O1 za pomocą pracy magazynowej pobrania materiału.</span><span class="sxs-lookup"><span data-stu-id="12c43-134">RM1 is stored in warehouse location BULK-001 and will be picked to location O1 by warehouse work for raw material picking.</span></span> <span data-ttu-id="12c43-135">Praca pobierania jest generowana po zwolnieniu produkcji PRD-002.</span><span class="sxs-lookup"><span data-stu-id="12c43-135">The picking work is generated when production PRD-002 is released.</span></span> 

<span data-ttu-id="12c43-136">[![Zasady pracy magazynowej](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span><span class="sxs-lookup"><span data-stu-id="12c43-136">[![Warehouse work policies](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span></span> 

<span data-ttu-id="12c43-137">Planując skonfigurowanie zasady pracy magazynowej dla tego scenariusza, należy uwzględnić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="12c43-137">When you plan to configure a warehouse work policy for this scenario, you should consider the following information:</span></span>

-   <span data-ttu-id="12c43-138">Praca magazynowa odłożenia wyrobów gotowych nie jest wymagana, jeżeli zgłaszasz produkt SC1 jako gotowy ze zlecenia produkcyjnego PRD-001 do lokalizacji O1.</span><span class="sxs-lookup"><span data-stu-id="12c43-138">Warehouse work for finished goods put-away isn’t required when you report product SC1 as finished from production order PRD-001 to location O1.</span></span> <span data-ttu-id="12c43-139">Wynika to z faktu, że operacja **Malowanie** dla zlecenia produkcyjnego PRD-002 zużywa produkt SC1 w tej samej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="12c43-139">This is because the **Painting** operation for production order PRD-002 consumes SC1 at the same location.</span></span>
-   <span data-ttu-id="12c43-140">Praca magazynowa pobrania surowca jest wymagana w celu przeniesienia surowca RM1 z lokalizacji magazynowej BULK-001 do lokalizacji O1.</span><span class="sxs-lookup"><span data-stu-id="12c43-140">Warehouse work for raw material picking is required in order to move raw material RM1 from warehouse location BULK-001 to location O1.</span></span>

<span data-ttu-id="12c43-141">Oto przykład zasady pracy, którą można skonfigurować z uwzględnieniem powyższych informacji.</span><span class="sxs-lookup"><span data-stu-id="12c43-141">Here is an example of the work policy that you can set up, based on these considerations.</span></span>


|                                       |                                       |
|---------------------------------------|---------------------------------------|
| <span data-ttu-id="12c43-142"><strong>Nazwa zasady pracy</strong></span><span class="sxs-lookup"><span data-stu-id="12c43-142"><strong>Work policy name</strong></span></span><br> | <span data-ttu-id="12c43-143"><strong>Typy zleceń</strong></span><span class="sxs-lookup"><span data-stu-id="12c43-143"><strong>Work order types</strong></span></span><br> |
|         <span data-ttu-id="12c43-144">Bez odłożenia 01     \`</span><span class="sxs-lookup"><span data-stu-id="12c43-144">No put away 01     \`</span></span>          |     <span data-ttu-id="12c43-145">- Odłożenie gotowego wyrobu</span><span class="sxs-lookup"><span data-stu-id="12c43-145">- Finished good put away</span></span><br>      |
|                                       |    <span data-ttu-id="12c43-146"><strong>Lokalizacje</strong></span><span class="sxs-lookup"><span data-stu-id="12c43-146"><strong>Locations</strong></span></span><br>     |
|                                       |                 <span data-ttu-id="12c43-147">- O1</span><span class="sxs-lookup"><span data-stu-id="12c43-147">- O1</span></span>                  |
|                                       |    <span data-ttu-id="12c43-148"><strong>Produkty</strong></span><span class="sxs-lookup"><span data-stu-id="12c43-148"><strong>Products</strong></span></span> <br>     |
|                                       |                 <span data-ttu-id="12c43-149">- SC1</span><span class="sxs-lookup"><span data-stu-id="12c43-149">- SC1</span></span>                 |

<span data-ttu-id="12c43-150">Poniższe procedury zawierają instrukcje krok po kroku dotyczące konfigurowania zasady pracy magazynowej dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="12c43-150">The following procedures provide step-by-step instructions about how to set up the warehouse work policy for this scenario.</span></span> <span data-ttu-id="12c43-151">Opisano również przykładową konfigurację prezentującą zgłaszanie zlecenia produkcyjnego jako gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="12c43-151">A sample setup showing how to report a production order as finished to a location that isn’t license plate–controlled is also described.</span></span>

## <a name="set-up-a-warehouse-work-policy"></a><span data-ttu-id="12c43-152">Konfigurowanie zasady pracy magazynowej</span><span class="sxs-lookup"><span data-stu-id="12c43-152">Set up a warehouse work policy</span></span>
<span data-ttu-id="12c43-153">Procesy magazynowe nie zawsze obejmują pracę magazynową.</span><span class="sxs-lookup"><span data-stu-id="12c43-153">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="12c43-154">Poprzez zdefiniowanie pracy magazynowej można zablokować tworzenie pracy pobierania surowców i odkładania wyrobów gotowych dla zbioru produktów w określonych lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="12c43-154">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="12c43-155">Do stworzenia tej procedury wykorzystano dane z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="12c43-155">The USMF demo data company was used to create this procedure.</span></span> 

<span data-ttu-id="12c43-156">KROKI (21)</span><span class="sxs-lookup"><span data-stu-id="12c43-156">STEPS (21)</span></span>

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| <span data-ttu-id="12c43-157">1.</span><span class="sxs-lookup"><span data-stu-id="12c43-157">1.</span></span>  | <span data-ttu-id="12c43-158">Wybierz kolejno opcje Zarządzanie magazynem &gt; Ustawienia &gt; Praca &gt; Zasady pracy.</span><span class="sxs-lookup"><span data-stu-id="12c43-158">Go to Warehouse management &gt; Setup &gt; Work &gt; Work policies.</span></span>        |
| <span data-ttu-id="12c43-159">2.</span><span class="sxs-lookup"><span data-stu-id="12c43-159">2.</span></span>  | <span data-ttu-id="12c43-160">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="12c43-160">Click New.</span></span>                                                                 |
| <span data-ttu-id="12c43-161">3.</span><span class="sxs-lookup"><span data-stu-id="12c43-161">3.</span></span>  | <span data-ttu-id="12c43-162">W polu Nazwa zasady pracy wpisz „Bez pracy odłożenia”.</span><span class="sxs-lookup"><span data-stu-id="12c43-162">In the Work policy name field, type 'No put-away work'.</span></span>                    |
| <span data-ttu-id="12c43-163">4.</span><span class="sxs-lookup"><span data-stu-id="12c43-163">4.</span></span>  | <span data-ttu-id="12c43-164">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="12c43-164">Click Save.</span></span>                                                                |
| <span data-ttu-id="12c43-165">5.</span><span class="sxs-lookup"><span data-stu-id="12c43-165">5.</span></span>  | <span data-ttu-id="12c43-166">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="12c43-166">Click Add.</span></span>                                                                 |
| <span data-ttu-id="12c43-167">6.</span><span class="sxs-lookup"><span data-stu-id="12c43-167">6.</span></span>  | <span data-ttu-id="12c43-168">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="12c43-168">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="12c43-169">7.</span><span class="sxs-lookup"><span data-stu-id="12c43-169">7.</span></span>  | <span data-ttu-id="12c43-170">W polu Typ zlecenia wybierz wartość „Ukończono odkładanie wyrobów”.</span><span class="sxs-lookup"><span data-stu-id="12c43-170">In the Work order type field, select 'Finished goods put away'.</span></span>            |
| <span data-ttu-id="12c43-171">8.</span><span class="sxs-lookup"><span data-stu-id="12c43-171">8.</span></span>  | <span data-ttu-id="12c43-172">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="12c43-172">Click Add.</span></span>                                                                 |
| <span data-ttu-id="12c43-173">9.</span><span class="sxs-lookup"><span data-stu-id="12c43-173">9.</span></span>  | <span data-ttu-id="12c43-174">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="12c43-174">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="12c43-175">10.</span><span class="sxs-lookup"><span data-stu-id="12c43-175">10.</span></span> | <span data-ttu-id="12c43-176">W polu Typ zlecenia wybierz opcję „Odłożenie produktu ubocznego i produktu towarzyszącego”.</span><span class="sxs-lookup"><span data-stu-id="12c43-176">In the Work order type field, select 'Co-product and by-product put away'.</span></span> |
| <span data-ttu-id="12c43-177">11.</span><span class="sxs-lookup"><span data-stu-id="12c43-177">11.</span></span> | <span data-ttu-id="12c43-178">Rozwiń sekcję Magazyny.</span><span class="sxs-lookup"><span data-stu-id="12c43-178">Expand the Inventory locations section.</span></span>                                    |
| <span data-ttu-id="12c43-179">12.</span><span class="sxs-lookup"><span data-stu-id="12c43-179">12.</span></span> | <span data-ttu-id="12c43-180">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="12c43-180">Click Add.</span></span>                                                                 |
| <span data-ttu-id="12c43-181">13.</span><span class="sxs-lookup"><span data-stu-id="12c43-181">13.</span></span> | <span data-ttu-id="12c43-182">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="12c43-182">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="12c43-183">14.</span><span class="sxs-lookup"><span data-stu-id="12c43-183">14.</span></span> | <span data-ttu-id="12c43-184">Na liście magazynów wpisz „51”.</span><span class="sxs-lookup"><span data-stu-id="12c43-184">In the Warehouse list, enter '51'.</span></span>                                         |
| <span data-ttu-id="12c43-185">15.</span><span class="sxs-lookup"><span data-stu-id="12c43-185">15.</span></span> | <span data-ttu-id="12c43-186">W polu Lokalizacja wprowadź lub wybierz wartość „001”.</span><span class="sxs-lookup"><span data-stu-id="12c43-186">In the Location field, enter or select '001'.</span></span>                              |
| <span data-ttu-id="12c43-187">16.</span><span class="sxs-lookup"><span data-stu-id="12c43-187">16.</span></span> | <span data-ttu-id="12c43-188">Rozwiń sekcję Produkty.</span><span class="sxs-lookup"><span data-stu-id="12c43-188">Expand the Products section.</span></span>                                               |
| <span data-ttu-id="12c43-189">17.</span><span class="sxs-lookup"><span data-stu-id="12c43-189">17.</span></span> | <span data-ttu-id="12c43-190">W polu Wybór produktu wybierz opcję „Wybrane”.</span><span class="sxs-lookup"><span data-stu-id="12c43-190">In the Product selection field, select 'Selected'.</span></span>                         |
| <span data-ttu-id="12c43-191">18.</span><span class="sxs-lookup"><span data-stu-id="12c43-191">18.</span></span> | <span data-ttu-id="12c43-192">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="12c43-192">Click Add.</span></span>                                                                 |
| <span data-ttu-id="12c43-193">19.</span><span class="sxs-lookup"><span data-stu-id="12c43-193">19.</span></span> | <span data-ttu-id="12c43-194">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="12c43-194">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="12c43-195">20.</span><span class="sxs-lookup"><span data-stu-id="12c43-195">20.</span></span> | <span data-ttu-id="12c43-196">W polu Numer pozycji wprowadź lub wybierz wartość „L0101”.</span><span class="sxs-lookup"><span data-stu-id="12c43-196">In the Item number field, enter or select 'L0101'.</span></span>                         |
| <span data-ttu-id="12c43-197">21.</span><span class="sxs-lookup"><span data-stu-id="12c43-197">21.</span></span> | <span data-ttu-id="12c43-198">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="12c43-198">Click Save.</span></span>                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a><span data-ttu-id="12c43-199">Zgłaszanie zlecenia produkcyjnego jako gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny</span><span class="sxs-lookup"><span data-stu-id="12c43-199">Report a production order as finished to a location that isn’t license plate–controlled</span></span>
<span data-ttu-id="12c43-200">Ta procedura zawiera przykład zgłaszania wyrobu gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="12c43-200">This procedure shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="12c43-201">Warunkiem wstępnym tego zadania jest istnienie odpowiedniej zasady pracy.</span><span class="sxs-lookup"><span data-stu-id="12c43-201">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="12c43-202">Poprzednia procedura ilustruje konfigurowanie zasady pracy.</span><span class="sxs-lookup"><span data-stu-id="12c43-202">The previous procedure shows the setup of the work policy.</span></span> 

<span data-ttu-id="12c43-203">KROKI (25)</span><span class="sxs-lookup"><span data-stu-id="12c43-203">STEPS (25)</span></span>

<table>
<tbody>
<tr>
<td colspan="3"><span data-ttu-id="12c43-204"><strong>Podzadanie: Konfigurowanie lokalizacji wyjściowej.</strong></span><span class="sxs-lookup"><span data-stu-id="12c43-204"><strong>Sub-task: Set up an output location.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="12c43-205">Wybierz kolejno opcje Administrowanie organizacją &gt; Zasoby &gt; Grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="12c43-205">Go to Organization administration &gt; Resources &gt; Resource groups.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="12c43-206">Na liście zaznacz grupę zasobów &#39;5102&#39;.</span><span class="sxs-lookup"><span data-stu-id="12c43-206">In the list, select resource group &#39;5102&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="12c43-207">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="12c43-207">Click Edit.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="12c43-208">W polu Magazyn wyjściowy wpisz &#39;51&#39;.</span><span class="sxs-lookup"><span data-stu-id="12c43-208">In the Output warehouse field, enter &#39;51&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="12c43-209">W polu Lokalizacja wyjściowa wpisz &#39;001&#39;.</span><span class="sxs-lookup"><span data-stu-id="12c43-209">In the Output location field, enter &#39;001&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="12c43-210">Lokalizacja 001 nie jest lokalizacją kontrolowaną przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="12c43-210">Location 001 isn&#39;t a license plate–controlled location.</span></span> <span data-ttu-id="12c43-211">Można skonfigurować lokalizację wyjściową niekontrolowaną za pomocą numeru identyfikacyjnego, ale tylko wtedy, gdy istnieje odpowiednia zasada pracy dla lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="12c43-211">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span></td>
</tr>
<tr>
<td colspan="3"><span data-ttu-id="12c43-212"><strong>Podzadanie: Tworzenie zlecenia produkcyjnego i zgłaszanie go jako gotowego.</strong></span><span class="sxs-lookup"><span data-stu-id="12c43-212"><strong>Sub-task: Create a production order and report it as finished.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="12c43-213">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="12c43-213">Close the page.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="12c43-214">Wybierz kolejno opcje Kontrola produkcji &gt; Zlecenia produkcyjne &gt; Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="12c43-214">Go to Production control &gt; Production orders &gt; All production orders.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="12c43-215">Kliknij opcję Nowe zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="12c43-215">Click New production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="12c43-216">W polu Numer pozycji wpisz &#39;L0101&#39;.</span><span class="sxs-lookup"><span data-stu-id="12c43-216">In the Item number field, enter &#39;L0101&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="12c43-217">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="12c43-217">Click Create.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="12c43-218">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="12c43-218">On the Action Pane, click Production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td><span data-ttu-id="12c43-219">Kliknij przycisk Szacuj.</span><span class="sxs-lookup"><span data-stu-id="12c43-219">Click Estimate.</span></span></td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td><span data-ttu-id="12c43-220">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="12c43-220">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td><span data-ttu-id="12c43-221">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="12c43-221">Click Start.</span></span></td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td><span data-ttu-id="12c43-222">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="12c43-222">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td><span data-ttu-id="12c43-223">W polu Automatyczne zużycie BOM zaznacz opcję &#39;Nigdy&#39;.</span><span class="sxs-lookup"><span data-stu-id="12c43-223">In the Automatic BOM consumption field, select &#39;Never&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td><span data-ttu-id="12c43-224">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="12c43-224">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td><span data-ttu-id="12c43-225">Po zakończeniu kliknij opcję Raport.</span><span class="sxs-lookup"><span data-stu-id="12c43-225">Click Report as finished.</span></span></td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td><span data-ttu-id="12c43-226">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="12c43-226">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td><span data-ttu-id="12c43-227">W polu Akceptacja błędu wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="12c43-227">Select Yes in the Accept error field.</span></span></td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td><span data-ttu-id="12c43-228">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="12c43-228">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td><span data-ttu-id="12c43-229">W okienku akcji kliknij pozycję Magazyn.</span><span class="sxs-lookup"><span data-stu-id="12c43-229">On the Action Pane, click Warehouse.</span></span></td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td><span data-ttu-id="12c43-230">Kliknij opcję Szczegóły pracy.</span><span class="sxs-lookup"><span data-stu-id="12c43-230">Click Work details.</span></span></td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td><span data-ttu-id="12c43-231">Po zgłoszeniu zlecenia produkcyjnego jako gotowego nie została wygenerowana żadna praca odłożenia.</span><span class="sxs-lookup"><span data-stu-id="12c43-231">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="12c43-232">Dzieje się tak, ponieważ zdefiniowano zasadę pracy, która blokuje generowanie pracy, gdy produkt L0101 jest zgłaszany jako gotowy do lokalizacji 001.</span><span class="sxs-lookup"><span data-stu-id="12c43-232">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span></td>
</tr>
</tbody>
</table>



