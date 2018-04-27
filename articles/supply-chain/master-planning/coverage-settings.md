---
title: Ustawienia zapotrzebowania
description: "Ustawienia zapotrzebowania są używane przez planowanie główne do obliczania zapotrzebowań na towary."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 591b1cd739bb3be61299f33f180ca7c264d21a35
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="coverage-settings"></a><span data-ttu-id="48b1b-103">Ustawienia zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="48b1b-103">Coverage settings</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="48b1b-104">Ustawienia zapotrzebowania są używane przez planowanie główne do obliczania zapotrzebowań na towary.</span><span class="sxs-lookup"><span data-stu-id="48b1b-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="48b1b-105">Ustawienia zapotrzebowania można określić na kilka sposobów:</span><span class="sxs-lookup"><span data-stu-id="48b1b-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="48b1b-106">Określ ustawienia zapotrzebowania dla grupy zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="48b1b-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="48b1b-107">Można utworzyć grupę zapotrzebowania zawierająca ustawienia dotyczące wszystkich produktów połączonych z tą grupą zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="48b1b-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="48b1b-108">Aby utworzyć grupę zapotrzebowania, kliknij kolejno opcje **Planowanie główne &gt; Ustawienia &gt; Zapotrzebowanie &gt; Grupy zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="48b1b-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="48b1b-109">Grupę zapotrzebowania można połączyć z produktem.</span><span class="sxs-lookup"><span data-stu-id="48b1b-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="48b1b-110">Jeśli łącze jest właściwe dla oddziału, magazynu lub wymiaru produktu, użyj pola **grupa zapotrzebowania** na stronie **zapotrzebowanie na towar**.</span><span class="sxs-lookup"><span data-stu-id="48b1b-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="48b1b-111">Jeśli łącze ma charakter ogólny, bez względu na wymiary produktu, należy użyć **grupy zapotrzebowania** na skróconej karcie **Plan** na stronie **Szczegóły produktu**.</span><span class="sxs-lookup"><span data-stu-id="48b1b-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="48b1b-112">Jeśli grupa zapotrzebowania nie jest połączona z produktem, planowanie główne używa **ogólnej grupy zapotrzebowania** określonej na stronie **Parametry planowania głównego** jako domyślna.</span><span class="sxs-lookup"><span data-stu-id="48b1b-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="48b1b-113">Określ ustawienia zapotrzebowania dla produktu.</span><span class="sxs-lookup"><span data-stu-id="48b1b-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="48b1b-114">Ustawienia zapotrzebowania można utworzyć dla określonego produktu.</span><span class="sxs-lookup"><span data-stu-id="48b1b-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="48b1b-115">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty &gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="48b1b-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="48b1b-116">Wybierz produkt, a następnie w **okienku akcji** na karcie **Plan** w obszarze **Grupa zapotrzebowania** kliknij przycisk **Zapotrzebowanie na towar**, aby otworzyć stronę **Zapotrzebowanie na towar**.</span><span class="sxs-lookup"><span data-stu-id="48b1b-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="48b1b-117">Jeśli produkt jest połączony z grupą zapotrzebowania, ustawienia grupy zapotrzebowania można zastąpić, korzystając z pola **Zastąp**.</span><span class="sxs-lookup"><span data-stu-id="48b1b-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="48b1b-118">Ustawienia zapotrzebowania na stronie**Zapotrzebowanie na towar** mają pierwszeństwo przed ustawieniami na stronie **Grupa zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="48b1b-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="48b1b-119">Określ ustawienia zapotrzebowania dla produktu za pomocą kreatora.</span><span class="sxs-lookup"><span data-stu-id="48b1b-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="48b1b-120">Kreator prowadzi krok po kroku przez procedurę konfiguracji podstawowych parametrów zapotrzebowania na towar.</span><span class="sxs-lookup"><span data-stu-id="48b1b-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="48b1b-121">Na stronie **Zapotrzebowanie na towar** kliknij **Kreator**, aby otworzyć **Kreator zapotrzebowania na towar**.</span><span class="sxs-lookup"><span data-stu-id="48b1b-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

- <span data-ttu-id="48b1b-122">Określ ustawienia zapotrzebowania dla grupy wymiarów.</span><span class="sxs-lookup"><span data-stu-id="48b1b-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="48b1b-123">Kliknij kolejno opcje <strong>Zarządzanie informacjami o produktach &gt; Wspólne &gt; Zwolnione produkty</strong>.</span><span class="sxs-lookup"><span data-stu-id="48b1b-123">Click <strong>Product information management &gt; Common &gt; Released products</strong>.</span></span> <span data-ttu-id="48b1b-124">Na stronie <strong>Szczegóły zwolnionego produktu** na karcie **Ogólne</strong> w grupie <strong>Administracja</strong> kliknij łącze <strong>Grupa wymiarów magazynowania</strong>.</span><span class="sxs-lookup"><span data-stu-id="48b1b-124">On the <strong>Released product detail **page, on the **General</strong> tab, in the <strong>Administration</strong> group, click the <strong>Storage dimension group</strong> link.</span></span> <span data-ttu-id="48b1b-125">Na stronie <strong>Grupa wymiarów magazynowania</strong> wybierz pole <strong>Plan zapotrzebowania wg wymiaru</strong>, aby utworzyć ustawienia zapotrzebowania dla wymiaru w grupie wymiarów magazynowania.</span><span class="sxs-lookup"><span data-stu-id="48b1b-125">On the <strong>Storage dimension group</strong> page, select the <strong>Coverage plan by dimension</strong> field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="48b1b-126">Wszystkie wymiary produktów, takie jak konfiguracja, kolor, rozmiar, styl, muszą mieć zaznaczone pole <strong>Plan zapotrzebowania wg wymiaru</strong>.</span><span class="sxs-lookup"><span data-stu-id="48b1b-126">All product dimensions, such as configuration, color, size, style, must have the <strong>Coverage plan by dimension</strong> field selected.</span></span>



<a name="see-also"></a><span data-ttu-id="48b1b-127">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="48b1b-127">See also</span></span>
--------

[<span data-ttu-id="48b1b-128">Plany główne</span><span class="sxs-lookup"><span data-stu-id="48b1b-128">Master plans</span></span>](master-plans.md)




