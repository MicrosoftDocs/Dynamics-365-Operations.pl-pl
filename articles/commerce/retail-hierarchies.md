---
title: Hierarchie Commerce
description: Ten artykuł opisuje hierarchie w programie Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager, EcoResCategoryHierarchyFactbox
audience: Application User
ms.reviewer: josaw
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 94b391ab5028f76debb75d25ac9469e25361cb12
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979623"
---
# <a name="commerce-hierarchies"></a><span data-ttu-id="745ce-103">Hierarchie Commerce</span><span class="sxs-lookup"><span data-stu-id="745ce-103">Commerce hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="745ce-104">Ten artykuł opisuje hierarchie w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="745ce-104">This article describes hierarchies in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="745ce-105">Można skonfigurować hierarchię kategorii w celu zorganizowania produktów sprzedawanych w Twoim kanale.</span><span class="sxs-lookup"><span data-stu-id="745ce-105">You can create a category hierarchy to organize the products that you sell through your channels.</span></span> <span data-ttu-id="745ce-106">Hierarchie produktów umożliwiają łączenie produktów w kategorie i grupy.</span><span class="sxs-lookup"><span data-stu-id="745ce-106">You can use product hierarchies to categorize or group products.</span></span> <span data-ttu-id="745ce-107">Następnie można używać tych produktów do tworzenia asortymentów produktów i programów lojalnościowych.</span><span class="sxs-lookup"><span data-stu-id="745ce-107">You can then use these products to create product assortments and customer loyalty programs.</span></span> <span data-ttu-id="745ce-108">Można również przypisywać właściwości i atrybuty produktu, strukturę cen, dodawać produkty w do produktów i używać produktów na potrzeby raportowania.</span><span class="sxs-lookup"><span data-stu-id="745ce-108">You can also assign product attributes and properties, assign a pricing structure, include the products in product promotions, and use the products for reporting.</span></span> <span data-ttu-id="745ce-109">Można utworzyć jedną hierarchię kategorii do reprezentowania wszystkich produktów i kategorii w organizacji, a następnie użyć tej hierarchii kategorii do wielu celów.</span><span class="sxs-lookup"><span data-stu-id="745ce-109">You can create one category hierarchy to represent all the products and categories in your organization, and then use that category hierarchy for multiple purposes.</span></span> <span data-ttu-id="745ce-110">Alternatywnie można utworzyć wiele hierarchii kategorii do celów specjalnych, takich jak promocja produktów.</span><span class="sxs-lookup"><span data-stu-id="745ce-110">Alternatively, you can create multiple category hierarchies for special purposes, such as product promotions.</span></span> <span data-ttu-id="745ce-111">Podczas tworzenia hierarchii produktów należy przypisać typ hierarchii kategorii w celu identyfikacji przeznaczenia hierarchii kategorii.</span><span class="sxs-lookup"><span data-stu-id="745ce-111">When you create a product hierarchy, you must assign a category hierarchy type to identify the purpose of the category hierarchy.</span></span> <span data-ttu-id="745ce-112">Na przykład tylko hierarchie produktów, które mają przypisany typ **Hierarchia nawigacji w handlu**, są wskazywane podczas przeglądania produktów według kategorii online lub w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="745ce-112">For example, only product hierarchies that are assigned the **Commerce navigation hierarchy** type are referenced when you browse products by category online or in point of sale (POS).</span></span>

## <a name="hierarchy-types"></a><span data-ttu-id="745ce-113">Typy hierarchii</span><span class="sxs-lookup"><span data-stu-id="745ce-113">Hierarchy types</span></span>

<span data-ttu-id="745ce-114">Poniższa tabela pokazuje dostępne hierarchie typów kategorii oraz ich ogólne zastosowania.</span><span class="sxs-lookup"><span data-stu-id="745ce-114">The following table lists the types of category hierarchies that are available and the general purpose of each type.</span></span>

| <span data-ttu-id="745ce-115">Typ hierarchii kategorii</span><span class="sxs-lookup"><span data-stu-id="745ce-115">Category hierarchy type</span></span>       | <span data-ttu-id="745ce-116">Cel</span><span class="sxs-lookup"><span data-stu-id="745ce-116">Purpose</span></span> |
|-------------------------------|---------|
| <span data-ttu-id="745ce-117">Hierarchia produktów</span><span class="sxs-lookup"><span data-stu-id="745ce-117">Product hierarchy</span></span>      | <span data-ttu-id="745ce-118">Ten typ kategorii pozwala zdefiniować ogólną hierarchę produktów dla Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="745ce-118">Use this hierarchy type to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="745ce-119">Ten typ hierarchii sprawdza się w merchandisingu, wycenach i promocjach, raportowaniu i planowaniu asortymentu.</span><span class="sxs-lookup"><span data-stu-id="745ce-119">You can use this hierarchy type for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="745ce-120">Z tym typem hierarchii można skojarzyć tylko jedną hierarchię produktu.</span><span class="sxs-lookup"><span data-stu-id="745ce-120">Only one product hierarchy can be assigned this hierarchy type.</span></span> |
| <span data-ttu-id="745ce-121">Uzupełniająca hierarchia</span><span class="sxs-lookup"><span data-stu-id="745ce-121">Supplemental hierarchy</span></span> | <span data-ttu-id="745ce-122">Ten typ hierarchii pozwala tworzyć wszelkie dodatkowe hierarchie kategorii.</span><span class="sxs-lookup"><span data-stu-id="745ce-122">Use this hierarchy type for any additional category hierarchies that you want to create.</span></span> <span data-ttu-id="745ce-123">Załóżmy na przykład, że na wiosnę chcesz promować stroje kąpielowe.</span><span class="sxs-lookup"><span data-stu-id="745ce-123">For example, in the spring, you have a promotion for swimwear.</span></span> <span data-ttu-id="745ce-124">W związku z tym umieszczasz produkty związane ze strojem kąpielowym w hierarchii kategorii i stosujesz cennik promocyjny w różnych kategoriach produktów.</span><span class="sxs-lookup"><span data-stu-id="745ce-124">Therefore, you include your swimwear products in a separate category hierarchy and apply the promotional pricing to the various product categories.</span></span> |
| <span data-ttu-id="745ce-125">Hierarchia nawigacji</span><span class="sxs-lookup"><span data-stu-id="745ce-125">Navigation hierarchy</span></span>   | <span data-ttu-id="745ce-126">Za pomocą tego typu hierarchii można grupować i organizować produkty według kategorii, tak aby dało się przeglądać produkty online lub w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="745ce-126">Use this hierarchy type to group and organize products into categories so that the products can be browsed online or in POS.</span></span> |

<span data-ttu-id="745ce-127">Za pomocą hierarchii kategorii można porządkować produkty, skonfigurować ich atrybuty oraz właściwości na poziomie kategorii.</span><span class="sxs-lookup"><span data-stu-id="745ce-127">By using a category hierarchy to structure your products, you can set up and maintain product attributes and properties at the category level.</span></span> <span data-ttu-id="745ce-128">Te atrybuty i właściwości obejmują ustawienia dla wymiarów produktu i ustawienia punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="745ce-128">These attributes and properties include settings for product dimensions and POS settings.</span></span> <span data-ttu-id="745ce-129">Wszystkie produkty, które zostaną przypisane do kategorii, automatycznie dziedziczą atrybuty i właściwości zdefiniowane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="745ce-129">Any products that you assign to the categories automatically inherit the attributes and properties that you define.</span></span> <span data-ttu-id="745ce-130">Można także jednocześnie skopiować ustawienia właściwości w odniesieniu do produktu do wielu produktów z wybranej kategorii.</span><span class="sxs-lookup"><span data-stu-id="745ce-130">You can also copy the property settings for any product to multiple products in a selected category at the same time.</span></span>
