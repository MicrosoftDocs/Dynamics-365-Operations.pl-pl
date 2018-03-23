---
title: "Zarządzanie kategoriami produktów"
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
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: pl-pl
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a><span data-ttu-id="79827-103">Ulepszone zarządzanie kategoriami i produktami</span><span class="sxs-lookup"><span data-stu-id="79827-103">Enhanced product and category management</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="79827-104">W tym temacie opisano poszerzony sposób zarządzania kategoriami produktów sieci sprzedaży i produktami w programie Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="79827-104">This topic describes an enhanced way to manage Retail product categories and products in Dynamics 365 for Retail.</span></span> <span data-ttu-id="79827-105">Te ulepszenia umożliwiają menedżerom ds. merchadisingu wyświetlanie wspólnej struktury właściwości produktów między hierarchiami produktów detalicznych a informacjami o zwolnionych produktach.</span><span class="sxs-lookup"><span data-stu-id="79827-105">These enhancements let merchandising managers view a common structure of product properties between Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="79827-106">Aby dowiedzieć się więcej o zarządzaniu kategoriami produktów sieci sprzedaży, w obszarze roboczym **Zarządzanie kategoriami i produktami** przejdź do sekcji **Hierarchia produktów sieci sprzedaży** i zwróć uwagę na ulepszoną strukturę znajdującą się na stronie **Kategoria produktów sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="79827-106">To learn more about managing Retail product categories, go to **Retail product hierarchy** from the **Category and product management** workspace, and note the enhanced structure of the **Retail product category** page.</span></span>

![Obszar roboczy Zarządzanie kategoriami i produktami](media/LaunchRetailProductHierarchy.png)

<span data-ttu-id="79827-108">W poprzednich wersjach właściwości produktów były podzielone na **podstawowe właściwości produktów** i **właściwości produktów sieci sprzedaży** na podstawie zakresu ich zastosowania.</span><span class="sxs-lookup"><span data-stu-id="79827-108">In previous versions, product properties were divided into **Basic product properties** and **Retail product properties**, based on the scope of their applicability.</span></span> <span data-ttu-id="79827-109">**Właściwości produktów sieci sprzedaży** były *globalne* ze względu na zakres zastosowania, co oznacza, że dla danej **właściwości produktu sieci sprzedaży** ta sama wartość jest wspólna we wszystkich firmach.</span><span class="sxs-lookup"><span data-stu-id="79827-109">**Retail product properties** were *global* by scope of applicability, which means that for a given **Retail product property**, the same value is shared across all legal entities.</span></span> <span data-ttu-id="79827-110">**Podstawowe właściwości produktów** były *specyficzne dla firmy*.</span><span class="sxs-lookup"><span data-stu-id="79827-110">**Basic product properties** are *legal entity specific*.</span></span> <span data-ttu-id="79827-111">Inaczej mówiąc, dana **podstawowa właściwość produktu** może mieć różne wartości dla różnych firm w zależności od wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="79827-111">In other words, for a given **Basic product property** the value can differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="79827-112">W ulepszonej strukturze kategorii produktów sieci sprzedaży właściwości produktów są logicznie rozdzielone na podstawie ich zastosowania w grupie, tak aby odzwierciedlić strukturę formularza szczegółów zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="79827-112">In the enhanced Retail product category structure, product properties are logically separated based on their applicability within a group, to reflect the released product details form structure.</span></span>

![Grupowanie pól w oparciu o ich zakres stosowania](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="79827-114">Można przełączyć się między zarządzaniem właściwościami specyficznymi dla firmy we wszystkich firmach i zarządzaniem nimi dla określonej firmy.</span><span class="sxs-lookup"><span data-stu-id="79827-114">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="79827-115">W tym celu wybierz opcję **Wyświetl/edytuj dla wszystkich firm** lub **Wyświetl/edytuj dla określonej firmy**.</span><span class="sxs-lookup"><span data-stu-id="79827-115">To do this, select either **View/Edit for all legal entities** or **View/Edit for a specific legal entity**.</span></span>

![Przełączanie widoku między jedną a wszystkimi firmami](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Przełączanie widoku między jedną a wszystkimi firmami](media/ToggleToEditForAllLegalEntities.PNG)  

<span data-ttu-id="79827-118">W porównaniu z poprzednimi wersjami w nowej strukturze kategorii produktów sieci sprzedaży kierownik ds. merchadisingu może zdefiniować domyślne wartości dodatkowego zestawu właściwości produktów na poziomie indywidualnej kategorii.</span><span class="sxs-lookup"><span data-stu-id="79827-118">Compared to previous versions, in the new Retail product category structure a merchandising manager can also define default values for an additional set of product properties at an individual category level.</span></span> <span data-ttu-id="79827-119">Podczas tworzenia produktu te domyślne właściwości produktu są dziedziczone przez produkt w oparciu o jego powiązanie z konkretną kategorią w hierarchii produktów sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="79827-119">At the time of product creation, these default product property values are inherited by a product, based on their association with an individual category from Retail product hierarchy.</span></span> <span data-ttu-id="79827-120">Te dziedziczone właściwości produktów można również modyfikować dla każdego produktu, aby spełnić indywidualne wymagania biznesowe.</span><span class="sxs-lookup"><span data-stu-id="79827-120">These inherited product properties can also be modified for each product, to meet individual business requirements.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="79827-121">Wybieranie właściwości do aktualizacji produktu z formularza kategorii produktów sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="79827-121">Select properties to update products from the Retail product category form</span></span> 
 
<span data-ttu-id="79827-122">Tej nowej ulepszonej struktury można używać dla właściwości produktów w celu określania, które zaktualizowane właściwości produktów mają być rozpowszechniane do powiązanych produktów.</span><span class="sxs-lookup"><span data-stu-id="79827-122">You can use this new enhanced structure for product properties to select which updated product properties must be pushed to associated products.</span></span> 

![Nowy, ulepszony widok aktualizacji produktów](media/NewUpdateProductsEnhancedView.PNG) 

<span data-ttu-id="79827-124">Menedżerowie ds. merchandisingu mogą zmodyfikować odziedziczone właściwości produktów dla każdego produktu, aby spełnić indywidualne wymagania biznesowe.</span><span class="sxs-lookup"><span data-stu-id="79827-124">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>


