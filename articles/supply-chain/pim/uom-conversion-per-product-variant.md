---
title: Przeliczanie jednostki miary dla wariantów produktów
description: W tym temacie wyjaśniono, jak skonfigurować przeliczanie jednostek miary dla wariantów produktu.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: e50be7fa6fa686a90b2dd5c5200c881e4629f019
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204500"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="3fc0b-103">Przeliczanie jednostki miary dla wariantów produktów</span><span class="sxs-lookup"><span data-stu-id="3fc0b-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3fc0b-104">W tym temacie wyjaśniono, jak skonfigurować przeliczanie jednostek miary dla wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="3fc0b-105">Zawiera przykładową konfigurację.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-105">It includes an example of the setup.</span></span>

<span data-ttu-id="3fc0b-106">Ta funkcja umożliwia firmom definiowanie różnych konwersji jednostek między wariantami tego samego produktu.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="3fc0b-107">W tym temacie używany jest poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-107">The following example is used in this topic.</span></span> <span data-ttu-id="3fc0b-108">Firma sprzedaje T-shirty w rozmiarach Small, Medium, Large, and Extra-Large.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="3fc0b-109">T-shirt jest definiowany jako produkt, a różne rozmiary są definiowane jako warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="3fc0b-110">T-shirty są pakowane w pudełka po pięć T-shirtów z wyjątkiem rozmiaru Extra-Large, których w pudełku mieści się tylko cztery.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="3fc0b-111">Firma chce śledzić różne warianty T-shirtów w jednostce **Sztuki**, ale sprzedaży T-shirty w jednostkach **Pudełka**.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="3fc0b-112">Konwersja między jednostką magazynową i jednostką sprzedaży to 1 pudełko = 5 sztuk, z wyjątkiem wariantu Extra-Large, w którym to przypadku konwersja to 1 pudełko = 4 sztuki.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="3fc0b-113">Konfigurowanie produktu pod katem konwersji jednostek dla wariantu produktu</span><span class="sxs-lookup"><span data-stu-id="3fc0b-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="3fc0b-114">Warianty produktów można tworzyć dla produktów **Podtyp produktu**: **Produkt główny**.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-114">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="3fc0b-115">Aby uzyskać więcej informacji, zobacz temat [Tworzenie produktu głównego](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="3fc0b-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="3fc0b-116">Funkcja nie jest włączona dla produktów, które są ustawiane dla procesów ilości efektywnej.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-116">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="3fc0b-117">Po utworzeniu produktu głównego z wariantami zwalnianych produktów można skonfigurować konwersje jednostek według wariantów.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-117">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="3fc0b-118">Element menu służący do otwierania strony konwersji jednostki można znaleźć w kontekście produktu lub wariantu produktu na następujących stronach.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-118">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="3fc0b-119">Strona **Szczegóły produktu**</span><span class="sxs-lookup"><span data-stu-id="3fc0b-119">**Product details** page</span></span>
-   <span data-ttu-id="3fc0b-120">Strona **Szczegóły zwalnianych produktów**</span><span class="sxs-lookup"><span data-stu-id="3fc0b-120">**Released products details** page</span></span>
-   <span data-ttu-id="3fc0b-121">Strona **Zwolnione warianty produktu**</span><span class="sxs-lookup"><span data-stu-id="3fc0b-121">**Released product variants** page</span></span>

<span data-ttu-id="3fc0b-122">Po otwarciu strony **Przeliczanie jednostek** w kontekście produktu głównego lub zwolnionego wariantu produktu możesz wybrać, czy chcesz skonfigurować konwersję jednostek dla produktu czy dla wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-122">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="3fc0b-123">Można to zrobić zaznaczając opcję **Wariant produktu** lub **Produktu** na stronie **Tworzenie konwersji dla**.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-123">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="3fc0b-124">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="3fc0b-124">Product variant</span></span>

<span data-ttu-id="3fc0b-125">W przypadku wybrania opcji **Wariant produktu** można wybrać dla którego wariantu chcesz skonfigurować konwersję jednostek w polu **Wariant produktu**.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-125">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="3fc0b-126">Produkt</span><span class="sxs-lookup"><span data-stu-id="3fc0b-126">Product</span></span>

<span data-ttu-id="3fc0b-127">W przypadku wybrania opcji **Produkt** można skonfigurować konwersję jednostek dla produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-127">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="3fc0b-128">Ta konwersja jednostki będzie stosowana do wszystkich wariantów produktu bez zdefiniowanej konwersji jednostki.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-128">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="3fc0b-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="3fc0b-129">Example</span></span>

<span data-ttu-id="3fc0b-130">Produkt główny **T-Shirt** ma cztery zwolnione warianty produktów: Small, Medium, Large i X-Large.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-130">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="3fc0b-131">T-shirty są pakowane w pudełka po pięć T-shirtów z wyjątkiem rozmiaru Extra-Large, których w pudełku mieści się tylko cztery.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-131">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="3fc0b-132">Najpierw otwórz stronę **Przeliczanie jednostek** ze strony Szczegóły zwalniania produktu dla **T-shirt.**</span><span class="sxs-lookup"><span data-stu-id="3fc0b-132">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="3fc0b-133">Na stronie **Przeliczanie jednostek** ustaw konwersję jednostek dla wariantu zwolnienia produktu X-Large.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-133">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="3fc0b-134">**Field**</span><span class="sxs-lookup"><span data-stu-id="3fc0b-134">**Field**</span></span>             | <span data-ttu-id="3fc0b-135">**Ustawienie**</span><span class="sxs-lookup"><span data-stu-id="3fc0b-135">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="3fc0b-136">Utwórz konwersję dla</span><span class="sxs-lookup"><span data-stu-id="3fc0b-136">Create conversion for</span></span> | <span data-ttu-id="3fc0b-137">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="3fc0b-137">Product variant</span></span>         |
| <span data-ttu-id="3fc0b-138">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="3fc0b-138">Product variant</span></span>       | <span data-ttu-id="3fc0b-139">T-Shirt : : X-Large : :</span><span class="sxs-lookup"><span data-stu-id="3fc0b-139">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="3fc0b-140">Od jednostki</span><span class="sxs-lookup"><span data-stu-id="3fc0b-140">From unit</span></span>             | <span data-ttu-id="3fc0b-141">Pola</span><span class="sxs-lookup"><span data-stu-id="3fc0b-141">Boxes</span></span>                   |
| <span data-ttu-id="3fc0b-142">Współczynnik</span><span class="sxs-lookup"><span data-stu-id="3fc0b-142">Factor</span></span>                | <span data-ttu-id="3fc0b-143">4</span><span class="sxs-lookup"><span data-stu-id="3fc0b-143">4</span></span>                       |
| <span data-ttu-id="3fc0b-144">Do jednostki</span><span class="sxs-lookup"><span data-stu-id="3fc0b-144">To Unit</span></span>               | <span data-ttu-id="3fc0b-145">Sztuki</span><span class="sxs-lookup"><span data-stu-id="3fc0b-145">Pieces</span></span>                  |

<span data-ttu-id="3fc0b-146">Warianty zwalniania produktów Small, Medium i Large mają tę samą konwersje jednostki między jednostkami Pudełko i Sztuki, co oznacza, że możesz zdefiniować jednostkę konwersji dla tych wariantów produktu w produkcie głównym.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-146">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="3fc0b-147">**Field**</span><span class="sxs-lookup"><span data-stu-id="3fc0b-147">**Field**</span></span>             | <span data-ttu-id="3fc0b-148">**Ustawienie**</span><span class="sxs-lookup"><span data-stu-id="3fc0b-148">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="3fc0b-149">Utwórz konwersję dla</span><span class="sxs-lookup"><span data-stu-id="3fc0b-149">Create conversion for</span></span> | <span data-ttu-id="3fc0b-150">Produkt</span><span class="sxs-lookup"><span data-stu-id="3fc0b-150">Product</span></span>     |
| <span data-ttu-id="3fc0b-151">Produkt</span><span class="sxs-lookup"><span data-stu-id="3fc0b-151">Product</span></span>               | <span data-ttu-id="3fc0b-152">T-Shirt</span><span class="sxs-lookup"><span data-stu-id="3fc0b-152">T-Shirt</span></span>     |
| <span data-ttu-id="3fc0b-153">Od jednostki</span><span class="sxs-lookup"><span data-stu-id="3fc0b-153">From unit</span></span>             | <span data-ttu-id="3fc0b-154">Pola</span><span class="sxs-lookup"><span data-stu-id="3fc0b-154">Boxes</span></span>       |
| <span data-ttu-id="3fc0b-155">Współczynnik</span><span class="sxs-lookup"><span data-stu-id="3fc0b-155">Factor</span></span>                | <span data-ttu-id="3fc0b-156">5</span><span class="sxs-lookup"><span data-stu-id="3fc0b-156">5</span></span>           |
| <span data-ttu-id="3fc0b-157">Do jednostki</span><span class="sxs-lookup"><span data-stu-id="3fc0b-157">To Unit</span></span>               | <span data-ttu-id="3fc0b-158">Sztuki</span><span class="sxs-lookup"><span data-stu-id="3fc0b-158">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="3fc0b-159">Aktualizowanie konwersji jednostek przy użyciu programu Excel</span><span class="sxs-lookup"><span data-stu-id="3fc0b-159">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="3fc0b-160">Jeśli produkt ma wiele wariantów produktu z różnymi konwersjami jednostek, dobrym rozwiązaniem jest eksportowanie jednostek konwersji ze strony **Przeliczanie jednostek** do arkusza kalkulacyjnego programu Excel, zaktualizowanie konwersji, a następnie opublikowanie ich ponownie w Supply Chain Mangement.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-160">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Supply Chain Mangement.</span></span>

<span data-ttu-id="3fc0b-161">Opcję eksportowania do programu Excel i publikowania zmian z powrotem w Supply Chain Mangement włącza się z elementu menu **Otwórz w programie Microsoft office** w okienku akcji na stronie **Przeliczanie jednostek**.</span><span class="sxs-lookup"><span data-stu-id="3fc0b-161">The option to export to Excel and publish the edits back to Supply Chain Mangement is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
