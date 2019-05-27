---
title: Ustawienia zapotrzebowania
description: Ten temat zawiera informacje o ustawieniach zapotrzebowania, których planowanie główne używa do obliczania zapotrzebowania na towar.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538901"
---
# <a name="coverage-settings"></a><span data-ttu-id="57b11-103">Ustawienia zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="57b11-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57b11-104">Ustawienia zapotrzebowania są używane przez planowanie główne do obliczania zapotrzebowań na towary.</span><span class="sxs-lookup"><span data-stu-id="57b11-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="57b11-105">Ustawienia zapotrzebowania można określić na kilka sposobów:</span><span class="sxs-lookup"><span data-stu-id="57b11-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="57b11-106">Określ ustawienia zapotrzebowania dla grupy zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="57b11-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="57b11-107">Można utworzyć grupę zapotrzebowania zawierająca ustawienia dotyczące wszystkich produktów połączonych z tą grupą zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="57b11-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="57b11-108">Aby utworzyć grupę zapotrzebowania, kliknij kolejno opcje **Planowanie główne &gt; Ustawienia &gt; Zapotrzebowanie &gt; Grupy zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="57b11-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="57b11-109">Grupę zapotrzebowania można połączyć z produktem.</span><span class="sxs-lookup"><span data-stu-id="57b11-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="57b11-110">Jeśli łącze jest właściwe dla oddziału, magazynu lub wymiaru produktu, użyj pola **grupa zapotrzebowania** na stronie **zapotrzebowanie na towar**.</span><span class="sxs-lookup"><span data-stu-id="57b11-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="57b11-111">Jeśli łącze ma charakter ogólny, bez względu na wymiary produktu, należy użyć **grupy zapotrzebowania** na skróconej karcie **Plan** na stronie **Szczegóły produktu**.</span><span class="sxs-lookup"><span data-stu-id="57b11-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="57b11-112">Domyślnie, jeśli grupa zapotrzebowania nie jest połączona z produktem, planowanie główne używa ogólnej grupy zapotrzebowania określonej na stronie **Parametry planowania głównego**.</span><span class="sxs-lookup"><span data-stu-id="57b11-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="57b11-113">Określ ustawienia zapotrzebowania dla produktu.</span><span class="sxs-lookup"><span data-stu-id="57b11-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="57b11-114">Ustawienia zapotrzebowania można utworzyć dla określonego produktu.</span><span class="sxs-lookup"><span data-stu-id="57b11-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="57b11-115">Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="57b11-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="57b11-116">Wybierz produkt, a następnie w okienku akcji na karcie **Plan** w obszarze **Grupa zapotrzebowania** wybierz **Zapotrzebowanie na towar**, aby otworzyć stronę **Zapotrzebowanie na towar**.</span><span class="sxs-lookup"><span data-stu-id="57b11-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="57b11-117">Jeśli produkt jest połączony z grupą zapotrzebowania, ustawienia grupy zapotrzebowania można zastąpić, korzystając z pola **Zastąp**.</span><span class="sxs-lookup"><span data-stu-id="57b11-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="57b11-118">Ustawienia zapotrzebowania na stronie**Zapotrzebowanie na towar** mają pierwszeństwo przed ustawieniami na stronie **Grupa zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="57b11-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="57b11-119">Określ ustawienia zapotrzebowania dla produktu za pomocą kreatora.</span><span class="sxs-lookup"><span data-stu-id="57b11-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="57b11-120">Kreator przeprowadzi Cię krok po kroku przez proces konfigurowania podstawowych parametrów zapotrzebowania na towar.</span><span class="sxs-lookup"><span data-stu-id="57b11-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="57b11-121">Na stronie **Zapotrzebowanie na towar** w okienku akcji kliknij **Kreator**, aby otworzyć **Kreator zapotrzebowania na towar**.</span><span class="sxs-lookup"><span data-stu-id="57b11-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="57b11-122">Określ ustawienia zapotrzebowania dla grupy wymiarów.</span><span class="sxs-lookup"><span data-stu-id="57b11-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="57b11-123">Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="57b11-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="57b11-124">Na stronie **Szczegóły zwolnionego produktu** na skróconej karcie **Ogólne** w grupie **Administracja** kliknij łącze w polu **Grupa wymiarów magazynowania**.</span><span class="sxs-lookup"><span data-stu-id="57b11-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="57b11-125">Na stronie **Grupy wymiarów magazynowania** zaznacz pole **Plan zapotrzebowania wg wymiaru**, aby utworzyć ustawienia zapotrzebowania dla wymiaru w grupie wymiarów magazynowania.</span><span class="sxs-lookup"><span data-stu-id="57b11-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="57b11-126">Wszystkie wymiary produktów, takie jak konfiguracja, kolor, rozmiar, styl, muszą mieć zaznaczone pole **Plan zapotrzebowania wg wymiaru**.</span><span class="sxs-lookup"><span data-stu-id="57b11-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="57b11-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="57b11-127">Additional resources</span></span>

[<span data-ttu-id="57b11-128">Plany główne</span><span class="sxs-lookup"><span data-stu-id="57b11-128">Master plans</span></span>](master-plans.md)
