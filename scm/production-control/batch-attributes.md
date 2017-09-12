---
title: Atrybuty partii
description: "Ten artykuł zawiera informacje o atrybutach partii. Atrybuty partii to cechy surowców i produktów gotowych wchodzących w skład partii zapasów. W artykule wyjaśniono też, jak przypisywać atrybuty partii i jak szukać według nich podczas rezerwowania partii."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 0c3f5115377178941984e53749c18cc1c9179812
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="batch-attributes"></a><span data-ttu-id="d9189-105">Atrybuty partii</span><span class="sxs-lookup"><span data-stu-id="d9189-105">Batch attributes</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d9189-106">Ten artykuł zawiera informacje o atrybutach partii.</span><span class="sxs-lookup"><span data-stu-id="d9189-106">This article provides information about batch attributes.</span></span> <span data-ttu-id="d9189-107">Atrybuty partii to cechy surowców i produktów gotowych wchodzących w skład partii zapasów.</span><span class="sxs-lookup"><span data-stu-id="d9189-107">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="d9189-108">W artykule wyjaśniono też, jak przypisywać atrybuty partii i jak szukać według nich podczas rezerwowania partii.</span><span class="sxs-lookup"><span data-stu-id="d9189-108">The article also explains how to assign batch attributes, and how you can search on them when you reserve batches.</span></span>

<span data-ttu-id="d9189-109">Atrybuty partii to cechy surowców i produktów gotowych wchodzących w skład partii zapasów.</span><span class="sxs-lookup"><span data-stu-id="d9189-109">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="d9189-110">Atrybuty partii mogą się różnić w zależności od czynników, takich jak warunki środowiskowe, jakość surowców używanych w procesie produkcji danej partii czy wyniku gotowego produktu.</span><span class="sxs-lookup"><span data-stu-id="d9189-110">Batch attributes can vary, depending on factors such as environmental conditions, the quality of the raw materials that are used to produce the batch, or the outcome of the finished product.</span></span> <span data-ttu-id="d9189-111">Liczba i typ stosowanych atrybutów partii może się znacznie różnić między poszczególnymi sektorami gospodarki.</span><span class="sxs-lookup"><span data-stu-id="d9189-111">The number and types of batch attributes that are used can vary widely from one industry to another.</span></span> <span data-ttu-id="d9189-112">Poniżej przedstawiono dwa przykłady pokazujące sposób korzystania z atrybutów partii:</span><span class="sxs-lookup"><span data-stu-id="d9189-112">Here are two examples that show how to use batch attributes:</span></span>

-   <span data-ttu-id="d9189-113">W firmach produkujących ser mleko będące surowcem do produkcji serów może mieć przypisane atrybuty takie jak zawartość tłuszczu lub procent wagi.</span><span class="sxs-lookup"><span data-stu-id="d9189-113">In the cheese industry, milk, which is one of the raw materials that are used to produce the cheese, can have attributes such as fat content and percentage weight.</span></span> <span data-ttu-id="d9189-114">Ser produkowany z takiego mleka może mieć natomiast inne atrybuty (np. wilgotność lub wiek).</span><span class="sxs-lookup"><span data-stu-id="d9189-114">The cheese that is produced from the milk can have other attributes, such as moisture and age.</span></span>
-   <span data-ttu-id="d9189-115">W branży stalowej żelazo może mieć przypisane atrybuty takie jak procent zawartości magnezu, procent zawartości srebra lub procent zawartości cynku.</span><span class="sxs-lookup"><span data-stu-id="d9189-115">In the steel industry, the iron that is produced might have attributes such as the percentages of magnesium content, silver content, and zinc content.</span></span>

<span data-ttu-id="d9189-116">Aby lepiej zarządzać liczbą i typami atrybutów, można stosować grupy atrybutów partii.</span><span class="sxs-lookup"><span data-stu-id="d9189-116">To better manage the number and types of attributes, you can use batch attribute groups.</span></span> <span data-ttu-id="d9189-117">Dzięki temu nie trzeba dodawać atrybutów pojedynczo.</span><span class="sxs-lookup"><span data-stu-id="d9189-117">In this way, you don't have to add each attribute individually.</span></span>

## <a name="assign-batch-attributes"></a><span data-ttu-id="d9189-118">Przypisywanie atrybutów partii</span><span class="sxs-lookup"><span data-stu-id="d9189-118">Assign batch attributes</span></span>
<span data-ttu-id="d9189-119">Atrybuty partii można przypisać do poszczególnych produktów znajdujących się w partiach zapasów lub można przypisywać je do produktów skojarzonych z konkretnymi odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="d9189-119">You can assign batch attributes to individual products that are held in inventory batches, or you can assign them to products that are associated with specific customers.</span></span> <span data-ttu-id="d9189-120">Przed przypisaniem atrybutu partii na poziomie odbiorcy, należy najpierw przypisać go na poziomie produktu.</span><span class="sxs-lookup"><span data-stu-id="d9189-120">Before you can assign a batch attribute at the customer level, you must assign it at the product level.</span></span> <span data-ttu-id="d9189-121">Produkt musi być mieć wymiar partii **Aktywny** w grupie wymiarów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="d9189-121">The product must have the batch dimension set to **Active** in the tracking dimension group.</span></span> <span data-ttu-id="d9189-122">Aby przypisać atrybut partii do danego produktu, użyj strony określonego produktu.</span><span class="sxs-lookup"><span data-stu-id="d9189-122">To assign a batch attribute to an individual product, use the product-specific page.</span></span> <span data-ttu-id="d9189-123">Jeśli atrybut jest właściwe dla produktu dla danego odbiorcy, użyj strony określonego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d9189-123">If the attribute is specific to a product for a customer, use the customer-specific page.</span></span> <span data-ttu-id="d9189-124">Po dodaniu atrybutu do produktu, można również zdefiniować inne parametry.</span><span class="sxs-lookup"><span data-stu-id="d9189-124">When you add an attribute to a product, you also define other parameters.</span></span> <span data-ttu-id="d9189-125">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="d9189-125">Here are some examples:</span></span>

-   <span data-ttu-id="d9189-126">Minimalne i minimalne zakresy dla atrybutu typu **Liczba całkowita** lub **Ułamek**.</span><span class="sxs-lookup"><span data-stu-id="d9189-126">The minimum and maximum ranges for an attribute of the **Integer** or **Fraction** type.</span></span>
-   <span data-ttu-id="d9189-127">Działania związane z przekroczeniem tolerancji dla atrybutów typu **Liczba całkowita** lub **Ułamek**.</span><span class="sxs-lookup"><span data-stu-id="d9189-127">The tolerance actions for an attribute of the **Integer** or **Fraction** type.</span></span> <span data-ttu-id="d9189-128">Jeśli wartość atrybutu wykracza poza minimalny lub maksymalny zakres, działanie może polegać na wyświetleniu ostrzeżenia lub komunikatu o błędzie.</span><span class="sxs-lookup"><span data-stu-id="d9189-128">If the value of the attribute falls outside the minimum and maximum range, the action can be either a warning message or an error message.</span></span>
-   <span data-ttu-id="d9189-129">Wartość docelowa atrybutu.</span><span class="sxs-lookup"><span data-stu-id="d9189-129">The target value for the attribute.</span></span> <span data-ttu-id="d9189-130">Ta wartość jest optymalną wartość atrybutu i odnosi się do wszystkich typów atrybutów.</span><span class="sxs-lookup"><span data-stu-id="d9189-130">This value is the optimal value of the attribute, and it applies to all attribute types.</span></span>

<span data-ttu-id="d9189-131">Dostępne są strony produktów wybranych na stronie **Zwolnione produkty** w module Zarządzanie informacjami o produktach.</span><span class="sxs-lookup"><span data-stu-id="d9189-131">You can access the pages for products that you select on the **Released products** page in Product information management.</span></span> <span data-ttu-id="d9189-132">Po przypisaniu atrybutów partii do produktu można dodać konkretne wartości atrybutów na stronie **Atrybuty partii zapasów**.</span><span class="sxs-lookup"><span data-stu-id="d9189-132">After you assign batch attributes to a product, you can add specific values to the attributes on the **Inventory batch attributes** page.</span></span>

## <a name="reserve-batches"></a><span data-ttu-id="d9189-133">Rezerwowanie partii</span><span class="sxs-lookup"><span data-stu-id="d9189-133">Reserve batches</span></span>
<span data-ttu-id="d9189-134">Można wyszukiwać atrybuty partii podczas rezerwowania partii dla zamówienia sprzedaży w celu wypełnienia zamówienia odbiorcy lub podczas odbierania i rezerwowania partii dla zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d9189-134">You can search on batch attributes when you do batch reservations for a sales order to fullfill a customer's order, or when you pick and reserve batches for a production order.</span></span> <span data-ttu-id="d9189-135">To ułatwia znajdowanie partii zapasów zawierającej produkt, który ma atrybut partii, którego szukasz.</span><span class="sxs-lookup"><span data-stu-id="d9189-135">The search helps locate an inventory batch that contains the product that has the batch attribute that you want.</span></span> <span data-ttu-id="d9189-136">Po znalezieniu partii możesz zarezerwować produkt w wierszu źródłowej transakcji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="d9189-136">After you locate the batch or batches, you can reserve the product to the originating inventory transaction line.</span></span>




