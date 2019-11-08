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
ms.openlocfilehash: 9a12ab249129dce24cdca5e29d737fa9f68c0eac
ms.sourcegitcommit: 6e0909e95f38b7487a4b7f68cc62b723f8b59bd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572456"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="cccf7-103">Hierarchia organizacyjna w usłudze Common Data Service</span><span class="sxs-lookup"><span data-stu-id="cccf7-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="cccf7-104">Ponieważ Dynamics 365 Finance jest systemem finansowym, *organizacja* jest podstawową koncepcją, a konfiguracja systemu rozpoczyna się od konfiguracji hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="cccf7-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="cccf7-105">Finanse biznesowe mogą być następnie śledzone na poziomie organizacji, a także na dowolnym poziomie w hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="cccf7-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="cccf7-106">Mimo że w usłudze Common Data Service nie występuje pojęcie hierarchii organizacyjnej, występuje w niej kilka luźnych pojęć, takich jak całkowity przychód ze sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cccf7-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="cccf7-107">W ramach integracji z usługą Common Data Service struktura danych hierarchii organizacyjnej jest dodawana do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cccf7-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="cccf7-108">Przepływ danych</span><span class="sxs-lookup"><span data-stu-id="cccf7-108">Data flow</span></span>

<span data-ttu-id="cccf7-109">Ekosystem biznesowy składający się z aplikacji Finance and Operations i usługi Common Data Service będzie nadal posiadał hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="cccf7-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="cccf7-110">Ta hierarchia organizacji jest zbudowana na aplikacjach Finance and Operations, ale jest dostępna w usłudze Common Data Service do celów informacyjnych i rozszerzania środowiska.</span><span class="sxs-lookup"><span data-stu-id="cccf7-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="cccf7-111">Poniższa ilustracja przedstawia informacje o hierarchii organizacyjnej, które są dostępne w usłudze Common Data Service w postaci jednokierunkowego przepływu danych z aplikacji Finance and Operations do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cccf7-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Obraz architektury](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="cccf7-113">Szablony</span><span class="sxs-lookup"><span data-stu-id="cccf7-113">Templates</span></span>

<span data-ttu-id="cccf7-114">Mapy encji hierarchii organizacyjnej są dostępne dla jednokierunkowego synchronizowania danych z aplikacji Finance and Operations do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cccf7-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="cccf7-115">Wewnętrzne cele hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="cccf7-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="cccf7-116">Ten szablon zapewnia jednokierunkową synchronizację encji Cele hierarchii organizacji z Finance and Operations do innych aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cccf7-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="cccf7-117">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-117">Source field</span></span> | <span data-ttu-id="cccf7-118">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="cccf7-118">Map type</span></span> | <span data-ttu-id="cccf7-119">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-119">Destination field</span></span>
---|---|---
<span data-ttu-id="cccf7-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="cccf7-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="cccf7-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="cccf7-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="cccf7-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="cccf7-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="cccf7-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="cccf7-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="cccf7-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="cccf7-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="cccf7-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="cccf7-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="cccf7-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="cccf7-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="cccf7-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="cccf7-127">msdyn\_immutable</span></span>
<span data-ttu-id="cccf7-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="cccf7-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="cccf7-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="cccf7-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="cccf7-130">Typ wewnętrznej hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="cccf7-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="cccf7-131">Ten szablon zapewnia jednokierunkową synchronizację encji Typ hierarchii organizacji z Finance and Operations do innych aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cccf7-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="cccf7-132">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-132">Source field</span></span> | <span data-ttu-id="cccf7-133">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="cccf7-133">Map type</span></span> | <span data-ttu-id="cccf7-134">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-134">Destination field</span></span>
---|---|---
<span data-ttu-id="cccf7-135">NAZWA</span><span class="sxs-lookup"><span data-stu-id="cccf7-135">NAME</span></span> | \> | <span data-ttu-id="cccf7-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="cccf7-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="cccf7-137">Wewnętrzna hierarchia organizacyjna</span><span class="sxs-lookup"><span data-stu-id="cccf7-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="cccf7-138">Ten szablon zapewnia jednokierunkową synchronizację encji Opublikowana hierarchia organizacji z Finance and Operations do innych aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cccf7-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="cccf7-139">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-139">Source field</span></span> | <span data-ttu-id="cccf7-140">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="cccf7-140">Map type</span></span> | <span data-ttu-id="cccf7-141">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-141">Destination field</span></span>
---|---|---
<span data-ttu-id="cccf7-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="cccf7-142">VALIDTO</span></span> | \> | <span data-ttu-id="cccf7-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="cccf7-143">msdyn\_validto</span></span>
<span data-ttu-id="cccf7-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="cccf7-144">VALIDFROM</span></span> | \> | <span data-ttu-id="cccf7-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="cccf7-145">msdyn\_validfrom</span></span>
<span data-ttu-id="cccf7-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="cccf7-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="cccf7-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="cccf7-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="cccf7-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="cccf7-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="cccf7-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="cccf7-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="cccf7-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="cccf7-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="cccf7-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="cccf7-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="cccf7-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="cccf7-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="cccf7-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="cccf7-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="cccf7-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="cccf7-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="cccf7-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="cccf7-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="cccf7-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="cccf7-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="cccf7-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="cccf7-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="cccf7-158">Wewnętrzna organizacja</span><span class="sxs-lookup"><span data-stu-id="cccf7-158">Internal Organization</span></span>

<span data-ttu-id="cccf7-159">Informacje o organizacji wewnętrznej Common Data Service pochodzą z dwóch encji, **jednostki operacyjnej** i **firm**.</span><span class="sxs-lookup"><span data-stu-id="cccf7-159">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="cccf7-160">Jednostka operacyjna</span><span class="sxs-lookup"><span data-stu-id="cccf7-160">Operating unit</span></span>

<span data-ttu-id="cccf7-161">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-161">Source field</span></span> | <span data-ttu-id="cccf7-162">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="cccf7-162">Map type</span></span> | <span data-ttu-id="cccf7-163">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-163">Destination field</span></span>
---|---|---
<span data-ttu-id="cccf7-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="cccf7-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="cccf7-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="cccf7-165">msdyn\_languageid</span></span>
<span data-ttu-id="cccf7-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="cccf7-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="cccf7-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="cccf7-167">msdyn\_namealias</span></span>
<span data-ttu-id="cccf7-168">NAZWA</span><span class="sxs-lookup"><span data-stu-id="cccf7-168">NAME</span></span> | \> | <span data-ttu-id="cccf7-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="cccf7-169">msdyn\_name</span></span>
<span data-ttu-id="cccf7-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="cccf7-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="cccf7-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="cccf7-171">msdyn\_partynumber</span></span>
<span data-ttu-id="cccf7-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="cccf7-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="cccf7-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="cccf7-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="cccf7-174">Firma</span><span class="sxs-lookup"><span data-stu-id="cccf7-174">Legal entity</span></span>

<span data-ttu-id="cccf7-175">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-175">Source field</span></span> | <span data-ttu-id="cccf7-176">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="cccf7-176">Map type</span></span> | <span data-ttu-id="cccf7-177">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-177">Destination field</span></span>
---|---|---
<span data-ttu-id="cccf7-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="cccf7-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="cccf7-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="cccf7-179">msdyn\_namealias</span></span>
<span data-ttu-id="cccf7-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="cccf7-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="cccf7-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="cccf7-181">msdyn\_languageid</span></span>
<span data-ttu-id="cccf7-182">NAZWA</span><span class="sxs-lookup"><span data-stu-id="cccf7-182">NAME</span></span> | \> | <span data-ttu-id="cccf7-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="cccf7-183">msdyn\_name</span></span>
<span data-ttu-id="cccf7-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="cccf7-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="cccf7-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="cccf7-185">msdyn\_partynumber</span></span>
<span data-ttu-id="cccf7-186">brak</span><span class="sxs-lookup"><span data-stu-id="cccf7-186">none</span></span> | \>\> | <span data-ttu-id="cccf7-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="cccf7-187">msdyn\_type</span></span>
<span data-ttu-id="cccf7-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="cccf7-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="cccf7-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="cccf7-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="cccf7-190">Firma</span><span class="sxs-lookup"><span data-stu-id="cccf7-190">Company</span></span>

<span data-ttu-id="cccf7-191">Zapewnia dwukierunkową synchronizację informacji podmiotu prawnego (firmy) między Finance and Operations a innymi aplikacjami Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cccf7-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="cccf7-192">Pole źródłowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-192">Source field</span></span> | <span data-ttu-id="cccf7-193">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="cccf7-193">Map type</span></span> | <span data-ttu-id="cccf7-194">Pole docelowe</span><span class="sxs-lookup"><span data-stu-id="cccf7-194">Destination field</span></span>
---|---|---
<span data-ttu-id="cccf7-195">NAZWA</span><span class="sxs-lookup"><span data-stu-id="cccf7-195">NAME</span></span> | = | <span data-ttu-id="cccf7-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="cccf7-196">cdm\_name</span></span>
<span data-ttu-id="cccf7-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="cccf7-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="cccf7-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="cccf7-198">cdm\_companycode</span></span>
