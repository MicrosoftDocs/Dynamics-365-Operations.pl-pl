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
ms.openlocfilehash: 8bd3c9bea010099f83d16dad70261bc2d46a1dac
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693289"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="f74b2-103">Konfigurowanie właściwości przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="f74b2-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f74b2-104">W tym temacie wyjaśniono sposób konfigurowania różnych właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="f74b2-105">Aby skonfigurować właściwości przepływu pracy, otwórz przepływ pracy w edytorze przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="f74b2-106">Kliknij w obszarze roboczym edytora przepływu pracy, a następnie kliknij przycisk **Właściwości**, aby otworzyć stronę **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="f74b2-107">Można użyć poniższych procedur, aby skonfigurować różne właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="f74b2-108">Nadawanie nazwy przepływowi pracy</span><span class="sxs-lookup"><span data-stu-id="f74b2-108">Name the workflow</span></span>

<span data-ttu-id="f74b2-109">Należy wykonać następujące kroki, aby wprowadzić nazwę przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="f74b2-110">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f74b2-111">W polu **Nazwa** wprowadź unikatową nazwę przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="f74b2-112">Na przykład jeśli tworzysz przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, można nazwać przepływy **Zapotrzebowania na zakup — Dania** lub **Zapotrzebowania na zakup — Hiszpania**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="f74b2-113">Określanie właściciela przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="f74b2-113">Specify the workflow owner</span></span>

<span data-ttu-id="f74b2-114">Właściciel przepływu pracy jest osobą, która zarządza przepływem pracy i obsługuje go.</span><span class="sxs-lookup"><span data-stu-id="f74b2-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="f74b2-115">Aby określić właściciela przepływu pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f74b2-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="f74b2-116">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f74b2-117">Na liście **Właściciel** zaznacz nazwę osoby, która będzie zarządzać przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="f74b2-118">Wybór szablonu wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="f74b2-118">Select an email template</span></span>

<span data-ttu-id="f74b2-119">Wykonaj następujące kroki, aby wybrać szablon wiadomości e-mail, który będzie używany do generowania komunikatów powiadomień dotyczących przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="f74b2-120">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f74b2-121">Na liście **Szablon wiadomości e-mail dla powiadomień o przepływie pracy** zaznacz szablon.</span><span class="sxs-lookup"><span data-stu-id="f74b2-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="f74b2-122">Wprowadzanie instrukcji dla użytkowników</span><span class="sxs-lookup"><span data-stu-id="f74b2-122">Enter instructions for users</span></span>

<span data-ttu-id="f74b2-123">Istnieje możliwość udostępniania instrukcji użytkownikom, którzy będą przesyłać dokumenty do przetwarzania i zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="f74b2-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="f74b2-124">Ci użytkownicy są również zwani *inicjatorami*.</span><span class="sxs-lookup"><span data-stu-id="f74b2-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="f74b2-125">Na przykład tworzysz przepływ pracy zapotrzebowania na zakup i wprowadzasz instrukcje.</span><span class="sxs-lookup"><span data-stu-id="f74b2-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="f74b2-126">Te instrukcje mogą być wyświetlane przez użytkowników wprowadzających zapotrzebowania na zakup na stronie **Zapotrzebowania na zakup**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="f74b2-127">Aby wyświetlić instrukcje, inicjator klika ikonę na pasku komunikatów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="f74b2-128">Aby wprowadzić instrukcje dla użytkowników, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f74b2-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="f74b2-129">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f74b2-130">W polu **Instrukcje przesyłania** wprowadź instrukcje.</span><span class="sxs-lookup"><span data-stu-id="f74b2-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="f74b2-131">Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="f74b2-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="f74b2-132">Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="f74b2-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="f74b2-133">Aby wstawić symbol zastępczy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="f74b2-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="f74b2-134">Kliknij w polu **Instrukcje przesyłania**, aby określić miejsce wyświetlania symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="f74b2-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="f74b2-135">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="f74b2-136">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="f74b2-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="f74b2-137">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-137">Click **Insert**.</span></span>

4. <span data-ttu-id="f74b2-138">Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="f74b2-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="f74b2-139">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="f74b2-140">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="f74b2-141">Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.</span><span class="sxs-lookup"><span data-stu-id="f74b2-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="f74b2-142">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="f74b2-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="f74b2-143">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="f74b2-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="f74b2-144">Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 3.</span><span class="sxs-lookup"><span data-stu-id="f74b2-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="f74b2-145">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="f74b2-146">Określ, kiedy ten przepływ pracy jest używany w warunkach aktywacji</span><span class="sxs-lookup"><span data-stu-id="f74b2-146">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="f74b2-147">Można utworzyć wiele przepływów pracy opartych na tym samym typie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-147">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="f74b2-148">Jeśli istnieje wiele przepływów pracy opartych na tym samym typie, trzeba określić warunki używania poszczególnych przepływów pracy w warunkach aktywacji.</span><span class="sxs-lookup"><span data-stu-id="f74b2-148">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="f74b2-149">Jeśli warunki aktywacji nie są spełnione, zostanie użyty domyślny przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-149">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="f74b2-150">Podobnie, jeśli dla danego typu przepływu pracy zdefiniowano tylko jedną konfigurację przepływu pracy, konfiguracja przepływu pracy będzie używana niezależnie od warunków aktywacji.</span><span class="sxs-lookup"><span data-stu-id="f74b2-150">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="f74b2-151">Na przykład można utworzyć przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, na przykład Zapotrzebowania na zakup — Dania lub Zapotrzebowania na zakup — Hiszpania, z następującymi warunkami:</span><span class="sxs-lookup"><span data-stu-id="f74b2-151">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="f74b2-152">Zapotrzebowania na zakup — Dania jest używany, gdy krajem/regionem jest DK.</span><span class="sxs-lookup"><span data-stu-id="f74b2-152">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="f74b2-153">Zapotrzebowania na zakup — Hiszpania jest używany, gdy krajem/regionem jest ES.</span><span class="sxs-lookup"><span data-stu-id="f74b2-153">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="f74b2-154">Aby określić, kiedy ma być używany konfigurowany przepływ pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f74b2-154">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="f74b2-155">W lewym okienku kliknij opcję **Aktywacja**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-155">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="f74b2-156">Zaznacz pole wyboru **Ustaw warunki uruchamiania tego przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-156">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="f74b2-157">Kliknij opcję **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-157">Click **Add condition**.</span></span>
4. <span data-ttu-id="f74b2-158">Służy do wprowadzania warunku.</span><span class="sxs-lookup"><span data-stu-id="f74b2-158">Enter a condition.</span></span>
5. <span data-ttu-id="f74b2-159">Wprowadź wszelkie wymagane dodatkowe warunki.</span><span class="sxs-lookup"><span data-stu-id="f74b2-159">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="f74b2-160">Przeprowadź przepływ pracy z niektórymi rekordami docelowymi, aby sprawdzić, czy warunek poprawnie obejmuje i wyklucza rekordy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-160">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="f74b2-161">Określanie, kiedy są wysyłane powiadomienia</span><span class="sxs-lookup"><span data-stu-id="f74b2-161">Specify when notifications are sent</span></span>

<span data-ttu-id="f74b2-162">Podczas przesyłania dokumentu do przetwarzania tworzone jest wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-162">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="f74b2-163">Można wysyłać powiadomienia do użytkowników, gdy wystąpienia przepływu pracy oparte na przepływie pracy są uruchamiane, kończone, przerywane lub zatrzymane z powodu błędu.</span><span class="sxs-lookup"><span data-stu-id="f74b2-163">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="f74b2-164">Aby określić, kiedy są wysyłane powiadomienia, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f74b2-164">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="f74b2-165">W lewym okienku kliknij opcję **Powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-165">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="f74b2-166">Zaznacz pole wyboru dla każdego zdarzenia, które powinno uruchamiać powiadomienia:</span><span class="sxs-lookup"><span data-stu-id="f74b2-166">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="f74b2-167">**Rozpoczęte** — wysyłanie powiadomień po uruchomieniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-167">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="f74b2-168">**Zatrzymane** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu błędu.</span><span class="sxs-lookup"><span data-stu-id="f74b2-168">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="f74b2-169">**Ukończono** — wysyłanie powiadomień po zakończeniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-169">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="f74b2-170">**Nieodwracalne** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu nieodwracalnego błędu.</span><span class="sxs-lookup"><span data-stu-id="f74b2-170">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="f74b2-171">**Przerwane** — wysyłanie powiadomień po przerwaniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-171">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="f74b2-172">Zaznacz wiersz zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="f74b2-172">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="f74b2-173">Na karcie **Tekst powiadomienia** wprowadź tekst powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="f74b2-173">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="f74b2-174">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="f74b2-174">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="f74b2-175">Podczas wyświetlania tekstu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="f74b2-175">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="f74b2-176">Aby wstawić symbol zastępczy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="f74b2-176">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="f74b2-177">Kliknij w polu, aby określić miejsce wyświetlania symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="f74b2-177">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="f74b2-178">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-178">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="f74b2-179">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="f74b2-179">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="f74b2-180">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-180">Click **Insert**.</span></span>
    5. <span data-ttu-id="f74b2-181">Popularnym dołączanym elementem zastępczym **Tekst powiadomienia** jest „Ostatnie uwagi: %Workflow.Last note%”, który pokazuje wszystkie komentarze z poprzedniego kroku.</span><span class="sxs-lookup"><span data-stu-id="f74b2-181">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="f74b2-182">Aby dodać tłumaczenia tekstu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="f74b2-182">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="f74b2-183">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-183">Click **Translations**.</span></span>
    2. <span data-ttu-id="f74b2-184">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-184">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="f74b2-185">Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.</span><span class="sxs-lookup"><span data-stu-id="f74b2-185">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="f74b2-186">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="f74b2-186">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="f74b2-187">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="f74b2-187">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="f74b2-188">Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 5.</span><span class="sxs-lookup"><span data-stu-id="f74b2-188">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="f74b2-189">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-189">Click **Close**.</span></span>

7. <span data-ttu-id="f74b2-190">Na karcie **Adresat** użyj poniższych opcji do określenia, kto ma otrzymywać powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="f74b2-190">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="f74b2-191">Opcja</span><span class="sxs-lookup"><span data-stu-id="f74b2-191">Option</span></span></th>
    <th><span data-ttu-id="f74b2-192">Powiadomienia są tym użytkownikom</span><span class="sxs-lookup"><span data-stu-id="f74b2-192">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="f74b2-193">Aby wysyłać powiadomienia, należy wykonać następujące czynności</span><span class="sxs-lookup"><span data-stu-id="f74b2-193">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="f74b2-194">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="f74b2-194">Participant</span></span></td>
    <td><span data-ttu-id="f74b2-195">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="f74b2-195">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="f74b2-196">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Uczestnik</strong>.</span><span class="sxs-lookup"><span data-stu-id="f74b2-196">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="f74b2-197">Na karcie <strong>Oparte na</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="f74b2-197">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="f74b2-198">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="f74b2-198">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="f74b2-199">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="f74b2-199">Workflow user</span></span></td>
    <td><span data-ttu-id="f74b2-200">Użytkownicy będący uczestnikami tego przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="f74b2-200">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="f74b2-201">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik przepływu pracy</strong>.</span><span class="sxs-lookup"><span data-stu-id="f74b2-201">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="f74b2-202">Na karcie <strong>Użytkownik przepływu pracy</strong> na liście <strong>Użytkownik przepływu pracy</strong> wybierz uczestnika w tym przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="f74b2-202">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="f74b2-203">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="f74b2-203">User</span></span></td>
    <td><span data-ttu-id="f74b2-204">Określeni użytkownicy</span><span class="sxs-lookup"><span data-stu-id="f74b2-204">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="f74b2-205">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="f74b2-205">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="f74b2-206">Na karcie <strong>Użytkownik</strong> lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="f74b2-206">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="f74b2-207">Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="f74b2-207">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="f74b2-208">Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="f74b2-208">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="f74b2-209">Wprowadzanie komentarzy dotyczących zmian zastosowanych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="f74b2-209">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="f74b2-210">Aby wprowadzić komentarze dotyczące zmian zastosowanych w przepływie pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f74b2-210">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="f74b2-211">W lewym okienku kliknij opcję **Uwagi**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-211">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="f74b2-212">W polu **Wprowadź komentarze dotyczące przepływu pracy** wprowadź komentarze.</span><span class="sxs-lookup"><span data-stu-id="f74b2-212">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="f74b2-213">Przejrzyj wprowadzone komentarze.</span><span class="sxs-lookup"><span data-stu-id="f74b2-213">Review your comments.</span></span> <span data-ttu-id="f74b2-214">Po dodaniu komentarzy nie można ich modyfikować.</span><span class="sxs-lookup"><span data-stu-id="f74b2-214">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="f74b2-215">Kliknij przycisk **Dodaj**, aby dodać komentarze do obszaru **Historia komentarzy**.</span><span class="sxs-lookup"><span data-stu-id="f74b2-215">Click **Add** to add your comments to the **Comment history** area.</span></span>
