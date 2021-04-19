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
ms.openlocfilehash: 367b662a43b3c3255632f20aeb821b973b04d890
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833600"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="81755-103">Rozłożenie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="81755-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81755-104">Ten artykuł wyjaśnia scenariusz planowania głównego, który obejmuje rozłożenie wersji listy składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="81755-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="81755-105">Pomyślne rozłożenie popytu wersji listy składowej (BOM) tworzy popyt na każdy towar wiersza BOM w określonym dziale i prawdopodobnie w określonym magazynie.</span><span class="sxs-lookup"><span data-stu-id="81755-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="81755-106">BOM właściwy dla oddziału może mieć określony magazyn dla każdego wiersza.</span><span class="sxs-lookup"><span data-stu-id="81755-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="81755-107">Ponadto dla każdego wiersza BOM ustawienia wymiarów towaru określają, czy magazyn jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="81755-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="81755-108">Wynikowy popyt poszczególnych towarów wiersza BOM staje się z kolei punktem początkowym dodatkowego rozłożenia popytu.</span><span class="sxs-lookup"><span data-stu-id="81755-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="81755-109">Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="81755-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="81755-110">Wymiar oddziału jest obowiązkowy i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="81755-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="81755-111">Wymiar oddziału jest spójny.</span><span class="sxs-lookup"><span data-stu-id="81755-111">The site dimension is consistent.</span></span> <span data-ttu-id="81755-112">Oddział związany z popytem niższego poziomu jest identyczny z oddziałem z początkowej transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="81755-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="81755-113">Poniższy rysunek przedstawia sposób przetwarzania rozłożenia popytu planu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="81755-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Rozłożenie popytu przy użyciu wersji BOM](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="81755-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="81755-115">Additional resources</span></span>
--------

[<span data-ttu-id="81755-116">Ustalanie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="81755-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="81755-117">Omówienie planowania głównego i funkcjonalności wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="81755-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]