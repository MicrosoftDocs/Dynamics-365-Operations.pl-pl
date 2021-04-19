---
title: Weryfikowanie dostępności zawartości strony
description: W tym temacie opisano, jak zweryfikować dostępność zawartości strony w aplikacji Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 885696c13b0e5353e6dbd9dc21cf075d5e301786
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791638"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="5fc31-103">Weryfikowanie dostępności zawartości strony</span><span class="sxs-lookup"><span data-stu-id="5fc31-103">Verify page content accessibility</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5fc31-104">W tym temacie opisano, jak zweryfikować dostępność zawartości strony w aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5fc31-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5fc31-105">Po zakończeniu zmieniania strony należy upewnić się, że zawartość jest dostępna dla wszystkich użytkowników w Internecie.</span><span class="sxs-lookup"><span data-stu-id="5fc31-105">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="5fc31-106">W narzędziach autorskich usługi Commerce można łatwo zweryfikować dostępność zawartości strony przy użyciu zintegrowanej usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/).</span><span class="sxs-lookup"><span data-stu-id="5fc31-106">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="5fc31-107">Ta usługa weryfikuje zawartość strony względem najnowszych wskazówek dotyczących [ułatwień dostępu organizacji World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).</span><span class="sxs-lookup"><span data-stu-id="5fc31-107">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="5fc31-108">Integracja usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) musi być włączona na poziomie dzierżawy lub witryny, zanim będzie można jej używać.</span><span class="sxs-lookup"><span data-stu-id="5fc31-108">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="5fc31-109">Włączanie usługi Microsoft Accessibility Insights dla wszystkich witryn w dzierżawie</span><span class="sxs-lookup"><span data-stu-id="5fc31-109">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="5fc31-110">Aby włączyć integrację usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) dla wszystkich witryn usługi Commerce w dzierżawie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5fc31-110">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="5fc31-111">Aby uzyskać dostęp do ustawień dzierżawy, użytkownik musi być zalogowany w usłudze Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="5fc31-111">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="5fc31-112">Zaloguj się do usługi Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="5fc31-112">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="5fc31-113">W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="5fc31-113">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="5fc31-114">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="5fc31-114">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="5fc31-115">Ustaw opcję **Sprawdzanie ułatwień dostępu** na **Wł.**</span><span class="sxs-lookup"><span data-stu-id="5fc31-115">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="5fc31-116">Włączanie usługi Microsoft Accessibility Insights dla pojedynczej witryny</span><span class="sxs-lookup"><span data-stu-id="5fc31-116">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="5fc31-117">Aby włączyć integrację usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) dla pojedynczej witryny usługi Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5fc31-117">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="5fc31-118">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="5fc31-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="5fc31-119">W lewym okienku nawigacji wybierz pozycję **Ustawienia witryny**, aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="5fc31-119">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="5fc31-120">W obszarze **Ustawienia witryny** wybierz pozycję **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="5fc31-120">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="5fc31-121">Ustaw opcję **Sprawdzanie ułatwień dostępu** na **Wł.**</span><span class="sxs-lookup"><span data-stu-id="5fc31-121">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="5fc31-122">Weryfikowanie dostępności zawartości na stronie głównej</span><span class="sxs-lookup"><span data-stu-id="5fc31-122">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="5fc31-123">Aby używać zintegrowanej usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) do skanowania i weryfikowania zawartości strony głównej w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5fc31-123">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="5fc31-124">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="5fc31-124">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="5fc31-125">W okienku nawigacji po lewej stronie wybierz pozycję **Strony**.</span><span class="sxs-lookup"><span data-stu-id="5fc31-125">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="5fc31-126">Znajdź i wybierz stronę główną, aby otworzyć ją w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="5fc31-126">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="5fc31-127">Na pasku poleceń wybierz opcję **Sprawdź dostępność**.</span><span class="sxs-lookup"><span data-stu-id="5fc31-127">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="5fc31-128">Zostanie wyświetlona strona **sprawdzania dostępności**.</span><span class="sxs-lookup"><span data-stu-id="5fc31-128">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="5fc31-129">Po zakończeniu skanowania przejrzyj zawartość raportu.</span><span class="sxs-lookup"><span data-stu-id="5fc31-129">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="5fc31-130">Jeśli dowolne testy nie powiodą się, wybierz każdy sprawdzony element z błędem, aby go rozwinąć i wyświetlić więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="5fc31-130">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="5fc31-131">Aby zamknąć raport po zakończeniu przeglądania, przewiń w dół strony **sprawdzania dostępności** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fc31-131">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5fc31-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5fc31-132">Additional resources</span></span>

[<span data-ttu-id="5fc31-133">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="5fc31-133">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="5fc31-134">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="5fc31-134">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="5fc31-135">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="5fc31-135">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="5fc31-136">Zarządzanie metadanymi SEO</span><span class="sxs-lookup"><span data-stu-id="5fc31-136">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="5fc31-137">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="5fc31-137">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="5fc31-138">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="5fc31-138">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="5fc31-139">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="5fc31-139">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="5fc31-140">Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL</span><span class="sxs-lookup"><span data-stu-id="5fc31-140">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
