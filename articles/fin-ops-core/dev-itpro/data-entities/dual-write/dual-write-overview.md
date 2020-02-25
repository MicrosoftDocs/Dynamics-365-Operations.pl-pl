---
title: Integracja danych w czasie zbliżonym do rzeczywistego z Common Data Service
description: Ten temat zawiera omówienie integracji między Finance and Operations i Common Data Service.
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
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019962"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="a3a8a-103">Integracja danych w czasie zbliżonym do rzeczywistego z Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a3a8a-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="a3a8a-104">W obecnym świecie cyfrowym ekosystemy biznesowe wykorzystują aplikacje Microsoft Dynamics 365 w całości.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="a3a8a-105">Ponieważ dane pochodzące od osób, klientów, z operacji i urządzeń Internetu rzeczy (IoT) trafiają do jednego źródła, istnieje szansa na tworzenie cyfrowych pętli sprzężenia zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="a3a8a-106">Aby osiągnąć ten komfort, niezbędna jest integracja między aplikacjami Finance and Operations i aplikacjami Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="a3a8a-107">Niektóre Customer Engagement są zbudowane na Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="a3a8a-108">Integracja między aplikacjami Finance and Operations z innymi aplikacjami Common Data Service pozwala innym aplikacją komunikować się płynnie i jasno z Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="a3a8a-109">Aplikacje Finance and Operations i Common Data Service zapewniają synchronizacje niemal w czasie rzeczywistym między aplikacjami Finance and Operations i innymi aplikacjami Dynamics 365 za pomocą schematu podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="a3a8a-110">Zasięg jest szeroki i obejmuje 28 obszarów aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="a3a8a-111">Celem jest zapewnienie środowiska użytkownika „One Dynamics 365” dzięki bezproblemowym przepływom danych, które łączą procesy biznesowe między aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagram poglądowy architektury](media/dual-write-overview.jpg)

<span data-ttu-id="a3a8a-113">Dla klientów dostępne są następujące propozycje:</span><span class="sxs-lookup"><span data-stu-id="a3a8a-113">The following value propositions are available:</span></span>

+ [<span data-ttu-id="a3a8a-114">Hierarchia organizacyjna w usłudze Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a3a8a-114">Organization hierarchy in Common Data Service</span></span>](organization-mapping.md)
+ [<span data-ttu-id="a3a8a-115">Pojęcie firmy w usługach Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a3a8a-115">Company concept in Common Data Service</span></span>](company-data.md)
+ [<span data-ttu-id="a3a8a-116">Zintegrowane dane główne odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a3a8a-116">Integrated customer master</span></span>](customer-mapping.md)
+ [<span data-ttu-id="a3a8a-117">Zintegrowana księga</span><span class="sxs-lookup"><span data-stu-id="a3a8a-117">Integrated ledger</span></span>](ledger-mapping.md)
+ [<span data-ttu-id="a3a8a-118">Ujednolicone działanie produktu</span><span class="sxs-lookup"><span data-stu-id="a3a8a-118">Unified product experience</span></span>](product-mapping.md)
+ [<span data-ttu-id="a3a8a-119">Zintegrowane dane główne dostawcy</span><span class="sxs-lookup"><span data-stu-id="a3a8a-119">Integrated vendor master</span></span>](vendor-mapping.md)
+ [<span data-ttu-id="a3a8a-120">Zintegrowane oddziały i magazyny</span><span class="sxs-lookup"><span data-stu-id="a3a8a-120">Integrated sites and warehouses</span></span>](sites-warehouses-mapping.md)
+ [<span data-ttu-id="a3a8a-121">Zintegrowane dane główne podatków</span><span class="sxs-lookup"><span data-stu-id="a3a8a-121">Integrated tax master</span></span>](tax-mapping.md)

## <a name="system-requirements"></a><span data-ttu-id="a3a8a-122">Wymagania systemowe</span><span class="sxs-lookup"><span data-stu-id="a3a8a-122">System requirements</span></span>

<span data-ttu-id="a3a8a-123">Synchroniczne, dwukierunkowe przepływy danych niemal w czasie rzeczywistym wymagają następujących wersji:</span><span class="sxs-lookup"><span data-stu-id="a3a8a-123">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="a3a8a-124">Microsoft Dynamics 365 for Finance and Operations w wersji 10.0.4 (lipiec 2019) z aktualizacją platformy 28 lub nowszą</span><span class="sxs-lookup"><span data-stu-id="a3a8a-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="a3a8a-125">Microsoft Dynamics 365 for Customer Engagement, wersja platformy 9.1 (4.2) lub nowsza</span><span class="sxs-lookup"><span data-stu-id="a3a8a-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="a3a8a-126">Instrukcje konfiguracji</span><span class="sxs-lookup"><span data-stu-id="a3a8a-126">Setup instructions</span></span>

<span data-ttu-id="a3a8a-127">Aby skonfigurować integrację między aplikacjami Finance and Operations i Common Data Service, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a3a8a-127">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="a3a8a-128">Aby skonfigurować system podwójnego zapisu, zobacz [szczegółowy poradnik](https://aka.ms/dualwrite-docs) na temat wprowadzenia podwójnego zapisu w wersji próbnej.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-128">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="a3a8a-129">Pobierz i zainstaluj rozwiązanie z grupy [integracji aplikacji Fin Ops i CDS/CE za pośrednictwem Dual-Write](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) w serwisie Yammer.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-129">Download and install the solution from the [Fin Ops and CDS/CE Integration via Dual-Write](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="a3a8a-130">Pakiet zawiera pięć rozwiązań:</span><span class="sxs-lookup"><span data-stu-id="a3a8a-130">The package contains five solutions:</span></span>

    + <span data-ttu-id="a3a8a-131">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="a3a8a-131">Dynamics365Company</span></span>
    + <span data-ttu-id="a3a8a-132">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="a3a8a-132">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="a3a8a-133">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="a3a8a-133">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="a3a8a-134">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="a3a8a-134">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="a3a8a-135">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="a3a8a-135">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="a3a8a-136">Postępuj zgodnie z kolejnością [wykonywania synchronizacji początkowych danych referencyjnych](initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="a3a8a-136">Follow the execution order for [synchronizing initial reference data](initial-sync.md).</span></span>
4. <span data-ttu-id="a3a8a-137">Jeśli wystąpią problemy z synchronizacją podwójnego zapisu, zobacz [Przewodnik rozwiązywania problemów z integracją danych](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="a3a8a-137">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3a8a-138">Nie można uruchomić równolegle podwójnego zapisu i [Prospekt do gotówki](../../../../supply-chain/sales-marketing/prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="a3a8a-138">You can’t run dual-write and [Prospect to cash](../../../../supply-chain/sales-marketing/prospect-to-cash.md) side-by-side.</span></span> <span data-ttu-id="a3a8a-139">Jeśli korzystasz z rozwiązania Prospekt na gotówkę, musisz ją odinstalować.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-139">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="a3a8a-140">Należy również wyłączyć szablony podwójnego zapisu odbiorcy i dostawcy, które są częścią rozwiązania Prospektem na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="a3a8a-140">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
