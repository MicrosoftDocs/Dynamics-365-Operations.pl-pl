---
title: Utwórz żądania konserwacji
description: W tym temacie wyjaśniono, jak utworzyć żądanie konserwacji w zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f45378405d9ea06ae847d93b7eacd9badf6d7e00
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019185"
---
# <a name="create-maintenance-requests"></a><span data-ttu-id="1e1b1-103">Utwórz żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="1e1b1-103">Create maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="1e1b1-104">Żądania konserwacji mogą być używane, jeśli pracownicy zajmujący się konserwacją lub pracownicy produkcyjni odkrywają, że sprzęt wymaga naprawy, ale nie można wykonać zadania naprawy od razu.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-104">Maintenance requests can be used if maintenance workers or production workers discover that equipment requires repair, but the repair job can't be done right away.</span></span>

<span data-ttu-id="1e1b1-105">**Przykład:** gdy konserwator robi naprawę, odkrywa, że inny składnik majątku w tej samej lokalizacji musi być serwisowany.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-105">**Example:** While a maintenance worker is making a repair, she discovers that another asset at the same location must be serviced.</span></span> <span data-ttu-id="1e1b1-106">Konserwator nie ma jednak czasu ani wymaganych części zamiennych do wykonania naprawy.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-106">However, the maintenance worker doesn't have the time or the required spare parts to do the repair job.</span></span> <span data-ttu-id="1e1b1-107">W związku z tym tworzy żądanie konserwacji składnika majątku i wprowadza krótki opis problemu.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-107">Therefore, she creates a maintenance request on the asset and enters a short description of the issue.</span></span>

<span data-ttu-id="1e1b1-108">Sekcja **Aktywne żądania konserwacji** w okienku **Powiązane informacje** po prawej stronie strony **Wszystkie składniki majątku** lub **Aktywne składniki majątku** (**Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku** lub **Aktywne składniki majątku**) zawiera aktywne żądania konserwacji, które są dołączone do wybranego składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-108">The **Active maintenance requests** section of the **Related information** pane on the right side of the **All assets** or **Active assets** page (**Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**) shows the active maintenance requests that are attached to the selected asset.</span></span>

1. <span data-ttu-id="1e1b1-109">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="1e1b1-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-110">Select **New**.</span></span>
3. <span data-ttu-id="1e1b1-111">W oknie dialogowym **Tworzenie żądania** w polu **Typ żądania konserwacji** wybierz typ żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-111">In the **Create request** dialog box, in the **Maintenance request type** field, select the type of maintenance request.</span></span> <span data-ttu-id="1e1b1-112">Sugerowany jest domyślny typ.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-112">A default type is suggested.</span></span>
4. <span data-ttu-id="1e1b1-113">W polu **opis** wprowadź nazwę lub tytuł, który krótko opisuje żądanie konserwacji.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-113">In the **Description** field, enter a name or title that briefly describes the maintenance request.</span></span>
5. <span data-ttu-id="1e1b1-114">W polach **lokalizacja** i **składnik majątku** wybierz pozycję Lokalizacja czynności konserwacyjnych lub składnik majątku lub kombinację lokalizacji czynności konserwacyjnych i składnika majątku, zgodnie z Twoimi potrzebami.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-114">In the **Functional location** and **Asset** fields, select a functional location or an asset, or a combination of a functional location and an asset, as you require.</span></span> <span data-ttu-id="1e1b1-115">Można utworzyć żądanie konserwacji bez wybierania składnika majątku i można później dodać składnik majątku do żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-115">You can create a maintenance request without selecting an asset, and the asset can be added to the maintenance request later.</span></span> <span data-ttu-id="1e1b1-116">Jeśli konserwator, który jest zalogowany i jest powiązany z zasobem powiązanym ze składnikiem majątku, pole **Składnik majątku** jest automatycznie ustawiane.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-116">If the maintenance worker who is signed in is related to a resource that is related to an asset, the **Asset** field is automatically set.</span></span>

    <span data-ttu-id="1e1b1-117">Jeśli żądanie konserwacji jest już dołączone do wybranego składnika majątku, na górze okna dialogowego **Utwórz żądanie** pojawi się pasek komunikatów informujący o identyfikatorze istniejącego żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-117">If a maintenance request is already attached to the selected asset, a message bar appears at the top of the **Create request** dialog box to notify you about the ID of the existing maintenance request.</span></span> <span data-ttu-id="1e1b1-118">Pasek komunikatów powiadamia również o tym, czy składnik majątku jest objęty umową gwarancyjną.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-118">A message bar also notifies you if the asset is covered by a warranty agreement.</span></span>

6. <span data-ttu-id="1e1b1-119">W polu **poziom usługi** wybierz poziom usługi wskazujący pilność żądania.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-119">In the **Service level** field, select a service level that indicates the urgency of the request.</span></span>
7. <span data-ttu-id="1e1b1-120">Jeśli wybrano składnik majątku w kroku 5, można użyć **symptomów usterek**, **obszaru błędów** i **Typu usterki**, aby utworzyć rejestrację błędów.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-120">If you selected an asset in step 5, you can use the **Fault symptom**, **Fault area**, and **Fault type** fields to create a fault registration.</span></span>
8. <span data-ttu-id="1e1b1-121">Jeśli żądanie konserwacji spowodowało przerwę konserwacyjną, wprowadź datę rozpoczęcia i czas przerwy.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-121">If the maintenance request has caused maintenance downtime, enter the start date and time of the downtime.</span></span>

    <span data-ttu-id="1e1b1-122">Pole **rozpoczęte przez** jest automatycznie ustawiane jako Twoja nazwa użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-122">The **Started by** field is automatically set to your name.</span></span>

10. <span data-ttu-id="1e1b1-123">W polu **Rzeczywisty początek** zostanie automatycznie ustawiona bieżąca data i godzina.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-123">The **Actual start** field is automatically set to the current date and time.</span></span> <span data-ttu-id="1e1b1-124">Można jednak zmienić jego wartość.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-124">However, you can change the value as you require.</span></span>
11. <span data-ttu-id="1e1b1-125">W polu **notatki** wprowadź wszelkie dodatkowe notatki, które są wymagane.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-125">In the **Notes** field, enter any additional notes that are required.</span></span>
12. <span data-ttu-id="1e1b1-126">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-126">Select **OK**.</span></span>

![Utwórz żądanie konserwacji](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a><span data-ttu-id="1e1b1-128">Późniejsze przetwarzanie żądań konserwacji</span><span class="sxs-lookup"><span data-stu-id="1e1b1-128">Subsequent processing of maintenance requests</span></span>

<span data-ttu-id="1e1b1-129">Po utworzeniu żądania konserwacji, ale zanim zostanie przekonwertowane na zlecenie pracy, konieczne jest zaktualizowanie różnych informacji.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-129">After a maintenance request is created, but before it's converted to a work order, various information should be updated on it.</span></span> <span data-ttu-id="1e1b1-130">Zwykle planista lub inny pracownik administracyjny wykonuje to zadanie.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-130">Typically, a planner or another administrative employee completes this task.</span></span>

- <span data-ttu-id="1e1b1-131">Na stronie **wszystkie żądania konserwacji** lub **aktywne żądania konserwacji** wybierz żądanie do obsługi, a następnie wybierz pozycję **Edytuj.**</span><span class="sxs-lookup"><span data-stu-id="1e1b1-131">On the **All maintenance requests** or **Active maintenance requests** page, select the request to work with, and then select **Edit**.</span></span>

<span data-ttu-id="1e1b1-132">W widoku szczegółów można aktualizować różne informacje.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-132">In the details view, you can update various information.</span></span> <span data-ttu-id="1e1b1-133">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="1e1b1-133">Here are some examples:</span></span>

- <span data-ttu-id="1e1b1-134">Wybierz i zweryfikuj składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-134">Select and verify the asset.</span></span> <span data-ttu-id="1e1b1-135">Jeśli musisz wybrać inny składnik majątku później, możesz ustawić opcję **zweryfikowany składnik majątku** jako **nie.**</span><span class="sxs-lookup"><span data-stu-id="1e1b1-135">If you must select a different asset later, you can set the **Asset verified** option to **No**.</span></span>
- <span data-ttu-id="1e1b1-136">Wybierz odpowiedzialną grupę konserwatorów i/lub odpowiedzialnego konserwatora.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-136">Select a responsible maintenance worker group and/or a responsible maintenance worker.</span></span> <span data-ttu-id="1e1b1-137">Aby uzyskać więcej informacji o wymaganej konfiguracji, zobacz [odpowiedzialni konserwatorzy](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="1e1b1-137">For more information about the required setup, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>
- <span data-ttu-id="1e1b1-138">Wybierz typ zadania konserwacji i, jeśli te informacje są istotne, wariant zadania konserwacji i profesję zadania.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-138">Select a maintenance job type and, if this information is relevant, a related maintenance job variant and a job trade.</span></span>
- <span data-ttu-id="1e1b1-139">W polach **szerokość** i **długość** geograficzna wprowadź współrzędne geograficzne.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-139">In the **Latitude** and **Longitude** fields, enter geographic coordinates.</span></span> <span data-ttu-id="1e1b1-140">Wszystkie współrzędne, które są dodawane do żądania konserwacji są automatycznie przenoszone do powiązanego zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-140">Any coordinates that are added to a maintenance request are automatically transferred to a related work order.</span></span> 

![Aktualizuj żądanie konserwacji](media/04-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="1e1b1-142">Jeśli wybierzesz składnik majątku podczas tworzenia żądania konserwacji, można dodać jeden błąd do zasobu.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-142">If you select an asset when you create a maintenance request, you can add one fault to the asset.</span></span> <span data-ttu-id="1e1b1-143">Po utworzeniu żądania konserwacji można dodać więcej błędów, zgodnie z żądaniem.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-143">After the maintenance request has been created, you can add more faults, as you require.</span></span> <span data-ttu-id="1e1b1-144">Aby dodać błędy, wybierz opcję **błąd składnika majątku** na stronie **wszystkie żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="1e1b1-144">To add faults, select **Asset fault** on the **All maintenance requests** page.</span></span>
