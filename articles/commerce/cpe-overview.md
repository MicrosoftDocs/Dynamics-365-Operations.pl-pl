---
title: Omówienie środowiska oceny rozwiązania Dynamics 365 Commerce
description: Ten temat zawiera omówienie środowiska oceny usługi Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c890d7c49b6607ab0cbad536bbf8a3649465a7c1
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193499"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a><span data-ttu-id="cf547-103">Omówienie środowiska oceny rozwiązania Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="cf547-103">Dynamics 365 Commerce evaluation environment overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cf547-104">Ten temat zawiera omówienie środowiska oceny usługi Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cf547-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

> [!NOTE]
> <span data-ttu-id="cf547-105">Środowiska testowe w handlu są zazwyczaj niedostępne i są przyznawane partnerom i odbiorcom na żądanie.</span><span class="sxs-lookup"><span data-stu-id="cf547-105">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="cf547-106">Aby uzyskać więcej informacji, skontaktuj się z partnerem firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf547-106">For more information, reach out to your Microsoft partner contact.</span></span>

<span data-ttu-id="cf547-107">Środowisko oceny usługi Commerce to opcjonalne kompleksowe środowisko wersji zapoznawczej usługi Dynamics 365 Commerce, które umożliwia partnerom i potencjalnym klientom wypróbowanie produktu Commerce.</span><span class="sxs-lookup"><span data-stu-id="cf547-107">The Commerce evaluation environment is an optional end-to-end environment of Dynamics 365 Commerce that lets partners and potential customers try out the Commerce product.</span></span>

<span data-ttu-id="cf547-108">Częściowo wstępnie skonfigurowane środowiska oceny w celu zmniejszenia wymaganych kroków po wykonaniu wstępnej obsługi administracyjnej.</span><span class="sxs-lookup"><span data-stu-id="cf547-108">Evaluation environments are partially preconfigured to reduce the required post-provisioning steps.</span></span>

<span data-ttu-id="cf547-109">Oprócz niektórych drobnych ograniczeń, które nie wpływają na funkcje lub funkcjonalność, środowisko oceny usługi Commerce zapewnia kompletne środowisko handlowe i może być używane przez klientów oraz partnerów wdrożeniowych do oceny produktu, dostarczania opinii i analizy dopasowania/luk.</span><span class="sxs-lookup"><span data-stu-id="cf547-109">Aside from some minor limitations that don't affect features or functionality, the Commerce evaluation environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-evaluation-environment"></a><span data-ttu-id="cf547-110">Ograniczenia środowiska oceny usługi Commerce</span><span class="sxs-lookup"><span data-stu-id="cf547-110">Limitations of the Commerce evaluation environment</span></span>

<span data-ttu-id="cf547-111">Chociaż środowisko oceny usługi Commerce zawiera pełny zestaw funkcji i funkcjonalności platformy handlowej, istnieją pewne drobne ograniczenia:</span><span class="sxs-lookup"><span data-stu-id="cf547-111">Although the Commerce evaluation environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="cf547-112">Chociaż środowisko oceny usługi Commerce nie ma żadnych ograniczeń geograficznych, składniki środowiska, takie jak aplikacje Retail Cloud Scale Unit (RCSU) i handlu elektronicznego, powinny być aprowizowane tylko w Stanach Zjednoczonych.</span><span class="sxs-lookup"><span data-stu-id="cf547-112">Although the Commerce evaluation environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, should be provisioned only in the United States.</span></span>
- <span data-ttu-id="cf547-113">Użycie środowiska oceny usługi Commerce jest ograniczone do 30 od daty aprowizacji handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="cf547-113">Use of the Commerce evaluation environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="cf547-114">Środowisko oceny usługi Commerce można pomyślnie wdrożyć i zainicjować tylko w środowisku, które używa topologii pokazów, gdzie wszystkie składniki środowiska są wdrażane w jednej maszynie wirtualnej w chmurze.</span><span class="sxs-lookup"><span data-stu-id="cf547-114">The Commerce evaluation environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed on a single cloud-hosted virtual machine (VM).</span></span> <span data-ttu-id="cf547-115">Głównym ograniczeniem tej topologii maszyny wirtualnej jest liczba współbieżnych użytkowników, które środowisko może obsługiwać.</span><span class="sxs-lookup"><span data-stu-id="cf547-115">The main limitation of this topology is the number of concurrent users that the environment can support.</span></span>

## <a name="get-started"></a><span data-ttu-id="cf547-116">Rozpocznij</span><span class="sxs-lookup"><span data-stu-id="cf547-116">Get started</span></span>

<span data-ttu-id="cf547-117">Aby aprowizować środowisko oceny usługi Commerce, zobacz [Aprowizowanie środowiska oceny usługi Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="cf547-117">To provision the Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cf547-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cf547-118">Additional resources</span></span>

[<span data-ttu-id="cf547-119">Ustanowienie środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="cf547-119">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="cf547-120">Konfigurowanie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="cf547-120">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="cf547-121">Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="cf547-121">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="cf547-122">Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="cf547-122">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="cf547-123">Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="cf547-123">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
