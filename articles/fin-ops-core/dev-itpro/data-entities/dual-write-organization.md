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
ms.openlocfilehash: fd159b38f69305dcaecb364ba0ccb3befabb3582
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182032"
---
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="80960-103">Hierarchia organizacyjna w usłudze Common Data Service</span><span class="sxs-lookup"><span data-stu-id="80960-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="80960-104">Ponieważ Dynamics 365 Finance jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="80960-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="80960-105">Finanse biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="80960-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="80960-106">Mimo że w usłudze Common Data Service nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="80960-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="80960-107">W ramach integracji z usługą Common Data Service struktura danych hierarchii organizacyjnej jest dodawana do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="80960-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="80960-108">Przepływ danych</span><span class="sxs-lookup"><span data-stu-id="80960-108">Data flow</span></span>

<span data-ttu-id="80960-109">Ekosystem biznesowy składający się z aplikacji Finance and Operations i usługi Common Data Service będzie nadal posiadał hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="80960-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="80960-110">Ta hierarchia organizacji jest zbudowana na aplikacjach Finance and Operations, ale jest dostępna w usłudze Common Data Service do celów informacyjnych i rozszerzania środowiska.</span><span class="sxs-lookup"><span data-stu-id="80960-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="80960-111">Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Common Data Service w postaci jednokierunkowego przepływu danych z aplikacji Finance and Operations do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="80960-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Obraz architektury](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="80960-113">Szablony</span><span class="sxs-lookup"><span data-stu-id="80960-113">Templates</span></span>

<span data-ttu-id="80960-114">Mapy encji hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z aplikacji Finance and Operations do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="80960-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="80960-115">Wewnętrzne cele hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="80960-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="80960-116">Ten szablon zapewnia jednokierunkową synchronizację encji Cele hierarchii organizacji z Finance and Operations do innych aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="80960-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="80960-117">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="80960-117">Source field</span></span> | <span data-ttu-id="80960-118">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="80960-118">Map type</span></span> | <span data-ttu-id="80960-119">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="80960-119">Destination field</span></span>
---|---|---
<span data-ttu-id="80960-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="80960-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="80960-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="80960-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="80960-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="80960-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="80960-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="80960-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="80960-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="80960-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="80960-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="80960-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="80960-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="80960-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="80960-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="80960-127">msdyn\_immutable</span></span>
<span data-ttu-id="80960-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="80960-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="80960-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="80960-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="80960-130">Typ wewnętrznej hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="80960-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="80960-131">Ten szablon zapewnia jednokierunkową synchronizację encji Typ hierarchii organizacji z Finance and Operations do innych aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="80960-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="80960-132">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="80960-132">Source field</span></span> | <span data-ttu-id="80960-133">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="80960-133">Map type</span></span> | <span data-ttu-id="80960-134">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="80960-134">Destination field</span></span>
---|---|---
<span data-ttu-id="80960-135">NAZWA</span><span class="sxs-lookup"><span data-stu-id="80960-135">NAME</span></span> | \> | <span data-ttu-id="80960-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="80960-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="80960-137">Wewnętrzna hierarchia organizacyjna</span><span class="sxs-lookup"><span data-stu-id="80960-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="80960-138">Ten szablon zapewnia jednokierunkową synchronizację encji Opublikowana hierarchia organizacji z Finance and Operations do innych aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="80960-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="80960-139">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="80960-139">Source field</span></span> | <span data-ttu-id="80960-140">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="80960-140">Map type</span></span> | <span data-ttu-id="80960-141">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="80960-141">Destination field</span></span>
---|---|---
<span data-ttu-id="80960-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="80960-142">VALIDTO</span></span> | \> | <span data-ttu-id="80960-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="80960-143">msdyn\_validto</span></span>
<span data-ttu-id="80960-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="80960-144">VALIDFROM</span></span> | \> | <span data-ttu-id="80960-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="80960-145">msdyn\_validfrom</span></span>
<span data-ttu-id="80960-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="80960-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="80960-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="80960-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="80960-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="80960-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="80960-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="80960-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="80960-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="80960-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="80960-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="80960-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="80960-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="80960-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="80960-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="80960-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="80960-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="80960-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="80960-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="80960-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="80960-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="80960-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="80960-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="80960-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="80960-158">Wewnętrzna organizacja</span><span class="sxs-lookup"><span data-stu-id="80960-158">Internal Organization</span></span>

<span data-ttu-id="80960-159">Informacje o organizacji wewnętrznej Common Data Service pochodzą z dwóch encji, **jednostki operacyjnej** i **firm**.</span><span class="sxs-lookup"><span data-stu-id="80960-159">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="80960-160">Jednostka operacyjna</span><span class="sxs-lookup"><span data-stu-id="80960-160">Operating unit</span></span>

<span data-ttu-id="80960-161">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="80960-161">Source field</span></span> | <span data-ttu-id="80960-162">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="80960-162">Map type</span></span> | <span data-ttu-id="80960-163">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="80960-163">Destination field</span></span>
---|---|---
<span data-ttu-id="80960-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="80960-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="80960-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="80960-165">msdyn\_languageid</span></span>
<span data-ttu-id="80960-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="80960-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="80960-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="80960-167">msdyn\_namealias</span></span>
<span data-ttu-id="80960-168">NAZWA</span><span class="sxs-lookup"><span data-stu-id="80960-168">NAME</span></span> | \> | <span data-ttu-id="80960-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="80960-169">msdyn\_name</span></span>
<span data-ttu-id="80960-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="80960-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="80960-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="80960-171">msdyn\_partynumber</span></span>
<span data-ttu-id="80960-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="80960-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="80960-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="80960-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="80960-174">Firma</span><span class="sxs-lookup"><span data-stu-id="80960-174">Legal entity</span></span>

<span data-ttu-id="80960-175">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="80960-175">Source field</span></span> | <span data-ttu-id="80960-176">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="80960-176">Map type</span></span> | <span data-ttu-id="80960-177">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="80960-177">Destination field</span></span>
---|---|---
<span data-ttu-id="80960-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="80960-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="80960-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="80960-179">msdyn\_namealias</span></span>
<span data-ttu-id="80960-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="80960-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="80960-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="80960-181">msdyn\_languageid</span></span>
<span data-ttu-id="80960-182">NAZWA</span><span class="sxs-lookup"><span data-stu-id="80960-182">NAME</span></span> | \> | <span data-ttu-id="80960-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="80960-183">msdyn\_name</span></span>
<span data-ttu-id="80960-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="80960-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="80960-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="80960-185">msdyn\_partynumber</span></span>
<span data-ttu-id="80960-186">brak</span><span class="sxs-lookup"><span data-stu-id="80960-186">none</span></span> | \>\> | <span data-ttu-id="80960-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="80960-187">msdyn\_type</span></span>
<span data-ttu-id="80960-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="80960-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="80960-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="80960-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="80960-190">Firma</span><span class="sxs-lookup"><span data-stu-id="80960-190">Company</span></span>

<span data-ttu-id="80960-191">Zapewnia dwukierunkową synchronizację informacji podmiotu prawnego (firmy) między Finance and Operations a innymi aplikacjami Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="80960-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="80960-192">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="80960-192">Source field</span></span> | <span data-ttu-id="80960-193">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="80960-193">Map type</span></span> | <span data-ttu-id="80960-194">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="80960-194">Destination field</span></span>
---|---|---
<span data-ttu-id="80960-195">NAZWA</span><span class="sxs-lookup"><span data-stu-id="80960-195">NAME</span></span> | = | <span data-ttu-id="80960-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="80960-196">cdm\_name</span></span>
<span data-ttu-id="80960-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="80960-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="80960-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="80960-198">cdm\_companycode</span></span>
