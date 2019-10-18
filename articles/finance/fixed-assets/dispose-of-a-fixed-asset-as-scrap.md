---
title: Likwidacja środków trwałych uznanych za odpadki
description: W tym temacie opisano proces eliminowania transakcji dla środka trwałego, który został zlikwidowany jako odpadki.
author: moaamer
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: de105e061712540fc8e3d720a65c029f865b8948
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187298"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a><span data-ttu-id="a6b70-103">Likwidacja środków trwałych uznanych za odpadki</span><span class="sxs-lookup"><span data-stu-id="a6b70-103">Dispose of a fixed asset as scrap</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="a6b70-104">W tym temacie opisano proces eliminowania transakcji dla środka trwałego, który został zlikwidowany jako odpadki.</span><span class="sxs-lookup"><span data-stu-id="a6b70-104">The topic describes the process of eliminating transactions for a fixed asset that was disposed of as scrap.</span></span> <span data-ttu-id="a6b70-105">Typy transakcji, które można wyeliminować, obejmują transakcje nabycia i skumulowanej amortyzacji środka trwałego oraz inne transakcje środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="a6b70-105">The transaction types that can be eliminated include an asset's acquisition and accumulated depreciation transactions and other fixed asset transactions.</span></span> <span data-ttu-id="a6b70-106">Eliminacja tych transakcji wpływa na konta arkuszy bilansowych, takie jak korekta nabycia, korekta amortyzacji, przeszacowanie, zmniejszenie wartości i konta zmniejszenia wartości.</span><span class="sxs-lookup"><span data-stu-id="a6b70-106">Elimination of these transactions affects balance sheet accounts, such as acquisition adjustment, depreciation adjustment, revaluation, write-up, and write-down accounts.</span></span>

| <span data-ttu-id="a6b70-107">Transakcja</span><span class="sxs-lookup"><span data-stu-id="a6b70-107">Transaction</span></span>                                         | <span data-ttu-id="a6b70-108">Debet (Dr.)</span><span class="sxs-lookup"><span data-stu-id="a6b70-108">Debit (Dr.)</span></span> | <span data-ttu-id="a6b70-109">Kredyt (Cr.)</span><span class="sxs-lookup"><span data-stu-id="a6b70-109">Credit (Cr.)</span></span> |
|-----------------------------------------------------|-------------|--------------|
| <span data-ttu-id="a6b70-110">Dr. Umorzenie</span><span class="sxs-lookup"><span data-stu-id="a6b70-110">Dr. Accumulated depreciation</span></span>                        | <span data-ttu-id="a6b70-111">X</span><span class="sxs-lookup"><span data-stu-id="a6b70-111">X</span></span>           |              |
| <span data-ttu-id="a6b70-112">Cr. Zysk/strata z tytułu środków trwałych</span><span class="sxs-lookup"><span data-stu-id="a6b70-112">Cr. Fixed assets gain/loss</span></span>                          |             | <span data-ttu-id="a6b70-113">X</span><span class="sxs-lookup"><span data-stu-id="a6b70-113">X</span></span>            |
| <span data-ttu-id="a6b70-114">Dr. Zysk/strata z tytułu środków trwałych</span><span class="sxs-lookup"><span data-stu-id="a6b70-114">Dr. Fixed assets gain/loss</span></span>                          | <span data-ttu-id="a6b70-115">X</span><span class="sxs-lookup"><span data-stu-id="a6b70-115">X</span></span>           |              |
| <span data-ttu-id="a6b70-116">Cr. Konto księgowania nabycia środka trwałego</span><span class="sxs-lookup"><span data-stu-id="a6b70-116">Cr. Fixed asset acquisition account</span></span>                 |             | <span data-ttu-id="a6b70-117">X</span><span class="sxs-lookup"><span data-stu-id="a6b70-117">X</span></span>            |
| <span data-ttu-id="a6b70-118">Dr. Zysk/strata z tytułu środków trwałych (wartość księgowa netto \[NBV\])</span><span class="sxs-lookup"><span data-stu-id="a6b70-118">Dr. Fixed assets gain/loss (net book value \[NBV\])</span></span> | <span data-ttu-id="a6b70-119">X</span><span class="sxs-lookup"><span data-stu-id="a6b70-119">X</span></span>           |              |
| <span data-ttu-id="a6b70-120">Cr. Zysk/strata z tytułu środków trwałych (NBV)</span><span class="sxs-lookup"><span data-stu-id="a6b70-120">Cr. Fixed assets gain/loss (NBV)</span></span>                    |             | <span data-ttu-id="a6b70-121">X</span><span class="sxs-lookup"><span data-stu-id="a6b70-121">X</span></span>            |

> [!NOTE]
> <span data-ttu-id="a6b70-122">Zalecamy ścisłą pracę z głównym oficerem finansowym firmy lub kontrolerem w celu zidentyfikowania prawidłowych kont, które powinny być używane dla poszczególnych typów transakcji, a także sprawdzenia, czy proces likwidacji i transakcje, które generuje aktualizują te konta poprawnie.</span><span class="sxs-lookup"><span data-stu-id="a6b70-122">We recommend that you work closely with your company's chief financial officer (CFO) or controller to identify the correct accounts that should be used for each transaction type, and also to verify that the disposal process and the transactions that it generates update those accounts correctly.</span></span>

<span data-ttu-id="a6b70-123">Przed usunięciem środka trwałego jako odpadki należy utworzyć konta księgowe skojarzone z wartością nabycia środka trwałego, amortyzację dla bieżącego roku, amortyzację w latach ubiegłych oraz NBV środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="a6b70-123">Before you dispose of a fixed asset as scrap, you must create ledger accounts that are associated with the asset's acquisition value, depreciation for the current year, depreciation for previous years, and the asset's NBV.</span></span> <span data-ttu-id="a6b70-124">Typy transakcji środków trwałych są wyświetlane na stronie **Profile księgowania środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="a6b70-124">The fixed asset transaction types are listed on the **Fixed assets posting profile** page.</span></span> <span data-ttu-id="a6b70-125">Przejdź do **Środki twałe \> Ustawienia \> Profile księgowania środków trwałych**, a następnie w skróconej karcie **Likwidacja** wybierz opcję **Odpadki** w polu powyżej siatki.</span><span class="sxs-lookup"><span data-stu-id="a6b70-125">Go to **Fixed assets \> Setup \> Fixed asset posting profiles**, and then, on the **Disposal** FastTab, select **Scrap** in the field above the grid.</span></span> <span data-ttu-id="a6b70-126">Poniższa ilustracja przedstawia listę typów transakcji środków trwałych na stronie **Profile księgowania środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="a6b70-126">The following illustration shows the list of fixed asset transaction types on the **Fixed asset posting profiles** page.</span></span>


<span data-ttu-id="a6b70-127">[![Likwidacja składnika majątki jako odpadków, rys. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span><span class="sxs-lookup"><span data-stu-id="a6b70-127">[![Disposing of an asset as scap, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span></span>

<span data-ttu-id="a6b70-128">W poniższym przykładzie środek trwały został nabyty 1 stycznia 2018 r. i zostanie uznany za odpadki w dniu 31 marca 2019 r.</span><span class="sxs-lookup"><span data-stu-id="a6b70-128">For the following example, a fixed asset was acquired on January 1, 2018, and it will be scrapped on March 31, 2019.</span></span>

- <span data-ttu-id="a6b70-129">**Cena nabycia:** 24 000,00 dolarów amerykańskich (USD)</span><span class="sxs-lookup"><span data-stu-id="a6b70-129">**Acquisition price:** 24,000.00 US dollars (USD)</span></span>
- <span data-ttu-id="a6b70-130">**Okres użytkowania:** Dwa lata</span><span class="sxs-lookup"><span data-stu-id="a6b70-130">**Service life:** Two years</span></span>
- <span data-ttu-id="a6b70-131">**Metoda amortyzacji:** Liniowy okres użytkowania</span><span class="sxs-lookup"><span data-stu-id="a6b70-131">**Depreciation method:** Straight line service life</span></span>
- <span data-ttu-id="a6b70-132">**Kwota amortyzacji:** 1 000,00 dolarów amerykańskich miesięcznie</span><span class="sxs-lookup"><span data-stu-id="a6b70-132">**Depreciation amount:** 1,000.00 USD per month</span></span>

<span data-ttu-id="a6b70-133">Kwota NBV środka trwałego jest obliczana przy użyciu następującej formuły:</span><span class="sxs-lookup"><span data-stu-id="a6b70-133">The NBV of a fixed asset is calculated by using the following formula:</span></span>

<span data-ttu-id="a6b70-134">Wartość księgowa netto = Cena nabycia - Amortyzacja</span><span class="sxs-lookup"><span data-stu-id="a6b70-134">Net book value = Acquisition price – Depreciation</span></span>

<span data-ttu-id="a6b70-135">W tym przykładzie środek trwały został nabyty i został zamortyzowany w ciągu 15 miesięcy od stycznia 2018 r. do marca 2019 r.</span><span class="sxs-lookup"><span data-stu-id="a6b70-135">In this example, the fixed asset was acquired and was depreciated for 15 months, from January 2018 through March 2019.</span></span> <span data-ttu-id="a6b70-136">Dlatego NBV składnika majatku jest 9 000,00 USD (24 000,00 USD – 15 000,00 USD).</span><span class="sxs-lookup"><span data-stu-id="a6b70-136">Therefore, the asset's NBV is 9,000.00 USD (24,000.00 USD – 15,000.00 USD).</span></span>

<span data-ttu-id="a6b70-137">[![Przykład amortyzacji środków trwałych](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span><span class="sxs-lookup"><span data-stu-id="a6b70-137">[![Fixed asset depreciation example](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span></span>


<span data-ttu-id="a6b70-138">Aby utworzyć arkusz likwidacji, należy przejść do **Środki trwałe \> Wpisy w arkuszu \> Arkusz środków trwałych**, a następnie w okienku akcji wybrać **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="a6b70-138">To create a disposal journal, go to **Fixed assets \> Journal entries \> Fixed assets journal**, and then, on the Action Pane, select **Lines**.</span></span> <span data-ttu-id="a6b70-139">Wybierz **Likwidacja — odpadki**, a następnie wybierz identyfikator środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="a6b70-139">Select **Disposal – scrap**, and then select a fixed asset ID.</span></span> <span data-ttu-id="a6b70-140">Aby w pełni usunąć środek trwały, nie wprowadzaj wartości w polach **Debet** lub **Kredyt**.</span><span class="sxs-lookup"><span data-stu-id="a6b70-140">To fully dispose of the asset, don't enter a value in either the **Debit** field or the **Credit** field.</span></span>

<span data-ttu-id="a6b70-141">[![Arkusz środków trwałych](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span><span class="sxs-lookup"><span data-stu-id="a6b70-141">[![Fixed assets journal](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span></span>

<span data-ttu-id="a6b70-142">Transakcja likwidacji środków trwałych zmienia wartości pól dla księgi środków trwałych w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="a6b70-142">The fixed asset disposal scrap transaction changes the field values for the fixed asset book in the following ways:</span></span>

- <span data-ttu-id="a6b70-143">W sekcji **Saldo** pole **Stan** jest aktualizowane na **Uznany za odpadki**.</span><span class="sxs-lookup"><span data-stu-id="a6b70-143">In the **Balance** section, the **Status** field is updated to **Scrapped**.</span></span>
- <span data-ttu-id="a6b70-144">W sekcji **Rozchód** w polu **Data likwidacji** jest ustawiana data uznania środka trwałego za odpadki.</span><span class="sxs-lookup"><span data-stu-id="a6b70-144">In the **Issue** section, the **Disposal date** field is set to the date when the asset was scrapped.</span></span>

<span data-ttu-id="a6b70-145">[![Szczegóły arkusza środków trwałych](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span><span class="sxs-lookup"><span data-stu-id="a6b70-145">[![Fixed assets journal detail](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span></span>

<span data-ttu-id="a6b70-146">Na poniższej ilustracji przedstawiono saldo środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="a6b70-146">The following illustration shows the fixed asset balance.</span></span>

<span data-ttu-id="a6b70-147">[![Saldo środka trwałego](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span><span class="sxs-lookup"><span data-stu-id="a6b70-147">[![Fixed asset balance](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span></span>

<span data-ttu-id="a6b70-148">Poniższa ilustracja przedstawia zaksięgowany załącznik.</span><span class="sxs-lookup"><span data-stu-id="a6b70-148">The following illustration shows the voucher that is posted.</span></span>

<span data-ttu-id="a6b70-149">[![Wartość księgowa netto](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span><span class="sxs-lookup"><span data-stu-id="a6b70-149">[![Net book value](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span></span>
