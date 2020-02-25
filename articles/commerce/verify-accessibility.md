---
title: Weryfikowanie dostępności zawartości strony
description: W tym temacie opisano, jak zweryfikować dostępność zawartości strony w aplikacji Microsoft Dynamics 365 Commerce.
author: arotkin
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: arotkin
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8e35b0f71ff41bade266fb177e4500c7d124ed1f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002666"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="61cf3-103">Weryfikowanie dostępności zawartości strony</span><span class="sxs-lookup"><span data-stu-id="61cf3-103">Verify page content accessibility</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="61cf3-104">W tym temacie opisano, jak zweryfikować dostępność zawartości strony w aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="61cf3-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="61cf3-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="61cf3-105">Overview</span></span>

<span data-ttu-id="61cf3-106">Po zakończeniu zmieniania strony należy upewnić się, że zawartość jest dostępna dla wszystkich użytkowników w Internecie.</span><span class="sxs-lookup"><span data-stu-id="61cf3-106">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="61cf3-107">W narzędziach autorskich usługi Commerce można łatwo zweryfikować dostępność zawartości strony przy użyciu zintegrowanej usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/).</span><span class="sxs-lookup"><span data-stu-id="61cf3-107">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="61cf3-108">Ta usługa weryfikuje zawartość strony względem najnowszych wskazówek dotyczących [ułatwień dostępu organizacji World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).</span><span class="sxs-lookup"><span data-stu-id="61cf3-108">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="61cf3-109">Integracja usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) musi być włączona na poziomie dzierżawy lub witryny, zanim będzie można jej używać.</span><span class="sxs-lookup"><span data-stu-id="61cf3-109">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="61cf3-110">Włączanie usługi Microsoft Accessibility Insights dla wszystkich witryn w dzierżawie</span><span class="sxs-lookup"><span data-stu-id="61cf3-110">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="61cf3-111">Aby włączyć integrację usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) dla wszystkich witryn usługi Commerce w dzierżawie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="61cf3-111">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="61cf3-112">Aby uzyskać dostęp do ustawień dzierżawy, użytkownik musi być zalogowany w usłudze Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="61cf3-112">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="61cf3-113">Zaloguj się do usługi Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="61cf3-113">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="61cf3-114">W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="61cf3-114">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="61cf3-115">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="61cf3-115">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="61cf3-116">Ustaw opcję **Sprawdzanie ułatwień dostępu** na **Wł.**</span><span class="sxs-lookup"><span data-stu-id="61cf3-116">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="61cf3-117">Włączanie usługi Microsoft Accessibility Insights dla pojedynczej witryny</span><span class="sxs-lookup"><span data-stu-id="61cf3-117">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="61cf3-118">Aby włączyć integrację usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) dla pojedynczej witryny usługi Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="61cf3-118">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="61cf3-119">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="61cf3-119">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="61cf3-120">W lewym okienku nawigacji wybierz pozycję **Ustawienia witryny**, aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="61cf3-120">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="61cf3-121">W obszarze **Ustawienia witryny** wybierz pozycję **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="61cf3-121">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="61cf3-122">Ustaw opcję **Sprawdzanie ułatwień dostępu** na **Wł.**</span><span class="sxs-lookup"><span data-stu-id="61cf3-122">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="61cf3-123">Weryfikowanie dostępności zawartości na stronie głównej</span><span class="sxs-lookup"><span data-stu-id="61cf3-123">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="61cf3-124">Aby używać zintegrowanej usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) do skanowania i weryfikowania zawartości strony głównej w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="61cf3-124">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="61cf3-125">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="61cf3-125">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="61cf3-126">W okienku nawigacji po lewej stronie wybierz pozycję **Strony**.</span><span class="sxs-lookup"><span data-stu-id="61cf3-126">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="61cf3-127">Znajdź i wybierz stronę główną, aby otworzyć ją w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="61cf3-127">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="61cf3-128">Na pasku poleceń wybierz opcję **Sprawdź dostępność**.</span><span class="sxs-lookup"><span data-stu-id="61cf3-128">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="61cf3-129">Zostanie wyświetlona strona **sprawdzania dostępności**.</span><span class="sxs-lookup"><span data-stu-id="61cf3-129">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="61cf3-130">Po zakończeniu skanowania przejrzyj zawartość raportu.</span><span class="sxs-lookup"><span data-stu-id="61cf3-130">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="61cf3-131">Jeśli dowolne testy nie powiodą się, wybierz każdy sprawdzony element z błędem, aby go rozwinąć i wyświetlić więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="61cf3-131">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="61cf3-132">Aby zamknąć raport po zakończeniu przeglądania, przewiń w dół strony **sprawdzania dostępności** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="61cf3-132">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61cf3-133">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="61cf3-133">Additional resources</span></span>

[<span data-ttu-id="61cf3-134">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="61cf3-134">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="61cf3-135">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="61cf3-135">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="61cf3-136">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="61cf3-136">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="61cf3-137">Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="61cf3-137">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="61cf3-138">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="61cf3-138">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="61cf3-139">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="61cf3-139">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="61cf3-140">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="61cf3-140">Enrich a category landing page</span></span>](enrich-category-page.md)
