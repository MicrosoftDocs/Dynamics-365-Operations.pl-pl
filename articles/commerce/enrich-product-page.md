---
title: Wzbogacanie strony produktu
description: W tym temacie opisano sposób wzbogacania strony produktu w Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d9c0f329d21cdda5c36a39a8c602d5925b720f52
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945750"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="b43ef-103">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="b43ef-103">Enrich a product page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="b43ef-104">W tym temacie opisano sposób wzbogacania strony produktu w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b43ef-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b43ef-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="b43ef-105">Overview</span></span>

<span data-ttu-id="b43ef-106">Domyślnie witryna używa strony ogólnej do wyświetlania danych produktu.</span><span class="sxs-lookup"><span data-stu-id="b43ef-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="b43ef-107">Ta strona zawiera podstawowe informacje o produkcie i formantach, które są wymagane do jego sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b43ef-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="b43ef-108">Można jednak uzupełnić informacje pochodzące z serwera Retail dodatkowymi obrazami lub tekstami dla określonego produktu.</span><span class="sxs-lookup"><span data-stu-id="b43ef-108">However, you can supplement the information that comes from the Retail Server with additional images or text for a specific product.</span></span> <span data-ttu-id="b43ef-109">Ten proces jest znany jako wzbogacanie strony produktu.</span><span class="sxs-lookup"><span data-stu-id="b43ef-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="b43ef-110">W wielu przypadkach użytkownik chce użyć konkretnej zawartości dodatkowej w odniesieniu do produktów.</span><span class="sxs-lookup"><span data-stu-id="b43ef-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="b43ef-111">Po przejściu do **Retail** w narzędziu autorskim zostanie wyświetlona lista produktów z kanału przypisanego do danego oddziału.</span><span class="sxs-lookup"><span data-stu-id="b43ef-111">When you go to **Retail** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="b43ef-112">Na tej liście **Wzbogacone** kolumna wskazuje, czy dana strona produktu została wzbogacona.</span><span class="sxs-lookup"><span data-stu-id="b43ef-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="b43ef-113">Jeśli w kolumnie zostanie wyświetlony znacznik wyboru, dla produktu istnieje wzbogacona strona produktu</span><span class="sxs-lookup"><span data-stu-id="b43ef-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="b43ef-114">Jeśli żaden znacznik wyboru nie zostanie wyświetlony, dla produktu zostanie użyta domyślna strona produktu i zawartość.</span><span class="sxs-lookup"><span data-stu-id="b43ef-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="b43ef-115">Można przeglądać zarówno wzbogacone, jak i niewzbogacone strony produktu, wybierając nazwę produktu z listy.</span><span class="sxs-lookup"><span data-stu-id="b43ef-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="b43ef-116">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="b43ef-116">Enrich a product page</span></span>

<span data-ttu-id="b43ef-117">Aby wzbogacić stronę produktu, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b43ef-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="b43ef-118">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="b43ef-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="b43ef-119">W okienku nawigacji po lewej stronie zaznacz **Produkty**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="b43ef-120">Wybierz produkt, który nie ma wzbogaconej strony produktu.</span><span class="sxs-lookup"><span data-stu-id="b43ef-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="b43ef-121">W okienku akcji wybierz pozycję **Wzbogać stronę produktu**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="b43ef-122">Zaznacz element **Szablon PDP** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="b43ef-123">W konspekcie strony z lewej strony rozwiń gniazdo **Główne**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="b43ef-124">Wybierz przycisk wielokropka (**...**) dla gniazda **Główne**, a następnie wybierz opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="b43ef-125">Zaznacz element **Kontener 2** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="b43ef-126">Wybierz przycisk wielokropka dla **Kontenera 2**, a następnie wybierz opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="b43ef-127">Zaznacz element **Funkcja** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="b43ef-128">W okienku właściwości z prawej strony w polu **tekst sformatowany** wprowadź zaktualizowany opis produktu.</span><span class="sxs-lookup"><span data-stu-id="b43ef-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="b43ef-129">W polu **Nagłówek** wprowadź tekst nagłówka, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="b43ef-130">Wybierz **Zapisz** i następnie wybierz **Zaewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-130">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="b43ef-131">W polu **Komentarze** wprowadź **Wzbogacono produkt**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="b43ef-132">Wybierz opcję **Podgląd**, aby wyświetlić podgląd wzbogaconej strony produktu.</span><span class="sxs-lookup"><span data-stu-id="b43ef-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="b43ef-133">Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.</span><span class="sxs-lookup"><span data-stu-id="b43ef-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="b43ef-134">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="b43ef-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b43ef-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b43ef-135">Additional resources</span></span>

[<span data-ttu-id="b43ef-136">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="b43ef-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="b43ef-137">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="b43ef-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="b43ef-138">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="b43ef-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="b43ef-139">Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="b43ef-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="b43ef-140">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="b43ef-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="b43ef-141">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="b43ef-141">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="b43ef-142">Weryfikowanie dostępności zawartości strony</span><span class="sxs-lookup"><span data-stu-id="b43ef-142">Verify page content accessibility</span></span>](verify-accessibility.md)
