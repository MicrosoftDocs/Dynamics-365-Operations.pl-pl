---
title: Konfigurowanie właściwości przepływu pracy
description: W tym temacie wyjaśniono sposób konfigurowania różnych właściwości przepływu pracy.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3cb5dc59373b7af76fffa1b1c59728c84dfb5fb
ms.sourcegitcommit: fd62ab3d399b0d6ea0d362f1d403a300e84a576d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "5067630"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="6ddc5-103">Konfigurowanie właściwości przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="6ddc5-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ddc5-104">W tym temacie wyjaśniono sposób konfigurowania różnych właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="6ddc5-105">Aby skonfigurować właściwości przepływu pracy, otwórz przepływ pracy w edytorze przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="6ddc5-106">Kliknij w obszarze roboczym edytora przepływu pracy, a następnie kliknij przycisk **Właściwości**, aby otworzyć stronę **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="6ddc5-107">Można użyć poniższych procedur, aby skonfigurować różne właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="6ddc5-108">Nadawanie nazwy przepływowi pracy</span><span class="sxs-lookup"><span data-stu-id="6ddc5-108">Name the workflow</span></span>

<span data-ttu-id="6ddc5-109">Należy wykonać następujące kroki, aby wprowadzić nazwę przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="6ddc5-110">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="6ddc5-111">W polu **Nazwa** wprowadź unikatową nazwę przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="6ddc5-112">Na przykład jeśli tworzysz przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, można nazwać przepływy **Zapotrzebowania na zakup — Dania** lub **Zapotrzebowania na zakup — Hiszpania**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="6ddc5-113">Określanie właściciela przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="6ddc5-113">Specify the workflow owner</span></span>

<span data-ttu-id="6ddc5-114">Właściciel przepływu pracy jest osobą, która zarządza przepływem pracy i obsługuje go.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="6ddc5-115">Aby określić właściciela przepływu pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="6ddc5-116">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="6ddc5-117">Na liście **Właściciel** zaznacz nazwę osoby, która będzie zarządzać przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="6ddc5-118">Wybór szablonu wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="6ddc5-118">Select an email template</span></span>

<span data-ttu-id="6ddc5-119">Wykonaj następujące kroki, aby wybrać szablon wiadomości e-mail, który będzie używany do generowania komunikatów powiadomień dotyczących przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="6ddc5-120">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="6ddc5-121">Na liście **Szablon wiadomości e-mail dla powiadomień o przepływie pracy** zaznacz szablon.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="6ddc5-122">Wprowadzanie instrukcji dla użytkowników</span><span class="sxs-lookup"><span data-stu-id="6ddc5-122">Enter instructions for users</span></span>

<span data-ttu-id="6ddc5-123">Istnieje możliwość udostępniania instrukcji użytkownikom, którzy będą przesyłać dokumenty do przetwarzania i zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="6ddc5-124">Ci użytkownicy są również zwani *inicjatorami*.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="6ddc5-125">Na przykład tworzysz przepływ pracy zapotrzebowania na zakup i wprowadzasz instrukcje.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="6ddc5-126">Te instrukcje mogą być wyświetlane przez użytkowników wprowadzających zapotrzebowania na zakup na stronie **Zapotrzebowania na zakup**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="6ddc5-127">Aby wyświetlić instrukcje, inicjator klika ikonę na pasku komunikatów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="6ddc5-128">Aby wprowadzić instrukcje dla użytkowników, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="6ddc5-129">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="6ddc5-130">W polu **Instrukcje przesyłania** wprowadź instrukcje.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="6ddc5-131">Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="6ddc5-132">Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="6ddc5-133">Aby wstawić symbol zastępczy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6ddc5-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="6ddc5-134">Kliknij w polu **Instrukcje przesyłania**, aby określić miejsce wyświetlania symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="6ddc5-135">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="6ddc5-136">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="6ddc5-137">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-137">Click **Insert**.</span></span>

4. <span data-ttu-id="6ddc5-138">Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="6ddc5-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="6ddc5-139">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="6ddc5-140">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="6ddc5-141">Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="6ddc5-142">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="6ddc5-143">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="6ddc5-144">Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 3.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="6ddc5-145">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-145">Click **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="6ddc5-146">Nie można dodać symboli zastępczych, używając funkcji kopiowania i wklejania, ponieważ informacje docelowe nie zostały poprawnie wklejone.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-146">Placeholders cannot be added using copy and paste because the target information is not pasted in correctly.</span></span> <span data-ttu-id="6ddc5-147">Użyj interfejsu, aby dodać symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-147">Use the interface to add placeholders.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="6ddc5-148">Określ, kiedy ten przepływ pracy jest używany w warunkach aktywacji</span><span class="sxs-lookup"><span data-stu-id="6ddc5-148">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="6ddc5-149">Można utworzyć wiele przepływów pracy opartych na tym samym typie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-149">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="6ddc5-150">Jeśli istnieje wiele przepływów pracy opartych na tym samym typie, trzeba określić warunki używania poszczególnych przepływów pracy w warunkach aktywacji.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-150">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="6ddc5-151">Jeśli warunki aktywacji nie są spełnione, zostanie użyty domyślny przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-151">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="6ddc5-152">Podobnie, jeśli dla danego typu przepływu pracy zdefiniowano tylko jedną konfigurację przepływu pracy, konfiguracja przepływu pracy będzie używana niezależnie od warunków aktywacji.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-152">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="6ddc5-153">Na przykład można utworzyć przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, na przykład Zapotrzebowania na zakup — Dania lub Zapotrzebowania na zakup — Hiszpania, z następującymi warunkami:</span><span class="sxs-lookup"><span data-stu-id="6ddc5-153">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="6ddc5-154">Zapotrzebowania na zakup — Dania jest używany, gdy krajem/regionem jest DK.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-154">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="6ddc5-155">Zapotrzebowania na zakup — Hiszpania jest używany, gdy krajem/regionem jest ES.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-155">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="6ddc5-156">Aby określić, kiedy ma być używany konfigurowany przepływ pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-156">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="6ddc5-157">W lewym okienku kliknij opcję **Aktywacja**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-157">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="6ddc5-158">Zaznacz pole wyboru **Ustaw warunki uruchamiania tego przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-158">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="6ddc5-159">Kliknij opcję **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-159">Click **Add condition**.</span></span>
4. <span data-ttu-id="6ddc5-160">Służy do wprowadzania warunku.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-160">Enter a condition.</span></span>
5. <span data-ttu-id="6ddc5-161">Wprowadź wszelkie wymagane dodatkowe warunki.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-161">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="6ddc5-162">Przeprowadź przepływ pracy z niektórymi rekordami docelowymi, aby sprawdzić, czy warunek poprawnie obejmuje i wyklucza rekordy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-162">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="6ddc5-163">Określanie, kiedy są wysyłane powiadomienia</span><span class="sxs-lookup"><span data-stu-id="6ddc5-163">Specify when notifications are sent</span></span>

<span data-ttu-id="6ddc5-164">Podczas przesyłania dokumentu do przetwarzania tworzone jest wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-164">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="6ddc5-165">Można wysyłać powiadomienia do użytkowników, gdy wystąpienia przepływu pracy oparte na przepływie pracy są uruchamiane, kończone, przerywane lub zatrzymane z powodu błędu.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-165">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="6ddc5-166">Aby określić, kiedy są wysyłane powiadomienia, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-166">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="6ddc5-167">W lewym okienku kliknij opcję **Powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-167">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="6ddc5-168">Zaznacz pole wyboru dla każdego zdarzenia, które powinno uruchamiać powiadomienia:</span><span class="sxs-lookup"><span data-stu-id="6ddc5-168">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="6ddc5-169">**Rozpoczęte** — wysyłanie powiadomień po uruchomieniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-169">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="6ddc5-170">**Zatrzymane** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu błędu.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-170">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="6ddc5-171">**Ukończono** — wysyłanie powiadomień po zakończeniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-171">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="6ddc5-172">**Nieodwracalne** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu nieodwracalnego błędu.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-172">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="6ddc5-173">**Przerwane** — wysyłanie powiadomień po przerwaniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-173">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="6ddc5-174">Zaznacz wiersz zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-174">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="6ddc5-175">Na karcie **Tekst powiadomienia** wprowadź tekst powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-175">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="6ddc5-176">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-176">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="6ddc5-177">Podczas wyświetlania tekstu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-177">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="6ddc5-178">Aby wstawić symbol zastępczy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6ddc5-178">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="6ddc5-179">Kliknij w polu, aby określić miejsce wyświetlania symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-179">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="6ddc5-180">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-180">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="6ddc5-181">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-181">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="6ddc5-182">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-182">Click **Insert**.</span></span>
    5. <span data-ttu-id="6ddc5-183">Popularnym dołączanym elementem zastępczym **Tekst powiadomienia** jest „Ostatnie uwagi: %Workflow.Last note%”, który pokazuje wszystkie komentarze z poprzedniego kroku.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-183">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="6ddc5-184">Aby dodać tłumaczenia tekstu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="6ddc5-184">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="6ddc5-185">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-185">Click **Translations**.</span></span>
    2. <span data-ttu-id="6ddc5-186">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-186">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="6ddc5-187">Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-187">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="6ddc5-188">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-188">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="6ddc5-189">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-189">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="6ddc5-190">Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 5.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-190">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="6ddc5-191">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-191">Click **Close**.</span></span>

7. <span data-ttu-id="6ddc5-192">Na karcie **Adresat** użyj poniższych opcji do określenia, kto ma otrzymywać powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-192">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="6ddc5-193">Opcja</span><span class="sxs-lookup"><span data-stu-id="6ddc5-193">Option</span></span></th>
    <th><span data-ttu-id="6ddc5-194">Powiadomienia są tym użytkownikom</span><span class="sxs-lookup"><span data-stu-id="6ddc5-194">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="6ddc5-195">Aby wysyłać powiadomienia, należy wykonać następujące czynności</span><span class="sxs-lookup"><span data-stu-id="6ddc5-195">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="6ddc5-196">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="6ddc5-196">Participant</span></span></td>
    <td><span data-ttu-id="6ddc5-197">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="6ddc5-197">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="6ddc5-198">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Uczestnik</strong>.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-198">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="6ddc5-199">Na karcie <strong>Oparte na</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-199">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="6ddc5-200">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-200">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="6ddc5-201">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="6ddc5-201">Workflow user</span></span></td>
    <td><span data-ttu-id="6ddc5-202">Użytkownicy będący uczestnikami tego przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="6ddc5-202">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="6ddc5-203">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik przepływu pracy</strong>.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-203">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="6ddc5-204">Na karcie <strong>Użytkownik przepływu pracy</strong> na liście <strong>Użytkownik przepływu pracy</strong> wybierz uczestnika w tym przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-204">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="6ddc5-205">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="6ddc5-205">User</span></span></td>
    <td><span data-ttu-id="6ddc5-206">Określeni użytkownicy</span><span class="sxs-lookup"><span data-stu-id="6ddc5-206">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="6ddc5-207">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-207">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="6ddc5-208">Na karcie <strong>Użytkownik</strong> lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-208">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="6ddc5-209">Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-209">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="6ddc5-210">Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-210">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="6ddc5-211">Wprowadzanie komentarzy dotyczących zmian zastosowanych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ddc5-211">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="6ddc5-212">Aby wprowadzić komentarze dotyczące zmian zastosowanych w przepływie pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-212">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="6ddc5-213">W lewym okienku kliknij opcję **Uwagi**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-213">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="6ddc5-214">W polu **Wprowadź komentarze dotyczące przepływu pracy** wprowadź komentarze.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-214">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="6ddc5-215">Przejrzyj wprowadzone komentarze.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-215">Review your comments.</span></span> <span data-ttu-id="6ddc5-216">Po dodaniu komentarzy nie można ich modyfikować.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-216">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="6ddc5-217">Kliknij przycisk **Dodaj**, aby dodać komentarze do obszaru **Historia komentarzy**.</span><span class="sxs-lookup"><span data-stu-id="6ddc5-217">Click **Add** to add your comments to the **Comment history** area.</span></span>
