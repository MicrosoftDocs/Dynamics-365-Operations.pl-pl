---
title: Typy krytyczności składnika majątku
description: W tym temacie objaśniono typy krytyczności składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c771e7ebda94687ab5442347e74c82b01ad2fcc6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245426"
---
# <a name="asset-criticality-types"></a><span data-ttu-id="2aacb-103">Typy krytyczności składnika majątku</span><span class="sxs-lookup"><span data-stu-id="2aacb-103">Asset criticality types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="2aacb-104">W tym temacie objaśniono typy krytyczności składników majątku w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="2aacb-104">The topic explains asset criticality types in Asset Management.</span></span> <span data-ttu-id="2aacb-105">Krytyczność składników majątku jest związana ze składnikami majątku i jest przenoszona do zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="2aacb-105">Asset criticality is related to assets and is transferred to work orders.</span></span> <span data-ttu-id="2aacb-106">Nie można jej zmienić w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="2aacb-106">It can't be changed on a work order.</span></span> <span data-ttu-id="2aacb-107">Krytyczność składników majątku jest używana do obliczania krytyczności zlecenia pracy podczas planowania zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="2aacb-107">Asset criticality is used to calculate work order criticality during work order scheduling.</span></span> <span data-ttu-id="2aacb-108">Innymi słowy, służy do obliczania stopnia, w jakim zadanie konserwacji składnika majątku wpływa na harmonogram produkcji i produktywność w firmie.</span><span class="sxs-lookup"><span data-stu-id="2aacb-108">In other words, it's used to calculate the extent to which a maintenance job on an asset affects the production schedule and productivity in your company.</span></span> <span data-ttu-id="2aacb-109">Aby uzyskać więcej informacji na temat konfiguracji, która jest powiązana z obliczaniem oceny wyników dla planowania zlecenia pracy, zobacz temat [Parametry modułu Zarządzania składnikami majątku](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="2aacb-109">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span>

<span data-ttu-id="2aacb-110">Aby skonfigurować krytyczność, należy najpierw utworzyć typy krytyczności, które powinny być używane w ustawieniach składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="2aacb-110">To set up criticality, you first create the criticality types that should be used in the asset setup.</span></span> <span data-ttu-id="2aacb-111">Następnie należy skonfigurować krytyczność składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="2aacb-111">You then set up asset criticalities.</span></span>

## <a name="set-up-criticality-types"></a><span data-ttu-id="2aacb-112">Konfigurowanie typów krytyczności</span><span class="sxs-lookup"><span data-stu-id="2aacb-112">Set up criticality types</span></span>

1. <span data-ttu-id="2aacb-113">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Typy krytyczności**.</span><span class="sxs-lookup"><span data-stu-id="2aacb-113">Select **Asset management** \> **Setup** \> **Assets** \> **Criticality types**.</span></span>
2. <span data-ttu-id="2aacb-114">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="2aacb-114">Select **New** to create a record.</span></span>
3. <span data-ttu-id="2aacb-115">W polu **Krytyczność** wprowadź liczbę oznaczającą krytyczność.</span><span class="sxs-lookup"><span data-stu-id="2aacb-115">In the **Criticality** field, enter a number that indicates the criticality.</span></span>
4. <span data-ttu-id="2aacb-116">W polu **Nazwa** wprowadź nazwę typu krytyczności.</span><span class="sxs-lookup"><span data-stu-id="2aacb-116">In the **Name** field, enter a name for the criticality type.</span></span>
5. <span data-ttu-id="2aacb-117">W polu **Współczynnik** wpisz współczynnik.</span><span class="sxs-lookup"><span data-stu-id="2aacb-117">In the **Factor** field, enter a factor.</span></span> <span data-ttu-id="2aacb-118">Ten współczynnik jest używany podczas obliczania planowania zleceń pracy w celu określenia rekordu krytyczności, który ma zostać użyty.</span><span class="sxs-lookup"><span data-stu-id="2aacb-118">This factor is used during the calculation of work order scheduling to determine the criticality record that should be used.</span></span> <span data-ttu-id="2aacb-119">(Zawsze jest używany rekord o najwyższym współczynniku). To ustawienie ma zastosowanie, jeśli, jak to pokazano na poniższej ilustracji, zostaną utworzone wiersze krytyczności, które mają taką samą wartość krytyczności.</span><span class="sxs-lookup"><span data-stu-id="2aacb-119">(The record that has the highest factor is always used.) This setting is relevant if, as shown in the following illustration, criticality lines are created that have the same criticality value.</span></span>

    ![Strona typów krytyczności](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a><span data-ttu-id="2aacb-121">Konfigurowanie krytyczności składników majątku</span><span class="sxs-lookup"><span data-stu-id="2aacb-121">Set up asset criticalities</span></span>

1. <span data-ttu-id="2aacb-122">Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Krytyczności składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="2aacb-122">Select **Asset management** \> **Setup** \> **Asset criticalities**.</span></span>
2. <span data-ttu-id="2aacb-123">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="2aacb-123">Select **New** to create a record.</span></span>
3. <span data-ttu-id="2aacb-124">W zależności od wymaganego poziomu szczegółowości krytyczności składnika majątku dokonaj odpowiednich selekcji w polach **Lokalizacja czynności konserwacyjnych**, **Typ składnika majątku**, **Producent** **Model**, **Składnik majątku**, **Kategoria typu zadania**, **Typ zadania**, **Wariant typu zadania** oraz **Kryterium doboru**.</span><span class="sxs-lookup"><span data-stu-id="2aacb-124">Depending on the required level of detail for asset criticality, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2aacb-125">Kiedy krytyczność składnika majątku jest wybrana, moduł Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy krytyczności składników majątku, szukając ewentualnego dopasowania.</span><span class="sxs-lookup"><span data-stu-id="2aacb-125">When an asset criticality is selected, Asset Management goes through all asset criticality records to check for a possible match.</span></span> <span data-ttu-id="2aacb-126">W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową.</span><span class="sxs-lookup"><span data-stu-id="2aacb-126">It always checks the most specific combination first.</span></span> <span data-ttu-id="2aacb-127">Innymi słowy, moduł Zarządzanie składnikami majątku najpierw sprawdza **Kryterium doboru**.</span><span class="sxs-lookup"><span data-stu-id="2aacb-127">In other words, Asset Management first checks **Job requirement**.</span></span> <span data-ttu-id="2aacb-128">Jeśli nie zostanie znaleziony żaden odpowiednik, sprawdza **Wariant typu zadania**.</span><span class="sxs-lookup"><span data-stu-id="2aacb-128">If no match is found, it checks **Job type variant**.</span></span> <span data-ttu-id="2aacb-129">Jeśli nie zostanie znaleziony żaden odpowiednik, sprawdza **Typ zadania** itd.</span><span class="sxs-lookup"><span data-stu-id="2aacb-129">If no match is found, it checks **Job type**, and so on.</span></span> <span data-ttu-id="2aacb-130">Jak widać w układzie strony to zachowanie oznacza, że aby znaleźć najbardziej konkretną kombinację, moduł Zarządzanie składnikami majątku sprawdza każdy rekord od prawej do lewej pod kątem dopasowania.</span><span class="sxs-lookup"><span data-stu-id="2aacb-130">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="2aacb-131">Jeśli nie uda się znaleźć dopasowania, jest używany rekord „domyślny”, który nie ma zaznaczeń.</span><span class="sxs-lookup"><span data-stu-id="2aacb-131">If no match is found, the "default" record that has no selections is used.</span></span>

4. <span data-ttu-id="2aacb-132">W polu **Krytyczność** wybierz jedną z wartości krytyczności utworzonych w poprzedniej procedurze.</span><span class="sxs-lookup"><span data-stu-id="2aacb-132">In the **Criticality** field, select one of the criticality values that you created in the previous procedure.</span></span>

### <a name="notes-about-criticality-setup"></a><span data-ttu-id="2aacb-133">Uwagi dotyczące konfiguracji krytyczności</span><span class="sxs-lookup"><span data-stu-id="2aacb-133">Notes about criticality setup</span></span>

- <span data-ttu-id="2aacb-134">Jeśli w tej konfiguracji zmienisz krytyczność składnika majątku po użyciu go w jakimś zleceniu pracy, krytyczność na zleceniu pracy nie jest odpowiednio aktualizowana.</span><span class="sxs-lookup"><span data-stu-id="2aacb-134">If you change an asset criticality in this setup after you've already used it on a work order, the criticality on the work order isn't updated accordingly.</span></span>
- <span data-ttu-id="2aacb-135">Krytyczność na zleceniu pracy jest przeliczana za każdym razem, gdy wiersz zlecenia pracy jest dodawany lub usuwany ze zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="2aacb-135">The criticality on a work order is recalculated every time that a work order line is added to or deleted from the work order.</span></span>
- <span data-ttu-id="2aacb-136">Jeśli zlecenie pracy zawiera kilka zadań pracy, najwyższy poziom krytyczności, zgodnie z polem **Współczynnik** na stronie **Typy krytyczności**, jest zawsze używana w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="2aacb-136">If a work order contains several work order jobs, the highest criticality, according to the **Factor** field on the **Criticality types** page, is always used on the work order.</span></span>
- <span data-ttu-id="2aacb-137">Ogólnie rzecz biorąc, krytyczność składników majątku można zmienić na przestrzeni czasu.</span><span class="sxs-lookup"><span data-stu-id="2aacb-137">Generally, asset criticality can change over a period.</span></span> <span data-ttu-id="2aacb-138">Krytyczność może mieć wpływ na zakup nowego sprzętu, remonty i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="2aacb-138">Criticality can be affected by the purchase of new equipment, refurbishments, and so on.</span></span> <span data-ttu-id="2aacb-139">Rozważ ponowną ocenę krytyczności składników majątku w regularnych odstępach czasu (np. raz na rok lub co dwa lata), aby upewnić się, że definicje krytyczności odpowiadają aktualnej konfiguracji produkcji.</span><span class="sxs-lookup"><span data-stu-id="2aacb-139">Consider reevaluating your asset criticalities at regular intervals (for example, once per year or every other year) to make sure that your criticality definitions match your current production setup.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]