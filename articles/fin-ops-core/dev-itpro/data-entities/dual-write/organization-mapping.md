---
title: Hierarchia organizacyjna w usłudze Common Data Service
description: W tym temacie opisano integrację danych organizacji między aplikacjami Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: fbf7cc33d12fb54d2ff02acc46ba2e284b2a2b3f
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019958"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="ed815-103">Hierarchia organizacyjna w usłudze Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ed815-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="ed815-104">Ponieważ Dynamics 365 Finance jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="ed815-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="ed815-105">Finanse biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="ed815-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="ed815-106">Mimo że w usłudze Common Data Service nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ed815-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="ed815-107">W ramach integracji z usługą Common Data Service struktura danych hierarchii organizacyjnej jest dodawana do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ed815-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="ed815-108">Przepływ danych</span><span class="sxs-lookup"><span data-stu-id="ed815-108">Data flow</span></span>

<span data-ttu-id="ed815-109">Ekosystem biznesowy składający się z aplikacji Finance and Operations i usługi Common Data Service będzie nadal posiadał hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="ed815-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="ed815-110">Ta hierarchia organizacji jest zbudowana na aplikacjach Finance and Operations, ale jest dostępna w usłudze Common Data Service do celów informacyjnych i rozszerzania środowiska.</span><span class="sxs-lookup"><span data-stu-id="ed815-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="ed815-111">Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Common Data Service w postaci jednokierunkowego przepływu danych z aplikacji Finance and Operations do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ed815-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Obraz architektury](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="ed815-113">Szablony</span><span class="sxs-lookup"><span data-stu-id="ed815-113">Templates</span></span>

<span data-ttu-id="ed815-114">Mapy encji hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z aplikacji Finance and Operations do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ed815-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="ed815-115">Szablony</span><span class="sxs-lookup"><span data-stu-id="ed815-115">Templates</span></span>

<span data-ttu-id="ed815-116">Informacje o produkcie zawierają wszystkie informacje związane z produktem i jego definicję, takie jak wymiary produktu lub wymiary śledzenia i przechowywania.</span><span class="sxs-lookup"><span data-stu-id="ed815-116">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="ed815-117">W poniższej tabeli przedstawiono kolekcję mapowań jednostek, która umożliwia synchronizowanie produktów i informacji pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="ed815-117">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="ed815-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ed815-118">Finance and Operations</span></span> | <span data-ttu-id="ed815-119">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ed815-119">Other Dynamics 365 apps</span></span> | <span data-ttu-id="ed815-120">Opis</span><span class="sxs-lookup"><span data-stu-id="ed815-120">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="ed815-121">Cele hierarchii organizacji</span><span class="sxs-lookup"><span data-stu-id="ed815-121">Organization hierarchy purposes</span></span> | <span data-ttu-id="ed815-122">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="ed815-122">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="ed815-123">Ten szablon umożliwia jednokierunkową synchronizację jednostki cel hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="ed815-123">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="ed815-124">Typ hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="ed815-124">Organization hierarchy type</span></span> | <span data-ttu-id="ed815-125">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="ed815-125">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="ed815-126">Ten szablon umożliwia jednokierunkową synchronizację jednostki typu hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="ed815-126">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="ed815-127">Hierarchia organizacyjna - opublikowana</span><span class="sxs-lookup"><span data-stu-id="ed815-127">Organization hierarchy - published</span></span> | <span data-ttu-id="ed815-128">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="ed815-128">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="ed815-129">Ten szablon umożliwia jednokierunkową synchronizację jednostki opublikowanej hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="ed815-129">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="ed815-130">Jednostka operacyjna</span><span class="sxs-lookup"><span data-stu-id="ed815-130">Operating unit</span></span> | <span data-ttu-id="ed815-131">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="ed815-131">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="ed815-132">Firmy</span><span class="sxs-lookup"><span data-stu-id="ed815-132">Legal entities</span></span> | <span data-ttu-id="ed815-133">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="ed815-133">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="ed815-134">Firmy</span><span class="sxs-lookup"><span data-stu-id="ed815-134">Legal entities</span></span> | <span data-ttu-id="ed815-135">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="ed815-135">cdm_companies</span></span> | <span data-ttu-id="ed815-136">Umożliwia synchronizację dwukierunkową informacji firmy (firmy).</span><span class="sxs-lookup"><span data-stu-id="ed815-136">Provides bidirectional synchronization of legal entity (company) information.</span></span>


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="ed815-137">Wewnętrzna organizacja</span><span class="sxs-lookup"><span data-stu-id="ed815-137">Internal Organization</span></span>

<span data-ttu-id="ed815-138">Informacje o organizacji wewnętrznej Common Data Service pochodzą z dwóch encji, **jednostki operacyjnej** i **firm**.</span><span class="sxs-lookup"><span data-stu-id="ed815-138">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]

