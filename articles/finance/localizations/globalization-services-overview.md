---
title: Usługi globalizacji Dynamics 365
description: Ten temat zawiera omówienie usług globalizacji Microsoft Dynamics 365.
author: JaneA07
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
ms.openlocfilehash: 2ef942f7f6dac2c321a51800ade0bf25f2162304
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018814"
---
# <a name="dynamics-365-globalization-services"></a><span data-ttu-id="c1c48-103">Usługi globalizacji Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c1c48-103">Dynamics 365 globalization services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1c48-104">Następujące usługi globalizacji można skonfigurować w celu rozszerzenia możliwości, które istnieją w niektórych usługach online Microsoft Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="c1c48-104">The following globalization services can be configured to extend the capabilities that exist in some Microsoft Dynamics 365 online services:</span></span>

- <span data-ttu-id="c1c48-105">**Usługa Regulatory Configuration Service (RCS)** obsługuje konfigurację różnych typów dokumentów i raportów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="c1c48-105">**Regulatory Configuration Service (RCS)** supports the configuration of different types of electronic documents and reports.</span></span> <span data-ttu-id="c1c48-106">RCS zapewnia ulepszoną wersję projektanta raportowania elektronicznego (ER), w którym repozytorium konfiguracji jest samodzielną usługą.</span><span class="sxs-lookup"><span data-stu-id="c1c48-106">RCS provides an enhanced version of the Electronic reporting (ER) designer where the configuration repository is a standalone service.</span></span> <span data-ttu-id="c1c48-107">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Regulatory Configuration Service](rcs-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c1c48-107">For more information, see [Regulatory Configuration Service](rcs-overview.md).</span></span>
- <span data-ttu-id="c1c48-108">**Fakturowanie elektroniczne** łączy konfigurowalne formaty dla przekształceń, podpisów cyfrowych i konfigurowalnych integracji dla łączności z zewnętrznymi usługami sieci web, w tym obsługi certyfikacji i odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="c1c48-108">**Electronic Invoicing** brings together configurable formats for transformations, digital signatures, and configurable integrations for connectivity with external web services, including certification and response handling.</span></span> <span data-ttu-id="c1c48-109">Aby uzyskać więcej informacji, zajrzyj do [Faktury elektroniczne](e-invoicing-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c1c48-109">For more information, see [Electronic Invoicing](e-invoicing-service-overview.md).</span></span>
- <span data-ttu-id="c1c48-110">**Obliczanie podatków** zapewnia większą elastyczność dzięki obsłudze wielu identyfikatorów podatkowych, określaniu kodów podatkowych, projektantowi obliczania podatków i mechanizmowi wykonawczemu, który zapewnia zgodność ze złożonymi przepisami podatkowymi na całym świecie.</span><span class="sxs-lookup"><span data-stu-id="c1c48-110">**Tax Calculation** provides enhanced flexibility by supporting multiple tax IDs, tax code determination, the tax calculation designer, and a runtime engine to comply with complex tax regulations worldwide.</span></span> <span data-ttu-id="c1c48-111">Aby uzyskać więcej informacji, zobacz [Obliczanie podatku](global-tax-calcuation-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c1c48-111">For more information, see [Tax Calculation](global-tax-calcuation-service-overview.md).</span></span>

<span data-ttu-id="c1c48-112">Te usługi globalizacji zapewniają bezpośrednią integrację z następującymi usługami online Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c1c48-112">These globalization services provide out-of-box integration with the following Dynamics 365 online services.</span></span>

| <span data-ttu-id="c1c48-113">Usługi online</span><span class="sxs-lookup"><span data-stu-id="c1c48-113">Online service</span></span> | <span data-ttu-id="c1c48-114">RCS</span><span class="sxs-lookup"><span data-stu-id="c1c48-114">RCS</span></span> | <span data-ttu-id="c1c48-115">Fakturowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="c1c48-115">Electronic Invoicing</span></span> | <span data-ttu-id="c1c48-116">Obliczanie podatku (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="c1c48-116">Tax Calculation (Preview)</span></span> |
|----------------|-----|----------------------|---------------------------|
| <span data-ttu-id="c1c48-117">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="c1c48-117">Dynamics 365 Finance</span></span> | <span data-ttu-id="c1c48-118">Tak</span><span class="sxs-lookup"><span data-stu-id="c1c48-118">Yes</span></span> | <span data-ttu-id="c1c48-119">Tak</span><span class="sxs-lookup"><span data-stu-id="c1c48-119">Yes</span></span> | <span data-ttu-id="c1c48-120">Tak</span><span class="sxs-lookup"><span data-stu-id="c1c48-120">Yes</span></span> | 
| <span data-ttu-id="c1c48-121">Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c1c48-121">Dynamics 365 Supply Chain Management</span></span> | <span data-ttu-id="c1c48-122">Tak</span><span class="sxs-lookup"><span data-stu-id="c1c48-122">Yes</span></span> | <span data-ttu-id="c1c48-123">Tak</span><span class="sxs-lookup"><span data-stu-id="c1c48-123">Yes</span></span> | <span data-ttu-id="c1c48-124">Tak</span><span class="sxs-lookup"><span data-stu-id="c1c48-124">Yes</span></span> | 
| <span data-ttu-id="c1c48-125">Dynamics 365 Project Operations</span><span class="sxs-lookup"><span data-stu-id="c1c48-125">Dynamics 365 Project Operations</span></span> | <span data-ttu-id="c1c48-126">Tak</span><span class="sxs-lookup"><span data-stu-id="c1c48-126">Yes</span></span> | <span data-ttu-id="c1c48-127">Tak</span><span class="sxs-lookup"><span data-stu-id="c1c48-127">Yes</span></span> | <span data-ttu-id="c1c48-128">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c1c48-128">Not applicable</span></span> | 
| <span data-ttu-id="c1c48-129">Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c1c48-129">Dynamics 365 Commerce</span></span> | <span data-ttu-id="c1c48-130">Tak</span><span class="sxs-lookup"><span data-stu-id="c1c48-130">Yes</span></span> | <span data-ttu-id="c1c48-131">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c1c48-131">Not applicable</span></span> | <span data-ttu-id="c1c48-132">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c1c48-132">Not applicable</span></span> | 

> [!NOTE]
> <span data-ttu-id="c1c48-133">Ze względu na różnice w dostępności lokalizacji geograficznych (geograficznych) platformy Azure dla RCS konfiguracja tej usługi może spowodować przeniesienie danych klientów poza obszar geograficzny wybrany dla odpowiedniej usługi online Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c1c48-133">Because of differences in the availability of Azure geographic locations (geos) for RCS, configuration of this service might cause customer data to be transferred outside the geo that is selected for the applicable Dynamics 365 online service.</span></span> <span data-ttu-id="c1c48-134">Aby uzyskać więcej informacji, zobacz temat [Dynamics 365 oraz Power Platform: Dostępność, lokalizacja danych, język i lokalizacja](https://aka.ms/rcs/D365Productavailabilityguide).</span><span class="sxs-lookup"><span data-stu-id="c1c48-134">For more information, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/rcs/D365Productavailabilityguide).</span></span>