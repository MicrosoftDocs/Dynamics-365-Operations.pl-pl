---
title: Omówienie środowiska wersji zapoznawczej usługi Commerce
description: Ten temat zawiera omówienie środowiska wersji zapoznawczej usługi Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 901583afde4739be5313fa129ff0e52f11326881
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906077"
---
# <a name="commerce-preview-environment-overview"></a><span data-ttu-id="cb7d3-103">Omówienie środowiska wersji zapoznawczej usługi Commerce</span><span class="sxs-lookup"><span data-stu-id="cb7d3-103">Commerce preview environment overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="cb7d3-104">Ten temat zawiera omówienie środowiska wersji zapoznawczej usługi Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cb7d3-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="overview"></a><span data-ttu-id="cb7d3-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="cb7d3-105">Overview</span></span>

<span data-ttu-id="cb7d3-106">Środowisko wersji zapoznawczej usługi Commerce to opcjonalne kompleksowe środowisko wersji zapoznawczej usługi Dynamics 365 Commerce, które umożliwia potencjalnym klientom wypróbowanie produktu Commerce przed jego wydaniem jako ogólnie dostępnego.</span><span class="sxs-lookup"><span data-stu-id="cb7d3-106">The Commerce preview environment is an optional end-to-end preview environment of Dynamics 365 Commerce that lets potential customers try out the Commerce product before its general release to the public.</span></span>

<span data-ttu-id="cb7d3-107">Oprócz niektórych drobnych ograniczeń, które nie wpływają na funkcje lub funkcjonalność, środowisko wersji zapoznawczej usługi Commerce zapewnia kompletne środowisko handlowe i może być używane przez klientów oraz partnerów wdrożeniowych do oceny produktu, dostarczania opinii i analizy dopasowania/luk.</span><span class="sxs-lookup"><span data-stu-id="cb7d3-107">Aside from some minor limitations that don't affect features or functionality, the Commerce preview environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-preview-environment"></a><span data-ttu-id="cb7d3-108">Ograniczenia środowiska wersji zapoznawczej usługi Commerce</span><span class="sxs-lookup"><span data-stu-id="cb7d3-108">Limitations of the Commerce preview environment</span></span>

<span data-ttu-id="cb7d3-109">Chociaż środowisko wersji zapoznawczej usługi Commerce zawiera pełny zestaw funkcji i funkcjonalności platformy handlowej, istnieją pewne drobne ograniczenia:</span><span class="sxs-lookup"><span data-stu-id="cb7d3-109">Although the Commerce preview environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="cb7d3-110">Chociaż środowisko wersji zapoznawczej usługi Commerce nie ma żadnych ograniczeń geograficznych, składniki środowiska, takie jak aplikacje Retail Cloud Scale Unit (RCSU) i e-Commerce, mogą być aprowizowane tylko w Stanach Zjednoczonych.</span><span class="sxs-lookup"><span data-stu-id="cb7d3-110">Although the Commerce preview environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, can be provisioned only in the United States.</span></span>
- <span data-ttu-id="cb7d3-111">Użycie środowiska wersji zapoznawczej usługi Commerce jest ograniczone do 30 od daty aprowizacji aplikacji e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="cb7d3-111">Use of the Commerce preview environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="cb7d3-112">Środowisko wersji zapoznawczej usługi Commerce można pomyślnie wdrożyć i zainicjować tylko w środowisku, które używa topologii pokazów, gdzie wszystkie składniki środowiska są wdrażane w jednej maszynie wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="cb7d3-112">The Commerce preview environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed in a single virtual machine (VM).</span></span> <span data-ttu-id="cb7d3-113">Głównym ograniczeniem tej topologii maszyny wirtualnej OneBox jest liczba współbieżnych użytkowników, które środowisko wersji zapoznawczej może obsługiwać.</span><span class="sxs-lookup"><span data-stu-id="cb7d3-113">The main limitation of this OneBox VM topology is the number of concurrent users that the preview environment can support.</span></span>
- <span data-ttu-id="cb7d3-114">Środowisko wersji zapoznawczej usługi Commerce może być oceniane tylko do momentu rozpoczęcia ogólnej dostępności produktu Commerce.</span><span class="sxs-lookup"><span data-stu-id="cb7d3-114">The Commerce preview environment can be evaluated only until the general availability (GA) of the Commerce product.</span></span> <span data-ttu-id="cb7d3-115">Nowe środowiska pokazów będą dostępne po rozpoczęciu ogólnej dostępności.</span><span class="sxs-lookup"><span data-stu-id="cb7d3-115">New demo environments will be available after GA.</span></span>

## <a name="get-started"></a><span data-ttu-id="cb7d3-116">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="cb7d3-116">Get started</span></span>

<span data-ttu-id="cb7d3-117">Aby aprowizować środowisko wersji zapoznawczej usługi Commerce, zobacz [Aprowizowanie środowiska wersji zapoznawczej usługi Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="cb7d3-117">To provision the Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb7d3-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cb7d3-118">Additional resources</span></span>

[<span data-ttu-id="cb7d3-119">Aprowizowanie środowiska wersji zapoznawczej usługi Commerce</span><span class="sxs-lookup"><span data-stu-id="cb7d3-119">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="cb7d3-120">Konfigurowanie środowiska wersji zapoznawczej usługi Commerce</span><span class="sxs-lookup"><span data-stu-id="cb7d3-120">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="cb7d3-121">Konfigurowanie funkcji opcjonalnych środowiska wersji zapoznawczej usługi Commerce</span><span class="sxs-lookup"><span data-stu-id="cb7d3-121">Configure optional features for a Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="cb7d3-122">Często zadawane pytania dotyczące środowiska wersji zapoznawczej usługi Commerce</span><span class="sxs-lookup"><span data-stu-id="cb7d3-122">Commerce preview environment FAQ</span></span>](cpe-faq.md)
