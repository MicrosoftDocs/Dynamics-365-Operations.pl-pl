---
title: Zarządzanie naprawami
description: Warto systematycznie grupować problemy, tak aby ułatwić podpowiadanie rozwiązań, które wcześniej okazały się trafne.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d45732ff35069a64b37b6c53d9e22adf9a9a46d
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975615"
---
# <a name="repair-management"></a><span data-ttu-id="e89ab-103">Zarządzanie naprawami</span><span class="sxs-lookup"><span data-stu-id="e89ab-103">Repair management</span></span>       

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e89ab-104">W celu zarządzania naprawami można regularnie grupować problemy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-104">For repair management you can group problems systematically.</span></span> <span data-ttu-id="e89ab-105">Ułatwi to sugerowanie rozwiązań, które wcześniej okazały się trafne.</span><span class="sxs-lookup"><span data-stu-id="e89ab-105">This is to help with the suggestion of solutions that have been successful in the past.</span></span>

<span data-ttu-id="e89ab-106">Definiuje się ustawienia objawów, diagnozy i rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="e89ab-106">You set up symptoms, diagnosis, and resolution settings.</span></span> <span data-ttu-id="e89ab-107">Wszystkie te parametry można później zastosować, gdy otrzymasz podobny przedmiot do naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-107">All these can later be applied when you receive a similar item for repair.</span></span> <span data-ttu-id="e89ab-108">Można także skonfigurować etapy naprawy, aby ułatwić śledzenie postępów w procesie naprawiania.</span><span class="sxs-lookup"><span data-stu-id="e89ab-108">You can also set up repair stages that can follow the progress of a repair issue.</span></span>

## <a name="setting-up-repair-management"></a><span data-ttu-id="e89ab-109">Konfigurowanie zarządzania naprawami</span><span class="sxs-lookup"><span data-stu-id="e89ab-109">Setting up repair management</span></span>

<span data-ttu-id="e89ab-110">Następujące formularze ustawień służą do wprowadzania informacji, które będą służyć do określania objawów, diagnozy i sposobów rozwiązania dla napraw.</span><span class="sxs-lookup"><span data-stu-id="e89ab-110">Use the following setup forms to enter information that will be used to specify the symptoms, the diagnosis, and the resolution, of the repair.</span></span>

1.  <span data-ttu-id="e89ab-111">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Warunki**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-111">Click **Service management** \> **Setup** \> **Repair** \> **Conditions**.</span></span>

2.  <span data-ttu-id="e89ab-112">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Obszary objawów**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-112">Click **Service management** \> **Setup** \> **Repair** \> **Symptom areas**.</span></span>

3.  <span data-ttu-id="e89ab-113">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Obszary diagnoz**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-113">Click **Service management** \> **Setup** \> **Repair** \> **Diagnosis areas**.</span></span>

4.  <span data-ttu-id="e89ab-114">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Rozwiązania**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-114">Click **Service management** \> **Setup** \> **Repair** \> **Resolutions**.</span></span>

5.  <span data-ttu-id="e89ab-115">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Etapy napraw**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-115">Click **Service management** \> **Setup** \> **Repair** \> **Repair stages**.</span></span>

## <a name="symptoms-and-conditions"></a><span data-ttu-id="e89ab-116">Objawy i warunki</span><span class="sxs-lookup"><span data-stu-id="e89ab-116">Symptoms and conditions</span></span>

<span data-ttu-id="e89ab-117">Objawy to charakterystyka problemu przedstawiona przez klienta.</span><span class="sxs-lookup"><span data-stu-id="e89ab-117">Symptoms are how the customer characterizes the problem.</span></span> <span data-ttu-id="e89ab-118">Objawy obejmują spostrzeżenia klienta sugerujące konieczność naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-118">Symptoms include the customer observations that indicate the need for repair.</span></span>

<span data-ttu-id="e89ab-119">Można skonfigurować obszary objawów, kody objawów i warunki.</span><span class="sxs-lookup"><span data-stu-id="e89ab-119">You can set up symptom areas, symptom codes, and conditions.</span></span> <span data-ttu-id="e89ab-120">Obszar objawów dotyczy obszaru nieprawidłowego funkcjonowania, a kod objawu dotyczy objawu nieprawidłowego funkcjonowania.</span><span class="sxs-lookup"><span data-stu-id="e89ab-120">The symptom area covers the area of malfunction, and the symptom code covers the malfunction symptom.</span></span> <span data-ttu-id="e89ab-121">Warunek opisuje sytuację lub środowisko, jakie istnieje w momencie występowania problemu.</span><span class="sxs-lookup"><span data-stu-id="e89ab-121">The condition describes the situation or environment that is present when the problem occurs.</span></span>

<span data-ttu-id="e89ab-122">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="e89ab-122">**Example**</span></span>

<span data-ttu-id="e89ab-123">Do naprawy dostarczono komputer, ponieważ dysk twardy przestaje działać po dłuższym okresie pracy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-123">A computer is brought in for repair because the hard drive fails after an extended period of use.</span></span> <span data-ttu-id="e89ab-124">Awaria dysku twardego powoduje że błąd niebieskiego ekranu.</span><span class="sxs-lookup"><span data-stu-id="e89ab-124">The hard drive failure causes a blue screen error.</span></span> <span data-ttu-id="e89ab-125">Serwisant, który odbiera komputer, wprowadza następujące objawy i warunki:</span><span class="sxs-lookup"><span data-stu-id="e89ab-125">The technician who receives the computer enters the following symptoms and conditions:</span></span>

1.  <span data-ttu-id="e89ab-126">Obszarem objawów jest dysk twardy</span><span class="sxs-lookup"><span data-stu-id="e89ab-126">The symptom area is the hard drive</span></span>

2.  <span data-ttu-id="e89ab-127">Kodem objawu jest błąd niebieskiego ekranu</span><span class="sxs-lookup"><span data-stu-id="e89ab-127">The symptom code is the blue screen error</span></span>

3.  <span data-ttu-id="e89ab-128">Warunek mówi, że dysk twardy przestaje działać po dłuższym okresie pracy</span><span class="sxs-lookup"><span data-stu-id="e89ab-128">The condition is that the hard drive fails after extended use</span></span>

## <a name="diagnosis-and-resolutions"></a><span data-ttu-id="e89ab-129">Diagnostyka i rozwiązania</span><span class="sxs-lookup"><span data-stu-id="e89ab-129">Diagnosis and resolutions</span></span>

<span data-ttu-id="e89ab-130">Pola diagnostyki i rozwiązania stanowią raporty z przebiegu naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-130">The diagnosis and resolution fields are statements from the repair perspective.</span></span> <span data-ttu-id="e89ab-131">Są to etapy, przez które przechodził personel techniczny, starając się zdiagnozować problem.</span><span class="sxs-lookup"><span data-stu-id="e89ab-131">These are the steps that a technician went through to investigate the problem.</span></span>

<span data-ttu-id="e89ab-132">Obszar diagnoz określa operację, którą należy wykonać, aby rozwiązać problem.</span><span class="sxs-lookup"><span data-stu-id="e89ab-132">The diagnosis area covers the operation that must occur to solve the issue.</span></span> <span data-ttu-id="e89ab-133">Kod diagnozy określa sposób postępowania przy obsłudze problemu, a rozwiązaniem może być informacja o naprawieniu towaru, wymianie elementu lub wycofaniu zlecenia przez klienta.</span><span class="sxs-lookup"><span data-stu-id="e89ab-133">The diagnosis code is how the problem was handled, and the resolution could be that the item was repaired, replaced, or the order was canceled by the customer.</span></span> <span data-ttu-id="e89ab-134">Na przykład jeśli naprawiono komputer, to obszarem diagnozy może być informacja „uszkodzona część”, kodem diagnozy może być „zainstalowano nową kartę graficzną”, a rozwiązaniem byłoby stwierdzenie „wymieniono”.</span><span class="sxs-lookup"><span data-stu-id="e89ab-134">For example, if the computer is repaired, the diagnosis area could be "defective part," the diagnosis code could be "new video card installed," and the resolution could be "replaced."</span></span>

## <a name="repair-stages"></a><span data-ttu-id="e89ab-135">Etapy napraw</span><span class="sxs-lookup"><span data-stu-id="e89ab-135">Repair stages</span></span>

<span data-ttu-id="e89ab-136">Etapy napraw odnoszą się do postępu prac w procesie naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-136">Repair stages state the progress of the repair process.</span></span> <span data-ttu-id="e89ab-137">Etap napraw ma parametr zamykający **Zakończono**, który oznacza, że wiersz naprawy został ukończony oraz zarejestrowano datę i godzinę zakończenia.</span><span class="sxs-lookup"><span data-stu-id="e89ab-137">The repair stage has a **Finished** sign-off parameter that indicates that the repair line has been completed, and the finishing date and time has been recorded.</span></span>

## <a name="applying-repair-management"></a><span data-ttu-id="e89ab-138">Wdrożenie zarządzania naprawą</span><span class="sxs-lookup"><span data-stu-id="e89ab-138">Applying repair management</span></span>

<span data-ttu-id="e89ab-139">Aby zastosować zasady zarządzania naprawą w kontekście jakiegoś towaru, towar ten musi być skonfigurowany w taki sposób, aby istniała relacja przedmiotu serwisu ze zleceniem serwisowym.</span><span class="sxs-lookup"><span data-stu-id="e89ab-139">To apply repair management to an item, the item must be set up with a service object relation on a service order.</span></span> <span data-ttu-id="e89ab-140">Dopiero wtedy z poziomu zlecenia serwisowego można utworzyć wiersz naprawy z informacjami dotyczącymi bieżącego przypadku.</span><span class="sxs-lookup"><span data-stu-id="e89ab-140">From the service order you can then create a repair line with information about the current issue.</span></span> <span data-ttu-id="e89ab-141">W wierszu reperacji jest definiowany przedmiot serwisu podlegający reperacji, a także informacje o objawach, diagnozie i wykonaniu.</span><span class="sxs-lookup"><span data-stu-id="e89ab-141">On the repair line you define the service object that is in repair and information about symptoms, diagnosis, and execution.</span></span> <span data-ttu-id="e89ab-142">Można też sporządzić notatkę dla wiersza naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-142">You can also create a note for the repair line.</span></span>

<span data-ttu-id="e89ab-143">Wiersze naprawy można utworzyć dla każdego etapu procesu naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-143">You can create repair lines for each step in the repair process.</span></span>

## <a name="create-a-repair-line-on-a-service-order"></a><span data-ttu-id="e89ab-144">Tworzenie wiersza naprawy do zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="e89ab-144">Create a repair line on a service order</span></span>

1.  <span data-ttu-id="e89ab-145">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-145">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="e89ab-146">Wybierz zlecenie serwisowe z przedmiotem serwisu wymagającym naprawienia.</span><span class="sxs-lookup"><span data-stu-id="e89ab-146">Select the service order with the service object that needs repair.</span></span>

3.  <span data-ttu-id="e89ab-147">Kliknij kolejno opcje **Naprawa** \> **Wiersze naprawy**, aby otworzyć formularz **Wiersze naprawy**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-147">Click **Repair** \> **Repair lines** to open the **Repair lines** form.</span></span>

4.  <span data-ttu-id="e89ab-148">Naciśnij klawisze CTRL+N, aby utworzyć nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="e89ab-148">Press CTRL+N to create a new line.</span></span>

5.  <span data-ttu-id="e89ab-149">Wybierz przedmiot serwisu.</span><span class="sxs-lookup"><span data-stu-id="e89ab-149">Select a service object.</span></span> <span data-ttu-id="e89ab-150">Można wybrać dowolny przedmiot serwisu, dla którego skonfigurowano relację obiektu do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e89ab-150">You can select any service object that has been set up with an object relation on the service order.</span></span>

6.  <span data-ttu-id="e89ab-151">Wybierz te predefiniowane objawy, diagnozy lub wartości wykonania, które są odpowiednie w wypadku danego wiersza naprawy, a następnie w razie potrzeby kliknij kartę **Notatka**, aby utworzyć notatkę do wiersza naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-151">Select any of the preset symptoms, diagnosis, and execution values that are relevant in the repair line and then click the **Note** tab to create a note on the repair line, if needed.</span></span>

7.  <span data-ttu-id="e89ab-152">Naciśnij klawisze CTRL+S, aby zapisać nowy wiersz naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-152">Press CTRL+S to save the new repair line.</span></span> <span data-ttu-id="e89ab-153">Pole **Data i godzina utworzenia** na karcie **Ogólne** w formularzu **Wiersze naprawy** zostanie zaktualizowane o godzinę zapisania.</span><span class="sxs-lookup"><span data-stu-id="e89ab-153">The **Created date and time** field in the **General** tab of the **Repair lines** form is updated with the time of saving.</span></span>

## <a name="tracking-progress-and-resolving-a-repair-issue"></a><span data-ttu-id="e89ab-154">Śledzenie postępu i rozwiązywanie problemu</span><span class="sxs-lookup"><span data-stu-id="e89ab-154">Tracking progress and resolving a repair issue</span></span>

<span data-ttu-id="e89ab-155">Dla wiersza naprawy można definiować etapy naprawy, aby śledzić postęp naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-155">You can set the repair stages of a repair line to track the progress of the repair.</span></span>

<span data-ttu-id="e89ab-156">Po rozwiązaniu problemu można zamknąć wiersz naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-156">When a repair issue is resolved, you can close the repair line.</span></span> <span data-ttu-id="e89ab-157">Ustaw etap naprawy z włączoną właściwością **Zakończono**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-157">Set the repair stage to a stage with a **Finished** property enabled.</span></span> <span data-ttu-id="e89ab-158">Jako czas zakończenia w wierszu zostanie zarejestrowana aktualna data i godzina.</span><span class="sxs-lookup"><span data-stu-id="e89ab-158">The current date and time is registered as the finish time on the line.</span></span>

## <a name="close-a-repair-line-for-a-resolved-issue"></a><span data-ttu-id="e89ab-159">Zamykanie wiersza naprawy dla rozwiązanej sprawy</span><span class="sxs-lookup"><span data-stu-id="e89ab-159">Close a repair line for a resolved issue</span></span>

1.  <span data-ttu-id="e89ab-160">Otwórz formularz **Wiersze naprawy**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-160">Open the **Repair lines** form.</span></span> <span data-ttu-id="e89ab-161">Postępując zgodnie z przedstawioną wcześniej procedurą, utwórz wiersz naprawy.</span><span class="sxs-lookup"><span data-stu-id="e89ab-161">Follow the procedure earlier in this topic to create a repair line.</span></span>

2.  <span data-ttu-id="e89ab-162">Wybierz wiersz naprawy ze sprawą naprawy, która ma zostać zamknięta.</span><span class="sxs-lookup"><span data-stu-id="e89ab-162">Select the repair line with the repair issue that you want to close.</span></span>

3.  <span data-ttu-id="e89ab-163">W polu **Etap naprawy** wybierz etap z włączoną właściwością **Zakończono**.</span><span class="sxs-lookup"><span data-stu-id="e89ab-163">In the **Repair stage** field, select a stage with the **Finished** property enabled.</span></span>

  


