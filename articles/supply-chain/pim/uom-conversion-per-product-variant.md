---
title: Przeliczanie jednostki miary dla wariantów produktów
description: W tym temacie wyjaśniono, jak skonfigurować przeliczanie jednostek miary dla wariantów produktu.
author: johanhoffmann
manager: AnnBe
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 9d5d6fd65717cd886f1c6576aabf2bc59ca4fcaf
ms.sourcegitcommit: a47f705976b7a5b34492294e28aa8cd47ea38825
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2019
ms.locfileid: "345934"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="ab038-103">Przeliczanie jednostki miary dla wariantów produktów</span><span class="sxs-lookup"><span data-stu-id="ab038-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

[!include [pivate-preview](../includes/pivate-preview-banner.md)]

<span data-ttu-id="ab038-104">W tym temacie wyjaśniono, jak skonfigurować przeliczanie jednostek miary dla wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="ab038-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="ab038-105">Zawiera przykładową konfigurację.</span><span class="sxs-lookup"><span data-stu-id="ab038-105">It includes an example of the setup.</span></span>

<span data-ttu-id="ab038-106">Ta funkcja umożliwia firmom definiowanie różnych konwersji jednostek między wariantami tego samego produktu.</span><span class="sxs-lookup"><span data-stu-id="ab038-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="ab038-107">W tym temacie używany jest poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="ab038-107">The following example is used in this topic.</span></span> <span data-ttu-id="ab038-108">Firma sprzedaje T-shirty w rozmiarach Small, Medium, Large, and Extra-Large.</span><span class="sxs-lookup"><span data-stu-id="ab038-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="ab038-109">T-shirt jest definiowany jako produkt, a różne rozmiary są definiowane jako warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="ab038-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="ab038-110">T-shirty są pakowane w pudełka po pięć T-shirtów z wyjątkiem rozmiaru Extra-Large, których w pudełku mieści się tylko cztery.</span><span class="sxs-lookup"><span data-stu-id="ab038-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="ab038-111">Firma chce śledzić różne warianty T-shirtów w jednostce **Sztuki**, ale sprzedaży T-shirty w jednostkach **Pudełka**.</span><span class="sxs-lookup"><span data-stu-id="ab038-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="ab038-112">Konwersja między jednostką magazynową i jednostką sprzedaży to 1 pudełko = 5 sztuk, z wyjątkiem wariantu Extra-Large, w którym to przypadku konwersja to 1 pudełko = 4 sztuki.</span><span class="sxs-lookup"><span data-stu-id="ab038-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

## <a name="setup"></a><span data-ttu-id="ab038-113">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="ab038-113">Setup</span></span>

<span data-ttu-id="ab038-114">Można skonfigurować parametry do używania funkcji produktów włączonych dla **Wszystkie procesy** lub tylko dla produktów włączonych dla **Procesów w magazynie** za pomocą **Włącz konwersację jednostek miary** na stronie **Parametry informacji o produkcie**.</span><span class="sxs-lookup"><span data-stu-id="ab038-114">You can configure the parameters for using the feature for products enabled for **All processes** or only for product enabled for the **Warehouse processes** by using the **Enable unit of measure conversations** option on the **Product information parameters** page.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="ab038-115">Konfigurowanie produktu pod katem konwersji jednostek dla wariantu produktu</span><span class="sxs-lookup"><span data-stu-id="ab038-115">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="ab038-116">Warianty produktów można tworzyć dla produktów **Podtyp produktu**: **Produkt główny**.</span><span class="sxs-lookup"><span data-stu-id="ab038-116">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="ab038-117">Aby uzyskać więcej informacji, zobacz temat [Tworzenie produktu głównego](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="ab038-117">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="ab038-118">Funkcja nie jest włączona dla produktów, które są ustawiane dla procesów ilości efektywnej.</span><span class="sxs-lookup"><span data-stu-id="ab038-118">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="ab038-119">Podczas tworzenia produktu głównego włącz konwersję jednostkę miary za pomocą opcji **Włącz konwersje jednostki miary** na stronie **Szczegóły produktu**.</span><span class="sxs-lookup"><span data-stu-id="ab038-119">During the creation of a product master enable unit of measure conversion by using the **Enable unit of measure conversions** option on the **Product details** page.</span></span>

<span data-ttu-id="ab038-120">Po utworzeniu produktu głównego z wariantami zwalnianych produktów można skonfigurować konwersje jednostek według wariantów.</span><span class="sxs-lookup"><span data-stu-id="ab038-120">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="ab038-121">Element menu służący do otwierania strony konwersji jednostki można znaleźć w kontekście produktu lub wariantu produktu na następujących stronach.</span><span class="sxs-lookup"><span data-stu-id="ab038-121">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="ab038-122">Strona **Szczegóły produktu**</span><span class="sxs-lookup"><span data-stu-id="ab038-122">**Product details** page</span></span>
-   <span data-ttu-id="ab038-123">Strona **Szczegóły zwalnianych produktów**</span><span class="sxs-lookup"><span data-stu-id="ab038-123">**Released products details** page</span></span>
-   <span data-ttu-id="ab038-124">Strona **Zwolnione warianty produktu**</span><span class="sxs-lookup"><span data-stu-id="ab038-124">**Released product variants** page</span></span>

<span data-ttu-id="ab038-125">Po otwarciu strony **Przeliczanie jednostek** w kontekście produktu głównego lub zwolnionego wariantu produktu możesz wybrać, czy chcesz skonfigurować konwersję jednostek dla produktu czy dla wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="ab038-125">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="ab038-126">Można to zrobić zaznaczając opcję **Wariant produktu** lub **Produktu** na stronie **Tworzenie konwersji dla**.</span><span class="sxs-lookup"><span data-stu-id="ab038-126">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="ab038-127">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="ab038-127">Product variant</span></span>

<span data-ttu-id="ab038-128">W przypadku wybrania opcji **Wariant produktu** można wybrać dla którego wariantu chcesz skonfigurować konwersję jednostek w polu **Wariant produktu**.</span><span class="sxs-lookup"><span data-stu-id="ab038-128">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="ab038-129">Produkt</span><span class="sxs-lookup"><span data-stu-id="ab038-129">Product</span></span>

<span data-ttu-id="ab038-130">W przypadku wybrania opcji **Produkt** można skonfigurować konwersję jednostek dla produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="ab038-130">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="ab038-131">Ta konwersja jednostki będzie stosowana do wszystkich wariantów produktu bez zdefiniowanej konwersji jednostki.</span><span class="sxs-lookup"><span data-stu-id="ab038-131">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="ab038-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="ab038-132">Example</span></span>

<span data-ttu-id="ab038-133">Produkt główny **T-Shirt** ma cztery zwolnione warianty produktów: Small, Medium, Large i X-Large.</span><span class="sxs-lookup"><span data-stu-id="ab038-133">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="ab038-134">T-shirty są pakowane w pudełka po pięć T-shirtów z wyjątkiem rozmiaru Extra-Large, których w pudełku mieści się tylko cztery.</span><span class="sxs-lookup"><span data-stu-id="ab038-134">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="ab038-135">Najpierw otwórz stronę **Przeliczanie jednostek** ze strony Szczegóły zwalniania produktu dla **T-shirt.**</span><span class="sxs-lookup"><span data-stu-id="ab038-135">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="ab038-136">Na stronie **Przeliczanie jednostek** ustaw konwersję jednostek dla wariantu zwolnienia produktu X-Large.</span><span class="sxs-lookup"><span data-stu-id="ab038-136">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="ab038-137">**Field**</span><span class="sxs-lookup"><span data-stu-id="ab038-137">**Field**</span></span>             | <span data-ttu-id="ab038-138">**Ustawienie**</span><span class="sxs-lookup"><span data-stu-id="ab038-138">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="ab038-139">Utwórz konwersję dla</span><span class="sxs-lookup"><span data-stu-id="ab038-139">Create conversion for</span></span> | <span data-ttu-id="ab038-140">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="ab038-140">Product variant</span></span>         |
| <span data-ttu-id="ab038-141">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="ab038-141">Product variant</span></span>       | <span data-ttu-id="ab038-142">T-Shirt : : X-Large : :</span><span class="sxs-lookup"><span data-stu-id="ab038-142">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="ab038-143">Od jednostki</span><span class="sxs-lookup"><span data-stu-id="ab038-143">From unit</span></span>             | <span data-ttu-id="ab038-144">Pola</span><span class="sxs-lookup"><span data-stu-id="ab038-144">Boxes</span></span>                   |
| <span data-ttu-id="ab038-145">Współczynnik</span><span class="sxs-lookup"><span data-stu-id="ab038-145">Factor</span></span>                | <span data-ttu-id="ab038-146">4</span><span class="sxs-lookup"><span data-stu-id="ab038-146">4</span></span>                       |
| <span data-ttu-id="ab038-147">Do jednostki</span><span class="sxs-lookup"><span data-stu-id="ab038-147">To Unit</span></span>               | <span data-ttu-id="ab038-148">Sztuki</span><span class="sxs-lookup"><span data-stu-id="ab038-148">Pieces</span></span>                  |

<span data-ttu-id="ab038-149">Warianty zwalniania produktów Small, Medium i Large mają tę samą konwersje jednostki między jednostkami Pudełko i Sztuki, co oznacza, że możesz zdefiniować jednostkę konwersji dla tych wariantów produktu w produkcie głównym.</span><span class="sxs-lookup"><span data-stu-id="ab038-149">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="ab038-150">**Field**</span><span class="sxs-lookup"><span data-stu-id="ab038-150">**Field**</span></span>             | <span data-ttu-id="ab038-151">**Ustawienie**</span><span class="sxs-lookup"><span data-stu-id="ab038-151">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="ab038-152">Utwórz konwersję dla</span><span class="sxs-lookup"><span data-stu-id="ab038-152">Create conversion for</span></span> | <span data-ttu-id="ab038-153">Produkt</span><span class="sxs-lookup"><span data-stu-id="ab038-153">Product</span></span>     |
| <span data-ttu-id="ab038-154">Produkt</span><span class="sxs-lookup"><span data-stu-id="ab038-154">Product</span></span>               | <span data-ttu-id="ab038-155">T-Shirt</span><span class="sxs-lookup"><span data-stu-id="ab038-155">T-Shirt</span></span>     |
| <span data-ttu-id="ab038-156">Od jednostki</span><span class="sxs-lookup"><span data-stu-id="ab038-156">From unit</span></span>             | <span data-ttu-id="ab038-157">Pola</span><span class="sxs-lookup"><span data-stu-id="ab038-157">Boxes</span></span>       |
| <span data-ttu-id="ab038-158">Współczynnik</span><span class="sxs-lookup"><span data-stu-id="ab038-158">Factor</span></span>                | <span data-ttu-id="ab038-159">5</span><span class="sxs-lookup"><span data-stu-id="ab038-159">5</span></span>           |
| <span data-ttu-id="ab038-160">Do jednostki</span><span class="sxs-lookup"><span data-stu-id="ab038-160">To Unit</span></span>               | <span data-ttu-id="ab038-161">Sztuki</span><span class="sxs-lookup"><span data-stu-id="ab038-161">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="ab038-162">Aktualizowanie konwersji jednostek przy użyciu programu Excel</span><span class="sxs-lookup"><span data-stu-id="ab038-162">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="ab038-163">Jeśli produkt ma wiele wariantów produktu z różnymi konwersjami jednostek, dobrym rozwiązaniem jest eksportowanie jednostek konwersji ze strony **Przeliczanie jednostek** do arkusza kalkulacyjnego programu Excel, zaktualizowanie konwersji, a następnie opublikowanie ich ponownie w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ab038-163">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Finance and Operations.</span></span>

<span data-ttu-id="ab038-164">Opcję eksportowania do programu Excel i publikowania zmian z powrotem w Finance and Operations włącza się z elementu menu **Otwórz w programie Microsoft office** w okienku akcji na stronie **Przeliczanie jednostek**.</span><span class="sxs-lookup"><span data-stu-id="ab038-164">The option to export to Excel and publish the edits back to Finance and Operations is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
