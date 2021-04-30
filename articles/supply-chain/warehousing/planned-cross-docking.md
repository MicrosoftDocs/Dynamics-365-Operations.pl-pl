---
title: Planowany przeładunek kompletacyjny
description: W tym temacie opisano zaawansowane planowane przeładunki kompletacyjne, w którym ilość zapasów wymagana dla zamówienia jest skierowana bezpośrednio z paragonu lub tworzenia do właściwego doku załadunkowego lub obszaru tymczasowego. Wszystkie pozostałe zapasy ze źródła przychodzącego są kierowane do poprawnego miejsca przechowywania za pośrednictwem zwykłego procesu umieszczenia.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 11e044e04e05c68af676bf97e6085e9975da5c1d
ms.sourcegitcommit: bef7bd2aac00d7eb837fd275d383b7a5c3f1c1ee
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "5911255"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="892e5-104">Planowany przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="892e5-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="892e5-105">W tym temacie opisano zaawansowany planowany przeładunek kompletacyjny.</span><span class="sxs-lookup"><span data-stu-id="892e5-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="892e5-106">Zaawansowany planowany przeładunek kompletacyjny to proces magazynowy, w którym ilość zapasów wymagana dla zamówienia jest skierowana bezpośrednio z paragonu lub tworzenia do właściwego doku załadunkowego lub obszaru tymczasowego.</span><span class="sxs-lookup"><span data-stu-id="892e5-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="892e5-107">Wszystkie pozostałe zapasy ze źródła przychodzącego są kierowane do poprawnego miejsca przechowywania za pośrednictwem zwykłego procesu umieszczenia.</span><span class="sxs-lookup"><span data-stu-id="892e5-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="892e5-108">Proces ten pozwala pracownikom pominąć przychodzące umieszczenia i pobrania wychodzące zapasów, które są już oznaczone dla zamówienia wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="892e5-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="892e5-109">Z tego względu liczba przypadków, gdy zapasy są poruszane, jest zminimalizowana, jeśli to możliwe.</span><span class="sxs-lookup"><span data-stu-id="892e5-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="892e5-110">Ponadto, ponieważ mniejsza jest interakcja z systemem, wzrasta oszczędność czasu i miejsca w ramach produkcji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="892e5-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="892e5-111">Aby można było uruchomić przeładunek kompletacyjny, użytkownik musi skonfigurować nowy szablon przeładunku kompletacyjnego, w którym określono źródło dostaw i inne zestawy wymagań.</span><span class="sxs-lookup"><span data-stu-id="892e5-111">Before you can run cross-docking, you must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="892e5-112">Po utworzeniu zamówienia wychodzącego wiersz musi być zaznaczony względem zamówienia przychodzącego, które zawiera ten sam towar.</span><span class="sxs-lookup"><span data-stu-id="892e5-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span> <span data-ttu-id="892e5-113">Można wybrać pole kodu dyrektywy w szablonie przeładunku kompletacyjnego, podobnie jak w przypadku konfigurowania zamówień uzupełniania i zakupu.</span><span class="sxs-lookup"><span data-stu-id="892e5-113">You can select the directive code field on the cross-docking template, similar to the way you set up replenishment and purchase orders.</span></span>

<span data-ttu-id="892e5-114">W momencie przyjęcia zamówienia przychodzącego konfiguracja przeładunku kompletacyjnego automatycznie identyfikuje potrzebę przeładunku kompletacyjnego i tworzy pracę dla wymaganej ilości w oparciu o konfigurację dyrektywy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="892e5-114">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="892e5-115">Transakcje magazynowe *nie są* rejestrowane, gdy praca przeładunku kompletacyjnego została anulowana, nawet jeśli ustawienie tej funkcji jest włączone w parametrach zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="892e5-115">Inventory transactions are *not* unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="892e5-116">Włącz funkcje planowanego przeładunku kompletacyjnego</span><span class="sxs-lookup"><span data-stu-id="892e5-116">Turn on the planned cross docking features</span></span>

<span data-ttu-id="892e5-117">Jeśli Twój system nie zawiera jeszcze funkcji opisanych w tym temacie, przejdź do [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz następujące funkcje w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="892e5-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="892e5-118">*Planowany przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="892e5-118">*Planned cross docking*</span></span>
1. <span data-ttu-id="892e5-119">*Szablony przeładunku kompletacyjnego z dyrektywami lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="892e5-119">*Cross docking templates with location directives*</span></span>
    > [!NOTE]
    > <span data-ttu-id="892e5-120">Ta funkcja umożliwia ustawienie pola **Kod dyrektywy** w szablonie przeładunku kompletacyjny, podobnie jak w przypadku tworzenia szablonów uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="892e5-120">This feature enables the **Directive code** field to be specified on the cross-docking template, similar to the way you set up replenishment templates.</span></span> <span data-ttu-id="892e5-121">Włączenie tej funkcji zapobiega dodaniu kodu dyrektywy w wierszach szablonu pracy przeładunku kompletacyjnego dla wiersza końcowego *Odłożenie*.</span><span class="sxs-lookup"><span data-stu-id="892e5-121">Enabling this feature prevents you from adding a directive code on the cross-docking work template lines for the final *Put* line.</span></span> <span data-ttu-id="892e5-122">Zapewnia to, że ostateczną lokalizację odkładania można określić podczas tworzenia pracy przed rozważeniem szablonów pracy.</span><span class="sxs-lookup"><span data-stu-id="892e5-122">This ensures that the final put location can be determined during work creation before considering work templates.</span></span>

## <a name="setup"></a><span data-ttu-id="892e5-123">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="892e5-123">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="892e5-124">Ponowne generowanie metod księgowania ładunku</span><span class="sxs-lookup"><span data-stu-id="892e5-124">Regenerate load posting methods</span></span>

<span data-ttu-id="892e5-125">Planowany przeładunek kompletacyjny jest implementowany jako metoda księgowania ładunku.</span><span class="sxs-lookup"><span data-stu-id="892e5-125">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="892e5-126">Po włączeniu funkcji należy ponownie wygenerować metody.</span><span class="sxs-lookup"><span data-stu-id="892e5-126">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="892e5-127">Przejdź do **Zarządzania magazynem \> Konfiguracja \> Metody księgowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="892e5-127">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="892e5-128">W okienku akcji wybierz pozycję **Ponownie utwórz metody**.</span><span class="sxs-lookup"><span data-stu-id="892e5-128">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="892e5-129">Po zakończeniu ponownego generowania powinna być widoczna metoda, która ma wartość **Nazwa metody** *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="892e5-129">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="892e5-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="892e5-130">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="892e5-131">Tworzenie szablonu przeładunku kompletacyjnego</span><span class="sxs-lookup"><span data-stu-id="892e5-131">Create a cross-docking template</span></span>

1. <span data-ttu-id="892e5-132">Przejdź kolejno do pozycji **Zarządzanie magazynem \> Konfiguracja \> Praca \> Szablony przeładunku kompletacyjnego**.</span><span class="sxs-lookup"><span data-stu-id="892e5-132">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="892e5-133">W okienku akcji wybierz opcję **Nowe**, aby utworzyć szablon.</span><span class="sxs-lookup"><span data-stu-id="892e5-133">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="892e5-134">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-134">In the header, set the following values:</span></span>

    - <span data-ttu-id="892e5-135">**Sekwencja:** *1*</span><span class="sxs-lookup"><span data-stu-id="892e5-135">**Sequence:** *1*</span></span>

        <span data-ttu-id="892e5-136">To pole określa kolejność, w jakiej są oceniane szablony.</span><span class="sxs-lookup"><span data-stu-id="892e5-136">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="892e5-137">**Identyfikator szablonu przeładunku kompletacyjnego** *51*</span><span class="sxs-lookup"><span data-stu-id="892e5-137">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="892e5-138">**Opis:** *Magazyn 51*</span><span class="sxs-lookup"><span data-stu-id="892e5-138">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="892e5-139">**Zasady zwalniania popytu** *Przed przyjęciem dostawy*</span><span class="sxs-lookup"><span data-stu-id="892e5-139">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="892e5-140">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="892e5-140">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="892e5-141">Konfiguracja na skróconej karcie **Planowanie** decyduje o sposobie działania szablonu.</span><span class="sxs-lookup"><span data-stu-id="892e5-141">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="892e5-142">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-142">Set the following values:</span></span>

    - <span data-ttu-id="892e5-143">**Wymagania dotyczące popytu:** *Brak*</span><span class="sxs-lookup"><span data-stu-id="892e5-143">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="892e5-144">To pole definiuje wymagania dotyczące zapasów zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="892e5-144">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="892e5-145">Jeśli zapotrzebowanie musi być połączone z dostawą przed zwolnieniem, wybierz opcję *Zaznaczenie*.</span><span class="sxs-lookup"><span data-stu-id="892e5-145">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="892e5-146">Jeśli zapotrzebowanie musi być zarezerwowane na podstawie zamówienia przed zwolnieniem, wybierz opcję *Rezerwacja zamówienia*.</span><span class="sxs-lookup"><span data-stu-id="892e5-146">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="892e5-147">**Lokalizowanie typu:** *Lokalizacje wysyłki*</span><span class="sxs-lookup"><span data-stu-id="892e5-147">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="892e5-148">To pole określa, czy w ramach pracy przeładunku kompletacyjnego powinny być używane lokalizacje pośredniego/ładunku z wysyłki, czy też mają być używane dyrektywy lokalizacji w celu znalezienia własnych lokalizacji przemieszczania/ładunku.</span><span class="sxs-lookup"><span data-stu-id="892e5-148">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="892e5-149">**Szablon pracy:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="892e5-149">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="892e5-150">To pole definiuje szablon pracy, który ma być używany podczas tworzenia przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="892e5-150">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="892e5-151">**Sprawdź ponownie na paragonie dostawy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="892e5-151">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="892e5-152">Ta opcja umożliwia zdefiniowanie, czy dostawa ma zostać sprawdzona ponownie podczas przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="892e5-152">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="892e5-153">Jeśli ta opcja ma wartość *Tak*, sprawdzane są zarówno maksymalne przedziały czasu, jak i zakres daty ważności.</span><span class="sxs-lookup"><span data-stu-id="892e5-153">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="892e5-154">Pole **Kod dyrektywy:** należy pozostawić puste</span><span class="sxs-lookup"><span data-stu-id="892e5-154">**Directive code:** Leave this field blank</span></span>

        <span data-ttu-id="892e5-155">Ta opcja jest włączona przez funkcję *Szablony przeładunku kompletarnego z dyrektywami lokalizacji*.</span><span class="sxs-lookup"><span data-stu-id="892e5-155">This option is enabled by the *Cross docking templates with location directives* feature.</span></span> <span data-ttu-id="892e5-156">System korzysta z dyrektyw lokalizacji, aby pomóc w określeniu najlepszej lokalizacji do przeniesienia zapasów kompletacyjnych.</span><span class="sxs-lookup"><span data-stu-id="892e5-156">The system uses location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="892e5-157">Możesz to skonfigurować, przypisując kod dyrektywy do każdego odpowiedniego szablonu przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="892e5-157">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="892e5-158">Jeśli kod dyrektywy jest ustawiony, kiedy praca musi zostać wygenerowana, system przeszuka dyrektywy lokalizacji według kodu dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="892e5-158">If a directive code is set, the system will search location directives by directive code when work is generated.</span></span> <span data-ttu-id="892e5-159">W ten sposób można ograniczyć dyrektywy lokalizacji, które są używane dla określonego szablonu przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="892e5-159">In this way, you can limit location directives that are used for a particular cross-docking template.</span></span>

    - <span data-ttu-id="892e5-160">**Sprawdzanie poprawności – okno czasowe:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="892e5-160">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="892e5-161">Ta opcja służy do definiowania, czy w przypadku wybrania źródła dostaw ma być oceniany maksymalny przedział czasu.</span><span class="sxs-lookup"><span data-stu-id="892e5-161">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="892e5-162">Jeśli ta opcja ma wartość *Tak*, pola związane z maksymalnym i minimalnym okienkiem czasowym staną się dostępne.</span><span class="sxs-lookup"><span data-stu-id="892e5-162">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="892e5-163">**Okienko czasu maksymalnego:** *5*</span><span class="sxs-lookup"><span data-stu-id="892e5-163">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="892e5-164">To pole określa maksymalny dopuszczalny okres między pojawieniem się dostawy a wysłaniem zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="892e5-164">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="892e5-165">**Maksymalna jednostka okna czasu:** *Dni*</span><span class="sxs-lookup"><span data-stu-id="892e5-165">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="892e5-166">**Okienko czasu minimalnego:** *0*</span><span class="sxs-lookup"><span data-stu-id="892e5-166">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="892e5-167">To pole określa minimalny dopuszczalny okres między pojawieniem się dostawy a wysłaniem zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="892e5-167">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="892e5-168">**Minimalna jednostka okna czasu:** *Dni*</span><span class="sxs-lookup"><span data-stu-id="892e5-168">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="892e5-169">**Zakres dni daty ważności:** *0*</span><span class="sxs-lookup"><span data-stu-id="892e5-169">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="892e5-170">*Kryterium pierwsze do wygaśnięcia – pierwsze do wyjścia (FEFO):* to pole określa maksymalną liczbę dni między datą ważności pierwszej partii, która znajduje się obecnie w magazynie a otrzymaną partią.</span><span class="sxs-lookup"><span data-stu-id="892e5-170">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="892e5-171">Na skróconej karcie **Źródła dostaw** można określić typy dostaw, które są prawidłowe dla tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="892e5-171">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="892e5-172">Wybierz opcję **Nowe**, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-172">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="892e5-173">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="892e5-173">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="892e5-174">**Źródło dostawy:** *Zamówienie zakupu*</span><span class="sxs-lookup"><span data-stu-id="892e5-174">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="892e5-175">Tworzenie klasy roboczej</span><span class="sxs-lookup"><span data-stu-id="892e5-175">Create a work class</span></span>

1. <span data-ttu-id="892e5-176">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.</span><span class="sxs-lookup"><span data-stu-id="892e5-176">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="892e5-177">W okienku akcji wybierz opcję **Nowe**, aby utworzyć klasę roboczą.</span><span class="sxs-lookup"><span data-stu-id="892e5-177">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="892e5-178">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-178">Set the following values:</span></span>

    - <span data-ttu-id="892e5-179">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="892e5-179">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="892e5-180">**Opis:** *Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="892e5-180">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="892e5-181">**Typ zlecenia pracy:** *Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="892e5-181">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="892e5-182">Tworzenie szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="892e5-182">Create a work template</span></span>

1. <span data-ttu-id="892e5-183">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="892e5-183">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="892e5-184">W polu **Typ zlecenia pracy** ustaw pozycję *Przeładunek kompletacyjny*.</span><span class="sxs-lookup"><span data-stu-id="892e5-184">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="892e5-185">W okienku akcji wybierz opcję **Nowe**, aby dodać nowy wiersz do karty **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="892e5-185">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="892e5-186">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="892e5-187">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="892e5-187">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="892e5-188">**Szablon pracy** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="892e5-188">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="892e5-189">**Opis szablonu pracy** *51 Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="892e5-189">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="892e5-190">Wybierz opcję **Zapisz**, aby skrócona karta **Szczegóły szablonu pracy** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="892e5-190">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="892e5-191">Na skróconej karcie **Szczegółów dot. szablonu pracy** wybierz opcję **Nowy**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="892e5-191">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="892e5-192">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-192">On the new line, set the following values:</span></span>

    - <span data-ttu-id="892e5-193">**Typ pracy:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="892e5-193">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="892e5-194">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="892e5-194">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="892e5-195">Wybierz polecenie **Nowy**, aby dodać dodatkowy wiersz i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-195">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="892e5-196">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="892e5-196">**Work type:** *Put*</span></span>
    - <span data-ttu-id="892e5-197">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="892e5-197">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="892e5-198">Wybierz opcję **Zapisz** i upewnij się, że zaznaczono pole wyboru **Prawidłowe** dla szablonu *51 Cross Dock*.</span><span class="sxs-lookup"><span data-stu-id="892e5-198">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="892e5-199">Identyfikatory klas roboczych dla typów pracy *Pobranie* i *Umieszczenie* muszą być takie same.</span><span class="sxs-lookup"><span data-stu-id="892e5-199">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="892e5-200">Tworzenie dyrektyw lokalizacji</span><span class="sxs-lookup"><span data-stu-id="892e5-200">Create location directives</span></span>

1. <span data-ttu-id="892e5-201">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="892e5-201">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="892e5-202">W lewym okienku w polu **Typ zlecenia produkcyjnego** ustaw wartość na *Przeładunek kompletacyjny*.</span><span class="sxs-lookup"><span data-stu-id="892e5-202">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="892e5-203">Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-203">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="892e5-204">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="892e5-204">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="892e5-205">**Nazwa:** *51 Cross Dock Put*</span><span class="sxs-lookup"><span data-stu-id="892e5-205">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="892e5-206">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="892e5-206">**Work type:** *Put*</span></span>
    - <span data-ttu-id="892e5-207">**Oddział:** *5*</span><span class="sxs-lookup"><span data-stu-id="892e5-207">**Site:** *5*</span></span>
    - <span data-ttu-id="892e5-208">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="892e5-208">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="892e5-209">Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="892e5-209">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="892e5-210">Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="892e5-210">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="892e5-211">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-211">On the new line, set the following values:</span></span>

    - <span data-ttu-id="892e5-212">**Od ilości:** *1*</span><span class="sxs-lookup"><span data-stu-id="892e5-212">**From quantity:** *1*</span></span>
    - <span data-ttu-id="892e5-213">**Do ilości:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="892e5-213">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="892e5-214">Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="892e5-214">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="892e5-215">Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="892e5-215">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="892e5-216">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-216">On the new line, set the following values:</span></span>

    - <span data-ttu-id="892e5-217">**Nazwa:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="892e5-217">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="892e5-218">**Stałe użycie lokalizacji:** *Stałe i niestałe lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="892e5-218">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="892e5-219">Wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę** na pasku **Dyrektywy akcji lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="892e5-219">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="892e5-220">Wybierz opcję **Edytuj kwerendę**, aby otworzyć edytor kwerend.</span><span class="sxs-lookup"><span data-stu-id="892e5-220">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="892e5-221">Na karcie **Zakres** upewnij się, że skonfigurowano dwa następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="892e5-221">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="892e5-222">Wiersz 1:</span><span class="sxs-lookup"><span data-stu-id="892e5-222">Line 1:</span></span>

        - <span data-ttu-id="892e5-223">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="892e5-223">**Table:** *Locations*</span></span>
        - <span data-ttu-id="892e5-224">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="892e5-224">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="892e5-225">**Pole:** *Magazyn*</span><span class="sxs-lookup"><span data-stu-id="892e5-225">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="892e5-226">**Kryteria:** *51*</span><span class="sxs-lookup"><span data-stu-id="892e5-226">**Criteria:** *51*</span></span>

    - <span data-ttu-id="892e5-227">Wiersz 2:</span><span class="sxs-lookup"><span data-stu-id="892e5-227">Line 2:</span></span>

        - <span data-ttu-id="892e5-228">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="892e5-228">**Table:** *Locations*</span></span>
        - <span data-ttu-id="892e5-229">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="892e5-229">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="892e5-230">**Pole:** *Lokalizacja*</span><span class="sxs-lookup"><span data-stu-id="892e5-230">**Field:** *Location*</span></span>
        - <span data-ttu-id="892e5-231">**Kryteria:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="892e5-231">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="892e5-232">Kliknij przycisk **OK**, aby zamknąć edytor.</span><span class="sxs-lookup"><span data-stu-id="892e5-232">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="892e5-233">Tworzenie elementu menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="892e5-233">Create a mobile device menu item</span></span>

1. <span data-ttu-id="892e5-234">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="892e5-234">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="892e5-235">Na liście elementów menu w lewym okienku wybierz pozycję **Umieszczenie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="892e5-235">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="892e5-236">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="892e5-236">Select **Edit**.</span></span>
1. <span data-ttu-id="892e5-237">Na skróconej karcie **Klasy robocze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="892e5-237">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="892e5-238">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-238">On the new line, set the following values:</span></span>

    - <span data-ttu-id="892e5-239">**Identyfikator klasy roboczej:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="892e5-239">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="892e5-240">**Typ zlecenia pracy:** *Przeładunek kompletacyjny*</span><span class="sxs-lookup"><span data-stu-id="892e5-240">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="892e5-241">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="892e5-241">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="892e5-242">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="892e5-242">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="892e5-243">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="892e5-243">Create a purchase order</span></span>

<span data-ttu-id="892e5-244">Aby utworzyć zamówienie zakupu jako źródło podaży, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="892e5-244">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="892e5-245">Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="892e5-245">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="892e5-246">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="892e5-246">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="892e5-247">W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-247">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="892e5-248">**Konto dostawcy:** *104*</span><span class="sxs-lookup"><span data-stu-id="892e5-248">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="892e5-249">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="892e5-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="892e5-250">Wybierz **OK** i zanotuj numer zamówienia.</span><span class="sxs-lookup"><span data-stu-id="892e5-250">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="892e5-251">Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="892e5-251">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="892e5-252">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-252">On this line, set the following values:</span></span>

    - <span data-ttu-id="892e5-253">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="892e5-253">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="892e5-254">**Ilość:** *5*</span><span class="sxs-lookup"><span data-stu-id="892e5-254">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="892e5-255">Utwórz zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="892e5-255">Create a sales order</span></span>

<span data-ttu-id="892e5-256">Aby utworzyć zamówienie sprzedaży jako źródło popytu, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="892e5-256">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="892e5-257">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="892e5-257">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="892e5-258">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="892e5-258">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="892e5-259">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-259">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="892e5-260">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="892e5-260">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="892e5-261">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="892e5-261">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="892e5-262">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-262">Select **OK**.</span></span>
1. <span data-ttu-id="892e5-263">Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="892e5-263">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="892e5-264">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="892e5-264">On this line, set the following values:</span></span>

    - <span data-ttu-id="892e5-265">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="892e5-265">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="892e5-266">**Ilość:** *3*</span><span class="sxs-lookup"><span data-stu-id="892e5-266">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="892e5-267">Utwórz planowany przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="892e5-267">Create planned cross-docking</span></span>

<span data-ttu-id="892e5-268">Aby utworzyć planowany przeładunek kompletacyjny na podstawie zamówienia sprzedaży, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="892e5-268">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="892e5-269">Na stronie **Szczegóły zamówienia sprzedaży** dla utworzonego właśnie zamówienia sprzedaży w okienku akcji na karcie **Magazyn** w grupie **Akcje**, wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="892e5-269">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="892e5-270">Akcja zwolnienie do magazynu powoduje utworzenie wiersza wysyłki i ładunku dla wiersza zamówienia sprzedaży i próbuje alokować zapasy.</span><span class="sxs-lookup"><span data-stu-id="892e5-270">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="892e5-271">Zostanie wyświetlony komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="892e5-271">You receive an informational message.</span></span> <span data-ttu-id="892e5-272">Pojawia się także następujący komunikat ostrzegawczy: „Nie utworzono żadnej pracy dla grupy czynności XXXX.</span><span class="sxs-lookup"><span data-stu-id="892e5-272">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="892e5-273">Aby uzyskać szczegółowe informacje, zajrzyj do dziennika historii tworzenia pracy”.</span><span class="sxs-lookup"><span data-stu-id="892e5-273">See the work creation history log for details."</span></span> <span data-ttu-id="892e5-274">Takie zachowanie jest oczekiwane, ponieważ w magazynie nie ma zapasów.</span><span class="sxs-lookup"><span data-stu-id="892e5-274">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="892e5-275">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Magazyn** wybierz opcję **Szczegóły wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="892e5-275">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="892e5-276">Zostanie wyświetlona strona **Szczegóły wysyłki**, która została utworzona dla danego wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="892e5-276">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="892e5-277">Na skróconej karcie **Wiersze ładunku**, w **Planowana ilość dla przeładunku kompletacyjnego** powinna być ustawiona wartość *3*.</span><span class="sxs-lookup"><span data-stu-id="892e5-277">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="892e5-278">Ponieważ w magazynie nie było dostępnych zapasów, ale podano prawidłowe źródło dostaw w oknie czasu zdefiniowanym w szablonie przeładunku kompletacyjnego, zostanie utworzona ilość przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="892e5-278">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="892e5-279">Na skróconej karcie **Wiersze ładunku** wybierz opcję **Planowany przeładunek kompletacyjny**, aby wyświetlić szczegóły utworzonego przeładunku kompletacyjnego.</span><span class="sxs-lookup"><span data-stu-id="892e5-279">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="892e5-280">Przetwórz przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="892e5-280">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="892e5-281">Zlecenie zakupu otrzymane na mobilnej aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="892e5-281">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="892e5-282">System otrzyma ilość 5 od zamówienia zakupu w lokalizacji przyjęcia i utworzy dwie sztuki pracy.</span><span class="sxs-lookup"><span data-stu-id="892e5-282">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="892e5-283">Pierwszy utworzony identyfikator pracy ma wartość **Typ zlecenia pracy** *Przeładunek kompletacyjny* i jest połączony z zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="892e5-283">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="892e5-284">Ma ilość 3 i jest kierowana do ostatecznej lokalizacji wysyłki, dzięki czemu można ją wysłać natychmiast.</span><span class="sxs-lookup"><span data-stu-id="892e5-284">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="892e5-285">Drugi utworzony identyfikator pracy ma wartość **Typ zlecenia pracy** *Zlecenie zakupu* i jest połączony z zamówieniem zakupu.</span><span class="sxs-lookup"><span data-stu-id="892e5-285">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="892e5-286">Ta wartość ma pozostałą ilość 2, która nie została zadokowana i jest kierowana do umieszczenia w magazynie.</span><span class="sxs-lookup"><span data-stu-id="892e5-286">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="892e5-287">Zaloguj się do urządzenia przenośnego jako użytkownik w magazynie *51*.</span><span class="sxs-lookup"><span data-stu-id="892e5-287">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="892e5-288">Przejdź do **Przychodzące \> Przyjęcia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="892e5-288">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="892e5-289">W polu **PONum** wprowadź numer zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="892e5-289">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="892e5-290">W polu **Ilość** wpisz wartość *5*.</span><span class="sxs-lookup"><span data-stu-id="892e5-290">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="892e5-291">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-291">Select **OK**.</span></span>
1. <span data-ttu-id="892e5-292">Na następnej stronie w polu **Pozycja** wpisz *A0001*.</span><span class="sxs-lookup"><span data-stu-id="892e5-292">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="892e5-293">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-293">Select **OK**.</span></span>
1. <span data-ttu-id="892e5-294">Na następnej stronie potwierdź wartości **PONum**, **Pozycja** oraz **Ilość** klikając **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-294">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="892e5-295">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="892e5-295">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="892e5-296">Wybierz **Anuluj**, aby wyjść.</span><span class="sxs-lookup"><span data-stu-id="892e5-296">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="892e5-297">Umieszczenie do przeładunku kompletacyjnego i sprzedaży zbiorczej</span><span class="sxs-lookup"><span data-stu-id="892e5-297">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="892e5-298">Obecnie oba identyfikatory pracy mają taki sam docelowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="892e5-298">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="892e5-299">Aby wykonać kolejne kroki, należy uzyskać identyfikator pracy i identyfikator docelowego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="892e5-299">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="892e5-300">Informacje te można uzyskać ze szczegółów pracy dla wiersza zamówienia zakupu oraz dla wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="892e5-300">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="892e5-301">Alternatywnie można przejść do **Zarządzanie magazynem \> Praca \> Szczegóły pracy** i odfiltrować wyniki dla wartości **Magazyn** *51*.</span><span class="sxs-lookup"><span data-stu-id="892e5-301">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="892e5-302">Na urządzeniu przenośnym przejdź do **Przychodzące \> Umieszczenie zakupu** i wprowadź docelowy numer identyfikacyjny pracy.</span><span class="sxs-lookup"><span data-stu-id="892e5-302">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="892e5-303">W polu **Identyfikator** wprowadź docelowy numer identyfikacyjny ze szczegółów dot. pracy.</span><span class="sxs-lookup"><span data-stu-id="892e5-303">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="892e5-304">Na stronie pobranie przeładunku kompletacyjnego jest wyświetlana lokalizacja pobrania (*RECV*), docelowy numer identyfikacyjny (*numer identyfikacyjny*), pozycja (*A0001*) oraz ilość (*3*).</span><span class="sxs-lookup"><span data-stu-id="892e5-304">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="892e5-305">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-305">Select **OK**.</span></span>
1. <span data-ttu-id="892e5-306">W polu **Docelowy num. id.** wprowadź docelowy numer identyfikacyjny dla identyfikatora numeru identyfikacyjnego, który ma zostać umieszczony (przeładunek kompletacyjny) w lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="892e5-306">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="892e5-307">Możesz wybrać dowolny identyfikator numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="892e5-307">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="892e5-308">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-308">Select **OK**.</span></span>
1. <span data-ttu-id="892e5-309">Na następnej stronie, w polu **Identyfikator** wprowadź docelowy numer identyfikacyjny ze szczegółów dot. pracy.</span><span class="sxs-lookup"><span data-stu-id="892e5-309">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="892e5-310">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-310">Select **OK**.</span></span>
1. <span data-ttu-id="892e5-311">Potwierdź pracę w celu pobrania pozostałej ilości w wys. 2, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-311">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="892e5-312">Na następnej stronie wybierz opcję **Gotowe**, aby zakończyć proces pobierania i rozpocząć proces umieszczenia.</span><span class="sxs-lookup"><span data-stu-id="892e5-312">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="892e5-313">Aplikacja mobilna zawiera adres i numer identyfikacyjny, w którym ma zostać umieszczony towar.</span><span class="sxs-lookup"><span data-stu-id="892e5-313">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="892e5-314">Potwierdź masowe przechowywanie **Umieść**, klikając **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-314">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="892e5-315">Na następnej stronie potwierdź przeładunek kompletacyjny **Umieść**, klikając **OK**.</span><span class="sxs-lookup"><span data-stu-id="892e5-315">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="892e5-316">Zostanie wyświetlony komunikat „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="892e5-316">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="892e5-317">Wybierz **Anuluj**, aby wyjść.</span><span class="sxs-lookup"><span data-stu-id="892e5-317">Select **Cancel** to exit.</span></span>

<span data-ttu-id="892e5-318">Na poniższej ilustracji przedstawiono sposób ukończenia pracy przeładunku kompletacyjnego w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="892e5-318">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="892e5-319">![Praca przeładunku kompletacyjnego została zakończona](media/PlannedCrossDockingWork.png "Praca przeładunku kompletacyjnego została zakończona")</span><span class="sxs-lookup"><span data-stu-id="892e5-319">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]