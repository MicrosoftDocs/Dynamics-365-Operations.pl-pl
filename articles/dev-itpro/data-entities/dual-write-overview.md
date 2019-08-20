---
title: Integracja danych prawie czasu rzeczywistego między programami Finance and Operations i Common Data Service.
description: Ten temat zawiera omówienie integracji między Microsoft Dynamics 365 for Finance and Operations i Common Data Service.
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
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797235"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a><span data-ttu-id="013ee-103">Integracja danych prawie czasu rzeczywistego między programami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="013ee-103">Near-real-time data integration between Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="013ee-104">W obecnym świecie cyfrowym ekosystemy biznesowe wykorzystują pakiet Microsoft Dynamics 365 w całości.</span><span class="sxs-lookup"><span data-stu-id="013ee-104">In the current digital world, business ecosystems use the Microsoft Dynamics 365 suite as a whole.</span></span> <span data-ttu-id="013ee-105">Ponieważ dane pochodzące od osób, klientów, z operacji i urządzeń Internetu rzeczy (IoT) trafiają do jednego źródła, istnieje szansa na tworzenie cyfrowych pętli sprzężenia zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="013ee-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="013ee-106">Aby osiągnąć ten komfort, niezbędna jest integracja między Dynamics 365 for Finance and Operations i Dynamics 365 pod kątem aplikacji Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="013ee-106">To achieve this experience, integration between Dynamics 365 for Finance and Operations and Dynamics 365 for Customer Engagement applications is essential.</span></span> <span data-ttu-id="013ee-107">Aplikacje Customer Engagement są zbudowane na Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="013ee-107">Customer Engagement applications are built on top of Common Data Service.</span></span> <span data-ttu-id="013ee-108">Integracja między danymi programu Finance and Operations z Common Data Service pozwala aplikacjom Customer Engagement komunikować się w sposób spójny i płynny z programem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="013ee-108">Integration between Finance and Operations data with Common Data Service lets Customer Engagement applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="013ee-109">Finance and Operations i Common Data Service zapewniają synchronizacje niemal w czasie rzeczywistym między aplikacjami Finance and Operations i Customer Engagement za pomocą schematu podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="013ee-109">Finance and Operations and Common Data Service provide near-real-time data synchronization between Finance and Operations and Customer Engagement applications via a dual-write framework.</span></span> <span data-ttu-id="013ee-110">Zasięg jest szeroki i obejmuje 28 obszarów Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="013ee-110">The coverage is broad and spans 28 surface areas of Finance and Operations.</span></span> <span data-ttu-id="013ee-111">Celem jest zapewnienie środowiska użytkownika „One Dynamics 365” dzięki bezproblemowym przepływom danych, które łączą procesy biznesowe między aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="013ee-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagram poglądowy architektury](media/dual-write-overview.jpg)

<span data-ttu-id="013ee-113">Dla klientów dostępne są następujące propozycje wartości:</span><span class="sxs-lookup"><span data-stu-id="013ee-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="013ee-114">Hierarchia organizacyjna w usłudze Common Data Service</span><span class="sxs-lookup"><span data-stu-id="013ee-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="013ee-115">Pojęcie firmy w usługach Common Data Service</span><span class="sxs-lookup"><span data-stu-id="013ee-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="013ee-116">Zintegrowane dane główne odbiorcy</span><span class="sxs-lookup"><span data-stu-id="013ee-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="013ee-117">Zintegrowane dane główne dostawcy</span><span class="sxs-lookup"><span data-stu-id="013ee-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="013ee-118">Ujednolicony produkt główny</span><span class="sxs-lookup"><span data-stu-id="013ee-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="013ee-119">Wymagania systemowe</span><span class="sxs-lookup"><span data-stu-id="013ee-119">System requirements</span></span>

<span data-ttu-id="013ee-120">Synchroniczne, dwukierunkowe przepływy danych niemal w czasie rzeczywistym wymagają następujących wersji:</span><span class="sxs-lookup"><span data-stu-id="013ee-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="013ee-121">Microsoft Dynamics 365 for Finance and Operations w wersji 10.0.4 (lipiec 2019) z aktualizacją platformy 28 lub nowszą</span><span class="sxs-lookup"><span data-stu-id="013ee-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="013ee-122">Microsoft Dynamics 365 for Customer Engagement, wersja platformy 9.1 (4.2) lub nowsza</span><span class="sxs-lookup"><span data-stu-id="013ee-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="013ee-123">Instrukcje konfiguracji</span><span class="sxs-lookup"><span data-stu-id="013ee-123">Setup instructions</span></span>

<span data-ttu-id="013ee-124">Wykonaj następujące kroki, aby skonfigurować integrację między programami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="013ee-124">Follow these steps to set up integration between Finance and Operations and Common Data Service.</span></span>
    
1. <span data-ttu-id="013ee-125">Aby skonfigurować system podwójnego zapisu, zobacz [szczegółowy poradnik](https://aka.ms/dualwrite-docs) na temat wprowadzenia podwójnego zapisu w wersji próbnej.</span><span class="sxs-lookup"><span data-stu-id="013ee-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="013ee-126">Pobierz i zainstaluj rozwiązanie z grupy Yammer [Integracja Finance and Operations, Common Data Service i Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096).</span><span class="sxs-lookup"><span data-stu-id="013ee-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="013ee-127">Pakiet zawiera pięć rozwiązań:</span><span class="sxs-lookup"><span data-stu-id="013ee-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="013ee-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="013ee-128">Dynamics365Company</span></span>
    + <span data-ttu-id="013ee-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="013ee-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="013ee-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="013ee-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="013ee-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="013ee-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="013ee-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="013ee-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="013ee-133">Postępuj zgodnie z kolejnością [wykonywania synchronizacji początkowych danych referencyjnych](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="013ee-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="013ee-134">Jeśli wystąpią problemy z synchronizacją podwójnego zapisu, zobacz [Przewodnik rozwiązywania problemów z integracją danych](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="013ee-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="013ee-135">Nie można uruchomić równolegle podwójnego zapisu i [Prospekt do gotówki](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="013ee-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="013ee-136">Jeśli korzystasz z rozwiązania Prospekt na gotówkę, musisz ją odinstalować.</span><span class="sxs-lookup"><span data-stu-id="013ee-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="013ee-137">Należy również wyłączyć szablony podwójnego zapisu odbiorcy i dostawcy, które są częścią rozwiązania Prospektem na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="013ee-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
