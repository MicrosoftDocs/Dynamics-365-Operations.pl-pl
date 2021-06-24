---
title: Rozłożenie wersji BOM
description: Ten artykuł wyjaśnia scenariusz planowania głównego, który obejmuje rozłożenie wersji listy składowej (BOM).
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 17e5d8638dc02d92a0c67364790353833551250f
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187417"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="51e13-103">Rozłożenie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="51e13-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51e13-104">Ten artykuł wyjaśnia scenariusz planowania głównego, który obejmuje rozłożenie wersji listy składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="51e13-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="51e13-105">Pomyślne rozłożenie popytu wersji listy składowej (BOM) tworzy popyt na każdy towar wiersza BOM w określonym dziale i prawdopodobnie w określonym magazynie.</span><span class="sxs-lookup"><span data-stu-id="51e13-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="51e13-106">BOM właściwy dla oddziału może mieć określony magazyn dla każdego wiersza.</span><span class="sxs-lookup"><span data-stu-id="51e13-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="51e13-107">Ponadto dla każdego wiersza BOM ustawienia wymiarów towaru określają, czy magazyn jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="51e13-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="51e13-108">Wynikowy popyt poszczególnych towarów wiersza BOM staje się z kolei punktem początkowym dodatkowego rozłożenia popytu.</span><span class="sxs-lookup"><span data-stu-id="51e13-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="51e13-109">Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="51e13-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="51e13-110">Wymiar oddziału jest obowiązkowy i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="51e13-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="51e13-111">Wymiar oddziału jest spójny.</span><span class="sxs-lookup"><span data-stu-id="51e13-111">The site dimension is consistent.</span></span> <span data-ttu-id="51e13-112">Oddział związany z popytem niższego poziomu jest identyczny z oddziałem z początkowej transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="51e13-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="51e13-113">Poniższy rysunek przedstawia sposób przetwarzania rozłożenia popytu planu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="51e13-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Rozłożenie popytu przy użyciu wersji BOM](./media/multisitedemandexplosionscenariousingbomversion.gif)

## <a name="additional-resources"></a><span data-ttu-id="51e13-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="51e13-115">Additional resources</span></span>

[<span data-ttu-id="51e13-116">Ustalanie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="51e13-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="51e13-117">Omówienie planowania głównego i funkcjonalności wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="51e13-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]