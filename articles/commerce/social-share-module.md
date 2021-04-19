---
title: Moduł udostępnienia w mediach społecznościowych
description: W tym temacie opisano moduły udostępniania w plikach społecznościowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: c34410a8c817de9fed350bf2cd2dd918a37c230f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795364"
---
# <a name="social-share-module"></a><span data-ttu-id="9f5fd-103">Moduł udostępniania społeczności</span><span class="sxs-lookup"><span data-stu-id="9f5fd-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9f5fd-104">W tym temacie opisano moduły udostępniania w plikach społecznościowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9f5fd-105">Moduły udostępniania w mediach społecznych umożliwiają użytkownikom udostępnianie adresów URL stron witryn handlu elektronicznego w mediach społecznościowych takich jak Facebook, Twitter, Pinterest i LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-105">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="9f5fd-106">Adres URL witryny może być również udostępniany za pośrednictwem poczty e-mail.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-106">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="9f5fd-107">Moduły udostępniania w mediach społecznościowych są często używane na stronach szczegółów produktów (PDP), aby ułatwić użytkownikom udostępnianie informacji o produktach.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-107">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="9f5fd-108">Każdy moduł udostępniania w mediach społecznościowych jest kontenerem modułów udostępniania w mediach społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-108">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="9f5fd-109">Każdy moduł udostępniania w mediach społecznościowych można tak skonfigurować, aby wskazywał określony serwis społeczności.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-109">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="9f5fd-110">Integracja z usługą Facebook, Twitter, Pinterest, LinkedIn i pocztą e-mail jest obsługiwana domyślnie.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-110">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="9f5fd-111">Gdy użytkownik witryny wybierze symbol mediów społecznościowych, uruchamiany jest element HTML iframe dla odpowiedniej witryny sieci społecznościowej.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-111">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="9f5fd-112">W ramach iframe użytkownik może zalogować się i zapostować zawartość oglądanej strony.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-112">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="9f5fd-113">Każda platforma mediów społecznych może śledzić pliki cookie, więc ten moduł wymaga, aby użytkownicy witryny mogli akceptować wiadomość z powiadomieniem o zgodzie na wykorzystanie plików cookie.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-113">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="9f5fd-114">Jeśli nie otrzymano zgody na wykorzystanie pliku cookie, moduł zostanie ukryty na stronie.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-114">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="9f5fd-115">Aby uzyskać więcej informacji, zajrzyj do [Zgodność z plikami cookie](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="9f5fd-115">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="9f5fd-116">Na poniższej ilustracji przedstawiono przykład modułu udostępniania w mediach społecznościowych użytego na stronie Szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-116">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Przykład modułu udostępniania w mediach społecznościowych](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="9f5fd-118">Ustawienia modułu udostępnienia w mediach społecznościowych</span><span class="sxs-lookup"><span data-stu-id="9f5fd-118">Social share module properties</span></span>

| <span data-ttu-id="9f5fd-119">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="9f5fd-119">Property name</span></span>             | <span data-ttu-id="9f5fd-120">Wartość</span><span class="sxs-lookup"><span data-stu-id="9f5fd-120">Value</span></span>                 | <span data-ttu-id="9f5fd-121">opis</span><span class="sxs-lookup"><span data-stu-id="9f5fd-121">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="9f5fd-122">Podpis</span><span class="sxs-lookup"><span data-stu-id="9f5fd-122">Caption</span></span>                  | <span data-ttu-id="9f5fd-123">Tekst</span><span class="sxs-lookup"><span data-stu-id="9f5fd-123">Text</span></span> | <span data-ttu-id="9f5fd-124">Właściwość ta określa podpis modułu.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-124">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="9f5fd-125">Orientacja</span><span class="sxs-lookup"><span data-stu-id="9f5fd-125">Orientation</span></span> | <span data-ttu-id="9f5fd-126">**Pozioma** lub **Pionowa**</span><span class="sxs-lookup"><span data-stu-id="9f5fd-126">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="9f5fd-127">Ta właściwość określa orientację układu elementów mediów społeczności.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-127">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="9f5fd-128">Ustawienia elementu modułu udostępnienia w mediach społecznościowych</span><span class="sxs-lookup"><span data-stu-id="9f5fd-128">Social share item module properties</span></span>
| <span data-ttu-id="9f5fd-129">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="9f5fd-129">Property name</span></span>             | <span data-ttu-id="9f5fd-130">Wartość</span><span class="sxs-lookup"><span data-stu-id="9f5fd-130">Value</span></span>                 | <span data-ttu-id="9f5fd-131">opis</span><span class="sxs-lookup"><span data-stu-id="9f5fd-131">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="9f5fd-132">Media społecznościowe</span><span class="sxs-lookup"><span data-stu-id="9f5fd-132">Social media</span></span>              | <span data-ttu-id="9f5fd-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **E-mail**</span><span class="sxs-lookup"><span data-stu-id="9f5fd-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="9f5fd-134">Menu rozwijane z listą platform społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-134">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="9f5fd-135">Ikona</span><span class="sxs-lookup"><span data-stu-id="9f5fd-135">Icon</span></span> |<span data-ttu-id="9f5fd-136">Wizerunek</span><span class="sxs-lookup"><span data-stu-id="9f5fd-136">Image</span></span>    | <span data-ttu-id="9f5fd-137">Oto obraz, który będzie wyświetlany dla odpowiednich mediów społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-137">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="9f5fd-138">Najlepszym rozwiązaniem jest użycie zestawu SDK platformy społecznościowej w celu odnalezienia zalecanego obrazu, który ma być używany dla danej platformy.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-138">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="9f5fd-139">Dodawanie modułu udostępniania w mediach społecznościowych do pola zakupu</span><span class="sxs-lookup"><span data-stu-id="9f5fd-139">Add a social share module to a buy box module</span></span>

<span data-ttu-id="9f5fd-140">Aby dodać moduł udostępniania w mediach społecznościowych do pola zakupu, należy wykonać poniższe działania.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-140">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="9f5fd-141">W witrynie Fabrikam wybierz opcję **Strony**, a następnie wybrać stronę **DefaultPDP**, aby otworzyć stronę szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-141">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="9f5fd-142">W gnieździe **Pole zakupu** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-142">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9f5fd-143">W oknie dialogowym **Dodaj moduł** wybierz moduł **Udostępnianie w mediach społecznościowych** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-143">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9f5fd-144">W gnieździe **Udostępnianie w mediach społecznościowych** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-144">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9f5fd-145">W oknie dialogowym **Dodaj moduł** wybierz moduł **Udostępnianie w mediach społecznościowych** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-145">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9f5fd-146">W okienku właściwości modułu **Udostępnianie w mediach społecznościowych**, w obszarze **Orientacja** wybierz opcję **Pozioma**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-146">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="9f5fd-147">W razie potrzeby dodaj podpis.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-147">Add a caption as needed.</span></span>
1. <span data-ttu-id="9f5fd-148">W gnieździe **Udostępnianie w mediach społecznościowych** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-148">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9f5fd-149">W oknie dialogowym **Dodaj moduł** wybierz moduł **Element udostępniania** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-149">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9f5fd-150">W okienku właściwości modułu **Element udostępniania** w obszarze **Media społecznościowe** wybierz opcję **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-150">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="9f5fd-151">W okienku właściwości modułu **Element udostępniania** w obszarze **Ikona** wybierz opcję **+ Dodaj obraz**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-151">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="9f5fd-152">W oknie dialogowym **Selektor elementów multimedialnych** wybierz logo Facebook i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-152">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="9f5fd-153">Jeśli nie jest obecne logo Facebook, wybierz opcję **Wgraj nowy element multimedialny**, aby wgrać logo.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-153">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="9f5fd-154">W razie potrzeby dodaj i skonfiguruj dodatkowe moduły **Elementy udostępniania**.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-154">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="9f5fd-155">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-155">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="9f5fd-156">Na stronie zostanie wyświetlony moduł udostępniania w mediach społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-156">The page will show the social share module.</span></span>
1. <span data-ttu-id="9f5fd-157">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="9f5fd-157">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f5fd-158">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9f5fd-158">Additional resources</span></span>

[<span data-ttu-id="9f5fd-159">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="9f5fd-159">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9f5fd-160">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="9f5fd-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="9f5fd-161">Zgodność z plikami cookie</span><span class="sxs-lookup"><span data-stu-id="9f5fd-161">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]