---
title: Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii
description: W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.
author: bicyclingfool
manager: annbe
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: dfebc6616186a3a8859b00e90c178129feaa324b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980164"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="0c373-103">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="0c373-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0c373-104">W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="0c373-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="0c373-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="0c373-105">Overview</span></span>

<span data-ttu-id="0c373-106">Narzędzie Web Analytics jest podstawowym narzędziem, które umożliwia zrozumienie, w jaki sposób klienci współpracują z daną witryną, a następnie podejmujmowanie decyzji, które pozwolą zoptymalizować możliwości konwersji.</span><span class="sxs-lookup"><span data-stu-id="0c373-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="0c373-107">Dostępnych jest wiele pakietów analiz sieci Web ułatwiających osiągnięcie tych celów, takich jak Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="0c373-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="0c373-108">Większość pakietów analiz sieci Web wymaga dodania kodu skryptu po stronie klienta w elemencie **\<head\>** kodu HTML na wszystkich stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="0c373-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="0c373-109">Instrukcje przedstawione w tym temacie dotyczą również innych niestandardowych funkcji po stronie klienta, które Microsoft Dynamics 365 Commerce nie oferuje w sposób macierzysty.</span><span class="sxs-lookup"><span data-stu-id="0c373-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="0c373-110">Tworzenie fragmentu wielokrotnego użytku dla kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="0c373-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="0c373-111">Fragment umożliwia ponowne użycie wewnętrznego lub zewnętrznego kodu skryptu na wszystkich stronach w witrynie, niezależnie od szablonu, którego używają.</span><span class="sxs-lookup"><span data-stu-id="0c373-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="0c373-112">Tworzenie fragmentu wielokrotnego użytku dla wbudowanego kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="0c373-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="0c373-113">Aby utworzyć fragment do ponownego użycia dla kodu skryptu wbudowanego w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0c373-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c373-114">Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0c373-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="0c373-115">W oknie dialogowym **Nowy fragment** wybierz opcję **Skrypt wbudowany**.</span><span class="sxs-lookup"><span data-stu-id="0c373-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="0c373-116">W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c373-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="0c373-117">Pod utworzonym fragmentem wybierz **Domyślny moduł skryptu wbudowanego**.</span><span class="sxs-lookup"><span data-stu-id="0c373-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="0c373-118">W okienku właściwości po prawej stronie, w obszarze **Skrypt wbudowany**, wprowadź skrypt po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="0c373-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="0c373-119">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="0c373-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="0c373-120">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="0c373-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c373-121">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="0c373-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="0c373-122">Tworzenie fragmentu wielokrotnego użytku dla zewnętrznego kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="0c373-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="0c373-123">Aby utworzyć fragment do ponownego użycia dla kodu skryptu zewnętrznego w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0c373-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c373-124">Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0c373-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="0c373-125">W oknie dialogowym **Nowy fragment** wybierz opcję **Skrypt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="0c373-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="0c373-126">W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c373-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="0c373-127">Pod utworzonym fragmentem wybierz **Domyślny moduł skryptu zewnętrznego**.</span><span class="sxs-lookup"><span data-stu-id="0c373-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="0c373-128">W okienku właściwości po prawej stronie w obszarze **Źródło skryptu** dodaj zewnętrzny lub względny adres URL dla zewnętrznego źródła skryptów.</span><span class="sxs-lookup"><span data-stu-id="0c373-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="0c373-129">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="0c373-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="0c373-130">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="0c373-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c373-131">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="0c373-131">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="0c373-132">Jeśli dla danej witryny jest włączona zasada zabezpieczeń zawartości (CSP), upewnij się, że wszystkie zewnętrzne adresy URL są dodane do dyrektywy **script-src** zasad CSP w module konstruktora witryn Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c373-132">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="0c373-133">Aby uzyskać więcej informacji, zajrzyj do [Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="0c373-133">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="0c373-134">Dodawanie fragmentu zawierającego kod skryptu do szablonu</span><span class="sxs-lookup"><span data-stu-id="0c373-134">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="0c373-135">Aby dodać fragment zawierający kod skryptu do szablonu w kreatorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0c373-135">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c373-136">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="0c373-136">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="0c373-137">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="0c373-137">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="0c373-138">W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="0c373-138">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="0c373-139">Umożliwia wybór fragmentu utworzonego dla kodu skryptu.</span><span class="sxs-lookup"><span data-stu-id="0c373-139">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="0c373-140">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="0c373-140">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c373-141">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="0c373-141">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="0c373-142">Dodawanie skryptu zewnętrznego lub skryptu wbudowanego bezpośrednio do szablonu</span><span class="sxs-lookup"><span data-stu-id="0c373-142">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="0c373-143">Jeśli chcesz wstawić wewnętrzny lub zewnętrzny skrypt bezpośrednio do zbioru stron, które są kontrolowane przez jeden szablon, nie musisz najpierw utworzyć fragmentu.</span><span class="sxs-lookup"><span data-stu-id="0c373-143">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="0c373-144">Dodawanie skryptu wbudowanego bezpośrednio do szablonu</span><span class="sxs-lookup"><span data-stu-id="0c373-144">Add an inline script directly to a template</span></span>

<span data-ttu-id="0c373-145">Aby dodać wbudowany skrypt bezpośrednio do szablonu w konstruktorze stron, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0c373-145">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c373-146">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="0c373-146">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="0c373-147">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="0c373-147">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="0c373-148">W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="0c373-148">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0c373-149">W oknie dialogowym **Dodaj moduł** wybierz opcję **Skrypt wbudowany**.</span><span class="sxs-lookup"><span data-stu-id="0c373-149">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="0c373-150">W okienku właściwości po prawej stronie, w obszarze **Skrypt wbudowany**, wprowadź skrypt po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="0c373-150">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="0c373-151">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="0c373-151">Then configure other options as you require.</span></span>
1. <span data-ttu-id="0c373-152">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="0c373-152">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c373-153">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="0c373-153">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="0c373-154">Dodawanie skryptu zewnętrznego bezpośrednio do szablonu</span><span class="sxs-lookup"><span data-stu-id="0c373-154">Add an external script directly to a template</span></span>

<span data-ttu-id="0c373-155">Aby dodać zewnętrzny skrypt bezpośrednio do szablonu w konstruktorze stron, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0c373-155">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c373-156">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="0c373-156">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="0c373-157">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="0c373-157">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="0c373-158">W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="0c373-158">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0c373-159">W oknie dialogowym **Dodaj moduł** wybierz opcję **Skrypt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="0c373-159">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="0c373-160">W okienku właściwości po prawej stronie w obszarze **Źródło skryptu** dodaj zewnętrzny lub względny adres URL dla zewnętrznego źródła skryptów.</span><span class="sxs-lookup"><span data-stu-id="0c373-160">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="0c373-161">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="0c373-161">Then configure other options as you require.</span></span>
1. <span data-ttu-id="0c373-162">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="0c373-162">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c373-163">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="0c373-163">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c373-164">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0c373-164">Additional resources</span></span>

[<span data-ttu-id="0c373-165">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="0c373-165">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="0c373-166">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="0c373-166">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="0c373-167">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="0c373-167">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="0c373-168">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="0c373-168">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="0c373-169">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="0c373-169">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="0c373-170">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="0c373-170">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="0c373-171">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="0c373-171">Add languages to your site</span></span>](add-languages-to-site.md)
