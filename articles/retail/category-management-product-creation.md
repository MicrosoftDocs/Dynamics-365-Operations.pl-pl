---
title: "Zarządzanie kategoriami produktów i produktami sieci sprzedaży"
description: "W tym temacie opisano, jak kierownicy ds. merchadisingu mogą używać kategorii produktów sieci sprzedaży do zarządzania relacjami między hierarchiami produktów sieci sprzedaży a szczegółami zwolnionych produktów."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 19c972164474c972aab642c3cccc67cf396a6cb2
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="manage-retail-product-categories-and-products"></a><span data-ttu-id="106f1-103">Zarządzanie kategoriami produktów i produktami sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="106f1-103">Manage Retail product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="106f1-104">W tym temacie opisano poszerzony sposób zarządzania kategoriami produktów sieci sprzedaży i produktami w programie Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="106f1-104">This topic describes an enhanced way to manage Retail product categories and products in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="106f1-105">Ulepszenia umożliwiają menedżerom ds. merchadisingu wyświetlanie struktury właściwości produktów, która jest wspólna dla hierarchii produktów sieci sprzedaży i informacji o zwolnionych produktach.</span><span class="sxs-lookup"><span data-stu-id="106f1-105">The enhancements let merchandising managers view a structure of product properties that is shared between the Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="106f1-106">Aby dowiedzieć się więcej o zarządzaniu kategoriami produktów sieci sprzedaży, w obszarze roboczym **Zarządzanie kategoriami i produktami** wybierz kafelek **Hierarchia produktów sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="106f1-106">To learn more about how to manage Retail product categories, in the **Category and product management** workspace, select the **Retail product hierarchy** tile.</span></span>

<span data-ttu-id="106f1-107">Zwróć uwagę na ulepszoną strukturę na stronie **Hierarchia produktów sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="106f1-107">Notice the enhanced structure of the **Retail product hierarchy** page that appears.</span></span> <span data-ttu-id="106f1-108">W poprzednich wersjach aplikacji Retail właściwości produktów były podzielone na *podstawowe właściwości produktów* i *właściwości produktów sieci sprzedaży* na podstawie zakresu ich zastosowania.</span><span class="sxs-lookup"><span data-stu-id="106f1-108">In previous versions of Retail, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="106f1-109">Właściwości produktów sieci sprzedaży są *globalne* pod względem zakresu ich zastosowania.</span><span class="sxs-lookup"><span data-stu-id="106f1-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="106f1-110">Inaczej mówiąc, dla danej właściwości produktu sieci sprzedaży ta sama wartość jest współdzielona we wszystkich firmach.</span><span class="sxs-lookup"><span data-stu-id="106f1-110">In other words, for a given Retail product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="106f1-111">Z kolei podstawowe właściwości produktów są *specyficzne dla firmy*.</span><span class="sxs-lookup"><span data-stu-id="106f1-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="106f1-112">Inaczej mówiąc, dana podstawowa właściwość produktu może mieć różne wartości dla różnych firm, w zależności od wymagań biznesowych konkretnej firmy.</span><span class="sxs-lookup"><span data-stu-id="106f1-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="106f1-113">W ulepszonej strukturze kategorii produktów sieci sprzedaży właściwości produktów są logicznie rozdzielone na podstawie ich zastosowania w grupie, tak aby odzwierciedlić strukturę formularza szczegółów zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="106f1-113">In the enhanced Retail product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Pola pogrupowane w oparciu o zakres stosowania właściwości](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="106f1-115">Można przełączyć się między zarządzaniem właściwościami specyficznymi dla firmy we wszystkich firmach a zarządzaniem nimi dla określonej firmy.</span><span class="sxs-lookup"><span data-stu-id="106f1-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="106f1-116">Aby zarządzać właściwościami we wszystkich firmach, wybierz opcję **Wyświetl dla wszystkich firm** (lub **Edytuj dla wszystkich firm**).</span><span class="sxs-lookup"><span data-stu-id="106f1-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Wyświetl/edytuj dla wszystkich firm](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="106f1-118">Aby zarządzać właściwościami określonej firmy, wybierz opcję **Wyświetl dla określonej firmy** (lub **Edytuj dla określonej firmy**).</span><span class="sxs-lookup"><span data-stu-id="106f1-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Wyświetl/edytuj dla określonej firmy](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="106f1-120">Ponadto w ulepszonej strukturze kategorii produktów sieci sprzedaży kierownik ds. merchadisingu może zdefiniować domyślne wartości dodatkowego zestawu właściwości produktów na poziomie indywidualnej kategorii.</span><span class="sxs-lookup"><span data-stu-id="106f1-120">Additionally, in the enhanced Retail product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="106f1-121">Wtedy podczas tworzenia produktów będą one dziedziczyły domyślne wartości w oparciu o ich powiązanie z konkretną kategorią w hierarchii produktów sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="106f1-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in Retail product hierarchy.</span></span> <span data-ttu-id="106f1-122">Te dziedziczone właściwości produktów można również modyfikować dla każdego produktu, aby spełnić indywidualne wymagania biznesowe.</span><span class="sxs-lookup"><span data-stu-id="106f1-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a><span data-ttu-id="106f1-123">Wybieranie właściwości w celu aktualizowania produktów na stronie hierarchii produktów sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="106f1-123">Selecting properties to update products on the Retail product hierarchy page</span></span>

<span data-ttu-id="106f1-124">Nowej ulepszonej struktury można używać dla właściwości produktów w celu określania, które zaktualizowane właściwości produktów mają być rozpowszechniane do powiązanych produktów.</span><span class="sxs-lookup"><span data-stu-id="106f1-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="106f1-125">Na stronie **Hierarchia produktów sieci sprzedaży** w okienku akcji wybierz opcję **Kategoria**, a następnie wybierz opcję **Aktualizuj produkty**, aby otworzyć okno dialogowe **Aktualizuj produkty**.</span><span class="sxs-lookup"><span data-stu-id="106f1-125">On the **Retail product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Okno dialogowe Aktualizuj produkty](media/NewUpdateProductsEnhancedView.PNG)


