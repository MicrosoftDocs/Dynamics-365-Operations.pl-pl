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
ms.openlocfilehash: fb598b3ac7dd72e8c500f0c2eaf07462009c67f7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970313"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="09261-104">Planowany przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="09261-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="09261-105">W tym temacie opisano zaawansowany planowany przeładunek kompletacyjny.</span><span class="sxs-lookup"><span data-stu-id="09261-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="09261-106">Zaawansowany planowany przeładunek kompletacyjny to proces magazynowy, w którym ilość zapasów wymagana dla zamówienia jest skierowana bezpośrednio z paragonu lub tworzenia do właściwego doku załadunkowego lub obszaru tymczasowego.</span><span class="sxs-lookup"><span data-stu-id="09261-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="09261-107">Wszystkie pozostałe zapasy ze źródła przychodzącego są kierowane do poprawnego miejsca przechowywania za pośrednictwem zwykłego procesu umieszczenia.</span><span class="sxs-lookup"><span data-stu-id="09261-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="09261-108">Proces ten pozwala pracownikom pominąć przychodzące umieszczenia i pobrania wychodzące zapasów, które są już oznaczone dla zamówienia wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="09261-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="09261-109">Z tego względu liczba przypadków, gdy zapasy są poruszane, jest zminimalizowana, jeśli to możliwe.</span><span class="sxs-lookup"><span data-stu-id="09261-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="09261-110">Ponadto, ponieważ mniejsza jest interakcja z systemem, wzrasta oszczędność czasu i miejsca w ramach produkcji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="09261-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="09261-111">Aby można było uruchomić przeładunek kompletacyjny, użytkownik musi skonfigurować nowy szablon przeładunku kompletacyjnego, w którym określono źródło dostaw i inne zestawy wymagań.</span><span class="sxs-lookup"><span data-stu-id="09261-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="09261-112">Po utworzeniu zamówienia wychodzącego wiersz musi być zaznaczony względem zamówienia przychodzącego, które zawiera ten sam towar.</span><span class="sxs-lookup"><span data-stu-id="09261-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="09261-113">W momencie przyjęcia zamówienia przychodzącego konfiguracja przeładunku kompletacyjnego automatycznie identyfikuje potrzebę przeładunku kompletacyjnego i tworzy pracę dla wymaganej ilości w oparciu o konfigurację dyrektywy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="09261-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="09261-114">Transakcje magazynowe **nie są** rejestrowane, gdy praca przeładunku kompletacyjnego została anulowana, nawet jeśli ustawienie tej funkcji jest włączone w parametrach zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="09261-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-feature"></a><span data-ttu-id="09261-115">Włącz funkcję planowanego przeładunku kompletacyjnego</span><span class="sxs-lookup"><span data-stu-id="09261-115">Turn on the Planned cross docking feature</span></span>

<span data-ttu-id="09261-116">Aby można było korzystać z funkcji zaawansowanego planowanego przeładunku kompletacyjnego, funkcja ta musi być włączona w systemie.</span><span class="sxs-lookup"><span data-stu-id="09261-116">Before you can use advanced planned cross-docking, the feature must be turned on in your system.</span></span> <span data-ttu-id="09261-117">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="09261-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="09261-118">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="09261-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="09261-119">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="09261-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="09261-120">**Nazwa funkcji:** *Planowany zaawansowany przeładunek kompletacyjnego*</span><span class="sxs-lookup"><span data-stu-id="09261-120">**Feature name:** *Planned cross docking*</span></span>

## <a name="setup"></a><span data-ttu-id="09261-121">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="09261-121">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="09261-122">Ponowne generowanie metod księgowania ładunku</span><span class="sxs-lookup"><span data-stu-id="09261-122">Regenerate load posting methods</span></span>

<span data-ttu-id="09261-123">Planowany przeładunek kompletacyjny jest implementowany jako metoda księgowania ładunku.</span><span class="sxs-lookup"><span data-stu-id="09261-123">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="09261-124">Po włączeniu funkcji należy ponownie wygenerować metody.</span><span class="sxs-lookup"><span data-stu-id="09261-124">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="09261-125">Przejdź do **Zarządzania magazynem \> Konfiguracja \> Metody księgowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="09261-125">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="09261-126">W okienku akcji wybierz pozycję **Ponownie utwórz metody**.</span><span class="sxs-lookup"><span data-stu-id="09261-126">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="09261-127">Po zakończeniu ponownego generowania powinna być widoczna metoda, która ma wartość **Nazwa metody** *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="09261-127">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="09261-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="09261-128">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="09261-129">Tworzenie szablonu przeładunku kompletacyjnego</span><span class="sxs-lookup"><span data-stu-id="09261-129">Create a cross-docking template</span></span>

1. <span data-ttu-id="09261-130">Przejdź kolejno do pozycji **Zarządzanie magazynem \> Konfiguracja \> Praca \> Szablony przeładunku kompletacyjnego**.</span><span class="sxs-lookup"><span data-stu-id="09261-130">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="09261-131">W okienku akcji wybierz opcję **Nowe**, aby utworzyć szablon.</span><span class="sxs-lookup"><span data-stu-id="09261-131">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="09261-132">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-132">In the header, set the following values:</span></span>

    - <span data-ttu-id="09261-133">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="09261-133">**Sequence:** *1*</span></span>

        <span data-ttu-id="09261-134">To pole określa kolejność, w jakiej są oceniane szablony.</span><span class="sxs-lookup"><span data-stu-id="09261-134">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="09261-135">**Identyfikator szablonu przeładunku kompletacyjnego** *51*</span><span class="sxs-lookup"><span data-stu-id="09261-135">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="09261-136">**Opis:** *Magazyn 51*</span><span class="sxs-lookup"><span data-stu-id="09261-136">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="09261-137">**Zasady zwalniania popytu** *Przed przyjęciem dostawy*</span><span class="sxs-lookup"><span data-stu-id="09261-137">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="09261-138">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="09261-138">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="09261-139">Konfiguracja na skróconej karcie **Planowanie** decyduje o sposobie działania szablonu.</span><span class="sxs-lookup"><span data-stu-id="09261-139">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="09261-140">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-140">Set the following values:</span></span>

    - <span data-ttu-id="09261-141">**Wymagania dotyczące popytu:** *Brak*</span><span class="sxs-lookup"><span data-stu-id="09261-141">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="09261-142">To pole definiuje wymagania dotyczące zapasów zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="09261-142">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="09261-143">Jeśli zapotrzebowanie musi być połączone z dostawą przed zwolnieniem, wybierz opcję *Zaznaczenie*.</span><span class="sxs-lookup"><span data-stu-id="09261-143">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="09261-144">Jeśli zapotrzebowanie musi być zarezerwowane na podstawie zamówienia przed zwolnieniem, wybierz opcję *Rezerwacja zamówienia*.</span><span class="sxs-lookup"><span data-stu-id="09261-144">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="09261-145">**Lokalizowanie typu:** *Lokalizacje wysyłki*</span><span class="sxs-lookup"><span data-stu-id="09261-145">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="09261-146">To pole określa, czy w ramach pracy przeładunku kompletacyjnego powinny być używane lokalizacje pośredniego/ładunku z wysyłki, czy też mają być używane dyrektywy lokalizacji w celu znalezienia własnych lokalizacji przemieszczania/ładunku.</span><span class="sxs-lookup"><span data-stu-id="09261-146">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="09261-147">**Szablon pracy:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="09261-147">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="09261-148">To pole definiuje szablon pracy, który ma być używany podczas tworzenia przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="09261-148">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="09261-149">**Sprawdź ponownie na paragonie dostawy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="09261-149">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="09261-150">Ta opcja umożliwia zdefiniowanie, czy dostawa ma zostać sprawdzona ponownie podczas przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="09261-150">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="09261-151">Jeśli ta opcja ma wartość *Tak*, sprawdzane są zarówno maksymalne przedziały czasu, jak i zakres daty ważności.</span><span class="sxs-lookup"><span data-stu-id="09261-151">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="09261-152">**Sprawdzanie poprawności – okno czasowe:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="09261-152">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="09261-153">Ta opcja służy do definiowania, czy w przypadku wybrania źródła dostaw ma być oceniany maksymalny przedział czasu.</span><span class="sxs-lookup"><span data-stu-id="09261-153">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="09261-154">Jeśli ta opcja ma wartość *Tak*, pola związane z maksymalnym i minimalnym okienkiem czasowym staną się dostępne.</span><span class="sxs-lookup"><span data-stu-id="09261-154">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="09261-155">**Okienko czasu maksymalnego:** *5*</span><span class="sxs-lookup"><span data-stu-id="09261-155">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="09261-156">To pole określa maksymalny dopuszczalny okres między pojawieniem się dostawy a wysłaniem zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="09261-156">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="09261-157">**Maksymalna jednostka okna czasu:** *Dni*</span><span class="sxs-lookup"><span data-stu-id="09261-157">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="09261-158">**Okienko czasu minimalnego:** *0*</span><span class="sxs-lookup"><span data-stu-id="09261-158">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="09261-159">To pole określa minimalny dopuszczalny okres między pojawieniem się dostawy a wysłaniem zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="09261-159">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="09261-160">**Minimalna jednostka okna czasu:** *Dni*</span><span class="sxs-lookup"><span data-stu-id="09261-160">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="09261-161">**Zakres dni daty ważności:** *0*</span><span class="sxs-lookup"><span data-stu-id="09261-161">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="09261-162">*Kryterium pierwsze do wygaśnięcia – pierwsze do wyjścia (FEFO):* to pole określa maksymalną liczbę dni między datą ważności pierwszej partii, która znajduje się obecnie w magazynie a otrzymaną partią.</span><span class="sxs-lookup"><span data-stu-id="09261-162">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="09261-163">Na skróconej karcie **Źródła dostaw** można określić typy dostaw, które są prawidłowe dla tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="09261-163">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="09261-164">Wybierz opcję **Nowe**, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-164">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="09261-165">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="09261-165">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="09261-166">**Źródło dostawy:** *Zamówienie zakupu*</span><span class="sxs-lookup"><span data-stu-id="09261-166">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="09261-167">Tworzenie klasy roboczej</span><span class="sxs-lookup"><span data-stu-id="09261-167">Create a work class</span></span>

1. <span data-ttu-id="09261-168">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.</span><span class="sxs-lookup"><span data-stu-id="09261-168">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="09261-169">W okienku akcji wybierz opcję **Nowe**, aby utworzyć klasę roboczą.</span><span class="sxs-lookup"><span data-stu-id="09261-169">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="09261-170">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-170">Set the following values:</span></span>

    - <span data-ttu-id="09261-171">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="09261-171">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="09261-172">**Opis:** *Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="09261-172">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="09261-173">**Typ zlecenia pracy:** *Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="09261-173">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="09261-174">Tworzenie szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="09261-174">Create a work template</span></span>

1. <span data-ttu-id="09261-175">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="09261-175">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="09261-176">W polu **Typ zlecenia pracy** ustaw pozycję *Przeładunek kompletacyjny*.</span><span class="sxs-lookup"><span data-stu-id="09261-176">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="09261-177">W okienku akcji wybierz opcję **Nowe**, aby dodać nowy wiersz do karty **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="09261-177">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="09261-178">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-178">On the new line, set the following values:</span></span>

    - <span data-ttu-id="09261-179">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="09261-179">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="09261-180">**Szablon pracy** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="09261-180">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="09261-181">**Opis szablonu pracy** *51 Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="09261-181">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="09261-182">Wybierz opcję **Zapisz**, aby skrócona karta **Szczegóły szablonu pracy** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="09261-182">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="09261-183">Na skróconej karcie **Szczegółów dot. szablonu pracy** wybierz opcję **Nowy**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="09261-183">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="09261-184">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-184">On the new line, set the following values:</span></span>

    - <span data-ttu-id="09261-185">**Typ pracy:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="09261-185">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="09261-186">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="09261-186">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="09261-187">Wybierz polecenie **Nowy**, aby dodać dodatkowy wiersz i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-187">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="09261-188">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="09261-188">**Work type:** *Put*</span></span>
    - <span data-ttu-id="09261-189">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="09261-189">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="09261-190">Wybierz opcję **Zapisz** i upewnij się, że zaznaczono pole wyboru **Prawidłowe** dla szablonu *51 Cross Dock*.</span><span class="sxs-lookup"><span data-stu-id="09261-190">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="09261-191">Identyfikatory klas roboczych dla typów pracy *Pobranie* i *Umieszczenie* muszą być takie same.</span><span class="sxs-lookup"><span data-stu-id="09261-191">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="09261-192">Tworzenie dyrektyw lokalizacji</span><span class="sxs-lookup"><span data-stu-id="09261-192">Create location directives</span></span>

1. <span data-ttu-id="09261-193">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="09261-193">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="09261-194">W lewym okienku w polu **Typ zlecenia produkcyjnego** ustaw wartość na *Przeładunek kompletacyjny*.</span><span class="sxs-lookup"><span data-stu-id="09261-194">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="09261-195">Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-195">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="09261-196">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="09261-196">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="09261-197">**Nazwa:** *51 Cross Dock Put*</span><span class="sxs-lookup"><span data-stu-id="09261-197">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="09261-198">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="09261-198">**Work type:** *Put*</span></span>
    - <span data-ttu-id="09261-199">**Oddział:** *5*</span><span class="sxs-lookup"><span data-stu-id="09261-199">**Site:** *5*</span></span>
    - <span data-ttu-id="09261-200">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="09261-200">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="09261-201">Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="09261-201">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="09261-202">Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="09261-202">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="09261-203">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-203">On the new line, set the following values:</span></span>

    - <span data-ttu-id="09261-204">**Od ilości:** *1*</span><span class="sxs-lookup"><span data-stu-id="09261-204">**From quantity:** *1*</span></span>
    - <span data-ttu-id="09261-205">**Do ilości:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="09261-205">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="09261-206">Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="09261-206">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="09261-207">Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="09261-207">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="09261-208">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="09261-209">**Nazwa:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="09261-209">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="09261-210">**Stałe użycie lokalizacji:** *Stałe i niestałe lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="09261-210">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="09261-211">Wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę** na pasku **Dyrektywy akcji lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="09261-211">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="09261-212">Wybierz opcję **Edytuj kwerendę**, aby otworzyć edytor kwerend.</span><span class="sxs-lookup"><span data-stu-id="09261-212">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="09261-213">Na karcie **Zakres** upewnij się, że skonfigurowano dwa następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="09261-213">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="09261-214">Wiersz 1:</span><span class="sxs-lookup"><span data-stu-id="09261-214">Line 1:</span></span>

        - <span data-ttu-id="09261-215">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="09261-215">**Table:** *Locations*</span></span>
        - <span data-ttu-id="09261-216">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="09261-216">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="09261-217">**Pole:** *Magazyn*</span><span class="sxs-lookup"><span data-stu-id="09261-217">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="09261-218">**Kryteria:** *51*</span><span class="sxs-lookup"><span data-stu-id="09261-218">**Criteria:** *51*</span></span>

    - <span data-ttu-id="09261-219">Wiersz 2:</span><span class="sxs-lookup"><span data-stu-id="09261-219">Line 2:</span></span>

        - <span data-ttu-id="09261-220">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="09261-220">**Table:** *Locations*</span></span>
        - <span data-ttu-id="09261-221">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="09261-221">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="09261-222">**Pole:** *Lokalizacja*</span><span class="sxs-lookup"><span data-stu-id="09261-222">**Field:** *Location*</span></span>
        - <span data-ttu-id="09261-223">**Kryteria:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="09261-223">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="09261-224">Kliknij przycisk **OK**, aby zamknąć edytor.</span><span class="sxs-lookup"><span data-stu-id="09261-224">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="09261-225">Tworzenie elementu menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="09261-225">Create a mobile device menu item</span></span>

1. <span data-ttu-id="09261-226">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="09261-226">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="09261-227">Na liście elementów menu w lewym okienku wybierz pozycję **Umieszczenie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="09261-227">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="09261-228">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="09261-228">Select **Edit**.</span></span>
1. <span data-ttu-id="09261-229">Na skróconej karcie **Klasy robocze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="09261-229">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="09261-230">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-230">On the new line, set the following values:</span></span>

    - <span data-ttu-id="09261-231">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="09261-231">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="09261-232">**Typ zlecenia pracy:** *Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="09261-232">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="09261-233">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="09261-233">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="09261-234">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="09261-234">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="09261-235">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="09261-235">Create a purchase order</span></span>

<span data-ttu-id="09261-236">Aby utworzyć zamówienie zakupu jako źródło podaży, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="09261-236">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="09261-237">Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="09261-237">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="09261-238">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="09261-238">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="09261-239">W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-239">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="09261-240">**Konto dostawcy:** *104*</span><span class="sxs-lookup"><span data-stu-id="09261-240">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="09261-241">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="09261-241">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="09261-242">Wybierz **OK** i zanotuj numer zamówienia.</span><span class="sxs-lookup"><span data-stu-id="09261-242">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="09261-243">Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="09261-243">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="09261-244">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-244">On this line, set the following values:</span></span>

    - <span data-ttu-id="09261-245">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="09261-245">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="09261-246">**Ilość:** *5*</span><span class="sxs-lookup"><span data-stu-id="09261-246">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="09261-247">Utwórz zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="09261-247">Create a sales order</span></span>

<span data-ttu-id="09261-248">Aby utworzyć zamówienie sprzedaży jako źródło popytu, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="09261-248">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="09261-249">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="09261-249">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="09261-250">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="09261-250">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="09261-251">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-251">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="09261-252">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="09261-252">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="09261-253">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="09261-253">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="09261-254">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-254">Select **OK**.</span></span>
1. <span data-ttu-id="09261-255">Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="09261-255">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="09261-256">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="09261-256">On this line, set the following values:</span></span>

    - <span data-ttu-id="09261-257">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="09261-257">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="09261-258">**Ilość:** *3*</span><span class="sxs-lookup"><span data-stu-id="09261-258">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="09261-259">Utwórz planowany przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="09261-259">Create planned cross-docking</span></span>

<span data-ttu-id="09261-260">Aby utworzyć planowany przeładunek kompletacyjny na podstawie zamówienia sprzedaży, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="09261-260">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="09261-261">Na stronie **Szczegóły zamówienia sprzedaży** dla utworzonego właśnie zamówienia sprzedaży w okienku akcji na karcie **Magazyn** w grupie **Akcje**, wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="09261-261">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="09261-262">Akcja zwolnienie do magazynu powoduje utworzenie wiersza wysyłki i ładunku dla wiersza zamówienia sprzedaży i próbuje alokować zapasy.</span><span class="sxs-lookup"><span data-stu-id="09261-262">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="09261-263">Zostanie wyświetlony komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="09261-263">You receive an informational message.</span></span> <span data-ttu-id="09261-264">Pojawia się także następujący komunikat ostrzegawczy: „Nie utworzono żadnej pracy dla grupy czynności XXXX.</span><span class="sxs-lookup"><span data-stu-id="09261-264">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="09261-265">Aby uzyskać szczegółowe informacje, zajrzyj do dziennika historii tworzenia pracy”.</span><span class="sxs-lookup"><span data-stu-id="09261-265">See the work creation history log for details."</span></span> <span data-ttu-id="09261-266">Takie zachowanie jest oczekiwane, ponieważ w magazynie nie ma zapasów.</span><span class="sxs-lookup"><span data-stu-id="09261-266">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="09261-267">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Magazyn** wybierz opcję **Szczegóły wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="09261-267">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="09261-268">Zostanie wyświetlona strona **Szczegóły wysyłki**, która została utworzona dla danego wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="09261-268">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="09261-269">Na skróconej karcie **Wiersze ładunku**, w **Planowana ilość dla przeładunku kompletacyjnego** powinna być ustawiona wartość *3*.</span><span class="sxs-lookup"><span data-stu-id="09261-269">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="09261-270">Ponieważ w magazynie nie było dostępnych zapasów, ale podano prawidłowe źródło dostaw w oknie czasu zdefiniowanym w szablonie przeładunku kompletacyjnego, zostanie utworzona ilość przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="09261-270">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="09261-271">Na skróconej karcie **Wiersze ładunku** wybierz opcję **Planowany przeładunek kompletacyjny**, aby wyświetlić szczegóły utworzonego przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="09261-271">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="09261-272">Przetwórz przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="09261-272">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="09261-273">Zlecenie zakupu otrzymane na mobilnej aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="09261-273">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="09261-274">System otrzyma ilość 5 od zamówienia zakupu w lokalizacji przyjęcia i utworzy dwie sztuki pracy.</span><span class="sxs-lookup"><span data-stu-id="09261-274">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="09261-275">Pierwszy utworzony identyfikator pracy ma wartość **Typ zlecenia pracy** *Przeładunek kompletacyjny* i jest połączony z zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="09261-275">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="09261-276">Ma ilość 3 i jest kierowana do ostatecznej lokalizacji wysyłki, dzięki czemu można ją wysłać natychmiast.</span><span class="sxs-lookup"><span data-stu-id="09261-276">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="09261-277">Drugi utworzony identyfikator pracy ma wartość **Typ zlecenia pracy** *Zlecenie zakupu* i jest połączony z zamówieniem zakupu.</span><span class="sxs-lookup"><span data-stu-id="09261-277">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="09261-278">Ta wartość ma pozostałą ilość 2, która nie została zadokowana i jest kierowana do umieszczenia w magazynie.</span><span class="sxs-lookup"><span data-stu-id="09261-278">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="09261-279">Zaloguj się do urządzenia przenośnego jako użytkownik w magazynie *51*.</span><span class="sxs-lookup"><span data-stu-id="09261-279">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="09261-280">Przejdź do **Przychodzące \> Przyjęcia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="09261-280">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="09261-281">W polu **PONum** wprowadź numer zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="09261-281">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="09261-282">W polu **Ilość** wpisz wartość *5*.</span><span class="sxs-lookup"><span data-stu-id="09261-282">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="09261-283">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-283">Select **OK**.</span></span>
1. <span data-ttu-id="09261-284">Na następnej stronie w polu **Pozycja** wpisz *A0001*.</span><span class="sxs-lookup"><span data-stu-id="09261-284">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="09261-285">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-285">Select **OK**.</span></span>
1. <span data-ttu-id="09261-286">Na następnej stronie potwierdź wartości **PONum**, **Pozycja** oraz **Ilość** klikając **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-286">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="09261-287">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="09261-287">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="09261-288">Wybierz **Anuluj**, aby wyjść.</span><span class="sxs-lookup"><span data-stu-id="09261-288">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="09261-289">Umieszczenie do przeładunku kompletacyjnego i sprzedaży zbiorczej</span><span class="sxs-lookup"><span data-stu-id="09261-289">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="09261-290">Obecnie oba identyfikatory pracy mają taki sam docelowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="09261-290">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="09261-291">Aby wykonać kolejne kroki, należy uzyskać identyfikator pracy i identyfikator docelowego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="09261-291">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="09261-292">Informacje te można uzyskać ze szczegółów pracy dla wiersza zamówienia zakupu oraz dla wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="09261-292">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="09261-293">Alternatywnie można przejść do **Zarządzanie magazynem \> Praca \> Szczegóły pracy** i odfiltrować wyniki dla wartości **Magazyn** *51*.</span><span class="sxs-lookup"><span data-stu-id="09261-293">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="09261-294">Na urządzeniu przenośnym przejdź do **Przychodzące \> Umieszczenie zakupu** i wprowadź docelowy numer identyfikacyjny pracy.</span><span class="sxs-lookup"><span data-stu-id="09261-294">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="09261-295">W polu **Identyfikator** wprowadź docelowy numer identyfikacyjny ze szczegółów dot. pracy.</span><span class="sxs-lookup"><span data-stu-id="09261-295">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="09261-296">Na stronie pobranie przeładunku kompletacyjnego jest wyświetlana lokalizacja pobrania (*RECV*), docelowy numer identyfikacyjny (*numer identyfikacyjny*), pozycja (*A0001*) oraz ilość (*3*).</span><span class="sxs-lookup"><span data-stu-id="09261-296">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="09261-297">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-297">Select **OK**.</span></span>
1. <span data-ttu-id="09261-298">W polu **Docelowy num. id.** wprowadź docelowy numer identyfikacyjny dla identyfikatora numeru identyfikacyjnego, który ma zostać umieszczony (przeładunek kompletacyjny) w lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="09261-298">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="09261-299">Możesz wybrać dowolny identyfikator numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="09261-299">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="09261-300">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-300">Select **OK**.</span></span>
1. <span data-ttu-id="09261-301">Na następnej stronie, w polu **Identyfikator** wprowadź docelowy numer identyfikacyjny ze szczegółów dot. pracy.</span><span class="sxs-lookup"><span data-stu-id="09261-301">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="09261-302">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-302">Select **OK**.</span></span>
1. <span data-ttu-id="09261-303">Potwierdź pracę w celu pobrania pozostałej ilości w wys. 2, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-303">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="09261-304">Na następnej stronie wybierz opcję **Gotowe**, aby zakończyć proces pobierania i rozpocząć proces umieszczenia.</span><span class="sxs-lookup"><span data-stu-id="09261-304">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="09261-305">Aplikacja mobilna zawiera adres i numer identyfikacyjny, w którym ma zostać umieszczony towar.</span><span class="sxs-lookup"><span data-stu-id="09261-305">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="09261-306">Potwierdź masowe przechowywanie **Umieść**, klikając **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-306">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="09261-307">Na następnej stronie potwierdź przeładunek kompletacyjny **Umieść**, klikając **OK**.</span><span class="sxs-lookup"><span data-stu-id="09261-307">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="09261-308">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="09261-308">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="09261-309">Wybierz **Anuluj**, aby wyjść.</span><span class="sxs-lookup"><span data-stu-id="09261-309">Select **Cancel** to exit.</span></span>

<span data-ttu-id="09261-310">Na poniższej ilustracji przedstawiono sposób ukończenia pracy przeładunku kompletacyjnego w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="09261-310">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="09261-311">![Praca przeładunku kompletacyjnego została zakończona](media/PlannedCrossDockingWork.png "Praca przeładunku kompletacyjnego została zakończona")</span><span class="sxs-lookup"><span data-stu-id="09261-311">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>
