---
title: Zarządzanie kategoriami produktów i produktami
description: W tym temacie opisano, jak kierownicy ds. merchadisingu mogą używać kategorii produktów do zarządzania relacjami między hierarchiami produktów Commerce a szczegółami zwolnionych produktów.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResProductCategory, EcoResCategoryAddProduct, EcoResAttributeValue
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9d47a866703b830e84e3f2e37a02d9d58f73987b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414908"
---
# <a name="manage-product-categories-and-products"></a><span data-ttu-id="9869b-103">Zarządzanie kategoriami produktów i produktami</span><span class="sxs-lookup"><span data-stu-id="9869b-103">Manage product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="9869b-104">W tym temacie opisano poszerzony sposób zarządzania kategoriami produktów sieci sprzedaży i produktami w usłudze Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9869b-104">This topic describes an enhanced way to manage product categories and products in Dynamics 365 Commerce.</span></span> <span data-ttu-id="9869b-105">Ulepszenia umożliwiają menedżerom ds. merchadisingu wyświetlanie struktury właściwości produktów, która jest wspólna dla hierarchii produktów i informacji o zwolnionych produktach.</span><span class="sxs-lookup"><span data-stu-id="9869b-105">The enhancements let merchandising managers view a structure of product properties that is shared between the product hierarchy and released product details.</span></span>

<span data-ttu-id="9869b-106">Aby dowiedzieć się więcej o zarządzaniu kategoriami produktów, w obszarze roboczym **Zarządzanie kategoriami i produktami** wybierz kafelek **Hierarchia produktów Commerce**.</span><span class="sxs-lookup"><span data-stu-id="9869b-106">To learn more about how to manage product categories, in the **Category and product management** workspace, select the **Commerce product hierarchy** tile.</span></span>

<span data-ttu-id="9869b-107">Zwróć uwagę na ulepszoną strukturę na stronie **Hierarchia produktów Commerce**.</span><span class="sxs-lookup"><span data-stu-id="9869b-107">Notice the enhanced structure of the **Commerce product hierarchy** page that appears.</span></span> <span data-ttu-id="9869b-108">W poprzednich wersjach aplikacji właściwości produktów były podzielone na *podstawowe właściwości produktów* i *właściwości produktów sieci sprzedaży* na podstawie zakresu ich zastosowania.</span><span class="sxs-lookup"><span data-stu-id="9869b-108">In previous versions of the app, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="9869b-109">Właściwości produktów sieci sprzedaży są *globalne* pod względem zakresu ich zastosowania.</span><span class="sxs-lookup"><span data-stu-id="9869b-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="9869b-110">Inaczej mówiąc, dla właściwości danego produktu ta sama wartość jest współdzielona we wszystkich firmach.</span><span class="sxs-lookup"><span data-stu-id="9869b-110">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="9869b-111">Z kolei podstawowe właściwości produktów są *specyficzne dla firmy*.</span><span class="sxs-lookup"><span data-stu-id="9869b-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="9869b-112">Inaczej mówiąc, dana podstawowa właściwość produktu może mieć różne wartości dla różnych firm, w zależności od wymagań biznesowych konkretnej firmy.</span><span class="sxs-lookup"><span data-stu-id="9869b-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="9869b-113">W ulepszonej strukturze kategorii produktów właściwości produktów są logicznie rozdzielone na podstawie ich zastosowania w grupie, tak aby odzwierciedlić strukturę formularza szczegółów zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="9869b-113">In the enhanced product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Pola pogrupowane w oparciu o zakres stosowania właściwości](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="9869b-115">Można przełączyć się między zarządzaniem właściwościami specyficznymi dla firmy we wszystkich firmach a zarządzaniem nimi dla określonej firmy.</span><span class="sxs-lookup"><span data-stu-id="9869b-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="9869b-116">Aby zarządzać właściwościami we wszystkich firmach, wybierz opcję **Wyświetl dla wszystkich firm** (lub **Edytuj dla wszystkich firm**).</span><span class="sxs-lookup"><span data-stu-id="9869b-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Wyświetl/edytuj dla wszystkich firm](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="9869b-118">Aby zarządzać właściwościami określonej firmy, wybierz opcję **Wyświetl dla określonej firmy** (lub **Edytuj dla określonej firmy**).</span><span class="sxs-lookup"><span data-stu-id="9869b-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Wyświetl/edytuj dla określonej firmy](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="9869b-120">Ponadto w ulepszonej strukturze kategorii produktów kierownik ds. merchadisingu może zdefiniować domyślne wartości dodatkowego zestawu właściwości produktów na poziomie indywidualnej kategorii.</span><span class="sxs-lookup"><span data-stu-id="9869b-120">Additionally, in the enhanced product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="9869b-121">Wtedy podczas tworzenia produktów będą one dziedziczyły domyślne wartości w oparciu o ich powiązanie z konkretną kategorią w hierarchii produktów.</span><span class="sxs-lookup"><span data-stu-id="9869b-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in the product hierarchy.</span></span> <span data-ttu-id="9869b-122">Te dziedziczone właściwości produktów można również modyfikować dla każdego produktu, aby spełnić indywidualne wymagania biznesowe.</span><span class="sxs-lookup"><span data-stu-id="9869b-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a><span data-ttu-id="9869b-123">Wybieranie właściwości w celu aktualizowania produktów na stronie hierarchii produktów Commerce</span><span class="sxs-lookup"><span data-stu-id="9869b-123">Selecting properties to update products on the Commerce product hierarchy page</span></span>

<span data-ttu-id="9869b-124">Nowej ulepszonej struktury można używać dla właściwości produktów w celu określania, które zaktualizowane właściwości produktów mają być rozpowszechniane do powiązanych produktów.</span><span class="sxs-lookup"><span data-stu-id="9869b-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="9869b-125">Na stronie **Hierarchia produktów Commerce** w okienku akcji wybierz opcję **Kategoria**, a następnie wybierz opcję **Aktualizuj produkty**, aby otworzyć okno dialogowe **Aktualizuj produkty**.</span><span class="sxs-lookup"><span data-stu-id="9869b-125">On the **Commerce product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Okno dialogowe Aktualizuj produkty](media/NewUpdateProductsEnhancedView.PNG)
