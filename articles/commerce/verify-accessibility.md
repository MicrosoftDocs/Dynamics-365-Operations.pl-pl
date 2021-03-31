---
title: Weryfikowanie dostępności zawartości strony
description: W tym temacie opisano, jak zweryfikować dostępność zawartości strony w aplikacji Microsoft Dynamics 365 Commerce.
author: josaw1
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 186044fc7a360f227cecffb39bad0e225245dd4d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210978"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="a11e0-103">Weryfikowanie dostępności zawartości strony</span><span class="sxs-lookup"><span data-stu-id="a11e0-103">Verify page content accessibility</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a11e0-104">W tym temacie opisano, jak zweryfikować dostępność zawartości strony w aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a11e0-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a11e0-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a11e0-105">Overview</span></span>

<span data-ttu-id="a11e0-106">Po zakończeniu zmieniania strony należy upewnić się, że zawartość jest dostępna dla wszystkich użytkowników w Internecie.</span><span class="sxs-lookup"><span data-stu-id="a11e0-106">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="a11e0-107">W narzędziach autorskich usługi Commerce można łatwo zweryfikować dostępność zawartości strony przy użyciu zintegrowanej usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/).</span><span class="sxs-lookup"><span data-stu-id="a11e0-107">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="a11e0-108">Ta usługa weryfikuje zawartość strony względem najnowszych wskazówek dotyczących [ułatwień dostępu organizacji World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).</span><span class="sxs-lookup"><span data-stu-id="a11e0-108">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="a11e0-109">Integracja usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) musi być włączona na poziomie dzierżawy lub witryny, zanim będzie można jej używać.</span><span class="sxs-lookup"><span data-stu-id="a11e0-109">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="a11e0-110">Włączanie usługi Microsoft Accessibility Insights dla wszystkich witryn w dzierżawie</span><span class="sxs-lookup"><span data-stu-id="a11e0-110">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="a11e0-111">Aby włączyć integrację usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) dla wszystkich witryn usługi Commerce w dzierżawie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a11e0-111">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="a11e0-112">Aby uzyskać dostęp do ustawień dzierżawy, użytkownik musi być zalogowany w usłudze Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="a11e0-112">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="a11e0-113">Zaloguj się do usługi Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="a11e0-113">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="a11e0-114">W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="a11e0-114">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="a11e0-115">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="a11e0-115">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="a11e0-116">Ustaw opcję **Sprawdzanie ułatwień dostępu** na **Wł.**</span><span class="sxs-lookup"><span data-stu-id="a11e0-116">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="a11e0-117">Włączanie usługi Microsoft Accessibility Insights dla pojedynczej witryny</span><span class="sxs-lookup"><span data-stu-id="a11e0-117">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="a11e0-118">Aby włączyć integrację usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) dla pojedynczej witryny usługi Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a11e0-118">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="a11e0-119">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="a11e0-119">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="a11e0-120">W lewym okienku nawigacji wybierz pozycję **Ustawienia witryny**, aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="a11e0-120">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="a11e0-121">W obszarze **Ustawienia witryny** wybierz pozycję **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="a11e0-121">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="a11e0-122">Ustaw opcję **Sprawdzanie ułatwień dostępu** na **Wł.**</span><span class="sxs-lookup"><span data-stu-id="a11e0-122">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="a11e0-123">Weryfikowanie dostępności zawartości na stronie głównej</span><span class="sxs-lookup"><span data-stu-id="a11e0-123">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="a11e0-124">Aby używać zintegrowanej usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) do skanowania i weryfikowania zawartości strony głównej w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a11e0-124">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="a11e0-125">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="a11e0-125">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="a11e0-126">W okienku nawigacji po lewej stronie wybierz pozycję **Strony**.</span><span class="sxs-lookup"><span data-stu-id="a11e0-126">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="a11e0-127">Znajdź i wybierz stronę główną, aby otworzyć ją w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="a11e0-127">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="a11e0-128">Na pasku poleceń wybierz opcję **Sprawdź dostępność**.</span><span class="sxs-lookup"><span data-stu-id="a11e0-128">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="a11e0-129">Zostanie wyświetlona strona **sprawdzania dostępności**.</span><span class="sxs-lookup"><span data-stu-id="a11e0-129">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="a11e0-130">Po zakończeniu skanowania przejrzyj zawartość raportu.</span><span class="sxs-lookup"><span data-stu-id="a11e0-130">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="a11e0-131">Jeśli dowolne testy nie powiodą się, wybierz każdy sprawdzony element z błędem, aby go rozwinąć i wyświetlić więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="a11e0-131">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="a11e0-132">Aby zamknąć raport po zakończeniu przeglądania, przewiń w dół strony **sprawdzania dostępności** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a11e0-132">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a11e0-133">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a11e0-133">Additional resources</span></span>

[<span data-ttu-id="a11e0-134">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="a11e0-134">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="a11e0-135">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="a11e0-135">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="a11e0-136">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="a11e0-136">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="a11e0-137">Zarządzanie metadanymi SEO</span><span class="sxs-lookup"><span data-stu-id="a11e0-137">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="a11e0-138">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="a11e0-138">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="a11e0-139">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="a11e0-139">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="a11e0-140">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="a11e0-140">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="a11e0-141">Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL</span><span class="sxs-lookup"><span data-stu-id="a11e0-141">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]