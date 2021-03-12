---
title: Hierarchia organizacyjna w usłudze Dataverse
description: W tym temacie opisano integrację danych organizacji między aplikacjami Finance and Operations i Dataverse.
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
ms.openlocfilehash: 5132fd85fdf2c08ccded9db590328c394a2f984e
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744700"
---
# <a name="organization-hierarchy-in-dataverse"></a><span data-ttu-id="a7811-103">Hierarchia organizacyjna w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="a7811-103">Organization hierarchy in Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a7811-104">Ponieważ Dynamics 365 Finance jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="a7811-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="a7811-105">Finanse biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="a7811-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="a7811-106">Mimo że w usłudze Dataverse nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a7811-106">Although Dataverse doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="a7811-107">W ramach integracji z usługą Dataverse struktura danych hierarchii organizacyjnej jest dodawana do usługi Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a7811-107">As part of Dataverse integration, the organization hierarchy data structure is added to Dataverse.</span></span>

## <a name="data-flow"></a><span data-ttu-id="a7811-108">Przepływ danych</span><span class="sxs-lookup"><span data-stu-id="a7811-108">Data flow</span></span>

<span data-ttu-id="a7811-109">Ekosystem biznesowy składający się z aplikacji Finance and Operations i usługi Dataverse będzie nadal posiadał hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="a7811-109">A business ecosystem that consists of Finance and Operations apps and Dataverse will continue to have an organization hierarchy.</span></span> <span data-ttu-id="a7811-110">Ta hierarchia organizacji jest zbudowana na aplikacjach Finance and Operations, ale jest dostępna w usłudze Dataverse do celów informacyjnych i rozszerzania środowiska.</span><span class="sxs-lookup"><span data-stu-id="a7811-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Dataverse for informational and extensibility purposes.</span></span> <span data-ttu-id="a7811-111">Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Dataverse w postaci jednokierunkowego przepływu danych z aplikacji Finance and Operations do usługi Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a7811-111">The following illustration shows the organization hierarchy information that is exposed in Dataverse as a one-way data flow from Finance and Operations apps to Dataverse.</span></span>

![Obraz architektury](media/dual-write-data-flow.png)

<span data-ttu-id="a7811-113">Mapy tabeli hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z aplikacji Finance and Operations do usługi Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a7811-113">Organization hierarchy table maps are available for one-way synchronization of data from Finance and Operations apps to Dataverse.</span></span>

## <a name="templates"></a><span data-ttu-id="a7811-114">Szablony</span><span class="sxs-lookup"><span data-stu-id="a7811-114">Templates</span></span>

<span data-ttu-id="a7811-115">Informacje o produkcie zawierają wszystkie informacje związane z produktem i jego definicję, takie jak wymiary produktu lub wymiary śledzenia i przechowywania.</span><span class="sxs-lookup"><span data-stu-id="a7811-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="a7811-116">W poniższej tabeli przedstawiono kolekcję mapowań tabel, która umożliwia synchronizowanie produktów i informacji pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="a7811-116">As the following table shows, a collection of table maps is created to sync products and related information.</span></span>

<span data-ttu-id="a7811-117">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a7811-117">Finance and Operations apps</span></span> | <span data-ttu-id="a7811-118">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a7811-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="a7811-119">opis</span><span class="sxs-lookup"><span data-stu-id="a7811-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="a7811-120">Cele hierarchii organizacji</span><span class="sxs-lookup"><span data-stu-id="a7811-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="a7811-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="a7811-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="a7811-122">Ten szablon umożliwia jednokierunkową synchronizację tabeli celu hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="a7811-122">This template provides one-way synchronization of the Organization Hierarchy Purpose table.</span></span>
<span data-ttu-id="a7811-123">Typ hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="a7811-123">Organization hierarchy type</span></span> | <span data-ttu-id="a7811-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="a7811-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="a7811-125">Ten szablon umożliwia jednokierunkową synchronizację tabeli typu hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="a7811-125">This template provides one-way synchronization of the Organization Hierarchy Type table.</span></span>
<span data-ttu-id="a7811-126">Hierarchia organizacyjna — opublikowana</span><span class="sxs-lookup"><span data-stu-id="a7811-126">Organization hierarchy - published</span></span> | <span data-ttu-id="a7811-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="a7811-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="a7811-128">Ten szablon umożliwia jednokierunkową synchronizację tabeli opublikowanej hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="a7811-128">This template provides one-way synchronization of the Organization Hierarchy Published table.</span></span>
<span data-ttu-id="a7811-129">Jednostka operacyjna</span><span class="sxs-lookup"><span data-stu-id="a7811-129">Operating unit</span></span> | <span data-ttu-id="a7811-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="a7811-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="a7811-131">Osoby prawne</span><span class="sxs-lookup"><span data-stu-id="a7811-131">Legal entities</span></span> | <span data-ttu-id="a7811-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="a7811-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="a7811-133">Firmy</span><span class="sxs-lookup"><span data-stu-id="a7811-133">Legal entities</span></span> | <span data-ttu-id="a7811-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="a7811-134">cdm_companies</span></span> | <span data-ttu-id="a7811-135">Umożliwia synchronizację dwukierunkową informacji firmy (firmy).</span><span class="sxs-lookup"><span data-stu-id="a7811-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="a7811-136">Wewnętrzna organizacja</span><span class="sxs-lookup"><span data-stu-id="a7811-136">Internal Organization</span></span>

<span data-ttu-id="a7811-137">Informacje o organizacji wewnętrznej Dataverse pochodzą z dwóch tabel, **jednostki operacyjnej** i **firm**.</span><span class="sxs-lookup"><span data-stu-id="a7811-137">Internal organization information in Dataverse comes from two tables, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
