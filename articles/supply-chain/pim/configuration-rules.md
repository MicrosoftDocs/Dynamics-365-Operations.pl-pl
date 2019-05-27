---
title: Reguły konfiguracji
description: Ten artykuł zawiera ogólne informacje o regułach konfiguracji. Reguły konfiguracji definiują relacje między towarami na liście składowej (BOM) dla produktów wykorzystujących technologię konfiguracji opartej na wymiarach.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 13f37cb4e472e91862e963a4952adcf61e6adcea
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555938"
---
# <a name="configuration-rules"></a><span data-ttu-id="51ee3-104">Reguły konfiguracji</span><span class="sxs-lookup"><span data-stu-id="51ee3-104">Configuration rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51ee3-105">Ten artykuł zawiera ogólne informacje o regułach konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="51ee3-105">This article provides general information about configuration rules.</span></span> <span data-ttu-id="51ee3-106">Reguły konfiguracji definiują relacje między towarami na liście składowej (BOM) dla produktów wykorzystujących technologię konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="51ee3-106">Configuration rules define relationships between items in a bill of materials (BOM) for products that use the dimension-based configuration technology.</span></span>

<span data-ttu-id="51ee3-107">Reguły konfiguracji są dostępne podczas definiowania modeli konfiguracji opartych na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="51ee3-107">Configuration rules are available when you define dimension-based configuration models.</span></span> <span data-ttu-id="51ee3-108">Reguły konfiguracji są używane do wymuszania albo zakazywania kombinacji określonych towarów na liście składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="51ee3-108">Configuration rules are used to either enforce or prohibit specific item combinations in a bill of materials (BOM).</span></span> <span data-ttu-id="51ee3-109">Po utworzeniu BOM i przypisaniu odpowiednich towarów do odpowiednich grup konfiguracji, można zdefiniować jedną lub więcej reguł konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="51ee3-109">After a BOM has been created and the relevant items have been assigned to their respective configuration groups, one or more configuration rules can be defined.</span></span> <span data-ttu-id="51ee3-110">Jeżeli dwa towary przynależą do siebie, można je ze sobą połączyć za pomocą operatora **Zaznacz**.</span><span class="sxs-lookup"><span data-stu-id="51ee3-110">If two items belong together, the **Select** operator is used to ensure inclusion.</span></span> <span data-ttu-id="51ee3-111">Jeśli dwa towary wzajemnie się wykluczają, można je od siebie oddzielić za pomocą operatora **Odznacz**.</span><span class="sxs-lookup"><span data-stu-id="51ee3-111">If two items are mutually exclusive, the **Deselect** operator is used to ensure exclusion.</span></span>  

<span data-ttu-id="51ee3-112">**Uwaga:** ta informacja dotyczy tylko produktów głównych, które używają technologii konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="51ee3-112">**Note:** This information applies only to product masters that use the dimension-based configuration technology.</span></span>  

<span data-ttu-id="51ee3-113">Istniejące konfiguracje nie są objęte kolejnymi zmianami reguł konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="51ee3-113">Existing configurations aren't affected by subsequent changes to the configuration rules.</span></span> <span data-ttu-id="51ee3-114">Jednak przed zdefiniowaniem nowej konfiguracji konieczne jest określenie reguł lub ich sprawdzenie, jeśli istnieje podejrzenie o zmianie reguł.</span><span class="sxs-lookup"><span data-stu-id="51ee3-114">However, it's important that you set the rules before you define a new configuration, and that you check the rules if you think they have been changed.</span></span>  

<span data-ttu-id="51ee3-115">**Uwaga:** dla metody **Zaznacz** pochodna grupa konfiguracji, numer towaru i konfiguracja wybierane są automatycznie.</span><span class="sxs-lookup"><span data-stu-id="51ee3-115">**Note:** For the **Select** method, the derived configuration group, item number, and configuration are automatically selected.</span></span> <span data-ttu-id="51ee3-116">Dla metody **Odznacz** pochodna grupa konfiguracji, numer towaru i konfiguracja nie może zostać wybrana.</span><span class="sxs-lookup"><span data-stu-id="51ee3-116">For the **Deselect** method, the derived configuration group, item number, and configuration can't be selected.</span></span>

<a name="additional-resources"></a><span data-ttu-id="51ee3-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="51ee3-117">Additional resources</span></span>
--------

[<span data-ttu-id="51ee3-118">Konfiguracja produktu oparta na wymiarach</span><span class="sxs-lookup"><span data-stu-id="51ee3-118">Dimension-based product configuration</span></span>](dimension-based-product-configuration.md)



