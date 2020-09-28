---
title: Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii
description: W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a88f4f920154aafaa15a48af67365152e21111f7
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761256"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="eb68c-103">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="eb68c-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="eb68c-104">W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="eb68c-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="eb68c-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="eb68c-105">Overview</span></span>

<span data-ttu-id="eb68c-106">Narzędzie Web Analytics jest podstawowym narzędziem, które umożliwia zrozumienie, w jaki sposób klienci współpracują z daną witryną, a następnie podejmujmowanie decyzji, które pozwolą zoptymalizować możliwości konwersji.</span><span class="sxs-lookup"><span data-stu-id="eb68c-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="eb68c-107">Dostępnych jest wiele pakietów analiz sieci Web ułatwiających osiągnięcie tych celów, takich jak Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="eb68c-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="eb68c-108">Większość pakietów analiz sieci Web wymaga dodania kodu skryptu po stronie klienta w elemencie **\<head\>** kodu HTML na wszystkich stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="eb68c-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="eb68c-109">Instrukcje przedstawione w tym temacie dotyczą również innych niestandardowych funkcji po stronie klienta, które Microsoft Dynamics 365 Commerce nie oferuje w sposób macierzysty.</span><span class="sxs-lookup"><span data-stu-id="eb68c-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="eb68c-110">Tworzenie fragmentu wielokrotnego użytku dla kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="eb68c-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="eb68c-111">Fragment umożliwia ponowne użycie wewnętrznego lub zewnętrznego kodu skryptu na wszystkich stronach w witrynie, niezależnie od szablonu, którego używają.</span><span class="sxs-lookup"><span data-stu-id="eb68c-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="eb68c-112">Tworzenie fragmentu wielokrotnego użytku dla wbudowanego kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="eb68c-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="eb68c-113">Aby utworzyć fragment do ponownego użycia dla kodu skryptu wbudowanego w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="eb68c-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="eb68c-114">Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="eb68c-115">W oknie dialogowym **Nowy fragment** wybierz opcję **Skrypt wbudowany**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="eb68c-116">W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="eb68c-117">Pod utworzonym fragmentem wybierz **Domyślny moduł skryptu wbudowanego**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="eb68c-118">W okienku właściwości po prawej stronie, w obszarze **Skrypt wbudowany**, wprowadź skrypt po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="eb68c-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="eb68c-119">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="eb68c-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="eb68c-120">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="eb68c-121">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="eb68c-122">Tworzenie fragmentu wielokrotnego użytku dla zewnętrznego kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="eb68c-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="eb68c-123">Aby utworzyć fragment do ponownego użycia dla kodu skryptu zewnętrznego w konstruktorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="eb68c-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="eb68c-124">Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="eb68c-125">W oknie dialogowym **Nowy fragment** wybierz opcję **Skrypt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="eb68c-126">W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="eb68c-127">Pod utworzonym fragmentem wybierz **Domyślny moduł skryptu zewnętrznego**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="eb68c-128">W okienku właściwości po prawej stronie w obszarze **Źródło skryptu** dodaj zewnętrzny lub względny adres URL dla zewnętrznego źródła skryptów.</span><span class="sxs-lookup"><span data-stu-id="eb68c-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="eb68c-129">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="eb68c-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="eb68c-130">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="eb68c-131">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-131">Select **Publish**.</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="eb68c-132">Dodawanie fragmentu zawierającego kod skryptu do szablonu</span><span class="sxs-lookup"><span data-stu-id="eb68c-132">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="eb68c-133">Aby dodać fragment zawierający kod skryptu do szablonu w kreatorze witryn, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="eb68c-133">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="eb68c-134">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="eb68c-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="eb68c-135">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="eb68c-136">W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="eb68c-137">Umożliwia wybór fragmentu utworzonego dla kodu skryptu.</span><span class="sxs-lookup"><span data-stu-id="eb68c-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="eb68c-138">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="eb68c-139">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="eb68c-140">Dodawanie skryptu zewnętrznego lub skryptu wbudowanego bezpośrednio do szablonu</span><span class="sxs-lookup"><span data-stu-id="eb68c-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="eb68c-141">Jeśli chcesz wstawić wewnętrzny lub zewnętrzny skrypt bezpośrednio do zbioru stron, które są kontrolowane przez jeden szablon, nie musisz najpierw utworzyć fragmentu.</span><span class="sxs-lookup"><span data-stu-id="eb68c-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="eb68c-142">Dodawanie skryptu wbudowanego bezpośrednio do szablonu</span><span class="sxs-lookup"><span data-stu-id="eb68c-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="eb68c-143">Aby dodać wbudowany skrypt bezpośrednio do szablonu w konstruktorze stron, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="eb68c-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="eb68c-144">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="eb68c-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="eb68c-145">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="eb68c-146">W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="eb68c-147">W oknie dialogowym **Dodaj moduł** wybierz opcję **Skrypt wbudowany**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="eb68c-148">W okienku właściwości po prawej stronie, w obszarze **Skrypt wbudowany**, wprowadź skrypt po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="eb68c-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="eb68c-149">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="eb68c-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="eb68c-150">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="eb68c-151">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="eb68c-152">Dodawanie skryptu zewnętrznego bezpośrednio do szablonu</span><span class="sxs-lookup"><span data-stu-id="eb68c-152">Add an external script directly to a template</span></span>

<span data-ttu-id="eb68c-153">Aby dodać zewnętrzny skrypt bezpośrednio do szablonu w konstruktorze stron, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="eb68c-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="eb68c-154">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="eb68c-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="eb68c-155">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="eb68c-156">W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="eb68c-157">W oknie dialogowym **Dodaj moduł** wybierz opcję **Skrypt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="eb68c-158">W okienku właściwości po prawej stronie w obszarze **Źródło skryptu** dodaj zewnętrzny lub względny adres URL dla zewnętrznego źródła skryptów.</span><span class="sxs-lookup"><span data-stu-id="eb68c-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="eb68c-159">Następnie skonfiguruj inne opcje stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="eb68c-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="eb68c-160">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="eb68c-161">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="eb68c-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eb68c-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="eb68c-162">Additional resources</span></span>

[<span data-ttu-id="eb68c-163">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="eb68c-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="eb68c-164">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="eb68c-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="eb68c-165">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="eb68c-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="eb68c-166">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="eb68c-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="eb68c-167">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="eb68c-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="eb68c-168">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="eb68c-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="eb68c-169">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="eb68c-169">Add languages to your site</span></span>](add-languages-to-site.md)
