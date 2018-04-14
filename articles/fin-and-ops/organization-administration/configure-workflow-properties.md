---
title: "Konfigurowanie właściwości przepływu pracy"
description: "W tym temacie wyjaśniono sposób konfigurowania różnych właściwości przepływu pracy."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0b8f17285fb845101e9fbec23de7dd7866811bbd
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="configure-workflow-properties"></a><span data-ttu-id="68da6-103">Konfigurowanie właściwości przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="68da6-103">Configure workflow properties</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="68da6-104">W tym temacie wyjaśniono sposób konfigurowania różnych właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="68da6-105">Aby skonfigurować właściwości przepływu pracy, otwórz przepływ pracy w edytorze przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="68da6-106">Kliknij w obszarze roboczym edytora przepływu pracy, a następnie kliknij przycisk **Właściwości**, aby otworzyć stronę **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="68da6-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="68da6-107">Można użyć poniższych procedur, aby skonfigurować różne właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="68da6-108">Nadawanie nazwy przepływowi pracy</span><span class="sxs-lookup"><span data-stu-id="68da6-108">Name the workflow</span></span>
<span data-ttu-id="68da6-109">Należy wykonać następujące kroki, aby wprowadzić nazwę przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-109">Follow these steps to enter a name for the workflow.</span></span>

1.  <span data-ttu-id="68da6-110">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="68da6-110">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="68da6-111">W polu **Nazwa** wprowadź unikatową nazwę przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="68da6-112">Na przykład jeśli tworzysz przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, można nazwać przepływy **Zapotrzebowania na zakup — Dania** lub **Zapotrzebowania na zakup — Hiszpania**.</span><span class="sxs-lookup"><span data-stu-id="68da6-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="68da6-113">Określanie właściciela przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="68da6-113">Specify the workflow owner</span></span>
<span data-ttu-id="68da6-114">Właściciel przepływu pracy jest osobą, która zarządza przepływem pracy i obsługuje go.</span><span class="sxs-lookup"><span data-stu-id="68da6-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="68da6-115">Aby określić właściciela przepływu pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68da6-115">Follow these steps to specify the workflow owner.</span></span>

1.  <span data-ttu-id="68da6-116">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="68da6-116">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="68da6-117">Na liście **Właściciel** zaznacz nazwę osoby, która będzie zarządzać przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="68da6-118">Wybór szablonu wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="68da6-118">Select an email template</span></span>
<span data-ttu-id="68da6-119">Wykonaj następujące kroki, aby wybrać szablon wiadomości e-mail, który będzie używany do generowania komunikatów powiadomień dotyczących przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1.  <span data-ttu-id="68da6-120">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="68da6-120">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="68da6-121">Na liście **Szablon wiadomości e-mail dla powiadomień o przepływie pracy** zaznacz szablon.</span><span class="sxs-lookup"><span data-stu-id="68da6-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="68da6-122">Wprowadzanie instrukcji dla użytkowników</span><span class="sxs-lookup"><span data-stu-id="68da6-122">Enter instructions for users</span></span>
<span data-ttu-id="68da6-123">Istnieje możliwość udostępniania instrukcji użytkownikom, którzy będą przesyłać dokumenty do przetwarzania i zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="68da6-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="68da6-124">Ci użytkownicy są również zwani *inicjatorami*.</span><span class="sxs-lookup"><span data-stu-id="68da6-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="68da6-125">Na przykład tworzysz przepływ pracy zapotrzebowania na zakup i wprowadzasz instrukcje.</span><span class="sxs-lookup"><span data-stu-id="68da6-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="68da6-126">Te instrukcje mogą być wyświetlane przez użytkowników wprowadzających zapotrzebowania na zakup na stronie **Zapotrzebowania na zakup**.</span><span class="sxs-lookup"><span data-stu-id="68da6-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="68da6-127">Aby wyświetlić instrukcje, inicjator klika ikonę na pasku komunikatów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="68da6-128">Aby wprowadzić instrukcje dla użytkowników, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68da6-128">Follow these steps to enter instructions for users.</span></span>

1.  <span data-ttu-id="68da6-129">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="68da6-129">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="68da6-130">W polu **Instrukcje przesyłania** wprowadź instrukcje.</span><span class="sxs-lookup"><span data-stu-id="68da6-130">In the **Submission instructions** field, enter the instructions.</span></span>
3.  <span data-ttu-id="68da6-131">Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="68da6-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="68da6-132">Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="68da6-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="68da6-133">Aby wstawić symbol zastępczy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="68da6-133">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="68da6-134">Kliknij w polu **Instrukcje przesyłania**, aby określić miejsce wyświetlania symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="68da6-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="68da6-135">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="68da6-135">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="68da6-136">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="68da6-136">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="68da6-137">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="68da6-137">Click **Insert**.</span></span>

4.  <span data-ttu-id="68da6-138">Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="68da6-138">To add translations of the instructions, follow these steps:</span></span>
    1.  <span data-ttu-id="68da6-139">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="68da6-139">Click **Translations**.</span></span>
    2.  <span data-ttu-id="68da6-140">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="68da6-140">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="68da6-141">Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.</span><span class="sxs-lookup"><span data-stu-id="68da6-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="68da6-142">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="68da6-142">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="68da6-143">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="68da6-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="68da6-144">Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 3.</span><span class="sxs-lookup"><span data-stu-id="68da6-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6.  <span data-ttu-id="68da6-145">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="68da6-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used"></a><span data-ttu-id="68da6-146">Określanie, kiedy jest używany ten przepływ pracy</span><span class="sxs-lookup"><span data-stu-id="68da6-146">Specify when this workflow is used</span></span>
<span data-ttu-id="68da6-147">Można utworzyć wiele przepływów pracy opartych na tym samym typie.</span><span class="sxs-lookup"><span data-stu-id="68da6-147">You can create multiple workflows that are based on the same type.</span></span> <span data-ttu-id="68da6-148">Na przykład można utworzyć przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, na przykład Zapotrzebowania na zakup — Dania lub Zapotrzebowania na zakup — Hiszpania.</span><span class="sxs-lookup"><span data-stu-id="68da6-148">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain.</span></span> <span data-ttu-id="68da6-149">Jeśli istnieje wiele przepływów pracy opartych na tym samym typie, trzeba określić warunki używania poszczególnych przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-149">When you have multiple workflows that are based on the same type, you must specify when each workflow is used.</span></span> <span data-ttu-id="68da6-150">Dla poprzedniego przykładu należałoby określić następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="68da6-150">For the preceding example, you specify the following conditions:</span></span>

-   <span data-ttu-id="68da6-151">Zapotrzebowania na zakup — Dania jest używany, gdy krajem/regionem jest DK.</span><span class="sxs-lookup"><span data-stu-id="68da6-151">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
-   <span data-ttu-id="68da6-152">Zapotrzebowania na zakup — Hiszpania jest używany, gdy krajem/regionem jest ES.</span><span class="sxs-lookup"><span data-stu-id="68da6-152">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="68da6-153">Aby określić, kiedy ma być używany konfigurowany przepływ pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68da6-153">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1.  <span data-ttu-id="68da6-154">W lewym okienku kliknij opcję **Aktywacja**.</span><span class="sxs-lookup"><span data-stu-id="68da6-154">In the left pane, click **Activation**.</span></span>
2.  <span data-ttu-id="68da6-155">Zaznacz pole wyboru **Ustaw warunki uruchamiania tego przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="68da6-155">Select the **Set the conditions for running this workflow** check box.</span></span>
3.  <span data-ttu-id="68da6-156">Kliknij opcję **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="68da6-156">Click **Add condition**.</span></span>
4.  <span data-ttu-id="68da6-157">Służy do wprowadzania warunku.</span><span class="sxs-lookup"><span data-stu-id="68da6-157">Enter a condition.</span></span>
5.  <span data-ttu-id="68da6-158">Wprowadź wszelkie wymagane dodatkowe warunki.</span><span class="sxs-lookup"><span data-stu-id="68da6-158">Enter any additional conditions that are required.</span></span>
6.  <span data-ttu-id="68da6-159">Aby sprawdzić, czy wprowadzone warunki są poprawnie ustawione, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="68da6-159">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>
    1.  <span data-ttu-id="68da6-160">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="68da6-160">Click **Test**.</span></span>
    2.  <span data-ttu-id="68da6-161">Na stronie **Warunek testowy przepływu pracy** w obszarze **Sprawdź poprawność warunku** wybierz rekord.</span><span class="sxs-lookup"><span data-stu-id="68da6-161">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3.  <span data-ttu-id="68da6-162">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="68da6-162">Click **Test**.</span></span> <span data-ttu-id="68da6-163">System oszacuje rekord i określi, czy rekord spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="68da6-163">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="68da6-164">Na przykład jeśli tworzysz przepływ pracy zapotrzebowania na zakup dla Hiszpanii, obszar **Sprawdź poprawność warunku** na stronie zawiera listę zapotrzebowań na zakup.</span><span class="sxs-lookup"><span data-stu-id="68da6-164">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="68da6-165">Kliknięcie przycisku **Test** spowoduje uruchomienie systemowego szacowania wybranego zapotrzebowania na zakup w celu sprawdzenia, czy krajem/regionem jest ES.</span><span class="sxs-lookup"><span data-stu-id="68da6-165">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4.  <span data-ttu-id="68da6-166">Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do strony **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="68da6-166">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="68da6-167">Określanie, kiedy są wysyłane powiadomienia</span><span class="sxs-lookup"><span data-stu-id="68da6-167">Specify when notifications are sent</span></span>
<span data-ttu-id="68da6-168">Podczas przesyłania dokumentu do przetwarzania tworzone jest wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-168">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="68da6-169">Można wysyłać powiadomienia do użytkowników, gdy wystąpienia przepływu pracy oparte na przepływie pracy są uruchamiane, kończone, przerywane lub zatrzymane z powodu błędu.</span><span class="sxs-lookup"><span data-stu-id="68da6-169">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="68da6-170">Aby określić, kiedy są wysyłane powiadomienia, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68da6-170">Follow these steps to specify when notifications are sent.</span></span>

1.  <span data-ttu-id="68da6-171">W lewym okienku kliknij opcję **Powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="68da6-171">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="68da6-172">Zaznacz pole wyboru dla każdego zdarzenia, które powinno uruchamiać powiadomienia:</span><span class="sxs-lookup"><span data-stu-id="68da6-172">Select the check box for each event that should trigger notifications:</span></span>
    -   <span data-ttu-id="68da6-173">**Rozpoczęte** — wysyłanie powiadomień po uruchomieniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-173">**Started** – Send notifications when a workflow instance is started.</span></span>
    -   <span data-ttu-id="68da6-174">**Zatrzymane** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu błędu.</span><span class="sxs-lookup"><span data-stu-id="68da6-174">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    -   <span data-ttu-id="68da6-175">**Ukończono** — wysyłanie powiadomień po zakończeniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-175">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    -   <span data-ttu-id="68da6-176">**Nieodwracalne** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu nieodwracalnego błędu.</span><span class="sxs-lookup"><span data-stu-id="68da6-176">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    -   <span data-ttu-id="68da6-177">**Przerwane** — wysyłanie powiadomień po przerwaniu wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-177">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3.  <span data-ttu-id="68da6-178">Zaznacz wiersz zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="68da6-178">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="68da6-179">Na karcie **Tekst powiadomienia** wprowadź tekst powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="68da6-179">On the **Notification text** tab, enter the text of the notification.</span></span>
5.  <span data-ttu-id="68da6-180">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="68da6-180">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="68da6-181">Podczas wyświetlania tekstu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="68da6-181">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="68da6-182">Aby wstawić symbol zastępczy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="68da6-182">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="68da6-183">Kliknij w polu, aby określić miejsce wyświetlania symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="68da6-183">Click in the field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="68da6-184">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="68da6-184">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="68da6-185">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="68da6-185">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="68da6-186">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="68da6-186">Click **Insert**.</span></span>

6.  <span data-ttu-id="68da6-187">Aby dodać tłumaczenia tekstu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="68da6-187">To add translations of the text, follow these steps:</span></span>
    1.  <span data-ttu-id="68da6-188">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="68da6-188">Click **Translations**.</span></span>
    2.  <span data-ttu-id="68da6-189">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="68da6-189">On the page that appears, Click **Add**.</span></span>
    3.  <span data-ttu-id="68da6-190">Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.</span><span class="sxs-lookup"><span data-stu-id="68da6-190">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="68da6-191">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="68da6-191">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="68da6-192">Aby spersonalizować tekst, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="68da6-192">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="68da6-193">Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 5.</span><span class="sxs-lookup"><span data-stu-id="68da6-193">For instructions about how to enter a placeholder, see step 5.</span></span>
    6.  <span data-ttu-id="68da6-194">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="68da6-194">Click **Close**.</span></span>

7.  <span data-ttu-id="68da6-195">Na karcie **Adresat** użyj poniższych opcji do określenia, kto ma otrzymywać powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="68da6-195">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="68da6-196">Opcja</span><span class="sxs-lookup"><span data-stu-id="68da6-196">Option</span></span></th>
    <th><span data-ttu-id="68da6-197">Powiadomienia są tym użytkownikom</span><span class="sxs-lookup"><span data-stu-id="68da6-197">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="68da6-198">Aby wysyłać powiadomienia, należy wykonać następujące czynności</span><span class="sxs-lookup"><span data-stu-id="68da6-198">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="68da6-199">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="68da6-199">Participant</span></span></td>
    <td><span data-ttu-id="68da6-200">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="68da6-200">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="68da6-201">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Uczestnik</strong>.</span><span class="sxs-lookup"><span data-stu-id="68da6-201">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="68da6-202">Na karcie <strong>Oparte na</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="68da6-202">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="68da6-203">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="68da6-203">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="68da6-204">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="68da6-204">Workflow user</span></span></td>
    <td><span data-ttu-id="68da6-205">Użytkownicy będący uczestnikami tego przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="68da6-205">Users who are participants in this workflow</span></span></td>
    <td><ol>
    <li><span data-ttu-id="68da6-206">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik przepływu pracy</strong>.</span><span class="sxs-lookup"><span data-stu-id="68da6-206">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="68da6-207">Na karcie <strong>Użytkownik przepływu pracy</strong> na liście <strong>Użytkownik przepływu pracy</strong> wybierz uczestnika w tym przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="68da6-207">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="68da6-208">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="68da6-208">User</span></span></td>
    <td><span data-ttu-id="68da6-209">Konkretny użytkownik programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="68da6-209">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="68da6-210">Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="68da6-210">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="68da6-211">Na karcie <strong>Użytkownik</strong> lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="68da6-211">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="68da6-212">Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="68da6-212">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="68da6-213">Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="68da6-213">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="68da6-214">Wprowadzanie komentarzy dotyczących zmian zastosowanych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="68da6-214">Enter comments about the changes that you made to the workflow</span></span>
<span data-ttu-id="68da6-215">Aby wprowadzić komentarze dotyczące zmian zastosowanych w przepływie pracy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68da6-215">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1.  <span data-ttu-id="68da6-216">W lewym okienku kliknij opcję **Uwagi**.</span><span class="sxs-lookup"><span data-stu-id="68da6-216">In the left pane, click **Notes**.</span></span>
2.  <span data-ttu-id="68da6-217">W polu **Wprowadź komentarze dotyczące przepływu pracy** wprowadź komentarze.</span><span class="sxs-lookup"><span data-stu-id="68da6-217">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3.  <span data-ttu-id="68da6-218">Przejrzyj wprowadzone komentarze.</span><span class="sxs-lookup"><span data-stu-id="68da6-218">Review your comments.</span></span> <span data-ttu-id="68da6-219">Po dodaniu komentarzy nie można ich modyfikować.</span><span class="sxs-lookup"><span data-stu-id="68da6-219">After you add comments, you can't modify them.</span></span>
4.  <span data-ttu-id="68da6-220">Kliknij przycisk **Dodaj**, aby dodać komentarze do obszaru **Historia komentarzy**.</span><span class="sxs-lookup"><span data-stu-id="68da6-220">Click **Add** to add your comments to the **Comment history** area.</span></span>





