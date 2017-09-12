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
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fb11a470d98a9742749daaac3244a5bb0d3a689c
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="coverage-settings"></a><span data-ttu-id="4eb59-103">Ustawienia zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="4eb59-103">Coverage settings</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4eb59-104">Ustawienia zapotrzebowania są używane przez planowanie główne do obliczania zapotrzebowań na towary.</span><span class="sxs-lookup"><span data-stu-id="4eb59-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="4eb59-105">Ustawienia zapotrzebowania można określić na kilka sposobów:</span><span class="sxs-lookup"><span data-stu-id="4eb59-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="4eb59-106">Określ ustawienia zapotrzebowania dla grupy zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="4eb59-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="4eb59-107">Można utworzyć grupę zapotrzebowania zawierająca ustawienia dotyczące wszystkich produktów połączonych z tą grupą zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="4eb59-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="4eb59-108">Aby utworzyć grupę zapotrzebowania, kliknij kolejno opcje **Planowanie główne &gt; Ustawienia &gt; Zapotrzebowanie &gt; Grupy zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="4eb59-109">Grupę zapotrzebowania można połączyć z produktem.</span><span class="sxs-lookup"><span data-stu-id="4eb59-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="4eb59-110">Jeśli łącze jest właściwe dla oddziału, magazynu lub wymiaru produktu, użyj pola **grupa zapotrzebowania** na stronie **zapotrzebowanie na towar**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="4eb59-111">Jeśli łącze ma charakter ogólny, bez względu na wymiary produktu, należy użyć **grupy zapotrzebowania** na skróconej karcie **Plan** na stronie **Szczegóły produktu**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="4eb59-112">Jeśli grupa zapotrzebowania nie jest połączona z produktem, planowanie główne używa **ogólnej grupy zapotrzebowania** określonej na stronie **Parametry planowania głównego** jako domyślna.</span><span class="sxs-lookup"><span data-stu-id="4eb59-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="4eb59-113">Określ ustawienia zapotrzebowania dla produktu.</span><span class="sxs-lookup"><span data-stu-id="4eb59-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="4eb59-114">Ustawienia zapotrzebowania można utworzyć dla określonego produktu.</span><span class="sxs-lookup"><span data-stu-id="4eb59-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="4eb59-115">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty &gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="4eb59-116">Wybierz produkt, a następnie w **okienku akcji** na karcie **Plan** w obszarze **Grupa zapotrzebowania** kliknij przycisk **Zapotrzebowanie na towar**, aby otworzyć stronę **Zapotrzebowanie na towar**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="4eb59-117">Jeśli produkt jest połączony z grupą zapotrzebowania, ustawienia grupy zapotrzebowania można zastąpić, korzystając z pola **Zastąp**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="4eb59-118">Ustawienia zapotrzebowania na stronie**Zapotrzebowanie na towar** mają pierwszeństwo przed ustawieniami na stronie **Grupa zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="4eb59-119">Określ ustawienia zapotrzebowania dla produktu za pomocą kreatora.</span><span class="sxs-lookup"><span data-stu-id="4eb59-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="4eb59-120">Kreator prowadzi krok po kroku przez procedurę konfiguracji podstawowych parametrów zapotrzebowania na towar.</span><span class="sxs-lookup"><span data-stu-id="4eb59-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="4eb59-121">Na stronie **Zapotrzebowanie na towar** kliknij **Kreator**, aby otworzyć **Kreator zapotrzebowania na towar**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

-   <span data-ttu-id="4eb59-122">Określ ustawienia zapotrzebowania dla grupy wymiarów.</span><span class="sxs-lookup"><span data-stu-id="4eb59-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="4eb59-123">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Wspólne &gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-123">Click **Product information management &gt; Common &gt; Released products**.</span></span> <span data-ttu-id="4eb59-124">Na stronie **Szczegóły zwolnionego produktu** na karcie **Ogólne** w grupie **Administracja** kliknij łącze **Grupa wymiarów magazynowania**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-124">On the **Released product detail **page, on the **General** tab, in the **Administration** group, click the **Storage dimension group** link.</span></span> <span data-ttu-id="4eb59-125">Na stronie **Grupa wymiarów magazynowania** wybierz pole **Plan zapotrzebowania wg wymiaru**, aby utworzyć ustawienia zapotrzebowania dla wymiaru w grupie wymiarów magazynowania.</span><span class="sxs-lookup"><span data-stu-id="4eb59-125">On the **Storage dimension group** page, select the **Coverage plan by dimension** field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="4eb59-126">Wszystkie wymiary produktów, takie jak konfiguracja, kolor, rozmiar, styl, muszą mieć zaznaczone pole **Plan zapotrzebowania wg wymiaru**.</span><span class="sxs-lookup"><span data-stu-id="4eb59-126">All product dimensions, such as configuration, color, size, style, must have the **Coverage plan by dimension** field selected.</span></span>



<a name="see-also"></a><span data-ttu-id="4eb59-127">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4eb59-127">See also</span></span>
--------

[<span data-ttu-id="4eb59-128">Plany główne</span><span class="sxs-lookup"><span data-stu-id="4eb59-128">Master plans</span></span>](master-plans.md)




