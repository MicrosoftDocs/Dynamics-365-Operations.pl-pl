---
title: "Czas i frekwencja w sieci sprzedaży"
description: "W tym temacie opisano scenariusze obsługiwane w zakresie zarządzania czasem i frekwencją w module Microsoft Dynamics 365 for Retail."
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ebbf3c72b4c34cba95ecd2fb3ce506af393acc34
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="retail-time-and-attendance"></a><span data-ttu-id="e5dfc-103">Czas i frekwencja w handlu detalicznym</span><span class="sxs-lookup"><span data-stu-id="e5dfc-103">Retail time and attendance</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="e5dfc-104">W tym temacie opisano scenariusze obsługiwane w zakresie zarządzania czasem i frekwencją w module Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-104">This topic describes the scenarios that are supported for time and attendance management in Microsoft Dynamics 365 for Retail.</span></span> 

<a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="e5dfc-105">Zarządzanie ustawieniami i planowaniem pracowników</span><span class="sxs-lookup"><span data-stu-id="e5dfc-105">Manage worker setup and scheduling</span></span>
----------------------------------

### <a name="initial-configuration"></a><span data-ttu-id="e5dfc-106">Pierwotna konfiguracja </span><span class="sxs-lookup"><span data-stu-id="e5dfc-106">Initial configuration</span></span>

-   <span data-ttu-id="e5dfc-107">Włącz kreatora konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-107">Run the configuration wizard.</span></span>
-   <span data-ttu-id="e5dfc-108">Zarejestruj pracowników jako pracowników odpowiedzialnych za rejestrację czasu.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="e5dfc-109">Planowanie harmonogramów pracowników</span><span class="sxs-lookup"><span data-stu-id="e5dfc-109">Plan worker schedules</span></span>

-   <span data-ttu-id="e5dfc-110">Zastosuj profil za pomocą planowania pracy.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="e5dfc-111">Aby uzyskać więcej informacji, zobacz <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-111">For more information, see <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span></span>

<span data-ttu-id="e5dfc-112">Aby uzyskać więcej informacji o etapach konfiguracji, zobacz <https://technet.microsoft.com/en-us/library/aa496971.aspx>.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-112">For information about the configuration steps, see <https://technet.microsoft.com/en-us/library/aa496971.aspx>.</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="e5dfc-113">Konfiguracja właściwa dla sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e5dfc-113">Retail-specific configuration</span></span>

-   <span data-ttu-id="e5dfc-114">Włącz profil funkcji dla Zegara, dla pracowników, którzy mają być odpowiedzialni za rejestrację czasu.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="e5dfc-115">Kliknij kolejno opcje **Profile funkcji punktu sprzedaży** &gt; **Funkcje** &gt; **Rejestracje czasu w punkcie sprzedaży** &gt; **Włącz rejestracje czasu**.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
-   <span data-ttu-id="e5dfc-116">Skonfiguruj grupy uprawnień w punkcie sprzedaży, aby włączyć uprawnienie Wyświetlanie wpisów zegara.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="e5dfc-117">To uprawnienie pozwala wyświetlać rejestracje zegara innych pracowników w danym sklepie (i w każdym innym sklepie, z którym użytkownik jest skojarzony, za pomocą książki adresowej).</span><span class="sxs-lookup"><span data-stu-id="e5dfc-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="e5dfc-118">Można włączyć uprawnienie dla roli Menedżer, ale nie dla roli Kasjer.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="e5dfc-119">Kliknij kolejno opcje **Grupy uprawnień punktu sprzedaży** &gt; **Wyświetlanie wpisów zegara**.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="e5dfc-120">Czas rejestracji</span><span class="sxs-lookup"><span data-stu-id="e5dfc-120">Register time</span></span>
### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="e5dfc-121">Rejestracje czasu dla roli Kasjer i ról innych niż Kasjer</span><span class="sxs-lookup"><span data-stu-id="e5dfc-121">Cashier and non-cashier time registrations</span></span>

-   <span data-ttu-id="e5dfc-122">W punkcie sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="e5dfc-122">On POS:</span></span>
    -   <span data-ttu-id="e5dfc-123">Operacje rejestrowania:</span><span class="sxs-lookup"><span data-stu-id="e5dfc-123">Clock-in operations:</span></span>
        -   <span data-ttu-id="e5dfc-124">Zaloguj się przy użyciu operację bez użycia szuflady lub jak Nowa zmiana.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-124">Log on with a non-drawer operation or New shift.</span></span>
        -   <span data-ttu-id="e5dfc-125">Wybierz operację Zegar.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-125">Select a Time Clock operation.</span></span>
        -   <span data-ttu-id="e5dfc-126">Wybierz żądaną operację:</span><span class="sxs-lookup"><span data-stu-id="e5dfc-126">Select a desired operation:</span></span>
            -   <span data-ttu-id="e5dfc-127">Wejście</span><span class="sxs-lookup"><span data-stu-id="e5dfc-127">Clock-in</span></span>
            -   <span data-ttu-id="e5dfc-128">Przerwa w pracy</span><span class="sxs-lookup"><span data-stu-id="e5dfc-128">Break for Work</span></span>
            -   <span data-ttu-id="e5dfc-129">Przerwa na lunch</span><span class="sxs-lookup"><span data-stu-id="e5dfc-129">Break for Lunch</span></span>
            -   <span data-ttu-id="e5dfc-130">Wyjście</span><span class="sxs-lookup"><span data-stu-id="e5dfc-130">Clock-out</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="e5dfc-131">Bieżący stan</span><span class="sxs-lookup"><span data-stu-id="e5dfc-131">Current state</span></span></th>
    <th><span data-ttu-id="e5dfc-132">Dostępne operacje</span><span class="sxs-lookup"><span data-stu-id="e5dfc-132">Available operations</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="e5dfc-133">Wejście</span><span class="sxs-lookup"><span data-stu-id="e5dfc-133">Clock-in</span></span></td>
    <td><ul>
    <li><span data-ttu-id="e5dfc-134">Przerwa w pracy</span><span class="sxs-lookup"><span data-stu-id="e5dfc-134">Break for Work</span></span></li>
    <li><span data-ttu-id="e5dfc-135">Przerwa na lunch</span><span class="sxs-lookup"><span data-stu-id="e5dfc-135">Break for Lunch</span></span></li>
    <li><span data-ttu-id="e5dfc-136">Wyjście</span><span class="sxs-lookup"><span data-stu-id="e5dfc-136">Clock-out</span></span></li>
    </ul></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="e5dfc-137">Przerwa w pracy</span><span class="sxs-lookup"><span data-stu-id="e5dfc-137">Break for Work</span></span></td>
    <td><span data-ttu-id="e5dfc-138">Wejście</span><span class="sxs-lookup"><span data-stu-id="e5dfc-138">Clock-in</span></span></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="e5dfc-139">Przerwa na lunch</span><span class="sxs-lookup"><span data-stu-id="e5dfc-139">Break for Lunch</span></span></td>
    <td><span data-ttu-id="e5dfc-140">Wejście</span><span class="sxs-lookup"><span data-stu-id="e5dfc-140">Clock-in</span></span></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="e5dfc-141">Wyjście</span><span class="sxs-lookup"><span data-stu-id="e5dfc-141">Clock-out</span></span></td>
    <td><span data-ttu-id="e5dfc-142">Wejście</span><span class="sxs-lookup"><span data-stu-id="e5dfc-142">Clock-in</span></span></td>
    </tr>
    </tbody>
    </table>

    <span data-ttu-id="e5dfc-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="e5dfc-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>
-   <span data-ttu-id="e5dfc-144">Wyświetl komunikat potwierdzający i sprawdź, czy godzina aktualnego działania jest prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
-   <span data-ttu-id="e5dfc-145">Dziennik:</span><span class="sxs-lookup"><span data-stu-id="e5dfc-145">Logbook:</span></span>
    -   <span data-ttu-id="e5dfc-146">Kliknij **Dziennik**, aby wyświetlić działanie zegara.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-146">Click **Logbook** to view time clock activity.</span></span>
    -   <span data-ttu-id="e5dfc-147">Za pomocą filtrów czasu możesz wybrać różne okna czasowe.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-147">Use time filters to select different time windows.</span></span>
    -   <span data-ttu-id="e5dfc-148">Jeśli pracujesz w wielu lokalizacjach sklepów, widoczne są rejestracje czasu we wszystkich sklepach, w których rejestrujesz czas.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="e5dfc-149">Za pomocą filtra sklepu możesz wyświetlać rejestracje czas z wybranego sklepu.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-149">You can use the store filter to view time registrations from a selected store.</span></span>

<!-- -->

-   <span data-ttu-id="e5dfc-150">Różne strefy czasowe:</span><span class="sxs-lookup"><span data-stu-id="e5dfc-150">Different time zones:</span></span>
    -   <span data-ttu-id="e5dfc-151">W przypadku wyświetlenia czasu z innej lokalizacji (dla dziennika kasjera lub za pomocą opcji **Wyświetlanie wpisów zegara** dla menedżera) i gdy ta lokalizacja jest w innej strefie czasowej, widoczne rejestracje czasu są konwertowane na czas lokalny.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="e5dfc-152">Załóżmy, że zarządzasz dwoma sklepami — w Arizonie i Nevadzie.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="e5dfc-153">Kasjer rejestruje przyjście do pracy o godzinie 9:00</span><span class="sxs-lookup"><span data-stu-id="e5dfc-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="e5dfc-154">w Arizonie.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-154">in Arizona.</span></span> <span data-ttu-id="e5dfc-155">W tym momencie w Nevadzie jest godzina 8:00.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="e5dfc-156">Jeśli więc jesteś w Nevadzie i przeglądasz dane rejestracji czasu, wskazywana jest godzina 8:00.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="e5dfc-157">Wyświetlanie rejestracji czasu pracownika</span><span class="sxs-lookup"><span data-stu-id="e5dfc-157">View worker time registrations</span></span>
### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="e5dfc-158">Wyświetlanie rejestracji czasu pracownika i filtrowanie według sklepu lub typu aktywności</span><span class="sxs-lookup"><span data-stu-id="e5dfc-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="e5dfc-159">W punkcie sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="e5dfc-159">On POS:</span></span>

-   <span data-ttu-id="e5dfc-160">Wybierz **Wyświetlanie wpisów zegara**.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-160">Select **View timeclock entries**.</span></span>
-   <span data-ttu-id="e5dfc-161">Widać działania rejestracji czasu dla wszystkich pracowników przypisanych do tych samych sklepów, do których jesteś przypisany Ty.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
-   <span data-ttu-id="e5dfc-162">Za pomocą filtrów typu działania i sklepu możesz filtrować rejestracje czasu.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="e5dfc-163">Przetwarzanie rejestracji czasu i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="e5dfc-163">Process and manage time registrations</span></span>
<span data-ttu-id="e5dfc-164">Użytkownik programu Dynamics 365 for Retail wykonuje procedurę obliczania, zatwierdzania i przesłania rejestracji czasu do listy płac.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-164">A Dynamics 365 for Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="e5dfc-165">Podstawowe operacje</span><span class="sxs-lookup"><span data-stu-id="e5dfc-165">Primary operations</span></span>

-   <span data-ttu-id="e5dfc-166">Oblicz</span><span class="sxs-lookup"><span data-stu-id="e5dfc-166">Calculate</span></span>
-   <span data-ttu-id="e5dfc-167">Zatwierdź</span><span class="sxs-lookup"><span data-stu-id="e5dfc-167">Approve</span></span>
-   <span data-ttu-id="e5dfc-168">Prześlij do listy płac</span><span class="sxs-lookup"><span data-stu-id="e5dfc-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="e5dfc-169">Inne częste operacje</span><span class="sxs-lookup"><span data-stu-id="e5dfc-169">Other common operations</span></span>

-   <span data-ttu-id="e5dfc-170">Grupowe wyrejestrowania</span><span class="sxs-lookup"><span data-stu-id="e5dfc-170">Bulk Clock-out</span></span>
-   <span data-ttu-id="e5dfc-171">Rejestrowanie nieobecności</span><span class="sxs-lookup"><span data-stu-id="e5dfc-171">Register Absence</span></span>

<span data-ttu-id="e5dfc-172">Aby uzyskać więcej informacji na temat przetwarzania rejestracji czasu i nieobecności, zobacz <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span><span class="sxs-lookup"><span data-stu-id="e5dfc-172">For more information about how to process time and attendance registrations, see <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span></span>




