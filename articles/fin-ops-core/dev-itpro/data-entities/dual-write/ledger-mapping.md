---
title: Zintegrowana księga
description: W tym temacie opisano integrację danych księgi między aplikacją Finance and Operations i innymi aplikacjami Dynamics 365 przy użyciu usługi Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 5fedcbcd8db2692214ea66b2fbab9f7381e0a622
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748524"
---
# <a name="integrated-ledger"></a><span data-ttu-id="75b6c-103">Zintegrowana księga</span><span class="sxs-lookup"><span data-stu-id="75b6c-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="75b6c-104">W aplikacji biznesowej dane księgi określają podstawowe ustawienia dotyczące sposobu prowadzenia działalności firmy.</span><span class="sxs-lookup"><span data-stu-id="75b6c-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="75b6c-105">Na przykład dane księgi opisują następujący rok obrachunkowy:, waluty transakcyjne oraz konta, z których korzysta firma.</span><span class="sxs-lookup"><span data-stu-id="75b6c-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="75b6c-106">W tym temacie opisano integrację tych podstawowych danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="75b6c-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="75b6c-107">Szablony</span><span class="sxs-lookup"><span data-stu-id="75b6c-107">Templates</span></span>

<span data-ttu-id="75b6c-108">Dane księgi zawierają kolekcję podstawowych mapowań tabel finansowych, które działają razem podczas interakcji z danymi, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="75b6c-108">Ledger data includes a collection of core financial table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="75b6c-109">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="75b6c-109">Finance and Operations apps</span></span>      | <span data-ttu-id="75b6c-110">Aplikacja oparta na modelu w systemie Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="75b6c-110">Model-driven app in Dynamics 365</span></span> | <span data-ttu-id="75b6c-111">opis</span><span class="sxs-lookup"><span data-stu-id="75b6c-111">Description</span></span>
---------------------------------|----------------------------------|------------
<span data-ttu-id="75b6c-112">Waluty</span><span class="sxs-lookup"><span data-stu-id="75b6c-112">Currencies</span></span>                       | <span data-ttu-id="75b6c-113">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="75b6c-113">transactioncurrencies</span></span>            |
<span data-ttu-id="75b6c-114">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="75b6c-114">FiscalCalendar</span></span>                   | <span data-ttu-id="75b6c-115">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="75b6c-115">msdyn\_fiscalcalendars</span></span>        |
<span data-ttu-id="75b6c-116">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="75b6c-116">FiscalCalendarYear</span></span>               | <span data-ttu-id="75b6c-117">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="75b6c-117">msdyn\_fiscalcalendaryears</span></span>        |
<span data-ttu-id="75b6c-118">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="75b6c-118">ExchRateType</span></span>                     | <span data-ttu-id="75b6c-119">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="75b6c-119">msdyn\_exchangeratetypes</span></span>        |
<span data-ttu-id="75b6c-120">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="75b6c-120">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="75b6c-121">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="75b6c-121">msdyn\_currencyexchangeratepairs</span></span>        |
<span data-ttu-id="75b6c-122">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="75b6c-122">FiscalPeriodEntity</span></span>               | <span data-ttu-id="75b6c-123">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="75b6c-123">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="75b6c-124">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="75b6c-124">MainAccountCategory</span></span>              | <span data-ttu-id="75b6c-125">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="75b6c-125">msdyn\_mainaccountcategory</span></span>        |
<span data-ttu-id="75b6c-126">Konto główne</span><span class="sxs-lookup"><span data-stu-id="75b6c-126">MainAccount</span></span>                      | <span data-ttu-id="75b6c-127">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="75b6c-127">msdyn\_mainaccounts</span></span>        |
<span data-ttu-id="75b6c-128">Księga</span><span class="sxs-lookup"><span data-stu-id="75b6c-128">Ledger</span></span>                           | <span data-ttu-id="75b6c-129">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="75b6c-129">msdyn\_ledgers</span></span>        |
<span data-ttu-id="75b6c-130">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="75b6c-130">ExchangeRates</span></span>                    | <span data-ttu-id="75b6c-131">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="75b6c-131">msdyn\_currencyexchangerates</span></span>        |
<span data-ttu-id="75b6c-132">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="75b6c-132">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="75b6c-133">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="75b6c-133">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="75b6c-134">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="75b6c-134">DimensionAttributeEntity</span></span>         | <span data-ttu-id="75b6c-135">msdyn\_dimensionattributes</span><span class="sxs-lookup"><span data-stu-id="75b6c-135">msdyn\_dimensionattributes</span></span>        |
<span data-ttu-id="75b6c-136">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="75b6c-136">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="75b6c-137">msdyn\_financialdimensionformats</span><span class="sxs-lookup"><span data-stu-id="75b6c-137">msdyn\_financialdimensionformats</span></span>        |
<span data-ttu-id="75b6c-138">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="75b6c-138">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="75b6c-139">msdyn\_chartofaccounts</span><span class="sxs-lookup"><span data-stu-id="75b6c-139">msdyn\_chartofaccounts</span></span>        |


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]