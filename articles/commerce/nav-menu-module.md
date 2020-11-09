---
title: Moduł Menu nawigacji
description: W tym temacie opisano moduły menu nawigacji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055744"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="b0fda-103">Moduł Menu nawigacji</span><span class="sxs-lookup"><span data-stu-id="b0fda-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b0fda-104">W tym temacie opisano moduły menu nawigacji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b0fda-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b0fda-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="b0fda-105">Overview</span></span>

<span data-ttu-id="b0fda-106">Głównym celem modułów menu nawigacji jest umożliwienie użytkownikom witryny przeglądania produktów i stron witryny zgodnie z hierarchią nawigacji kanału zdefiniowaną w centrali Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b0fda-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="b0fda-107">Elementy skonfigurowane w module menu nawigacji są wyświetlane jako nawigacja nagłówka oddziału.</span><span class="sxs-lookup"><span data-stu-id="b0fda-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="b0fda-108">Moduły menu nawigacji obsługują także statyczne elementy menu, które łączą się z innymi stronami w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="b0fda-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="b0fda-109">Moduł menu nawigacji można dodać do modułu nagłówka strony.</span><span class="sxs-lookup"><span data-stu-id="b0fda-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="b0fda-110">W motywie Fabrikam w menu nawigacji domyślnie są wyświetlane dwa poziomy.</span><span class="sxs-lookup"><span data-stu-id="b0fda-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="b0fda-111">W motywie Starter w menu nawigacji domyślnie są wyświetlane trzy poziomy.</span><span class="sxs-lookup"><span data-stu-id="b0fda-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="b0fda-112">Aby zmienić liczbę poziomów, na motywie jest wymagane rozszerzenie widoku.</span><span class="sxs-lookup"><span data-stu-id="b0fda-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="b0fda-113">Na poniższej ilustracji pokazano przykład menu nawigacji dla witryny Fabrikam z dwoma poziomami hierarchii kategorii i pewnymi statycznymi elementami menu.</span><span class="sxs-lookup"><span data-stu-id="b0fda-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="b0fda-114">![Przykład modułu menu nawigacji](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="b0fda-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="b0fda-115">Moduł Menu nawigacji — właściwości</span><span class="sxs-lookup"><span data-stu-id="b0fda-115">Navigation menu module properties</span></span>

| <span data-ttu-id="b0fda-116">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="b0fda-116">Property name</span></span>             | <span data-ttu-id="b0fda-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="b0fda-117">Value</span></span>                 | <span data-ttu-id="b0fda-118">opis</span><span class="sxs-lookup"><span data-stu-id="b0fda-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="b0fda-119">Źródło</span><span class="sxs-lookup"><span data-stu-id="b0fda-119">Source</span></span>                  | <span data-ttu-id="b0fda-120">**Handel detaliczny** , **Ręczne tworzenie** , **Tworzenie detaliczne i ręczne**</span><span class="sxs-lookup"><span data-stu-id="b0fda-120">**Retail** , **Manual authoring** , **Retail and manual authoring**</span></span> | <span data-ttu-id="b0fda-121">Wartość **Detaliczna** umożliwia wyświetlanie hierarchii nawigacji kanału w menu nawigacji z poziomu modułu Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="b0fda-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="b0fda-122">**Tworzenie ręczne** umożliwia analizę statycznych elementów menu.</span><span class="sxs-lookup"><span data-stu-id="b0fda-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="b0fda-123">Ustawienie wartości **Tworzenie ręczne i detaliczne** umożliwia stosowanie kombinacji obu typów.</span><span class="sxs-lookup"><span data-stu-id="b0fda-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="b0fda-124">Wyświetlanie obrazów kategorii</span><span class="sxs-lookup"><span data-stu-id="b0fda-124">Show category images</span></span> | <span data-ttu-id="b0fda-125">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="b0fda-125">**True** or **False**</span></span>    | <span data-ttu-id="b0fda-126">Po włączeniu tej właściwości w menu nawigacji są wyświetlane obrazy kategorii zdefiniowane w module Commerce Headquarter dla każdej kategorii.</span><span class="sxs-lookup"><span data-stu-id="b0fda-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="b0fda-127">Dodane do modułu Commerce Release 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="b0fda-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="b0fda-128">Włącz wielopoziomowe menu nawigacji</span><span class="sxs-lookup"><span data-stu-id="b0fda-128">Enable multi-level navigation menu</span></span> | <span data-ttu-id="b0fda-129">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="b0fda-129">**True** or **False**</span></span> | <span data-ttu-id="b0fda-130">Po włączeniu tej właściwości menu nawigacji może zawierać wiele poziomów hierarchii nawigacji.</span><span class="sxs-lookup"><span data-stu-id="b0fda-130">When this property is enabled, the navigation menu can show multiple levels of the navigation hierarchy.</span></span> <span data-ttu-id="b0fda-131">Ta funkcja nie jest dostępna tylko w Dynamics 365 Commerce w wersji 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="b0fda-131">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="b0fda-132">Liczba poziomów</span><span class="sxs-lookup"><span data-stu-id="b0fda-132">Number of levels</span></span> | <span data-ttu-id="b0fda-133">liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="b0fda-133">integer</span></span> | <span data-ttu-id="b0fda-134">Właściwość ta definiuje liczby poziomów, które powinny być pokazywane, jeśli dla właściwości **Włącz wielopoziomowe menu nawigacji** jest ustawiona wartość **Prawda**.</span><span class="sxs-lookup"><span data-stu-id="b0fda-134">This property defines the numbers of levels that should be shown if the **Enable multilevel navigation menu** property is set to **True**.</span></span> |
| <span data-ttu-id="b0fda-135">Statyczny element menu</span><span class="sxs-lookup"><span data-stu-id="b0fda-135">Static menu item</span></span>| <span data-ttu-id="b0fda-136">Tablica wartości</span><span class="sxs-lookup"><span data-stu-id="b0fda-136">Array of values</span></span>| <span data-ttu-id="b0fda-137">Statyczne elementy menu, które kojarzą nazwę elementu menu z łączem do statycznej strony witryny.</span><span class="sxs-lookup"><span data-stu-id="b0fda-137">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="b0fda-138">Można utworzyć elementy menu poniżej innych elementów menu.</span><span class="sxs-lookup"><span data-stu-id="b0fda-138">You can create menu items below other menu items.</span></span> <span data-ttu-id="b0fda-139">Domyślnie menu statyczne pojawia się na poziomie głównym i zostanie dołączone do hierarchii nawigacji kanału, jeśli taka istnieje.</span><span class="sxs-lookup"><span data-stu-id="b0fda-139">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |
| <span data-ttu-id="b0fda-140">Pokazywanie menu głównego</span><span class="sxs-lookup"><span data-stu-id="b0fda-140">Show root menu</span></span> | <span data-ttu-id="b0fda-141">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="b0fda-141">**True** or **False**</span></span> | <span data-ttu-id="b0fda-142">Gdy ta właściwość jest włączona, menu nawigacji można zdefiniować za pomocą niestandardowego katalogu głównego (na przykład **Kup teraz** ).</span><span class="sxs-lookup"><span data-stu-id="b0fda-142">When this property is enabled, the navigation menu can be defined under a custom root (for example, **Shop now** ).</span></span> <span data-ttu-id="b0fda-143">Ta funkcja nie jest dostępna tylko w Dynamics 365 Commerce w wersji 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="b0fda-143">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="b0fda-144">Menu główne</span><span class="sxs-lookup"><span data-stu-id="b0fda-144">Root menu</span></span> | <span data-ttu-id="b0fda-145">ciąg</span><span class="sxs-lookup"><span data-stu-id="b0fda-145">string</span></span> | <span data-ttu-id="b0fda-146">Ta właściwość może służyć do definiowania tekstu dla niestandardowego katalogu głównego, jeśli właściwość **Pokazywanie menu głównego** ma wartość **Prawda**.</span><span class="sxs-lookup"><span data-stu-id="b0fda-146">This property can be used to define text for a custom root if the **Show root menu** property is set to **True**.</span></span> |

<span data-ttu-id="b0fda-147">Na poniższej ilustracji pokazano przykład obrazu kategorii wyświetlanego w menu nawigacji witryny Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="b0fda-147">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="b0fda-148">![Przykład modułu menu nawigacji z obrazami kategorii](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="b0fda-148">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="b0fda-149">Dodawanie modułu menu nawigacji do modułu nagłówka</span><span class="sxs-lookup"><span data-stu-id="b0fda-149">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="b0fda-150">Aby uzyskać szczegółowe informacje na temat dodawania modułu menu nawigacji do modułu nagłówka, skorzystaj z [modułu nagłówka](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="b0fda-150">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b0fda-151">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b0fda-151">Additional resources</span></span>

[<span data-ttu-id="b0fda-152">Przegląd biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="b0fda-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b0fda-153">Moduł szlaków nawigacyjnych</span><span class="sxs-lookup"><span data-stu-id="b0fda-153">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="b0fda-154">Moduł wyboru witryny</span><span class="sxs-lookup"><span data-stu-id="b0fda-154">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="b0fda-155">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="b0fda-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="b0fda-156">Zgodność z plikami cookie</span><span class="sxs-lookup"><span data-stu-id="b0fda-156">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="b0fda-157">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="b0fda-157">Header module</span></span>](author-header-module.md)
