---
title: Dodawanie strony zasad ochrony prywatności
description: W tym temacie opisano, jak dodać stronę zasad ochrony prywatności do witryny w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/08/2020
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fd39ff5f8c5d97f2d524043b65627dc7e87fcf64
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946067"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="1fb69-103">Dodawanie strony zasad ochrony prywatności</span><span class="sxs-lookup"><span data-stu-id="1fb69-103">Add a privacy policy page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1fb69-104">W tym temacie opisano, jak dodać stronę zasad ochrony prywatności do witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1fb69-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1fb69-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="1fb69-105">Overview</span></span>

<span data-ttu-id="1fb69-106">Zgodność z zasadami ochrony prywatności obejmuje środki organizacyjne, które informują użytkowników witryny o sposobie gromadzenia i zbierania ich danych.</span><span class="sxs-lookup"><span data-stu-id="1fb69-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="1fb69-107">Użytkownicy mogą zdecydować, w jaki sposób mają być przetwarzane dane osobowe, i mogą podejmować odpowiednie akcje.</span><span class="sxs-lookup"><span data-stu-id="1fb69-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="1fb69-108">Przeczytaj zasady ochrony prywatności Microsoft w aplikacji Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1fb69-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="1fb69-109">Aby przeczytać zasady ochrony prywatności Microsoft po zalogowaniu do narzędzi autorskich Dynamics 365 Commerce, wybierz przycisk **Pomoc** (**?**) w prawym górnym rogu, a następnie wybierz pozycję **Prywatność i pliki cookie**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="1fb69-110">Zostanie otwarta nowa karta z linkiem do [oświadczenia o ochronie prywatności Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="1fb69-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="1fb69-111">Tworzenie strony zasad ochrony prywatności dla witryny</span><span class="sxs-lookup"><span data-stu-id="1fb69-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="1fb69-112">W aplikacji Dynamics 365 Commerce istnieje kilka sposobów udostępniania użytkownikom witryny zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="1fb69-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="1fb69-113">W tej sekcji przedstawiono sposób tworzenia strony zasad ochrony prywatności, a następnie odwoływania się do tej strony za pomocą fragmentu stopki.</span><span class="sxs-lookup"><span data-stu-id="1fb69-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="1fb69-114">Poniższe wskazówki to przykład, który pokazuje, jak utworzyć stronę ogólnych zasad ochrony prywatności dla witryny usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="1fb69-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="1fb69-115">Odpowiadasz za zaprojektowanie i zaimplementowanie rozwiązania strony polityki prywatności, które najlepiej spełnia wymagania prawne Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="1fb69-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="1fb69-116">Aby rozpocząć, w narzędziach autorskich przejdź do witryny, dla której chcesz utworzyć stronę zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="1fb69-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="1fb69-117">Utwórz szablon</span><span class="sxs-lookup"><span data-stu-id="1fb69-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="1fb69-118">Jeśli szablon, który może być użyty na stronie zasad ochrony prywatności, został już utworzony, przejdź do sekcji [Tworzenie strony zasad ochrony prywatności](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="1fb69-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="1fb69-119">Aby utworzyć szablon, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="1fb69-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="1fb69-120">Przejdź do pozycji **Szablony \> Nowy szablon**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-120">Go to **Templates \> New Template**.</span></span>
1. <span data-ttu-id="1fb69-121">Wprowadź nazwę szablonu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-121">Enter the template name, and then select **OK**.</span></span>
1. <span data-ttu-id="1fb69-122">W szablonie dodaj wszystkie wymagane moduły do wymaganych gniazd stron.</span><span class="sxs-lookup"><span data-stu-id="1fb69-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="1fb69-123">Aby uzyskać wskazówki, najedź kursorem na czerwone wykrzykniki.</span><span class="sxs-lookup"><span data-stu-id="1fb69-123">For guidance, hover over the red exclamation marks.</span></span>

    <span data-ttu-id="1fb69-124">Na przykład miejsce **Nagłówek HTML** może wymagać modułu **Domyślny skrypt zewnętrzny”**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-124">For example, the **HTML Head** slot might require a **Default External Script** module.</span></span>

1. <span data-ttu-id="1fb69-125">W miejscu **Treść** dodaj moduł **Strona domyślna**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="1fb69-126">W module **Strona domyślna** w miejscu **Główne** dodaj moduł **Blok zawartości zaawansowanej**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="1fb69-127">W module **Blok zawartości zaawansowanej** dodaj moduł **Element bloku zawartości zaawansowanej**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="1fb69-128">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="1fb69-128">Check the template in, and publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="1fb69-129">Tworzenie strony zasad ochrony prywatności</span><span class="sxs-lookup"><span data-stu-id="1fb69-129">Build a privacy policy page</span></span>

<span data-ttu-id="1fb69-130">Aby utworzyć stronę zasad ochrony prywatności, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1fb69-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="1fb69-131">Przejdź do **Strony \> Nowa strona**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-131">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="1fb69-132">Wybierz szablon strony zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="1fb69-132">Select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="1fb69-133">Wprowadź nazwę i adres URL strony, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-133">Enter a page name and URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="1fb69-134">W miejscu **Główne** na stronie dodaj moduł **Blok zawartości zaawansowanej**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="1fb69-135">W module **Blok zawartości zaawansowanej** dodaj moduł **Element bloku zawartości zaawansowanej**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="1fb69-136">W okienku właściwości modułu **Blok zawartości zaawansowanej** wybierz pozycję **Dodaj źródło danych**, a następnie wybierz pozycję **Zawartość tekstu sformatowanego**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="1fb69-137">W edytorze tekstu sformatowanego wprowadź zawartość strony zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="1fb69-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="1fb69-138">W razie potrzeby rozwiń edytor tekstu sformatowanego do trybu pełnoekranowego.</span><span class="sxs-lookup"><span data-stu-id="1fb69-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="1fb69-139">Po zakończeniu wprowadzania zawartości wybierz pozycję **Podgląd**, aby wyświetlić podgląd strony w przeglądarce internetowej.</span><span class="sxs-lookup"><span data-stu-id="1fb69-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="1fb69-140">Zakończ wszystkie pozostałe operacje dodawania do właściwości strony i modułu.</span><span class="sxs-lookup"><span data-stu-id="1fb69-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="1fb69-141">Zaewidencjonuj stronę zasad ochrony prywatności i opublikuj ją.</span><span class="sxs-lookup"><span data-stu-id="1fb69-141">Check the privacy policy page in, and publish it.</span></span>

<span data-ttu-id="1fb69-142">Aby opublikować adres URL strony zasad ochrony prywatności, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1fb69-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="1fb69-143">Przejdź do obszaru **Adresy URL** i wybierz adres URL strony zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="1fb69-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="1fb69-144">Publikowanie wybranego adresu URL</span><span class="sxs-lookup"><span data-stu-id="1fb69-144">Publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="1fb69-145">Tworzenie linku do strony zasad ochrony prywatności w stopce</span><span class="sxs-lookup"><span data-stu-id="1fb69-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="1fb69-146">Do fragmentu można dodać link do strony zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="1fb69-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="1fb69-147">W ten sposób można udostępnić link i zaktualizować go na wielu stronach witryny, odwołując się do fragmentu.</span><span class="sxs-lookup"><span data-stu-id="1fb69-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="1fb69-148">W tym przykładzie pokazano, jak dodać link do strony zasad ochrony prywatności do fragmentu stopki.</span><span class="sxs-lookup"><span data-stu-id="1fb69-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="1fb69-149">Aby dodać link do fragmentu stopki, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1fb69-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="1fb69-150">Przejdź do pozycji **Fragmenty strony \> Nowy fragment strony**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-150">Go to **Page Fragments \> New Page Fragment**.</span></span>
1. <span data-ttu-id="1fb69-151">Wybierz moduł **Stopka**, a następnie wprowadź nazwę w polu **Nazwa fragmentu strony**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-151">Select the **Footer** module, and then enter a name in the **Page Fragment Name** field.</span></span>
1. <span data-ttu-id="1fb69-152">W miejscu **Kategoria stopki** dodaj moduł **Element stopki**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-152">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="1fb69-153">W panelu właściwości po prawej stronie wybierz pozycję **Tekst linku**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-153">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="1fb69-154">W oknie dialogowym **Tekst linku** wprowadź tekst linku i docelowy link strony zasady ochrony prywatności, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fb69-154">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>

    <span data-ttu-id="1fb69-155">Aby uzyskać adres URL strony zasad ochrony prywatności, przejdź do obszaru **Strony**, przejdź do strony zasad ochrony prywatności i skopiuj adres URL z okienka właściwości.</span><span class="sxs-lookup"><span data-stu-id="1fb69-155">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>

1. <span data-ttu-id="1fb69-156">Zapisz fragment, zaewidencjonuj go i opublikuj.</span><span class="sxs-lookup"><span data-stu-id="1fb69-156">Save the fragment, check it in, and publish it.</span></span>
1. <span data-ttu-id="1fb69-157">Wyświetl podgląd fragmentu i przetestuj link do strony zasad ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="1fb69-157">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="1fb69-158">Teraz można odwoływać się do fragmentu w szablonie dla innych stron witryny.</span><span class="sxs-lookup"><span data-stu-id="1fb69-158">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="1fb69-159">Gdy ten fragment jest przywoływany w module **Stopka** szablonu, odwołanie do linku pojawi się na wszystkich stronach, które zostaną zbudowane przy użyciu tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="1fb69-159">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1fb69-160">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1fb69-160">Additional resources</span></span>

[<span data-ttu-id="1fb69-161">Omówienie zgodności</span><span class="sxs-lookup"><span data-stu-id="1fb69-161">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="1fb69-162">Funkcje i możliwości dostępności</span><span class="sxs-lookup"><span data-stu-id="1fb69-162">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="1fb69-163">Zgodność z plikami cookie</span><span class="sxs-lookup"><span data-stu-id="1fb69-163">Cookie compliance</span></span>](cookie-compliance.md)
