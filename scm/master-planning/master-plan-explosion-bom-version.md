---
title: "Rozłożenie wersji BOM"
description: "Ten artykuł wyjaśnia scenariusz planowania głównego, który obejmuje rozłożenie wersji listy składowej (BOM)."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f8c633e09103c45aff5614270a94a3bfe4fc5e20
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="2ac68-103">Rozłożenie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="2ac68-103">Explosion of a BOM version</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2ac68-104">Ten artykuł wyjaśnia scenariusz planowania głównego, który obejmuje rozłożenie wersji listy składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="2ac68-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="2ac68-105">Pomyślne rozłożenie popytu wersji listy składowej (BOM) tworzy popyt na każdy towar wiersza BOM w określonym dziale i prawdopodobnie w określonym magazynie.</span><span class="sxs-lookup"><span data-stu-id="2ac68-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="2ac68-106">BOM właściwy dla oddziału może mieć określony magazyn dla każdego wiersza.</span><span class="sxs-lookup"><span data-stu-id="2ac68-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="2ac68-107">Ponadto dla każdego wiersza BOM ustawienia wymiarów towaru określają, czy magazyn jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="2ac68-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="2ac68-108">Wynikowy popyt poszczególnych towarów wiersza BOM staje się z kolei punktem początkowym dodatkowego rozłożenia popytu.</span><span class="sxs-lookup"><span data-stu-id="2ac68-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="2ac68-109">Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="2ac68-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="2ac68-110">Wymiar oddziału jest obowiązkowy i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="2ac68-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="2ac68-111">Wymiar oddziału jest spójny.</span><span class="sxs-lookup"><span data-stu-id="2ac68-111">The site dimension is consistent.</span></span> <span data-ttu-id="2ac68-112">Oddział związany z popytem niższego poziomu jest identyczny z oddziałem z początkowej transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="2ac68-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="2ac68-113">Poniższy rysunek przedstawia sposób przetwarzania rozłożenia popytu planu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="2ac68-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Rozłożenie popytu przy użyciu wersji BOM](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a><span data-ttu-id="2ac68-115">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="2ac68-115">See also</span></span>
--------

[<span data-ttu-id="2ac68-116">Planowanie główne — jak określa się wersję BOM</span><span class="sxs-lookup"><span data-stu-id="2ac68-116">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="2ac68-117">Planowanie główne a funkcjonalność wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="2ac68-117">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)




