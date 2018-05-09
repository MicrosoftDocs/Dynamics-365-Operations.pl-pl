---
title: "Planowanie główne a funkcjonalność wielooddziałowości"
description: "Planowanie główne uwzględnia ustawienia wymiarów magazynowych „oddział” i „magazyn”."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 23932351cc9f164a341e83a7b84fc7c76ab331f4
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="master-planning-and-multisite-functionality"></a><span data-ttu-id="84b03-103">Planowanie główne a funkcjonalność wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="84b03-103">Master planning and multisite functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84b03-104">Planowanie główne uwzględnia ustawienia wymiarów magazynowych „oddział” i „magazyn”.</span><span class="sxs-lookup"><span data-stu-id="84b03-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="84b03-105">Wymiar oddziału jest obowiązkowy. Można też ustawić wymiar magazynu jako obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="84b03-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="84b03-106">Jeśli dany wymiar jest wymagany, jego wartość należy wprowadzać we wszystkich transakcjach magazynowych.</span><span class="sxs-lookup"><span data-stu-id="84b03-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="84b03-107">Dlatego podczas planowania głównego jest znany oddział i magazyn, które będą realizować pierwsze zamówienie.</span><span class="sxs-lookup"><span data-stu-id="84b03-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="84b03-108">Wymiary oddziału także muszą być zgodne, aby podczas dużego wzrostu liczby zamówień niższego poziomu nie zmieniła się wartość oddziału.</span><span class="sxs-lookup"><span data-stu-id="84b03-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="84b03-109">Jeśli magazyn nie zostanie ustawiony jako wymagany, może nie zostać rozpoznany przy pierwszym zamówieniu.</span><span class="sxs-lookup"><span data-stu-id="84b03-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="84b03-110">Aparat planowania, na podstawie zdefiniowanych ustawień towaru, poszczególnych magazynów i szczegółów wiersza zamówienia musi określać, który magazyn ma być użyty.</span><span class="sxs-lookup"><span data-stu-id="84b03-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="84b03-111">Poniższe tematy zawierają opisy działania aparatu planowania podczas określania magazynu, który ma być użyty, w przypadku różnych ustawień.</span><span class="sxs-lookup"><span data-stu-id="84b03-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="84b03-112">Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="84b03-112">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="84b03-113">Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="84b03-113">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="84b03-114">Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="84b03-114">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="84b03-115">Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="84b03-115">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="84b03-116">Planowanie główne — jak określa się wersję BOM</span><span class="sxs-lookup"><span data-stu-id="84b03-116">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




