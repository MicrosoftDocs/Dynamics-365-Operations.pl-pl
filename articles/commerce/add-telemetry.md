---
title: Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii
description: W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.
author: bicyclingfool
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fb1773ab10b23a586eb6a8286f145181818585b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797438"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="8dd14-103">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="8dd14-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8dd14-104">W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="8dd14-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

<span data-ttu-id="8dd14-105">Narzędzie Web Analytics jest podstawowym narzędziem, które umożliwia zrozumienie, w jaki sposób klienci współpracują z daną witryną, a następnie podejmujmowanie decyzji, które pozwolą zoptymalizować możliwości konwersji.</span><span class="sxs-lookup"><span data-stu-id="8dd14-105">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="8dd14-106">Dostępnych jest wiele pakietów analiz sieci Web ułatwiających osiągnięcie tych celów, takich jak Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="8dd14-106">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="8dd14-107">Większość pakietów analiz sieci Web wymaga dodania kodu skryptu po stronie klienta w elemencie **\<head\>** kodu HTML na wszystkich stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="8dd14-107">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="8dd14-108">Instrukcje przedstawione w tym temacie dotyczą również innych niestandardowych funkcji po stronie klienta, które Microsoft Dynamics 365 Commerce nie oferuje w sposób macierzysty.</span><span class="sxs-lookup"><span data-stu-id="8dd14-108">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="8dd14-109">Tworzenie fragmentu wielokrotnego użytku dla kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="8dd14-109">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="8dd14-110">Fragment umożliwia ponowne użycie wewnętrznego lub zewnętrznego kodu skryptu na wszystkich stronach w witrynie, niezależnie od szablonu, którego używają.</span><span class="sxs-lookup"><span data-stu-id="8dd14-110">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="8dd14-111">Tworzenie fragmentu wielokrotnego użytku dla wbudowanego kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="8dd14-111">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="8dd14-112">Aby utworzyć fragment do ponownego użycia dla kodu skryptu wbudowanego w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8dd14-112">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8dd14-113">Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-113">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="8dd14-114">W oknie dialogowym **Nowy fragment** wybierz opcję **Skrypt wbudowany**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-114">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="8dd14-115">W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-115">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="8dd14-116">Pod utworzonym fragmentem wybierz **Domyślny moduł skryptu wbudowanego**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-116">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="8dd14-117">W okienku właściwości po prawej stronie, w obszarze **Skrypt wbudowany**, wprowadź skrypt po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="8dd14-117">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="8dd14-118">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="8dd14-118">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8dd14-119">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-119">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8dd14-120">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-120">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="8dd14-121">Tworzenie fragmentu wielokrotnego użytku dla zewnętrznego kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="8dd14-121">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="8dd14-122">Aby utworzyć fragment do ponownego użycia dla kodu skryptu zewnętrznego w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8dd14-122">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8dd14-123">Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-123">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="8dd14-124">W oknie dialogowym **Nowy fragment** wybierz opcję **Skrypt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-124">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="8dd14-125">W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-125">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="8dd14-126">Pod utworzonym fragmentem wybierz **Domyślny moduł skryptu zewnętrznego**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-126">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="8dd14-127">W okienku właściwości po prawej stronie w obszarze **Źródło skryptu** dodaj zewnętrzny lub względny adres URL dla zewnętrznego źródła skryptów.</span><span class="sxs-lookup"><span data-stu-id="8dd14-127">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="8dd14-128">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="8dd14-128">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8dd14-129">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8dd14-130">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-130">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="8dd14-131">Jeśli dla danej witryny jest włączona zasada zabezpieczeń zawartości (CSP), upewnij się, że wszystkie zewnętrzne adresy URL są dodane do dyrektywy **script-src** zasad CSP w module konstruktora witryn Commerce.</span><span class="sxs-lookup"><span data-stu-id="8dd14-131">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="8dd14-132">Aby uzyskać więcej informacji, zajrzyj do [Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="8dd14-132">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="8dd14-133">Dodawanie fragmentu zawierającego kod skryptu do szablonu</span><span class="sxs-lookup"><span data-stu-id="8dd14-133">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="8dd14-134">Aby dodać fragment zawierający kod skryptu do szablonu w kreatorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8dd14-134">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8dd14-135">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="8dd14-135">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="8dd14-136">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-136">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="8dd14-137">W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-137">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="8dd14-138">Umożliwia wybór fragmentu utworzonego dla kodu skryptu.</span><span class="sxs-lookup"><span data-stu-id="8dd14-138">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="8dd14-139">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-139">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8dd14-140">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-140">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="8dd14-141">Dodawanie skryptu zewnętrznego lub skryptu wbudowanego bezpośrednio do szablonu</span><span class="sxs-lookup"><span data-stu-id="8dd14-141">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="8dd14-142">Jeśli chcesz wstawić wewnętrzny lub zewnętrzny skrypt bezpośrednio do zbioru stron, które są kontrolowane przez jeden szablon, nie musisz najpierw utworzyć fragmentu.</span><span class="sxs-lookup"><span data-stu-id="8dd14-142">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="8dd14-143">Dodawanie skryptu wbudowanego bezpośrednio do szablonu</span><span class="sxs-lookup"><span data-stu-id="8dd14-143">Add an inline script directly to a template</span></span>

<span data-ttu-id="8dd14-144">Aby dodać wbudowany skrypt bezpośrednio do szablonu w konstruktorze stron, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8dd14-144">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8dd14-145">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="8dd14-145">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="8dd14-146">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-146">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="8dd14-147">W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-147">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8dd14-148">W oknie dialogowym **Dodaj moduł** wybierz opcję **Skrypt wbudowany**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-148">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="8dd14-149">W okienku właściwości po prawej stronie, w obszarze **Skrypt wbudowany**, wprowadź skrypt po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="8dd14-149">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="8dd14-150">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="8dd14-150">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8dd14-151">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-151">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8dd14-152">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-152">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="8dd14-153">Dodawanie skryptu zewnętrznego bezpośrednio do szablonu</span><span class="sxs-lookup"><span data-stu-id="8dd14-153">Add an external script directly to a template</span></span>

<span data-ttu-id="8dd14-154">Aby dodać zewnętrzny skrypt bezpośrednio do szablonu w konstruktorze stron, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8dd14-154">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8dd14-155">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="8dd14-155">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="8dd14-156">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-156">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="8dd14-157">W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-157">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8dd14-158">W oknie dialogowym **Dodaj moduł** wybierz opcję **Skrypt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-158">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="8dd14-159">W okienku właściwości po prawej stronie w obszarze **Źródło skryptu** dodaj zewnętrzny lub względny adres URL dla zewnętrznego źródła skryptów.</span><span class="sxs-lookup"><span data-stu-id="8dd14-159">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="8dd14-160">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="8dd14-160">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8dd14-161">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-161">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8dd14-162">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="8dd14-162">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8dd14-163">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8dd14-163">Additional resources</span></span>

[<span data-ttu-id="8dd14-164">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="8dd14-164">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="8dd14-165">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="8dd14-165">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="8dd14-166">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="8dd14-166">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="8dd14-167">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="8dd14-167">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="8dd14-168">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="8dd14-168">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="8dd14-169">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="8dd14-169">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="8dd14-170">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="8dd14-170">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
