---
title: Dodawanie strony zasad ochrony prywatności
description: W tym temacie opisano, jak dodać stronę zasad ochrony prywatności do witryny w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 07a806ac040df9dee284e2466629221fbc3403a4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209282"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="31477-103">Dodawanie strony zasad ochrony prywatności</span><span class="sxs-lookup"><span data-stu-id="31477-103">Add a privacy policy page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="31477-104">W tym temacie opisano, jak dodać stronę zasad ochrony prywatności do witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="31477-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="31477-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="31477-105">Overview</span></span>

<span data-ttu-id="31477-106">Zgodność z zasadami ochrony prywatności obejmuje środki organizacyjne, które informują użytkowników witryny o sposobie gromadzenia i zbierania ich danych.</span><span class="sxs-lookup"><span data-stu-id="31477-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="31477-107">Użytkownicy mogą zdecydować, w jaki sposób mają być przetwarzane dane osobowe, i mogą podejmować odpowiednie akcje.</span><span class="sxs-lookup"><span data-stu-id="31477-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="31477-108">Przeczytaj zasady ochrony prywatności Microsoft w aplikacji Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="31477-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="31477-109">Aby przeczytać zasady ochrony prywatności Microsoft po zalogowaniu do narzędzi autorskich Dynamics 365 Commerce, wybierz przycisk **Pomoc** (**?**) w prawym górnym rogu, a następnie wybierz pozycję **Prywatność i pliki cookie**.</span><span class="sxs-lookup"><span data-stu-id="31477-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="31477-110">Zostanie otwarta nowa karta z linkiem do [oświadczenia o ochronie prywatności Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="31477-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="31477-111">Tworzenie strony zasad ochrony prywatności dla witryny</span><span class="sxs-lookup"><span data-stu-id="31477-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="31477-112">W aplikacji Dynamics 365 Commerce istnieje kilka sposobów udostępniania użytkownikom witryny zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="31477-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="31477-113">W tej sekcji przedstawiono sposób tworzenia strony zasad ochrony prywatności, a następnie odwoływania się do tej strony za pomocą fragmentu stopki.</span><span class="sxs-lookup"><span data-stu-id="31477-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="31477-114">Poniższe wskazówki to przykład, który pokazuje, jak utworzyć stronę ogólnych zasad ochrony prywatności dla witryny usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="31477-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="31477-115">Odpowiadasz za zaprojektowanie i zaimplementowanie rozwiązania strony polityki prywatności, które najlepiej spełnia wymagania prawne Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="31477-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="31477-116">Aby rozpocząć, w narzędziach autorskich przejdź do witryny, dla której chcesz utworzyć stronę zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="31477-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="31477-117">Utwórz szablon</span><span class="sxs-lookup"><span data-stu-id="31477-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="31477-118">Jeśli szablon, który może być użyty na stronie zasad ochrony prywatności, został już utworzony, przejdź do sekcji [Tworzenie strony zasad ochrony prywatności](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="31477-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="31477-119">Aby utworzyć szablon, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="31477-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="31477-120">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć szablon strony.</span><span class="sxs-lookup"><span data-stu-id="31477-120">Go to **Templates**, and then select **New** to create a page template.</span></span>
1. <span data-ttu-id="31477-121">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon baneru promocyjnego**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="31477-121">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="31477-122">W szablonie dodaj wszystkie wymagane moduły do wymaganych gniazd stron.</span><span class="sxs-lookup"><span data-stu-id="31477-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="31477-123">Aby uzyskać wskazówki, najedź kursorem na czerwone wykrzykniki.</span><span class="sxs-lookup"><span data-stu-id="31477-123">For guidance, hover over the red exclamation marks.</span></span> <span data-ttu-id="31477-124">(Na przykład miejsce **Nagłówek HTML** może wymagać modułu **Domyślny skrypt zewnętrzny**.)</span><span class="sxs-lookup"><span data-stu-id="31477-124">(For example, the **HTML Head** slot might require a **Default External Script** module.)</span></span>
1. <span data-ttu-id="31477-125">W miejscu **Treść** dodaj moduł **Strona domyślna**.</span><span class="sxs-lookup"><span data-stu-id="31477-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="31477-126">W module **Strona domyślna** w miejscu **Główne** dodaj moduł **Blok zawartości zaawansowanej**.</span><span class="sxs-lookup"><span data-stu-id="31477-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="31477-127">W module **Blok zawartości zaawansowanej** dodaj moduł **Element bloku zawartości zaawansowanej**.</span><span class="sxs-lookup"><span data-stu-id="31477-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="31477-128">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="31477-128">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="31477-129">Tworzenie strony zasad ochrony prywatności</span><span class="sxs-lookup"><span data-stu-id="31477-129">Build a privacy policy page</span></span>

<span data-ttu-id="31477-130">Aby utworzyć stronę zasad ochrony prywatności, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="31477-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="31477-131">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć stronę.</span><span class="sxs-lookup"><span data-stu-id="31477-131">Go to **Pages**, and then select **New** to create a page.</span></span>
1. <span data-ttu-id="31477-132">W oknie dialogowym **Wybierz szablon** wybierz szablon strony zasady prywatności.</span><span class="sxs-lookup"><span data-stu-id="31477-132">In the **Choose a template** dialog box, select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="31477-133">Wprowadź nazwę i adres URL strony, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="31477-133">Enter a page name and page URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="31477-134">W miejscu **Główne** na stronie dodaj moduł **Blok zawartości zaawansowanej**.</span><span class="sxs-lookup"><span data-stu-id="31477-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="31477-135">W module **Blok zawartości zaawansowanej** dodaj moduł **Element bloku zawartości zaawansowanej**.</span><span class="sxs-lookup"><span data-stu-id="31477-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="31477-136">W okienku właściwości modułu **Blok zawartości zaawansowanej** wybierz pozycję **Dodaj źródło danych**, a następnie wybierz pozycję **Zawartość tekstu sformatowanego**.</span><span class="sxs-lookup"><span data-stu-id="31477-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="31477-137">W edytorze tekstu sformatowanego wprowadź zawartość strony zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="31477-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="31477-138">W razie potrzeby rozwiń edytor tekstu sformatowanego do trybu pełnoekranowego.</span><span class="sxs-lookup"><span data-stu-id="31477-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="31477-139">Po zakończeniu wprowadzania zawartości wybierz pozycję **Podgląd**, aby wyświetlić podgląd strony w przeglądarce internetowej.</span><span class="sxs-lookup"><span data-stu-id="31477-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="31477-140">Zakończ wszystkie pozostałe operacje dodawania do właściwości strony i modułu.</span><span class="sxs-lookup"><span data-stu-id="31477-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="31477-141">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="31477-141">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="31477-142">Aby opublikować adres URL strony zasad ochrony prywatności, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="31477-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="31477-143">Przejdź do obszaru **Adresy URL** i wybierz adres URL strony zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="31477-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="31477-144">Wybierz opcję **Publikuj**, aby opublikować wybrany adres URL.</span><span class="sxs-lookup"><span data-stu-id="31477-144">Select **Publish** to publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="31477-145">Tworzenie linku do strony zasad ochrony prywatności w stopce</span><span class="sxs-lookup"><span data-stu-id="31477-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="31477-146">Do fragmentu można dodać link do strony zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="31477-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="31477-147">W ten sposób można udostępnić link i zaktualizować go na wielu stronach witryny, odwołując się do fragmentu.</span><span class="sxs-lookup"><span data-stu-id="31477-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="31477-148">W tym przykładzie pokazano, jak dodać link do strony zasad ochrony prywatności do fragmentu stopki.</span><span class="sxs-lookup"><span data-stu-id="31477-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="31477-149">Aby dodać link do fragmentu stopki, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="31477-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="31477-150">Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment strony.</span><span class="sxs-lookup"><span data-stu-id="31477-150">Go to **Fragments**, and then select **New** to create a page fragment.</span></span>
1. <span data-ttu-id="31477-151">W oknie dialogowym **Nowy fragment** wybierz moduł **Stopki**.</span><span class="sxs-lookup"><span data-stu-id="31477-151">In the **New fragment** dialog box, select the **Footer** module.</span></span>
1. <span data-ttu-id="31477-152">W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="31477-152">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="31477-153">W miejscu **Kategoria stopki** dodaj moduł **Element stopki**.</span><span class="sxs-lookup"><span data-stu-id="31477-153">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="31477-154">W panelu właściwości po prawej stronie wybierz pozycję **Tekst linku**.</span><span class="sxs-lookup"><span data-stu-id="31477-154">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="31477-155">W oknie dialogowym **Tekst linku** wprowadź tekst linku i docelowy link strony zasady ochrony prywatności, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="31477-155">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>
1. <span data-ttu-id="31477-156">Aby uzyskać adres URL strony zasad ochrony prywatności, przejdź do obszaru **Strony**, przejdź do strony zasad ochrony prywatności i skopiuj adres URL z okienka właściwości.</span><span class="sxs-lookup"><span data-stu-id="31477-156">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>
1. <span data-ttu-id="31477-157">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="31477-157">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="31477-158">Wyświetl podgląd fragmentu i przetestuj link do strony zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="31477-158">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="31477-159">Teraz można odwoływać się do fragmentu w szablonie dla innych stron witryny.</span><span class="sxs-lookup"><span data-stu-id="31477-159">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="31477-160">Gdy ten fragment jest przywoływany w module **Stopka** szablonu, odwołanie do linku pojawi się na wszystkich stronach, które zostaną zbudowane przy użyciu tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="31477-160">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31477-161">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="31477-161">Additional resources</span></span>

[<span data-ttu-id="31477-162">Omówienie zgodności</span><span class="sxs-lookup"><span data-stu-id="31477-162">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="31477-163">Funkcje i możliwości dostępności</span><span class="sxs-lookup"><span data-stu-id="31477-163">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="31477-164">Zgodność z plikami cookie</span><span class="sxs-lookup"><span data-stu-id="31477-164">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="31477-165">Zamień identyfikatory użytkowników skojarzone ze śledzonymi zmianami zawartości</span><span class="sxs-lookup"><span data-stu-id="31477-165">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]