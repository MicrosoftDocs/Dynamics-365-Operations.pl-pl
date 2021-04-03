---
title: Przeliczanie jednostki miary dla wariantów produktów
description: W tym temacie wyjaśniono, jak skonfigurować konwersje jednostek miary dla wariantów produktu. Zawiera przykładową konfigurację.
author: johanhoffmann
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: ddb6c614ede98e46e46ff284a1a16669bbaaaf66
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258054"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="714fa-104">Przeliczanie jednostki miary dla wariantów produktów</span><span class="sxs-lookup"><span data-stu-id="714fa-104">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="714fa-105">W tym temacie wyjaśniono, jak skonfigurować konwersje jednostek miary dla różnych wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="714fa-105">This topic explains how to set up unit of measure conversions for various product variants.</span></span>

<span data-ttu-id="714fa-106">Zamiast tworzyć wiele pojedynczych produktów, które wymagają obsługi, można użyć wariantów produktu w celu utworzenia różnych wariantów jednego produktu.</span><span class="sxs-lookup"><span data-stu-id="714fa-106">Instead of creating multiple individual products that must be maintained, you can use product variants to create variations of a single product.</span></span> <span data-ttu-id="714fa-107">Na przykład wariantem produktu może być koszulka w danym rozmiarze i kolorze.</span><span class="sxs-lookup"><span data-stu-id="714fa-107">For example, a product variant might be a T-shirt of a given size and color.</span></span>

<span data-ttu-id="714fa-108">Wcześniej konwersje jednostek można było konfigurować tylko na poziomie produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="714fa-108">Previously, unit conversions could be set up only on the product master.</span></span> <span data-ttu-id="714fa-109">Dlatego wszystkie warianty produktu miały takie same reguły konwersji jednostek.</span><span class="sxs-lookup"><span data-stu-id="714fa-109">Therefore, all product variants had the same unit conversion rules.</span></span> <span data-ttu-id="714fa-110">Jeśli jednak funkcja *Konwersje jednostki miary dla wariantów produktów* jest włączona, a koszulki są sprzedawane w pudełkach i liczba koszulek, które można zapakować do pudełka, zależy od rozmiaru koszulki, można teraz skonfigurować konwersję jednostek między różnymi rozmiarami koszulek a pudełkami używanymi do pakowania.</span><span class="sxs-lookup"><span data-stu-id="714fa-110">However, when the *Unit of measure conversions for product variants* feature is turned on, if your T-shirts are sold in boxes, and the number of T-shirts that can be packed in a box depends on the size of the T-shirts, you can now set up unit conversions between the different shirt sizes and the boxes that are used for packaging.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="714fa-111">Włączanie funkcji w systemie</span><span class="sxs-lookup"><span data-stu-id="714fa-111">Turn on the feature in your system</span></span>

<span data-ttu-id="714fa-112">Jeśli ta funkcja nie jest jeszcze widoczna w systemie, przejdź do tematu [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Konwersje jednostki miary dla wariantów produktów*.</span><span class="sxs-lookup"><span data-stu-id="714fa-112">If you don't already see this feature in your system, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Unit of measure conversions for product variants* feature.</span></span>

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="714fa-113">Konfigurowanie produktu pod katem konwersji jednostek dla wariantu produktu</span><span class="sxs-lookup"><span data-stu-id="714fa-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="714fa-114">Warianty produktów można tworzyć tylko dla produktów głównych.</span><span class="sxs-lookup"><span data-stu-id="714fa-114">Product variants can be created only for products that are product masters.</span></span> <span data-ttu-id="714fa-115">Aby uzyskać więcej informacji, zobacz temat [Tworzenie produktu głównego](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="714fa-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span> <span data-ttu-id="714fa-116">Funkcja *Konwersje jednostki miary dla wariantów produktów* jest niedostępna dla produktów skonfigurowanych dla procesów obsługi ilości efektywnej.</span><span class="sxs-lookup"><span data-stu-id="714fa-116">The *Unit of measure conversions for product variants* feature isn't available for products that are set up for catch-weight processes.</span></span>

<span data-ttu-id="714fa-117">Aby skonfigurować produkt główny w celu obsługi konwersji jednostek na wariant, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="714fa-117">To configure a product master to support unit conversion per variant, follow these steps.</span></span>

1. <span data-ttu-id="714fa-118">Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Produkty \> Produkty główne**.</span><span class="sxs-lookup"><span data-stu-id="714fa-118">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="714fa-119">Utwórz lub otwórz produkt główny, aby przejść do jego strony **Szczegóły produktu**.</span><span class="sxs-lookup"><span data-stu-id="714fa-119">Create or open a product master to go to its **Product details** page.</span></span>
1. <span data-ttu-id="714fa-120">Ustaw opcję **Włącz konwersje jednostek miary** na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="714fa-120">Set the **Enable unit of measure conversions** option to *Yes*.</span></span>
1. <span data-ttu-id="714fa-121">W okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz pozycję **Konwersje jednostek**.</span><span class="sxs-lookup"><span data-stu-id="714fa-121">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Unit conversions**.</span></span>
1. <span data-ttu-id="714fa-122">Zostanie otwarta strona **Konwersje jednostek**.</span><span class="sxs-lookup"><span data-stu-id="714fa-122">The **Unit conversions** page opens.</span></span> <span data-ttu-id="714fa-123">Wybierz jedną z następujących kart:</span><span class="sxs-lookup"><span data-stu-id="714fa-123">Select one of the following tabs:</span></span>

    - <span data-ttu-id="714fa-124">**Przeliczenia wewnątrz klasy** — tę kartę należy wybrać, aby dokonać konwersji między jednostkami należącymi do tej samej klasy jednostek.</span><span class="sxs-lookup"><span data-stu-id="714fa-124">**Intra-class conversions** – Select this tab to convert between units that belong to the same unit class.</span></span>
    - <span data-ttu-id="714fa-125">**Przeliczenia między klasami** — tę kartę należy wybrać, aby dokonać konwersji między jednostkami należącymi do różnych klas jednostek.</span><span class="sxs-lookup"><span data-stu-id="714fa-125">**Inter-class conversions** – Select this tab to convert between units that belong to different unit classes.</span></span>

1. <span data-ttu-id="714fa-126">Wybierz pozycję **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="714fa-126">Select **New** to add a new unit conversion.</span></span>
1. <span data-ttu-id="714fa-127">Ustaw pole **Utwórz konwersję dla** na jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="714fa-127">Set the **Create conversion for** field to one of the following values:</span></span>

    - <span data-ttu-id="714fa-128">**Produkt** — wybranie tej wartości umożliwi skonfigurowanie konwersji jednostek dla produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="714fa-128">**Product** – If you select this value, you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="714fa-129">Ta konwersja jednostek będzie używana jako rezerwowa dla wszystkich wariantów produktu, dla których nie zdefiniowano żadnej konwersji jednostek.</span><span class="sxs-lookup"><span data-stu-id="714fa-129">That unit conversion will be used as a fallback for all product variants that no unit conversion is defined for.</span></span>
    - <span data-ttu-id="714fa-130">**Wariant produktu** — wybranie tej wartości umożliwi skonfigurowanie konwersji jednostek dla określonego wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="714fa-130">**Product variant** – If you select this value, you can set up a unit conversion for a specific product variant.</span></span> <span data-ttu-id="714fa-131">Użyj pola **Wariant produktu**, aby wybrać wariant.</span><span class="sxs-lookup"><span data-stu-id="714fa-131">Use the **Product variant** field to select the variant.</span></span>

    <span data-ttu-id="714fa-132">![Dodawanie nowej konwersji jednostek](media/uom-new-conversion.png "Dodawanie nowej konwersji jednostek")</span><span class="sxs-lookup"><span data-stu-id="714fa-132">![Adding a new unit conversion](media/uom-new-conversion.png "Adding a new unit conversion")</span></span>

1. <span data-ttu-id="714fa-133">Aby skonfigurować konwersję jednostek, skorzystaj z dostępnych pól.</span><span class="sxs-lookup"><span data-stu-id="714fa-133">Use the other fields that are provided to set up your unit conversion.</span></span>
1. <span data-ttu-id="714fa-134">Wybierz przycisk **OK**, aby zapisać nową konwersję jednostek.</span><span class="sxs-lookup"><span data-stu-id="714fa-134">Select **OK** to save the new unit conversion.</span></span>

> [!TIP]
> <span data-ttu-id="714fa-135">Stronę **Konwersja jednostek** dla produktu lub wariantu produktu można otworzyć z dowolnej z następujących stron:</span><span class="sxs-lookup"><span data-stu-id="714fa-135">You can open the **Unit conversions** page for a product or a product variant from any of the following pages:</span></span>
> 
> - <span data-ttu-id="714fa-136">Szczegóły produktu</span><span class="sxs-lookup"><span data-stu-id="714fa-136">Product details</span></span>
> - <span data-ttu-id="714fa-137">Szczegóły zwolnionych produktów</span><span class="sxs-lookup"><span data-stu-id="714fa-137">Released products details</span></span>
> - <span data-ttu-id="714fa-138">Zwolnione warianty produktu</span><span class="sxs-lookup"><span data-stu-id="714fa-138">Released product variants</span></span>

## <a name="example-scenario"></a><span data-ttu-id="714fa-139">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="714fa-139">Example scenario</span></span>

<span data-ttu-id="714fa-140">W tym scenariuszu firma sprzedaje T-shirty w rozmiarach Mały, Średni, Duży i Bardzo duży.</span><span class="sxs-lookup"><span data-stu-id="714fa-140">In this scenario, a company sells T-shirts in sizes small, medium, large, and extra-large.</span></span> <span data-ttu-id="714fa-141">T-shirt jest definiowany jako produkt, a różne rozmiary są definiowane jako warianty tego produktu.</span><span class="sxs-lookup"><span data-stu-id="714fa-141">The T-shirt is defined as a product, and the different sizes are defined as variants of that product.</span></span> <span data-ttu-id="714fa-142">Koszulki są pakowane w pudełka.</span><span class="sxs-lookup"><span data-stu-id="714fa-142">The shirts are packed in boxes.</span></span> <span data-ttu-id="714fa-143">W przypadku rozmiarów Mały, Średni i Duży w każdym pudełku może znajdować się pięć koszulek.</span><span class="sxs-lookup"><span data-stu-id="714fa-143">For sizes small, medium, and large, there can be five shirts in each box.</span></span> <span data-ttu-id="714fa-144">Jednak w przypadku rozmiaru Bardzo duży w każdym pudełku mieszczą się tylko cztery koszulki.</span><span class="sxs-lookup"><span data-stu-id="714fa-144">However, for size extra-large, there is space for only four shirts in each box.</span></span>

<span data-ttu-id="714fa-145">Firma chce śledzić różne warianty w jednostce *Sztuki*, ale sprzedaje T-shirty w jednostkach *Pudełka*.</span><span class="sxs-lookup"><span data-stu-id="714fa-145">The company wants to track the different variants in the *Pieces* unit, but it's selling them in the *Boxes* unit.</span></span> <span data-ttu-id="714fa-146">W przypadku rozmiarów Mały, Średni i Duży konwersja między jednostką zapasów i jednostką sprzedaży to 1 pudełko = 5 sztuk.</span><span class="sxs-lookup"><span data-stu-id="714fa-146">For sizes small, medium, and large, the conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces.</span></span> <span data-ttu-id="714fa-147">W przypadku rozmiaru Bardzo duży konwersja to 1 pudełko = 4 sztuki.</span><span class="sxs-lookup"><span data-stu-id="714fa-147">For size extra-large, the conversion is 1 Box = 4 Pieces.</span></span>

1. <span data-ttu-id="714fa-148">Na stronie **Szczegóły zwolnionego produktu** produktu **T-Shirt** otwórz stronę **Konwersje jednostek**.</span><span class="sxs-lookup"><span data-stu-id="714fa-148">From the **Released product details** page for the **T-Shirt** product, open the **Unit conversions** page.</span></span>
1. <span data-ttu-id="714fa-149">Na stronie **Konwersje jednostek** ustaw następującą konwersję jednostek dla wariantu zwolnionego produktu **Bardzo duży**.</span><span class="sxs-lookup"><span data-stu-id="714fa-149">On the **Unit conversions** page, set up the following unit conversion for the **X-Large** released product variant.</span></span>

    | <span data-ttu-id="714fa-150">Pole</span><span class="sxs-lookup"><span data-stu-id="714fa-150">Field</span></span>                 | <span data-ttu-id="714fa-151">Ustawienie</span><span class="sxs-lookup"><span data-stu-id="714fa-151">Setting</span></span>                 |
    |-----------------------|-------------------------|
    | <span data-ttu-id="714fa-152">Utwórz konwersję dla</span><span class="sxs-lookup"><span data-stu-id="714fa-152">Create conversion for</span></span> | <span data-ttu-id="714fa-153">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="714fa-153">Product variant</span></span>         |
    | <span data-ttu-id="714fa-154">Wariant produktu</span><span class="sxs-lookup"><span data-stu-id="714fa-154">Product variant</span></span>       | <span data-ttu-id="714fa-155">T-Shirt : : X-Large : :</span><span class="sxs-lookup"><span data-stu-id="714fa-155">T-Shirt : : X-Large : :</span></span> |
    | <span data-ttu-id="714fa-156">Od jednostki</span><span class="sxs-lookup"><span data-stu-id="714fa-156">From unit</span></span>             | <span data-ttu-id="714fa-157">Pola</span><span class="sxs-lookup"><span data-stu-id="714fa-157">Boxes</span></span>                   |
    | <span data-ttu-id="714fa-158">Współczynnik</span><span class="sxs-lookup"><span data-stu-id="714fa-158">Factor</span></span>                | <span data-ttu-id="714fa-159">4</span><span class="sxs-lookup"><span data-stu-id="714fa-159">4</span></span>                       |
    | <span data-ttu-id="714fa-160">Do jednostki</span><span class="sxs-lookup"><span data-stu-id="714fa-160">To Unit</span></span>               | <span data-ttu-id="714fa-161">Sztuki</span><span class="sxs-lookup"><span data-stu-id="714fa-161">Pieces</span></span>                  |

1. <span data-ttu-id="714fa-162">Ponieważ warianty produktu **Mały**, **Średni** i **Duży** mają tę samą konwersję jednostki między jednostkami *Pudełko* i *Sztuki*, możesz zdefiniować następującą konwersję jednostek dla tych wariantów w produkcie głównym.</span><span class="sxs-lookup"><span data-stu-id="714fa-162">Because the **Small**, **Medium**, and **Large** product variants all have the same unit conversion between the *Box* and *Pieces* units, you can define the following unit conversion for them on the product master.</span></span>

    | <span data-ttu-id="714fa-163">Pole</span><span class="sxs-lookup"><span data-stu-id="714fa-163">Field</span></span>                 | <span data-ttu-id="714fa-164">Ustawienie</span><span class="sxs-lookup"><span data-stu-id="714fa-164">Setting</span></span> |
    |-----------------------|---------|
    | <span data-ttu-id="714fa-165">Utwórz konwersję dla</span><span class="sxs-lookup"><span data-stu-id="714fa-165">Create conversion for</span></span> | <span data-ttu-id="714fa-166">Produkt</span><span class="sxs-lookup"><span data-stu-id="714fa-166">Product</span></span> |
    | <span data-ttu-id="714fa-167">Produkt</span><span class="sxs-lookup"><span data-stu-id="714fa-167">Product</span></span>               | <span data-ttu-id="714fa-168">T-Shirt</span><span class="sxs-lookup"><span data-stu-id="714fa-168">T-Shirt</span></span> |
    | <span data-ttu-id="714fa-169">Od jednostki</span><span class="sxs-lookup"><span data-stu-id="714fa-169">From unit</span></span>             | <span data-ttu-id="714fa-170">Pola</span><span class="sxs-lookup"><span data-stu-id="714fa-170">Boxes</span></span>   |
    | <span data-ttu-id="714fa-171">Współczynnik</span><span class="sxs-lookup"><span data-stu-id="714fa-171">Factor</span></span>                | <span data-ttu-id="714fa-172">5</span><span class="sxs-lookup"><span data-stu-id="714fa-172">5</span></span>       |
    | <span data-ttu-id="714fa-173">Do jednostki</span><span class="sxs-lookup"><span data-stu-id="714fa-173">To Unit</span></span>               | <span data-ttu-id="714fa-174">Sztuki</span><span class="sxs-lookup"><span data-stu-id="714fa-174">Pieces</span></span>  |

## <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="714fa-175">Aktualizowanie konwersji jednostek przy użyciu programu Excel</span><span class="sxs-lookup"><span data-stu-id="714fa-175">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="714fa-176">Jeśli produkt ma wiele wariantów z różnymi konwersjami jednostek, dobrym pomysłem jest wyeksportowanie konwersji jednostek do skoroszytu programu Microsoft Excel, zaktualizowanie ich i ponowne opublikowanie w aplikacji Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="714fa-176">If a product has many product variants that have different unit conversions, it's a good idea to export the unit conversions to a Microsoft Excel workbook, update them, and then publish them back to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="714fa-177">Aby wyeksportować konwersje jednostek do programu Excel, na stronie **Konwersje jednostek** w okienku akcji wybierz pozycję **Otwórz w pakiecie Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="714fa-177">To export unit conversions to Excel, on the **Unit conversions** page, on the Action Pane, select **Open in Microsoft Office**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="714fa-178">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="714fa-178">Additional resources</span></span>

[<span data-ttu-id="714fa-179">Zarządzanie jednostką miary</span><span class="sxs-lookup"><span data-stu-id="714fa-179">Manage unit of measure</span></span>](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]