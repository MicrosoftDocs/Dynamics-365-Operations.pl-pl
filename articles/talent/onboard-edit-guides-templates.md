---
title: Edytowanie przewodników wdrażania do pracy i szablonów w Dynamics 365 Talent - Onboard
description: W tym temacie opisano sposób dodawania działań i innych informacji do przewodników wdrażania do pracy i szablonów w Dynamics 365 Talent - Onboard rozwiązania Microsoft.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
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
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 291f7aefac61c26dfab81cfff28c1c6580d46de5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462250"
---
# <a name="edit-onboarding-guides-and-templates"></a><span data-ttu-id="bbe58-103">Edytowanie przewodników i szablonów wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="bbe58-103">Edit onboarding guides and templates</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bbe58-104">Po utworzeniu przewodnika lub szablonu w systemie Microsoft Dynamics 365 Talent: Onboard należy dodać do niego wprowadzenie, działania, kontakty i zasoby.</span><span class="sxs-lookup"><span data-stu-id="bbe58-104">After you create an onboarding guide or template in Microsoft Dynamics 365 Talent: Onboard, you must add an introduction, activities, contacts, and resources.</span></span> <span data-ttu-id="bbe58-105">Onboard umożliwia dołączanie bogatej zawartości do przewdoników wdrażania do pracy, w tym:</span><span class="sxs-lookup"><span data-stu-id="bbe58-105">Onboard lets you include rich content in your onboarding guides, including:</span></span>

- <span data-ttu-id="bbe58-106">Filmiki YouTube</span><span class="sxs-lookup"><span data-stu-id="bbe58-106">YouTube videos</span></span>
- <span data-ttu-id="bbe58-107">Prezentacje aplikacji Microsoft Sway</span><span class="sxs-lookup"><span data-stu-id="bbe58-107">Microsoft Sway presentations</span></span>
- <span data-ttu-id="bbe58-108">Aplikacje Microsoft PowerApps</span><span class="sxs-lookup"><span data-stu-id="bbe58-108">Microsoft PowerApps apps</span></span>
- <span data-ttu-id="bbe58-109">Filmiki Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="bbe58-109">Microsoft Stream videos</span></span>
- <span data-ttu-id="bbe58-110">Formularze Microsoft Forms</span><span class="sxs-lookup"><span data-stu-id="bbe58-110">Microsoft Forms forms</span></span>
- <span data-ttu-id="bbe58-111">Ramki iframe, które zawierają zawartość sieci Web</span><span class="sxs-lookup"><span data-stu-id="bbe58-111">Iframes that contains web content</span></span>

## <a name="edit-introductions-or-activities-imported-from-a-template"></a><span data-ttu-id="bbe58-112">Umożliwia edytowanie wstępów i działań zaimportowanych z szablonu</span><span class="sxs-lookup"><span data-stu-id="bbe58-112">Edit introductions or activities imported from a template</span></span>

<span data-ttu-id="bbe58-113">W przypadku utworzenia przewodnika wdrażania do pracy na podstawie szablonu lub zaimportowaniu działań z jednego szablonu do innego zostanie wyświetlony przycisk **Zablokuj** w zaimportowanych działaniach.</span><span class="sxs-lookup"><span data-stu-id="bbe58-113">If you create an onboarding guide from a template, or if you import activities from one template into another, you'll notice a **Lock** button on the imported activities.</span></span> <span data-ttu-id="bbe58-114">Są to tzw. *działania zarządzane*.</span><span class="sxs-lookup"><span data-stu-id="bbe58-114">These are called *managed activities*.</span></span>

<span data-ttu-id="bbe58-115">[![Zarządzane działania](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span><span class="sxs-lookup"><span data-stu-id="bbe58-115">[![Managed activities](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span></span>

<span data-ttu-id="bbe58-116">Po wybraniu zarządzanego działania można wyświetlić szablon źródłowy u góry działania.</span><span class="sxs-lookup"><span data-stu-id="bbe58-116">When you select a managed activity, you can see the source template at the top of the activity.</span></span>

<span data-ttu-id="bbe58-117">[![Źródło zarządzanego działania](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span><span class="sxs-lookup"><span data-stu-id="bbe58-117">[![Managed activity source](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span></span>

<span data-ttu-id="bbe58-118">Jeśli użytkownik edytuje działanie w szablonie, Onboard przekaże zmiany do wszystkich szablonów i niewysłanych przewodników opartych na tym szablonie.</span><span class="sxs-lookup"><span data-stu-id="bbe58-118">If you edit an activity in a template, Onboard will push the changes to all templates and unsent guides that are based on that template.</span></span> <span data-ttu-id="bbe58-119">Jeśli wybierzesz niewysłany przewodnik na podstawie edytowanego szablonu, a następnie wybierzesz kartę **Działania** w przewodniku, zobaczysz informację, że poradnik został zmieniony.</span><span class="sxs-lookup"><span data-stu-id="bbe58-119">If you select an unsent guide based on a template you edited and then select the **Activities** tab in the guide, you will see a notice that your guide has changed.</span></span> <span data-ttu-id="bbe58-120">Aby anulować powiadomienie, należy wybrać **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-120">To dismiss the notification, select **OK**.</span></span> 

<span data-ttu-id="bbe58-121">[![Zmień powiadomienie](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span><span class="sxs-lookup"><span data-stu-id="bbe58-121">[![Change notification](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span></span>

<span data-ttu-id="bbe58-122">Obok zaktualizowanych działań zostanie wyświetlona czarna kropka.</span><span class="sxs-lookup"><span data-stu-id="bbe58-122">You'll see a black dot next to the updated activities.</span></span>

<span data-ttu-id="bbe58-123">[![Zmienione działanie](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span><span class="sxs-lookup"><span data-stu-id="bbe58-123">[![Changed activity](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span></span>

<span data-ttu-id="bbe58-124">Nie można edytować działań zarządzanych poza oryginalnym szablonem, z wyjątkiem dodawania osoby przydzielonej, terminu lub innych informacji w prawej sekcji działania.</span><span class="sxs-lookup"><span data-stu-id="bbe58-124">You can't edit managed activities outside of the original template, except to add an assignee, due date, or other information in the right-hand section of the activity.</span></span>

<span data-ttu-id="bbe58-125">Jeśli chcesz edytować zarządzane działanie lub jeśli nie chcesz, aby dana czynność otrzymywała aktualizacje z szablonu, z którego pochodzi, wybierz przycisk **Zablokuj** dla tego działania.</span><span class="sxs-lookup"><span data-stu-id="bbe58-125">If you want to edit a managed activity, or if you don't want an activity to receive updates from the template it came from, select the **Lock** button for that activity.</span></span> <span data-ttu-id="bbe58-126">Przycisk **Zablokuj** zniknie.</span><span class="sxs-lookup"><span data-stu-id="bbe58-126">The **Lock** button will disappear.</span></span> <span data-ttu-id="bbe58-127">Działanie nie będzie już zarządzane przez oryginalny szablon i nie będzie już otrzymywać aktualizacji z tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-127">The activity will no longer be managed by the original template, and it will no longer receive updates from that template.</span></span> <span data-ttu-id="bbe58-128">Aktualizacje wprowadzane do działania nie mają wpływu na oryginalny szablon.</span><span class="sxs-lookup"><span data-stu-id="bbe58-128">Updates you make to an activity do not affect the original template.</span></span>

<span data-ttu-id="bbe58-129">W przypadku usunięcia działania z przewodnika i wprowadzenia zmian z szablonu tego przewodnika działanie pozostanie usunięte w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="bbe58-129">If you delete an activity from a guide and push changes from that guide's template, the activity will remain deleted in the guide.</span></span>

> [!NOTE]
> <span data-ttu-id="bbe58-130">W szablonach nie są zarządzane kontakty i zasoby.</span><span class="sxs-lookup"><span data-stu-id="bbe58-130">Contacts and resources aren't managed by templates.</span></span> <span data-ttu-id="bbe58-131">Ponadto sekcje nie są zarządzane, więc w przypadku dodania lub edycji sekcji w szablonie zmiany nie zostaną przesunięte do żadnych przewodników lub szablonów używających tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-131">In addition, sections aren't managed, so if you add or edit a section in a template, the changes won't be pushed to any guides or templates that use that template.</span></span>
> 
> <span data-ttu-id="bbe58-132">W przypadku dodania nowych działań do szablonu nowe działania są przekazywane do przewodników i szablonów opartych na tym szablonie, a nowe działania są wyświetlane u góry.</span><span class="sxs-lookup"><span data-stu-id="bbe58-132">If you add new activities to a template, the new activities are pushed to guides and templates based on that template, and the new activities display at the top.</span></span>

## <a name="import-activities-from-another-template"></a><span data-ttu-id="bbe58-133">Importowanie działań z innego szablonu</span><span class="sxs-lookup"><span data-stu-id="bbe58-133">Import activities from another template</span></span>

<span data-ttu-id="bbe58-134">Istnieje możliwość importowania działań z jednego lub większej liczby szablonów do przewodnika lub szablonu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-134">You can import activities from one or more templates into a guide or template.</span></span>

1. <span data-ttu-id="bbe58-135">Wybierz przewodnik lub szablon, który ma zostać edytowany.</span><span class="sxs-lookup"><span data-stu-id="bbe58-135">Select the guide or template you want to edit.</span></span>

2. <span data-ttu-id="bbe58-136">Kliknij kartę **Działania**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-136">Select the **Activities** tab.</span></span>

3. <span data-ttu-id="bbe58-137">Wybierz kartę **Import** w sekcji po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="bbe58-137">Select the **Import** tab in the section on the right.</span></span>

   <span data-ttu-id="bbe58-138">[![Importowanie działań](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span><span class="sxs-lookup"><span data-stu-id="bbe58-138">[![Import activities](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span></span>

4. <span data-ttu-id="bbe58-139">Aby wyświetlić podgląd zadań na nowej karcie w przeglądarce, wybierz przycisk **Otwórz w nowej karcie** na dowolnym szablonie.</span><span class="sxs-lookup"><span data-stu-id="bbe58-139">To preview the tasks in a new tab in your browser, select the **Open in new tab** button on any template.</span></span>

   <span data-ttu-id="bbe58-140">[![Importowanie działań](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span><span class="sxs-lookup"><span data-stu-id="bbe58-140">[![Import activities](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span></span>

5. <span data-ttu-id="bbe58-141">Przeciągnij i upuść żądany szablon do miejsca w szablonie przewodnika, gdzie mają się pojawiać działania.</span><span class="sxs-lookup"><span data-stu-id="bbe58-141">Drag and drop the desired template to the place in your guide template where you want the activities to appear.</span></span> <span data-ttu-id="bbe58-142">Kontynuuj edytowanie przewodnika lub szablonu</span><span class="sxs-lookup"><span data-stu-id="bbe58-142">Continue editing your guide or template.</span></span>

<span data-ttu-id="bbe58-143">Zaimportowane działania będą zawierać przycisk **Zablokuj**, który wskazuje działania zarządzane przez szablon, z którego zaimportowano dane.</span><span class="sxs-lookup"><span data-stu-id="bbe58-143">The imported activities will contain a **Lock** button, which indicates those activities are managed by the template you imported from.</span></span> <span data-ttu-id="bbe58-144">Po wprowadzeniu zmian w zaimportowanym szablonie działania te będą aktualizowane w szablonie, do którego zostały zaimportowane.</span><span class="sxs-lookup"><span data-stu-id="bbe58-144">When you make changes to the template you imported, those activities will update in the template you imported them to.</span></span> <span data-ttu-id="bbe58-145">Jednak zmiany nie będą automatycznie przekazywane do żadnych prowadnic utworzonych na podstawie zaimportowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-145">However, the changes will not be pushed automatically to any guides created from the template you imported to.</span></span>

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a><span data-ttu-id="bbe58-146">Wypchnij zmiany z szablonu do innych szablonów lub przewodników</span><span class="sxs-lookup"><span data-stu-id="bbe58-146">Push changes from a template to other templates or guides</span></span>

<span data-ttu-id="bbe58-147">W przypadku edytowania szablonu zawierającego działania używane w innych szablonach lub przewodnikach należy wprowadzić zmiany, jeśli mają być wyświetlane w innych szablonach lub przewodnikach.</span><span class="sxs-lookup"><span data-stu-id="bbe58-147">If you edit a template that contains activities that are used in other templates or guides, you must push the changes if you want them to appear in the other templates or guides.</span></span>

<span data-ttu-id="bbe58-148">Jeśli nie masz pewności, czy działania szablonu są używane w innych szablonach lub w przewodnikach, wybierz opcję **Używane** na karcie, aby zobaczyć, gdzie są wyświetlane te działania.</span><span class="sxs-lookup"><span data-stu-id="bbe58-148">If you're not sure whether your template's activities are used in other templates or guides, select the **Used in** tab to view where those activities appear.</span></span>

   <span data-ttu-id="bbe58-149">[![Zobacz przewodniki i szablony, w których są używane działania](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span><span class="sxs-lookup"><span data-stu-id="bbe58-149">[![View guides and templates activities are used in](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span></span>

<span data-ttu-id="bbe58-150">Aby wprowadzić zmiany:</span><span class="sxs-lookup"><span data-stu-id="bbe58-150">To push your changes:</span></span>

1. <span data-ttu-id="bbe58-151">Aby zapisać zmiany, należy zaznaczyć przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-151">Save your changes by selecting the **Save** button.</span></span> <span data-ttu-id="bbe58-152">W przeciwnym razie zostanie wyświetlony monit o zapisanie zmian w następnym kroku.</span><span class="sxs-lookup"><span data-stu-id="bbe58-152">If you don't do this, you'll be prompted to save your changes in the next step.</span></span>

2. <span data-ttu-id="bbe58-153">Wybierz **Wyślij te zmiany**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-153">Select **Push these changes**.</span></span>

   
## <a name="add-or-edit-an-introduction"></a><span data-ttu-id="bbe58-154">Dodawanie lub edytowanie wprowadzenia</span><span class="sxs-lookup"><span data-stu-id="bbe58-154">Add or edit an introduction</span></span>

1. <span data-ttu-id="bbe58-155">Na karcie **Wprowadzenie** wprowadź tytuł przewodnika i komunikat otwierający.</span><span class="sxs-lookup"><span data-stu-id="bbe58-155">On the **Introduction** tab, enter a title for your guide and an opening message.</span></span> <span data-ttu-id="bbe58-156">Aby skorzystać z przykładowego tekstu, wybierz opcję **Używaj tego komunikatu**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-156">To use the sample text, select **Use this message**.</span></span>

    <span data-ttu-id="bbe58-157">[![Karta wprowadzenie w szablonie Onboard](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span><span class="sxs-lookup"><span data-stu-id="bbe58-157">[![Introduction tab in an Onboard template](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span></span>

2. <span data-ttu-id="bbe58-158">Użyj przycisków formatowania, aby wywoływać tekst w razie konieczności lub dodać obrazy lub łącza.</span><span class="sxs-lookup"><span data-stu-id="bbe58-158">Use the formatting buttons to call out text as you require, or to add images or links.</span></span>
3. <span data-ttu-id="bbe58-159">Wybierz **Zapisz**, żeby zapisać pracę.</span><span class="sxs-lookup"><span data-stu-id="bbe58-159">Select **Save** to save your work.</span></span>

## <a name="add-or-edit-activities"></a><span data-ttu-id="bbe58-160">Dodaj lub edytuj działania</span><span class="sxs-lookup"><span data-stu-id="bbe58-160">Add or edit activities</span></span>

1. <span data-ttu-id="bbe58-161">Na karcie **Działania** przeciągnij elementy z prawej strony do obszaru edycji.</span><span class="sxs-lookup"><span data-stu-id="bbe58-161">On the **Activities** tab, drag items from the right to the editing area.</span></span>
2. <span data-ttu-id="bbe58-162">Aby zorganizować przewodnik w sekcjach, przeciągnij element **Nowa sekcja** do obszaru edycji, a następnie wprowadź nazwę i opcjonalny opis sekcji.</span><span class="sxs-lookup"><span data-stu-id="bbe58-162">To organize your guide into sections, drag the **New section** item to the editing area, and enter a name and an optional description for the section.</span></span>

    ![[<span data-ttu-id="bbe58-163">Dodawanie nowej sekcji do przewodnika lub szablonu wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="bbe58-163">Adding a new section to an onboarding guide or template</span></span>](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. <span data-ttu-id="bbe58-164">Aby dodać działania dotyczące nowego zatrudnienia, przeciągnij element **Nowe działanie** do obszaru edycji, a następnie wprowadź nazwę i opis działania.</span><span class="sxs-lookup"><span data-stu-id="bbe58-164">To add activities for your new hire to complete, drag the **New activity** item to the editing area, and enter a name and description for the activity.</span></span>

    ![[<span data-ttu-id="bbe58-165">Dodawanie nowego działania do przewodnika lub szablonu wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="bbe58-165">Adding a new activity to an onboarding guide or template</span></span>](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. <span data-ttu-id="bbe58-166">Dodaj zawartość sformatowaną do przewodnika wdrażania do pracy:</span><span class="sxs-lookup"><span data-stu-id="bbe58-166">Add rich content to your onboarding guide:</span></span>

    - <span data-ttu-id="bbe58-167">Aby dodać filmik YouTube, przeciągnij element **YouTube** do obszaru edycji, wprowadź nazwę i opis działania, a następnie wprowadź adres URL wideo YouTube.</span><span class="sxs-lookup"><span data-stu-id="bbe58-167">To add a YouTube video, drag the **YouTube** item to the editing area, enter a name and description for the activity, and enter the URL for the YouTube video.</span></span>
    - <span data-ttu-id="bbe58-168">Aby dodać prezentację lub biuletyn w aplikacji Sway, przeciągnij element **Sway** do obszaru edycji, wprowadź nazwę i opis działania, a następnie wprowadź osadzony adres URL prezentacji lub biuletynu dla aplikacji Sway.</span><span class="sxs-lookup"><span data-stu-id="bbe58-168">To add a Sway presentation or newsletter, drag the **Sway** item to the editing area, enter a name and description for the activity, and enter the embedded URL for the Sway presentation or newsletter.</span></span>
    - <span data-ttu-id="bbe58-169">Aby dodać aplikację Microsoft Power Apps, przeciągnij element **Power Apps** do obszaru edycji, wprowadź nazwę i opis działania, a następnie wybierz aplikację Power Apps lub wprowadź identyfikator aplikacji Power Apps.</span><span class="sxs-lookup"><span data-stu-id="bbe58-169">To add a Microsoft Power Apps app, drag the **Power Apps** item to the editing area, enter a name and description for the activity, and either select the Power Apps app or enter the Power Apps app ID.</span></span>
    - <span data-ttu-id="bbe58-170">Aby dodać filmik Microsoft Stream, przeciągnij element **Microsoft Stream** do obszaru edycji, wprowadź nazwę i opis działania, a następnie wprowadź adres URL wideo Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="bbe58-170">To add a Microsoft Stream video, drag the **Microsoft Stream** item to the editing area, enter a name and description for the activity, and enter the URL for the Microsoft Stream video.</span></span>
    - <span data-ttu-id="bbe58-171">Aby dodać formularz programu Microsoft Forms, przeciągnij element programu **Microsoft Forms** do obszaru edycji, wprowadź nazwę i opis działania, wprowadź adres URL formularza Microsoft Forms i określ rozmiar obszaru ekranu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-171">To add a Microsoft Forms form, drag the **Microsoft Forms** item to the editing area, enter a name and description for the activity, enter the URL for the Microsoft Forms form, and specify the size of the screen area.</span></span>
    - <span data-ttu-id="bbe58-172">Aby dodać iframe zawierające treści internetowe, przeciągnij element programu **Treści internetowe (iframe)** do obszaru edycji, wprowadź nazwę i opis działania, wprowadź adres URL i treść oraz określ rozmiar obszaru ekranu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-172">To add an iframe that contains web content, drag the **Web Content (iframe)** item to the editing area, enter a name and description for the activity, enter the URL for the web content, and specify the size of the screen area.</span></span>

    ![[<span data-ttu-id="bbe58-173">Dodawanie zawartości sformatowanej do przewodnika lub szablonu wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="bbe58-173">Adding rich content to an onboarding guide or template</span></span>](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. <span data-ttu-id="bbe58-174">Opcjonalnie: w obszarze po prawej stronie każdego działania należy przypisać działanie do określonej osoby lub roli, dodać termin płatności i osobę kontaktową, a następnie przypisać kolor kategorii.</span><span class="sxs-lookup"><span data-stu-id="bbe58-174">Optional: In the area on the right of each activity, assign the activity to a specific person or role, add a due date and contact person, and assign a category color.</span></span> <span data-ttu-id="bbe58-175">Podczas przypisywania działania do osoby lub roli tworzone jest zadanie dla każdej jednostki.</span><span class="sxs-lookup"><span data-stu-id="bbe58-175">When you assign an activity to a person or role, a task is created for each individual.</span></span> <span data-ttu-id="bbe58-176">To zadanie pojawia się w menu **Zadania** w Onboard.</span><span class="sxs-lookup"><span data-stu-id="bbe58-176">This task appears on the **Tasks** menu in Onboard.</span></span>

    <span data-ttu-id="bbe58-177">[![Przypisywanie działania do przewodnika lub szablonu wdrażania do pracy](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span><span class="sxs-lookup"><span data-stu-id="bbe58-177">[![Assigning an activity in an onboarding guide or template](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span></span>

3. <span data-ttu-id="bbe58-178">Wybierz **Zapisz**, żeby zapisać pracę.</span><span class="sxs-lookup"><span data-stu-id="bbe58-178">Select **Save** to save your work.</span></span>

<span data-ttu-id="bbe58-179">Aby usunąć działanie lub sekcję, wybierz przycisk **Usuń** (symbol kosza) znajdujący się w prawym górnym rogu działania lub sekcji.</span><span class="sxs-lookup"><span data-stu-id="bbe58-179">To delete an activity or section, select the **Delete** button (the trash can symbol) in the upper-right corner of the activity or section.</span></span>

<span data-ttu-id="bbe58-180">Aby zmienić kolejność działań i sekcji, przeciągnij je do nowej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="bbe58-180">To rearrange activities and sections, drag them to a new location.</span></span>

## <a name="add-or-edit-contacts"></a><span data-ttu-id="bbe58-181">Dodaj lub edytuj kontakty</span><span class="sxs-lookup"><span data-stu-id="bbe58-181">Add or edit contacts</span></span>

<span data-ttu-id="bbe58-182">Możesz dodać osoby kontaktowe, które mogą pomóc w nowym zatrudnieniu pomyślne od pierwszego dnia.</span><span class="sxs-lookup"><span data-stu-id="bbe58-182">You can add contact people who can help your new hire succeed from day one.</span></span> <span data-ttu-id="bbe58-183">Tymi kontaktami mogą być rekruterzy, członkowie zespołu, znajomi wdrażania do pracy, doradcy, Administratorzy oraz personel pomocy technicznej działu informatycznego.</span><span class="sxs-lookup"><span data-stu-id="bbe58-183">These contacts can be recruiters, teammates, onboarding buddies, mentors, admins, and IT support staff.</span></span>

1. <span data-ttu-id="bbe58-184">Na karcie **Kontakty** wybierz opcję **Nowy kontakt**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-184">On the **Contacts** tab, select **New contact**.</span></span>
2. <span data-ttu-id="bbe58-185">W oknie dialogowym **Dodawanie członka zespołu** wprowadź imię i nazwisko osoby kontaktowej lub adres e-mail, a następnie wprowadź krótki opis wyjaśniający, w jaki sposób osoba kontaktowa może pomóc nowym zatrudnieniu, a następnie wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-185">In the **Add team member** dialog box, enter the contact person's name or email address, enter a short description that explains how the contact person can help the new hire, and then select **Add**.</span></span> 

    ![[<span data-ttu-id="bbe58-186">Dodawanie kontaktów do przewodnika lub szablonu wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="bbe58-186">Adding contacts to an onboarding guide or template</span></span>](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    <span data-ttu-id="bbe58-187">Alternatywnie można wybrać co najmniej jeden kontakt w ramach **Sugestie**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-187">Alternately, you can select one or more contacts under **Suggestions**.</span></span>

3. <span data-ttu-id="bbe58-188">Wybierz **Zapisz**, żeby zapisać pracę.</span><span class="sxs-lookup"><span data-stu-id="bbe58-188">Select **Save** to save your work.</span></span>

<span data-ttu-id="bbe58-189">Aby usunąć kontakt, wybierz przycisk **Usuń** (kosz na śmieci) z prawej strony kontaktu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-189">To delete a contact, select the **Delete** button (the trash can symbol) to the right of the contact.</span></span>

<span data-ttu-id="bbe58-190">Aby edytować kontakt, wybierz przycisk **Edytuj** (symbol ołówka) z prawej strony kontaktu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-190">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the contact.</span></span>

## <a name="add-or-edit-resources"></a><span data-ttu-id="bbe58-191">Dodaj lub edytuj zasoby</span><span class="sxs-lookup"><span data-stu-id="bbe58-191">Add or edit resources</span></span>

<span data-ttu-id="bbe58-192">Można dodawać przydatne pliki, mapy i łącza do sekcji **Zasoby** w przewodniku wdrażania do pracy.</span><span class="sxs-lookup"><span data-stu-id="bbe58-192">You can add useful files, maps, and links to the **Resources** section of your onboarding guide.</span></span>

1. <span data-ttu-id="bbe58-193">Na karcie **Zasoby** wybierz opcję **Nowe zasoby**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-193">On the **Resources** tab, select **New resource**.</span></span>
2. <span data-ttu-id="bbe58-194">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="bbe58-194">Follow one of these steps:</span></span>

    - <span data-ttu-id="bbe58-195">Aby dodać plik, wybierz kartę **Plik** i przeciągnij plik do wyznaczonego obszaru.</span><span class="sxs-lookup"><span data-stu-id="bbe58-195">To add a file, select the **File** tab, and drag the file into the designated area.</span></span> <span data-ttu-id="bbe58-196">(Można również kliknąć w dowolnym miejscu w tym obszarze, aby odszukać plik na komputerze lub wybrać **Przeglądaj OneDrive**.) Wprowadź nazwę pliku, a następnie wybierz przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-196">(Alternatively, click anywhere in that area to browse for the file on your computer, or select **Browse OneDrive**.) Enter a name for the file, and then select **Add**.</span></span>
    - <span data-ttu-id="bbe58-197">Aby dodać łącze, wybierz kartę **Łącze**, wprowadź nazwę i adres łącza, a następnie wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-197">To add a link, select the **Link** tab, enter a name and address for the link, and then select **Add**.</span></span>
    - <span data-ttu-id="bbe58-198">Aby dodać mapę, wybierz kartę **Mapa**, wprowadź nazwę i adres mapy, a następnie wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bbe58-198">To add a map, select the **Map** tab, enter a name and address for the map, and then select **Add**.</span></span> <span data-ttu-id="bbe58-199">Onboard będzie uwzględniał Mapę określonego adresu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-199">Onboard will include a map of the address that you specify.</span></span>

    ![[<span data-ttu-id="bbe58-200">Dodawanie zasobu do przewodnika lub szablonu wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="bbe58-200">Adding a resource to an onboarding guide or template</span></span>](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. <span data-ttu-id="bbe58-201">Wybierz **Zapisz**, żeby zapisać pracę.</span><span class="sxs-lookup"><span data-stu-id="bbe58-201">Select **Save** to save your work.</span></span>

<span data-ttu-id="bbe58-202">Aby usunąć zasoby, wybierz przycisk **Usuń** (kosz na śmieci) z prawej strony zasobu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-202">To delete a resource, select the **Delete** button (the trash can symbol) to the right of the resource.</span></span>

<span data-ttu-id="bbe58-203">Aby edytować kontakt, wybierz przycisk **Edytuj** (symbol ołówka) z prawej strony zasobu.</span><span class="sxs-lookup"><span data-stu-id="bbe58-203">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the resource.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bbe58-204">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="bbe58-204">Next steps</span></span>

- [<span data-ttu-id="bbe58-205">Udostępnianie zawartości innym współautorom</span><span class="sxs-lookup"><span data-stu-id="bbe58-205">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="bbe58-206">Wyświetlanie stanu zadań i dołączania pracowników</span><span class="sxs-lookup"><span data-stu-id="bbe58-206">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="bbe58-207">Tworzenie zespołów rekrutacyjnych w Onboard</span><span class="sxs-lookup"><span data-stu-id="bbe58-207">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="bbe58-208">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="bbe58-208">See also</span></span>

- [<span data-ttu-id="bbe58-209">Wypróbuj lub kup aplikację Onboard</span><span class="sxs-lookup"><span data-stu-id="bbe58-209">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="bbe58-210">Nowości i zmiany w Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="bbe58-210">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="bbe58-211">Plany wydań</span><span class="sxs-lookup"><span data-stu-id="bbe58-211">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="bbe58-212">Uzyskiwanie pomocy technicznej dotyczącej rozwiązania Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="bbe58-212">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
