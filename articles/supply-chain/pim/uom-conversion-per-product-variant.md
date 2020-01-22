---
title: Przeliczanie jednostki miary dla wariantów produktów
description: W tym temacie wyjaśniono, jak skonfigurować przeliczanie jednostek miary dla wariantów produktu.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: c8181f0bda9b781a6c2b0feb0aba1beb51bfea65
ms.sourcegitcommit: af36eb17b36092a3101bbfc96486b25036676558
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/06/2020
ms.locfileid: "2935106"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="0e9ff-103">Przeliczanie jednostki miary dla wariantów produktów</span><span class="sxs-lookup"><span data-stu-id="0e9ff-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e9ff-104">W tym temacie wyjaśniono, jak skonfigurować przeliczanie jednostek miary dla wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="0e9ff-105">Zawiera przykładową konfigurację.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-105">It includes an example of the setup.</span></span>

<span data-ttu-id="0e9ff-106">Ta funkcja umożliwia firmom definiowanie różnych konwersji jednostek między wariantami tego samego produktu.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="0e9ff-107">W tym temacie używany jest poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-107">The following example is used in this topic.</span></span> <span data-ttu-id="0e9ff-108">Firma sprzedaje T-shirty w rozmiarach Small, Medium, Large, and Extra-Large.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="0e9ff-109">T-shirt jest definiowany jako produkt, a różne rozmiary są definiowane jako warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="0e9ff-110">T-shirty są pakowane w pudełka po pięć T-shirtów z wyjątkiem rozmiaru Extra-Large, których w pudełku mieści się tylko cztery.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="0e9ff-111">Firma chce śledzić różne warianty T-shirtów w jednostce **Sztuki**, ale sprzedaży T-shirty w jednostkach **Pudełka**.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="0e9ff-112">Konwersja między jednostką magazynową i jednostką sprzedaży to 1 pudełko = 5 sztuk, z wyjątkiem wariantu Extra-Large, w którym to przypadku konwersja to 1 pudełko = 4 sztuki.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="0e9ff-113">Konfigurowanie produktu pod katem konwersji jednostek dla wariantu produktu</span><span class="sxs-lookup"><span data-stu-id="0e9ff-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="0e9ff-114">Warianty produktów można tworzyć dla produktów **Podtyp produktu**: **Produkt główny**.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-114">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="0e9ff-115">Aby uzyskać więcej informacji, zobacz temat [Tworzenie produktu głównego](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="0e9ff-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="0e9ff-116">Funkcja nie jest włączona dla produktów, które są ustawiane dla procesów ilości efektywnej.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-116">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="0e9ff-117">Po utworzeniu produktu głównego z wariantami zwalnianych produktów można skonfigurować konwersje jednostek według wariantów.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-117">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="0e9ff-118">Element menu służący do otwierania strony konwersji jednostki można znaleźć w kontekście produktu lub wariantu produktu na następujących stronach.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-118">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="0e9ff-119">Strona **Szczegóły produktu**</span><span class="sxs-lookup"><span data-stu-id="0e9ff-119">**Product details** page</span></span>
-   <span data-ttu-id="0e9ff-120">Strona **Szczegóły zwalnianych produktów**</span><span class="sxs-lookup"><span data-stu-id="0e9ff-120">**Released products details** page</span></span>
-   <span data-ttu-id="0e9ff-121">Strona **Zwolnione warianty produktu**</span><span class="sxs-lookup"><span data-stu-id="0e9ff-121">**Released product variants** page</span></span>

<span data-ttu-id="0e9ff-122">Po otwarciu strony **Przeliczanie jednostek** w kontekście produktu głównego lub zwolnionego wariantu produktu możesz wybrać, czy chcesz skonfigurować konwersję jednostek dla produktu czy dla wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-122">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="0e9ff-123">Można to zrobić zaznaczając opcję **Wariant produktu** lub **Produktu** na stronie **Tworzenie konwersji dla**.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-123">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="0e9ff-124">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="0e9ff-124">Product variant</span></span>

<span data-ttu-id="0e9ff-125">W przypadku wybrania opcji **Wariant produktu** można wybrać dla którego wariantu chcesz skonfigurować konwersję jednostek w polu **Wariant produktu**.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-125">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="0e9ff-126">Produkt</span><span class="sxs-lookup"><span data-stu-id="0e9ff-126">Product</span></span>

<span data-ttu-id="0e9ff-127">W przypadku wybrania opcji **Produkt** można skonfigurować konwersję jednostek dla produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-127">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="0e9ff-128">Ta konwersja jednostki będzie stosowana do wszystkich wariantów produktu bez zdefiniowanej konwersji jednostki.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-128">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="0e9ff-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="0e9ff-129">Example</span></span>

<span data-ttu-id="0e9ff-130">Produkt główny **T-Shirt** ma cztery zwolnione warianty produktów: Small, Medium, Large i X-Large.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-130">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="0e9ff-131">T-shirty są pakowane w pudełka po pięć T-shirtów z wyjątkiem rozmiaru Extra-Large, których w pudełku mieści się tylko cztery.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-131">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="0e9ff-132">Najpierw otwórz stronę **Przeliczanie jednostek** ze strony Szczegóły zwalniania produktu dla **T-shirt.**</span><span class="sxs-lookup"><span data-stu-id="0e9ff-132">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="0e9ff-133">Na stronie **Przeliczanie jednostek** ustaw konwersję jednostek dla wariantu zwolnienia produktu X-Large.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-133">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="0e9ff-134">**Field**</span><span class="sxs-lookup"><span data-stu-id="0e9ff-134">**Field**</span></span>             | <span data-ttu-id="0e9ff-135">**Ustawienie**</span><span class="sxs-lookup"><span data-stu-id="0e9ff-135">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="0e9ff-136">Utwórz konwersję dla</span><span class="sxs-lookup"><span data-stu-id="0e9ff-136">Create conversion for</span></span> | <span data-ttu-id="0e9ff-137">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="0e9ff-137">Product variant</span></span>         |
| <span data-ttu-id="0e9ff-138">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="0e9ff-138">Product variant</span></span>       | <span data-ttu-id="0e9ff-139">T-Shirt : : X-Large : :</span><span class="sxs-lookup"><span data-stu-id="0e9ff-139">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="0e9ff-140">Od jednostki</span><span class="sxs-lookup"><span data-stu-id="0e9ff-140">From unit</span></span>             | <span data-ttu-id="0e9ff-141">Pola</span><span class="sxs-lookup"><span data-stu-id="0e9ff-141">Boxes</span></span>                   |
| <span data-ttu-id="0e9ff-142">Współczynnik</span><span class="sxs-lookup"><span data-stu-id="0e9ff-142">Factor</span></span>                | <span data-ttu-id="0e9ff-143">4</span><span class="sxs-lookup"><span data-stu-id="0e9ff-143">4</span></span>                       |
| <span data-ttu-id="0e9ff-144">Do jednostki</span><span class="sxs-lookup"><span data-stu-id="0e9ff-144">To Unit</span></span>               | <span data-ttu-id="0e9ff-145">Sztuki</span><span class="sxs-lookup"><span data-stu-id="0e9ff-145">Pieces</span></span>                  |

<span data-ttu-id="0e9ff-146">Warianty zwalniania produktów Small, Medium i Large mają tę samą konwersje jednostki między jednostkami Pudełko i Sztuki, co oznacza, że możesz zdefiniować jednostkę konwersji dla tych wariantów produktu w produkcie głównym.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-146">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="0e9ff-147">**Field**</span><span class="sxs-lookup"><span data-stu-id="0e9ff-147">**Field**</span></span>             | <span data-ttu-id="0e9ff-148">**Ustawienie**</span><span class="sxs-lookup"><span data-stu-id="0e9ff-148">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="0e9ff-149">Utwórz konwersję dla</span><span class="sxs-lookup"><span data-stu-id="0e9ff-149">Create conversion for</span></span> | <span data-ttu-id="0e9ff-150">Produkt</span><span class="sxs-lookup"><span data-stu-id="0e9ff-150">Product</span></span>     |
| <span data-ttu-id="0e9ff-151">Produkt</span><span class="sxs-lookup"><span data-stu-id="0e9ff-151">Product</span></span>               | <span data-ttu-id="0e9ff-152">T-Shirt</span><span class="sxs-lookup"><span data-stu-id="0e9ff-152">T-Shirt</span></span>     |
| <span data-ttu-id="0e9ff-153">Od jednostki</span><span class="sxs-lookup"><span data-stu-id="0e9ff-153">From unit</span></span>             | <span data-ttu-id="0e9ff-154">Pola</span><span class="sxs-lookup"><span data-stu-id="0e9ff-154">Boxes</span></span>       |
| <span data-ttu-id="0e9ff-155">Współczynnik</span><span class="sxs-lookup"><span data-stu-id="0e9ff-155">Factor</span></span>                | <span data-ttu-id="0e9ff-156">5</span><span class="sxs-lookup"><span data-stu-id="0e9ff-156">5</span></span>           |
| <span data-ttu-id="0e9ff-157">Do jednostki</span><span class="sxs-lookup"><span data-stu-id="0e9ff-157">To Unit</span></span>               | <span data-ttu-id="0e9ff-158">Sztuki</span><span class="sxs-lookup"><span data-stu-id="0e9ff-158">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="0e9ff-159">Aktualizowanie konwersji jednostek przy użyciu programu Excel</span><span class="sxs-lookup"><span data-stu-id="0e9ff-159">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="0e9ff-160">Jeśli produkt ma wiele wariantów produktu z różnymi konwersjami jednostek, dobrym rozwiązaniem jest eksportowanie jednostek konwersji ze strony **Przeliczanie jednostek** do arkusza kalkulacyjnego programu Excel, zaktualizowanie konwersji, a następnie opublikowanie ich ponownie w Supply Chain Mangement.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-160">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Supply Chain Mangement.</span></span>

<span data-ttu-id="0e9ff-161">Opcję eksportowania do programu Excel i publikowania zmian z powrotem w Supply Chain Mangement włącza się z elementu menu **Otwórz w programie Microsoft office** w okienku akcji na stronie **Przeliczanie jednostek**.</span><span class="sxs-lookup"><span data-stu-id="0e9ff-161">The option to export to Excel and publish the edits back to Supply Chain Mangement is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
