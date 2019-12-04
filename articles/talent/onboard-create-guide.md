---
title: Tworzenie i wysyłanie przewodnika wdrażania do pracy poprzez Dynamics 365 Talent - Onboard
description: W tym temacie wyjaśniono użycie Microsoft Dynamics 365 Talent - Onboard do utworzenia szablonu dla przewodnika wdrażania do pracy dla nowych pracowników. To zadanie jest podstawowym pierwszym krokiem w zarządzaniu kapitałem ludzkim (HCM) zatrudniania do wycofania strategii.
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a095fe97b05898403b501763204a462ee8dcc12a
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814635"
---
# <a name="create-and-send-an-onboarding-guide-by-using-dynamics-365-talent---onboard"></a><span data-ttu-id="e2c88-104">Tworzenie i wysyłanie przewodnika wdrażania do pracy poprzez Dynamics 365 Talent - Onboard</span><span class="sxs-lookup"><span data-stu-id="e2c88-104">Create and send an onboarding guide by using Dynamics 365 Talent - Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e2c88-105">Microsoft Dynamics 365 Talent: Onboard umożliwia tworzenie przewodników wdrażania do pracy z szablonów, które zostały utworzone samodzielnie, z szablonów, które są dostępne w galerii lub od podstaw.</span><span class="sxs-lookup"><span data-stu-id="e2c88-105">Microsoft Dynamics 365 Talent: Onboard lets you create onboarding guides from templates that you created yourself, from templates that are available in a gallery, or from scratch.</span></span>

<span data-ttu-id="e2c88-106">Po utworzeniu przewodnika wdrażania do pracy można wysłać go do nowego pracownika.</span><span class="sxs-lookup"><span data-stu-id="e2c88-106">After you've created an onboarding guide, you can send it to a new hire.</span></span> <span data-ttu-id="e2c88-107">Alternatywnie można wysłać go do wielu nowych pracowników, których określisz w pliku Microsoft Excel, który można pobrać z aplikacji Onboard.</span><span class="sxs-lookup"><span data-stu-id="e2c88-107">Alternatively, you can send it to multiple new hires that you specify in a Microsoft Excel file that you download from the Onboard app.</span></span>

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a><span data-ttu-id="e2c88-108">Utwórz przewodnik wdrażania do pracy z szablonu i wyślij go do jednego nowego pracownika</span><span class="sxs-lookup"><span data-stu-id="e2c88-108">Create an onboarding guide from a template and send it to a single new hire</span></span>

1. <span data-ttu-id="e2c88-109">W menu po lewej stronie wybierz **Szablony**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-109">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="e2c88-110">W obszarze **Moje szablony**, wybierz szablon, który chcesz skonfigurować jako przewodnik wdrażania do pracy dla nowego pracownika.</span><span class="sxs-lookup"><span data-stu-id="e2c88-110">Under **My templates**, select the template that you want to set up as an onboarding guide for the new hire.</span></span>
3. <span data-ttu-id="e2c88-111">Edytuj szablon jak chcesz.</span><span class="sxs-lookup"><span data-stu-id="e2c88-111">Edit the template as you desire.</span></span> <span data-ttu-id="e2c88-112">Pamiętaj, aby regularnie zapisywać swoją pracę.</span><span class="sxs-lookup"><span data-stu-id="e2c88-112">Be sure to save your work as you go.</span></span>
4. <span data-ttu-id="e2c88-113">Po zakończeniu edytowania szablonu wybierz opcję **Utwórz przewodnik**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-113">When you've finished editing the template, select **Create guide**.</span></span>

    <span data-ttu-id="e2c88-114">[![Utwórz przewodnik wdrażania do pracy z szablonu](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)</span><span class="sxs-lookup"><span data-stu-id="e2c88-114">[![Creating an onboarding guide from a template](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)</span></span>

5. <span data-ttu-id="e2c88-115">W oknie **Utwórz Przewodnik**, w obszarze **Kogo wdrażasz do pracy**, wprowadź imię nowego pracownika lub adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="e2c88-115">In the **Create a guide** window, under **Who are you onboarding**, enter the new hire's name or email address.</span></span> <span data-ttu-id="e2c88-116">Jeśli nowy pracownik nie znajduje się jeszcze w systemie, wybierz pozycję **Dodaj** i wprowadź informacje o pracowniku.</span><span class="sxs-lookup"><span data-stu-id="e2c88-116">If the new hire isn't in the system yet, select **Add now**, and enter the employee's information.</span></span>

    ![[<span data-ttu-id="e2c88-117">Wprowadzanie informacji o przewodniku wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="e2c88-117">Entering information for the onboarding guide</span></span>](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. <span data-ttu-id="e2c88-118">W obszarze **Kiedy zacznie się praca** wybierz datę początkową.</span><span class="sxs-lookup"><span data-stu-id="e2c88-118">Under **When do they start**, select a start date.</span></span>
7. <span data-ttu-id="e2c88-119">Jeśli przewodnik wdrażania do pracy powinien być automatycznie wysyłany do nowego pracownika w określonym dniu, upewnij się , że jest włączona opcja **Zaplanuj datę automatycznego wysyłania**, a następnie wybierz datę automatycznego wysyłania.</span><span class="sxs-lookup"><span data-stu-id="e2c88-119">If the onboarding guide should be sent automatically to the new hire on a specific date, make sure that the **Schedule an automatic send date** option is turned on, and then select the automatic send date.</span></span> <span data-ttu-id="e2c88-120">Aby natychmiast wysłać przewodnik, wyłącz opcję **Zaplanuj datę automatycznego wysyłania**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-120">To send the guide immediately, turn off the **Schedule an automatic send date** option.</span></span>
8. <span data-ttu-id="e2c88-121">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-121">Select **Done**.</span></span>
9. <span data-ttu-id="e2c88-122">Po zakończeniu edytowania przewodnika wdrażania do pracy wybierz pozycję **Wyślij** w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="e2c88-122">When you've finished editing the onboarding guide, select **Send** in the upper-right corner.</span></span> <span data-ttu-id="e2c88-123">Następnie wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="e2c88-123">Then follow one of these steps:</span></span>

    - <span data-ttu-id="e2c88-124">Aby wysłać nowemu pracownikowi łącze do przewodnika wdrażania do pracy, wybierz opcję **Kopiuj łącze**, a następnie wybierz **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-124">To send the new hire a link to the onboarding guide, select **copy a link**, and then select **Copy**.</span></span>
    - <span data-ttu-id="e2c88-125">Aby dostosować adres e-mail przewodnika wdrażania do pracy przed jego wysłaniem, wybierz pozycję **Dostosuj wiadomość e-mail przed wysłaniem**, wybierz pozycję **Dalej**, dostosuj żądany adres e-mail, a następnie wybierz pozycję **Wyślij**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-125">To customize the email for the onboarding guide before you send it, select **Customize the email before sending**, select **Next**, customize the email as you desire, and then select **Send**.</span></span>
    - <span data-ttu-id="e2c88-126">Aby wysłać wiadomość e-mail bez dostosowywania go, wybierz pozycję **Dalej**, a następnie wybierz pozycję **Wyślij**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-126">To send the email without customizing it, select **Next**, and then select **Send**.</span></span>

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a><span data-ttu-id="e2c88-127">Utwórz przewodnik wdrażania do pracy z szablonu i wyślij go do wielu nowych pracowników.</span><span class="sxs-lookup"><span data-stu-id="e2c88-127">Create an onboarding guide from a template and send it to multiple new hires</span></span>

<span data-ttu-id="e2c88-128">Onboard pozwala wysłać przewodnik wdrażania do pracy do wielu nowych pracowników w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="e2c88-128">Onboard lets you send an onboarding guide to multiple new hires at the same time.</span></span>

1. <span data-ttu-id="e2c88-129">W menu po lewej stronie wybierz **Szablony**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-129">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="e2c88-130">W obszarze **Moje szablony**, wybierz szablon, który chcesz skonfigurować jako przewodnik wdrażania do pracy dla nowych pracowników.</span><span class="sxs-lookup"><span data-stu-id="e2c88-130">Under **My templates**, select the template that you want to set up as an onboarding guide for the new hires.</span></span>
3. <span data-ttu-id="e2c88-131">Edytuj szablon jak chcesz.</span><span class="sxs-lookup"><span data-stu-id="e2c88-131">Edit the template as you desire.</span></span> <span data-ttu-id="e2c88-132">Pamiętaj, aby regularnie zapisywać swoją pracę.</span><span class="sxs-lookup"><span data-stu-id="e2c88-132">Be sure to save your work as you go.</span></span>
4. <span data-ttu-id="e2c88-133">Po zakończeniu edytowania szablonu wybierz opcję **Utwórz przewodnik**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-133">When you've finished editing the template, select **Create guide**.</span></span>
5. <span data-ttu-id="e2c88-134">W oknie **Utwórz przewodnik** zaznacz opcję **Musisz wdrożyć do pracy wiele osób jednocześnie**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-134">In the **Create a guide** window, select **Need to onboard multiple people at once**.</span></span>

    <span data-ttu-id="e2c88-135">[![Tworzenie przewodnika wdrażania do pracy dla wielu nowych pracowników](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)</span><span class="sxs-lookup"><span data-stu-id="e2c88-135">[![Creating an onboarding guide for multiple new hires](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)</span></span>

6. <span data-ttu-id="e2c88-136">Wybierz **szablon nowego pracownika**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-136">Select **new hire template**.</span></span>
7. <span data-ttu-id="e2c88-137">Po pobraniu pliku xlsx wybierz opcję **Otwórz**, wprowadź informacje o pracownikach w skoroszycie programu Excel i zapisz skoroszyt.</span><span class="sxs-lookup"><span data-stu-id="e2c88-137">After the .xlsx file is downloaded, select **Open**, enter the employees' information in the Excel workbook, and save the workbook.</span></span>

    <span data-ttu-id="e2c88-138">[![Pobieranie szablonu programu Excel do wysłania przewodnika po wielu nowych pracowników](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)</span><span class="sxs-lookup"><span data-stu-id="e2c88-138">[![Downloading the Excel template for sending the onboarding guide to multiple new hires](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2c88-139">Aby móc edytować skoroszyt, musisz wybrać opcję **Włącz edytowanie** w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="e2c88-139">Before you can edit the workbook, you must select **Enable editing** in Excel.</span></span>
    > 
    > <span data-ttu-id="e2c88-140">[![Włączanie edytowania](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)</span><span class="sxs-lookup"><span data-stu-id="e2c88-140">[![Enabling editing](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)</span></span>

8. <span data-ttu-id="e2c88-141">Przeciągnij skoroszyt programu Excel do wyznaczonego obszaru w oknie **Tworzenie wielu przewodników** lub kliknij w dowolnym miejscu w tym obszarze, aby odszukać plik na komputerze.</span><span class="sxs-lookup"><span data-stu-id="e2c88-141">Drag the Excel workbook to the designated area in the **Create multiple guides** window, or click anywhere in that area to browse for the file on your computer.</span></span>

    <span data-ttu-id="e2c88-142">[![Przeciąganie edytowanego skoroszytu](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)</span><span class="sxs-lookup"><span data-stu-id="e2c88-142">[![Dragging the edited workbook](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)</span></span>

9. <span data-ttu-id="e2c88-143">Po zakończeniu edytowania przewodnika wdrażania do pracy wybierz pozycję **Wyślij** w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="e2c88-143">When you've finished editing the onboarding guide, select **Send** in the upper-right corner.</span></span> <span data-ttu-id="e2c88-144">Następnie wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="e2c88-144">Then follow one of these steps:</span></span>

    - <span data-ttu-id="e2c88-145">Aby wysłać nowemu pracownikowi łącze do przewodnika wdrażania do pracy, wybierz opcję **kopiuj łącze**, a następnie wybierz **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-145">To send the new hires a link to the onboarding guide, select **copy a link**, and then select **Copy**.</span></span>
    - <span data-ttu-id="e2c88-146">Aby dostosować adres e-mail przewodnika wdrażania do pracy przed jego wysłaniem, wybierz pozycję **Dostosuj wiadomość e-mail przed wysłaniem**, wybierz pozycję **Dalej**, dostosuj żądany adres e-mail, a następnie wybierz pozycję **Wyślij**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-146">To customize the email for the onboarding guide before you send it, select **Customize the email before sending**, select **Next**, customize the email as you desire, and then select **Send**.</span></span>
    - <span data-ttu-id="e2c88-147">Aby wysłać wiadomość e-mail bez dostosowywania go, wybierz pozycję **Dalej**, a następnie wybierz pozycję **Wyślij**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-147">To send the email without customizing it, select **Next**, and then select **Send**.</span></span>

## <a name="create-a-guide-without-using-a-template"></a><span data-ttu-id="e2c88-148">Utwórz przewodnik bez używania szablonu</span><span class="sxs-lookup"><span data-stu-id="e2c88-148">Create a guide without using a template</span></span>

<span data-ttu-id="e2c88-149">Nie zawsze trzeba tworzyć przewodnik na podstawie szablonu.</span><span class="sxs-lookup"><span data-stu-id="e2c88-149">You don't always have to create a guide from a template.</span></span> <span data-ttu-id="e2c88-150">Jeśli wolisz, możesz utworzyć przewdonik od podstaw.</span><span class="sxs-lookup"><span data-stu-id="e2c88-150">If you prefer, you can create a guide from scratch instead.</span></span>

1. <span data-ttu-id="e2c88-151">W menu po lewej wybierz opcję **Przewodniki**, a następnie wybierz przycisk **Dodaj** (znak plus \[**+**\]).</span><span class="sxs-lookup"><span data-stu-id="e2c88-151">On the left menu, select **Guides**, and then select the **Add** button (the plus sign \[**+**\]).</span></span>
2. <span data-ttu-id="e2c88-152">W oknie **Utwórz Przewodnik**, w obszarze **Kogo wdrażasz do pracy**, wprowadź imię nowego pracownika lub adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="e2c88-152">In the **Create a guide** window, under **Who are you onboarding**, enter the new hire's name or email address.</span></span> <span data-ttu-id="e2c88-153">Jeśli nowy pracownik nie znajduje się jeszcze w systemie, wybierz pozycję **Dodaj** i wprowadź informacje o pracowniku.</span><span class="sxs-lookup"><span data-stu-id="e2c88-153">If the new hire isn't in the system yet, select **Add now**, and enter the employee's information.</span></span>

    ![[<span data-ttu-id="e2c88-154">Wprowadzanie informacji o przewodniku wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="e2c88-154">Entering information for the onboarding guide</span></span>](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. <span data-ttu-id="e2c88-155">W obszarze **Kiedy zacznie się praca** wybierz datę początkową.</span><span class="sxs-lookup"><span data-stu-id="e2c88-155">Under **When do they start**, select a start date.</span></span>
4. <span data-ttu-id="e2c88-156">Jeśli przewodnik wdrażania do pracy powinien być automatycznie wysyłany do nowego pracownika w określonym dniu, upewnij się , że jest włączona opcja **Zaplanuj datę automatycznego wysyłania**, a następnie wybierz datę automatycznego wysyłania.</span><span class="sxs-lookup"><span data-stu-id="e2c88-156">If the onboarding guide should be sent automatically to the new hire on a specific date, make sure that the **Schedule an automatic send date** option is turned on, and then select the automatic send date.</span></span> <span data-ttu-id="e2c88-157">Aby natychmiast wysłać przewodnik, wyłącz opcję **Zaplanuj datę automatycznego wysyłania**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-157">To send the guide immediately, turn off the **Schedule an automatic send date** option.</span></span>
5. <span data-ttu-id="e2c88-158">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-158">Select **Done**.</span></span>

## <a name="save-a-guide-as-a-template"></a><span data-ttu-id="e2c88-159">Zapisz przewodnik jako szablon</span><span class="sxs-lookup"><span data-stu-id="e2c88-159">Save a guide as a template</span></span>

<span data-ttu-id="e2c88-160">Przewodnik wdrażania do pracy można zapisać jako szablon.</span><span class="sxs-lookup"><span data-stu-id="e2c88-160">You can save an onboarding guide as a template.</span></span> <span data-ttu-id="e2c88-161">W ten sposób można zaoszczędzić czas w przypadku konieczności późniejszego utworzenia kolejnych przewodników.</span><span class="sxs-lookup"><span data-stu-id="e2c88-161">In this way, you can save time when you must create more onboarding guides later.</span></span>

1. <span data-ttu-id="e2c88-162">W menu po lewej stronie wybierz **Przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-162">On the left menu, select **Guides**.</span></span>
2. <span data-ttu-id="e2c88-163">Wybierz przycisk **Więcej** (wielokropek \[**...**\]) dla przewodnika, na podstawie którego chcesz utworzyć szablon, a następnie wybierz opcję **Zapisz jako szablon**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-163">Select the **More** button (the ellipsis \[**...**\]) for the guide that you want to create a template from, and then select **Save as template**.</span></span>

    ![[<span data-ttu-id="e2c88-164">Zapisywanie przewodnika wdrażania do pracy jako szablon</span><span class="sxs-lookup"><span data-stu-id="e2c88-164">Saving an onboarding guide as a template</span></span>](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. <span data-ttu-id="e2c88-165">W oknie **Zapisz jako nowy szablon** wprowadź nazwę nowego szablonu, a następnie wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e2c88-165">In the **Save as a new template** window, enter a name for your new template, and then select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2c88-166">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="e2c88-166">Next steps</span></span>

- [<span data-ttu-id="e2c88-167">Edytowanie przewodników i szablonów wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="e2c88-167">Edit onboarding guides and templates</span></span>](./onboard-edit-guides-templates.md)
- [<span data-ttu-id="e2c88-168">Udostępnianie zawartości innym współautorom</span><span class="sxs-lookup"><span data-stu-id="e2c88-168">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="e2c88-169">Wyświetlanie stanu zadań i dołączania pracowników</span><span class="sxs-lookup"><span data-stu-id="e2c88-169">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="e2c88-170">Tworzenie zespołów rekrutacyjnych w Onboard</span><span class="sxs-lookup"><span data-stu-id="e2c88-170">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="e2c88-171">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e2c88-171">See also</span></span>

- [<span data-ttu-id="e2c88-172">Wypróbuj lub kup aplikację Onboard</span><span class="sxs-lookup"><span data-stu-id="e2c88-172">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="e2c88-173">Nowości i zmiany w Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="e2c88-173">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="e2c88-174">Plany wydań</span><span class="sxs-lookup"><span data-stu-id="e2c88-174">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="e2c88-175">Uzyskiwanie pomocy technicznej dotyczącej rozwiązania Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="e2c88-175">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
