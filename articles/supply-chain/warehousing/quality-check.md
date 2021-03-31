---
title: Kontrola jakości
description: Ten temat zawiera informacje dotyczące funkcji Kontrola jakości. Ta funkcja pozwala pracownikom magazynowym na szybkie sprawdzenie jakości podczas przyjmowania towarów do obszaru doków przychodzących.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 31afcfcb9d8dbb91f4ea4e3e7a7282c2a87328d4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228472"
---
# <a name="quality-check"></a><span data-ttu-id="8a620-104">Kontrola jakości</span><span class="sxs-lookup"><span data-stu-id="8a620-104">Quality check</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a620-105">Funkcja *Kontroli jakości* pozwala pracownikom magazynowym na szybkie sprawdzenie jakości podczas przyjmowania towarów do obszaru doków przychodzących.</span><span class="sxs-lookup"><span data-stu-id="8a620-105">The *Quality check* feature lets warehouse workers do quick spot checks for quality while they receive items to the inbound dock area.</span></span> <span data-ttu-id="8a620-106">Te kontrole na miejscu są korzystne w przypadku, gdy pracownicy badają pakowanie lub inne łatwo rozpoznawalne części towaru.</span><span class="sxs-lookup"><span data-stu-id="8a620-106">These spot checks are beneficial when workers inspect packaging or other easily recognizable parts of an item.</span></span> <span data-ttu-id="8a620-107">Ta funkcja prowadzi pracowników do szybkiego spojrzenia, aby sprawdzić, czy coś jest ewidentnie wadliwe lub uszkodzone, zanim zapiszą zapasy w miejscu składowania.</span><span class="sxs-lookup"><span data-stu-id="8a620-107">The feature guides workers to take a quick look to see whether anything is obviously faulty or damaged before they stock the inventory in its putaway location.</span></span>

<span data-ttu-id="8a620-108">Ta funkcja jest alternatywą dla standardowego procesu kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-108">This feature is an alternative to the standard quality check process.</span></span> <span data-ttu-id="8a620-109">Zapewnia większą elastyczność i szybsze przetwarzanie.</span><span class="sxs-lookup"><span data-stu-id="8a620-109">It offers more flexibility and faster processing.</span></span>

<span data-ttu-id="8a620-110">Podczas korzystania z tej funkcji przybycie i kontrola jakości odbywają się w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8a620-110">When you use this feature, the arrival and quality check occur in the following way:</span></span>

1. <span data-ttu-id="8a620-111">Kiedy nadejdzie przesyłka, magazynier rejestruje przybycie.</span><span class="sxs-lookup"><span data-stu-id="8a620-111">When a shipment arrives, a warehouse worker registers the arrival.</span></span> <span data-ttu-id="8a620-112">Pracownik również skanuje numer identyfikacyjny w celu zarejestrowania lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="8a620-112">The worker also scans a license plate to register the location.</span></span>
1. <span data-ttu-id="8a620-113">Pracownik przeprowadza szybką kontrolę jakości i zapisuje wynik (pozytywny lub negatywny) dla danego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="8a620-113">The worker does a quick quality check and records the result (pass or fail) for that license plate.</span></span>
1. <span data-ttu-id="8a620-114">Następuje jedna z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="8a620-114">One of the following actions occurs:</span></span>

    - <span data-ttu-id="8a620-115">Jeśli kontrola jakości jest przekazywana, numer identyfikacyjny jest akceptowany i kierowany do lokalizacji odbiorczej w zwykły sposób.</span><span class="sxs-lookup"><span data-stu-id="8a620-115">If the quality check is passed, the license plate is accepted and guided to a receiving location, as usual.</span></span>
    - <span data-ttu-id="8a620-116">Jeśli kontrola jakości nie powiodło się, oznacza to, że numer identyfikacyjny jest odrzucony, a istniejące prace odkładane dla niej są przekierowywane do innej lokalizacji w celu dalszej kontroli.</span><span class="sxs-lookup"><span data-stu-id="8a620-116">If the quality check is failed, the license plate is rejected, and existing putaway work for it is redirected to an alternate location for further inspection.</span></span> <span data-ttu-id="8a620-117">Zostanie utworzone nowe zlecenie kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-117">A new quality order is created.</span></span> <span data-ttu-id="8a620-118">Aby wyświetlić zlecenie kontroli jakości utworzone na podstawie niepowodzenia kontroli jakości, należy przejść do **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="8a620-118">To view the quality order that is created from the failed quality check, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="8a620-119">Ten proces można również skonfigurować w taki sposób, aby wszystkie zeskanowane numey identyfikacyjne zostały natychmiast skierowane do lokalizacji kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-119">This process can also be set up so that all scanned license plates are immediately diverted to the quality check location.</span></span>

## <a name="turn-on-the-quality-check-feature"></a><span data-ttu-id="8a620-120">Włącz funkcję kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="8a620-120">Turn on the Quality check feature</span></span>

<span data-ttu-id="8a620-121">Aby móc używać funkcji *Kontroli jakości*, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="8a620-121">Before you can use the *Quality check* feature, it must be turned on in your system.</span></span> <span data-ttu-id="8a620-122">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="8a620-122">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="8a620-123">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="8a620-123">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="8a620-124">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="8a620-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="8a620-125">**Nazwa funkcji:** *Kontrola jakości*</span><span class="sxs-lookup"><span data-stu-id="8a620-125">**Feature name:** *Quality check*</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="8a620-126">Skonfiguruj funkcję dla tego scenariusza przykładowego</span><span class="sxs-lookup"><span data-stu-id="8a620-126">Set up the feature for the example scenario</span></span>

<span data-ttu-id="8a620-127">Ta sekcja zawiera wskazówki oraz przykład, w jaki sposób należy skonfigurować funkcję *Kontrola jakości* i przygotować przykładowe dane do scenariusza przykładowego, który opisano w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="8a620-127">This section provides guidelines and an example that shows how to set up the *Quality check* feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="8a620-128">Udostępnianie danych pokazowych</span><span class="sxs-lookup"><span data-stu-id="8a620-128">Make sample data available</span></span>

<span data-ttu-id="8a620-129">Aby pracować z tymi [przykładowymi scenariuszami](#example-scenario) przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8a620-129">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="8a620-130">Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="8a620-130">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="quality-check-template"></a><a name="quality-template"></a><span data-ttu-id="8a620-131">Szablon kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="8a620-131">Quality check template</span></span>

<span data-ttu-id="8a620-132">Szablon kontroli jakości określa reguły przeprowadzania szybkich kontroli jakości w momencie przyjmowania.</span><span class="sxs-lookup"><span data-stu-id="8a620-132">The quality check template defines the rules for doing quick spot checks for quality at the time of receiving.</span></span>

1. <span data-ttu-id="8a620-133">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablon kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="8a620-133">Go to **Warehouse management \> Setup \> Work \> Quality check template**.</span></span>
1. <span data-ttu-id="8a620-134">Kliknij przycisk **Nowe**, aby dodać szablon do siatki.</span><span class="sxs-lookup"><span data-stu-id="8a620-134">Select **New** to add a template to the grid.</span></span>
1. <span data-ttu-id="8a620-135">Ustaw następujące wartości, aby zdefiniować nowy szablon:</span><span class="sxs-lookup"><span data-stu-id="8a620-135">Set the following values to define the new template:</span></span>

    - <span data-ttu-id="8a620-136">**Nazwa szablonu kontrolu jakości:** *Kontrola doku*</span><span class="sxs-lookup"><span data-stu-id="8a620-136">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="8a620-137">Umożliwia wprowadzenie nazwy identyfikującej zasady stosowane do tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="8a620-137">Enter a name that identifies the policies applied for this template.</span></span>

    - <span data-ttu-id="8a620-138">**Zasady akceptacji:** *Monituj użytkownika*</span><span class="sxs-lookup"><span data-stu-id="8a620-138">**Acceptance policy:** *Prompt user*</span></span>

        <span data-ttu-id="8a620-139">Umożliwia określenie, czy użytkownicy powinni być monitowani o zaakceptowanie lub odrzucenie jakości zapasów podczas przetwarzania pracy lub określać, czy jakość ma być automatycznie odrzucona.</span><span class="sxs-lookup"><span data-stu-id="8a620-139">Specify whether users should be prompted to accept or reject the quality of the inventory while they process the work, or whether the quality should automatically be rejected.</span></span> <span data-ttu-id="8a620-140">Dostępne opcje to *Automatyczne odrzucanie* i *Monituj użytkownika*.</span><span class="sxs-lookup"><span data-stu-id="8a620-140">The available options are *Auto reject* and *Prompt user*.</span></span>

    - <span data-ttu-id="8a620-141">**Zasady przetwarzania jakości:** *Tworzenie zlecenia kontroli jakości*</span><span class="sxs-lookup"><span data-stu-id="8a620-141">**Quality processing policy:** *Create quality order*</span></span>

        <span data-ttu-id="8a620-142">Wybierz zasadę, która ma być stosowana w przypadku odrzucenia jakości zasobów reklamowych.</span><span class="sxs-lookup"><span data-stu-id="8a620-142">Select the policy that should be used when the quality of the inventory is rejected.</span></span> <span data-ttu-id="8a620-143">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="8a620-143">The following options are available:</span></span>

        - <span data-ttu-id="8a620-144">*Utwórz tylko pracę* — Utwórz tylko pracę, aby ułatwić przenoszenie zapasów.</span><span class="sxs-lookup"><span data-stu-id="8a620-144">*Create work only* – Just create work to facilitate inventory movement.</span></span>
        - <span data-ttu-id="8a620-145">*Tworzenie zlecenia kontroli jakości* — umożliwia tworzenie zlecenia kontroli jakości w celu ułatwienia testowania jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-145">*Create quality order* – Create a quality order to facilitate quality tests.</span></span>

    - <span data-ttu-id="8a620-146">**Grupa testowa:** *Odgrodzona*</span><span class="sxs-lookup"><span data-stu-id="8a620-146">**Test group:** *Enclosure*</span></span>

        <span data-ttu-id="8a620-147">Umożliwia określenie grupy testowej, która powinna być używana w tworzonym zleceniu kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-147">Specify the test group that should be used in the quality order that is created.</span></span> <span data-ttu-id="8a620-148">Grupy testowe są konfigurowane w module **Zarządzania zapasami**.</span><span class="sxs-lookup"><span data-stu-id="8a620-148">Test groups are set up in the **Inventory management** module.</span></span>

        <span data-ttu-id="8a620-149">Pozostaw opcję **Testy destrukcyjne** wyłączoną dla grupy testowej</span><span class="sxs-lookup"><span data-stu-id="8a620-149">Leave the **Destructive text** option turned off for the test group.</span></span> <span data-ttu-id="8a620-150">Ta opcja określa, czy próbka zostanie zniszczona w ramach testów w grupie testowej.</span><span class="sxs-lookup"><span data-stu-id="8a620-150">This option defines whether the sample will be destroyed as part of the tests in the test group.</span></span> <span data-ttu-id="8a620-151">Jeśli używany jest test niszczący, system generuje transakcję magazynową po utworzeniu zlecenia kontroli jakości dla towaru.</span><span class="sxs-lookup"><span data-stu-id="8a620-151">If a destructive test is used, the system generates an inventory transaction when a quality order is created for an item.</span></span> <span data-ttu-id="8a620-152">Nowa transakcja magazynowa przewiduje zmniejszenie zapasu dla ilości testowej.</span><span class="sxs-lookup"><span data-stu-id="8a620-152">The new inventory transaction predicts the inventory reduction for the test quantity.</span></span> <span data-ttu-id="8a620-153">Zmniejszenie zapasów następuje, gdy zlecenie kontroli jakości jest zakończone w kroku walidacji.</span><span class="sxs-lookup"><span data-stu-id="8a620-153">The inventory reduction occurs when the quality order is completed through the validation step.</span></span> <span data-ttu-id="8a620-154">Transakcja magazynowa jest identyfikowana jako zlecenie kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-154">The inventory transaction is identified as a quality order.</span></span>

### <a name="work-class--quality-check"></a><a name="work-class"></a><span data-ttu-id="8a620-155">Klasa robocza – Kontrola jakości</span><span class="sxs-lookup"><span data-stu-id="8a620-155">Work class – Quality check</span></span>

<span data-ttu-id="8a620-156">Klas pracy są używane do kierowania i/lub ograniczania typów wierszy zlecenia, które pracownicy magazynu może przetwarzać na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="8a620-156">Work classes are used to direct and/or limit the type of work order lines that warehouse workers can process on a mobile device.</span></span>

1. <span data-ttu-id="8a620-157">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.</span><span class="sxs-lookup"><span data-stu-id="8a620-157">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="8a620-158">Wybierz pozycję **Nowy**, aby utworzyć nową klasę pracy.</span><span class="sxs-lookup"><span data-stu-id="8a620-158">Select **New** to create a work class.</span></span>
1. <span data-ttu-id="8a620-159">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-159">In the header, set the following values:</span></span>

    - <span data-ttu-id="8a620-160">**Identyfikator klasy roboczej:** *Sprawdzanie jakości kontroli*</span><span class="sxs-lookup"><span data-stu-id="8a620-160">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="8a620-161">Umożliwia wprowadzenie nazwy identyfikującej klasę pracy.</span><span class="sxs-lookup"><span data-stu-id="8a620-161">Enter a name that identifies the work class.</span></span>

    - <span data-ttu-id="8a620-162">**Opis:** *Sprawdzanie jakości kontroli*</span><span class="sxs-lookup"><span data-stu-id="8a620-162">**Description:** *QC Check*</span></span>

        <span data-ttu-id="8a620-163">Służy do wprowadzania krótkiego opisu, który wskazuje klasę pracy, której jest używana.</span><span class="sxs-lookup"><span data-stu-id="8a620-163">Enter a short description that indicates what the work class is used for.</span></span>

    - <span data-ttu-id="8a620-164">**Typ zlecenia pracy:** *Jakość w kontroli jakości*</span><span class="sxs-lookup"><span data-stu-id="8a620-164">**Work order type:** *Quality in quality check*</span></span>

        <span data-ttu-id="8a620-165">Wybierz typ zlecenia pracy utworzonego przez klasę pracy.</span><span class="sxs-lookup"><span data-stu-id="8a620-165">Select the type of work order that is created by the work class.</span></span> <span data-ttu-id="8a620-166">Podczas ustawiania działania kontroli jakości należy zawsze wybierać opcje *Jakość w kontroli jakości*.</span><span class="sxs-lookup"><span data-stu-id="8a620-166">When you set up quality control work, always select *Quality in quality check*.</span></span>

1. <span data-ttu-id="8a620-167">Na skróconej karcie **Prawidłowe typy lokalizacji odłożenia** pozostaw pole **Typ lokalizacji** puste.</span><span class="sxs-lookup"><span data-stu-id="8a620-167">On the **Valid put location types** FastTab, leave the **Location type** field blank.</span></span>

    <span data-ttu-id="8a620-168">W przypadku wybrania typu lokalizacji można ograniczyć lokalizacje, w których towary mogą być umieszczane po pobraniu.</span><span class="sxs-lookup"><span data-stu-id="8a620-168">If you select a location type, you limit the locations where items can be put after they are picked.</span></span> <span data-ttu-id="8a620-169">To pole jest używane, gdy dyrektywa lokalizacji próbuje rozpoznać lokalizację lub gdy pracownik magazynu ręcznie określa lokalizację w elemencie menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="8a620-169">This field is used when a location directive tries to resolve the location, or when a warehouse worker manually specifies the location for the mobile device menu item.</span></span>

<span data-ttu-id="8a620-170">Aby uzyskać więcej informacji o klasach pracy i sposobach ich tworzenia, należy zapoznać się z tematem [Tworzenie klasy pracy](tasks/create-work-class.md).</span><span class="sxs-lookup"><span data-stu-id="8a620-170">For more information about work classes and how to create them, see [Create a work class](tasks/create-work-class.md).</span></span>

### <a name="work-template"></a><span data-ttu-id="8a620-171">Szablon pracy</span><span class="sxs-lookup"><span data-stu-id="8a620-171">Work template</span></span>

<span data-ttu-id="8a620-172">Szablony pracy pozwalają zdefiniować operacje pracy, które muszą być wykonane w magazynie.</span><span class="sxs-lookup"><span data-stu-id="8a620-172">Work templates let you define the work operations that must be performed in the warehouse.</span></span> <span data-ttu-id="8a620-173">Zwykle operacje pracy w magazynie składają się z dwóch działań: pracownik magazynu odbiera dostępny towar w lokalizacji, a następnie odkłada odebrany towar w innej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="8a620-173">Typically, warehouse work operations consist of a pair of actions: a warehouse worker picks on-hand inventory up in one location and then puts the picked inventory down in another location.</span></span> <span data-ttu-id="8a620-174">Szablon pracy kontroli jakości określa operacje wykonywane przy wykonywaniu kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-174">A work template for quality control defines the work operations for doing quality checks.</span></span>

#### <a name="purchase-orders"></a><span data-ttu-id="8a620-175">Zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="8a620-175">Purchase orders</span></span>

1. <span data-ttu-id="8a620-176">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="8a620-176">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="8a620-177">W nagłówku w polu **Typ zlecenia pracy** zaznacz opcję *Zamówienia zakupu*.</span><span class="sxs-lookup"><span data-stu-id="8a620-177">In the header, set the **Work order type** field to *Purchase orders*.</span></span>
1. <span data-ttu-id="8a620-178">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="8a620-178">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="8a620-179">Wybierz szablon pracy, który powinien zawierać krok kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-179">Select a work template that should include a quality check step.</span></span> <span data-ttu-id="8a620-180">W sekcji **Przegląd** w polu **Szablon pracy** wybierz pozycję *Paragon zamówienia zakupu 51*.</span><span class="sxs-lookup"><span data-stu-id="8a620-180">In the **Overview** section, in the **Work template** field, select *51 PO Receipt*.</span></span>
1. <span data-ttu-id="8a620-181">W sekcji **Szczegóły szablonu pracy** zwróć uwagę, że siatka ma dwa istniejące wiersze: jeden dla *Pobrania*, a drugi do *Odłożenia*.</span><span class="sxs-lookup"><span data-stu-id="8a620-181">In the **Work template details** section, notice that the grid has two existing lines: one for *Pick* and one for *Put*.</span></span>
1. <span data-ttu-id="8a620-182">W sekcji **Szczegóły szablonu pracy** wybierz opcję **Nowy**, aby dodać wiersz kontroli jakości do siatki.</span><span class="sxs-lookup"><span data-stu-id="8a620-182">In the **Work template details** section, select **New** to add a row for quality control to the grid.</span></span> <span data-ttu-id="8a620-183">Zwróć uwagę, że pole **Numer wiersza** dla nowego wiersza jest ustawione na wartość *3*.</span><span class="sxs-lookup"><span data-stu-id="8a620-183">Notice that the **Line number** field for the new line is set to *3*.</span></span>
1. <span data-ttu-id="8a620-184">W nowym wierszu ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="8a620-184">On the new line, set the following values.</span></span> <span data-ttu-id="8a620-185">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="8a620-185">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="8a620-186">**Typ pracy:** *Kontrola jakości*</span><span class="sxs-lookup"><span data-stu-id="8a620-186">**Work type:** *Quality check*</span></span>
    - <span data-ttu-id="8a620-187">**Identyfikator klasy roboczej:** *Zakup*</span><span class="sxs-lookup"><span data-stu-id="8a620-187">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="8a620-188">**Nazwa szablonu kontrolu jakości:** *Kontrola doku*</span><span class="sxs-lookup"><span data-stu-id="8a620-188">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="8a620-189">Wybierz unikatowy identyfikator dla klasy roboczej.</span><span class="sxs-lookup"><span data-stu-id="8a620-189">Select the unique ID for the work class.</span></span> <span data-ttu-id="8a620-190">Ta wartość służy do konfigurowania elementów menu na urządzeniu przenośnym i typów pracy, które te elementy mają przetwarzać.</span><span class="sxs-lookup"><span data-stu-id="8a620-190">You use this value to configure the menu items on the mobile device and the types of work that those menu items can process.</span></span>

1. <span data-ttu-id="8a620-191">W okienku akcji wybierz opcję **Zapisz**, aby zapisać dotychczasową pracę.</span><span class="sxs-lookup"><span data-stu-id="8a620-191">On the Action Pane, select **Save** to save your work so far.</span></span>

    <span data-ttu-id="8a620-192">Otrzymujesz komunikat informacyjny o treści „Nieprawidłowe - kontrola jakości musi nastąpić bezpośrednio po pobraniu”.</span><span class="sxs-lookup"><span data-stu-id="8a620-192">You receive an informational message that states, "Invalid - Quality check must come directly after a pick."</span></span> <span data-ttu-id="8a620-193">Dlatego należy zmienić wartość **Numeru wiersza** dla dodanego właśnie wiersza.</span><span class="sxs-lookup"><span data-stu-id="8a620-193">Therefore, you must change the **Line number** value for the line that you just added.</span></span>

1. <span data-ttu-id="8a620-194">Aby zmienić wartość **Numeru wiersza** dla nowego wiersza, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8a620-194">Follow these steps to change the **Line number** value for the new line:</span></span>

    1. <span data-ttu-id="8a620-195">W sekcji **Szczegóły szablonu pracy** wybierz wiersz, w którym pole **Typ pracy** ma wartość *Kontrola jakości*.</span><span class="sxs-lookup"><span data-stu-id="8a620-195">In the **Work template details** section, select the line where the **Work type** field is set to *Quality check*.</span></span>
    2. <span data-ttu-id="8a620-196">Wybierz przycisk **Przenieś w górę** lub **Przenieś w dół**, aby przenieść wiersz *Kontroli jakości*, tak aby był po wierszu *Pobranie*.</span><span class="sxs-lookup"><span data-stu-id="8a620-196">Select the **Move up** or **Move down** button to move the *Quality check* line so that it's after the *Pick* line.</span></span>

1. <span data-ttu-id="8a620-197">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8a620-197">On the Action Pane, select **Save**.</span></span>

#### <a name="quality-in-quality-check"></a><span data-ttu-id="8a620-198">Kontrolowane aspekty jakości</span><span class="sxs-lookup"><span data-stu-id="8a620-198">Quality in quality check</span></span>

<span data-ttu-id="8a620-199">Następnie uUtwórz szablon pracy dla kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-199">Next, create a work template for the quality check.</span></span>

1. <span data-ttu-id="8a620-200">W nagłówku strony **Szablony pracy** zmień wartość pola **Typ zlecenia pracy** na *Jakość w kontroli jakości*.</span><span class="sxs-lookup"><span data-stu-id="8a620-200">In the header of the **Work templates** page, change the value of the **Work order type** field to *Quality in quality check*.</span></span>
1. <span data-ttu-id="8a620-201">W okienku akcji wybierz opcję **Nowy** w okienku akcji, aby dodać nowy wiersz do siatki w sekcji **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="8a620-201">On the Action Pane, select **New** to add a row to the grid in the **Overview** section.</span></span>
1. <span data-ttu-id="8a620-202">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-202">In the new row, set the following values:</span></span>

    - <span data-ttu-id="8a620-203">**Szablon pracy:** *51 Kontrola jakości*</span><span class="sxs-lookup"><span data-stu-id="8a620-203">**Work template:** *51 Quality Check*</span></span>

        <span data-ttu-id="8a620-204">Wprowadź nazwę szablonu.</span><span class="sxs-lookup"><span data-stu-id="8a620-204">Enter a name for the template.</span></span>

    - <span data-ttu-id="8a620-205">**Opis szablonu pracy:** *51 Kontrola jakości*</span><span class="sxs-lookup"><span data-stu-id="8a620-205">**Work template description:** *51 Quality Check*</span></span>

1. <span data-ttu-id="8a620-206">W okienku akcji wybierz opcję **Zapisz**, aby sekcja **Szczegóły szablonu pracy** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="8a620-206">On the Action Pane, select **Save** to make the **Work template details** section available.</span></span>
1. <span data-ttu-id="8a620-207">Gdy nowy szablon jest wciąż wybrany w sekcji **Przegląd**, wybierz opcję **Nowy** w sekcji **Szczegóły szablonu pracy**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="8a620-207">While the new template is still selected in the **Overview** section, select **New** in the **Work template details** section to add a row to the grid there.</span></span>
1. <span data-ttu-id="8a620-208">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-208">In the new row, set the following values:</span></span>

    - <span data-ttu-id="8a620-209">**Typ pracy:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="8a620-209">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="8a620-210">**Identyfikator klasy roboczej:** *Sprawdzanie jakości kontroli*</span><span class="sxs-lookup"><span data-stu-id="8a620-210">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="8a620-211">Wybierz nazwę [klasy pracy](#work-class), która została utworzona wcześniej dla pracy kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-211">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="8a620-212">W sekcji **Szczegóły szablonu pracy** wybierz ponownie opcję **Nowy**, aby dodać kolejny wiersz.</span><span class="sxs-lookup"><span data-stu-id="8a620-212">In the **Work template details** section, select **New** again to add another row.</span></span>
1. <span data-ttu-id="8a620-213">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-213">In the new row, set the following values:</span></span>

    - <span data-ttu-id="8a620-214">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="8a620-214">**Work type:** *Put*</span></span>
    - <span data-ttu-id="8a620-215">**Identyfikator klasy roboczej:** *Sprawdzanie jakości kontroli*</span><span class="sxs-lookup"><span data-stu-id="8a620-215">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="8a620-216">Wybierz nazwę [klasy pracy](#work-class), która została utworzona wcześniej dla pracy kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-216">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="8a620-217">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8a620-217">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="8a620-218">Aby uzyskać więcej informacji dotyczących szablonów pracy, zobacz [Kontrolowanie pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji](control-warehouse-location-directives.md)</span><span class="sxs-lookup"><span data-stu-id="8a620-218">For more information about work templates, see [Control warehouse work by using work templates and location directives](control-warehouse-location-directives.md)</span></span>

### <a name="location-directive--quality-failures"></a><span data-ttu-id="8a620-219">Dyrektywa lokalizacji — błędy jakości</span><span class="sxs-lookup"><span data-stu-id="8a620-219">Location directive – Quality failures</span></span>

<span data-ttu-id="8a620-220">Dyrektywy lokalizacji to zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego.</span><span class="sxs-lookup"><span data-stu-id="8a620-220">Location directives are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="8a620-221">Na przykład w ramach transakcji zamówienia sprzedaży, dyrektywa lokalizacji określa, gdzie towary zostaną pobrane i gdzie zostaną umieszczone pobrane zapasy.</span><span class="sxs-lookup"><span data-stu-id="8a620-221">For example, in a sales order transaction, a location directive determines where the items will be picked and where the picked items will be put.</span></span> <span data-ttu-id="8a620-222">Należy skonfigurować regułę dyrektywy lokalizacji, aby określić, jak będą obsługiwane niepowodzenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-222">You must configure a location directive rule to define how failed quality checks will be handled.</span></span>

1. <span data-ttu-id="8a620-223">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="8a620-223">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="8a620-224">W lewym okienku skonfiguruj pole **Typ zlecenia produkcyjnego**, aby *Zamówienia zakupu* działały z dyrektywami lokalizacji tego typu.</span><span class="sxs-lookup"><span data-stu-id="8a620-224">In the left pane, set the **Work order type** field to *Purchase orders* to work with location directives of that type.</span></span>
1. <span data-ttu-id="8a620-225">W okienku akcji wybierz opcję **Nowy**, aby utworzyć dyrektywę lokalizacji do kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-225">On the Action Pane, select **New** to create a location directive for quality checks.</span></span>
1. <span data-ttu-id="8a620-226">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-226">In the header, set the following values:</span></span>

    - <span data-ttu-id="8a620-227">**Numer sekwencyjny:** Zaakceptuj wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="8a620-227">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="8a620-228">**Nazwa:** *51 do jakości*</span><span class="sxs-lookup"><span data-stu-id="8a620-228">**Name:** *51 To Quality*</span></span>

1. <span data-ttu-id="8a620-229">Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="8a620-229">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="8a620-230">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="8a620-230">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="8a620-231">**Typ pracy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="8a620-231">**Work type:** *Put*</span></span>
    - <span data-ttu-id="8a620-232">**Oddział:** *5*</span><span class="sxs-lookup"><span data-stu-id="8a620-232">**Site:** *5*</span></span>
    - <span data-ttu-id="8a620-233">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="8a620-233">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="8a620-234">W okienku akcji wybierz opcję **Zapisz**, aby zapisać dyrektywę i udostępnić skróconą kartę **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="8a620-234">On the Action Pane select **Save** to save your directive and make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="8a620-235">Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="8a620-235">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="8a620-236">W nowym wierszu ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="8a620-236">On the new line, set the following values.</span></span> <span data-ttu-id="8a620-237">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="8a620-237">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="8a620-238">**Od ilości:** *1*</span><span class="sxs-lookup"><span data-stu-id="8a620-238">**From quantity:** *1*</span></span>
    - <span data-ttu-id="8a620-239">**Do ilości:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="8a620-239">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="8a620-240">W okienku akcji wybierz opcję **Zapisz**, aby zapisać nowy wiersz i udostępnić na skróconą kartę **Akcje dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="8a620-240">On the Action Pane, select **Save** to save the new line and make the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="8a620-241">Gdy nowy wiersz jest wciąż wybrany na skróconej karcie **Wiersze**, wybierz opcję **Nowy** na skróconej karcie **Akcje dyrektywy lokalizacji**, aby dodać wiersz do siatki, tak aby można było skonfigurować akcję dla wiersza.</span><span class="sxs-lookup"><span data-stu-id="8a620-241">While the new line is still selected on the **Lines** FastTab, select **New** on the **Location directive actions** FastTab to add a row to the grid there, so that you can set up an action for the line.</span></span>
1. <span data-ttu-id="8a620-242">W nowym wierszu należy określić wartość w polu **Nazwa** na *Jakość*.</span><span class="sxs-lookup"><span data-stu-id="8a620-242">In the new row, set the **Name** field to *Quality*.</span></span> <span data-ttu-id="8a620-243">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="8a620-243">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="8a620-244">W okienku akcji wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę** na skróconej karcie **Dyrektywy akcji lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="8a620-244">On the Action Pane, select **Save** to make the **Edit query** button on the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="8a620-245">Mimo że dodany wiersz jest wciąż zaznaczony na skróconej karcie **Akcje dyrektywy lokalizacji**, wybierz opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe, w którym można edytować kwerendę dotyczącą danej akcji.</span><span class="sxs-lookup"><span data-stu-id="8a620-245">While the line that you just added is still selected on the **Location directive actions** FastTab, select **Edit query** to open a dialog box where you can edit the query for the action.</span></span>
1. <span data-ttu-id="8a620-246">Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do kwerendy.</span><span class="sxs-lookup"><span data-stu-id="8a620-246">On the **Range** tab, select **Add** to add a row to the query.</span></span>
1. <span data-ttu-id="8a620-247">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-247">In the new row, set the following values:</span></span>

    - <span data-ttu-id="8a620-248">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="8a620-248">**Table:** *Locations*</span></span>
    - <span data-ttu-id="8a620-249">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="8a620-249">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="8a620-250">**Pole:** *Lokalizacja*</span><span class="sxs-lookup"><span data-stu-id="8a620-250">**Field:** *Location*</span></span>
    - <span data-ttu-id="8a620-251">**Kryteria QMS:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="8a620-251">**Criteria:** *QMS*</span></span>

    <span data-ttu-id="8a620-252">Lokalizacja *QMS* jest lokalizacją magazynu dla jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-252">The *QMS* location is a warehouse location for quality.</span></span>

1. <span data-ttu-id="8a620-253">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="8a620-253">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="8a620-254">Musisz teraz zmienić kolejność dyrektyw lokalizacji zamówienia zakupu dla magazynu *51*.</span><span class="sxs-lookup"><span data-stu-id="8a620-254">You must now change the sequence of purchase order location directives for warehouse *51*.</span></span> <span data-ttu-id="8a620-255">Zapisz nową dyrektywę lokalizacji *51 do jakości*, odśwież stronę i wybierz dyrektywę lokalizacji z listy.</span><span class="sxs-lookup"><span data-stu-id="8a620-255">Save the new *51 To Quality* location directive, refresh the page, and select the location directive in the list.</span></span> <span data-ttu-id="8a620-256">Następnie użyj przycisków **Przenieś w górę** i **Przenieś w dół** w okienku akcji, aby umieścić dyrektywę lokalizacji dla magazynu *51* w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="8a620-256">Then use the **Move up** and **Move down** buttons on the Action Pane to put the location directive for warehouse *51* in the following order.</span></span> <span data-ttu-id="8a620-257">(Przed wybraniem opcji **Przenieś w górę** lub **Przenieś w dół**, na liście należy wybrać lokalizację dyrektywy.)</span><span class="sxs-lookup"><span data-stu-id="8a620-257">(Before you select **Move up** or **Move down**, you must select a location directive in the list.)</span></span>

    1. <span data-ttu-id="8a620-258">51 do jakości</span><span class="sxs-lookup"><span data-stu-id="8a620-258">51 To Quality</span></span>
    2. <span data-ttu-id="8a620-259">51 bezpośrednie zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="8a620-259">51 PO Direct</span></span>
    3. <span data-ttu-id="8a620-260">51 QMS</span><span class="sxs-lookup"><span data-stu-id="8a620-260">51 QMS</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="8a620-261">Elementy menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="8a620-261">Mobile device menu items</span></span>

<span data-ttu-id="8a620-262">Skonfiguruj element menu, aby urządzenia przenośne mogły wykonywać funkcję **Kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="8a620-262">Configure a menu item so that mobile devices can perform the **Quality Check** function.</span></span>

#### <a name="purchase-putaway"></a><span data-ttu-id="8a620-263">Odłożenie zakupu</span><span class="sxs-lookup"><span data-stu-id="8a620-263">Purchase putaway</span></span>

1. <span data-ttu-id="8a620-264">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="8a620-264">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="8a620-265">Na liście wybierz element menu **Odłożenie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="8a620-265">In the list, select the **Purchase put-away** menu item.</span></span>
1. <span data-ttu-id="8a620-266">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="8a620-266">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="8a620-267">W sekcji **Klasy robocze** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="8a620-267">In the **Work classes** section, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="8a620-268">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-268">In the new row, set the following values:</span></span>

    - <span data-ttu-id="8a620-269">**Identyfikator klasy roboczej:** *Sprawdzanie jakości kontroli*</span><span class="sxs-lookup"><span data-stu-id="8a620-269">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="8a620-270">Wpisz nazwę [klasy pracy](#work-class), która została utworzona wcześniej dla pracy kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-270">Enter the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

    - <span data-ttu-id="8a620-271">**Typ zlecenia pracy:** *Jakość w kontroli jakości*</span><span class="sxs-lookup"><span data-stu-id="8a620-271">**Work order type:** *Quality in quality check*</span></span>

1. <span data-ttu-id="8a620-272">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8a620-272">On the Action Pane, select **Save**.</span></span>

#### <a name="purchase-order-line-receiving"></a><span data-ttu-id="8a620-273">Przyjęcie wiersza zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="8a620-273">Purchase order line receiving</span></span>

1. <span data-ttu-id="8a620-274">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="8a620-274">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="8a620-275">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="8a620-275">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8a620-276">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-276">In the header, set the following values:</span></span>

    - <span data-ttu-id="8a620-277">**Nazwa elementu menu:** *Wiersz zamówienia zakupu – przyjęcie*</span><span class="sxs-lookup"><span data-stu-id="8a620-277">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="8a620-278">**Nazwa:** *Wiersz zamówienia zakupu – przyjęcie*</span><span class="sxs-lookup"><span data-stu-id="8a620-278">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="8a620-279">**Tryb:** *Praca*</span><span class="sxs-lookup"><span data-stu-id="8a620-279">**Mode:** *Work*</span></span>
    - <span data-ttu-id="8a620-280">**Używanie istniejącej pracy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="8a620-280">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="8a620-281">Na skróconej karcie **Ogólne** ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="8a620-281">On the **General** FastTab, set the following values.</span></span> <span data-ttu-id="8a620-282">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="8a620-282">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="8a620-283">**Proces tworzenia pracy:** *Przyjęcie i umieszczenie wierszy zamówienia zakupu*</span><span class="sxs-lookup"><span data-stu-id="8a620-283">**Work creation process:** *Purchase order line receiving and put away*</span></span>
    - <span data-ttu-id="8a620-284">**Generuj numer identyfikacyjny:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="8a620-284">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="8a620-285">**Szablon pracy:** *51 przyjęcie zamówienia zakupu*</span><span class="sxs-lookup"><span data-stu-id="8a620-285">**Work template:** *51 PO Receipt*</span></span>

1. <span data-ttu-id="8a620-286">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8a620-286">On the Action Pane, select **Save**.</span></span>

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="8a620-287">Dodawanie element menu do menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="8a620-287">Add the menu item to a mobile device menu</span></span>

1. <span data-ttu-id="8a620-288">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="8a620-288">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="8a620-289">W lewym okienku wybierz menu **Przychodzące**.</span><span class="sxs-lookup"><span data-stu-id="8a620-289">In the left pane, select the **Inbound** menu.</span></span>
1. <span data-ttu-id="8a620-290">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="8a620-290">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="8a620-291">W kolumnie **Dostępne menu i elementy menu** wybierz nowy element menu **Wiersz zamówienia zakupu – przyjęcie**.</span><span class="sxs-lookup"><span data-stu-id="8a620-291">In the **Available menus and menu items** column, select the new **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="8a620-292">Wybierz strzałkę w prawo, aby przenieść **Wiersz zamówienia zakupu – przyjęcie** do kolumny **Struktura menu**.</span><span class="sxs-lookup"><span data-stu-id="8a620-292">Select the right arrow button to move **PO line receiving** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="8a620-293">W kolumnie **Struktura menu** wybierz opcję **Wiersz zamówienia zakupu – przyjęcie**, a następnie wybierz przycisk strzałka w górę lub strzałka w dół, aby przenieść element menu do żądanej pozycji w menu urządzenie przenośne.</span><span class="sxs-lookup"><span data-stu-id="8a620-293">In the **Menu structure** column, select **PO line receiving**, and then select the up arrow or down arrow button to move the menu item to the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="8a620-294">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8a620-294">On the Action Pane, select **Save**.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="8a620-295">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="8a620-295">Example scenario</span></span>

<span data-ttu-id="8a620-296">Po wykonaniu wszystkich poprzednio opisanych przykładowych danych i ich skonfigurowania można korzystać z tego scenariusza, aby wypróbować funkcję *Kontroli jakości*.</span><span class="sxs-lookup"><span data-stu-id="8a620-296">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Quality check* feature.</span></span> <span data-ttu-id="8a620-297">Wartości przedstawione w tym scenariuszu zakładają, że pracujesz ze standardowymi danymi demonstracyjnymi, które zostały wybrane firmę **USMF**, oraz że zostały przygotowane przykładowe rekordy opisane wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="8a620-297">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="8a620-298">Ten scenariusz służy także jako przykład, który pokazuje, w jaki sposób funkcja może być używana w ustawieniu produkcji.</span><span class="sxs-lookup"><span data-stu-id="8a620-298">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="8a620-299">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="8a620-299">Create a purchase order</span></span>

1. <span data-ttu-id="8a620-300">Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="8a620-300">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="8a620-301">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="8a620-301">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8a620-302">W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-302">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="8a620-303">**Konto dostawcy:** *104*</span><span class="sxs-lookup"><span data-stu-id="8a620-303">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="8a620-304">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="8a620-304">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="8a620-305">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i otworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="8a620-305">Select **OK** to close the dialog box and open the new purchase order.</span></span>
1. <span data-ttu-id="8a620-306">Na skróconej karcie **Wiersze zamówienia sprzedaży** siatka zawiera nowy, pusty wiersz.</span><span class="sxs-lookup"><span data-stu-id="8a620-306">On the **Purchase order lines** FastTab, the grid contains a new, blank line.</span></span> <span data-ttu-id="8a620-307">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8a620-307">On this line, set the following values:</span></span>

    - <span data-ttu-id="8a620-308">**Numer pozycji:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="8a620-308">**Item number:** *M9203*</span></span>
    - <span data-ttu-id="8a620-309">**Ilość:** *3*</span><span class="sxs-lookup"><span data-stu-id="8a620-309">**Quantity:** *3*</span></span>
    - <span data-ttu-id="8a620-310">**Jednostka:** *PL*</span><span class="sxs-lookup"><span data-stu-id="8a620-310">**Unit:** *PL*</span></span>

1. <span data-ttu-id="8a620-311">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8a620-311">On the Action Pane, select **Save**.</span></span>

### <a name="process-quality-check-receiving"></a><span data-ttu-id="8a620-312">Odbiór kontroli jakości procesu</span><span class="sxs-lookup"><span data-stu-id="8a620-312">Process quality check receiving</span></span>

<span data-ttu-id="8a620-313">Po utworzeniu zamówienia zakupu można go odebrać za pomocą elementu menu **Wiersz zamówienia zakupu – przyjęcie** oraz funkcji *Kontroli jakości*.</span><span class="sxs-lookup"><span data-stu-id="8a620-313">After the purchase order has been created, it can be received by using the **PO line receiving** menu item and the functionality of the *Quality check* feature.</span></span>

#### <a name="receive-pallet-1"></a><span data-ttu-id="8a620-314">Odbiór palety 1</span><span class="sxs-lookup"><span data-stu-id="8a620-314">Receive pallet 1</span></span>

1. <span data-ttu-id="8a620-315">Zaloguj się do aplikacji magazynowania jako użytkownik dla magazynu *51*.</span><span class="sxs-lookup"><span data-stu-id="8a620-315">Sign in to the warehouse app as a user for warehouse *51*.</span></span> <span data-ttu-id="8a620-316">(Wprowadź *51* jako identyfikator użytkownika i *1* jako hasło.)</span><span class="sxs-lookup"><span data-stu-id="8a620-316">(Enter *51* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="8a620-317">Przejdź do **Przychodzące \> Wiersz zamówienia zakupu – przyjęcie**.</span><span class="sxs-lookup"><span data-stu-id="8a620-317">Go to **Inbound \> PO line receiving**.</span></span>
1. <span data-ttu-id="8a620-318">W polu **PONUM** wprowadź numer zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="8a620-318">In the **PONUM** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="8a620-319">Potwierdź numer zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="8a620-319">Confirm the purchase order number.</span></span>
1. <span data-ttu-id="8a620-320">W polu **LINENUM** wprowadź numer otrzymywanego wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="8a620-320">In the **LINENUM** field, enter the number of the purchase order line that is being received.</span></span> <span data-ttu-id="8a620-321">Ponieważ zamówienie ma tylko jedną linię w tym scenariuszu, wpisz *1* w polu **LINENUM** dla każdego kroku odbioru.</span><span class="sxs-lookup"><span data-stu-id="8a620-321">Because the order has only one line in this scenario, you will enter *1* in the **LINENUM** field for each receiving step.</span></span>
1. <span data-ttu-id="8a620-322">Potwierdź numer wiersza.</span><span class="sxs-lookup"><span data-stu-id="8a620-322">Confirm the line number.</span></span>
1. <span data-ttu-id="8a620-323">W polu **Ilość** wprowadź ilość do odbioru.</span><span class="sxs-lookup"><span data-stu-id="8a620-323">In the **QTY** field, enter the quantity to receive.</span></span> <span data-ttu-id="8a620-324">Ponieważ zamówienie zakupu jest przeznaczone dla trzech palet (*PL*) w tym scenariuszu, a istnieją trzy czynności, należy wprowadzić wartość *1* w polu **Ilość** dla każdego kroku przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="8a620-324">Because the purchase order is for three pallets (*PL*) in this scenario, and there are three receiving steps, you will enter *1* in the **QTY** field for each receiving step.</span></span>
1. <span data-ttu-id="8a620-325">Potwierdź ilość.</span><span class="sxs-lookup"><span data-stu-id="8a620-325">Confirm the quantity.</span></span>

    <span data-ttu-id="8a620-326">Strona **Kontrola jakości**, która zostanie wyświetlona, nie zawiera pól wpisów.</span><span class="sxs-lookup"><span data-stu-id="8a620-326">The **Quality check** page that appears has no entry fields.</span></span> <span data-ttu-id="8a620-327">Ma tylko przycisk potwierdzenia (znacznik wyboru) u dołu i przycisk Menu (**≡**) u góry.</span><span class="sxs-lookup"><span data-stu-id="8a620-327">It has only the confirmation (check mark) button at the bottom and the Menu button (**≡**) at the top.</span></span> <span data-ttu-id="8a620-328">(Przycisk Menu jest czasami nazywany przyciskiem hamburgera lub hamburgerem). Aby przyspieszyć proces kontroli jakości, gdy paleta przejdzie kontrolę jakości, użytkownik po prostu potwierdza stronę **Kontrolę jakości**.</span><span class="sxs-lookup"><span data-stu-id="8a620-328">(The Menu button is sometimes referred to as the hamburger or the hamburger button.) To expedite the quality check process, when the pallet passes the quality check, the user just confirms the **Quality check** page.</span></span>

    <span data-ttu-id="8a620-329">![Strona kontroli jakości](media/quality-check.png "Strona kontroli jakości")</span><span class="sxs-lookup"><span data-stu-id="8a620-329">![Quality check page](media/quality-check.png "Quality check page")</span></span>

1. <span data-ttu-id="8a620-330">Wybierz przycisk potwierdzenia, aby przejść kontrolę jakości dla palety 1 z wiersza 1.</span><span class="sxs-lookup"><span data-stu-id="8a620-330">Select the confirmation button to pass the quality check for pallet 1 from line 1.</span></span>

    <span data-ttu-id="8a620-331">Wyświetlona strona **Zamówienia zakupu: Odłóż** zawiera szczegóły dotyczące pracy odłożenia:</span><span class="sxs-lookup"><span data-stu-id="8a620-331">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="8a620-332">**Lokalizacja:** system ustalił lokalizację</span><span class="sxs-lookup"><span data-stu-id="8a620-332">**LOC:** The system determined location</span></span>

        <span data-ttu-id="8a620-333">Ta lokalizacja jest wyznaczonym miejscem odłożenia na potrzeby przyjęcia zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="8a620-333">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="8a620-334">**Numer identyfikacyjny:** wygenerowany przez system identyfikator numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="8a620-334">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="8a620-335">**Pozycja:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="8a620-335">**Item:** *M9203*</span></span>
    - <span data-ttu-id="8a620-336">**Ilość:** *1 PL: 100 każdy*</span><span class="sxs-lookup"><span data-stu-id="8a620-336">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="8a620-337">Pokazany jest również opis pozycji.</span><span class="sxs-lookup"><span data-stu-id="8a620-337">The item description is also shown.</span></span>

1. <span data-ttu-id="8a620-338">Potwierdź pracę odłożenia.</span><span class="sxs-lookup"><span data-stu-id="8a620-338">Confirm the putaway work.</span></span>

    <span data-ttu-id="8a620-339">Na stronie **Zadania** dla przyjęcia wiersza zamówienia zakupu zostanie wyświetlony komunikat „praca wykonana”.</span><span class="sxs-lookup"><span data-stu-id="8a620-339">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="8a620-340">Pole **LINENUM** jest dostępne w taki sposób, aby można było rozpocząć otrzymywanie następnej palety.</span><span class="sxs-lookup"><span data-stu-id="8a620-340">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

#### <a name="receive-pallet-2"></a><span data-ttu-id="8a620-341">Odbiór palety 2</span><span class="sxs-lookup"><span data-stu-id="8a620-341">Receive pallet 2</span></span>

<span data-ttu-id="8a620-342">W tym scenariuszu paleta 2 zostanie odrzucona.</span><span class="sxs-lookup"><span data-stu-id="8a620-342">For this scenario, pallet 2 will be rejected.</span></span>

1. <span data-ttu-id="8a620-343">W polu **LINENUM** wprowadź wartość *1* i potwierdź numer wiersza.</span><span class="sxs-lookup"><span data-stu-id="8a620-343">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="8a620-344">Pole **Ilość** jest teraz dostępne.</span><span class="sxs-lookup"><span data-stu-id="8a620-344">The **QTY** field is now available.</span></span> <span data-ttu-id="8a620-345">Wprowadź wartość *1* i potwierdź ilość.</span><span class="sxs-lookup"><span data-stu-id="8a620-345">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="8a620-346">Zostanie wyświetlona strona **Kontrola jakości**.</span><span class="sxs-lookup"><span data-stu-id="8a620-346">The **Quality check** page appears.</span></span> <span data-ttu-id="8a620-347">W przypadku tego przyjęcia paleta zostanie odrzucona w celu uzyskania jakości i zostanie umieszczona w lokalizacji jakości *QMS*.</span><span class="sxs-lookup"><span data-stu-id="8a620-347">For this receipt, the pallet will be rejected for quality, and it will be put into the *QMS* quality location.</span></span>

1. <span data-ttu-id="8a620-348">Wybierz przycisk menu (**≡**) u góry strony, a następnie w menu wybierz opcję **Odrzuć**.</span><span class="sxs-lookup"><span data-stu-id="8a620-348">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Reject**.</span></span>
1. <span data-ttu-id="8a620-349">Na wyświetlonej stronie **Zadanie** wprowadź **QMS** jako lokalizację *Odłożenia*, aby wysłać paletę do dalszej inspekcji.</span><span class="sxs-lookup"><span data-stu-id="8a620-349">On the **Task** page that appears, enter **QMS** as the *Put* location to send the pallet to for further inspection.</span></span>

    <span data-ttu-id="8a620-350">Wyświetlona strona **Jakość w kontroli jakości: Odłóż** zawiera szczegóły dotyczące pracy odłożenia:</span><span class="sxs-lookup"><span data-stu-id="8a620-350">The **Quality in quality check: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="8a620-351">**Lokalizacja:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="8a620-351">**LOC:** *QMS*</span></span>

        <span data-ttu-id="8a620-352">Ta lokalizacja jest wyznaczonym miejscem odłożenia na potrzeby przyjęcia odrzuconej jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-352">This location is the designated putaway location for rejected quality receiving.</span></span>

    - <span data-ttu-id="8a620-353">**Numer identyfikacyjny:** wygenerowany przez system identyfikator numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="8a620-353">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="8a620-354">**Pozycja:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="8a620-354">**Item:** *M9203*</span></span>
    - <span data-ttu-id="8a620-355">**Ilość:** *1 PL: 100 każdy*</span><span class="sxs-lookup"><span data-stu-id="8a620-355">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="8a620-356">Pokazany jest również opis pozycji.</span><span class="sxs-lookup"><span data-stu-id="8a620-356">The item description is also shown.</span></span>

1. <span data-ttu-id="8a620-357">Potwierdź pracę odłożenia.</span><span class="sxs-lookup"><span data-stu-id="8a620-357">Confirm the putaway work.</span></span>

    <span data-ttu-id="8a620-358">Na stronie **Zadania** dla przyjęcia wiersza zamówienia zakupu zostanie wyświetlony komunikat „praca wykonana”.</span><span class="sxs-lookup"><span data-stu-id="8a620-358">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="8a620-359">Pole **LINENUM** jest dostępne w taki sposób, aby można było rozpocząć otrzymywanie następnej palety.</span><span class="sxs-lookup"><span data-stu-id="8a620-359">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

<span data-ttu-id="8a620-360">Teraz ukończono sprawdzanie jakości i utworzono zlecenie kontroli jakości dla odrzuconej palety.</span><span class="sxs-lookup"><span data-stu-id="8a620-360">You've now completed the quality check and created a quality order for the rejected pallet.</span></span> <span data-ttu-id="8a620-361">Aby wyświetlić zlecenie kontroli jakości utworzone, należy przejść do **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="8a620-361">To view the order that was created, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="8a620-362">Testy zlecenia kontroli jakości można teraz przetworzyć.</span><span class="sxs-lookup"><span data-stu-id="8a620-362">Quality order testing can now be processed.</span></span> <span data-ttu-id="8a620-363">Testowanie jakości nie jest opisane w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="8a620-363">Quality testing isn't covered in this topic.</span></span>

<span data-ttu-id="8a620-364">Aby uzyskać więcej informacji o zarządzaniu jakością funkcji, zapoznaj się z [Zarządzanie jakością — omówienie](../inventory/enable-quality-management.md)</span><span class="sxs-lookup"><span data-stu-id="8a620-364">For more information about quality management, see [Quality management overview](../inventory/enable-quality-management.md)</span></span>

#### <a name="receive-pallet-3"></a><span data-ttu-id="8a620-365">Odbiór palety 3</span><span class="sxs-lookup"><span data-stu-id="8a620-365">Receive pallet 3</span></span>

<span data-ttu-id="8a620-366">W tym scenariuszu paleta 3 zostanie zaakceptowana.</span><span class="sxs-lookup"><span data-stu-id="8a620-366">For this scenario, pallet 3 will be accepted.</span></span>

1. <span data-ttu-id="8a620-367">W polu **LINENUM** wprowadź wartość *1* i potwierdź numer wiersza.</span><span class="sxs-lookup"><span data-stu-id="8a620-367">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="8a620-368">Pole **Ilość** jest teraz dostępne.</span><span class="sxs-lookup"><span data-stu-id="8a620-368">The **QTY** field is now available.</span></span> <span data-ttu-id="8a620-369">Wprowadź wartość *1* i potwierdź ilość.</span><span class="sxs-lookup"><span data-stu-id="8a620-369">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="8a620-370">Zostanie wyświetlona strona **Kontrola jakości**.</span><span class="sxs-lookup"><span data-stu-id="8a620-370">The **Quality check** page appears.</span></span> <span data-ttu-id="8a620-371">W przypadku tego przyjęcia paleta zostanie zaakceptowana w celu uzyskania jakości i zostanie umieszczona w lokalizacji odłożenia partii.</span><span class="sxs-lookup"><span data-stu-id="8a620-371">For this receipt, the pallet will be accepted for quality, and it will be put into a bulk putaway location.</span></span>

1. <span data-ttu-id="8a620-372">Wybierz przycisk potwierdzenia, aby przejść kontrolę jakości.</span><span class="sxs-lookup"><span data-stu-id="8a620-372">Select the confirmation button to pass the quality check.</span></span>

    <span data-ttu-id="8a620-373">Wyświetlona strona **Zamówienia zakupu: Odłóż** zawiera szczegóły dotyczące pracy odłożenia:</span><span class="sxs-lookup"><span data-stu-id="8a620-373">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="8a620-374">**Lokalizacja:** system ustalił lokalizację</span><span class="sxs-lookup"><span data-stu-id="8a620-374">**LOC:** The system determined location</span></span>

        <span data-ttu-id="8a620-375">Ta lokalizacja jest wyznaczonym miejscem odłożenia na potrzeby przyjęcia zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="8a620-375">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="8a620-376">**Numer identyfikacyjny:** wygenerowany przez system identyfikator numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="8a620-376">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="8a620-377">**Pozycja:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="8a620-377">**Item:** *M9203*</span></span>
    - <span data-ttu-id="8a620-378">**Ilość:** *1 PL: 100 każdy*</span><span class="sxs-lookup"><span data-stu-id="8a620-378">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="8a620-379">Pokazany jest również opis pozycji.</span><span class="sxs-lookup"><span data-stu-id="8a620-379">The item description is also shown.</span></span>

1. <span data-ttu-id="8a620-380">Potwierdź pracę odłożenia.</span><span class="sxs-lookup"><span data-stu-id="8a620-380">Confirm the putaway work.</span></span>

    <span data-ttu-id="8a620-381">Na stronie **Zadania** dla przyjęcia wiersza zamówienia zakupu zostanie wyświetlony komunikat „praca wykonana”.</span><span class="sxs-lookup"><span data-stu-id="8a620-381">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="8a620-382">Pole **LINENUM** jest dostępne w taki sposób, aby można było rozpocząć otrzymywanie następnej palety.</span><span class="sxs-lookup"><span data-stu-id="8a620-382">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

1. <span data-ttu-id="8a620-383">Wybierz przycisk menu (**≡**) u góry strony, a następnie w menu wybierz opcję **Anuluj**, aby wrócić do menu.</span><span class="sxs-lookup"><span data-stu-id="8a620-383">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Cancel** to return to the menu.</span></span>

<span data-ttu-id="8a620-384">Teraz możesz zamknąć aplikację mobilną.</span><span class="sxs-lookup"><span data-stu-id="8a620-384">You can now close the mobile app.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]