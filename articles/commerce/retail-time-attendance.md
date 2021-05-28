---
title: Zarządzanie czasem i frekwencją w module Retail
description: W tym temacie opisano scenariusze obsługiwane w zakresie zarządzania czasem i frekwencją w module Dynamics 365 Commerce.
author: aamirallaqaband
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7ac7eec69bda7ad2fa41a7311a71a969eddeafb6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021495"
---
# <a name="time-and-attendance-management-in-retail"></a><span data-ttu-id="4b4fb-103">Zarządzanie czasem i frekwencją w module Retail</span><span class="sxs-lookup"><span data-stu-id="4b4fb-103">Time and attendance management in Retail</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4b4fb-104">W tym temacie opisano scenariusze obsługiwane w zakresie zarządzania czasem i frekwencją w module Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-104">This topic describes the scenarios that are supported for time and attendance management in Dynamics 365 Commerce.</span></span>

## <a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="4b4fb-105">Zarządzanie ustawieniami i planowaniem pracowników</span><span class="sxs-lookup"><span data-stu-id="4b4fb-105">Manage worker setup and scheduling</span></span>

### <a name="initial-configuration"></a><span data-ttu-id="4b4fb-106">Pierwotna konfiguracja </span><span class="sxs-lookup"><span data-stu-id="4b4fb-106">Initial configuration</span></span>

- <span data-ttu-id="4b4fb-107">Włącz kreatora konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-107">Run the configuration wizard.</span></span>
- <span data-ttu-id="4b4fb-108">Zarejestruj pracowników jako pracowników odpowiedzialnych za rejestrację czasu.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="4b4fb-109">Planowanie harmonogramów pracowników</span><span class="sxs-lookup"><span data-stu-id="4b4fb-109">Plan worker schedules</span></span>

- <span data-ttu-id="4b4fb-110">Zastosuj profil za pomocą planowania pracy.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="4b4fb-111">Aby uzyskać więcej informacji, zobacz [Stosowanie profilu poprzez planowanie pracy](/dynamicsax-2012/appuser-itpro/apply-profiles-using-work-planner).</span><span class="sxs-lookup"><span data-stu-id="4b4fb-111">For more information, see [Apply profiles using work planner](/dynamicsax-2012/appuser-itpro/apply-profiles-using-work-planner).</span></span>

<span data-ttu-id="4b4fb-112">Uzyskać informacje dotyczące kroków konfiguracji, zobacz [Konfigurowanie modułu Czas i frekwencja](/dynamicsax-2012/appuser-itpro/setting-up-time-and-attendance).</span><span class="sxs-lookup"><span data-stu-id="4b4fb-112">For information about the configuration steps, see [Setting up time and attendance](/dynamicsax-2012/appuser-itpro/setting-up-time-and-attendance).</span></span>

### <a name="commerce-specific-configuration"></a><span data-ttu-id="4b4fb-113">Konfiguracja usług określonych dla Commerce</span><span class="sxs-lookup"><span data-stu-id="4b4fb-113">Commerce-specific configuration</span></span>

- <span data-ttu-id="4b4fb-114">Włącz profil funkcji dla Zegara, dla pracowników, którzy mają być odpowiedzialni za rejestrację czasu.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="4b4fb-115">Kliknij kolejno opcje **Profile funkcji punktu sprzedaży** &gt; **Funkcje** &gt; **Rejestracje czasu w punkcie sprzedaży** &gt; **Włącz rejestracje czasu**.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
- <span data-ttu-id="4b4fb-116">Skonfiguruj grupy uprawnień w punkcie sprzedaży, aby włączyć uprawnienie Wyświetlanie wpisów zegara.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="4b4fb-117">To uprawnienie pozwala wyświetlać rejestracje zegara innych pracowników w danym sklepie (i w każdym innym sklepie, z którym użytkownik jest skojarzony, za pomocą książki adresowej).</span><span class="sxs-lookup"><span data-stu-id="4b4fb-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="4b4fb-118">Można włączyć uprawnienie dla roli Menedżer, ale nie dla roli Kasjer.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="4b4fb-119">Kliknij kolejno opcje **Grupy uprawnień punktu sprzedaży** &gt; **Wyświetlanie wpisów zegara**.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="4b4fb-120">Czas rejestracji</span><span class="sxs-lookup"><span data-stu-id="4b4fb-120">Register time</span></span>

### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="4b4fb-121">Rejestracje czasu dla roli Kasjer i ról innych niż Kasjer</span><span class="sxs-lookup"><span data-stu-id="4b4fb-121">Cashier and non-cashier time registrations</span></span>

- <span data-ttu-id="4b4fb-122">W punkcie sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="4b4fb-122">On POS:</span></span>

    - <span data-ttu-id="4b4fb-123">Operacje rejestrowania:</span><span class="sxs-lookup"><span data-stu-id="4b4fb-123">Clock-in operations:</span></span>

        - <span data-ttu-id="4b4fb-124">Zaloguj się przy użyciu operację bez użycia szuflady lub jak Nowa zmiana.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-124">Log on with a non-drawer operation or New shift.</span></span>
        - <span data-ttu-id="4b4fb-125">Wybierz operację Zegar.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-125">Select a Time Clock operation.</span></span>
        - <span data-ttu-id="4b4fb-126">Wybierz żądaną operację:</span><span class="sxs-lookup"><span data-stu-id="4b4fb-126">Select a desired operation:</span></span>

            - <span data-ttu-id="4b4fb-127">Wejście</span><span class="sxs-lookup"><span data-stu-id="4b4fb-127">Clock-in</span></span>
            - <span data-ttu-id="4b4fb-128">Przerwa w pracy</span><span class="sxs-lookup"><span data-stu-id="4b4fb-128">Break for Work</span></span>
            - <span data-ttu-id="4b4fb-129">Przerwa na lunch</span><span class="sxs-lookup"><span data-stu-id="4b4fb-129">Break for Lunch</span></span>
            - <span data-ttu-id="4b4fb-130">Wyjście</span><span class="sxs-lookup"><span data-stu-id="4b4fb-130">Clock-out</span></span>

        <table>
        <thead>
        <tr>
        <th><span data-ttu-id="4b4fb-131">Bieżący stan</span><span class="sxs-lookup"><span data-stu-id="4b4fb-131">Current state</span></span></th>
        <th><span data-ttu-id="4b4fb-132">Dostępne operacje</span><span class="sxs-lookup"><span data-stu-id="4b4fb-132">Available operations</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td><span data-ttu-id="4b4fb-133">Wejście</span><span class="sxs-lookup"><span data-stu-id="4b4fb-133">Clock-in</span></span></td>
        <td>
        <ul>
        <li><span data-ttu-id="4b4fb-134">Przerwa w pracy</span><span class="sxs-lookup"><span data-stu-id="4b4fb-134">Break for Work</span></span></li>
        <li><span data-ttu-id="4b4fb-135">Przerwa na lunch</span><span class="sxs-lookup"><span data-stu-id="4b4fb-135">Break for Lunch</span></span></li>
        <li><span data-ttu-id="4b4fb-136">Wyjście</span><span class="sxs-lookup"><span data-stu-id="4b4fb-136">Clock-out</span></span></li>
        </ul>
        </td>
        </tr>
        <tr>
        <td><span data-ttu-id="4b4fb-137">Przerwa w pracy</span><span class="sxs-lookup"><span data-stu-id="4b4fb-137">Break for Work</span></span></td>
        <td><span data-ttu-id="4b4fb-138">Wejście</span><span class="sxs-lookup"><span data-stu-id="4b4fb-138">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="4b4fb-139">Przerwa na lunch</span><span class="sxs-lookup"><span data-stu-id="4b4fb-139">Break for Lunch</span></span></td>
        <td><span data-ttu-id="4b4fb-140">Wejście</span><span class="sxs-lookup"><span data-stu-id="4b4fb-140">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="4b4fb-141">Wyjście</span><span class="sxs-lookup"><span data-stu-id="4b4fb-141">Clock-out</span></span></td>
        <td><span data-ttu-id="4b4fb-142">Wejście</span><span class="sxs-lookup"><span data-stu-id="4b4fb-142">Clock-in</span></span></td>
        </tr>
        </tbody>
        </table>

        <span data-ttu-id="4b4fb-143">[![Stany zegara](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="4b4fb-143">[![Time Clock States](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>

- <span data-ttu-id="4b4fb-144">Wyświetl komunikat potwierdzający i sprawdź, czy godzina aktualnego działania jest prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
- <span data-ttu-id="4b4fb-145">Dziennik:</span><span class="sxs-lookup"><span data-stu-id="4b4fb-145">Logbook:</span></span>

    - <span data-ttu-id="4b4fb-146">Kliknij **Dziennik**, aby wyświetlić działanie zegara.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-146">Click **Logbook** to view time clock activity.</span></span>
    - <span data-ttu-id="4b4fb-147">Za pomocą filtrów czasu możesz wybrać różne okna czasowe.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-147">Use time filters to select different time windows.</span></span>
    - <span data-ttu-id="4b4fb-148">Jeśli pracujesz w wielu lokalizacjach sklepów, widoczne są rejestracje czasu we wszystkich sklepach, w których rejestrujesz czas.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="4b4fb-149">Za pomocą filtra sklepu możesz wyświetlać rejestracje czas z wybranego sklepu.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-149">You can use the store filter to view time registrations from a selected store.</span></span>

- <span data-ttu-id="4b4fb-150">Różne strefy czasowe:</span><span class="sxs-lookup"><span data-stu-id="4b4fb-150">Different time zones:</span></span>

    - <span data-ttu-id="4b4fb-151">W przypadku wyświetlenia czasu z innej lokalizacji (dla dziennika kasjera lub za pomocą opcji **Wyświetlanie wpisów zegara** dla menedżera) i gdy ta lokalizacja jest w innej strefie czasowej, widoczne rejestracje czasu są konwertowane na czas lokalny.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="4b4fb-152">Załóżmy, że zarządzasz dwoma sklepami — w Arizonie i Nevadzie.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="4b4fb-153">Kasjer rejestruje przyjście do pracy o godzinie 9:00</span><span class="sxs-lookup"><span data-stu-id="4b4fb-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="4b4fb-154">w Arizonie.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-154">in Arizona.</span></span> <span data-ttu-id="4b4fb-155">W tym momencie w Nevadzie jest godzina 8:00.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="4b4fb-156">Jeśli więc jesteś w Nevadzie i przeglądasz dane rejestracji czasu, wskazywana jest godzina 8:00.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="4b4fb-157">Wyświetlanie rejestracji czasu pracownika</span><span class="sxs-lookup"><span data-stu-id="4b4fb-157">View worker time registrations</span></span>

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="4b4fb-158">Wyświetlanie rejestracji czasu pracownika i filtrowanie według sklepu lub typu aktywności</span><span class="sxs-lookup"><span data-stu-id="4b4fb-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="4b4fb-159">W punkcie sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="4b4fb-159">On POS:</span></span>

- <span data-ttu-id="4b4fb-160">Wybierz **Wyświetlanie wpisów zegara**.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-160">Select **View timeclock entries**.</span></span>
- <span data-ttu-id="4b4fb-161">Widać działania rejestracji czasu dla wszystkich pracowników przypisanych do tych samych sklepów, do których jesteś przypisany Ty.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
- <span data-ttu-id="4b4fb-162">Za pomocą filtrów typu działania i sklepu możesz filtrować rejestracje czasu.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="4b4fb-163">Przetwarzanie rejestracji czasu i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="4b4fb-163">Process and manage time registrations</span></span>

<span data-ttu-id="4b4fb-164">Użytkownik usługi Commerce wykonuje procedurę obliczania, zatwierdzania i przesłania rejestracji czasu do listy płac.</span><span class="sxs-lookup"><span data-stu-id="4b4fb-164">A Commerce user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="4b4fb-165">Podstawowe operacje</span><span class="sxs-lookup"><span data-stu-id="4b4fb-165">Primary operations</span></span>

- <span data-ttu-id="4b4fb-166">Oblicz</span><span class="sxs-lookup"><span data-stu-id="4b4fb-166">Calculate</span></span>
- <span data-ttu-id="4b4fb-167">Zatwierdź</span><span class="sxs-lookup"><span data-stu-id="4b4fb-167">Approve</span></span>
- <span data-ttu-id="4b4fb-168">Prześlij do listy płac</span><span class="sxs-lookup"><span data-stu-id="4b4fb-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="4b4fb-169">Inne częste operacje</span><span class="sxs-lookup"><span data-stu-id="4b4fb-169">Other common operations</span></span>

- <span data-ttu-id="4b4fb-170">Grupowe wyrejestrowania</span><span class="sxs-lookup"><span data-stu-id="4b4fb-170">Bulk Clock-out</span></span>
- <span data-ttu-id="4b4fb-171">Rejestrowanie nieobecności</span><span class="sxs-lookup"><span data-stu-id="4b4fb-171">Register Absence</span></span>

<span data-ttu-id="4b4fb-172">Aby uzyskać więcej informacji na temat procesu rejestracji czasu i obecności, zobacz [Przetwarzanie rejestracji czasu i frekwencji](/dynamicsax-2012/appuser-itpro/process-time-and-attendance-registrations).</span><span class="sxs-lookup"><span data-stu-id="4b4fb-172">For more information about how to process time and attendance registrations, see [Process time and attendance registrations](/dynamicsax-2012/appuser-itpro/process-time-and-attendance-registrations).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]