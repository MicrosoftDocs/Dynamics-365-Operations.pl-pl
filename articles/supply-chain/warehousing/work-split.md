---
title: Podział pracy
description: Ten temat zawiera informacje dotyczące funkcji podziału pracy. Ta funkcja umożliwia dzielenie dużych zleceń roboczych na kilka mniejszych zleceń produkcyjnych, które można następnie przypisać do wielu pracowników magazynu. Dzięki temu ta sama praca może być pobierana jednocześnie przez kilku pracowników magazynu.
author: mirzaab
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: eae1e722a7c4d819cbca398eb14a2b36fa04eec5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830769"
---
# <a name="work-split"></a><span data-ttu-id="682e7-105">Podział pracy</span><span class="sxs-lookup"><span data-stu-id="682e7-105">Work split</span></span>

<span data-ttu-id="682e7-106">Funkcja podziału pracy umożliwia dzielenie identyfikatorów dużych zleceń roboczych (czyli zleceń pracy, które mają kilka wierszy) na kilka mniejszych identyfikatorów zleceń produkcyjnych, które można następnie przypisać do wielu pracowników magazynu.</span><span class="sxs-lookup"><span data-stu-id="682e7-106">Work split functionality lets you split large work IDs (that is, work orders that have several lines) into several smaller work IDs that you can then assign to multiple warehouse workers.</span></span> <span data-ttu-id="682e7-107">Dzięki temu numer utworzenia tej samej pracy może być pobierany jednocześnie przez kilku pracowników magazynu.</span><span class="sxs-lookup"><span data-stu-id="682e7-107">In this way, the same work creation number can be picked simultaneously by several warehouse workers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="682e7-108">Można dzielić tylko zlecenia pracy, które mają stan *Otwarte* lub *W toku*.</span><span class="sxs-lookup"><span data-stu-id="682e7-108">You can split only work orders that have a status of *Open* or *In-progress*.</span></span>

## <a name="turn-on-the-work-split-functionality"></a><span data-ttu-id="682e7-109">Włącz funkcję podziału pracy</span><span class="sxs-lookup"><span data-stu-id="682e7-109">Turn on the work split functionality</span></span>

<span data-ttu-id="682e7-110">Aby można było korzystać z funkcji podziału pracy, należy włączyć tę funkcję i jej funkcję wstępnie wymaganą w systemie.</span><span class="sxs-lookup"><span data-stu-id="682e7-110">Before you can use the work split functionality, you must turn on the feature and its prerequisite feature in your system.</span></span> <span data-ttu-id="682e7-111">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć je, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="682e7-111">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on as required.</span></span>

<span data-ttu-id="682e7-112">Najpierw włącz wstępnie wymaganą funkcję *Blokowania pracy w całej organizacji*, jeśli nie została jeszcze włączona.</span><span class="sxs-lookup"><span data-stu-id="682e7-112">First, turn on the prerequisite *Organization-wide work blocking* feature if it isn't already turned on.</span></span> <span data-ttu-id="682e7-113">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="682e7-113">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="682e7-114">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="682e7-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="682e7-115">**Nazwa funkcji:** *Blokowanie pracy w całej organizacji*</span><span class="sxs-lookup"><span data-stu-id="682e7-115">**Feature name:** *Organization-wide work blocking*</span></span>

> [!NOTE]
> <span data-ttu-id="682e7-116">Po uaktywnieniu tej funkcji uaktualnienie danych jest automatycznie stosowane po włączeniu funkcji we wszystkich osobach prawnych.</span><span class="sxs-lookup"><span data-stu-id="682e7-116">When this feature is activated, a data upgrade is automatically applied after the feature is turned on across all legal entities.</span></span>

<span data-ttu-id="682e7-117">Następnie włącz funkcję *Podziału pracy*, która jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="682e7-117">Next, turn on the *Work split* feature, which is listed in the following way:</span></span>

- <span data-ttu-id="682e7-118">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="682e7-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="682e7-119">**Nazwa funkcji:** *Podział pracy*</span><span class="sxs-lookup"><span data-stu-id="682e7-119">**Feature name:** *Work split*</span></span>

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a><span data-ttu-id="682e7-120">Ulepszenia szczegółów pracy i wszystkich stron pracy</span><span class="sxs-lookup"><span data-stu-id="682e7-120">Enhancements to the Work details and All work pages</span></span>

<span data-ttu-id="682e7-121">Funkcja *Podziału pracy* powoduje dodanie poniższych dwóch przycisków do karty **Praca** w okienku akcji na stronach **Szczegóły pracy** i **Cała praca**:</span><span class="sxs-lookup"><span data-stu-id="682e7-121">The *Work split* feature adds the following two buttons to the **Work** tab on the Action Pane of the **Work details** and **All work** pages:</span></span>

- <span data-ttu-id="682e7-122">**Podział pracy** — dzielenie bieżącej pracy o podanym identyfikatorze na wiele mniejszych prac, które mogą być wykonywane przez różnych pracowników.</span><span class="sxs-lookup"><span data-stu-id="682e7-122">**Split work** – Split the current work ID into multiple smaller work IDs that can be processed by separate workers.</span></span>
- <span data-ttu-id="682e7-123">**Anuluj sesję podziału pracy** — umożliwia anulowanie sesji podziału pracy i udostępnienie pracy do przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="682e7-123">**Cancel work split session** – Cancel the work split session, and make the work available for processing.</span></span>

<span data-ttu-id="682e7-124">![Przyciski sesji podziału pracy i anulowania podziału pracy](media/Work_split_buttons.png "Przyciski sesji podziału pracy i anulowania podziału pracy")</span><span class="sxs-lookup"><span data-stu-id="682e7-124">![Split work and Cancel work split session buttons](media/Work_split_buttons.png "Split work and Cancel work split session buttons")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="682e7-125">Przycisk **Podziału pracy** nie jest dostępny, jeśli spełniony jest dowolny z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="682e7-125">The **Split work** button won't be available if any of the following conditions are met:</span></span>
>
> - <span data-ttu-id="682e7-126">Stan pracy to coś innego niż *Otwarte* lub *W toku*.</span><span class="sxs-lookup"><span data-stu-id="682e7-126">The work status is something other than *Open* or *In progress*.</span></span>
> - <span data-ttu-id="682e7-127">Identyfikator kontenera jest skojarzony z identyfikatorem pracy.</span><span class="sxs-lookup"><span data-stu-id="682e7-127">A container ID is associated with the work ID.</span></span> <span data-ttu-id="682e7-128">(Kontener nie może być podzielony systematycznie, ponieważ wymaga fizycznego działania.)</span><span class="sxs-lookup"><span data-stu-id="682e7-128">(A container can't be systematically split, because it requires physical actions.)</span></span>
> - <span data-ttu-id="682e7-129">Praca jest skojarzona z klastrem.</span><span class="sxs-lookup"><span data-stu-id="682e7-129">The work is associated with a cluster.</span></span>
> - <span data-ttu-id="682e7-130">Typ zlecenia produkcyjnego ma wartość inną niż jeden z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="682e7-130">The work order type is something other than one of the following types:</span></span>
>
>    - <span data-ttu-id="682e7-131">Zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="682e7-131">Sales orders</span></span>
>    - <span data-ttu-id="682e7-132">Pobranie surowca</span><span class="sxs-lookup"><span data-stu-id="682e7-132">Raw material picking</span></span>
>    - <span data-ttu-id="682e7-133">Wydanie przeniesienia</span><span class="sxs-lookup"><span data-stu-id="682e7-133">Transfer issue</span></span>
>
> - <span data-ttu-id="682e7-134">Obecnie praca jest dzielona przez innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="682e7-134">The work is currently being split by another user.</span></span> <span data-ttu-id="682e7-135">W przypadku próby otwarcia strony podziału dla pracy, która jest już podzielona przez innego użytkownika, pojawia się następujący komunikat o błędzie: „Praca o identyfikatorze \#\#\#\# jest obecnie dzielona.</span><span class="sxs-lookup"><span data-stu-id="682e7-135">If you try to open the splitting page for work that is already being split by another user, you receive the following error message: "The work with ID \#\#\#\# is currently being split.</span></span> <span data-ttu-id="682e7-136">Spróbuj ponownie za kilka minut.</span><span class="sxs-lookup"><span data-stu-id="682e7-136">Retry in a few minutes.</span></span> <span data-ttu-id="682e7-137">Jeśli ten komunikat będzie nadal wyświetlany, skontaktuj się z kierownikiem”.</span><span class="sxs-lookup"><span data-stu-id="682e7-137">If you continue to receive this message, contact a supervisor."</span></span>

<span data-ttu-id="682e7-138">Nowa przyczyna blokowania pracy — *Podział pracy* wskazuje, kiedy identyfikator pracy jest w trakcie dzielenia.</span><span class="sxs-lookup"><span data-stu-id="682e7-138">A new work blocking reason, *Split work*, indicates when the work ID is in the process of being split.</span></span> <span data-ttu-id="682e7-139">Jest ona wyświetlana zarówno na stronie **Podziału pracy**, jak i w aplikacji Warehouse Management, jeśli użytkownik podejmie próbę uruchomienia pracy.</span><span class="sxs-lookup"><span data-stu-id="682e7-139">It's shown both on the **Split work** page and in the Warehouse Management mobile app if a user tries to run the work.</span></span> <span data-ttu-id="682e7-140">Jeśli są używane przyczyny blokowania, nazwa pola **Zablokowanej grupy czynności** w identyfikatorze pracy zostaje zmieniona na **Zablokowane**.</span><span class="sxs-lookup"><span data-stu-id="682e7-140">When blocking reasons are used, the name of the **Blocked wave** field from the work ID is changed to **Blocked**.</span></span>

## <a name="initiate-a-work-split"></a><span data-ttu-id="682e7-141">Inicjowanie podziału pracy</span><span class="sxs-lookup"><span data-stu-id="682e7-141">Initiate a work split</span></span>

<span data-ttu-id="682e7-142">Ta funkcja dodaje nową stronę **Podziału pracy**, która umożliwia użytkownikom podzielenie wierszy pracy od identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="682e7-142">The feature adds a new **Split work** page that lets users split work lines from the work ID.</span></span> <span data-ttu-id="682e7-143">Po pierwszym otwarciu strony wyświetlane są wiersze o stanie pracy *Otwarte* i dostępne do podziału.</span><span class="sxs-lookup"><span data-stu-id="682e7-143">When the page is first opened, it shows lines that have a work status of *Open* and that are available to be split.</span></span> <span data-ttu-id="682e7-144">W okienku akcji wybierz opcję **Podziel pracę**, aby przetworzyć wybraną pracę.</span><span class="sxs-lookup"><span data-stu-id="682e7-144">On the Action Pane, select **Split work** to process the selected work.</span></span>

<span data-ttu-id="682e7-145">Aby podzielić pracę, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="682e7-145">To split work, follow these steps.</span></span>

1. <span data-ttu-id="682e7-146">Otwórz jedną z następujących stron pracy:</span><span class="sxs-lookup"><span data-stu-id="682e7-146">Open one of the following work pages:</span></span>

    - <span data-ttu-id="682e7-147">**Szczegóły pracy** (**Zarządzanie magazynem \> Praca \> Szczegóły pracy**)</span><span class="sxs-lookup"><span data-stu-id="682e7-147">**Work details** (**Warehouse management \> Work \> Work details**)</span></span>
    - <span data-ttu-id="682e7-148">**Cała praca** (**Zarządzanie magazynem \> Praca \> Cała praca**)</span><span class="sxs-lookup"><span data-stu-id="682e7-148">**All work** (**Warehouse management \> Work \> All work**)</span></span>

1. <span data-ttu-id="682e7-149">W siatce wybierz identyfikator pracy, który ma zostać podzielony.</span><span class="sxs-lookup"><span data-stu-id="682e7-149">In the grid, select a work ID to split.</span></span> <span data-ttu-id="682e7-150">Dla pola **Typ zlecenia produkcyjnego** należy określić jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="682e7-150">The **Work order type** field must be set to one of the following values:</span></span>

    - <span data-ttu-id="682e7-151">Zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="682e7-151">Sales orders</span></span>
    - <span data-ttu-id="682e7-152">Pobranie surowca</span><span class="sxs-lookup"><span data-stu-id="682e7-152">Raw material picking</span></span>
    - <span data-ttu-id="682e7-153">Wydanie przeniesienia</span><span class="sxs-lookup"><span data-stu-id="682e7-153">Transfer issue</span></span>

1. <span data-ttu-id="682e7-154">W okienku akcji, na karcie **Praca**, w grupie **Praca** wybierz pozycję **Podział pracy**.</span><span class="sxs-lookup"><span data-stu-id="682e7-154">On the Action Pane, on the **Work** tab, in the **Work** group, select **Split work**.</span></span>

    <span data-ttu-id="682e7-155">Zostanie wyświetlona strona **Podział pracy** zawierająca wiersze pracy, które są otwarte i dostępne do podziału.</span><span class="sxs-lookup"><span data-stu-id="682e7-155">The **Split work** page appears and shows the work lines that are open and available to be split.</span></span> <span data-ttu-id="682e7-156">Domyślnie wyświetlane są tylko dostępne wiersze pracy.</span><span class="sxs-lookup"><span data-stu-id="682e7-156">By default, only available work lines are shown.</span></span> <span data-ttu-id="682e7-157">Aby wyświetlić wszystkie wiersze dla identyfikatora pracy (na przykład wiersze z typem pracy *Odłóż*), zaznacz pole wyboru **Pokaż wszystkie wiersze** nad siatką.</span><span class="sxs-lookup"><span data-stu-id="682e7-157">To view all lines for the work ID (for example, lines that have a work type of *Put*), select the **Show all lines** check box above the grid.</span></span>

    <span data-ttu-id="682e7-158">Pokazany jest następujący komunikat: „Użytkownicy nie mogą przetwarzać wierszy pracy, dopóki nie skończysz dzielenia i zamknięcia tej strony”.</span><span class="sxs-lookup"><span data-stu-id="682e7-158">The following message is shown: "Users can't process lines of the work until you finish splitting and close this page."</span></span>

    <span data-ttu-id="682e7-159">W polu **Przyczyna blokady pracy** dla bieżącej pracy zostanie ustawiona wartość *Podział pracy*, a praca zostanie zablokowana.</span><span class="sxs-lookup"><span data-stu-id="682e7-159">The **Work blocking reason** field for the current work will be set to *Split work*, and the work will be blocked.</span></span>

    <span data-ttu-id="682e7-160">![Przyczyna blokowania](media/Blocking_reason.png "Przyczyna blokowania")</span><span class="sxs-lookup"><span data-stu-id="682e7-160">![Blocking reason](media/Blocking_reason.png "Blocking reason")</span></span>

1. <span data-ttu-id="682e7-161">Wybierz wiersze, które mają zostać usunięte z bieżącego identyfikatora pracy i dodane do nowego identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="682e7-161">Select the lines to remove from the current work ID and add to a new work ID.</span></span> <span data-ttu-id="682e7-162">Występują wówczas następujące zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="682e7-162">The following events occur:</span></span>

    - <span data-ttu-id="682e7-163">Po podzieleniu pracy wybrane wiersze lub wiersze z oryginalnego identyfikatora pracy zostaną anulowane, a następnie skopiowane do nowego identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="682e7-163">When you split the work, the selected line or lines from the original work ID are canceled and then copied to a new work ID.</span></span>
    - <span data-ttu-id="682e7-164">Zachowana zostanie struktura szablonu pracy oraz lokalizacja funkcji odłożenia (a także przyszłych par pobranie/odłożenie).</span><span class="sxs-lookup"><span data-stu-id="682e7-164">The existing work template structure and the location of the put (and also future pick/put pairs) are preserved.</span></span> <span data-ttu-id="682e7-165">Wartości następujących pól identyfikatora pracy są kopiowane z oryginalnej pracy do nowej pracy:</span><span class="sxs-lookup"><span data-stu-id="682e7-165">Values for the following work ID fields are copied from the original work to the new work:</span></span>

        - <span data-ttu-id="682e7-166">Identyfikator ładunku</span><span class="sxs-lookup"><span data-stu-id="682e7-166">Load ID</span></span>
        - <span data-ttu-id="682e7-167">Identyfikator wysyłki</span><span class="sxs-lookup"><span data-stu-id="682e7-167">Shipment ID</span></span>
        - <span data-ttu-id="682e7-168">Typ zlecenia</span><span class="sxs-lookup"><span data-stu-id="682e7-168">Work order type</span></span>
        - <span data-ttu-id="682e7-169">Numer zamówienia</span><span class="sxs-lookup"><span data-stu-id="682e7-169">Order number</span></span>
        - <span data-ttu-id="682e7-170">Oddział</span><span class="sxs-lookup"><span data-stu-id="682e7-170">Site</span></span>
        - <span data-ttu-id="682e7-171">Magazyn</span><span class="sxs-lookup"><span data-stu-id="682e7-171">Warehouse</span></span>
        - <span data-ttu-id="682e7-172">Priorytet pracy</span><span class="sxs-lookup"><span data-stu-id="682e7-172">Work priority</span></span>
        - <span data-ttu-id="682e7-173">Identyfikator puli pracy</span><span class="sxs-lookup"><span data-stu-id="682e7-173">Work pool ID</span></span>
        - <span data-ttu-id="682e7-174">Identyfikator grupy czynności</span><span class="sxs-lookup"><span data-stu-id="682e7-174">Wave ID</span></span>
        - <span data-ttu-id="682e7-175">Identyfikator tworzenia pracy</span><span class="sxs-lookup"><span data-stu-id="682e7-175">Work creation number</span></span>

    - <span data-ttu-id="682e7-176">Następujące pola nie są kopiowane do nowego identyfikatora pracy:</span><span class="sxs-lookup"><span data-stu-id="682e7-176">The following fields aren't copied to the new work ID:</span></span>

        - <span data-ttu-id="682e7-177">**Identyfikator pracy** — nowy identyfikator pracy jest generowany na podstawie odpowiedniej sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="682e7-177">**Work ID** – A new work ID is generated from the appropriate number sequence.</span></span>
        - <span data-ttu-id="682e7-178">**Stan pracy** — to pole jest ustawione jako *Otwarte*.</span><span class="sxs-lookup"><span data-stu-id="682e7-178">**Work status** – This field is set to *Open*.</span></span>
        - <span data-ttu-id="682e7-179">**Zablokowane przez** — to pole jest początkowo ustawione jako puste.</span><span class="sxs-lookup"><span data-stu-id="682e7-179">**Locked by** – This field is initially set to blank.</span></span>
        - <span data-ttu-id="682e7-180">**Docelowy identyfikator numeru identyfikacyjnego** — to pole jest puste.</span><span class="sxs-lookup"><span data-stu-id="682e7-180">**Target license plate ID** – This field is left blank.</span></span>
        - <span data-ttu-id="682e7-181">**Data i godzina utworzenia** — to pole ma ustawioną bieżącą datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="682e7-181">**Created date and time** – This field is set to the current date and time.</span></span>
        - <span data-ttu-id="682e7-182">**Zablokowana grupa czynności/zamrożona** — to pole jest przeliczane dla oryginalnego identyfikatora pracy i nowego identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="682e7-182">**Blocked wave/frozen** – This field is recomputed for the original work ID and the new work ID.</span></span>

1. <span data-ttu-id="682e7-183">W okienku akcji wybierz **Podział pracy**.</span><span class="sxs-lookup"><span data-stu-id="682e7-183">On the Action Pane, select **Split work**.</span></span>

<span data-ttu-id="682e7-184">Podczas dzielenia pracy jest pokazywany następujący komunikat: „Operacja przetwarzania — podział pracy”.</span><span class="sxs-lookup"><span data-stu-id="682e7-184">While the work is being split, the following message is shown: "Processing operation - Split work".</span></span> <span data-ttu-id="682e7-185">Gdy ten komunikat jest widoczny, można anulować operację, klikając przycisk **Anuluj** w oknie komunikatu.</span><span class="sxs-lookup"><span data-stu-id="682e7-185">While this message is visible, you can cancel the operation by selecting **Cancel** in the message box.</span></span>

<span data-ttu-id="682e7-186">Jeśli pole wyboru **Pokaż wszystkie wiersze** jest wyczyszczone, wiersz, który został podzielony i anulowany, nie będzie już wyświetlany w siatce.</span><span class="sxs-lookup"><span data-stu-id="682e7-186">If the **Show all lines** check box is cleared, the line that was split off and canceled will no longer appear in the grid.</span></span> <span data-ttu-id="682e7-187">Jeśli to pole wyboru jest zaznaczone, należy sprawdzić, czy wartość w polu **Stan pracy** dla danego wiersza została zmieniona na *Anulowane*.</span><span class="sxs-lookup"><span data-stu-id="682e7-187">If the check box is selected, you should see that the value of the **Work status** field for that line has changed to *Canceled*.</span></span>

<span data-ttu-id="682e7-188">Pokazane jest następujące powiadomienie wskazujące, że utworzono identyfikator nowego zadania: „Praca \#\#\#\# została utworzona przez podzielenie od pracy oryginalnej \#\#\#\#”.</span><span class="sxs-lookup"><span data-stu-id="682e7-188">The following notification is shown to indicate that the new work ID has been created: "Work \#\#\#\# has been created by splitting off from original work \#\#\#\#."</span></span>

<span data-ttu-id="682e7-189">Inne wiersze pracy z oryginalnego identyfikatora pracy (np. wierszy *odłożenia*) będą korygowane zgodnie z potrzebami, aby odzwierciedlić wiersze pracy, które zostały anulowane.</span><span class="sxs-lookup"><span data-stu-id="682e7-189">Other work lines from the original work ID (such as *Put* lines) will be adjusted as required to reflect the lines of work that have been canceled.</span></span> <span data-ttu-id="682e7-190">Jeśli na przykład pierwotny identyfikator pracy ma wiersz *odłożenia* dla ilości 15, a wiersze *pobrania* o całkowitej ilości 10 zostały anulowane, nowa ilość w *odłożenia* oryginalnym identyfikatorze pracy będzie teraz równa 5.</span><span class="sxs-lookup"><span data-stu-id="682e7-190">For example, if the original work ID had a *Put* line for a quantity of 15, and *Pick* lines that have a total quantity of 10 were canceled, the new *Put* quantity on the original work ID will now be 5.</span></span>

<span data-ttu-id="682e7-191">Nowa praca nie zostanie natychmiast przypisana do żadnego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="682e7-191">The new work won't immediately be assigned to any user.</span></span> <span data-ttu-id="682e7-192">Można jednak przypisać ją do użytkownika teraz, zgodnie z potrzebą, za pomocą standardowych funkcji strony **Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="682e7-192">However, you can assign it to a user now, as required, by using the standard functionality of the **Work details** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="682e7-193">Można podzielić tylko te identyfikatory pracy, które zawierają co najmniej dwa dostępne wiersze pracy.</span><span class="sxs-lookup"><span data-stu-id="682e7-193">You can split only work IDs that contain two or more available work lines.</span></span> <span data-ttu-id="682e7-194">Jeśli wybrano tylko jeden wiersz pracy **Podział pracy**, zostanie wyświetlony następujący komunikat o błędzie: „Co najmniej jeden wiersz pracy musi pozostać w pracy początkowej”.</span><span class="sxs-lookup"><span data-stu-id="682e7-194">If you select **Split work** when there is only one work line, you will receive the following error message: "At least one work line must remain on initial work."</span></span> <span data-ttu-id="682e7-195">W takim przypadku podział nie zostanie wykonany.</span><span class="sxs-lookup"><span data-stu-id="682e7-195">In this case, no splitting will occur.</span></span>

## <a name="finish-a-work-split"></a><span data-ttu-id="682e7-196">Kończenie podziału pracy</span><span class="sxs-lookup"><span data-stu-id="682e7-196">Finish a work split</span></span>

<span data-ttu-id="682e7-197">Aby zakończyć pracę z podziałem, należy usunąć przyczynę blokady *Podziału pracy*.</span><span class="sxs-lookup"><span data-stu-id="682e7-197">To finish splitting work, the *Split work* blocking reason must be removed.</span></span> <span data-ttu-id="682e7-198">Istnieją dwa sposoby na zakończenie tego kroku:</span><span class="sxs-lookup"><span data-stu-id="682e7-198">There are two ways to complete this step:</span></span>

- <span data-ttu-id="682e7-199">Użytkownik, który dzieli pracę, zamyka stronę **Podziału pracy**, wybierając przycisk **Zamknij** (**X**) w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="682e7-199">The user who is splitting the work closes the **Split work** page by selecting the **Close** button (**X**) in the upper-right corner.</span></span> <span data-ttu-id="682e7-200">Gdy strona zostanie zamknięta, przyczyna blokady *Podziału pracy* zostanie usunięta.</span><span class="sxs-lookup"><span data-stu-id="682e7-200">When the page is closed, the *Split Work* blocking reason will be removed.</span></span> <span data-ttu-id="682e7-201">Stan *Zablokowane* tej pracy zostanie ponownie obliczony, jeśli nie pozostały żadne przyczyny blokowania tej pracy, praca zostanie odblokowana.</span><span class="sxs-lookup"><span data-stu-id="682e7-201">The *Blocked* state of this work will be recomputed and, if there are no remaining blocking reasons for this work, the work will be unblocked.</span></span>
- <span data-ttu-id="682e7-202">Każdy użytkownik otworzy identyfikator pracy i wybierze przycisk **Anuluj sesję podziału pracy** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="682e7-202">Any user opens the work ID and selects the **Cancel work split session** button on the Action Pane.</span></span> <span data-ttu-id="682e7-203">Przyczyna blokowania *Podziału pracy* zostanie usunięta, a stan *Zablokowane* dla tej pracy zostanie ponownie obliczony, tak jak w przypadku zamknięcia strony **Podziału pracy**.</span><span class="sxs-lookup"><span data-stu-id="682e7-203">The *Split work* blocking reason will be removed, and the *Blocked* state of this work will be recomputed, just as when the **Split work** page is closed.</span></span>

<span data-ttu-id="682e7-204">Po usunięciu przyczyny zablokowania *Podziału pracy* można uruchomić pracę na urządzeniu przenośnym, pod warunkiem, że w identyfikatorze pracy stan **Zablokowane** jest ustawiony wartość *Nie*.</span><span class="sxs-lookup"><span data-stu-id="682e7-204">After the *Split work* blocking reason is removed, the work can be run on the mobile device, provided that the **Blocked** state is set to *No* on the work ID.</span></span>

## <a name="user-blocking-on-the-warehouse-management-mobile-app"></a><span data-ttu-id="682e7-205">Blokowanie użytkowników w aplikacji mobilnej Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="682e7-205">User blocking on the Warehouse Management mobile app</span></span>

<span data-ttu-id="682e7-206">W przypadku użycia aplikacji Warehouse Management do uruchomienia pobierania pracy według identyfikatora pracy, pojawi się następujący komunikat o błędzie: „Praca o identyfikatorze \#\#\#\# jest obecnie dzielona”.</span><span class="sxs-lookup"><span data-stu-id="682e7-206">If you try to use the Warehouse Management mobile app to run picking work against a work ID that is being split, you will receive the following error message: "The work with ID \#\#\#\# is currently being split."</span></span> <span data-ttu-id="682e7-207">Jeśli zostanie wyświetlony ten komunikat, wybierz przycisk **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="682e7-207">If you receive this message, select **Cancel**.</span></span> <span data-ttu-id="682e7-208">Następnie można kontynuować przetwarzanie innej pracy.</span><span class="sxs-lookup"><span data-stu-id="682e7-208">You can then continue to process other work.</span></span>

## <a name="other-blocked-operations"></a><span data-ttu-id="682e7-209">Inne zablokowane operacje</span><span class="sxs-lookup"><span data-stu-id="682e7-209">Other blocked operations</span></span>

<span data-ttu-id="682e7-210">Wszystkie operacje, które modyfikują wiersze pracy, transakcje dotyczące magazynu pracy lub łącza uzupełniania związane z pracą, która jest podzielona, będą kończyć się niepowodzeniem i wyświetlany będzie następujący komunikat o błędzie: „Praca z identyfikatorem \#\#\#\# jest obecnie dzielona”.</span><span class="sxs-lookup"><span data-stu-id="682e7-210">Any operations that modify work lines, work inventory transactions, or replenishment links that are related to work that is being split will fail, and the following error message will be shown: "The work with ID \#\#\#\# is currently being split."</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]