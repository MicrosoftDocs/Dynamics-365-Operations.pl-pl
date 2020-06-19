---
title: Praca z plikami zastępowania CSS
description: W tym temacie opisano, dlaczego, kiedy i jak używać plików zastępowania kaskadowych arkuszy stylów (CSS) w aplikacji Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3ec43b16b1df07400cffe597378ad4035e4d07e0
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411254"
---
# <a name="work-with-css-override-files"></a><span data-ttu-id="b8e9f-103">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="b8e9f-103">Work with CSS override files</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b8e9f-104">W tym temacie opisano, dlaczego, kiedy i jak używać plików zastępowania kaskadowych arkuszy stylów (CSS) w aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-104">This topic describes why, when, and how to use Cascading Style Sheets (CSS) override files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b8e9f-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="b8e9f-105">Overview</span></span>

<span data-ttu-id="b8e9f-106">Stałe style witryny zazwyczaj powinny być obsługiwane za pośrednictwem motywu witryny.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-106">Permanent site styles should usually be handled through a site's theme.</span></span> <span data-ttu-id="b8e9f-107">Motywy udostępniają podstawowe ustawienia stylów CSS i ustawienia stylów dla modułów na dowolnej stronie witryny.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-107">Themes provide the foundational CSS and style settings for the modules on any page of your site.</span></span> <span data-ttu-id="b8e9f-108">Motywy są tworzone przy użyciu zestawu Dynamics 365 Commerce SDK (Software Development Kit) w trybie online i są wdrażane w witrynach internetowych za pośrednictwem usług Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b8e9f-108">Themes are created by using the Dynamics 365 Commerce online software development kit (SDK), and they are deployed to your websites through Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="b8e9f-109">Możliwości debugowania modułu i konfiguracje interfejsu modułu w zestawie SDK pomagają deweloperom tworzyć dostosowywalne i spójne pakiety projektów witryny.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-109">Theme debugging capabilities and module interface configurations in the SDK help site developers create customizable and cohesive site design packages.</span></span> <span data-ttu-id="b8e9f-110">Gdy te pakiety projektów są wdrażane w witrynie, autorzy witryn mogą skupić się na tworzeniu, edytowaniu i publikowaniu zawartości, a nie na programowaniu witryny.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-110">When these design packages are deployed to a site, site authors can focus on creating, editing, and publishing content instead of site development.</span></span>

<span data-ttu-id="b8e9f-111">Biorąc pod uwagę zwykły cykl życia motywu, zależność od tego, aby deweloperzy zmienili styl za pomocą zestawu SDK i potoku wdrażania usługi LCS może stanowić element zaporowy w niektórych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-111">Given the usual lifecycle of a theme, the dependency on developers to make style changes through the SDK and LCS deployment pipeline can be prohibitive in some scenarios.</span></span> <span data-ttu-id="b8e9f-112">Prototypy lub poprawki witryny mogą wydawać się kłopotliwe, jeśli zestaw SDK nie jest skonfigurowany lub jeśli nie masz czasu na oczekiwanie na wdrożenie usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-112">Site prototypes or hotfixes can seem cumbersome if the SDK isn't configured, or if you don't have time to wait for an LCS deployment.</span></span>

<span data-ttu-id="b8e9f-113">W tych scenariuszach mogą pomóc pliki zastępowania CSS.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-113">In these scenarios, CSS override files can help.</span></span> <span data-ttu-id="b8e9f-114">W narzędziach autorskich usługi Commerce uwierzytelnieni użytkownicy mogą przekazać plik CSS, wyświetlić jego podgląd, a następnie aktywować go w celu zastąpienia motywu witryny.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-114">In the Commerce authoring tools, authenticated users can upload a CSS file, preview it, and then activate it to override a site's theme.</span></span> <span data-ttu-id="b8e9f-115">Obciążenie związane z wdrożeniem zestawu SDK lub usługi LCS nie jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-115">The overhead of SDK or LCS deployment isn't required.</span></span> <span data-ttu-id="b8e9f-116">Zastąpienia, które są określone w pliku zastępowania CSS, mogą być tak małe, jak zmiana stylu pojedynczego tekstu, lub szeroko zakrojone, na przykład kompletna przebudowa marki.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-116">The overrides that are specified in a CSS override file can be as small as a change to a single text style or as wide-ranging as a complete brand overhaul.</span></span>

<span data-ttu-id="b8e9f-117">Przed użyciem plików zastępowania CSS pamiętać o następujących ograniczeniach:</span><span class="sxs-lookup"><span data-stu-id="b8e9f-117">Before you use CSS override files, be aware of the following limitations:</span></span>

- <span data-ttu-id="b8e9f-118">Tylko jeden plik zastępowania CSS może być aktywny w danej witrynie w danym momencie.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-118">Only one CSS override file can be active on a site at a time.</span></span> <span data-ttu-id="b8e9f-119">W związku z tym wszystkie aktywne zastąpienia muszą być obecne w pojedynczym pliku zastępowania.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-119">Therefore, all active overrides must be present in a single override file.</span></span>
- <span data-ttu-id="b8e9f-120">Chociaż podgląd zastąpień można wyświetlać w narzędziach autorskich usługi Commerce, nie ma żadnych dedykowanych funkcji debugowania, które pomogą zidentyfikować błędy wprowadzane przez zastąpienia.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-120">Although you can preview the overrides in the Commerce authoring tools, there are no dedicated debugging features to help identify any bugs that the overrides introduce.</span></span> <span data-ttu-id="b8e9f-121">Innymi słowy, jeśli używasz plików zastępowania CSS, nie masz tego samego zestawu narzędzi, który zawiera zestaw SDK do weryfikowania modułu i procesu tworzenia.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-121">In other words, when you use CSS override files, you don't have the same toolset that the SDK provides for module and authoring validation.</span></span>

<span data-ttu-id="b8e9f-122">Niemniej jednak pliki zastępowania CSS oferują szybki sposób tworzenia prototypu projektu lub implementowania poprawki, zanim zostanie opracowana i zaimplementowana pełna aktualizacja motywu.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-122">Nevertheless, CSS override files provide a quick way to prototype a design or implement a hotfix before a full theme update is developed and deployed.</span></span>

## <a name="create-a-css-override-file"></a><span data-ttu-id="b8e9f-123">Tworzenie pliku zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="b8e9f-123">Create a CSS override file</span></span>

<span data-ttu-id="b8e9f-124">Aby utworzyć plik zastępowania CSS, można użyć dowolnego zintegrowanego środowiska projektowego (IDE), edytora tekstów lub edytora kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-124">To create a CSS override file, you can use any integrated development environment (IDE), text editor, or source code editor.</span></span> <span data-ttu-id="b8e9f-125">Typowym podejściem jest użycie standardowych debugerów internetowych w przeglądarce do identyfikowania selektorów stylów, właściwości i wartości w istniejącej witrynie.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-125">A typical approach is to use standard web debuggers in your browser to identify style selectors, properties, and values on your existing site.</span></span> <span data-ttu-id="b8e9f-126">Większość przeglądarek umożliwia zmienianie wartości i wyświetlanie ich podglądu w debugerze.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-126">Most browsers let you change values and preview them in the debugger.</span></span> <span data-ttu-id="b8e9f-127">Po zidentyfikowaniu zmian, które chcesz wprowadzić, można zapisać je we własnym pliku CSS.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-127">After you've identified the changes that you want to make, you can save them to your own CSS file.</span></span>

## <a name="upload-a-css-override-file"></a><span data-ttu-id="b8e9f-128">Przekazywanie pliku zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="b8e9f-128">Upload a CSS override file</span></span>

<span data-ttu-id="b8e9f-129">Aby przekazać plik CSS do witryny w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-129">To upload a CSS file to your site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="b8e9f-130">W narzędziach autorskich przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-130">In the authoring tools, go to your site.</span></span>
1. <span data-ttu-id="b8e9f-131">W okienku nawigacji po lewej stronie wybierz pozycję **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-131">In the navigation pane on the left, select **Design**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8e9f-132">W zależności od wersji narzędzi autorskich usługi Commerce, których używasz, być może trzeba rozwinąć pozycję **Ustawienia** w okienku nawigacji, aby można było wybrać pozycję **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-132">Depending on the version of the Commerce authoring tools that you're using, you might have to expand **Settings** in the navigation pane before you can select **Design**.</span></span>

1. <span data-ttu-id="b8e9f-133">W górnej części głównego okienka projektu wybierz kartę **Zastępowanie CSS**, jeśli nie jest jeszcze wybrana.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-133">At the top of the main design pane, select the **CSS override** tab, if it isn't already selected.</span></span>
1. <span data-ttu-id="b8e9f-134">W obszarze **Dostępne zastąpienia CSS** wybierz pozycję **Przekaż plik CSS**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-134">Under **Available CSS overrides**, select **Upload CSS file**.</span></span> <span data-ttu-id="b8e9f-135">Zostanie wyświetlone okno Eksploratora plików.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-135">A File Explorer window appears.</span></span>
1. <span data-ttu-id="b8e9f-136">W Eksploratorze plików przejdź do pliku CSS i zaznacz go, a następnie wybierz pozycję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-136">In File Explorer, browse to and select a CSS file, and then select **Open**.</span></span> <span data-ttu-id="b8e9f-137">Przekazany plik CSS pojawi się teraz w obszarze **Dostępne zastąpienia CSS**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-137">The uploaded CSS file now appears under **Available CSS overrides**.</span></span>

## <a name="preview-a-css-override-file"></a><span data-ttu-id="b8e9f-138">Wyświetlanie podglądu pliku zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="b8e9f-138">Preview a CSS override file</span></span>

<span data-ttu-id="b8e9f-139">Aby wyświetlić podgląd pliku zastępowania CSS przed uaktywnieniem go w aktywnej witrynie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-139">To preview a CSS override file before you make it active on your live site, follow these steps.</span></span>

1. <span data-ttu-id="b8e9f-140">W okienku nawigacji po lewej stronie wybierz pozycję **Projekt**, a następnie na karcie **Zastępowanie CSS** w obszarze **Dostępne zastąpienia CSS** znajdź plik CSS, którego podgląd chcesz wyświetlić.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-140">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to preview.</span></span>
1. <span data-ttu-id="b8e9f-141">Obok nazwy pliku CSS wybierz opcję **Podgląd witryny**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-141">Next to the CSS file name, select **Preview site**.</span></span>
1. <span data-ttu-id="b8e9f-142">W oknie dialogowym **Wybieranie adresu URL** wybierz adres URL witryny, dla której chcesz zobaczyć zastosowane zastąpienie, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-142">In the **Select a URL** dialog box, select the URL of the site that you want to see the override applied to, and then select **OK**.</span></span>
1. <span data-ttu-id="b8e9f-143">Jeśli istnieje wiele wariantów wybranego adresu URL, wybierz żądany wariant w wyświetlonym oknie dialogowym **Podgląd wariantów**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-143">If there are multiple variants for the selected URL, select the desired variant in the **Preview variations** dialog box that appears.</span></span>

<span data-ttu-id="b8e9f-144">Zostanie otwarta nowa karta lub okno przeglądarki, w którym możesz zweryfikować zastąpienia stylu względem witryny.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-144">A new browser tab or window is opened, where you can validate your style overrides against your site.</span></span> <span data-ttu-id="b8e9f-145">Następnie możesz udostępnić adres URL innym uwierzytelnionym użytkownikom usługi Commerce w celu przejrzenia i przesłania opinii.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-145">You can then share the URL with other authenticated Commerce users for review and feedback.</span></span>

## <a name="activate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="b8e9f-146">Aktywowanie pliku zastępowania CSS w aktywnej witrynie</span><span class="sxs-lookup"><span data-stu-id="b8e9f-146">Activate a CSS override file on your live site</span></span>

<span data-ttu-id="b8e9f-147">Po wyświetleniu podglądu i zatwierdzeniu pliku zastępowania CSS można go aktywować w aktywnej witrynie.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-147">After you've previewed and approved the CSS override file, you can activate it on your live site.</span></span>

> [!NOTE]
> <span data-ttu-id="b8e9f-148">Tylko jeden plik zastępowania CSS może być aktywny w Twojej witrynie w danym momencie.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-148">Only one CSS override file can be active on your site at a time.</span></span> <span data-ttu-id="b8e9f-149">Jeśli uaktywnisz nowy plik zastępowania, poprzedni plik zastępowania zostanie wyłączony.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-149">If you activate a new override file, the previous override file is inactivated.</span></span> <span data-ttu-id="b8e9f-150">W związku z tym upewnij się, że wszystkie wymagane zastąpienia są obecne w pojedynczym pliku zastępowania CSS.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-150">Therefore, make sure that all required overrides are present in a single CSS override file.</span></span>

<span data-ttu-id="b8e9f-151">Aby aktywować pliki zastępowania CSS, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-151">To activate a CSS override file, follow these steps.</span></span>

1. <span data-ttu-id="b8e9f-152">W okienku nawigacji po lewej stronie wybierz pozycję **Projekt**, a następnie na karcie **Zastępowanie CSS** w obszarze **Dostępne zastąpienia CSS** znajdź plik CSS, który chcesz aktywować.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-152">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to activate.</span></span>
1. <span data-ttu-id="b8e9f-153">W obszarze nazwy pliku CSS wybierz pozycję **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-153">Under the CSS file name, select **Activate**.</span></span> <span data-ttu-id="b8e9f-154">Plik zastępowania natychmiast uaktywni się w Twojej aktywnej witrynie.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-154">The override file immediately becomes active on your live site.</span></span>

## <a name="deactivate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="b8e9f-155">Dezaktywowanie pliku zastępowania CSS w aktywnej witrynie</span><span class="sxs-lookup"><span data-stu-id="b8e9f-155">Deactivate a CSS override file on your live site</span></span>

<span data-ttu-id="b8e9f-156">Aby dezaktywować plik zastępowania CSS w witrynie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-156">To deactivate a CSS override file on your site, follow these steps.</span></span>

1. <span data-ttu-id="b8e9f-157">W okienku nawigacji po lewej stronie wybierz pozycję **Projekt**, a następnie na karcie **Zastępowanie CSS** w obszarze **Dostępne zastąpienia CSS** znajdź plik CSS, który chcesz dezaktywować.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-157">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to deactivate.</span></span>
1. <span data-ttu-id="b8e9f-158">W obszarze nazwy pliku CSS wybierz pozycję **Dezaktywuj**.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-158">Under the CSS file name, select **Deactivate**.</span></span> <span data-ttu-id="b8e9f-159">Plik zastępowania natychmiast zostanie wyłączony w Twojej aktywnej witrynie.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-159">The override file immediately becomes inactive on your live site.</span></span>

> [!TIP]
> <span data-ttu-id="b8e9f-160">Aby uzyskać dostęp do dodatkowych opcji plików zastępowania CSS, wybierz wielokropek (**...**) obok nazwy pliku CSS.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-160">To access additional options for CSS override files, select the ellipsis (**...**) next to the CSS file name.</span></span> <span data-ttu-id="b8e9f-161">Opcje **pobierania**, **zmieniania nazwy** i **zastępowania** są przydatne w przypadku szybkich zmian w istniejącym pliku zastępowania CSS.</span><span class="sxs-lookup"><span data-stu-id="b8e9f-161">The **Download**, **Rename**, and **Replace** options are useful for quick changes to an existing CSS override file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8e9f-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b8e9f-162">Additional resources</span></span>

[<span data-ttu-id="b8e9f-163">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="b8e9f-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="b8e9f-164">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="b8e9f-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="b8e9f-165">Praca z predefiniowanymi ustawieniami stylów</span><span class="sxs-lookup"><span data-stu-id="b8e9f-165">Work with style presets</span></span>](style-presets.md)

[<span data-ttu-id="b8e9f-166">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="b8e9f-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="b8e9f-167">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="b8e9f-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="b8e9f-168">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="b8e9f-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="b8e9f-169">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="b8e9f-169">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="b8e9f-170">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="b8e9f-170">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)
