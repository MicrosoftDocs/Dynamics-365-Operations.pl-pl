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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f502519ba419cb8fa322eb1d22f06d2b805f5f05
ms.sourcegitcommit: afc43699c0edc4ff2be310cb37add2ab586b64c0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "4000741"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="23eaa-103">Hierarchia organizacyjna w usłudze Common Data Service</span><span class="sxs-lookup"><span data-stu-id="23eaa-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="23eaa-104">Ponieważ Dynamics 365 Finance jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="23eaa-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="23eaa-105">Finanse biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="23eaa-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="23eaa-106">Mimo że w usłudze Common Data Service nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="23eaa-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="23eaa-107">W ramach integracji z usługą Common Data Service struktura danych hierarchii organizacyjnej jest dodawana do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="23eaa-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="23eaa-108">Przepływ danych</span><span class="sxs-lookup"><span data-stu-id="23eaa-108">Data flow</span></span>

<span data-ttu-id="23eaa-109">Ekosystem biznesowy składający się z aplikacji Finance and Operations i usługi Common Data Service będzie nadal posiadał hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="23eaa-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="23eaa-110">Ta hierarchia organizacji jest zbudowana na aplikacjach Finance and Operations, ale jest dostępna w usłudze Common Data Service do celów informacyjnych i rozszerzania środowiska.</span><span class="sxs-lookup"><span data-stu-id="23eaa-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="23eaa-111">Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Common Data Service w postaci jednokierunkowego przepływu danych z aplikacji Finance and Operations do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="23eaa-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Obraz architektury](media/dual-write-data-flow.png)

<span data-ttu-id="23eaa-113">Mapy encji hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z aplikacji Finance and Operations do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="23eaa-113">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="23eaa-114">Szablony</span><span class="sxs-lookup"><span data-stu-id="23eaa-114">Templates</span></span>

<span data-ttu-id="23eaa-115">Informacje o produkcie zawierają wszystkie informacje związane z produktem i jego definicję, takie jak wymiary produktu lub wymiary śledzenia i przechowywania.</span><span class="sxs-lookup"><span data-stu-id="23eaa-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="23eaa-116">W poniższej tabeli przedstawiono kolekcję mapowań jednostek, która umożliwia synchronizowanie produktów i informacji pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="23eaa-116">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="23eaa-117">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="23eaa-117">Finance and Operations apps</span></span> | <span data-ttu-id="23eaa-118">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="23eaa-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="23eaa-119">opis</span><span class="sxs-lookup"><span data-stu-id="23eaa-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="23eaa-120">Cele hierarchii organizacji</span><span class="sxs-lookup"><span data-stu-id="23eaa-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="23eaa-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="23eaa-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="23eaa-122">Ten szablon umożliwia jednokierunkową synchronizację jednostki cel hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="23eaa-122">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="23eaa-123">Typ hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="23eaa-123">Organization hierarchy type</span></span> | <span data-ttu-id="23eaa-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="23eaa-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="23eaa-125">Ten szablon umożliwia jednokierunkową synchronizację jednostki typu hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="23eaa-125">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="23eaa-126">Hierarchia organizacyjna - opublikowana</span><span class="sxs-lookup"><span data-stu-id="23eaa-126">Organization hierarchy - published</span></span> | <span data-ttu-id="23eaa-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="23eaa-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="23eaa-128">Ten szablon umożliwia jednokierunkową synchronizację jednostki opublikowanej hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="23eaa-128">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="23eaa-129">Jednostka operacyjna</span><span class="sxs-lookup"><span data-stu-id="23eaa-129">Operating unit</span></span> | <span data-ttu-id="23eaa-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="23eaa-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="23eaa-131">Firmy</span><span class="sxs-lookup"><span data-stu-id="23eaa-131">Legal entities</span></span> | <span data-ttu-id="23eaa-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="23eaa-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="23eaa-133">Firmy</span><span class="sxs-lookup"><span data-stu-id="23eaa-133">Legal entities</span></span> | <span data-ttu-id="23eaa-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="23eaa-134">cdm_companies</span></span> | <span data-ttu-id="23eaa-135">Umożliwia synchronizację dwukierunkową informacji firmy (firmy).</span><span class="sxs-lookup"><span data-stu-id="23eaa-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="23eaa-136">Wewnętrzna organizacja</span><span class="sxs-lookup"><span data-stu-id="23eaa-136">Internal Organization</span></span>

<span data-ttu-id="23eaa-137">Informacje o organizacji wewnętrznej Common Data Service pochodzą z dwóch encji, **jednostki operacyjnej** i **firm**.</span><span class="sxs-lookup"><span data-stu-id="23eaa-137">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
