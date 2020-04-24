---
title: Konfigurowanie właściwości przepływu pracy
description: W tym temacie wyjaśniono sposób konfigurowania różnych właściwości przepływu pracy.
author: sericks007
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d745389b37b899760ea32ae75c5cb80d9139be2d
ms.sourcegitcommit: 1852f08f015acd106f4cefd03fa07985dc009123
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2020
ms.locfileid: "3199443"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="a9c27-103">Konfigurowanie właściwości przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="a9c27-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9c27-104">W tym temacie wyjaśniono sposób konfigurowania różnych właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="a9c27-105">Aby skonfigurować właściwości przepływu pracy, otwórz przepływ pracy w edytorze przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="a9c27-106">Kliknij w obszarze roboczym edytora przepływu pracy, a następnie kliknij przycisk **Właściwości**, aby otworzyć stronę **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="a9c27-107">Można użyć poniższych procedur, aby skonfigurować różne właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="a9c27-108">Nadawanie nazwy przepływowi pracy</span><span class="sxs-lookup"><span data-stu-id="a9c27-108">Name the workflow</span></span>

<span data-ttu-id="a9c27-109">Należy wykonać następujące kroki, aby wprowadzić nazwę przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="a9c27-110">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="a9c27-111">W polu **Nazwa** wprowadź unikatową nazwę przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="a9c27-112">Na przykład jeśli tworzysz przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, można nazwać przepływy **Zapotrzebowania na zakup — Dania** lub **Zapotrzebowania na zakup — Hiszpania**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="a9c27-113">Określanie właściciela przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="a9c27-113">Specify the workflow owner</span></span>

<span data-ttu-id="a9c27-114">Właściciel przepływu pracy jest osobą, która zarządza przepływem pracy i obsługuje go.</span><span class="sxs-lookup"><span data-stu-id="a9c27-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="a9c27-115">Aby określić właściciela przepływu pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a9c27-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="a9c27-116">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="a9c27-117">Na liście **Właściciel** zaznacz nazwę osoby, która będzie zarządzać przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="a9c27-118">Wybór szablonu wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="a9c27-118">Select an email template</span></span>

<span data-ttu-id="a9c27-119">Wykonaj następujące kroki, aby wybrać szablon wiadomości e-mail, który będzie używany do generowania komunikatów powiadomień dotyczących przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="a9c27-120">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="a9c27-121">Na liście **Szablon wiadomości e-mail dla powiadomień o przepływie pracy** zaznacz szablon.</span><span class="sxs-lookup"><span data-stu-id="a9c27-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="a9c27-122">Wprowadzanie instrukcji dla użytkowników</span><span class="sxs-lookup"><span data-stu-id="a9c27-122">Enter instructions for users</span></span>

<span data-ttu-id="a9c27-123">Istnieje możliwość udostępniania instrukcji użytkownikom, którzy będą przesyłać dokumenty do przetwarzania i zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="a9c27-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="a9c27-124">Ci użytkownicy są również zwani *inicjatorami*.</span><span class="sxs-lookup"><span data-stu-id="a9c27-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="a9c27-125">Na przykład tworzysz przepływ pracy zapotrzebowania na zakup i wprowadzasz instrukcje.</span><span class="sxs-lookup"><span data-stu-id="a9c27-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="a9c27-126">Te instrukcje mogą być wyświetlane przez użytkowników wprowadzających zapotrzebowania na zakup na stronie **Zapotrzebowania na zakup**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="a9c27-127">Aby wyświetlić instrukcje, inicjator klika ikonę na pasku komunikatów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="a9c27-128">Aby wprowadzić instrukcje dla użytkowników, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a9c27-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="a9c27-129">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="a9c27-130">W polu **Instrukcje przesyłania** wprowadź instrukcje.</span><span class="sxs-lookup"><span data-stu-id="a9c27-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="a9c27-131">Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="a9c27-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="a9c27-132">Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="a9c27-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="a9c27-133">Aby wstawić symbol zastępczy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a9c27-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="a9c27-134">Kliknij w polu **Instrukcje przesyłania**, aby określić miejsce wyświetlania symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="a9c27-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="a9c27-135">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="a9c27-136">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="a9c27-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="a9c27-137">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-137">Click **Insert**.</span></span>

4. <span data-ttu-id="a9c27-138">Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a9c27-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="a9c27-139">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="a9c27-140">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="a9c27-141">Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.</span><span class="sxs-lookup"><span data-stu-id="a9c27-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="a9c27-142">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="a9c27-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="a9c27-143">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="a9c27-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="a9c27-144">Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 3.</span><span class="sxs-lookup"><span data-stu-id="a9c27-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="a9c27-145">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="a9c27-146">Określ, kiedy ten przepływ pracy jest używany w warunkach aktywacji</span><span class="sxs-lookup"><span data-stu-id="a9c27-146">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="a9c27-147">Można utworzyć wiele przepływów pracy opartych na tym samym typie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-147">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="a9c27-148">Jeśli istnieje wiele przepływów pracy opartych na tym samym typie, trzeba określić warunki używania poszczególnych przepływów pracy w warunkach aktywacji.</span><span class="sxs-lookup"><span data-stu-id="a9c27-148">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="a9c27-149">Jeśli warunki aktywacji nie są spełnione, zostanie użyty domyślny przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-149">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="a9c27-150">Podobnie, jeśli dla danego typu przepływu pracy zdefiniowano tylko jedną konfigurację przepływu pracy, konfiguracja przepływu pracy będzie używana niezależnie od warunków aktywacji.</span><span class="sxs-lookup"><span data-stu-id="a9c27-150">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="a9c27-151">Na przykład można utworzyć przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, na przykład Zapotrzebowania na zakup — Dania lub Zapotrzebowania na zakup — Hiszpania, z następującymi warunkami:</span><span class="sxs-lookup"><span data-stu-id="a9c27-151">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="a9c27-152">Zapotrzebowania na zakup — Dania jest używany, gdy krajem/regionem jest DK.</span><span class="sxs-lookup"><span data-stu-id="a9c27-152">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="a9c27-153">Zapotrzebowania na zakup — Hiszpania jest używany, gdy krajem/regionem jest ES.</span><span class="sxs-lookup"><span data-stu-id="a9c27-153">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="a9c27-154">Aby określić, kiedy ma być używany konfigurowany przepływ pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a9c27-154">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="a9c27-155">W lewym okienku kliknij opcję **Aktywacja**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-155">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="a9c27-156">Zaznacz pole wyboru **Ustaw warunki uruchamiania tego przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-156">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="a9c27-157">Kliknij opcję **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-157">Click **Add condition**.</span></span>
4. <span data-ttu-id="a9c27-158">Służy do wprowadzania warunku.</span><span class="sxs-lookup"><span data-stu-id="a9c27-158">Enter a condition.</span></span>
5. <span data-ttu-id="a9c27-159">Wprowadź wszelkie wymagane dodatkowe warunki.</span><span class="sxs-lookup"><span data-stu-id="a9c27-159">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="a9c27-160">Aby sprawdzić, czy wprowadzone warunki są poprawnie ustawione, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a9c27-160">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>

    1. <span data-ttu-id="a9c27-161">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-161">Click **Test**.</span></span>
    2. <span data-ttu-id="a9c27-162">Na stronie **Warunek testowy przepływu pracy** w obszarze **Sprawdź poprawność warunku** wybierz rekord.</span><span class="sxs-lookup"><span data-stu-id="a9c27-162">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="a9c27-163">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-163">Click **Test**.</span></span> <span data-ttu-id="a9c27-164">System oszacuje rekord i określi, czy rekord spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="a9c27-164">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="a9c27-165">Na przykład jeśli tworzysz przepływ pracy zapotrzebowania na zakup dla Hiszpanii, obszar **Sprawdź poprawność warunku** na stronie zawiera listę zapotrzebowań na zakup.</span><span class="sxs-lookup"><span data-stu-id="a9c27-165">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="a9c27-166">Kliknięcie przycisku **Test** spowoduje uruchomienie systemowego szacowania wybranego zapotrzebowania na zakup w celu sprawdzenia, czy krajem/regionem jest ES.</span><span class="sxs-lookup"><span data-stu-id="a9c27-166">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4. <span data-ttu-id="a9c27-167">Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do strony **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-167">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="a9c27-168">Określanie, kiedy są wysyłane powiadomienia</span><span class="sxs-lookup"><span data-stu-id="a9c27-168">Specify when notifications are sent</span></span>

<span data-ttu-id="a9c27-169">Podczas przesyłania dokumentu do przetwarzania tworzone jest wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-169">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="a9c27-170">Można wysyłać powiadomienia do użytkowników, gdy wystąpienia przepływu pracy oparte na przepływie pracy są uruchamiane, kończone, przerywane lub zatrzymane z powodu błędu.</span><span class="sxs-lookup"><span data-stu-id="a9c27-170">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="a9c27-171">Aby określić, kiedy są wysyłane powiadomienia, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a9c27-171">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="a9c27-172">W lewym okienku kliknij opcję **Powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-172">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="a9c27-173">Zaznacz pole wyboru dla każdego zdarzenia, które powinno uruchamiać powiadomienia:</span><span class="sxs-lookup"><span data-stu-id="a9c27-173">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="a9c27-174">**Rozpoczęte** — wysyłanie powiadomień po uruchomieniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-174">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="a9c27-175">**Zatrzymane** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu błędu.</span><span class="sxs-lookup"><span data-stu-id="a9c27-175">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="a9c27-176">**Ukończono** — wysyłanie powiadomień po zakończeniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-176">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="a9c27-177">**Nieodwracalne** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu nieodwracalnego błędu.</span><span class="sxs-lookup"><span data-stu-id="a9c27-177">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="a9c27-178">**Przerwane** — wysyłanie powiadomień po przerwaniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-178">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="a9c27-179">Zaznacz wiersz zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="a9c27-179">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="a9c27-180">Na karcie **Tekst powiadomienia** wprowadź tekst powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="a9c27-180">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="a9c27-181">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="a9c27-181">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="a9c27-182">Podczas wyświetlania tekstu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="a9c27-182">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="a9c27-183">Aby wstawić symbol zastępczy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a9c27-183">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="a9c27-184">Kliknij w polu, aby określić miejsce wyświetlania symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="a9c27-184">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="a9c27-185">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-185">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="a9c27-186">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="a9c27-186">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="a9c27-187">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-187">Click **Insert**.</span></span>
    5. <span data-ttu-id="a9c27-188">Popularnym dołączanym elementem zastępczym **Tekst powiadomienia** jest „Ostatnie uwagi: %Workflow.Last note%”, który pokazuje wszystkie komentarze z poprzedniego kroku.</span><span class="sxs-lookup"><span data-stu-id="a9c27-188">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="a9c27-189">Aby dodać tłumaczenia tekstu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a9c27-189">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="a9c27-190">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-190">Click **Translations**.</span></span>
    2. <span data-ttu-id="a9c27-191">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-191">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="a9c27-192">Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.</span><span class="sxs-lookup"><span data-stu-id="a9c27-192">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="a9c27-193">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="a9c27-193">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="a9c27-194">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="a9c27-194">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="a9c27-195">Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 5.</span><span class="sxs-lookup"><span data-stu-id="a9c27-195">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="a9c27-196">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-196">Click **Close**.</span></span>

7. <span data-ttu-id="a9c27-197">Na karcie **Adresat** użyj poniższych opcji do określenia, kto ma otrzymywać powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="a9c27-197">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="a9c27-198">Opcja</span><span class="sxs-lookup"><span data-stu-id="a9c27-198">Option</span></span></th>
    <th><span data-ttu-id="a9c27-199">Powiadomienia są tym użytkownikom</span><span class="sxs-lookup"><span data-stu-id="a9c27-199">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="a9c27-200">Aby wysyłać powiadomienia, należy wykonać następujące czynności</span><span class="sxs-lookup"><span data-stu-id="a9c27-200">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="a9c27-201">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="a9c27-201">Participant</span></span></td>
    <td><span data-ttu-id="a9c27-202">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="a9c27-202">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="a9c27-203">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Uczestnik</strong>.</span><span class="sxs-lookup"><span data-stu-id="a9c27-203">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="a9c27-204">Na karcie <strong>Oparte na</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="a9c27-204">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="a9c27-205">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="a9c27-205">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="a9c27-206">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="a9c27-206">Workflow user</span></span></td>
    <td><span data-ttu-id="a9c27-207">Użytkownicy będący uczestnikami tego przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="a9c27-207">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="a9c27-208">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik przepływu pracy</strong>.</span><span class="sxs-lookup"><span data-stu-id="a9c27-208">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="a9c27-209">Na karcie <strong>Użytkownik przepływu pracy</strong> na liście <strong>Użytkownik przepływu pracy</strong> wybierz uczestnika w tym przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="a9c27-209">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="a9c27-210">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="a9c27-210">User</span></span></td>
    <td><span data-ttu-id="a9c27-211">Określeni użytkownicy</span><span class="sxs-lookup"><span data-stu-id="a9c27-211">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="a9c27-212">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="a9c27-212">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="a9c27-213">Na karcie <strong>Użytkownik</strong> lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="a9c27-213">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="a9c27-214">Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="a9c27-214">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="a9c27-215">Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="a9c27-215">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="a9c27-216">Wprowadzanie komentarzy dotyczących zmian zastosowanych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="a9c27-216">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="a9c27-217">Aby wprowadzić komentarze dotyczące zmian zastosowanych w przepływie pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a9c27-217">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="a9c27-218">W lewym okienku kliknij opcję **Uwagi**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-218">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="a9c27-219">W polu **Wprowadź komentarze dotyczące przepływu pracy** wprowadź komentarze.</span><span class="sxs-lookup"><span data-stu-id="a9c27-219">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="a9c27-220">Przejrzyj wprowadzone komentarze.</span><span class="sxs-lookup"><span data-stu-id="a9c27-220">Review your comments.</span></span> <span data-ttu-id="a9c27-221">Po dodaniu komentarzy nie można ich modyfikować.</span><span class="sxs-lookup"><span data-stu-id="a9c27-221">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="a9c27-222">Kliknij przycisk **Dodaj**, aby dodać komentarze do obszaru **Historia komentarzy**.</span><span class="sxs-lookup"><span data-stu-id="a9c27-222">Click **Add** to add your comments to the **Comment history** area.</span></span>
