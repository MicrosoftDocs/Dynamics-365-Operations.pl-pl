---
title: Planowany przeładunek kompletacyjny
description: W tym temacie opisano zaawansowane planowane przeładunki kompletacyjne, w którym ilość zapasów wymagana dla zamówienia jest skierowana bezpośrednio z paragonu lub tworzenia do właściwego doku załadunkowego lub obszaru tymczasowego. Wszystkie pozostałe zapasy ze źródła przychodzącego są kierowane do poprawnego miejsca przechowywania za pośrednictwem zwykłego procesu umieszczenia.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 722b004e607cb2e6b7de292d92b67b18c2024696
ms.sourcegitcommit: 70b1567d316f19c15a4b032b4897f15c8dcdca09
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2021
ms.locfileid: "5556273"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="26b6a-104">Planowany przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="26b6a-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26b6a-105">W tym temacie opisano zaawansowany planowany przeładunek kompletacyjny.</span><span class="sxs-lookup"><span data-stu-id="26b6a-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="26b6a-106">Zaawansowany planowany przeładunek kompletacyjny to proces magazynowy, w którym ilość zapasów wymagana dla zamówienia jest skierowana bezpośrednio z paragonu lub tworzenia do właściwego doku załadunkowego lub obszaru tymczasowego.</span><span class="sxs-lookup"><span data-stu-id="26b6a-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="26b6a-107">Wszystkie pozostałe zapasy ze źródła przychodzącego są kierowane do poprawnego miejsca przechowywania za pośrednictwem zwykłego procesu umieszczenia.</span><span class="sxs-lookup"><span data-stu-id="26b6a-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="26b6a-108">Proces ten pozwala pracownikom pominąć przychodzące umieszczenia i pobrania wychodzące zapasów, które są już oznaczone dla zamówienia wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="26b6a-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="26b6a-109">Z tego względu liczba przypadków, gdy zapasy są poruszane, jest zminimalizowana, jeśli to możliwe.</span><span class="sxs-lookup"><span data-stu-id="26b6a-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="26b6a-110">Ponadto, ponieważ mniejsza jest interakcja z systemem, wzrasta oszczędność czasu i miejsca w ramach produkcji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="26b6a-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="26b6a-111">Aby można było uruchomić przeładunek kompletacyjny, użytkownik musi skonfigurować nowy szablon przeładunku kompletacyjnego, w którym określono źródło dostaw i inne zestawy wymagań.</span><span class="sxs-lookup"><span data-stu-id="26b6a-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="26b6a-112">Po utworzeniu zamówienia wychodzącego wiersz musi być zaznaczony względem zamówienia przychodzącego, które zawiera ten sam towar.</span><span class="sxs-lookup"><span data-stu-id="26b6a-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="26b6a-113">W momencie przyjęcia zamówienia przychodzącego konfiguracja przeładunku kompletacyjnego automatycznie identyfikuje potrzebę przeładunku kompletacyjnego i tworzy pracę dla wymaganej ilości w oparciu o konfigurację dyrektywy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="26b6a-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="26b6a-114">Transakcje magazynowe **nie są** rejestrowane, gdy praca przeładunku kompletacyjnego została anulowana, nawet jeśli ustawienie tej funkcji jest włączone w parametrach zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="26b6a-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="26b6a-115">Włącz funkcje planowanego przeładunku kompletacyjnego</span><span class="sxs-lookup"><span data-stu-id="26b6a-115">Turn on the planned cross docking features</span></span>

<span data-ttu-id="26b6a-116">Jeśli Twój system nie zawiera jeszcze funkcji opisanych w tym temacie, przejdź do [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz następujące funkcje w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="26b6a-116">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="26b6a-117">*Planowany przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="26b6a-117">*Planned cross docking*</span></span>
2. <span data-ttu-id="26b6a-118">*Szablony przeładunku kompletacyjnego z dyrektywami lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="26b6a-118">*Cross docking templates with location directives*</span></span>

## <a name="setup"></a><span data-ttu-id="26b6a-119">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="26b6a-119">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="26b6a-120">Ponowne generowanie metod księgowania ładunku</span><span class="sxs-lookup"><span data-stu-id="26b6a-120">Regenerate load posting methods</span></span>

<span data-ttu-id="26b6a-121">Planowany przeładunek kompletacyjny jest implementowany jako metoda księgowania ładunku.</span><span class="sxs-lookup"><span data-stu-id="26b6a-121">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="26b6a-122">Po włączeniu funkcji należy ponownie wygenerować metody.</span><span class="sxs-lookup"><span data-stu-id="26b6a-122">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="26b6a-123">Przejdź do **Zarządzania magazynem \> Konfiguracja \> Metody księgowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-123">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="26b6a-124">W okienku akcji wybierz pozycję **Ponownie utwórz metody**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-124">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="26b6a-125">Po zakończeniu ponownego generowania powinna być widoczna metoda, która ma wartość **Nazwa metody** *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-125">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="26b6a-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="26b6a-126">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="26b6a-127">Tworzenie szablonu przeładunku kompletacyjnego</span><span class="sxs-lookup"><span data-stu-id="26b6a-127">Create a cross-docking template</span></span>

1. <span data-ttu-id="26b6a-128">Przejdź kolejno do pozycji **Zarządzanie magazynem \> Konfiguracja \> Praca \> Szablony przeładunku kompletacyjnego**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-128">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="26b6a-129">W okienku akcji wybierz opcję **Nowe**, aby utworzyć szablon.</span><span class="sxs-lookup"><span data-stu-id="26b6a-129">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="26b6a-130">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-130">In the header, set the following values:</span></span>

    - <span data-ttu-id="26b6a-131">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="26b6a-131">**Sequence:** *1*</span></span>

        <span data-ttu-id="26b6a-132">To pole określa kolejność, w jakiej są oceniane szablony.</span><span class="sxs-lookup"><span data-stu-id="26b6a-132">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="26b6a-133">**Identyfikator szablonu przeładunku kompletacyjnego** *51*</span><span class="sxs-lookup"><span data-stu-id="26b6a-133">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="26b6a-134">**Opis:** *Magazyn 51*</span><span class="sxs-lookup"><span data-stu-id="26b6a-134">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="26b6a-135">**Zasady zwalniania popytu** *Przed przyjęciem dostawy*</span><span class="sxs-lookup"><span data-stu-id="26b6a-135">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="26b6a-136">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="26b6a-136">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="26b6a-137">Konfiguracja na skróconej karcie **Planowanie** decyduje o sposobie działania szablonu.</span><span class="sxs-lookup"><span data-stu-id="26b6a-137">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="26b6a-138">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-138">Set the following values:</span></span>

    - <span data-ttu-id="26b6a-139">**Wymagania dotyczące popytu:** *Brak*</span><span class="sxs-lookup"><span data-stu-id="26b6a-139">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="26b6a-140">To pole definiuje wymagania dotyczące zapasów zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="26b6a-140">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="26b6a-141">Jeśli zapotrzebowanie musi być połączone z dostawą przed zwolnieniem, wybierz opcję *Zaznaczenie*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-141">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="26b6a-142">Jeśli zapotrzebowanie musi być zarezerwowane na podstawie zamówienia przed zwolnieniem, wybierz opcję *Rezerwacja zamówienia*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-142">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="26b6a-143">**Lokalizowanie typu:** *Lokalizacje wysyłki*</span><span class="sxs-lookup"><span data-stu-id="26b6a-143">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="26b6a-144">To pole określa, czy w ramach pracy przeładunku kompletacyjnego powinny być używane lokalizacje pośredniego/ładunku z wysyłki, czy też mają być używane dyrektywy lokalizacji w celu znalezienia własnych lokalizacji przemieszczania/ładunku.</span><span class="sxs-lookup"><span data-stu-id="26b6a-144">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="26b6a-145">**Szablon pracy:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="26b6a-145">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="26b6a-146">To pole definiuje szablon pracy, który ma być używany podczas tworzenia przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="26b6a-146">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="26b6a-147">**Sprawdź ponownie na paragonie dostawy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="26b6a-147">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="26b6a-148">Ta opcja umożliwia zdefiniowanie, czy dostawa ma zostać sprawdzona ponownie podczas przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="26b6a-148">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="26b6a-149">Jeśli ta opcja ma wartość *Tak*, sprawdzane są zarówno maksymalne przedziały czasu, jak i zakres daty ważności.</span><span class="sxs-lookup"><span data-stu-id="26b6a-149">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="26b6a-150">Pole **Kod dyrektywy** należy pozostawić puste</span><span class="sxs-lookup"><span data-stu-id="26b6a-150">**Directive code** Leave this field blank</span></span>

        <span data-ttu-id="26b6a-151">Ta opcja umożliwia systemowi korzystanie z dyrektyw lokalizacji, aby pomóc w określeniu najlepszej lokalizacji do przeniesienia zapasów kompletacyjnych.</span><span class="sxs-lookup"><span data-stu-id="26b6a-151">This option enables the system to use location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="26b6a-152">Możesz to skonfigurować, przypisując kod dyrektywy do każdego odpowiedniego szablonu przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="26b6a-152">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="26b6a-153">Każdy kod dyrektywy określa unikatową dyrektywę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="26b6a-153">Each directive code identifies a unique location directive.</span></span>

    - <span data-ttu-id="26b6a-154">**Sprawdzanie poprawności – okno czasowe:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="26b6a-154">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="26b6a-155">Ta opcja służy do definiowania, czy w przypadku wybrania źródła dostaw ma być oceniany maksymalny przedział czasu.</span><span class="sxs-lookup"><span data-stu-id="26b6a-155">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="26b6a-156">Jeśli ta opcja ma wartość *Tak*, pola związane z maksymalnym i minimalnym okienkiem czasowym staną się dostępne.</span><span class="sxs-lookup"><span data-stu-id="26b6a-156">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="26b6a-157">**Okienko czasu maksymalnego:** *5*</span><span class="sxs-lookup"><span data-stu-id="26b6a-157">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="26b6a-158">To pole określa maksymalny dopuszczalny okres między pojawieniem się dostawy a wysłaniem zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="26b6a-158">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="26b6a-159">**Maksymalna jednostka okna czasu:** *Dni*</span><span class="sxs-lookup"><span data-stu-id="26b6a-159">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="26b6a-160">**Okienko czasu minimalnego:** *0*</span><span class="sxs-lookup"><span data-stu-id="26b6a-160">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="26b6a-161">To pole określa minimalny dopuszczalny okres między pojawieniem się dostawy a wysłaniem zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="26b6a-161">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="26b6a-162">**Minimalna jednostka okna czasu:** *Dni*</span><span class="sxs-lookup"><span data-stu-id="26b6a-162">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="26b6a-163">**Zakres dni daty ważności:** *0*</span><span class="sxs-lookup"><span data-stu-id="26b6a-163">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="26b6a-164">*Kryterium pierwsze do wygaśnięcia – pierwsze do wyjścia (FEFO):* to pole określa maksymalną liczbę dni między datą ważności pierwszej partii, która znajduje się obecnie w magazynie a otrzymaną partią.</span><span class="sxs-lookup"><span data-stu-id="26b6a-164">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="26b6a-165">Na skróconej karcie **Źródła dostaw** można określić typy dostaw, które są prawidłowe dla tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="26b6a-165">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="26b6a-166">Wybierz opcję **Nowe**, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-166">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="26b6a-167">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="26b6a-167">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="26b6a-168">**Źródło dostawy:** *Zamówienie zakupu*</span><span class="sxs-lookup"><span data-stu-id="26b6a-168">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="26b6a-169">Tworzenie klasy roboczej</span><span class="sxs-lookup"><span data-stu-id="26b6a-169">Create a work class</span></span>

1. <span data-ttu-id="26b6a-170">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-170">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="26b6a-171">W okienku akcji wybierz opcję **Nowe**, aby utworzyć klasę roboczą.</span><span class="sxs-lookup"><span data-stu-id="26b6a-171">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="26b6a-172">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-172">Set the following values:</span></span>

    - <span data-ttu-id="26b6a-173">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="26b6a-173">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="26b6a-174">**Opis:** *Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="26b6a-174">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="26b6a-175">**Typ zlecenia pracy:** *Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="26b6a-175">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="26b6a-176">Tworzenie szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="26b6a-176">Create a work template</span></span>

1. <span data-ttu-id="26b6a-177">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-177">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="26b6a-178">W polu **Typ zlecenia pracy** ustaw pozycję *Przeładunek kompletacyjny*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-178">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="26b6a-179">W okienku akcji wybierz opcję **Nowe**, aby dodać nowy wiersz do karty **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-179">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="26b6a-180">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="26b6a-181">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="26b6a-181">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="26b6a-182">**Szablon pracy** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="26b6a-182">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="26b6a-183">**Opis szablonu pracy** *51 Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="26b6a-183">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="26b6a-184">Wybierz opcję **Zapisz**, aby skrócona karta **Szczegóły szablonu pracy** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="26b6a-184">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="26b6a-185">Na skróconej karcie **Szczegółów dot. szablonu pracy** wybierz opcję **Nowy**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="26b6a-185">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="26b6a-186">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="26b6a-187">**Typ pracy:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="26b6a-187">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="26b6a-188">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="26b6a-188">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="26b6a-189">Wybierz polecenie **Nowy**, aby dodać dodatkowy wiersz i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-189">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="26b6a-190">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="26b6a-190">**Work type:** *Put*</span></span>
    - <span data-ttu-id="26b6a-191">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="26b6a-191">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="26b6a-192">Wybierz opcję **Zapisz** i upewnij się, że zaznaczono pole wyboru **Prawidłowe** dla szablonu *51 Cross Dock*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-192">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="26b6a-193">Identyfikatory klas roboczych dla typów pracy *Pobranie* i *Umieszczenie* muszą być takie same.</span><span class="sxs-lookup"><span data-stu-id="26b6a-193">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="26b6a-194">Tworzenie dyrektyw lokalizacji</span><span class="sxs-lookup"><span data-stu-id="26b6a-194">Create location directives</span></span>

1. <span data-ttu-id="26b6a-195">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-195">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="26b6a-196">W lewym okienku w polu **Typ zlecenia produkcyjnego** ustaw wartość na *Przeładunek kompletacyjny*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-196">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="26b6a-197">Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-197">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="26b6a-198">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="26b6a-198">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="26b6a-199">**Nazwa:** *51 Cross Dock Put*</span><span class="sxs-lookup"><span data-stu-id="26b6a-199">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="26b6a-200">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="26b6a-200">**Work type:** *Put*</span></span>
    - <span data-ttu-id="26b6a-201">**Oddział:** *5*</span><span class="sxs-lookup"><span data-stu-id="26b6a-201">**Site:** *5*</span></span>
    - <span data-ttu-id="26b6a-202">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="26b6a-202">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="26b6a-203">Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="26b6a-203">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="26b6a-204">Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="26b6a-204">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="26b6a-205">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-205">On the new line, set the following values:</span></span>

    - <span data-ttu-id="26b6a-206">**Od ilości:** *1*</span><span class="sxs-lookup"><span data-stu-id="26b6a-206">**From quantity:** *1*</span></span>
    - <span data-ttu-id="26b6a-207">**Do ilości:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="26b6a-207">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="26b6a-208">Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="26b6a-208">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="26b6a-209">Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="26b6a-209">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="26b6a-210">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-210">On the new line, set the following values:</span></span>

    - <span data-ttu-id="26b6a-211">**Nazwa:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="26b6a-211">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="26b6a-212">**Stałe użycie lokalizacji:** *Stałe i niestałe lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="26b6a-212">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="26b6a-213">Wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę** na pasku **Dyrektywy akcji lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-213">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="26b6a-214">Wybierz opcję **Edytuj kwerendę**, aby otworzyć edytor kwerend.</span><span class="sxs-lookup"><span data-stu-id="26b6a-214">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="26b6a-215">Na karcie **Zakres** upewnij się, że skonfigurowano dwa następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="26b6a-215">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="26b6a-216">Wiersz 1:</span><span class="sxs-lookup"><span data-stu-id="26b6a-216">Line 1:</span></span>

        - <span data-ttu-id="26b6a-217">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="26b6a-217">**Table:** *Locations*</span></span>
        - <span data-ttu-id="26b6a-218">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="26b6a-218">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="26b6a-219">**Pole:** *Magazyn*</span><span class="sxs-lookup"><span data-stu-id="26b6a-219">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="26b6a-220">**Kryteria:** *51*</span><span class="sxs-lookup"><span data-stu-id="26b6a-220">**Criteria:** *51*</span></span>

    - <span data-ttu-id="26b6a-221">Wiersz 2:</span><span class="sxs-lookup"><span data-stu-id="26b6a-221">Line 2:</span></span>

        - <span data-ttu-id="26b6a-222">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="26b6a-222">**Table:** *Locations*</span></span>
        - <span data-ttu-id="26b6a-223">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="26b6a-223">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="26b6a-224">**Pole:** *Lokalizacja*</span><span class="sxs-lookup"><span data-stu-id="26b6a-224">**Field:** *Location*</span></span>
        - <span data-ttu-id="26b6a-225">**Kryteria:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="26b6a-225">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="26b6a-226">Kliknij przycisk **OK**, aby zamknąć edytor.</span><span class="sxs-lookup"><span data-stu-id="26b6a-226">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="26b6a-227">Tworzenie elementu menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="26b6a-227">Create a mobile device menu item</span></span>

1. <span data-ttu-id="26b6a-228">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-228">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="26b6a-229">Na liście elementów menu w lewym okienku wybierz pozycję **Umieszczenie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-229">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="26b6a-230">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-230">Select **Edit**.</span></span>
1. <span data-ttu-id="26b6a-231">Na skróconej karcie **Klasy robocze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="26b6a-231">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="26b6a-232">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="26b6a-233">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="26b6a-233">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="26b6a-234">**Typ zlecenia pracy:** *Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="26b6a-234">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="26b6a-235">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-235">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="26b6a-236">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="26b6a-236">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="26b6a-237">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="26b6a-237">Create a purchase order</span></span>

<span data-ttu-id="26b6a-238">Aby utworzyć zamówienie zakupu jako źródło podaży, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="26b6a-238">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="26b6a-239">Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-239">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="26b6a-240">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-240">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="26b6a-241">W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-241">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="26b6a-242">**Konto dostawcy:** *104*</span><span class="sxs-lookup"><span data-stu-id="26b6a-242">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="26b6a-243">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="26b6a-243">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="26b6a-244">Wybierz **OK** i zanotuj numer zamówienia.</span><span class="sxs-lookup"><span data-stu-id="26b6a-244">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="26b6a-245">Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-245">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="26b6a-246">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-246">On this line, set the following values:</span></span>

    - <span data-ttu-id="26b6a-247">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="26b6a-247">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="26b6a-248">**Ilość:** *5*</span><span class="sxs-lookup"><span data-stu-id="26b6a-248">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="26b6a-249">Utwórz zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="26b6a-249">Create a sales order</span></span>

<span data-ttu-id="26b6a-250">Aby utworzyć zamówienie sprzedaży jako źródło popytu, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="26b6a-250">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="26b6a-251">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-251">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="26b6a-252">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-252">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="26b6a-253">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-253">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="26b6a-254">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="26b6a-254">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="26b6a-255">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="26b6a-255">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="26b6a-256">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-256">Select **OK**.</span></span>
1. <span data-ttu-id="26b6a-257">Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-257">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="26b6a-258">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="26b6a-258">On this line, set the following values:</span></span>

    - <span data-ttu-id="26b6a-259">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="26b6a-259">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="26b6a-260">**Ilość:** *3*</span><span class="sxs-lookup"><span data-stu-id="26b6a-260">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="26b6a-261">Utwórz planowany przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="26b6a-261">Create planned cross-docking</span></span>

<span data-ttu-id="26b6a-262">Aby utworzyć planowany przeładunek kompletacyjny na podstawie zamówienia sprzedaży, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="26b6a-262">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="26b6a-263">Na stronie **Szczegóły zamówienia sprzedaży** dla utworzonego właśnie zamówienia sprzedaży w okienku akcji na karcie **Magazyn** w grupie **Akcje**, wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-263">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="26b6a-264">Akcja zwolnienie do magazynu powoduje utworzenie wiersza wysyłki i ładunku dla wiersza zamówienia sprzedaży i próbuje alokować zapasy.</span><span class="sxs-lookup"><span data-stu-id="26b6a-264">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="26b6a-265">Zostanie wyświetlony komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="26b6a-265">You receive an informational message.</span></span> <span data-ttu-id="26b6a-266">Pojawia się także następujący komunikat ostrzegawczy: „Nie utworzono żadnej pracy dla grupy czynności XXXX.</span><span class="sxs-lookup"><span data-stu-id="26b6a-266">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="26b6a-267">Aby uzyskać szczegółowe informacje, zajrzyj do dziennika historii tworzenia pracy”.</span><span class="sxs-lookup"><span data-stu-id="26b6a-267">See the work creation history log for details."</span></span> <span data-ttu-id="26b6a-268">Takie zachowanie jest oczekiwane, ponieważ w magazynie nie ma zapasów.</span><span class="sxs-lookup"><span data-stu-id="26b6a-268">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="26b6a-269">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Magazyn** wybierz opcję **Szczegóły wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-269">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="26b6a-270">Zostanie wyświetlona strona **Szczegóły wysyłki**, która została utworzona dla danego wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="26b6a-270">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="26b6a-271">Na skróconej karcie **Wiersze ładunku**, w **Planowana ilość dla przeładunku kompletacyjnego** powinna być ustawiona wartość *3*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-271">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="26b6a-272">Ponieważ w magazynie nie było dostępnych zapasów, ale podano prawidłowe źródło dostaw w oknie czasu zdefiniowanym w szablonie przeładunku kompletacyjnego, zostanie utworzona ilość przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="26b6a-272">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="26b6a-273">Na skróconej karcie **Wiersze ładunku** wybierz opcję **Planowany przeładunek kompletacyjny**, aby wyświetlić szczegóły utworzonego przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="26b6a-273">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="26b6a-274">Przetwórz przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="26b6a-274">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="26b6a-275">Zlecenie zakupu otrzymane na mobilnej aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="26b6a-275">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="26b6a-276">System otrzyma ilość 5 od zamówienia zakupu w lokalizacji przyjęcia i utworzy dwie sztuki pracy.</span><span class="sxs-lookup"><span data-stu-id="26b6a-276">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="26b6a-277">Pierwszy utworzony identyfikator pracy ma wartość **Typ zlecenia pracy** *Przeładunek kompletacyjny* i jest połączony z zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="26b6a-277">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="26b6a-278">Ma ilość 3 i jest kierowana do ostatecznej lokalizacji wysyłki, dzięki czemu można ją wysłać natychmiast.</span><span class="sxs-lookup"><span data-stu-id="26b6a-278">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="26b6a-279">Drugi utworzony identyfikator pracy ma wartość **Typ zlecenia pracy** *Zlecenie zakupu* i jest połączony z zamówieniem zakupu.</span><span class="sxs-lookup"><span data-stu-id="26b6a-279">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="26b6a-280">Ta wartość ma pozostałą ilość 2, która nie została zadokowana i jest kierowana do umieszczenia w magazynie.</span><span class="sxs-lookup"><span data-stu-id="26b6a-280">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="26b6a-281">Zaloguj się do urządzenia przenośnego jako użytkownik w magazynie *51*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-281">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="26b6a-282">Przejdź do **Przychodzące \> Przyjęcia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-282">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="26b6a-283">W polu **PONum** wprowadź numer zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="26b6a-283">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="26b6a-284">W polu **Ilość** wpisz wartość *5*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-284">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="26b6a-285">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-285">Select **OK**.</span></span>
1. <span data-ttu-id="26b6a-286">Na następnej stronie w polu **Pozycja** wpisz *A0001*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-286">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="26b6a-287">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-287">Select **OK**.</span></span>
1. <span data-ttu-id="26b6a-288">Na następnej stronie potwierdź wartości **PONum**, **Pozycja** oraz **Ilość** klikając **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-288">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="26b6a-289">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="26b6a-289">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="26b6a-290">Wybierz **Anuluj**, aby wyjść.</span><span class="sxs-lookup"><span data-stu-id="26b6a-290">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="26b6a-291">Umieszczenie do przeładunku kompletacyjnego i sprzedaży zbiorczej</span><span class="sxs-lookup"><span data-stu-id="26b6a-291">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="26b6a-292">Obecnie oba identyfikatory pracy mają taki sam docelowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="26b6a-292">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="26b6a-293">Aby wykonać kolejne kroki, należy uzyskać identyfikator pracy i identyfikator docelowego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="26b6a-293">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="26b6a-294">Informacje te można uzyskać ze szczegółów pracy dla wiersza zamówienia zakupu oraz dla wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="26b6a-294">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="26b6a-295">Alternatywnie można przejść do **Zarządzanie magazynem \> Praca \> Szczegóły pracy** i odfiltrować wyniki dla wartości **Magazyn** *51*.</span><span class="sxs-lookup"><span data-stu-id="26b6a-295">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="26b6a-296">Na urządzeniu przenośnym przejdź do **Przychodzące \> Umieszczenie zakupu** i wprowadź docelowy numer identyfikacyjny pracy.</span><span class="sxs-lookup"><span data-stu-id="26b6a-296">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="26b6a-297">W polu **Identyfikator** wprowadź docelowy numer identyfikacyjny ze szczegółów dot. pracy.</span><span class="sxs-lookup"><span data-stu-id="26b6a-297">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="26b6a-298">Na stronie pobranie przeładunku kompletacyjnego jest wyświetlana lokalizacja pobrania (*RECV*), docelowy numer identyfikacyjny (*numer identyfikacyjny*), pozycja (*A0001*) oraz ilość (*3*).</span><span class="sxs-lookup"><span data-stu-id="26b6a-298">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="26b6a-299">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-299">Select **OK**.</span></span>
1. <span data-ttu-id="26b6a-300">W polu **Docelowy num. id.** wprowadź docelowy numer identyfikacyjny dla identyfikatora numeru identyfikacyjnego, który ma zostać umieszczony (przeładunek kompletacyjny) w lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="26b6a-300">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="26b6a-301">Możesz wybrać dowolny identyfikator numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="26b6a-301">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="26b6a-302">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-302">Select **OK**.</span></span>
1. <span data-ttu-id="26b6a-303">Na następnej stronie, w polu **Identyfikator** wprowadź docelowy numer identyfikacyjny ze szczegółów dot. pracy.</span><span class="sxs-lookup"><span data-stu-id="26b6a-303">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="26b6a-304">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-304">Select **OK**.</span></span>
1. <span data-ttu-id="26b6a-305">Potwierdź pracę w celu pobrania pozostałej ilości w wys. 2, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-305">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="26b6a-306">Na następnej stronie wybierz opcję **Gotowe**, aby zakończyć proces pobierania i rozpocząć proces umieszczenia.</span><span class="sxs-lookup"><span data-stu-id="26b6a-306">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="26b6a-307">Aplikacja mobilna zawiera adres i numer identyfikacyjny, w którym ma zostać umieszczony towar.</span><span class="sxs-lookup"><span data-stu-id="26b6a-307">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="26b6a-308">Potwierdź masowe przechowywanie **Umieść**, klikając **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-308">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="26b6a-309">Na następnej stronie potwierdź przeładunek kompletacyjny **Umieść**, klikając **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b6a-309">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="26b6a-310">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="26b6a-310">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="26b6a-311">Wybierz **Anuluj**, aby wyjść.</span><span class="sxs-lookup"><span data-stu-id="26b6a-311">Select **Cancel** to exit.</span></span>

<span data-ttu-id="26b6a-312">Na poniższej ilustracji przedstawiono sposób ukończenia pracy przeładunku kompletacyjnego w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="26b6a-312">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="26b6a-313">![Praca przeładunku kompletacyjnego została zakończona](media/PlannedCrossDockingWork.png "Praca przeładunku kompletacyjnego została zakończona")</span><span class="sxs-lookup"><span data-stu-id="26b6a-313">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]