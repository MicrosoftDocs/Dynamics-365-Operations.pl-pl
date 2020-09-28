---
title: Moduł udostępnienia w mediach społecznościowych
description: W tym temacie opisano moduły udostępniania w plikach społecznościowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 0fd81aa1f4b1358528f0135c1334dc7b4ac4461f
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761416"
---
# <a name="social-share-module"></a><span data-ttu-id="f7fef-103">Moduł udostępnienia w mediach społecznościowych</span><span class="sxs-lookup"><span data-stu-id="f7fef-103">Social share module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="f7fef-104">W tym temacie opisano moduły udostępniania w plikach społecznościowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f7fef-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f7fef-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="f7fef-105">Overview</span></span>

<span data-ttu-id="f7fef-106">Moduły udostępniania w mediach społecznych umożliwiają użytkownikom udostępnianie adresów URL stron witryn handlu elektronicznego w mediach społecznościowych takich jak Facebook, Twitter, Pinterest i LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="f7fef-106">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="f7fef-107">Adres URL witryny może być również udostępniany za pośrednictwem poczty e-mail.</span><span class="sxs-lookup"><span data-stu-id="f7fef-107">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="f7fef-108">Moduły udostępniania w mediach społecznościowych są często używane na stronach szczegółów produktów (PDP), aby ułatwić użytkownikom udostępnianie informacji o produktach.</span><span class="sxs-lookup"><span data-stu-id="f7fef-108">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="f7fef-109">Każdy moduł udostępniania w mediach społecznościowych jest kontenerem modułów udostępniania w mediach społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="f7fef-109">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="f7fef-110">Każdy moduł udostępniania w mediach społecznościowych można tak skonfigurować, aby wskazywał określony serwis społeczności.</span><span class="sxs-lookup"><span data-stu-id="f7fef-110">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="f7fef-111">Integracja z usługą Facebook, Twitter, Pinterest, LinkedIn i pocztą e-mail jest obsługiwana domyślnie.</span><span class="sxs-lookup"><span data-stu-id="f7fef-111">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="f7fef-112">Gdy użytkownik witryny wybierze symbol mediów społecznościowych, uruchamiany jest element HTML iframe dla odpowiedniej witryny sieci społecznościowej.</span><span class="sxs-lookup"><span data-stu-id="f7fef-112">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="f7fef-113">W ramach iframe użytkownik może zalogować się i zapostować zawartość oglądanej strony.</span><span class="sxs-lookup"><span data-stu-id="f7fef-113">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="f7fef-114">Każda platforma mediów społecznych może śledzić pliki cookie, więc ten moduł wymaga, aby użytkownicy witryny mogli akceptować wiadomość z powiadomieniem o zgodzie na wykorzystanie plików cookie.</span><span class="sxs-lookup"><span data-stu-id="f7fef-114">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="f7fef-115">Jeśli nie otrzymano zgody na wykorzystanie pliku cookie, moduł zostanie ukryty na stronie.</span><span class="sxs-lookup"><span data-stu-id="f7fef-115">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="f7fef-116">Aby uzyskać więcej informacji, zajrzyj do [Zgodność z plikami cookie](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="f7fef-116">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="f7fef-117">Na poniższej ilustracji przedstawiono przykład modułu udostępniania w mediach społecznościowych użytego na stronie Szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="f7fef-117">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Przykład modułu udostępniania w mediach społecznościowych](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="f7fef-119">Ustawienia modułu udostępnienia w mediach społecznościowych</span><span class="sxs-lookup"><span data-stu-id="f7fef-119">Social share module properties</span></span>

| <span data-ttu-id="f7fef-120">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="f7fef-120">Property name</span></span>             | <span data-ttu-id="f7fef-121">Wartość</span><span class="sxs-lookup"><span data-stu-id="f7fef-121">Value</span></span>                 | <span data-ttu-id="f7fef-122">opis</span><span class="sxs-lookup"><span data-stu-id="f7fef-122">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="f7fef-123">Podpis</span><span class="sxs-lookup"><span data-stu-id="f7fef-123">Caption</span></span>                  | <span data-ttu-id="f7fef-124">Tekst</span><span class="sxs-lookup"><span data-stu-id="f7fef-124">Text</span></span> | <span data-ttu-id="f7fef-125">Właściwość ta określa podpis modułu.</span><span class="sxs-lookup"><span data-stu-id="f7fef-125">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="f7fef-126">Orientacja</span><span class="sxs-lookup"><span data-stu-id="f7fef-126">Orientation</span></span> | <span data-ttu-id="f7fef-127">**Pozioma** lub **Pionowa**</span><span class="sxs-lookup"><span data-stu-id="f7fef-127">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="f7fef-128">Ta właściwość określa orientację układu elementów mediów społeczności.</span><span class="sxs-lookup"><span data-stu-id="f7fef-128">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="f7fef-129">Ustawienia elementu modułu udostępnienia w mediach społecznościowych</span><span class="sxs-lookup"><span data-stu-id="f7fef-129">Social share item module properties</span></span>
| <span data-ttu-id="f7fef-130">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="f7fef-130">Property name</span></span>             | <span data-ttu-id="f7fef-131">Wartość</span><span class="sxs-lookup"><span data-stu-id="f7fef-131">Value</span></span>                 | <span data-ttu-id="f7fef-132">opis</span><span class="sxs-lookup"><span data-stu-id="f7fef-132">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="f7fef-133">Media społecznościowe</span><span class="sxs-lookup"><span data-stu-id="f7fef-133">Social media</span></span>              | <span data-ttu-id="f7fef-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **E-mail**</span><span class="sxs-lookup"><span data-stu-id="f7fef-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="f7fef-135">Menu rozwijane z listą platform społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="f7fef-135">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="f7fef-136">Ikona</span><span class="sxs-lookup"><span data-stu-id="f7fef-136">Icon</span></span> |<span data-ttu-id="f7fef-137">Wizerunek</span><span class="sxs-lookup"><span data-stu-id="f7fef-137">Image</span></span>    | <span data-ttu-id="f7fef-138">Oto obraz, który będzie wyświetlany dla odpowiednich mediów społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="f7fef-138">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="f7fef-139">Najlepszym rozwiązaniem jest użycie zestawu SDK platformy społecznościowej w celu odnalezienia zalecanego obrazu, który ma być używany dla danej platformy.</span><span class="sxs-lookup"><span data-stu-id="f7fef-139">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="f7fef-140">Dodawanie modułu udostępniania w mediach społecznościowych do pola zakupu</span><span class="sxs-lookup"><span data-stu-id="f7fef-140">Add a social share module to a buy box module</span></span>

<span data-ttu-id="f7fef-141">Aby dodać moduł udostępniania w mediach społecznościowych do pola zakupu, należy wykonać poniższe działania.</span><span class="sxs-lookup"><span data-stu-id="f7fef-141">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="f7fef-142">W witrynie Fabrikam wybierz opcję **Strony**, a następnie wybrać stronę **DefaultPDP**, aby otworzyć stronę szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="f7fef-142">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="f7fef-143">W gnieździe **Pole zakupu** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-143">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7fef-144">W oknie dialogowym **Dodaj moduł** wybierz moduł **Udostępnianie w mediach społecznościowych** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-144">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f7fef-145">W gnieździe **Udostępnianie w mediach społecznościowych** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-145">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7fef-146">W oknie dialogowym **Dodaj moduł** wybierz moduł **Udostępnianie w mediach społecznościowych** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-146">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f7fef-147">W okienku właściwości modułu **Udostępnianie w mediach społecznościowych**, w obszarze **Orientacja** wybierz opcję **Pozioma**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-147">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="f7fef-148">W razie potrzeby dodaj podpis.</span><span class="sxs-lookup"><span data-stu-id="f7fef-148">Add a caption as needed.</span></span>
1. <span data-ttu-id="f7fef-149">W gnieździe **Udostępnianie w mediach społecznościowych** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-149">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7fef-150">W oknie dialogowym **Dodaj moduł** wybierz moduł **Element udostępniania** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-150">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f7fef-151">W okienku właściwości modułu **Element udostępniania** w obszarze **Media społecznościowe** wybierz opcję **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-151">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="f7fef-152">W okienku właściwości modułu **Element udostępniania** w obszarze **Ikona** wybierz opcję **+ Dodaj obraz**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-152">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="f7fef-153">W oknie dialogowym **Selektor elementów multimedialnych** wybierz logo Facebook i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-153">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="f7fef-154">Jeśli nie jest obecne logo Facebook, wybierz opcję **Wgraj nowy element multimedialny**, aby wgrać logo.</span><span class="sxs-lookup"><span data-stu-id="f7fef-154">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="f7fef-155">W razie potrzeby dodaj i skonfiguruj dodatkowe moduły **Elementy udostępniania**.</span><span class="sxs-lookup"><span data-stu-id="f7fef-155">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="f7fef-156">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="f7fef-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="f7fef-157">Na stronie zostanie wyświetlony moduł udostępniania w mediach społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="f7fef-157">The page will show the social share module.</span></span>
1. <span data-ttu-id="f7fef-158">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="f7fef-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f7fef-159">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f7fef-159">Additional resources</span></span>

[<span data-ttu-id="f7fef-160">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="f7fef-160">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f7fef-161">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="f7fef-161">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="f7fef-162">Zgodność z plikami cookie</span><span class="sxs-lookup"><span data-stu-id="f7fef-162">Cookie compliance</span></span>](cookie-compliance.md)
