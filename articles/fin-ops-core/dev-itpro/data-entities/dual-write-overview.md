---
title: Integracja danych w czasie zbliżonym do rzeczywistego z Common Data Service
description: W tym temacie przedstawiono przegląd integracji danych produktu między Finance and Operations i Common Data Service.
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
ms.openlocfilehash: d70bce4e47c05a7974c1b974fdca17682e5370aa
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550864"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="6cc52-103">Integracja danych w czasie zbliżonym do rzeczywistego z Common Data Service</span><span class="sxs-lookup"><span data-stu-id="6cc52-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="6cc52-104">W obecnym świecie cyfrowym ekosystemy biznesowe wykorzystują aplikacje Microsoft Dynamics 365 w całości.</span><span class="sxs-lookup"><span data-stu-id="6cc52-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="6cc52-105">Ponieważ dane pochodzące od osób, klientów, z operacji i urządzeń Internetu rzeczy (IoT) trafiają do jednego źródła, istnieje szansa na tworzenie cyfrowych pętli sprzężenia zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="6cc52-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="6cc52-106">Aby osiągnąć ten komfort, niezbędna jest integracja między aplikacjami Finance and Operations i aplikacjami Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6cc52-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="6cc52-107">Niektóre Customer Engagement są zbudowane na Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6cc52-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="6cc52-108">Integracja między danymi aplikacji Finance and Operations z Common Data Service pozwala innym aplikacjom komunikować się w sposób spójny i płynny z rozwiązaniem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6cc52-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="6cc52-109">Aplikacje Finance and Operations i Common Data Service zapewniają synchronizacje niemal w czasie rzeczywistym między aplikacjami Finance and Operations i innymi aplikacjami Dynamics 365 za pomocą schematu podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="6cc52-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="6cc52-110">Zasięg jest szeroki i obejmuje 28 obszarów aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6cc52-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="6cc52-111">Celem jest zapewnienie środowiska użytkownika „One Dynamics 365” dzięki bezproblemowym przepływom danych, które łączą procesy biznesowe między aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="6cc52-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagram poglądowy architektury](media/dual-write-overview.jpg)

<span data-ttu-id="6cc52-113">Dla klientów dostępne są następujące propozycje wartości:</span><span class="sxs-lookup"><span data-stu-id="6cc52-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="6cc52-114">Hierarchia organizacyjna w usłudze Common Data Service</span><span class="sxs-lookup"><span data-stu-id="6cc52-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="6cc52-115">Pojęcie firmy w usługach Common Data Service</span><span class="sxs-lookup"><span data-stu-id="6cc52-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="6cc52-116">Zintegrowane dane główne odbiorcy</span><span class="sxs-lookup"><span data-stu-id="6cc52-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="6cc52-117">Zintegrowane dane główne dostawcy</span><span class="sxs-lookup"><span data-stu-id="6cc52-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="6cc52-118">Ujednolicony produkt główny</span><span class="sxs-lookup"><span data-stu-id="6cc52-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="6cc52-119">Wymagania systemowe</span><span class="sxs-lookup"><span data-stu-id="6cc52-119">System requirements</span></span>

<span data-ttu-id="6cc52-120">Synchroniczne, dwukierunkowe przepływy danych niemal w czasie rzeczywistym wymagają następujących wersji:</span><span class="sxs-lookup"><span data-stu-id="6cc52-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="6cc52-121">Microsoft Dynamics 365 for Finance and Operations w wersji 10.0.4 (lipiec 2019) z aktualizacją platformy 28 lub nowszą</span><span class="sxs-lookup"><span data-stu-id="6cc52-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="6cc52-122">Microsoft Dynamics 365 for Customer Engagement, wersja platformy 9.1 (4.2) lub nowsza</span><span class="sxs-lookup"><span data-stu-id="6cc52-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="6cc52-123">Instrukcje konfiguracji</span><span class="sxs-lookup"><span data-stu-id="6cc52-123">Setup instructions</span></span>

<span data-ttu-id="6cc52-124">Wykonaj następujące kroki, aby skonfigurować integrację między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6cc52-124">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="6cc52-125">Aby skonfigurować system podwójnego zapisu, zobacz [szczegółowy poradnik](https://aka.ms/dualwrite-docs) na temat wprowadzenia podwójnego zapisu w wersji próbnej.</span><span class="sxs-lookup"><span data-stu-id="6cc52-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="6cc52-126">Pobierz i zainstaluj rozwiązanie z grupy Yammer [Integracja Finance and Operations, Common Data Service i Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096).</span><span class="sxs-lookup"><span data-stu-id="6cc52-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="6cc52-127">Pakiet zawiera pięć rozwiązań:</span><span class="sxs-lookup"><span data-stu-id="6cc52-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="6cc52-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="6cc52-128">Dynamics365Company</span></span>
    + <span data-ttu-id="6cc52-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="6cc52-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="6cc52-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="6cc52-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="6cc52-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="6cc52-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="6cc52-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="6cc52-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="6cc52-133">Postępuj zgodnie z kolejnością [wykonywania synchronizacji początkowych danych referencyjnych](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="6cc52-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="6cc52-134">Jeśli wystąpią problemy z synchronizacją podwójnego zapisu, zobacz [Przewodnik rozwiązywania problemów z integracją danych](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="6cc52-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cc52-135">Nie można uruchomić równolegle podwójnego zapisu i [Prospekt do gotówki](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="6cc52-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="6cc52-136">Jeśli korzystasz z rozwiązania Prospekt na gotówkę, musisz ją odinstalować.</span><span class="sxs-lookup"><span data-stu-id="6cc52-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="6cc52-137">Należy również wyłączyć szablony podwójnego zapisu odbiorcy i dostawcy, które są częścią rozwiązania Prospektem na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="6cc52-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
