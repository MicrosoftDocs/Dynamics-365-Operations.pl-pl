---
title: Omówienie planowania głównego i funkcjonalności wielooddziałowości
description: Planowanie główne uwzględnia ustawienia wymiarów magazynowych „oddział” i „magazyn”.
author: roxanadiaconu
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da8db87f44c974b3fee8e249e318669ca8e9f2b8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220831"
---
# <a name="master-planning-and-multisite-functionality-overview"></a><span data-ttu-id="5b015-103">Omówienie planowania głównego i funkcjonalności wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="5b015-103">Master planning and multisite functionality overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b015-104">Planowanie główne uwzględnia ustawienia wymiarów magazynowych „oddział” i „magazyn”.</span><span class="sxs-lookup"><span data-stu-id="5b015-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="5b015-105">Wymiar oddziału jest obowiązkowy. Można też ustawić wymiar magazynu jako obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="5b015-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="5b015-106">Jeśli dany wymiar jest wymagany, jego wartość należy wprowadzać we wszystkich transakcjach magazynowych.</span><span class="sxs-lookup"><span data-stu-id="5b015-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="5b015-107">Dlatego podczas planowania głównego jest znany oddział i magazyn, które będą realizować pierwsze zamówienie.</span><span class="sxs-lookup"><span data-stu-id="5b015-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="5b015-108">Wymiary oddziału także muszą być zgodne, aby podczas dużego wzrostu liczby zamówień niższego poziomu nie zmieniła się wartość oddziału.</span><span class="sxs-lookup"><span data-stu-id="5b015-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="5b015-109">Jeśli magazyn nie zostanie ustawiony jako wymagany, może nie zostać rozpoznany przy pierwszym zamówieniu.</span><span class="sxs-lookup"><span data-stu-id="5b015-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="5b015-110">Aparat planowania, na podstawie zdefiniowanych ustawień towaru, poszczególnych magazynów i szczegółów wiersza zamówienia musi określać, który magazyn ma być użyty.</span><span class="sxs-lookup"><span data-stu-id="5b015-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="5b015-111">Poniższe tematy zawierają opisy działania aparatu planowania podczas określania magazynu, który ma być użyty, w przypadku różnych ustawień.</span><span class="sxs-lookup"><span data-stu-id="5b015-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="5b015-112">Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="5b015-112">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="5b015-113">Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="5b015-113">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="5b015-114">Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="5b015-114">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="5b015-115">Planowanie główne dla zapotrzebowania oddziału, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="5b015-115">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="5b015-116">Ustalanie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="5b015-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]