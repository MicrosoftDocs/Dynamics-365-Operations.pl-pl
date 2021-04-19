---
title: Tworzenie zlecenia pracy
description: W tym temacie opisano tworzenie zleceń pracy w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 3982232e5008d6f8c283d6cecfaf2fa6e66150a1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836741"
---
# <a name="creating-work-orders"></a><span data-ttu-id="0cb13-103">Tworzenie zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="0cb13-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0cb13-104">Po zaplanowaniu zadań konserwacji zapobiegawczej następnym krokiem jest utworzenie dla nich zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="0cb13-104">After you've scheduled preventive maintenance jobs, the next step is to create work orders for them.</span></span> <span data-ttu-id="0cb13-105">Ten krok można wykonać, korzystając z jednego z harmonogramów konserwacji.</span><span class="sxs-lookup"><span data-stu-id="0cb13-105">You can complete this step by using one of the maintenance schedules.</span></span> <span data-ttu-id="0cb13-106">Zaplanowane zadania w harmonogramie konserwacji mogą mieć różne typy odwołań, jak opisano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="0cb13-106">The scheduled jobs in a maintenance schedule can have different reference types, as described in the following table.</span></span>

| <span data-ttu-id="0cb13-107">Typ odwołania</span><span class="sxs-lookup"><span data-stu-id="0cb13-107">Reference type</span></span> | <span data-ttu-id="0cb13-108">opis</span><span class="sxs-lookup"><span data-stu-id="0cb13-108">Description</span></span> |
|---|---|
| <span data-ttu-id="0cb13-109">Plany konserwacji</span><span class="sxs-lookup"><span data-stu-id="0cb13-109">Maintenance plans</span></span> | <span data-ttu-id="0cb13-110">Zadania konserwacji zapobiegawczej oparte na planie konserwacji typu *Czas* lub *Licznik*.</span><span class="sxs-lookup"><span data-stu-id="0cb13-110">Preventive maintenance jobs that are based on the *Time* or *Counter* maintenance plan type.</span></span> |
| <span data-ttu-id="0cb13-111">Serie czynności konserwacyjnych</span><span class="sxs-lookup"><span data-stu-id="0cb13-111">Maintenance rounds</span></span> | <span data-ttu-id="0cb13-112">Zadania profilaktycznej obsługi technicznej, które zawierają kilka składników majątku, które wymagają podobnego typu obsługi.</span><span class="sxs-lookup"><span data-stu-id="0cb13-112">Preventive maintenance jobs that contain several assets that require a similar type of maintenance.</span></span> |
| <span data-ttu-id="0cb13-113">Żądanie konserwacji</span><span class="sxs-lookup"><span data-stu-id="0cb13-113">Maintenance request</span></span> | <span data-ttu-id="0cb13-114">Ręcznie utworzone żądanie konserwacji lub naprawy składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="0cb13-114">A manually created request for maintenance or repair of an asset.</span></span> <span data-ttu-id="0cb13-115">To żądanie można przekonwertować na zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="0cb13-115">This request can be converted to a work order.</span></span> |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a><span data-ttu-id="0cb13-116">Tworzenie zleceń pracy na podstawie harmonogramu konserwacji</span><span class="sxs-lookup"><span data-stu-id="0cb13-116">Create work orders based on your maintenance schedule</span></span>

<span data-ttu-id="0cb13-117">Aby utworzyć zlecenia pracy na podstawie harmonogramu konserwacji, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0cb13-117">To create work orders that are based on your maintenance schedule, follow these steps.</span></span>

1. <span data-ttu-id="0cb13-118">Otwórz jedną z następujących stron w zależności od sposobu wybierania pozycji planowania dla zleceń pracy:</span><span class="sxs-lookup"><span data-stu-id="0cb13-118">Open one of the following pages, depending on how you want to select schedule items for your work orders:</span></span>

    - <span data-ttu-id="0cb13-119">Wszystkie harmonogramy konserwacji (**Zarządzanie składnikami majątku \> Harmonogram zarządzania \> Wszystkie harmonogramy konserwacji)**</span><span class="sxs-lookup"><span data-stu-id="0cb13-119">All maintenance schedule (**Asset management \> Management schedule \> All maintenance schedule**)</span></span>
    - <span data-ttu-id="0cb13-120">Otwarte wiersze harmonogramu konserwacji (**Zarządzanie składnikami majątku \> Harmonogram zarządzania \> Otwarte wiersze harmonogramu konserwacji)**</span><span class="sxs-lookup"><span data-stu-id="0cb13-120">Open maintenance schedule lines (**Asset management \> Management schedule \> Open maintenance schedule lines**)</span></span>
    - <span data-ttu-id="0cb13-121">Otwarte pule harmonogramu konserwacji (**Zarządzanie składnikami majątku \> Harmonogram zarządzania \> Otwarte pule harmonogramu konserwacji)**</span><span class="sxs-lookup"><span data-stu-id="0cb13-121">Open maintenance schedule pools (**Asset management \> Management schedule \> Open maintenance schedule pools**)</span></span>

1. <span data-ttu-id="0cb13-122">W siatce zaznacz pole wyboru przy każdym zaplanowanym zadaniu konserwacji, dla którego chcesz utworzyć zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="0cb13-122">In the grid, select the check box for every scheduled maintenance job that you want to create a work order for.</span></span> <span data-ttu-id="0cb13-123">Następnie w okienku akcji wybierz opcję **Zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="0cb13-123">Then, on the Action Pane, select **Work order**.</span></span>

    <span data-ttu-id="0cb13-124">Zostanie wyświetlone okno dialogowe **Tworzenie zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="0cb13-124">The **Create work orders** dialog box appears.</span></span> <span data-ttu-id="0cb13-125">W polu **Godziny prognozy konserwacji** zostanie wyświetlona liczba godzin prognozowanych dla wybranych wierszy.</span><span class="sxs-lookup"><span data-stu-id="0cb13-125">The **Maintenance forecast hours** field shows the total number of forecast hours for the selected lines.</span></span>

    ![Okno dialogowe Tworzenie zleceń pracy](media/18-preventive-maintenance.png)

1. <span data-ttu-id="0cb13-127">W sekcji **Parametry** określ liczbę zleceń pracy, które mają zostać utworzone.</span><span class="sxs-lookup"><span data-stu-id="0cb13-127">In the **Parameters** section, specify the number of work orders that should be created.</span></span> <span data-ttu-id="0cb13-128">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="0cb13-128">Select one of the following options:</span></span>

    - <span data-ttu-id="0cb13-129">**Jedno zlecenie pracy na wiersz** — należy utworzyć jedno zlecenie pracy na wiersz harmonogramu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="0cb13-129">**One work order per line** – Create one work order per maintenance schedule line.</span></span>
    - <span data-ttu-id="0cb13-130">**Jedno zlecenie na** — należy utworzyć zlecenia pracy pogrupowane zgodnie z ustawieniami innych opcji, które stają się dostępne po wybraniu tej opcji.</span><span class="sxs-lookup"><span data-stu-id="0cb13-130">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="0cb13-131">W polu **Typ zlecenia pracy** wybierz typ zlecenia, który będzie używany dla wszystkich tworzonych zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="0cb13-131">In the **Work order type** field, select the work order type to use for all the work orders that you create.</span></span>
1. <span data-ttu-id="0cb13-132">Wybierz przycisk **OK**, aby utworzyć zlecenia zgodnie z ustawieniami.</span><span class="sxs-lookup"><span data-stu-id="0cb13-132">Select **OK** to create the work orders according to your settings.</span></span>

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a><span data-ttu-id="0cb13-133">Grupowanie wierszy zlecenia pracy tworzonych automatycznie podczas planowania konserwacji</span><span class="sxs-lookup"><span data-stu-id="0cb13-133">Group work order lines that are automatically created while a maintenance plan runs</span></span>

<span data-ttu-id="0cb13-134">Ta funkcja umożliwia definiowanie reguł grupowania wierszy zleceń pracy w ramach pojedynczego zlecenia, gdy system jest tak ustawiony, aby generował zlecenia pracy automatycznie na podstawie planu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="0cb13-134">This feature lets you define rules for grouping work order lines under a single work order when the system is set up to generate work orders automatically, based on a maintenance plan.</span></span> <span data-ttu-id="0cb13-135">Wcześniej generowane automatycznie zlecenia pracy mogły zawierać tylko jeden wiersz.</span><span class="sxs-lookup"><span data-stu-id="0cb13-135">Previously, automatically generated work orders could contain only one line.</span></span> <span data-ttu-id="0cb13-136">Teraz jednak można grupować zlecenia według na przykład składnika majątku, typu składnika majątku lub lokalizacji czynności.</span><span class="sxs-lookup"><span data-stu-id="0cb13-136">However, you can now group work orders by, for example, asset, asset type, or functional location.</span></span> <span data-ttu-id="0cb13-137">(Ręcznie wygenerowane zlecenia pracy można już grupować w ten sposób, zgodnie z opisem w poprzedniej sekcji tego tematu).</span><span class="sxs-lookup"><span data-stu-id="0cb13-137">(Manually generated work orders could already be grouped in this way, as described in the previous section of this topic.)</span></span>

### <a name="enable-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="0cb13-138">Włącz grupowanie dla automatycznie generowanych zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="0cb13-138">Enable grouping for automatically generated work orders</span></span>

<span data-ttu-id="0cb13-139">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="0cb13-139">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="0cb13-140">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją.</span><span class="sxs-lookup"><span data-stu-id="0cb13-140">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="0cb13-141">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="0cb13-141">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="0cb13-142">**Moduł:** *Zarządzanie składnikami majątku*</span><span class="sxs-lookup"><span data-stu-id="0cb13-142">**Module:** *Asset Management*</span></span>
- <span data-ttu-id="0cb13-143">**Nazwa funkcji:** *Stosowanie reguł grupowania zleceń pracy podczas uruchamiania planu konserwacji*</span><span class="sxs-lookup"><span data-stu-id="0cb13-143">**Feature name:** *Apply rules for grouping work orders while running a maintenance plan*</span></span>

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="0cb13-144">Konfiguruj grupowanie dla automatycznie generowanych zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="0cb13-144">Set up grouping for automatically generated work orders</span></span>

<span data-ttu-id="0cb13-145">Aby skonfigurować grupowanie dla automatycznie generowanych zleceń pracy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0cb13-145">To set up grouping for automatically generated work orders, follow these steps.</span></span>

1. <span data-ttu-id="0cb13-146">Przejdź do obszaru **Zarządzanie składnikami majątku \> Ustawienia \> Konserwacja zapobiegawcza \> Plany konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="0cb13-146">Go to **Asset management \> Setup \> Preventative maintenance \> Maintenance plans**.</span></span>
1. <span data-ttu-id="0cb13-147">Dla każdego planu, w którym mają być generowane pogrupowane zlecenia pracy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="0cb13-147">For each plan where you want to generate grouped work orders, follow these steps:</span></span>

    1. <span data-ttu-id="0cb13-148">Wybierz plan w okienku listy.</span><span class="sxs-lookup"><span data-stu-id="0cb13-148">Select the plan in the list pane.</span></span>
    1. <span data-ttu-id="0cb13-149">Upewnij się, że na skróconej karcie **Wiersze** jest zaznaczone pole wyboru **Automatycznie utwórz** w każdym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0cb13-149">On the **Lines** FastTab, make sure that the **Auto create** check box is selected on every line.</span></span>

1. <span data-ttu-id="0cb13-150">Przejdź do obszaru **Zarządzanie składnikami majątku \> Okresowe \> Konserwacja zapobiegawcza \> Planowanie planów konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="0cb13-150">Go to **Asset management \> Periodic \> Preventive maintenance \> Schedule maintenance plans**.</span></span>
1. <span data-ttu-id="0cb13-151">W oknie dialogowym **Planowanie planów konserwacji** w sekcji **Okres** określ horyzont czasowy planu (jak daleko w przyszłości będą wyszukiwane zaplanowane zadania konserwacji, dla których mają zostać wygenerowane prace).</span><span class="sxs-lookup"><span data-stu-id="0cb13-151">In the **Schedule maintenance plans** dialog box, in the **Period** section, specify the time horizon for the plan (how far to look ahead when finding scheduled maintenance jobs to generate work for).</span></span>
1. <span data-ttu-id="0cb13-152">Ustaw opcję **Automatycznie utwórz zlecenie pracy z harmonogramu** na *Tak*.</span><span class="sxs-lookup"><span data-stu-id="0cb13-152">Set the **Automatically create work order from schedule** option to *Yes*.</span></span>
1. <span data-ttu-id="0cb13-153">W sekcji **Zlecenie pracy** wybierz jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="0cb13-153">In the **Work order** section, select one of the following options:</span></span>

    - <span data-ttu-id="0cb13-154">**Jedno zlecenie pracy na wiersz** — należy utworzyć jedno zlecenie pracy na wiersz harmonogramu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="0cb13-154">**One work order per line** – Create one work order per maintenance schedule line.</span></span> <span data-ttu-id="0cb13-155">(Ta opcja udostępnia te same funkcje, które są dostępne, gdy funkcja *Stosowanie reguł grupowania zleceń pracy podczas uruchamiania planu konserwacji* jest wyłączona).</span><span class="sxs-lookup"><span data-stu-id="0cb13-155">(This option provides the same functionality that is available when the *Apply rules for grouping work orders while running a maintenance plan* feature is turned off.)</span></span>
    - <span data-ttu-id="0cb13-156">**Jedno zlecenie na** — należy utworzyć zlecenia pracy pogrupowane zgodnie z ustawieniami innych opcji, które stają się dostępne po wybraniu tej opcji.</span><span class="sxs-lookup"><span data-stu-id="0cb13-156">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="0cb13-157">Jeśli chcesz, aby opcje były stosowane podczas uruchamiania tylko niektórych planów konserwacji, na skróconej karcie **Rekordy do uwzględnienia** dodaj filtry zgodnie z potrzebami, tak jak w przypadku innych zadań wsadowych w aplikacji Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0cb13-157">If you want the options to apply when you run only some of your maintenance plans, on the **Records to include** FastTab, add filters as you require, just as you might do for other batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="0cb13-158">Na skróconej karcie **Uruchom w tle** skonfiguruj wymagane opcje przetwarzania wsadowego i planowania, tak jak w przypadku innych zadań wsadowych w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0cb13-158">On the **Run in the background** FastTab, set up batch and scheduling options as you require, just as you might do for other batch jobs in Supply Chain Management.</span></span>
1. <span data-ttu-id="0cb13-159">Wybierz przycisk **OK**, aby uruchomić i/lub zaplanować wybrane plany konserwacji.</span><span class="sxs-lookup"><span data-stu-id="0cb13-159">Select **OK** to run and/or schedule the selected maintenance plans.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]