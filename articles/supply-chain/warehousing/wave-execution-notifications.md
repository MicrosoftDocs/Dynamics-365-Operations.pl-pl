---
title: Powiadomienia dotyczące wykonania grupy czynności
description: W tym temacie opisano powiadomienia o wykonywaniu grupy czynności i wyjaśniono, jak je skonfigurować.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2022-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: fee112d3211f619b2146dd21c4f8a52ad33667d6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019161"
---
# <a name="wave-execution-notifications"></a><span data-ttu-id="7eb22-103">Powiadomienia dotyczące wykonania grupy czynności</span><span class="sxs-lookup"><span data-stu-id="7eb22-103">Wave execution notifications</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="7eb22-104">Funkcja *powiadomień o wykonaniu grupy czynności* korzysta ze zdarzeń biznesowych i centrum akcji w celu dostarczania powiadomień dotyczących wykonywania grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="7eb22-104">The *Wave execution notifications* feature uses business events and the Action center to deliver notifications that are related to wave execution.</span></span> <span data-ttu-id="7eb22-105">Użytkownik może określać typy zdarzeń generujące powiadomienia, magazyny je generujące oraz użytkowników, którzy je otrzymują.</span><span class="sxs-lookup"><span data-stu-id="7eb22-105">It lets you specify the types of events that generate notifications, the warehouses that generate them, and the users who receive them.</span></span>

<span data-ttu-id="7eb22-106">Przycisk **Pokaż komunikaty** (symbol dzwonka) po prawej stronie paska nawigacji wskazuje, kiedy wiadomość z centrum akcji jest dostępna dla bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7eb22-106">The **Show messages** button (bell symbol) on the right side of the navigation bar indicates when an Action center message is available for the current user.</span></span> <span data-ttu-id="7eb22-107">Użytkownik może wybrać przycisk **Pokaż wiadomości**, aby otworzyć Centrum akcji i przejrzeć wiadomości.</span><span class="sxs-lookup"><span data-stu-id="7eb22-107">The user can select the **Show messages** button to open the Action center and review the messages.</span></span>

<span data-ttu-id="7eb22-108">Zdarzenia biznesowe mają miejsce podczas uruchamiania procesów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="7eb22-108">Business events occur when business processes are run.</span></span> <span data-ttu-id="7eb22-109">Procesy biznesowe są składa się z zadań.</span><span class="sxs-lookup"><span data-stu-id="7eb22-109">Business processes are made up of tasks.</span></span> <span data-ttu-id="7eb22-110">W trakcie procesu biznesowego użytkownicy, którzy uczestniczą w tym procesie, wykonują akcje biznesowe w celu wykonania tych zadań.</span><span class="sxs-lookup"><span data-stu-id="7eb22-110">During a business process, the users who participate in it perform business actions to complete those tasks.</span></span> <span data-ttu-id="7eb22-111">Zdarzenia biznesowe zapewniają mechanizm, za który zewnętrzne systemy otrzymują powiadomienia od aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7eb22-111">Business events provide a mechanism that lets external systems receive notifications from Finance and Operations applications.</span></span> <span data-ttu-id="7eb22-112">W ten sposób systemy mogą wykonywać akcje biznesowe w odpowiedzi na zdarzenia biznesowe.</span><span class="sxs-lookup"><span data-stu-id="7eb22-112">In this way, the systems can perform business actions in response to the business events.</span></span> <span data-ttu-id="7eb22-113">Aby uzyskać więcej informacji, zajrzyj do [Zdarzenia biznesowe - omówienie](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span><span class="sxs-lookup"><span data-stu-id="7eb22-113">For more information, see [Business events overview](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span></span>

## <a name="turn-on-the-wave-execution-notifications-feature"></a><span data-ttu-id="7eb22-114">Włącz funkcję powiadomień o wykonaniu Wave</span><span class="sxs-lookup"><span data-stu-id="7eb22-114">Turn on the Wave execution notifications feature</span></span>

<span data-ttu-id="7eb22-115">Aby móc używać funkcji *Powiadomieniw ykonania grupy czynności*, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="7eb22-115">Before you can use the *Wave execution notifications* feature, it must be turned on in your system.</span></span> <span data-ttu-id="7eb22-116">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="7eb22-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="7eb22-117">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="7eb22-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="7eb22-118">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="7eb22-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="7eb22-119">**Nazwa funkcji:** *Powiadomienia o wykonaniu grupy czynności*</span><span class="sxs-lookup"><span data-stu-id="7eb22-119">**Feature name:** *Wave execution notifications*</span></span>

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a><span data-ttu-id="7eb22-120">Scenariusz: wysyłanie powiadomień o przetwarzaniu wsadowym grupy czynności do centrum akcji</span><span class="sxs-lookup"><span data-stu-id="7eb22-120">Scenario: Send wave batch execution notifications to the Action center</span></span>

<span data-ttu-id="7eb22-121">Ten scenariusz przedstawia przepływ końca okresu, w którym można wysyłać powiadomienia o błędach przetwarzania wsadowego grupy czynności do określonej roli za pośrednictwem centrum akcji.</span><span class="sxs-lookup"><span data-stu-id="7eb22-121">This scenario shows the end-to-end flow for sending notifications about wave batch execution errors to a specific role via the Action center.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="7eb22-122">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="7eb22-122">Make demo data available</span></span>

<span data-ttu-id="7eb22-123">W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma **USMF**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-123">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a><span data-ttu-id="7eb22-124">Upewnij się, że partie są uruchamiane w trybie wsadowym</span><span class="sxs-lookup"><span data-stu-id="7eb22-124">Make sure that waves are run in batch mode</span></span>

1. <span data-ttu-id="7eb22-125">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-125">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="7eb22-126">Na skróconej karcie **Przetwarzanie grupy czynności** należy skonfigurować **Przetwarzanie wsadowe grup czynności** na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="7eb22-126">On the **Wave processing** FastTab, set the **Process waves in batch** option to *Yes*.</span></span>

> [!NOTE]
> <span data-ttu-id="7eb22-127">Jeśli chcesz wyłączyć powiadomienia dotyczące przetwarzania wsadowego grupy czynności, ustaw opcję **Wyłącz powiadomienia o przetwarzaniu wsadowym grupy czynności** na Wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="7eb22-127">If you want to disable wave batch execution notifications, set the **Disable wave processing batch notifications** option to *Yes*.</span></span>

### <a name="configure-a-wave-notification-policy"></a><span data-ttu-id="7eb22-128">Konfigurowanie zasad powiadamiania o grupy czynności</span><span class="sxs-lookup"><span data-stu-id="7eb22-128">Configure a wave notification policy</span></span>

<span data-ttu-id="7eb22-129">Zasady powiadomień grupy czynności określają typy wysyłanych powiadomień oraz powiadamianych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="7eb22-129">Wave notification policies define the types of notifications that are sent and the users who are notified.</span></span>

1. <span data-ttu-id="7eb22-130">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Zasady powiadamiania o grupie czynności**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-130">Go to **Warehouse management \> Setup \> Waves \> Wave notification policies**.</span></span>
1. <span data-ttu-id="7eb22-131">Dodaj rekord z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="7eb22-131">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="7eb22-132">**Zasady powiadamiania o grupie czynności:** *24BatchError*</span><span class="sxs-lookup"><span data-stu-id="7eb22-132">**Wave notification policy:** *24BatchError*</span></span>
    - <span data-ttu-id="7eb22-133">**Opis:** *Błąd partii grupy czynności magazynu 24*</span><span class="sxs-lookup"><span data-stu-id="7eb22-133">**Description:** *Warehouse 24 wave batch error*</span></span>
    - <span data-ttu-id="7eb22-134">**Wyślij powiadomienie w:** *tylko błąd*</span><span class="sxs-lookup"><span data-stu-id="7eb22-134">**Send notification on:** *Error only*</span></span>
    - <span data-ttu-id="7eb22-135">**Do roli:** *Administrator systemu*</span><span class="sxs-lookup"><span data-stu-id="7eb22-135">**To role:** *System administrator*</span></span>

        > [!NOTE]
        > <span data-ttu-id="7eb22-136">Ponieważ w tym scenariuszu są używane dane demonstracyjne, rola *Administrator systemu* jest wybierana na potrzeby zakańca.</span><span class="sxs-lookup"><span data-stu-id="7eb22-136">Because this scenario uses demo data, the *System administrator* role is selected for the sake of simplicity.</span></span> <span data-ttu-id="7eb22-137">Dlatego, ponieważ jesteś zalogowanym użytkownikiem administratora systemu, otrzymasz powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="7eb22-137">Therefore, because you're signed in as a system administrator user, you will receive the notifications.</span></span> <span data-ttu-id="7eb22-138">Jednak w praktyce zazwyczaj należy wybrać bardziej specyficzną rolę, aby powiadamiać o błędach przetwarzania wsadowego grupy czynności, takich jak *Menedżer magazynu*.</span><span class="sxs-lookup"><span data-stu-id="7eb22-138">However, in practice, you should usually select a more specific role to notify about wave batch execution errors, such as *Warehouse manager*.</span></span>

1. <span data-ttu-id="7eb22-139">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-139">On the Action Pane, select **Save**.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="7eb22-140">Skonfiguruj szablon grupy czynności</span><span class="sxs-lookup"><span data-stu-id="7eb22-140">Configure a wave template</span></span>

<span data-ttu-id="7eb22-141">Szablony grupy czynności umożliwiają łączenie konkretnych instancji metod grupy czynności z odpowiednim szablonem etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="7eb22-141">Wave templates let you link specific instances of wave methods to corresponding wave label templates.</span></span>

1. <span data-ttu-id="7eb22-142">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-142">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="7eb22-143">W okienku listy ustaw w polu **Typ szablonu grupy czynności** wartość *Wysyłka*, a następnie wybierz szablon *domyślnej wysyłki 24* grupy czynności dla magazynu 24.</span><span class="sxs-lookup"><span data-stu-id="7eb22-143">In the list pane, set the **Wave template type** field to *Shipping*, and then select the *24 Shipping Default* wave template for warehouse 24.</span></span>
1. <span data-ttu-id="7eb22-144">Na skróconej karcie **Ogólne** należy określić wartość w polu **Zasady powiadomień grupy** na *24BatchError*.</span><span class="sxs-lookup"><span data-stu-id="7eb22-144">On the **General** FastTab, set the **Wave notification policy** field to *24BatchError*.</span></span>

### <a name="configure-a-work-template"></a><span data-ttu-id="7eb22-145">Skonfiguruj szablon pracy</span><span class="sxs-lookup"><span data-stu-id="7eb22-145">Configure a work template</span></span>

<span data-ttu-id="7eb22-146">Szablony pracy są używane podczas wykonywania grupy czynności do generowania pracy.</span><span class="sxs-lookup"><span data-stu-id="7eb22-146">Work templates are used during wave execution to generate work.</span></span> <span data-ttu-id="7eb22-147">W tym scenariuszu wykonanie grupy czynności powinno wyzwolić błąd.</span><span class="sxs-lookup"><span data-stu-id="7eb22-147">For this scenario, wave execution should trigger an error.</span></span> <span data-ttu-id="7eb22-148">Ustawienie kwerendy szablonu pracy na użycie nieistniejącego magazynu pozwoli upewnić się, że wykonanie grupy czynności nie powiedzie się i dlatego zostanie wysyłane powiadomienie.</span><span class="sxs-lookup"><span data-stu-id="7eb22-148">By setting the work template query to use a nonexistent warehouse, you will ensure that wave execution fails and therefore sends a notification.</span></span>

1. <span data-ttu-id="7eb22-149">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-149">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="7eb22-150">W okienku listy ustaw w polu **Typ szablonu pracy** wartość *Zlecenie sprzedaży*, a następnie wybierz szablon *24 SO Stage* pracy dla magazynu 24.</span><span class="sxs-lookup"><span data-stu-id="7eb22-150">In the list pane, set the **Work template type** field to *Sales orders* and then select the *24 SO Stage* work template for warehouse 24.</span></span>
1. <span data-ttu-id="7eb22-151">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-151">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="7eb22-152">W oknie dialogowym edytora zapytań, na karcie **Zakres** dokonaj edycji następującego wiersza (lub dodaj go, jeśli nie istnieje):</span><span class="sxs-lookup"><span data-stu-id="7eb22-152">In the query editor dialog box, on the **Range** tab, edit the following row (or add it if it doesn't exist):</span></span>

    - <span data-ttu-id="7eb22-153">**Tabela:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7eb22-153">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="7eb22-154">**Tabela pochodna:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7eb22-154">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="7eb22-155">**Pole:** *Magazyn*</span><span class="sxs-lookup"><span data-stu-id="7eb22-155">**Field:** *Warehouse*</span></span>
    - <span data-ttu-id="7eb22-156">**Kryteria:** zmień wartość z *24* na *Błąd*.</span><span class="sxs-lookup"><span data-stu-id="7eb22-156">**Criteria:** Change the value from *24* to *Error*.</span></span>

1. <span data-ttu-id="7eb22-157">Potwierdź zmiany i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-157">Select **OK**, and confirm the change.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="7eb22-158">Utwórz zamówienie sprzedaży i zwolnij je do magazynu</span><span class="sxs-lookup"><span data-stu-id="7eb22-158">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="7eb22-159">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienie sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-159">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="7eb22-160">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="7eb22-160">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="7eb22-161">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="7eb22-161">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="7eb22-162">**Magazyn:** *24*</span><span class="sxs-lookup"><span data-stu-id="7eb22-162">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="7eb22-163">Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj drugie zamówienie sprzedaży o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="7eb22-163">On the **Sales order lines** FastTab, add a sales order line that has the following settings:</span></span>

    - <span data-ttu-id="7eb22-164">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="7eb22-164">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="7eb22-165">**Ilość:** *10*</span><span class="sxs-lookup"><span data-stu-id="7eb22-165">**Quantity:** *10*</span></span>

    > [!NOTE]
    > <span data-ttu-id="7eb22-166">Te towary i ilości są tylko przykładami.</span><span class="sxs-lookup"><span data-stu-id="7eb22-166">These items and quantities are only examples.</span></span> <span data-ttu-id="7eb22-167">Określony magazyn musi zawierać wystarczającą ilość zapasów.</span><span class="sxs-lookup"><span data-stu-id="7eb22-167">The specified warehouse must contain enough stock.</span></span>

1. <span data-ttu-id="7eb22-168">Gdy nowy wiersz zamówienia jest wciąż wybrany na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Inventory \> Rezerwacja** na pasku narzędzi..</span><span class="sxs-lookup"><span data-stu-id="7eb22-168">While the new line is still selected on the **Sales order lines** FastTab, select **Inventory \> Reservation** on the toolbar.</span></span>
1. <span data-ttu-id="7eb22-169">Na stronie **Rezerwacje** w okienku akcji wybierz **Rezerwacja partii**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-169">On the **Reservation** page, on the Action Pane, select **Reserve lot**.</span></span> <span data-ttu-id="7eb22-170">Następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7eb22-170">Then close the page.</span></span>
1. <span data-ttu-id="7eb22-171">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="7eb22-171">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

### <a name="notifications-from-wave-batch-job-execution"></a><span data-ttu-id="7eb22-172">Powiadomienia z wykonania zadania wsadowego grupy czynności</span><span class="sxs-lookup"><span data-stu-id="7eb22-172">Notifications from wave batch job execution</span></span>

<span data-ttu-id="7eb22-173">W zależności od konfiguracji zdarzeń biznesowych użytkownik ostatecznie otrzyma powiadomienie o niepowodzeniu wykonania grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="7eb22-173">Depending on the setup of your business events, you will eventually receive a notification about wave execution failure.</span></span> <span data-ttu-id="7eb22-174">Komunikat centrum akcji przypomina poniższy przykład i zawiera łącze do grupy czynności, która zakończyła się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="7eb22-174">The Action center message will resemble the following example and will include a link to the wave that failed.</span></span>

> <span data-ttu-id="7eb22-175">**Błąd podczas wykonywania grupy czynności**</span><span class="sxs-lookup"><span data-stu-id="7eb22-175">**Error during wave execution**</span></span>  
> <span data-ttu-id="7eb22-176">Wystąpił błąd podczas wykonywania grupy czynności USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="7eb22-176">An error occurred while executing wave USMF-000000001.</span></span>  
> <span data-ttu-id="7eb22-177">Ostatnie komunikaty: Nie utworzono pracy dla grupy czynności USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="7eb22-177">Last messages: No Work was created for Wave USMF-000000001.</span></span>
>
> <span data-ttu-id="7eb22-178">**STAN**</span><span class="sxs-lookup"><span data-stu-id="7eb22-178">**STATUS**</span></span>  
> <span data-ttu-id="7eb22-179">Aktywni</span><span class="sxs-lookup"><span data-stu-id="7eb22-179">Active</span></span>
>
> <span data-ttu-id="7eb22-180">Otwórz szczegóły grupy czynności</span><span class="sxs-lookup"><span data-stu-id="7eb22-180">Open wave details</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
