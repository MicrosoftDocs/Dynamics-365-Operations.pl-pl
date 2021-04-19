---
title: Planowanie międzyfirmowe
description: W tym temacie opisano planowanie międzyfirmowe i wyjaśniono sposób konfigurowania planowania międzyfirmowego przy użyciu optymalizacji planowania w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5c9ab724034a9bb40cfe155b748a0c7e25978add
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833360"
---
# <a name="intercompany-planning"></a><span data-ttu-id="5e0ef-103">Planowanie międzyfirmowe</span><span class="sxs-lookup"><span data-stu-id="5e0ef-103">Intercompany planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5e0ef-104">W niektórych organizacjach operacje logistyczne zależą od innych osób prawnych (firm) w organizacji.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-104">For some organizations, logistics operations depend on other legal entities (companies) in the organization.</span></span> <span data-ttu-id="5e0ef-105">Operacje te są obsługiwane przy użyciu międzyfirmowych procesów sprzedaży i zakupów, ponieważ każda osoba prawna ma osobny plan kont.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-105">These operations are handled by using intercompany sales and purchases, because each legal entity has a separate chart of accounts.</span></span>

<span data-ttu-id="5e0ef-106">W tym temacie opisano planowanie międzyfirmowe i wyjaśniono sposób konfigurowania planowania międzyfirmowego przy użyciu optymalizacji planowania w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-106">This topic describes intercompany planning and explains how to configure intercompany planning with Planning Optimization in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="5e0ef-107">W tym temacie są używane następujące ważne terminy związane z obrotem międzyfirmowym:</span><span class="sxs-lookup"><span data-stu-id="5e0ef-107">This topic uses the following important intercompany terms:</span></span>

- <span data-ttu-id="5e0ef-108">**Od odbiorcy do dostawcy** — odwołanie względne w łańcuchu firm lub dostaw.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-108">**Upstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="5e0ef-109">Oznacza przesunięcie w kierunku dostawcy surowca.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-109">It indicates movement in the direction of the raw material supplier.</span></span>
- <span data-ttu-id="5e0ef-110">**Od dostawcy do odbiorcy** — odwołanie względne w łańcuchu firm lub dostaw.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-110">**Downstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="5e0ef-111">Oznacza przesunięcie w kierunku odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-111">It indicates movement in the direction of the customer.</span></span>
- <span data-ttu-id="5e0ef-112">**Zaplanowany popyt międzyfirmowy** — planowane zapotrzebowanie na produkt w firmie, w oparciu o planowane zapotrzebowanie na produkt w firmie podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-112">**Planned intercompany demand** – Planned demand for a product in a company, based on planned demand for the product from a downstream company.</span></span>

<span data-ttu-id="5e0ef-113">W planowaniu głównym plan jednej firmy może zawierać zaplanowany popyt międzyfirmowy związany z zamówieniami planowanymi w planie innej firmy.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-113">In master planning, a plan in one company can include planned intercompany demand that is related to planned orders from a plan in another company.</span></span> <span data-ttu-id="5e0ef-114">Jest to przydatna możliwość, ponieważ daje pełen wgląd w planowane zamówienia między firmami.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-114">This capability is useful, because it provides full visibility into planned orders across companies.</span></span> <span data-ttu-id="5e0ef-115">Ponadto zapewnia, że wszystkie wymagane planowane zamówienia podażowe są tworzone, ale bez konieczności akceptowania zamówień planowanych dla popytu międzyfirmowego.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-115">It also ensures that all required planned supply orders are created, but without requiring that planned orders be firmed for the intercompany demand.</span></span>

<span data-ttu-id="5e0ef-116">W przypadku uruchomienia planowania głównego z planu głównego, który zawiera planowany popyt od dostawcy do odbiorcy, planowane zamówienia zakupu od powiązanych dostawców międzyfirmowych będą uwzględniane w planie jako zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-116">If you run master planning from a master plan that includes planned downstream demand, planned purchase orders from the related intercompany vendors will be included in the plan as demand.</span></span>

## <a name="required-setup"></a><span data-ttu-id="5e0ef-117">Wymagana konfiguracja</span><span class="sxs-lookup"><span data-stu-id="5e0ef-117">Required setup</span></span>

<span data-ttu-id="5e0ef-118">Aby skorzystać z planowania międzyfirmowego, należy przygotować system w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="5e0ef-118">To use intercompany planning, you must prepare your system in the following way:</span></span>

1. <span data-ttu-id="5e0ef-119">Odpowiednie produkty muszą być zwolnione we wszystkich odpowiednich firmach.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-119">The relevant products must be released in all the relevant companies.</span></span> <span data-ttu-id="5e0ef-120">Aby uzyskać więcej informacji, zobacz [Konfigurowanie i używanie handlu międzyfirmowego w Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) w witrynie Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-120">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="5e0ef-121">Popyt od dostawcy do odbiorcy musi być pokryty zakupami od dostawcy, który pozostaje w relacji międzyfirmowej z firmą nadrzędną oraz odpowiednimi wymiarami magazynowymi (oddział i magazyn) odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-121">Downstream demand must be covered by purchases from a vendor that has an intercompany relation to the upstream company and relevant default inventory dimensions (site and warehouse) on the customer.</span></span> <span data-ttu-id="5e0ef-122">Aby uzyskać więcej informacji, zobacz [Konfigurowanie i używanie handlu międzyfirmowego w Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) w witrynie Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-122">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="5e0ef-123">Plan główny w firmie obsługującej przełączenie musi zawierać planowane zapotrzebowanie na zamówienie podrzędne, a odpowiednia firma i plan główny muszą być określone w planach podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-123">The master plan in the upstream company must include planned downstream demand, and the relevant company and master plan must be specified in the downstream plans.</span></span>

## <a name="include-planned-downstream-demand"></a><span data-ttu-id="5e0ef-124">Uwzględnij planowany popyt od dostawcy do odbiorcy</span><span class="sxs-lookup"><span data-stu-id="5e0ef-124">Include planned downstream demand</span></span>

<span data-ttu-id="5e0ef-125">Wykonaj poniższe kroki, aby skonfigurować swój plan główny, tak aby uwzględniał planowany popyt od dostawcy do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-125">Follow these steps to configure your master plan so that it includes planned downstream demand.</span></span>

1. <span data-ttu-id="5e0ef-126">Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-126">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="5e0ef-127">Wybierz lub utwórz plan główny.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-127">Select or create a master plan.</span></span>
1. <span data-ttu-id="5e0ef-128">Na skróconej karcie **planowania międzyfirmowego** ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="5e0ef-128">On the **Intercompany planning** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="5e0ef-129">**Uwzględnij planowany popyt od dostawcy do odbiorcy** — ustawienie tej opcji na wartość *Tak* spowoduje włączenie planowania międzyfirmowego dla planu głównego.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-129">**Include planned downstream demand** – Set this option to *Yes* to enable intercompany planning for the master plan.</span></span>
    - <span data-ttu-id="5e0ef-130">**Plany od dostawcy do odbiorcy** — w przypadku ustawienia opcji **Uwzględnij planowany popyt od dostawcy do odbiorcy** na wartość *Tak* należy użyć paska narzędzi i siatki, aby dodać żądane plany główne z innych firm.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-130">**Downstream plans** – If you set the **Include planned downstream demand** option to *Yes*, use the toolbar and grid to add the desired master plans from other companies.</span></span>

## <a name="peg-across-companies-by-using-multilevel-pegging"></a><span data-ttu-id="5e0ef-131">Ustalanie między firmami przy użyciu wielopoziomowego oznaczania transakcji</span><span class="sxs-lookup"><span data-stu-id="5e0ef-131">Peg across companies by using multilevel pegging</span></span>

<span data-ttu-id="5e0ef-132">W przypadku wielopoziomowego oznaczania transakcji można wyświetlić oznaczanie transakcji między firmami, aby zobaczyć początkowe źródło popytu, które jest objęte dostawą.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-132">In multilevel pegging, you can view pegging across companies to see the initial source of demand that is being covered by a supply.</span></span>

<span data-ttu-id="5e0ef-133">Aby wyświetlić informacje o wielopoziomowym oznaczaniu transakcji, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-133">To view multilevel pegging information, follow these steps.</span></span>

1. <span data-ttu-id="5e0ef-134">Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Zamówienia planowane**.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-134">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="5e0ef-135">Wybierz lub otwórz zamówienie planowane.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-135">Select or open a planned order.</span></span>
1. <span data-ttu-id="5e0ef-136">W okienku akcji, na karcie **Widok** w grupie **Wymagania** wybierz **Wielopoziomowe oznaczanie transakcji**.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-136">On the Action Pane, on the **View** tab, in the **Requirements** group, select **Multilevel pegging**.</span></span>

### <a name="intercompany-example-that-involves-two-companies"></a><span data-ttu-id="5e0ef-137">Przykład obrotu międzyfirmowego obejmujący dwie firmy</span><span class="sxs-lookup"><span data-stu-id="5e0ef-137">Intercompany example that involves two companies</span></span>

<span data-ttu-id="5e0ef-138">W tym przykładzie planowane zlecenie produkcyjne jest tworzone w firmie USMF w celu pokrycia zamówienia sprzedaży firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-138">For this example, a planned production order is created in the USMF company to cover a sales order in the DEMF company.</span></span> <span data-ttu-id="5e0ef-139">W firmie USMF bezpośrednie zapotrzebowanie jest zaplanowanym popytem międzyfirmowym.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-139">In USMF, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="5e0ef-140">Aby to zapotrzebowanie pojawiło się w firmie USMF, planowanie główne jest uruchamiane najpierw w firmie DEMF, a następnie w firmie USMF.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-140">To make this demand appear in USMF, master planning is run first in DEMF and then in USMF.</span></span>

<span data-ttu-id="5e0ef-141">Na poniższej ilustracji pokazano, jak ten przykład może wyglądać na stronie **Wielopoziomowe oznaczanie transakcji** dla planowanego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-141">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Przykład obrotu międzyfirmowego obejmujący dwie firmy](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a><span data-ttu-id="5e0ef-143">Przykład obrotu międzyfirmowego obejmujący trzy firmy</span><span class="sxs-lookup"><span data-stu-id="5e0ef-143">Intercompany example that involves three companies</span></span>

<span data-ttu-id="5e0ef-144">W tym przykładzie planowane zamówienie zakupu jest tworzone w firmie USMF w celu pokrycia zamówienia sprzedaży firmy FRRT.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-144">For this example, a planned purchase order is created in the USMF company to cover a sales order in the FRRT company.</span></span> <span data-ttu-id="5e0ef-145">W firmach DEMF and USMF bezpośrednie zapotrzebowanie jest zaplanowanym popytem międzyfirmowym.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-145">In the DEMF and USMF companies, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="5e0ef-146">Aby to zapotrzebowanie pojawiło się w firmie USMF, planowanie główne jest uruchamiane najpierw w firmie FRRT, następnie w firmie DEMF, a na końcu w firmie USMF.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-146">To make this demand appear in USMF, master planning is run first in FRRT, then in DEMF, and finally in USMF.</span></span>

<span data-ttu-id="5e0ef-147">Na poniższej ilustracji pokazano, jak ten przykład może wyglądać na stronie **Wielopoziomowe oznaczanie transakcji** dla planowanego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="5e0ef-147">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Przykład obrotu międzyfirmowego obejmujący trzy firmy](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]