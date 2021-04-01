---
title: Stanowisko w grupie pełne
description: Ten temat zawiera informacje dotyczące funkcji Stanowisko w grupie pełne. Ta funkcja oferuje alternatywę dla sztywnego egzekwowania reguł przerwy w pracy, gdy jest używana funkcja pobierania dla grupy. Zezwala ona na większy margines błędu w ramach ograniczeń dotyczących objętości kontenerów lub pojemników.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b6a7cad070377de58d21a8eb91ee3e1ffaf1c660
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233014"
---
# <a name="cluster-position-full"></a><span data-ttu-id="b928a-104">Stanowisko w grupie pełne</span><span class="sxs-lookup"><span data-stu-id="b928a-104">Cluster position full</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b928a-105">Funkcja *Stanowisko w grupie pełne* oferuje alternatywę dla sztywnego egzekwowania reguł przerwy w pracy, gdy jest używana funkcja pobierania dla grupy. Zezwala ona na większy margines błędu w ramach ograniczeń dotyczących objętości kontenerów lub pojemników.</span><span class="sxs-lookup"><span data-stu-id="b928a-105">The *Cluster position full* feature offers an alternative to more rigid enforcement of work break rules when cluster picking is used, because it enables a larger margin of error in the volumetric constraints of containers or totes.</span></span> <span data-ttu-id="b928a-106">W typowym przebiegu pracy nie wszystkie towary w zleceniu pracy mieszczą się w wybranym kontenerze.</span><span class="sxs-lookup"><span data-stu-id="b928a-106">In a common scenario, not all items on a work order fit into a selected container.</span></span> <span data-ttu-id="b928a-107">Pracownicy magazynowi, którzy pobierają z grupy, mają w takiej sytuacji tylko kilka opcji: muszą zmienić rozmiar kontenera na większy lub porozmawiać z przełożonym w i znaleźć jakieś inne rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="b928a-107">Warehouse workers who are cluster picking have few options in this scenario: they must either change to a larger container size or work with their supervisor to come up with a different solution.</span></span>

<span data-ttu-id="b928a-108">Ta funkcja wprowadza możliwość skorzystania z przycisku **Pełne** przy jednej z jednostek pracy w grupie.</span><span class="sxs-lookup"><span data-stu-id="b928a-108">This feature introduces the ability to run the **Full** button on one of the work units in a cluster.</span></span> <span data-ttu-id="b928a-109">W starszych wersjach ta opcja była dostępna tylko w przypadku pobierania zamówienia zwykłego, a nie w przypadku pobierania z grupy.</span><span class="sxs-lookup"><span data-stu-id="b928a-109">In older versions, this option was available only for regular order picking, not for cluster picking.</span></span> <span data-ttu-id="b928a-110">Jednak ta funkcja różni się od standardowego przycisku **Pełne**, gdyż anuluje pozostałą pracę.</span><span class="sxs-lookup"><span data-stu-id="b928a-110">However, this feature differs from the standard **Full** button in that it cancels the remaining work.</span></span> <span data-ttu-id="b928a-111">Nie sugeruje to użytkownikowi dodaia kolejnego pojemnika do tego samego klastra i nie powoduje automatycznego utworzenia nowej pracy.</span><span class="sxs-lookup"><span data-stu-id="b928a-111">It doesn't suggest that the user add another bin to the same cluster, and it doesn't automatically create new work.</span></span>

## <a name="turn-on-the-cluster-position-full-feature"></a><span data-ttu-id="b928a-112">Włącz funkcję „Stanowisko w grupie pełne”</span><span class="sxs-lookup"><span data-stu-id="b928a-112">Turn on the Cluster position full feature</span></span>

<span data-ttu-id="b928a-113">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="b928a-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="b928a-114">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją.</span><span class="sxs-lookup"><span data-stu-id="b928a-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="b928a-115">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="b928a-115">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b928a-116">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="b928a-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b928a-117">**Nazwa funkcji:** *Stanowisko w grupie pełne*</span><span class="sxs-lookup"><span data-stu-id="b928a-117">**Feature name:** *Cluster position full*</span></span>

## <a name="setup"></a><span data-ttu-id="b928a-118">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="b928a-118">Setup</span></span>

<span data-ttu-id="b928a-119">W tej sekcji znajdują się wskazówki i sposób konfigurowania i używania funkcji *Stanowisko w grupie pełne*.</span><span class="sxs-lookup"><span data-stu-id="b928a-119">This section provides guidelines, and an example that shows how to set up and use the *Cluster position full* feature.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="b928a-120">Udostępnianie danych pokazowych</span><span class="sxs-lookup"><span data-stu-id="b928a-120">Make sample data available</span></span>

<span data-ttu-id="b928a-121">Aby pracować z tymi [przykładowymi scenariuszami](#example-scenario) przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b928a-121">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="b928a-122">Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="b928a-122">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="b928a-123">Tego scenariusza przykładowego można również używać jako wskazówek podczas używania danej funkcji w produkcji.</span><span class="sxs-lookup"><span data-stu-id="b928a-123">You can also use the example scenario as guidance for working with this feature on a production system.</span></span> <span data-ttu-id="b928a-124">Jednak w takim przypadku należy podstawić własne wartości dla ustawień opisanych w tym polu.</span><span class="sxs-lookup"><span data-stu-id="b928a-124">However, in that case, you must substitute your own values for the settings that are described here.</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="b928a-125">Profile grup</span><span class="sxs-lookup"><span data-stu-id="b928a-125">Cluster profiles</span></span>

<span data-ttu-id="b928a-126">Należy określić, czy identyfikatory grupy są generowane automatycznie, jaka jest liczba stanowisk, kiedy grupy są przerywane oraz jak wygląda sekwencja i weryfikacja pracy pobierania.</span><span class="sxs-lookup"><span data-stu-id="b928a-126">You must specify whether cluster IDs are automatically generated, how many positions are used, when clusters are broken, and how the picking work is sequenced and verified.</span></span>

1. <span data-ttu-id="b928a-127">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Profile grup**.</span><span class="sxs-lookup"><span data-stu-id="b928a-127">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="b928a-128">W okienku listy wybierz opcję rekord **Utwórz grupę**.</span><span class="sxs-lookup"><span data-stu-id="b928a-128">In the list pane, select the **Create Cluster** record.</span></span>
1. <span data-ttu-id="b928a-129">Na skróconej karcie **Ogólne** zweryfikuj następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b928a-129">On the **General** FastTab, verify the following values:</span></span>

    - <span data-ttu-id="b928a-130">**Generuj identyfikator grupy:** — wybierz opcję *Tak*</span><span class="sxs-lookup"><span data-stu-id="b928a-130">**Generate cluster ID:** *Yes*</span></span>
    - <span data-ttu-id="b928a-131">**Aktywuj stanowiska:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="b928a-131">**Activate positions:** *Yes*</span></span>
    - <span data-ttu-id="b928a-132">**Liczba stanowisk:** *2*</span><span class="sxs-lookup"><span data-stu-id="b928a-132">**Number of positions:** *2*</span></span>
    - <span data-ttu-id="b928a-133">**Nazwa stanowiska:** *Numeryczne*</span><span class="sxs-lookup"><span data-stu-id="b928a-133">**Position name:** *Numeric*</span></span>
    - <span data-ttu-id="b928a-134">**Podziel grupę w:** — wybierz pozycję *Odłożenie*.</span><span class="sxs-lookup"><span data-stu-id="b928a-134">**Break cluster at:** *Put*</span></span>
    - <span data-ttu-id="b928a-135">**Typ weryfikacji sortowania:** *Skan pozycji*</span><span class="sxs-lookup"><span data-stu-id="b928a-135">**Sort verification type:** *Position scan*</span></span>

1. <span data-ttu-id="b928a-136">Na skróconej karcie **Sortowanie grupy**.</span><span class="sxs-lookup"><span data-stu-id="b928a-136">In the **Cluster sorting** FastTab.</span></span> <span data-ttu-id="b928a-137">Siatka powinna być pusta (czyli nie powinna zawierać żadnych wierszy).</span><span class="sxs-lookup"><span data-stu-id="b928a-137">The grid should be blank (that is, it should contain no lines).</span></span>

### <a name="work-templates"></a><span data-ttu-id="b928a-138">Szablony pracy</span><span class="sxs-lookup"><span data-stu-id="b928a-138">Work templates</span></span>

<span data-ttu-id="b928a-139">Należy określić sposób tworzenia pracy pobierania dla pobierania dla grup.</span><span class="sxs-lookup"><span data-stu-id="b928a-139">You must define how the picking work for cluster picking is created.</span></span>

1. <span data-ttu-id="b928a-140">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="b928a-140">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="b928a-141">U góry strony, w polu **Typ zlecenia produkcyjnego** ustaw wartość *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="b928a-141">At the top of the page, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="b928a-142">Upewnij się, że spośród danych demonstracyjnych są wymienione następujące szablony pracy.</span><span class="sxs-lookup"><span data-stu-id="b928a-142">Make sure that the following work templates from the demo data are listed.</span></span> <span data-ttu-id="b928a-143">Jeśli nie są one dostępne, nie można ukończyć tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="b928a-143">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="b928a-144">61 Zamówienie sprzedaży — etap</span><span class="sxs-lookup"><span data-stu-id="b928a-144">61 SO Stage</span></span>
    - <span data-ttu-id="b928a-145">61 Zamówienie sprzedaży — pobranie z grupy</span><span class="sxs-lookup"><span data-stu-id="b928a-145">61 SO Cluster pick</span></span>

### <a name="location-directives"></a><span data-ttu-id="b928a-146">Dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="b928a-146">Location directives</span></span>

<span data-ttu-id="b928a-147">Należy określić, skąd towary są pobierane i gdzie są umieszczane.</span><span class="sxs-lookup"><span data-stu-id="b928a-147">You must specify where items are picked from and where they are put.</span></span>

1. <span data-ttu-id="b928a-148">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="b928a-148">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="b928a-149">W nagłówku listy w polu **Typ zlecenia pracy** zaznacz opcję *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="b928a-149">In the list header, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="b928a-150">Upewnij się, że spośród danych demonstracyjnych są wymienione następujące dyrektywy zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b928a-150">Make sure that the following sales order directives from the demo data are listed.</span></span> <span data-ttu-id="b928a-151">Jeśli nie są one dostępne, nie można ukończyć tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="b928a-151">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="b928a-152">61 pobranie z grupy</span><span class="sxs-lookup"><span data-stu-id="b928a-152">61 Cluster pick</span></span>
    - <span data-ttu-id="b928a-153">61 Zamówienie sprzedaży — pobranie zamówienia</span><span class="sxs-lookup"><span data-stu-id="b928a-153">61 SO Pick order</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="b928a-154">Elementy menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="b928a-154">Mobile device menu items</span></span>

<span data-ttu-id="b928a-155">Należy skonfigurować menu urządzenia przenośnego do wykorzystania istniejącej pracy, która jest sterowana przez pobieranie dla grup.</span><span class="sxs-lookup"><span data-stu-id="b928a-155">You must configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="b928a-156">W elemencie menu urządzenia przenośnego do pobierania grupy musi być włączona opcja **Zezwalaj na dzielenie pracy** oraz musi być dodana klasa pracy *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="b928a-156">In the mobile device menu item for cluster picking, the **Allow splitting of work** parameter must be turned on, and the *SO Pick* work class must be added.</span></span>

1. <span data-ttu-id="b928a-157">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="b928a-157">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="b928a-158">W okienku listy wybierz rekord **Utwórz pobieranie dla grupy**.</span><span class="sxs-lookup"><span data-stu-id="b928a-158">In the list pane, select the **Cluster Pick Create** record.</span></span>
1. <span data-ttu-id="b928a-159">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="b928a-159">Select **Edit** in the Action pane.</span></span>
1. <span data-ttu-id="b928a-160">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b928a-160">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="b928a-161">**Zarządzane przez:** *Pobieranie dla grupy*</span><span class="sxs-lookup"><span data-stu-id="b928a-161">**Directed by:** *Cluster picking*</span></span>
    - <span data-ttu-id="b928a-162">**Generuj numer identyfikacyjny:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="b928a-162">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="b928a-163">**Zezwalaj na dzielenie pracy:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="b928a-163">**Allow splitting of work:** *Yes*</span></span>
    - <span data-ttu-id="b928a-164">**Identyfikator profilu grupy:** *Utwórz grupę*</span><span class="sxs-lookup"><span data-stu-id="b928a-164">**Cluster profile ID:** *Create Cluster*</span></span>

    <span data-ttu-id="b928a-165">Zaakceptuj wartość domyślną we wszystkich pozostałych polach.</span><span class="sxs-lookup"><span data-stu-id="b928a-165">Accept the default values for all other fields.</span></span>

1. <span data-ttu-id="b928a-166">W przypadku skróconej karty **Klasa pracy**, w razie potrzeby dodaj następujące dwa wiersze:</span><span class="sxs-lookup"><span data-stu-id="b928a-166">On the **Work classes** FastTab, add the following two lines, as required:</span></span>

    - <span data-ttu-id="b928a-167">Wiersz 1 (zwykle obecny w danych demonstracyjnych):</span><span class="sxs-lookup"><span data-stu-id="b928a-167">Line 1 (usually present in demo data):</span></span>

        - <span data-ttu-id="b928a-168">**Identyfikator klasy roboczej:** *Sprzedaż*</span><span class="sxs-lookup"><span data-stu-id="b928a-168">**Work class ID:** *Sales*</span></span> 
        - <span data-ttu-id="b928a-169">**Typ zamówienia pracy:** *zamówienia sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="b928a-169">**Work order type:** *Sales orders*</span></span>

    - <span data-ttu-id="b928a-170">Wiersz 2 (zwykle nieobecny w danych demonstracyjnych):</span><span class="sxs-lookup"><span data-stu-id="b928a-170">Line 2 (probably not present in demo data):</span></span>

        - <span data-ttu-id="b928a-171">**Identyfikator klasy roboczej:** *Pobranie zamówienia sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="b928a-171">**Work class ID:** *SO Pick*</span></span>
        - <span data-ttu-id="b928a-172">**Typ zamówienia pracy:** *zamówienia sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="b928a-172">**Work order type:** *Sales orders*</span></span>

1. <span data-ttu-id="b928a-173">Przejdź do **Ustawień potwierdzenia pracy** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="b928a-173">Go to **Work confirmation setup** in the Action pane.</span></span>
1. <span data-ttu-id="b928a-174">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="b928a-174">Select **Edit**.</span></span>
1. <span data-ttu-id="b928a-175">Wprowadź jedną z następujących wartości w wierszu na siatce.</span><span class="sxs-lookup"><span data-stu-id="b928a-175">Enter the following values on the line in grid.</span></span>
    - <span data-ttu-id="b928a-176">**Typ pracy** - *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="b928a-176">**Work type** - *Pick*</span></span>
    - <span data-ttu-id="b928a-177">**Potwierdzenie produktu** - *Zaznacz pole wyboru*</span><span class="sxs-lookup"><span data-stu-id="b928a-177">**Product confirmation** - *Select the check box*</span></span>

1. <span data-ttu-id="b928a-178">Wybierz **Zapisz** w okienku akcji i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b928a-178">Select **Save** in the Action pane and close the page.</span></span>

## <a name="create-picking-work"></a><span data-ttu-id="b928a-179">Tworzenie pracy pobrania</span><span class="sxs-lookup"><span data-stu-id="b928a-179">Create picking work</span></span>

<span data-ttu-id="b928a-180">Aby można było uruchomić pobieranie z grupy, należy utworzyć kilka prac wychodzących.</span><span class="sxs-lookup"><span data-stu-id="b928a-180">Before you can start cluster picking, you must create some outbound work.</span></span> <span data-ttu-id="b928a-181">Utworzony wcześniej profil grupy określa dwie pozycje grupy.</span><span class="sxs-lookup"><span data-stu-id="b928a-181">The cluster profile that you created earlier specifies two cluster positions.</span></span> <span data-ttu-id="b928a-182">Dla pobrania zamówienia sprzedaży trzeba utworzyć co najmniej dwa identyfikatory robocze.</span><span class="sxs-lookup"><span data-stu-id="b928a-182">Therefore, at least two work IDs must be created for sales order picking.</span></span> <span data-ttu-id="b928a-183">W tym scenariuszu transakcje będą mieć miejsce w magazynie *61* i będą korzystały z towarów *L0101* i *T0100*.</span><span class="sxs-lookup"><span data-stu-id="b928a-183">For this scenario, transactions will occur in warehouse *61*, and they will use items *L0101* and *T0100*.</span></span> <span data-ttu-id="b928a-184">Dane demonstracyjne powinny zawierać wystarczająco dużo dostępnych zapasów tych towarów.</span><span class="sxs-lookup"><span data-stu-id="b928a-184">The demo data should have enough on-hand inventory of these items.</span></span> <span data-ttu-id="b928a-185">Upewnij się, że masz wystarczające zapasy do ukończenia transakcji.</span><span class="sxs-lookup"><span data-stu-id="b928a-185">Make sure that you have enough inventory to complete the transactions.</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="b928a-186">Utwórz zamówienie sprzedaży 1</span><span class="sxs-lookup"><span data-stu-id="b928a-186">Create sales order 1</span></span>

1. <span data-ttu-id="b928a-187">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b928a-187">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b928a-188">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="b928a-188">Select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="b928a-189">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b928a-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b928a-190">**Konto odbiorcy:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="b928a-190">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="b928a-191">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="b928a-191">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="b928a-192">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b928a-192">Select **OK**.</span></span>
1. <span data-ttu-id="b928a-193">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="b928a-193">The new sales order is opened.</span></span> <span data-ttu-id="b928a-194">Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="b928a-194">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="b928a-195">**Numer pozycji:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="b928a-195">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="b928a-196">**Ilość:** *5*</span><span class="sxs-lookup"><span data-stu-id="b928a-196">**Quantity:** *5*</span></span>

1. <span data-ttu-id="b928a-197">W polu **Potwierdzona data dostawy** na karcie **Ustawienia** na skróconej karcie **Szczegóły wiersza** należy ustawić dzisiejszą datę.</span><span class="sxs-lookup"><span data-stu-id="b928a-197">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="b928a-198">Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj drugi wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="b928a-198">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="b928a-199">**Numer pozycji:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="b928a-199">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="b928a-200">**Ilość:** *20*</span><span class="sxs-lookup"><span data-stu-id="b928a-200">**Quantity:** *20*</span></span>

1. <span data-ttu-id="b928a-201">W polu **Potwierdzona data dostawy** na karcie **Ustawienia** na skróconej karcie **Szczegóły wiersza** należy ustawić dzisiejszą datę.</span><span class="sxs-lookup"><span data-stu-id="b928a-201">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="b928a-202">Dla każdego właśnie dodanego wiersza należy wykonać następujące kroki, aby zarezerwować zapasy:</span><span class="sxs-lookup"><span data-stu-id="b928a-202">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="b928a-203">Wybierz wiersz do zarezerwowania.</span><span class="sxs-lookup"><span data-stu-id="b928a-203">Select the line to reserve.</span></span>
    2. <span data-ttu-id="b928a-204">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="b928a-204">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="b928a-205">Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.</span><span class="sxs-lookup"><span data-stu-id="b928a-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="b928a-206">Zamknij stronę **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="b928a-206">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="b928a-207">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="b928a-207">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="b928a-208">Po wykonaniu zwolnienia, użytkownik otrzymuje komunikaty informacyjne, które zawierają identyfikator grupy czynności oraz identyfikator wysyłki.</span><span class="sxs-lookup"><span data-stu-id="b928a-208">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="b928a-209">Utwórz zamówienie sprzedaży 2</span><span class="sxs-lookup"><span data-stu-id="b928a-209">Create sales order 2</span></span>

1. <span data-ttu-id="b928a-210">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b928a-210">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b928a-211">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="b928a-211">Select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="b928a-212">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="b928a-212">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b928a-213">**Konto odbiorcy:** *US-011*</span><span class="sxs-lookup"><span data-stu-id="b928a-213">**Customer account:** *US-011*</span></span>
    - <span data-ttu-id="b928a-214">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="b928a-214">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="b928a-215">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b928a-215">Select **OK**.</span></span>
1. <span data-ttu-id="b928a-216">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="b928a-216">The new sales order is opened.</span></span> <span data-ttu-id="b928a-217">Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="b928a-217">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="b928a-218">**Numer pozycji:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="b928a-218">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="b928a-219">**Ilość:** *20*</span><span class="sxs-lookup"><span data-stu-id="b928a-219">**Quantity:** *20*</span></span>

1. <span data-ttu-id="b928a-220">W polu **Potwierdzona data dostawy** na karcie **Ustawienia** na skróconej karcie **Szczegóły wiersza** należy ustawić dzisiejszą datę.</span><span class="sxs-lookup"><span data-stu-id="b928a-220">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="b928a-221">Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj drugi wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="b928a-221">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="b928a-222">**Numer pozycji:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="b928a-222">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="b928a-223">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="b928a-223">**Quantity:** *2*</span></span>

1. <span data-ttu-id="b928a-224">W polu **Potwierdzona data dostawy** na karcie **Ustawienia** na skróconej karcie **Szczegóły wiersza** należy ustawić dzisiejszą datę.</span><span class="sxs-lookup"><span data-stu-id="b928a-224">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="b928a-225">Dla każdego właśnie dodanego wiersza należy wykonać następujące kroki, aby zarezerwować zapasy:</span><span class="sxs-lookup"><span data-stu-id="b928a-225">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="b928a-226">Wybierz wiersz do zarezerwowania.</span><span class="sxs-lookup"><span data-stu-id="b928a-226">Select the line to reserve.</span></span>
    2. <span data-ttu-id="b928a-227">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="b928a-227">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="b928a-228">Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.</span><span class="sxs-lookup"><span data-stu-id="b928a-228">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="b928a-229">Zamknij stronę **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="b928a-229">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="b928a-230">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="b928a-230">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="b928a-231">Po wykonaniu zwolnienia, użytkownik otrzymuje komunikaty informacyjne, które zawierają identyfikator grupy czynności oraz identyfikator wysyłki.</span><span class="sxs-lookup"><span data-stu-id="b928a-231">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="get-work-ids-and-license-plate-numbers"></a><span data-ttu-id="b928a-232">Pobierz identyfikatory pracy i numery identyfikacyjne</span><span class="sxs-lookup"><span data-stu-id="b928a-232">Get work IDs and license plate numbers</span></span>

<span data-ttu-id="b928a-233">Powinny zostać utworzone dwa identyfikatory pracy, z których każdy ma dwa wiersze pobrania.</span><span class="sxs-lookup"><span data-stu-id="b928a-233">Two work IDs should have been created, each of which has two pick lines.</span></span> <span data-ttu-id="b928a-234">Aby znaleźć identyfikatory pracy i przypisania numerów identyfikacyjnych, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b928a-234">Follow these steps to find the work IDs and license plate assignments.</span></span>

1. <span data-ttu-id="b928a-235">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="b928a-235">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="b928a-236">W siatce **Przeglądu** wyszukaj w kolumnie **Numery zamówień** dwóch nowo utworzonych zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b928a-236">In the **Overview** grid, search the **Order number** column for the two sales orders that you just created.</span></span> <span data-ttu-id="b928a-237">Zapisz identyfikatory pracy dla każdego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b928a-237">For each sales order, make a note of the corresponding work ID.</span></span>
1. <span data-ttu-id="b928a-238">Wybierz wiersz dla każdego zamówienia sprzedaży, aby wyświetlić informacje powiązane z siatką **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="b928a-238">Select the row for each sales order to show related information in the **Lines** grid.</span></span> <span data-ttu-id="b928a-239">Umożliwia zanotowanie lokalizacji, z której będzie pobierany każdy towar.</span><span class="sxs-lookup"><span data-stu-id="b928a-239">Make a note of the location that each item will be picked from.</span></span>
1. <span data-ttu-id="b928a-240">Wybierz kolejno opcje **Zarządzanie zapasami \> Zapytania i raporty \> Dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="b928a-240">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="b928a-241">Wybierz opcję **Wymiary** w okienku akcji, aby otworzyć okno dialogowe **Wyświetlane wymiary**.</span><span class="sxs-lookup"><span data-stu-id="b928a-241">On the Action Pane, select **Dimensions** to open the **Dimension display** dialog box.</span></span>
1. <span data-ttu-id="b928a-242">Upewnij się, że pola wyboru **Numer identyfikacyjy**, **Magazyn** i **Kod towaru** są zaznaczone, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b928a-242">Make sure that the **License plate**, **Warehouse**, and **Item number** check boxes are selected, and then select **OK**.</span></span>
1. <span data-ttu-id="b928a-243">W okienku **Filtr** należy skonfigurować następujące filtry:</span><span class="sxs-lookup"><span data-stu-id="b928a-243">In the **Filter** pane, set the following filters:</span></span>

    - <span data-ttu-id="b928a-244">**Kod pozycji** — **jeden z** — *L0101* i *T100*</span><span class="sxs-lookup"><span data-stu-id="b928a-244">**Item number** – **is one of** – *L0101* and *T100*</span></span>
    - <span data-ttu-id="b928a-245">**Magazyn** — **zaczyna się od** – *61*</span><span class="sxs-lookup"><span data-stu-id="b928a-245">**Warehouse** – **begins with** – *61*</span></span>

1. <span data-ttu-id="b928a-246">Zanotuj wyświetlony **numer identyfikacyjny**.</span><span class="sxs-lookup"><span data-stu-id="b928a-246">Make a note of the **License plate** values that are shown.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="b928a-247">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="b928a-247">Example scenario</span></span>

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a><span data-ttu-id="b928a-248">Wykonywanie przepływu urządzeń przenośnych — konfiguracja potwierdzenia pracy dla produktu</span><span class="sxs-lookup"><span data-stu-id="b928a-248">Mobile device flow execution – Work confirmation setup for the product</span></span>

1. <span data-ttu-id="b928a-249">Zaloguj się do aplikacji magazynowania jako użytkownik w magazynie *61*.</span><span class="sxs-lookup"><span data-stu-id="b928a-249">Sign in to the warehouse app as a user in warehouse *61*.</span></span>
1. <span data-ttu-id="b928a-250">Przejdź do **Wychodzące \> Tworzenie pobrania w grupie**.</span><span class="sxs-lookup"><span data-stu-id="b928a-250">Go to **Outbound \> Cluster pick create**.</span></span>

    <span data-ttu-id="b928a-251">Zostanie wyświetlona strona **ZADANIE: Przypisz pracę do grupy**.</span><span class="sxs-lookup"><span data-stu-id="b928a-251">The **TASK: Assign work to Cluster** page appears.</span></span>

1. <span data-ttu-id="b928a-252">Wprowadź identyfikator pracy dla zamówienia sprzedaży 1 w celu przypisania go do pozycji w grupie 1.</span><span class="sxs-lookup"><span data-stu-id="b928a-252">Enter the work ID for sales order 1 to assign it to cluster position 1.</span></span>
1. <span data-ttu-id="b928a-253">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-253">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="b928a-254">Wprowadź identyfikator pracy dla zamówienia sprzedaży 2 w celu przypisania go do pozycji w grupie 2.</span><span class="sxs-lookup"><span data-stu-id="b928a-254">Enter the work ID for sales order 2 to assign it to cluster position 2.</span></span>
1. <span data-ttu-id="b928a-255">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-255">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="b928a-256">Pojawi się strona **ZADANIE: Utwórz pobieranie dla grupy: pobierz**, które wyświetli *Pozycja L0101 2 PL*.</span><span class="sxs-lookup"><span data-stu-id="b928a-256">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item L0101 2 PL*.</span></span>

<span data-ttu-id="b928a-257">Ponieważ profil grupy ustawia liczbę stanowisk na 2, system automatycznie kieruje do pierwszego pobrania: dwie palety (PL) pozycji *L0101*.</span><span class="sxs-lookup"><span data-stu-id="b928a-257">Because the cluster profile set the number of positions to 2, the system automatically directs you to the first consolidate pick: two pallets (PL) of item *L0101*.</span></span>

<span data-ttu-id="b928a-258">W dowolnym momencie podczas wykonywania poniższych kroków można wybrać kartę **Szczegóły**, aby wyświetlić dodatkowe informacje o zadaniu, takie jak lokalizacja pobierania.</span><span class="sxs-lookup"><span data-stu-id="b928a-258">At any time during the following steps, you can select the **Details** tab to view additional information about the task, such as the picking location.</span></span>

1. <span data-ttu-id="b928a-259">Ustaw wartość w polu **POZYCJA** na *L0101*.</span><span class="sxs-lookup"><span data-stu-id="b928a-259">Set the **ITEM** field to *L0101*.</span></span> <span data-ttu-id="b928a-260">Powoduje to potwierdzenie kodu towaru wymaganego dla tego elementu menu (wcześniej skonfigurowano przez wybranie **Ustawienia potwierdzenie pracy** z poziomu strony **Element menu urządzenia przenośnego** po utworzeniu tego elementu menu).</span><span class="sxs-lookup"><span data-stu-id="b928a-260">This confirms the item number, which is required for this menu item (you configured this earlier by selecting **Work confirmation setup**  from the **Mobile device menu item** page when you created this menu item).</span></span>
1. <span data-ttu-id="b928a-261">Umożliwia wprowadzenie numeru identyfikacyjnego, który jest skojarzony z towarem w lokalizacji pobierania.</span><span class="sxs-lookup"><span data-stu-id="b928a-261">Enter the license plate number that is associated with the item in the location that is being picked.</span></span> <span data-ttu-id="b928a-262">Zostaną pobrane dwie palety.</span><span class="sxs-lookup"><span data-stu-id="b928a-262">You will pick two pallets.</span></span>
1. <span data-ttu-id="b928a-263">W polu **LP** ustaw wartość *LP\_PICK\_01*.</span><span class="sxs-lookup"><span data-stu-id="b928a-263">Set the **LP** field to *LP\_PICK\_01*.</span></span>
1. <span data-ttu-id="b928a-264">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-264">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="b928a-265">Zostanie wyświetlona strona **ZADANIE:Sortuj: Tworzenie pobierania dla grupy**.</span><span class="sxs-lookup"><span data-stu-id="b928a-265">The **TASK: Sort: Cluster Pick Create** page appears.</span></span> <span data-ttu-id="b928a-266">W tym miejscu zostaną posortowane dwie pobrane palety w wybrane pozycje pobrania.</span><span class="sxs-lookup"><span data-stu-id="b928a-266">Here, you will sort the two picked pallets into a pick position.</span></span> <span data-ttu-id="b928a-267">To stanowisko może być pojemnikiem lub kontenerem używanym do oddzielenia pobranego przedmiotu według zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b928a-267">This position might be a tote or container that is used to separate the picked inventory by sales order.</span></span>

1. <span data-ttu-id="b928a-268">Wyświetl szczegóły dotyczące towaru (*L0101*) i ilości (*20* ea), które zostaną posortowane w ramach stanowiska 1 (dla zamówienia sprzedaży 1).</span><span class="sxs-lookup"><span data-stu-id="b928a-268">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="b928a-269">W polu **NAZWA STAN** wybierz *1*.</span><span class="sxs-lookup"><span data-stu-id="b928a-269">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="b928a-270">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-270">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="b928a-271">Wyświetl szczegóły dotyczące towaru (*L0101*) i ilości (*20* ea), które zostaną posortowane w ramach stanowiska 2 (dla zamówienia sprzedaży 2).</span><span class="sxs-lookup"><span data-stu-id="b928a-271">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="b928a-272">W polu **NAZWA STAN** wybierz *2*.</span><span class="sxs-lookup"><span data-stu-id="b928a-272">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="b928a-273">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-273">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="b928a-274">Pojawi się strona **ZADANIE: Utwórz pobieranie dla grupy: pobierz**, które wyświetli *Pozycja T0100 7 ea*.</span><span class="sxs-lookup"><span data-stu-id="b928a-274">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item T0100 7 ea*.</span></span>

<span data-ttu-id="b928a-275">W tym scenariuszu pozycja 1 nie akceptuje pełnej ilości towarów, które muszą zostać pobrane, aby zrealizować zamówienie sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="b928a-275">In this scenario, position 1 can't accept the full quantity of items that must be picked to fulfill sales order 1.</span></span> <span data-ttu-id="b928a-276">Pozycja musi być oznaczona jako pełna.</span><span class="sxs-lookup"><span data-stu-id="b928a-276">A position must be marked as full.</span></span> <span data-ttu-id="b928a-277">W tym scenariuszu zostanie wydane częściowe pobranie drugiego towaru.</span><span class="sxs-lookup"><span data-stu-id="b928a-277">In this scenario, you will do a partial pick of the second item.</span></span> <span data-ttu-id="b928a-278">Drugi towar zostanie częściowo pobrany dla stanowiska 1, a w celu wybrania pozostałej ilości do zrealizowania zamówienia zostanie utworzona nowa praca.</span><span class="sxs-lookup"><span data-stu-id="b928a-278">The second item will be partially picked for position 1, and new work will be created to pick the remaining quantity to fulfill the order.</span></span>

1. <span data-ttu-id="b928a-279">Wybierz przycisk menu (czasami nazywany przyciskiem hamburger lub hamburgerem), a następnie wybierz opcję **Stanowisko pełne**.</span><span class="sxs-lookup"><span data-stu-id="b928a-279">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Position full**.</span></span>
1. <span data-ttu-id="b928a-280">Określ zapełnione stanowisko i wybierz opcję *1*.</span><span class="sxs-lookup"><span data-stu-id="b928a-280">Identify the position that is full, and select *1*.</span></span>
1. <span data-ttu-id="b928a-281">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-281">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="b928a-282">Wprowadź ilość pobrania, która może zostać jeszcze pobrana do pozycji 1.</span><span class="sxs-lookup"><span data-stu-id="b928a-282">Enter the pick quantity that can still be picked into position 1.</span></span> <span data-ttu-id="b928a-283">System może ustalić, który numer pozycji jest pobierany.</span><span class="sxs-lookup"><span data-stu-id="b928a-283">The system can determine which item number is being picked.</span></span>
1. <span data-ttu-id="b928a-284">Wprowadź *2*.</span><span class="sxs-lookup"><span data-stu-id="b928a-284">Enter *2*.</span></span>
1. <span data-ttu-id="b928a-285">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-285">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="b928a-286">Potwierdź numer pozycji, aby zakończyć pobieranie pozostałego towaru w stanowisku 2.</span><span class="sxs-lookup"><span data-stu-id="b928a-286">Confirm the item number to complete the pick of the remaining item into position 2.</span></span>
1. <span data-ttu-id="b928a-287">Ustaw wartość w polu **POZYCJA** na *T0100*.</span><span class="sxs-lookup"><span data-stu-id="b928a-287">Set the **ITEM** field to *T0100*.</span></span>
1. <span data-ttu-id="b928a-288">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-288">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="b928a-289">Wprowadź numer identyfikacyjny towaru, z którego ma zostać pobrany towar, ustawiając **pole LP** na wartość *LPREPL04*.</span><span class="sxs-lookup"><span data-stu-id="b928a-289">Enter the license plate that the item is being picked from by setting the **LP** field to *LPREPL04*.</span></span>
1. <span data-ttu-id="b928a-290">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-290">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="b928a-291">Wyświetl szczegóły dotyczące towaru (*T0100*) i ilości (*2* ea), które zostaną posortowane w ramach stanowiska 2 (dla zamówienia sprzedaży 2).</span><span class="sxs-lookup"><span data-stu-id="b928a-291">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="b928a-292">W polu **NAZWA STAN** wybierz *2*.</span><span class="sxs-lookup"><span data-stu-id="b928a-292">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="b928a-293">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-293">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="b928a-294">Wyświetl szczegóły dotyczące towaru (*T0100*) i ilości (*2* ea), które zostaną posortowane w ramach stanowiska 1 (dla zamówienia sprzedaży 1).</span><span class="sxs-lookup"><span data-stu-id="b928a-294">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="b928a-295">W polu **NAZWA STAN** wybierz *1*.</span><span class="sxs-lookup"><span data-stu-id="b928a-295">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="b928a-296">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-296">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="b928a-297">Zostanie wyświetlona strona **ZADANIE: Tworzenie pobierania dla grupy: Odłóż**.</span><span class="sxs-lookup"><span data-stu-id="b928a-297">The **TASK: Cluster Pick Create: Put** page appears.</span></span>

<span data-ttu-id="b928a-298">W tym scenariuszu pobranie klastra zostało zakończone i użytkownik jest proszony o odłożenie pobranych pozycji z pozycji 1 i 2 i umieszczenie ich w lokalizacji *STAGE01*.</span><span class="sxs-lookup"><span data-stu-id="b928a-298">In this scenario, the cluster pick has been completed, and the user is directed to put away the picked items from position 1 and position 2 into staging location *STAGE01*.</span></span>

1. <span data-ttu-id="b928a-299">Przejrzyj informacje znajdujące się na stronie.</span><span class="sxs-lookup"><span data-stu-id="b928a-299">Review the information on the page.</span></span> <span data-ttu-id="b928a-300">Wskazują one, że całkowita ilość *44* zostanie wprowadzona do lokalizacji pośredniej.</span><span class="sxs-lookup"><span data-stu-id="b928a-300">It shows that a total quantity of *44* will be put to the staging location.</span></span>
1. <span data-ttu-id="b928a-301">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="b928a-301">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="b928a-302">Zostanie wyświetlony komunikat „Pobieranie dla grupy zakończone”.</span><span class="sxs-lookup"><span data-stu-id="b928a-302">You receive a "Cluster Completed" message.</span></span>

<span data-ttu-id="b928a-303">Za pomocą elementu menu **Pobranie sprzedaży** można teraz pobrać pozostałą ilość.</span><span class="sxs-lookup"><span data-stu-id="b928a-303">You can now use the **Sales Picking** menu item to pick the remaining quantity.</span></span> <span data-ttu-id="b928a-304">Następnie można skorzystać z elementu menu **Ładowanie sprzedaży**, aby przenieść elementy z lokalizacji pośredniej do doku załadunku.</span><span class="sxs-lookup"><span data-stu-id="b928a-304">You can then use the **Sales loading** menu item to move the items from the staging location to the loading dock.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]