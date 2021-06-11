---
title: Zastosuj ustawienia wyświetlania dla wymiarów produktu
description: W tym temacie omówiono ustawienia wyświetlania wymiarów produktów i opisano sposób ich stosowania w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: b901622bbfc8d6b3066879f6456a4ab618ca4076
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117241"
---
# <a name="apply-display-settings-for-product-dimensions"></a><span data-ttu-id="1effc-103">Zastosuj ustawienia wyświetlania dla wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="1effc-103">Apply display settings for product dimensions</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="1effc-104">W tym temacie omówiono ustawienia wyświetlania wymiarów produktów i opisano sposób ich stosowania w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1effc-104">This topic covers the display settings for product dimensions and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1effc-105">Dynamics 365 Commerce umożliwia używanie wymiarów typu rozmiar, styl i kolor do rozróżniania wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="1effc-105">Dynamics 365 Commerce supports size, style, and color dimensions to distinguish product variants.</span></span> <span data-ttu-id="1effc-106">Wymiary są zwykle wyświetlane jako wartości tekstowe, takie jak „Mały”, „Średni” i „Duży” dla rozmiarów, oraz „Czarna” i „Brązowy” w przypadku kolorów.</span><span class="sxs-lookup"><span data-stu-id="1effc-106">Dimensions are typically shown as text values, such as "Small," "Medium," and "Large" for sizes, and "Black" and "Brown" for colors.</span></span> <span data-ttu-id="1effc-107">Jeśli jednak produkt posiada wiele wariantów, ich przeglądanie może być trudne, ponieważ do wyświetlenia obrazu dla każdego wariantu wymagane jest wielokrotne wybranie opcji.</span><span class="sxs-lookup"><span data-stu-id="1effc-107">However, if a product supports many variations, it can be difficult to browse product variants, because multiple selections are required to view the image for each variant.</span></span> <span data-ttu-id="1effc-108">Aby ułatwić przeglądanie wariantów produktów, wersja 10.0.20 Commerce może używać obrazów i kodów szesnastkowych (hex), aby pokazać wymiary jako próbki.</span><span class="sxs-lookup"><span data-stu-id="1effc-108">To make it easier to browse product variants, the version 10.0.20 release of Commerce can use images and hexadecimal (hex) codes to show dimensions as swatches.</span></span>

<span data-ttu-id="1effc-109">W konstruktorze witryn. Commerce ustawienia wymiarów są definiowane w **Ustawienia witryny \> Rozszerzenia \> Zarządzanie zapasami**.</span><span class="sxs-lookup"><span data-stu-id="1effc-109">In Commerce site builder, dimension settings are defined at **Site Settings \> Extensions \> Dimension Settings**.</span></span> <span data-ttu-id="1effc-110">Poniższa ilustracja pokazuje przykład ustawień wymiarów w programie do budowania witryn.</span><span class="sxs-lookup"><span data-stu-id="1effc-110">The following illustration shows an example of dimension settings in site builder.</span></span>

![Przykład ustawień witryny w kreatorze witryn Commerce](./dev-itpro/media/swatch_site_settings.PNG)

<span data-ttu-id="1effc-112">Dostępne są dwa ustawienia wymiarów:</span><span class="sxs-lookup"><span data-stu-id="1effc-112">Two dimension settings are available:</span></span>

- <span data-ttu-id="1effc-113">**Wymiary wyświetlane jako obrazy** — Określeni, które wymiary powinny być wyświetlane jako próbki na stronach witryny e-commerce, takich jak strony szczegółów produktu (PDP) i strony z listą wyników wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="1effc-113">**Dimensions to display as image** – Specify which dimensions should appear as swatches on e-commerce site pages such as product details pages (PDPs) and search result list pages.</span></span> <span data-ttu-id="1effc-114">Każda kombinacja kolorów, rozmiarów i stylów może być pokazana jako próbka.</span><span class="sxs-lookup"><span data-stu-id="1effc-114">Any combination of color, size, and style dimensions can be shown as a swatch.</span></span> <span data-ttu-id="1effc-115">Jeśli wymiar zostanie wybrany do wyświetlenia jako próbka, moduł Commerce będzie szukał dostępnej konfiguracji próbki z kodem heksadecymalnym.</span><span class="sxs-lookup"><span data-stu-id="1effc-115">If a dimension is selected for display as a swatch, Commerce module rendering will look for an available configuration of a hex code swatch.</span></span> <span data-ttu-id="1effc-116">Jeśli nie skonfigurowano kodu heksadecymalnego, logika systemu będzie szukać konfiguracji wzorca URL obrazu.</span><span class="sxs-lookup"><span data-stu-id="1effc-116">If no hex code is configured, system logic will look for a configuration of an image URL swatch.</span></span> <span data-ttu-id="1effc-117">Jeśli nie skonfigurowano ani kodu heksadecymalnego, ani adresu URL obrazu, zostanie wyświetlony tekst.</span><span class="sxs-lookup"><span data-stu-id="1effc-117">If neither a hex code nor an image URL is configured, text will be shown.</span></span>

    <span data-ttu-id="1effc-118">Poniższa ilustracja przedstawia przykład, w którym PDP na stronie e-commerce zawiera próbki kolorów i rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="1effc-118">The following illustration shows an example where a PDP on an e-commerce site includes color and size swatches.</span></span> <span data-ttu-id="1effc-119">W tym przykładzie kod heksadecymalny jest skonfigurowany dla wymiaru koloru.</span><span class="sxs-lookup"><span data-stu-id="1effc-119">In this example, a hex code is configured for the color dimension.</span></span> <span data-ttu-id="1effc-120">W związku z tym próbki są wyświetlane jako kolory.</span><span class="sxs-lookup"><span data-stu-id="1effc-120">Therefore, swatches are shown as colors.</span></span> <span data-ttu-id="1effc-121">Jednak ani kod heksadecymalny, ani adres URL obrazu nie są skonfigurowane dla wymiaru wielkości.</span><span class="sxs-lookup"><span data-stu-id="1effc-121">However, neither a hex code nor an image URL is configured for the size dimension.</span></span> <span data-ttu-id="1effc-122">W związku z tym jest wyświetlany tekst.</span><span class="sxs-lookup"><span data-stu-id="1effc-122">Therefore, text is shown.</span></span>

    ![Przykład wymiarów kolorów pokazanych jako próbki na stronie szczegółów produktu e-commerce](./dev-itpro/media/swatch_pdp.png)

- <span data-ttu-id="1effc-124">**Wymiary wyświetlane na karcie produktu** — umożliwia określenie, które wymiary powinny być wyświetlane na kartach produktów widocznych na listach i na stronach list.</span><span class="sxs-lookup"><span data-stu-id="1effc-124">**Dimensions to display in product card** – Specify which dimensions should appear on product cards that are shown in lists and on list pages.</span></span> <span data-ttu-id="1effc-125">Aby wymiar mógł pojawić się na karcie produktu, ustawienie to musi być włączone dla tego wymiaru.</span><span class="sxs-lookup"><span data-stu-id="1effc-125">Before a dimension can appear on a product card, this setting must be enabled for that dimension.</span></span> <span data-ttu-id="1effc-126">Należy również włączyć ustawienie **Wymiary wyświetlane jako obraz**.</span><span class="sxs-lookup"><span data-stu-id="1effc-126">The **Dimensions to display as image** setting should also be enabled.</span></span> <span data-ttu-id="1effc-127">Zachowanie przy wyborze próbek na kartach produktów jest zoptymalizowane dla wymiaru kolorów.</span><span class="sxs-lookup"><span data-stu-id="1effc-127">The swatch selection behavior on product cards is optimized for the color dimension.</span></span> <span data-ttu-id="1effc-128">W przypadku innych wymiarów może być wymagane rozszerzenie widoku, aby dostosować zachowanie wyboru wzorca.</span><span class="sxs-lookup"><span data-stu-id="1effc-128">For other dimensions, a view extension might be required to customize swatch selection behavior.</span></span>

    <span data-ttu-id="1effc-129">Poniższa ilustracja przedstawia przykład, w którym strona z listą w witrynie e-commerce zawiera karty produktów zawierające próbki kolorów.</span><span class="sxs-lookup"><span data-stu-id="1effc-129">The following illustration shows an example where a list page on an e-commerce site contains product cards that include color swatches.</span></span>

    ![Przykład wymiarów kolorów pokazanych jako próbki na listy produktu e-commerce](./dev-itpro/media/swatch_searchresults.PNG)

<span data-ttu-id="1effc-131">Aby uzyskać więcej informacji na temat konfigurowania wymiarów produktów w taki sposób, aby były one wyświetlane jako próbki na stronach witryny, patrz [Konfigurowanie wartości wymiarów produktów, aby były wyświetlane jako próbki](./dev-itpro/dimensions-swatch.md).</span><span class="sxs-lookup"><span data-stu-id="1effc-131">For information about how to configure product dimensions so that they are shown as swatches on site pages, see [Configure product dimension values to appear as swatches](./dev-itpro/dimensions-swatch.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1effc-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1effc-132">Additional resources</span></span>

[<span data-ttu-id="1effc-133">Przegląd biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="1effc-133">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1effc-134">Moduł wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="1effc-134">Search results module</span></span>](search-result-module.md)

[<span data-ttu-id="1effc-135">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="1effc-135">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="1effc-136">Skonfiguruj wartości wymiarów produktu, aby były wyświetlane jako próbki</span><span class="sxs-lookup"><span data-stu-id="1effc-136">Configure product dimension values to appear as swatches</span></span>](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
