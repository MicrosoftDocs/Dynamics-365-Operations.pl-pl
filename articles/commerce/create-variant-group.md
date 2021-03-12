---
title: Utwórz grupę wariantów
description: W tym temacie opisano sposób tworzenia rozmiaru, stylu lub grupy wariantów kolorów dla produktu w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e19d9a2549fa9957126592f3db7e468147997261
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965160"
---
# <a name="create-a-variant-group"></a><span data-ttu-id="a40c0-103">Utwórz grupę wariantów</span><span class="sxs-lookup"><span data-stu-id="a40c0-103">Create a variant group</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a40c0-104">W tym temacie opisano sposób tworzenia rozmiaru, stylu lub grupy wariantów kolorów dla produktu w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a40c0-104">This topic describes how to create a size, style, or color variant group for a product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a40c0-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a40c0-105">Overview</span></span>

<span data-ttu-id="a40c0-106">Dynamics 365 Commerce obsługuje wiele wariantów produktów.</span><span class="sxs-lookup"><span data-stu-id="a40c0-106">Dynamics 365 Commerce supports multiple variants for products.</span></span> <span data-ttu-id="a40c0-107">Doskonale nadaje się do konfigurowania grup wariantów dla różnych kategorii produktów.</span><span class="sxs-lookup"><span data-stu-id="a40c0-107">It is ideal to set up variant groups for different product categories.</span></span> <span data-ttu-id="a40c0-108">Można na przykład utworzyć grupę rozmiarów dla koszulki o rozmiarach bardzo małych, małych, średnich, dużych i bardzo dużych, lub utworzyć grupę kolorów, tak aby obejmowała wszystkie dostępne kolory produktu.</span><span class="sxs-lookup"><span data-stu-id="a40c0-108">For example, a size group can be created for t-shirts with sizes extra small, small, medium, large, and extra large, or a color group could be created to include all available colors of a product.</span></span> <span data-ttu-id="a40c0-109">Przed dodaniem produktów należy dodać grupy wariantów.</span><span class="sxs-lookup"><span data-stu-id="a40c0-109">Variant groups should be added before products are added.</span></span>

<span data-ttu-id="a40c0-110">W tym temacie zostanie utworzona i skonfigurowana grupa rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="a40c0-110">In this topic, a size group will be created and configured.</span></span> <span data-ttu-id="a40c0-111">Podobne procedury mogą służyć do dodawania i konfigurowania grup stylów oraz grup kolorów.</span><span class="sxs-lookup"><span data-stu-id="a40c0-111">Similar procedures can be used for adding and configuring style groups and color groups.</span></span>

## <a name="create-a-size-group"></a><span data-ttu-id="a40c0-112">Tworzenie grupy rozmiarów</span><span class="sxs-lookup"><span data-stu-id="a40c0-112">Create a size group</span></span>

<span data-ttu-id="a40c0-113">Aby utworzyć grupę rozmiarów, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="a40c0-113">To create a size group, follow these steps.</span></span>
 
1. <span data-ttu-id="a40c0-114">W okienku nawigacji przejdź do **Moduły \> Retail i commerce \> Produkty i kategorie \> Grupy wariantów \> Grupy rozmiarów**.</span><span class="sxs-lookup"><span data-stu-id="a40c0-114">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**.</span></span>
1. <span data-ttu-id="a40c0-115">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a40c0-115">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a40c0-116">W polu **Grupa rozmiarów** wpisz unikatową nazwę grupy rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="a40c0-116">In the **Size group** box, enter a name for the size group.</span></span>
1. <span data-ttu-id="a40c0-117">W razie potrzeby w polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="a40c0-117">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="a40c0-118">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a40c0-118">On the action pane, select **Save**.</span></span>

## <a name="add-attributes-to-the-size-group"></a><span data-ttu-id="a40c0-119">Dodaj atrybuty do grupy rozmiarów</span><span class="sxs-lookup"><span data-stu-id="a40c0-119">Add attributes to the size group</span></span>

<span data-ttu-id="a40c0-120">Aby dodać atrybuty do grupy rozmiarów, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a40c0-120">To add attributes to a size group, follow these steps.</span></span>

1. <span data-ttu-id="a40c0-121">W okienku nawigacji przejdź do **Moduły \> Retail i commerce \> Produkty i kategorie \> Grupy wariantów \> Grupy rozmiarów**</span><span class="sxs-lookup"><span data-stu-id="a40c0-121">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**</span></span>
1. <span data-ttu-id="a40c0-122">W okienku nawigacji kategorii wybierz grupę rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="a40c0-122">In the navigation pane, select a size group.</span></span>
1. <span data-ttu-id="a40c0-123">W obszarze **Wiersze grupy rozmiarów** wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a40c0-123">Under **Size group lines**, select **Add**.</span></span>
1. <span data-ttu-id="a40c0-124">W polu **Grupa rozmiarów** wpisz ciąg reprezentujący rozmiar (na przykład „XL”).</span><span class="sxs-lookup"><span data-stu-id="a40c0-124">In the **Size** box, enter a string representing the size (for example, "XL").</span></span>
1. <span data-ttu-id="a40c0-125">W polu **Nazwa rozmiaru** wprowadź nazwę rozmiaru (na przykład „ekstra duże”).</span><span class="sxs-lookup"><span data-stu-id="a40c0-125">In the **Size name** box, enter a name for the size (for example, "Extra Large").</span></span>
1. <span data-ttu-id="a40c0-126">W polu **Waga uzupełnienia** wprowadź liczbę reprezentującą wagę uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="a40c0-126">In the **Replenishment weight** box, enter a number representing the replenishment weight.</span></span>
1. <span data-ttu-id="a40c0-127">W polu **numer w kodzie kreskowym** wprowadź liczbę reprezentującą kod kreskowy.</span><span class="sxs-lookup"><span data-stu-id="a40c0-127">In the **Number in bar code** box, enter a number representing the bar code.</span></span>
1. <span data-ttu-id="a40c0-128">W polu **Kolejność wyświetlania** wprowadź numer kolejności wyświetlania.</span><span class="sxs-lookup"><span data-stu-id="a40c0-128">In the **Display order** box, enter a number representing the display order.</span></span>
1. <span data-ttu-id="a40c0-129">Po zakończeniu dodawania rozmiarów wybierz opcję **Zapisz** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="a40c0-129">When finished adding sizes, select **Save** on the action pane.</span></span>

<span data-ttu-id="a40c0-130">Poniższy obraz przedstawia przykład konfiguracji przypisania grupy rozmiary dla „rozmiary koszulek codziennych”.</span><span class="sxs-lookup"><span data-stu-id="a40c0-130">The following image shows an example of a size group for "casual shirt sizes".</span></span>

![Tworzenie grupy rozmiarów](media/create-variant-group.png)

## <a name="additional-resources"></a><span data-ttu-id="a40c0-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a40c0-132">Additional resources</span></span>

[<span data-ttu-id="a40c0-133">Omówienie informacji o produktach</span><span class="sxs-lookup"><span data-stu-id="a40c0-133">Product information overview</span></span>](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="a40c0-134">Konfigurowanie produktów sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="a40c0-134">Set up retail products</span></span>](set-up-retail-products.md)

[<span data-ttu-id="a40c0-135">Wymiary produktu</span><span class="sxs-lookup"><span data-stu-id="a40c0-135">Product dimensions</span></span>](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)
