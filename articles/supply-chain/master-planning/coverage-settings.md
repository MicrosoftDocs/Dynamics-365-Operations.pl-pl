---
title: Ustawienia zapotrzebowania
description: Ten temat zawiera informacje o ustawieniach zapotrzebowania, których planowanie główne używa do obliczania zapotrzebowania na towar.
author: roxanadiaconu
manager: tfehr
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard, ReqItemTableSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b1134f734f1025151a56b2a72266a6baa5763ba4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435469"
---
# <a name="coverage-settings"></a><span data-ttu-id="d02d5-103">Ustawienia zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="d02d5-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d02d5-104">Ustawienia zapotrzebowania są używane przez planowanie główne do obliczania zapotrzebowań na towary.</span><span class="sxs-lookup"><span data-stu-id="d02d5-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="d02d5-105">Ustawienia zapotrzebowania można określić na kilka sposobów:</span><span class="sxs-lookup"><span data-stu-id="d02d5-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="d02d5-106">Określ ustawienia zapotrzebowania dla grupy zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="d02d5-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="d02d5-107">Można utworzyć grupę zapotrzebowania zawierająca ustawienia dotyczące wszystkich produktów połączonych z tą grupą zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="d02d5-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="d02d5-108">Aby utworzyć grupę zapotrzebowania, kliknij kolejno opcje **Planowanie główne &gt; Ustawienia &gt; Zapotrzebowanie &gt; Grupy zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="d02d5-109">Grupę zapotrzebowania można połączyć z produktem.</span><span class="sxs-lookup"><span data-stu-id="d02d5-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="d02d5-110">Jeśli łącze jest właściwe dla oddziału, magazynu lub wymiaru produktu, użyj pola **grupa zapotrzebowania** na stronie **zapotrzebowanie na towar**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="d02d5-111">Jeśli łącze ma charakter ogólny, bez względu na wymiary produktu, należy użyć **grupy zapotrzebowania** na skróconej karcie **Plan** na stronie **Szczegóły produktu**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="d02d5-112">Domyślnie, jeśli grupa zapotrzebowania nie jest połączona z produktem, planowanie główne używa ogólnej grupy zapotrzebowania określonej na stronie **Parametry planowania głównego**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="d02d5-113">Określ ustawienia zapotrzebowania dla produktu.</span><span class="sxs-lookup"><span data-stu-id="d02d5-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="d02d5-114">Ustawienia zapotrzebowania można utworzyć dla określonego produktu.</span><span class="sxs-lookup"><span data-stu-id="d02d5-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="d02d5-115">Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="d02d5-116">Wybierz produkt, a następnie w okienku akcji na karcie **Plan** w obszarze **Grupa zapotrzebowania** wybierz **Zapotrzebowanie na towar**, aby otworzyć stronę **Zapotrzebowanie na towar**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="d02d5-117">Jeśli produkt jest połączony z grupą zapotrzebowania, ustawienia grupy zapotrzebowania można zastąpić, korzystając z pola **Zastąp**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="d02d5-118">Ustawienia zapotrzebowania na stronie **Zapotrzebowanie na towar** mają pierwszeństwo przed ustawieniami na stronie **Grupa zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="d02d5-119">Określ ustawienia zapotrzebowania dla produktu za pomocą kreatora.</span><span class="sxs-lookup"><span data-stu-id="d02d5-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="d02d5-120">Kreator przeprowadzi Cię krok po kroku przez proces konfigurowania podstawowych parametrów zapotrzebowania na towar.</span><span class="sxs-lookup"><span data-stu-id="d02d5-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="d02d5-121">Na stronie **Zapotrzebowanie na towar** w okienku akcji kliknij **Kreator**, aby otworzyć **Kreator zapotrzebowania na towar**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="d02d5-122">Określ ustawienia zapotrzebowania dla grupy wymiarów.</span><span class="sxs-lookup"><span data-stu-id="d02d5-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="d02d5-123">Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="d02d5-124">Na stronie **Szczegóły zwolnionego produktu** na skróconej karcie **Ogólne** w grupie **Administracja** kliknij łącze w polu **Grupa wymiarów magazynowania**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="d02d5-125">Na stronie **Grupy wymiarów magazynowania** zaznacz pole **Plan zapotrzebowania wg wymiaru**, aby utworzyć ustawienia zapotrzebowania dla wymiaru w grupie wymiarów magazynowania.</span><span class="sxs-lookup"><span data-stu-id="d02d5-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="d02d5-126">Wszystkie wymiary produktów, takie jak konfiguracja, kolor, rozmiar, styl, muszą mieć zaznaczone pole **Plan zapotrzebowania wg wymiaru**.</span><span class="sxs-lookup"><span data-stu-id="d02d5-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>


## <a name="coverage-codes"></a><span data-ttu-id="d02d5-127">Kody zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="d02d5-127">Coverage codes</span></span>

<span data-ttu-id="d02d5-128">Planowanie główne można skonfigurować w taki sposób, aby korzystało z różnych metod uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="d02d5-128">Master planning can be configured to use different replenishment methods.</span></span> <span data-ttu-id="d02d5-129">Metody uzupełniania lub metody ustalania wielkości zapasów są technikami stosowanymi w systemie do określania rozmiaru partii zakupionych lub wyprodukowanych towarów.</span><span class="sxs-lookup"><span data-stu-id="d02d5-129">The replenishment methods or lot-sizing methods are the techniques used by the system to determine the batch size for purchased or produced items.</span></span> 

<span data-ttu-id="d02d5-130">Do każdej metody uzupełnień jest przypisany jeden z następujących kodów zapotrzebowania:</span><span class="sxs-lookup"><span data-stu-id="d02d5-130">Each replenishment method is assigned one of the following coverage codes:</span></span>

- <span data-ttu-id="d02d5-131">**Ręczna** — metoda ustalania rozmiaru partii, w której system nie sugeruje nabywania, przenoszenia lub zleceń produkcyjnych dla danego towaru.</span><span class="sxs-lookup"><span data-stu-id="d02d5-131">**Manual** - The lot-sizing method where the system does not suggest purchased, transfer, or production orders for the item.</span></span> <span data-ttu-id="d02d5-132">Terminarz pozycji będzie odpowiedzialny za tworzenie wymaganych zamówień uzupełniania towaru.</span><span class="sxs-lookup"><span data-stu-id="d02d5-132">The planner for the item will be in charge of creating the required orders for the replenishment of the item.</span></span>
- <span data-ttu-id="d02d5-133">**Dla zapotrzebowania** — metoda ustalania rozmiaru partii, w której system tworzy planowany zakup, przeniesienie lub zlecenie produkcyjne według zapotrzebowania na dany towar.</span><span class="sxs-lookup"><span data-stu-id="d02d5-133">**Per requirement** - The lot-sizing method in which the system creates a planned purchase, transfer, or production order per requirement for the item.</span></span> <span data-ttu-id="d02d5-134">Jest to zwykle używane w przypadku kosztownych towarów ze sporadycznym popytem.</span><span class="sxs-lookup"><span data-stu-id="d02d5-134">This is generally used for expensive items with intermittent demand.</span></span>  
- <span data-ttu-id="d02d5-135">**Na okres** — metoda określania rozmiaru partii, która łączy wszystkie zapotrzebowania na okres w jednym zamówieniu towaru.</span><span class="sxs-lookup"><span data-stu-id="d02d5-135">**Per period** - The lot-sizing method that combines all the demand for a period into one order for the item.</span></span> <span data-ttu-id="d02d5-136">Zamówienie zostanie zaplanowane na pierwszy dzień okresu, a jego ilość będzie spełniać zapotrzebowania netto w ustalonym okresie.</span><span class="sxs-lookup"><span data-stu-id="d02d5-136">The order will be planned for the first day of the period and its quantity will fulfill the net requirements during the established period.</span></span> <span data-ttu-id="d02d5-137">Okres rozpoczyna się od pierwszego zapotrzebowania na towar i obejmuje zdefiniowany okres w czasie.</span><span class="sxs-lookup"><span data-stu-id="d02d5-137">The period starts with the first demand of the item and covers the defined length in time.</span></span> <span data-ttu-id="d02d5-138">Następny okres rozpocznie się od kolejnych wymagań dotyczących towaru.</span><span class="sxs-lookup"><span data-stu-id="d02d5-138">The next period will start with the next requirements of the item.</span></span>
- <span data-ttu-id="d02d5-139">**Minimum/maksimum** — metoda określania rozmiaru partii, która zawiera uzupełnienie zapasów do określonego poziomu, gdy przewidywana ilość zapasów jest mniejsza niż wartość progowa.</span><span class="sxs-lookup"><span data-stu-id="d02d5-139">**Min/Max** - The lot-sizing method that contains the replenishment of inventory up to a certain level when the predicted on-hand is below a threshold.</span></span> <span data-ttu-id="d02d5-140">Ilość uzupełniania zapasów będzie różnicą między maksymalnym poziomem i przewidywanym poziomem zapasów.</span><span class="sxs-lookup"><span data-stu-id="d02d5-140">The replenishment quantity will be the difference between the maximum level and the predicted on-hand level.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="d02d5-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d02d5-141">Additional resources</span></span>

[<span data-ttu-id="d02d5-142">Omówienie planów głównych</span><span class="sxs-lookup"><span data-stu-id="d02d5-142">Master plans overview</span></span>](master-plans.md)
