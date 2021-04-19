---
title: Moduł iframe
description: W tym temacie opisano moduł iframe i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 7b397b91d1b8a45347ef2d05f42fb7c610ab3912
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797077"
---
# <a name="iframe-module"></a><span data-ttu-id="1098d-103">Moduł iframe</span><span class="sxs-lookup"><span data-stu-id="1098d-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1098d-104">W tym temacie opisano moduł iframe i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1098d-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1098d-105">Moduł iframe udostępnia element iframe (ramkę wbudowaną), który obsługuje zawartość zewnętrzną w witrynie.</span><span class="sxs-lookup"><span data-stu-id="1098d-105">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="1098d-106">Na przykład można go używać do obsługi pliku wideo YouTube lub przeglądarki plików PDF na dowolnej stronie witryny.</span><span class="sxs-lookup"><span data-stu-id="1098d-106">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="1098d-107">Moduł iframe wymaga docelowego adresu URL.</span><span class="sxs-lookup"><span data-stu-id="1098d-107">An iframe module requires a target URL.</span></span> <span data-ttu-id="1098d-108">Następnie znajduje zawartość strony docelowej w elemencie **iframe** HTML.</span><span class="sxs-lookup"><span data-stu-id="1098d-108">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="1098d-109">Zewnętrzne adresy URL muszą znajdować się na liście dozwolonych zgodnie z zasadami zabezpieczeń zawartości (CSP) witryny.</span><span class="sxs-lookup"><span data-stu-id="1098d-109">External URLs must be on the allow list per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="1098d-110">W przypadku zawartości iframe adresy URL powinny być dozwolone przy użyciu dyrektywy **przodek ramki**.</span><span class="sxs-lookup"><span data-stu-id="1098d-110">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="1098d-111">Aby uzyskać więcej informacji, zajrzyj do [Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="1098d-111">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1098d-112">Moduł iframe jest dostępny w wydaniu Dynamics 365 Commerce 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="1098d-112">The iframe module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="1098d-113">Poniższy obraz przedstawia przykłady modułów iframe, które prezentują zewnętrzne pliki wideo na stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="1098d-113">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Przykład modułów iframe, które prezentują zewnętrzne pliki wideo](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="1098d-115">Właściwości modułu Iframe</span><span class="sxs-lookup"><span data-stu-id="1098d-115">Iframe module properties</span></span>

| <span data-ttu-id="1098d-116">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="1098d-116">Property name</span></span>             | <span data-ttu-id="1098d-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="1098d-117">Value</span></span>                 | <span data-ttu-id="1098d-118">opis</span><span class="sxs-lookup"><span data-stu-id="1098d-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="1098d-119">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="1098d-119">Heading</span></span> | <span data-ttu-id="1098d-120">Tekst</span><span class="sxs-lookup"><span data-stu-id="1098d-120">Text</span></span> | <span data-ttu-id="1098d-121">Nagłówek modułu.</span><span class="sxs-lookup"><span data-stu-id="1098d-121">The heading for the module.</span></span> |
| <span data-ttu-id="1098d-122">Docelowy adres URL</span><span class="sxs-lookup"><span data-stu-id="1098d-122">Target URL</span></span> | <span data-ttu-id="1098d-123">Adres URL</span><span class="sxs-lookup"><span data-stu-id="1098d-123">URL</span></span> | <span data-ttu-id="1098d-124">Adres URL znajdujący się w module.</span><span class="sxs-lookup"><span data-stu-id="1098d-124">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="1098d-125">Wysokość</span><span class="sxs-lookup"><span data-stu-id="1098d-125">Height</span></span> | <span data-ttu-id="1098d-126">Liczba lub procent</span><span class="sxs-lookup"><span data-stu-id="1098d-126">Number or percentage</span></span> | <span data-ttu-id="1098d-127">Wysokość modułu w pikselach lub w procentach.</span><span class="sxs-lookup"><span data-stu-id="1098d-127">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="1098d-128">Na przykład wartość **100** będzie traktowana jako liczba pikseli, a wartość **100%** będzie traktowana jako wartość procentowa.</span><span class="sxs-lookup"><span data-stu-id="1098d-128">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="1098d-129">Etykieta aria</span><span class="sxs-lookup"><span data-stu-id="1098d-129">Aria label</span></span> | <span data-ttu-id="1098d-130">Tekst</span><span class="sxs-lookup"><span data-stu-id="1098d-130">Text</span></span> | <span data-ttu-id="1098d-131">W celu ułatwienia dostępu można zdefiniować etykietę Accessible Rich Internet Applications (ARIA).</span><span class="sxs-lookup"><span data-stu-id="1098d-131">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="1098d-132">Dodawanie modułu iframe do strony</span><span class="sxs-lookup"><span data-stu-id="1098d-132">Add an iframe module to a page</span></span>

<span data-ttu-id="1098d-133">Aby dodać moduł iframe do strony w celu wyświetlenia zewnętrznego wideo, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1098d-133">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="1098d-134">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="1098d-134">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="1098d-135">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon marketingowy**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="1098d-135">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="1098d-136">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="1098d-136">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="1098d-137">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.</span><span class="sxs-lookup"><span data-stu-id="1098d-137">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="1098d-138">W oknie dialogowym **Wybierz szablon** wybierz szablon **Szablon marketingowy**.</span><span class="sxs-lookup"><span data-stu-id="1098d-138">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="1098d-139">W sekcji **Nazwa strony** przejdź do **Strona marketingu**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1098d-139">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="1098d-140">Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="1098d-140">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1098d-141">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1098d-141">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1098d-142">W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="1098d-142">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="1098d-143">W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="1098d-143">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1098d-144">W oknie dialogowym **Dodaj moduł** wybierz moduł **iframe** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1098d-144">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1098d-145">W okienku właściwości modułu należy określić wartość **Docelowego adresu URL** w celu uzyskania zewnętrznego adresu URL wideo.</span><span class="sxs-lookup"><span data-stu-id="1098d-145">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="1098d-146">W razie konieczności określ inne właściwości, takie jak **Nagłówek** i **Wysokość**.</span><span class="sxs-lookup"><span data-stu-id="1098d-146">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="1098d-147">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="1098d-147">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="1098d-148">Przejdź do strony Marketing w witrynie.</span><span class="sxs-lookup"><span data-stu-id="1098d-148">Go to the marketing page on your site.</span></span> <span data-ttu-id="1098d-149">Należy sprawdzić, czy plik wideo jest renderowany w module iframe.</span><span class="sxs-lookup"><span data-stu-id="1098d-149">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="1098d-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1098d-150">Additional resources</span></span>

[<span data-ttu-id="1098d-151">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="1098d-151">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1098d-152">Zarządzanie zasadami zabezpieczeń zawartości (CSP)</span><span class="sxs-lookup"><span data-stu-id="1098d-152">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]