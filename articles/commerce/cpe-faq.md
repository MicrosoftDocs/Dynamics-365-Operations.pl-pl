---
title: Często zadawane pytania dotyczące środowiska oceny rozwiązania Dynamics 365 Commerce
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące środowiska oceny Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a0c6f82432a4786f23f12122f3806c3b96a05c8f
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193601"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a><span data-ttu-id="023d9-103">Często zadawane pytania dotyczące środowiska oceny rozwiązania Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="023d9-103">Dynamics 365 Commerce evaluation environment FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="023d9-104">Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące środowiska oceny Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="023d9-104">This topic provides answers to frequently asked questions about the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="023d9-105">**Czy możemy użyć środowiska oceny usługi Commerce jako sklepu internetowego dla klientów, którzy obecnie wdrażają aplikację Retail?**</span><span class="sxs-lookup"><span data-stu-id="023d9-105">**Can we use the Commerce evaluation environment as an e-Commerce storefront for customers that currently implement Retail?**</span></span>

<span data-ttu-id="023d9-106">Nr</span><span class="sxs-lookup"><span data-stu-id="023d9-106">No.</span></span> <span data-ttu-id="023d9-107">Środowisko oceny Commerce jest przeznaczone wyłącznie do oceny.</span><span class="sxs-lookup"><span data-stu-id="023d9-107">The Commerce evaluation environment is only for evaluation.</span></span> <span data-ttu-id="023d9-108">Jeśli wymagane jest środowisko dla klienta, który implementuje aplikację Retail, skontaktuj się z firmą Microsoft.</span><span class="sxs-lookup"><span data-stu-id="023d9-108">If you require an environment for a customer that implements Retail, contact Microsoft.</span></span>

<span data-ttu-id="023d9-109">**Czy środowisko oceny usługi Commerce może służyć do aprowizowania funkcji handlu elektronicznego jako uzupełnienie istniejącej aplikacji/środowiska, które implementuje aplikację Retail?**</span><span class="sxs-lookup"><span data-stu-id="023d9-109">**Can the Commerce evaluation environment be used to provision the e-Commerce features on top of an existing application/environment that implements Retail?**</span></span>

<span data-ttu-id="023d9-110">Nie (głównie).</span><span class="sxs-lookup"><span data-stu-id="023d9-110">No (mostly).</span></span> <span data-ttu-id="023d9-111">Składniki oceny aplikacji Commerce są dostępne tylko w środowiskach zgodnych z konfiguracjami określonymi w wymaganiach wstępnych i przewodniku obsługi administracyjnej.</span><span class="sxs-lookup"><span data-stu-id="023d9-111">The Commerce evaluation components are available only to environments that match the configurations that are specified in the prerequisites and provisioning guide.</span></span> <span data-ttu-id="023d9-112">Ponadto wymagane podstawowe dane demonstracyjne nie będą dostępne w środowiskach wdrożonych z początkową wersją wcześniejszą niż 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="023d9-112">Additionally, the required base demo data won't be available in environments that were deployed with an initial release that is earlier than 10.0.8.</span></span> 

<span data-ttu-id="023d9-113">**Jakie koszty są zaangażowane we wdrażanie środowiska oceny usługi Commerce na platformie Microsoft Azure za pośrednictwem usług Microsoft Dynamics Lifecycle Services (LCS)?**</span><span class="sxs-lookup"><span data-stu-id="023d9-113">**What costs are involved in deploying the Commerce evaluation environment on Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**</span></span>

<span data-ttu-id="023d9-114">Tradycyjne środowisko demonstracyjne//główne Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce (maszyna wirtualna \[VM\]) będzie hostowana w Twojej subskrypcji platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="023d9-114">A traditional Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce headquarters demo environment (virtual machine \[VM\]) will be hosted in your Azure subscription.</span></span> <span data-ttu-id="023d9-115">Możesz użyć [kalkulatora cen platformy Azure](https://azure.microsoft.com/pricing/calculator/), aby oszacować ten koszt.</span><span class="sxs-lookup"><span data-stu-id="023d9-115">You can use the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/) to estimate this cost.</span></span>

<span data-ttu-id="023d9-116">Inne składniki, takie jak Commerce Scale Unit, Commerce Site Builder i Twoja witryna handlu elektronicznego, będą dostępne jako oprogramowanie jako usługa (SaaS) i będą obsługiwane przez firmę Microsoft.</span><span class="sxs-lookup"><span data-stu-id="023d9-116">Other components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site will be available as software as a service (SaaS) and hosted by Microsoft.</span></span>

<span data-ttu-id="023d9-117">**Które regiony geograficzne platformy Azure są obecnie obsługiwane w środowisku oceny usługi Commerce?**</span><span class="sxs-lookup"><span data-stu-id="023d9-117">**Which Azure geographies are currently supported for the Commerce evaluation environment?**</span></span>

<span data-ttu-id="023d9-118">Środowisko oceny usługi Commerce można wdrożyć tylko w regionie Ameryka Północna.</span><span class="sxs-lookup"><span data-stu-id="023d9-118">The Commerce evaluation environment can be deployed only in the North America geography.</span></span>

<span data-ttu-id="023d9-119">**Czy istnieje wirtualny dysk twardy (VHD) z możliwością pobrania, który ma pełną opcję maszyny wirtualnej OneBox?**</span><span class="sxs-lookup"><span data-stu-id="023d9-119">**Is there a downloadable virtual hard disk (VHD) that has the complete OneBox virtual machine (VM) option?**</span></span>

<span data-ttu-id="023d9-120">Dynamics 365 Commerce i Commerce Scale Unit to w całości oprogramowanie jako usługa (SaaS) i muszą być hostowane w chmurze.</span><span class="sxs-lookup"><span data-stu-id="023d9-120">Dynamics 365 Commerce and Commerce Scale Unit are completely software as a service (SaaS) and must be cloud-hosted.</span></span>

<span data-ttu-id="023d9-121">**Jak długo można używać środowiska oceny usługi Commerce?**</span><span class="sxs-lookup"><span data-stu-id="023d9-121">**How long can the Commerce evaluation environment be used?**</span></span>

<span data-ttu-id="023d9-122">Środowisko oceny Commerce ma 30-dniowy limit czasu od daty udostępnienia składników SaaS, takich jak Commerce Scale Unit, narzędzie do tworzenia witryn Commerce i Twoja witryna handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="023d9-122">The Commerce evaluation environment has a 30-day time limit from the date when SaaS components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site are provisioned.</span></span>

<span data-ttu-id="023d9-123">**Czy mogę przedłużyć limit czasu dla mojego środowiska oceny usługi Commerce?**</span><span class="sxs-lookup"><span data-stu-id="023d9-123">**Can I extend the time limit for my Commerce evaluation environment?**</span></span>

<span data-ttu-id="023d9-124">Wydłużenie limitu czasu jest wyjątkiem od normy i jest brane pod uwagę oddzielnie dla każdego przypadku.</span><span class="sxs-lookup"><span data-stu-id="023d9-124">Extension of the time limit is an exception to the norm and is considered on a case-by-case basis.</span></span> <span data-ttu-id="023d9-125">Aby uzyskać pomoc, skontaktuj się z partnerem firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="023d9-125">You should reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="023d9-126">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="023d9-126">Additional resources</span></span>

[<span data-ttu-id="023d9-127">Omówienie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="023d9-127">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="023d9-128">Ustanowienie środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="023d9-128">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="023d9-129">Konfigurowanie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="023d9-129">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="023d9-130">Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="023d9-130">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="023d9-131">Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="023d9-131">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]