---
title: Moduł Menu nawigacji
description: W tym temacie opisano moduły menu nawigacji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: 91239bd1db3f5819b7ad8d45ccfd8ab0d88b1b41
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817881"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="1a2a0-103">Moduł Menu nawigacji</span><span class="sxs-lookup"><span data-stu-id="1a2a0-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="1a2a0-104">W tym temacie opisano moduły menu nawigacji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1a2a0-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="1a2a0-105">Overview</span></span>

<span data-ttu-id="1a2a0-106">Głównym celem modułów menu nawigacji jest umożliwienie użytkownikom witryny przeglądania produktów i stron witryny zgodnie z hierarchią nawigacji kanału zdefiniowaną w centrali Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="1a2a0-107">Elementy skonfigurowane w module menu nawigacji są wyświetlane jako nawigacja nagłówka oddziału.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="1a2a0-108">Moduły menu nawigacji obsługują także statyczne elementy menu, które łączą się z innymi stronami w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="1a2a0-109">Moduł menu nawigacji można dodać do modułu nagłówka strony.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="1a2a0-110">W motywie Fabrikam w menu nawigacji domyślnie są wyświetlane dwa poziomy.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="1a2a0-111">W motywie Starter w menu nawigacji domyślnie są wyświetlane trzy poziomy.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="1a2a0-112">Aby zmienić liczbę poziomów, na motywie jest wymagane rozszerzenie widoku.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="1a2a0-113">Na poniższej ilustracji pokazano przykład menu nawigacji dla witryny Fabrikam z dwoma poziomami hierarchii kategorii i pewnymi statycznymi elementami menu.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="1a2a0-114">![Przykład modułu menu nawigacji](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="1a2a0-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="1a2a0-115">Moduł Menu nawigacji — właściwości</span><span class="sxs-lookup"><span data-stu-id="1a2a0-115">Navigation menu module properties</span></span>

| <span data-ttu-id="1a2a0-116">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="1a2a0-116">Property name</span></span>             | <span data-ttu-id="1a2a0-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="1a2a0-117">Value</span></span>                 | <span data-ttu-id="1a2a0-118">opis</span><span class="sxs-lookup"><span data-stu-id="1a2a0-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="1a2a0-119">Źródło</span><span class="sxs-lookup"><span data-stu-id="1a2a0-119">Source</span></span>                  | <span data-ttu-id="1a2a0-120">**Handel detaliczny**, **Ręczne tworzenie**, **Tworzenie detaliczne i ręczne**</span><span class="sxs-lookup"><span data-stu-id="1a2a0-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="1a2a0-121">Wartość **Detaliczna** umożliwia wyświetlanie hierarchii nawigacji kanału w menu nawigacji z poziomu modułu Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="1a2a0-122">**Tworzenie ręczne** umożliwia analizę statycznych elementów menu.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="1a2a0-123">Ustawienie wartości **Tworzenie ręczne i detaliczne** umożliwia stosowanie kombinacji obu typów.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="1a2a0-124">Wyświetlanie obrazów kategorii</span><span class="sxs-lookup"><span data-stu-id="1a2a0-124">Show category images</span></span> | <span data-ttu-id="1a2a0-125">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="1a2a0-125">**True** or **False**</span></span>    | <span data-ttu-id="1a2a0-126">Po włączeniu tej właściwości w menu nawigacji są wyświetlane obrazy kategorii zdefiniowane w module Commerce Headquarter dla każdej kategorii.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="1a2a0-127">Dodane do modułu Commerce Release 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="1a2a0-128">Statyczny element menu</span><span class="sxs-lookup"><span data-stu-id="1a2a0-128">Static menu item</span></span>| <span data-ttu-id="1a2a0-129">Tablica wartości</span><span class="sxs-lookup"><span data-stu-id="1a2a0-129">Array of values</span></span>| <span data-ttu-id="1a2a0-130">Statyczne elementy menu, które kojarzą nazwę elementu menu z łączem do statycznej strony witryny.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-130">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="1a2a0-131">Można utworzyć elementy menu poniżej innych elementów menu.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-131">You can create menu items below other menu items.</span></span> <span data-ttu-id="1a2a0-132">Domyślnie menu statyczne pojawia się na poziomie głównym i zostanie dołączone do hierarchii nawigacji kanału, jeśli taka istnieje.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-132">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |

<span data-ttu-id="1a2a0-133">Na poniższej ilustracji pokazano przykład obrazu kategorii wyświetlanego w menu nawigacji witryny Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="1a2a0-133">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="1a2a0-134">![Przykład modułu menu nawigacji z obrazami kategorii](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="1a2a0-134">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="1a2a0-135">Dodawanie modułu menu nawigacji do modułu nagłówka</span><span class="sxs-lookup"><span data-stu-id="1a2a0-135">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="1a2a0-136">Aby uzyskać szczegółowe informacje na temat dodawania modułu menu nawigacji do modułu nagłówka, skorzystaj z [modułu nagłówka](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="1a2a0-136">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a2a0-137">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1a2a0-137">Additional resources</span></span>

[<span data-ttu-id="1a2a0-138">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="1a2a0-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1a2a0-139">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="1a2a0-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="1a2a0-140">Zgodność z plikami cookie</span><span class="sxs-lookup"><span data-stu-id="1a2a0-140">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="1a2a0-141">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="1a2a0-141">Header module</span></span>](author-header-module.md)
