---
title: Usługi globalizacji Dynamics 365
description: Ten temat zawiera omówienie usług globalizacji Microsoft Dynamics 365.
author: JaneA07
manager: AnnBe
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 8c6f3b7fb4dec0dffe55014e9e2d60620dc3b193
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893055"
---
# <a name="dynamics-365-globalization-services"></a><span data-ttu-id="887ce-103">Usługi globalizacji Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="887ce-103">Dynamics 365 globalization services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="887ce-104">Następujące usługi globalizacji można skonfigurować w celu rozszerzenia możliwości, które istnieją w niektórych usługach online Microsoft Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="887ce-104">The following globalization services can be configured to extend the capabilities that exist in some Microsoft Dynamics 365 online services:</span></span>

- <span data-ttu-id="887ce-105">**Usługa Regulatory Configuration Service (RCS)** obsługuje konfigurację różnych typów dokumentów i raportów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="887ce-105">**Regulatory Configuration Service (RCS)** supports the configuration of different types of electronic documents and reports.</span></span> <span data-ttu-id="887ce-106">RCS zapewnia ulepszoną wersję projektanta raportowania elektronicznego (ER), w którym repozytorium konfiguracji jest samodzielną usługą.</span><span class="sxs-lookup"><span data-stu-id="887ce-106">RCS provides an enhanced version of the Electronic reporting (ER) designer where the configuration repository is a standalone service.</span></span> <span data-ttu-id="887ce-107">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Regulatory Configuration Service](rcs-overview.md).</span><span class="sxs-lookup"><span data-stu-id="887ce-107">For more information, see [Regulatory Configuration Service](rcs-overview.md).</span></span>
- <span data-ttu-id="887ce-108">**Fakturowanie elektroniczne** łączy konfigurowalne formaty dla przekształceń, podpisów cyfrowych i konfigurowalnych integracji dla łączności z zewnętrznymi usługami sieci web, w tym obsługi certyfikacji i odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="887ce-108">**Electronic Invoicing** brings together configurable formats for transformations, digital signatures, and configurable integrations for connectivity with external web services, including certification and response handling.</span></span> <span data-ttu-id="887ce-109">Aby uzyskać więcej informacji, zajrzyj do [Faktury elektroniczne](e-invoicing-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="887ce-109">For more information, see [Electronic Invoicing](e-invoicing-service-overview.md).</span></span>
- <span data-ttu-id="887ce-110">**Obliczanie podatków** zapewnia większą elastyczność dzięki obsłudze wielu identyfikatorów podatkowych, określaniu kodów podatkowych, projektantowi obliczania podatków i mechanizmowi wykonawczemu, który zapewnia zgodność ze złożonymi przepisami podatkowymi na całym świecie.</span><span class="sxs-lookup"><span data-stu-id="887ce-110">**Tax Calculation** provides enhanced flexibility by supporting multiple tax IDs, tax code determination, the tax calculation designer, and a runtime engine to comply with complex tax regulations worldwide.</span></span> <span data-ttu-id="887ce-111">Aby uzyskać więcej informacji, zobacz [Obliczanie podatku](global-tax-calcuation-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="887ce-111">For more information, see [Tax Calculation](global-tax-calcuation-service-overview.md).</span></span>

<span data-ttu-id="887ce-112">Te usługi globalizacji zapewniają bezpośrednią integrację z następującymi usługami online Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="887ce-112">These globalization services provide out-of-box integration with the following Dynamics 365 online services.</span></span>

| <span data-ttu-id="887ce-113">Usługi online</span><span class="sxs-lookup"><span data-stu-id="887ce-113">Online service</span></span> | <span data-ttu-id="887ce-114">RCS</span><span class="sxs-lookup"><span data-stu-id="887ce-114">RCS</span></span> | <span data-ttu-id="887ce-115">Fakturowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="887ce-115">Electronic Invoicing</span></span> | <span data-ttu-id="887ce-116">Obliczanie podatku (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="887ce-116">Tax Calculation (Preview)</span></span> |
|----------------|-----|----------------------|---------------------------|
| <span data-ttu-id="887ce-117">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="887ce-117">Dynamics 365 Finance</span></span> | <span data-ttu-id="887ce-118">Tak</span><span class="sxs-lookup"><span data-stu-id="887ce-118">Yes</span></span> | <span data-ttu-id="887ce-119">Tak</span><span class="sxs-lookup"><span data-stu-id="887ce-119">Yes</span></span> | <span data-ttu-id="887ce-120">Tak</span><span class="sxs-lookup"><span data-stu-id="887ce-120">Yes</span></span> | 
| <span data-ttu-id="887ce-121">Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="887ce-121">Dynamics 365 Supply Chain Management</span></span> | <span data-ttu-id="887ce-122">Tak</span><span class="sxs-lookup"><span data-stu-id="887ce-122">Yes</span></span> | <span data-ttu-id="887ce-123">Tak</span><span class="sxs-lookup"><span data-stu-id="887ce-123">Yes</span></span> | <span data-ttu-id="887ce-124">Tak</span><span class="sxs-lookup"><span data-stu-id="887ce-124">Yes</span></span> | 
| <span data-ttu-id="887ce-125">Dynamics 365 Project Operations</span><span class="sxs-lookup"><span data-stu-id="887ce-125">Dynamics 365 Project Operations</span></span> | <span data-ttu-id="887ce-126">Tak</span><span class="sxs-lookup"><span data-stu-id="887ce-126">Yes</span></span> | <span data-ttu-id="887ce-127">Tak</span><span class="sxs-lookup"><span data-stu-id="887ce-127">Yes</span></span> | <span data-ttu-id="887ce-128">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="887ce-128">Not applicable</span></span> | 
| <span data-ttu-id="887ce-129">Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="887ce-129">Dynamics 365 Commerce</span></span> | <span data-ttu-id="887ce-130">Tak</span><span class="sxs-lookup"><span data-stu-id="887ce-130">Yes</span></span> | <span data-ttu-id="887ce-131">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="887ce-131">Not applicable</span></span> | <span data-ttu-id="887ce-132">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="887ce-132">Not applicable</span></span> | 

> [!NOTE]
> <span data-ttu-id="887ce-133">Ze względu na różnice w dostępności lokalizacji geograficznych (geograficznych) platformy Azure dla RCS konfiguracja tej usługi może spowodować przeniesienie danych klientów poza obszar geograficzny wybrany dla odpowiedniej usługi online Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="887ce-133">Because of differences in the availability of Azure geographic locations (geos) for RCS, configuration of this service might cause customer data to be transferred outside the geo that is selected for the applicable Dynamics 365 online service.</span></span> <span data-ttu-id="887ce-134">Aby uzyskać więcej informacji, zobacz temat [Dynamics 365 oraz Power Platform: Dostępność, lokalizacja danych, język i lokalizacja](https://aka.ms/rcs/D365Productavailabilityguide).</span><span class="sxs-lookup"><span data-stu-id="887ce-134">For more information, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/rcs/D365Productavailabilityguide).</span></span>