---
title: Rejestrator zadań i Pomoc dla aplikacji Retail Modern POS (MPOS) i Cloud POS
description: W tym temacie opisano, jak korzystać z Rejestratora zadań w programach Retail Modern POS (MPOS) i Cloud POS.
author: mugunthanm
manager: AnnBe
ms.date: 06/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable, SystemParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 1205393
ms.assetid: 2f13e9cf-55b5-458b-8c32-3f8cd98c9ecf
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0ab8456d81fbe2dca495b65b932395572242a25c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415002"
---
# <a name="task-recorder-and-help-for-retail-modern-pos-mpos-and-cloud-pos"></a><span data-ttu-id="a5d5b-103">Rejestrator zadań i Pomoc dla aplikacji Retail Modern POS (MPOS) i Cloud POS</span><span class="sxs-lookup"><span data-stu-id="a5d5b-103">Task recorder and Help for Retail Modern POS (MPOS) and Cloud POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a5d5b-104">W tym temacie opisano, jak korzystać z Rejestratora zadań w programach Retail Modern POS (MPOS) i Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-104">This topic describes how to use Task recorder in Retail Modern POS and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="a5d5b-105">Przegląd</span><span class="sxs-lookup"><span data-stu-id="a5d5b-105">Overview</span></span>

<span data-ttu-id="a5d5b-106">Rejestrator zadań w programie Retail Modern POS lub Cloud POS jest to nowe rozwiązanie, utworzone z myślą o krótkim czasie reakcji.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-106">Task recorder in Retail Modern POS or Cloud POS is a new solution that was built with a focus on high responsiveness.</span></span> <span data-ttu-id="a5d5b-107">Zawiera elastyczny interfejs programowania aplikacji (API) umożliwiający rozszerzenie i bezproblemową integrację z użytkownikami zapisów procesu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-107">It provides a flexible application programming interface (API) for extensibility and seamless integration with consumers of business process recordings.</span></span> <span data-ttu-id="a5d5b-108">Ponadto integracja Rejestratora zadań z narzędziem do modelowania procesów biznesowych (BPM) w usługach Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) została wyeksponowana.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-108">Additionally, Task recorder integration with the Business process modeler (BPM) tool on Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) has been brought forward.</span></span> <span data-ttu-id="a5d5b-109">W związku z tym użytkownicy mogą nadal tworzyć diagramy procesów biznesowych na podstawie zapisów w celu analizy i projektowania swoich zgłoszeń.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-109">Therefore, users can continue to produce rich business process diagrams from recordings to analyze and design their applications.</span></span>

## <a name="architecture"></a><span data-ttu-id="a5d5b-110">Architektura</span><span class="sxs-lookup"><span data-stu-id="a5d5b-110">Architecture</span></span>

<span data-ttu-id="a5d5b-111">Rejestrator zadań może rejestrować działania użytkownika na komputerze klienckim z precyzyjną dokładnością.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-111">Task recorder can record user actions in the client with exact fidelity.</span></span> <span data-ttu-id="a5d5b-112">Każdy element sterujący jest wyposażony w narzędzie do powiadamiania Rejestratora zadań o wykonaniu czynności przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-112">Each control is instrumented to notify Task recorder about the execution of a user action.</span></span> <span data-ttu-id="a5d5b-113">Element sterujący powiadamia Rejestrator zadań o wystąpieniu zdarzenia i przekazuje wszelkie stosowne informacje o odpowiedniej akcji użytkownika w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-113">The control notifies Task recorder that an event occurred and passes along all pertinent information about the corresponding user action in real time.</span></span> <span data-ttu-id="a5d5b-114">Z tych informacji Rejestrator zadań uzyskuje dane o typie akcji użytkownika (na przykład kliknięciu przycisku, wprowadzeniu wartości lub nawigowaniu) oraz wszelkie dane związane z daną akcją użytkownika (na przykład wartość i typ danych wejściowych, kontekst formularza lub rekordu).</span><span class="sxs-lookup"><span data-stu-id="a5d5b-114">From this information, Task recorder can capture the type of user action (such as a button click, value entry, or navigation) and any data that is related to the user action (such as the input data value and type, form context, or record context).</span></span> <span data-ttu-id="a5d5b-115">Rejestrator zachowuje informacje z wystarczającą ilością szczegółów w celu zagwarantowania, że odtwarzanie nagrania może przeprowadzić zarejestrowane akcje dokładnie tak samo, jak były wykonywane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-115">Task recorder persists the information with enough detail to help guarantee that a playback of the recording can perform the recorded actions exactly as the user performed them.</span></span> <span data-ttu-id="a5d5b-116">(Funkcja odtwarzania nie została jeszcze zaimplementowana w programie Retail modern POS lub Cloud POS.)</span><span class="sxs-lookup"><span data-stu-id="a5d5b-116">(The playback feature isn't yet implemented at Retail modern POS or Cloud POS.)</span></span>

## <a name="basic-configuration"></a><span data-ttu-id="a5d5b-117">Konfiguracja podstawowa</span><span class="sxs-lookup"><span data-stu-id="a5d5b-117">Basic configuration</span></span>

<span data-ttu-id="a5d5b-118">Aby włączyć rejestrowanie zadań w punkcie sprzedaży, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-118">To enable task recording in POS, follow these steps.</span></span>

1. <span data-ttu-id="a5d5b-119">Kliknij kolejno opcje **Handel detaliczny i inny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Rejestry**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-119">Click **Retail and Commerce** &gt; **Channel Setup** &gt; **POS Setup** &gt; **Registers**.</span></span>
2. <span data-ttu-id="a5d5b-120">Kliknij rejestr, aby włączyć rejestrowanie zadań.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-120">Click the register to enable task recording on.</span></span>
3. <span data-ttu-id="a5d5b-121">Na karcie **Rejestr**, na skróconej karcie **Ogólne** dla opcji **Włącz rejestrowanie zadań** wybierz ustawienie **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-121">On the **Register** tab, on the **General** FastTab, set the **Enable task recording** option to **Yes**.</span></span>
4. <span data-ttu-id="a5d5b-122">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-122">Click **Save**.</span></span>
5. <span data-ttu-id="a5d5b-123">Wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Dane IT sprzedaży** &gt; **Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-123">Go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedule**.</span></span>
6. <span data-ttu-id="a5d5b-124">Wybierz zadanie **Rejestry (1090)**, a następnie kliknij przycisk **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-124">Select the **Registers (1090)** job, and then click **Run now**.</span></span>

## <a name="create-a-recording"></a><span data-ttu-id="a5d5b-125">Utwórz nagranie</span><span class="sxs-lookup"><span data-stu-id="a5d5b-125">Create a recording</span></span>

<span data-ttu-id="a5d5b-126">Wykonaj następujące kroki, aby utworzyć nowe nagranie przy użyciu Rejestratora zadań.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-126">Follow these steps to create a new recording using Task recorder.</span></span>

1. <span data-ttu-id="a5d5b-127">Uruchom program Retail Modern POS lub Cloud POS i zaloguj się.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-127">Start Retail Modern POS or Cloud POS, and sign in.</span></span>
2. <span data-ttu-id="a5d5b-128">Na stronie **Ustawienia**, w sekcji **Rejestrator zadań** kliknij przycisk **Otwórz rejestratora zadań**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-128">On the **Settings** page, in the **Task Recorder** section, click **Open task recorder**.</span></span> <span data-ttu-id="a5d5b-129">Pojawi się okienko **Rejestrator zadań**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-129">The **Task recorder** pane appears.</span></span> <span data-ttu-id="a5d5b-130">Przed rozpoczęciem nowego nagrania możesz kliknąć przycisk **Zamknij** (**X**) w prawym górnym rogu, aby zamknąć okienko **Rejestrator zadań**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-130">You can click the **Close** button (**X**) in the upper-right corner to close the **Task recorder** pane before you begin a new recording.</span></span> <span data-ttu-id="a5d5b-131">Aby ponownie otworzyć okienko, powtórz krok 2.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-131">To reopen the pane, repeat step 2.</span></span>

    <span data-ttu-id="a5d5b-132">[![okienko rejestratora zadań](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)</span><span class="sxs-lookup"><span data-stu-id="a5d5b-132">[![Task recorder pane](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)</span></span>

3. <span data-ttu-id="a5d5b-133">Wprowadź nazwę i opis nagrania, a następnie kliknij przycisk **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-133">Enter a name and description for the recording, and then click **Start**.</span></span> <span data-ttu-id="a5d5b-134">Sesja nagrywania rozpoczyna się natychmiast po kliknięciu przycisku **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-134">The recording session begins as soon as you click **Start**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a5d5b-135">Po kliknięciu przycisku **Zamknij** (**X**) w prawym górnym rogu, gdy operacja rejestrowania jest w toku, okienko **Rejestrator zadań** zostaje zamknięte, ale sesja rejestrowania nie jest zakończona.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-135">If you click the **Close** button (**X**) in the upper-right corner while recording is in progress, the **Task recorder** pane is closed, but the recording session isn't ended.</span></span> <span data-ttu-id="a5d5b-136">Aby ponownie otworzyć okienko rejestratora zadań, kliknij przycisk **Pomoc** (znak zapytania) w górnej części ekranu.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-136">To reopen the Task recorder pane, click the **Help** button (question mark) at the top of the screen.</span></span>
    >
    > <span data-ttu-id="a5d5b-137">[![Znak zapytania](./media/help.jpg)](./media/help.jpg)</span><span class="sxs-lookup"><span data-stu-id="a5d5b-137">[![Question mark](./media/help.jpg)](./media/help.jpg)</span></span>

4. <span data-ttu-id="a5d5b-138">Po kliknięciu przycisku **Uruchom** Rejestrator zadań wchodzi w tryb rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-138">After you click **Start**, Task recorder enters recording mode.</span></span> <span data-ttu-id="a5d5b-139">W okienku **Rejestrator zadań** są wyświetlane informacje i elementy sterujące, które są związane z procesem rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-139">The **Task recorder** pane shows information and controls that are related to the recording process.</span></span>
5. <span data-ttu-id="a5d5b-140">Wykonaj działania, które chcesz wykonać w interfejsu użytkownika (UI) Retail Modern POS lub Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-140">Perform the actions that you want to perform in the Retail Modern POS or Cloud POS user interface (UI).</span></span>
6. <span data-ttu-id="a5d5b-141">Aby zakończyć sesję rejestrowania, kliknij przycisk **Zatrzymaj**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-141">To end the recording session, click **Stop**.</span></span>

## <a name="download-options"></a><span data-ttu-id="a5d5b-142">Opcje pobierania</span><span class="sxs-lookup"><span data-stu-id="a5d5b-142">Download options</span></span>

<span data-ttu-id="a5d5b-143">Po zakończeniu sesji rejestrowania wyświetlanych jest kilka opcji, dzięki czemu można pobrać nagranie.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-143">After you end the recording session, several options are shown, so that you can download your recording.</span></span>

<span data-ttu-id="a5d5b-144">[![Opcje pobierania](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)</span><span class="sxs-lookup"><span data-stu-id="a5d5b-144">[![Download options](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)</span></span>

### <a name="save-to-this-pc"></a><span data-ttu-id="a5d5b-145">Zapisz na tym komputerze</span><span class="sxs-lookup"><span data-stu-id="a5d5b-145">Save to this PC</span></span>

<span data-ttu-id="a5d5b-146">Pakiet rejestracji umożliwia odtwarzanie przewodnika po zadaniu, obsługę rejestrowania oraz edytowanie adnotacji do nagrania.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-146">You can use the recording package to play a Task guide, maintain the recording, or edit the annotations in the recording.</span></span> <span data-ttu-id="a5d5b-147">(Funkcja ta nie została jeszcze zaimplementowana w programie Retail Modern POS i Cloud POS).</span><span class="sxs-lookup"><span data-stu-id="a5d5b-147">(This feature isn't yet implemented in Retail Modern POS and Cloud POS.)</span></span>

### <a name="export-as-word-document"></a><span data-ttu-id="a5d5b-148">Eksportuj jako dokument programu Word</span><span class="sxs-lookup"><span data-stu-id="a5d5b-148">Export as Word document</span></span>

<span data-ttu-id="a5d5b-149">Nagranie można zapisać jako dokument programu Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-149">You can save the recording as a Microsoft Word document.</span></span> <span data-ttu-id="a5d5b-150">Dokument będzie zawierać nagrane kroki i wykonane zrzuty ekranu.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-150">The document will contain the recorded steps and the screenshots that were captured.</span></span>

### <a name="save-as-developer-recording"></a><span data-ttu-id="a5d5b-151">Zapisz jako nagranie dewelopera</span><span class="sxs-lookup"><span data-stu-id="a5d5b-151">Save as developer recording</span></span>

<span data-ttu-id="a5d5b-152">Nieprzetworzony plik nagrania będzie przydatny w scenariuszach deweloperskich, takich jak generowanie kodu testowego.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-152">The raw recording file will be useful for developer scenarios such as test code generation.</span></span> <span data-ttu-id="a5d5b-153">(Ta funkcja nie została jeszcze zaimplementowana.)</span><span class="sxs-lookup"><span data-stu-id="a5d5b-153">(This feature isn't yet implemented.)</span></span>

## <a name="recording-controls"></a><span data-ttu-id="a5d5b-154">Elementy sterujące rejestrowania</span><span class="sxs-lookup"><span data-stu-id="a5d5b-154">Recording controls</span></span>

<span data-ttu-id="a5d5b-155">[![Elementy sterujące rejestrowania](./media/controls.jpg)](./media/controls.jpg)</span><span class="sxs-lookup"><span data-stu-id="a5d5b-155">[![Recording controls](./media/controls.jpg)](./media/controls.jpg)</span></span>

### <a name="stop"></a><span data-ttu-id="a5d5b-156">Zatrzymaj</span><span class="sxs-lookup"><span data-stu-id="a5d5b-156">Stop</span></span>

<span data-ttu-id="a5d5b-157">Kliknij przycisk **Zatrzymaj**, aby zakończyć sesję rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-157">Click **Stop** to end the recording session.</span></span> <span data-ttu-id="a5d5b-158">Pamiętaj, że nie można ponownie uruchomić sesji po jej zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-158">Note that you can't restart a session after you end it.</span></span> <span data-ttu-id="a5d5b-159">W związku z tym upewnij się, czy rejestrowanie zostało ukończone przed zakończeniem sesji.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-159">Therefore, make sure that the recording is completed before you end it.</span></span>

### <a name="pause"></a><span data-ttu-id="a5d5b-160">Wstrzymaj</span><span class="sxs-lookup"><span data-stu-id="a5d5b-160">Pause</span></span>

<span data-ttu-id="a5d5b-161">Kliknij przycisk **Wstrzymaj**, aby tymczasowo zatrzymać (wstrzymać) sesję rejestrowania i kontynuować operację.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-161">Click **Pause** to temporarily stop (pause) the recording session and continue with the operation.</span></span> <span data-ttu-id="a5d5b-162">Czynności wykonane po kliknięciu przycisku **Wstrzymaj** nie są rejestrowane.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-162">Steps that you perform after you click **Pause** aren't recorded.</span></span>

### <a name="continue"></a><span data-ttu-id="a5d5b-163">Kontynuuj</span><span class="sxs-lookup"><span data-stu-id="a5d5b-163">Continue</span></span>

<span data-ttu-id="a5d5b-164">Aby wznowić sesję rejestrowania po wstrzymaniu jej, kliknij przycisk **Kontynuuj**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-164">To resume the recording session after you've paused it, click **Continue**.</span></span>

### <a name="capture-screenshots"></a><span data-ttu-id="a5d5b-165">Przechwyć zrzuty ekranu</span><span class="sxs-lookup"><span data-stu-id="a5d5b-165">Capture screenshots</span></span>

<span data-ttu-id="a5d5b-166">Rejestrator zadań może przechwycić zrzuty ekranu interfejsu użytkownika Retail Modern POS podczas nagrywania procesu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-166">Task recorder can capture screenshots of the Retail Modern POS UI as you record a business process.</span></span> <span data-ttu-id="a5d5b-167">Aby włączyć funkcję przechwytywania zrzutów ekranu, należy dla opcji **Przechwyć zrzuty ekranu** wybrać ustawienie **Tak**, a następnie wykonać nagranie.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-167">To turn on the screenshot capture feature, set the **Capture screenshot** option to **Yes** and then make the recording.</span></span> <span data-ttu-id="a5d5b-168">Po zakończeniu nagrywania kliknij przycisk **Zatrzymaj** i pobierz dokument programu Word.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-168">Once the recording is completed, click **Stop** and download the Word document.</span></span> <span data-ttu-id="a5d5b-169">Dokument będzie zawierał czynności w odpowiednimi zrzutami ekranu.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-169">The document will contain the steps with relevant screenshots.</span></span>

> [!NOTE]
> <span data-ttu-id="a5d5b-170">Funkcja przechwytywania zrzutów ekranu nie jest obsługiwana w programie Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-170">Capture screenshot functionality is not supported in Cloud POS.</span></span>

### <a name="start-task-and-end-task"></a><span data-ttu-id="a5d5b-171">Rozpoczęcie i zakończenie zadania</span><span class="sxs-lookup"><span data-stu-id="a5d5b-171">Start task and End task</span></span>

<span data-ttu-id="a5d5b-172">Początek i koniec zestawu zgrupowanych kroków można określić przy użyciu przycisków **Rozpocznij zadanie** i **Zakończ** **zadanie**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-172">You can specify the beginning and end of a set of grouped steps by using the **Start task** and **End** **task** buttons.</span></span> <span data-ttu-id="a5d5b-173">Kliknij przycisk **Rozpocznij zadanie**, aby dodać krok rozpoczęcia zadania, a następnie wykonaj kroki, które powinny zostać uwzględnione w grupie.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-173">Click **Start task** to add a "Start Task" step, and then perform the steps that should be included in the group.</span></span> <span data-ttu-id="a5d5b-174">Po zakończeniu wykonywania kroków do uwzględnienia w grupie, kliknij przycisk **Zakończ zadanie**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-174">After you've finished performing the steps for the group, click **End task**.</span></span> <span data-ttu-id="a5d5b-175">Zadania pomagają porządkować procedury.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-175">Tasks help you organize your procedures.</span></span> <span data-ttu-id="a5d5b-176">Zadania można zagnieżdżać wewnątrz innych zadań.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-176">Tasks can be nested within other tasks.</span></span> <span data-ttu-id="a5d5b-177">W ten sposób można lepiej organizować bardzo długie i złożone procesy biznesowe.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-177">In this way, you can better organize very long and complex business processes.</span></span>

## <a name="adding-annotations"></a><span data-ttu-id="a5d5b-178">Dodawanie adnotacji</span><span class="sxs-lookup"><span data-stu-id="a5d5b-178">Adding annotations</span></span>

<span data-ttu-id="a5d5b-179">Adnotacja to dodatkowy tekst, który można dodać do kroku w nagraniu.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-179">An annotation is additional text that you add to a step in a recording.</span></span> <span data-ttu-id="a5d5b-180">Na przykład można użyć adnotacji w celu udostępnienia użytkownikowi dodatkowego kontekstu lub instrukcji.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-180">For example, you can use annotations to give the user more context or instructions.</span></span> <span data-ttu-id="a5d5b-181">Można dodać adnotacje, przed lub po kroku.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-181">You can add annotations before or after a step.</span></span> <span data-ttu-id="a5d5b-182">Adnotację można dodać do dowolnego kroku, klikając przycisk **Edytuj** (symbol ołówka) po prawej stronie kroku.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-182">You can add an annotation to any step by clicking the **Edit** button (pencil symbol) to the right of the step.</span></span>

<span data-ttu-id="a5d5b-183">[![Przycisk Edytuj dla kroku](./media/annotate.jpg)](./media/annotate.jpg)</span><span class="sxs-lookup"><span data-stu-id="a5d5b-183">[![Edit button for a step](./media/annotate.jpg)](./media/annotate.jpg)</span></span>

### <a name="texts-and-notes"></a><span data-ttu-id="a5d5b-184">Teksty i notatki</span><span class="sxs-lookup"><span data-stu-id="a5d5b-184">Texts and notes</span></span>

<span data-ttu-id="a5d5b-185">Można użyć pól **Teksty** i **Notatki** w celu dodania tekstu, który ma być skojarzony z krokiem w przewodniku po zadaniu.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-185">You can use the **Texts** and **Notes** fields to add text that should be associated with a step in a Task guide.</span></span>

<span data-ttu-id="a5d5b-186">[![Pola Teksty i Notatki](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)</span><span class="sxs-lookup"><span data-stu-id="a5d5b-186">[![Text and Notes fields](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)</span></span>

#### <a name="text"></a><span data-ttu-id="a5d5b-187">Tekst</span><span class="sxs-lookup"><span data-stu-id="a5d5b-187">Text</span></span>

<span data-ttu-id="a5d5b-188">Tekst wprowadzony w polu **Tekst** pojawi się *nad* tekstem kroku w przewodniku po zadaniu.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-188">Text that you enter in the **Text** field appears *above* the step text in the Task guide.</span></span> <span data-ttu-id="a5d5b-189">Ta lokalizacja jest odpowiednia dla tekstu, który ma być odczytany przez użytkownika przed wykonaniem kroku.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-189">This location is appropriate for text that you want the user to read before he or she completes the step.</span></span>

#### <a name="notes"></a><span data-ttu-id="a5d5b-190">Notatki</span><span class="sxs-lookup"><span data-stu-id="a5d5b-190">Notes</span></span>

<span data-ttu-id="a5d5b-191">Tekst wprowadzony w polu **Notatki** pojawi się *pod* tekstem kroku w przewodniku po zadaniu.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-191">Text that you enter in the **Notes** field appears *below* the step text in the Task guide.</span></span> <span data-ttu-id="a5d5b-192">Aby odczytać tekst notatki, użytkownik musi rozwinąć tekst kroku w oknie podręcznym.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-192">To read the note text, the user must expand the step text in the pop-up window.</span></span> <span data-ttu-id="a5d5b-193">Ta lokalizacja jest odpowiednia dla materiałów do przeczytania opcjonalnie lub innych informacji, która mogą być użyteczne dla użytkownika, ale nie są konieczne dla użytkownika do zakończenia akcji.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-193">This location is appropriate for optional reading material or other information that might be useful to the user, but that the user doesn't require in order to complete the action.</span></span>

## <a name="help-in-retail-modern-pos-and-cloud-pos"></a><span data-ttu-id="a5d5b-194">Pomoc w programie Retail Modern POS i Cloud POS</span><span class="sxs-lookup"><span data-stu-id="a5d5b-194">Help in Retail Modern POS and Cloud POS</span></span>

<span data-ttu-id="a5d5b-195">Aby wyświetlić własne niestandardowe nagrania zadań w okienku Pomocy programu Retail Modern POS i Cloud POS, by mogły być wyświetlane jako tekst, należy zapisać nagrania zadań w bibliotece BPM, a następnie zaktualizować parametry systemu Pomocy, aby wskazywał bibliotekę BPM.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-195">To show your own custom task recordings in the Help pane of Retail Modern POS and Cloud POS so that they can be viewed as text, you must save your task recordings to your own BPM library, and then update your Help system parameters to point to your BPM library.</span></span> <span data-ttu-id="a5d5b-196">Aby uzyskać więcej informacji, zobacz [Łączenie z systemem Pomocy](../fin-and-ops/get-started/help-connect.md).</span><span class="sxs-lookup"><span data-stu-id="a5d5b-196">For more information, see [Connecting the Help system](../fin-and-ops/get-started/help-connect.md).</span></span> <span data-ttu-id="a5d5b-197">Pomoc programu Retail Modern POS i Cloud POS wyszukuje usługi LCS w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-197">Retail Modern POS and Cloud POS Help searches LCS in real time.</span></span> <span data-ttu-id="a5d5b-198">Przeszukuje wszystkie biblioteki BPM wybrane w parametrach systemu Commerce — Pomoc i przedstawia odpowiednie wyniki.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-198">It searches across all the BPM libraries that are selected in the Commerce Help system parameters and shows the relevant results.</span></span> <span data-ttu-id="a5d5b-199">Aby uzyskać dostęp do menu **Pomoc**, kliknij przycisk **Pomoc** (znak zapytania) znajdujący się u góry ekranu, a następnie w polu wyszukiwania wpisz nazwę procesu i kliknij przycisk wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-199">To access the **Help** menu, click the **Help** button (question mark) at the top of the screen and then in the search box type your process name and hit the search button.</span></span>

<span data-ttu-id="a5d5b-200">[![Przycisk Pomoc](./media/help.jpg)](./media/help.jpg)</span><span class="sxs-lookup"><span data-stu-id="a5d5b-200">[![Help button](./media/help.jpg)](./media/help.jpg)</span></span>

<span data-ttu-id="a5d5b-201">Po kliknięciu pozycji Przewodnik po zadaniu w wynikach wyszukiwania można wyświetlić kroki jako tematy pomocy lub wyeksportować kroki do dokumentu programu Word.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-201">When you click a Task guide in the search results, you can either view the steps as a Help topic or export the steps to a Word document.</span></span>

> [!NOTE]
> <span data-ttu-id="a5d5b-202">Pomoc w programach Retail Modern POS and Cloud POS nie powoduje uruchamiania przewodników po zadaniach dopasowanych do otwartego formularza lub wykonywanej operacji.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-202">Help in Retail Modern POS and Cloud POS will not bring up task guides according to what form you're on or operation you're doing.</span></span> <span data-ttu-id="a5d5b-203">Należy wpisać nazwę procesu w polu wyszukiwania, a następnie kliknąć przycisk **Szukaj**.</span><span class="sxs-lookup"><span data-stu-id="a5d5b-203">You have to type the process name in the search box and then click **Search**.</span></span>
