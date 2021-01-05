---
title: Mapowanie elementów członkowskich wymiaru elementu kosztów na wspólny zestaw elementów członkowskich wymiaru
description: Poprzez mapowanie elementów członkowskich różnych wymiarów składników kosztów na wspólny zestaw takich elementów można scalić dane we wspólny format umożliwiający efektywną analizę.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember, CAMDimensionMapping
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c6a9618a762d3af840beb05d86518b3588118e80
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446715"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a><span data-ttu-id="72fe5-103">Mapowanie elementów członkowskich wymiaru elementu kosztów na wspólny zestaw elementów członkowskich wymiaru</span><span class="sxs-lookup"><span data-stu-id="72fe5-103">Map cost element dimension members to a common set of dimension members</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72fe5-104">Poprzez mapowanie elementów członkowskich różnych wymiarów składników kosztów na wspólny zestaw takich elementów można scalić dane we wspólny format umożliwiający efektywną analizę.</span><span class="sxs-lookup"><span data-stu-id="72fe5-104">By mapping different cost element dimension members to a common set of cost element dimension members, you merge data into a common format for analysis purposes.</span></span>

<span data-ttu-id="72fe5-105">Jeśli pracujesz w globalnej firmie i musisz spełniać ustawowe wymagania księgowe, prawdopodobnie używasz wielu planów kont.</span><span class="sxs-lookup"><span data-stu-id="72fe5-105">If you're a global company and comply with statutory accounting requirements, you might use multiple charts of accounts.</span></span> <span data-ttu-id="72fe5-106">W przypadku importowania elementów członkowskich wymiarów składników kosztów z różnych planów kont możesz otrzymać chaotycznie wyglądający zbiór różnych kont.</span><span class="sxs-lookup"><span data-stu-id="72fe5-106">When you import cost element dimension members from different charts of accounts, you can end up with a mix of accounts.</span></span> <span data-ttu-id="72fe5-107">W rzeczywistości te konta mogą mieć ten sam charakter i może istnieć możliwość ich analizowania oraz przypisywania im kosztów przy użyciu wspólnego formatu.</span><span class="sxs-lookup"><span data-stu-id="72fe5-107">However, these accounts might actually have the same nature, and you might want to analyze and allocate costs for them by using a common format.</span></span>

## <a name="map-cost-element-dimension-members-to-a-common-format"></a><span data-ttu-id="72fe5-108">Mapowanie elementów członkowskich wymiarów składników kosztów na wspólny format</span><span class="sxs-lookup"><span data-stu-id="72fe5-108">Map cost element dimension members to a common format</span></span>
<span data-ttu-id="72fe5-109">W poniższym przykładzie pokazano, jak kontroler kosztów może w module Rachunek kosztów utworzyć nowy wymiar składników kosztów, który mapuje elementy członkowskie wymiarów składników kosztów ze struktur amerykańskiego planu kont i francuskiego planu kont do wspólnego zestawu elementów członkowskich wymiarów składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="72fe5-109">The following example shows how you, as a cost controller, can create a new cost element dimension in Cost accounting that maps cost element dimension members from the US chart of accounts structure and the French chart of accounts structure to a common set of cost element dimension members.</span></span> <span data-ttu-id="72fe5-110">Następnie wspólnego zestawu elementów członkowskich wymiarów składników kosztów można używać do analizowania danych kosztów z dwóch firm w księdze rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="72fe5-110">You can then use the common set of cost element dimension members to analyze cost data from the two legal entities in a cost accounting ledger.</span></span>

| <span data-ttu-id="72fe5-111">Źródło: Amerykański plan kont</span><span class="sxs-lookup"><span data-stu-id="72fe5-111">Source: US chart of accounts</span></span>                                          | <span data-ttu-id="72fe5-112">Źródło: Francuski plan kont</span><span class="sxs-lookup"><span data-stu-id="72fe5-112">Source: French chart of accounts</span></span>                                          | <span data-ttu-id="72fe5-113">Nowy wspólny zestaw elementów członkowskich wymiarów składników kosztów</span><span class="sxs-lookup"><span data-stu-id="72fe5-113">New common set of cost element dimension members</span></span>                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="72fe5-114">Elementy członkowskie wymiarów składników kosztów zaimportowane z amerykańskiego planu kont</span><span class="sxs-lookup"><span data-stu-id="72fe5-114">Imported cost element dimension members from the US chart of accounts</span></span> | <span data-ttu-id="72fe5-115">Elementy członkowskie wymiarów składników kosztów zaimportowane z francuskiego planu kont</span><span class="sxs-lookup"><span data-stu-id="72fe5-115">Imported cost element dimension members from the French chart of accounts</span></span> | <span data-ttu-id="72fe5-116">Mapowanie amerykańskich i francuskich elementów członkowskich wymiarów składników kosztów do wspólnego zestawu</span><span class="sxs-lookup"><span data-stu-id="72fe5-116">Mapping of US and French cost element dimension members to a common set</span></span> |
| <span data-ttu-id="72fe5-117">5001: Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="72fe5-117">5001: Sales</span></span>                                                           | <span data-ttu-id="72fe5-118">5001: Sprzedaż i reklama</span><span class="sxs-lookup"><span data-stu-id="72fe5-118">5001: Sales and advertising</span></span>                                               | <span data-ttu-id="72fe5-119">5000: Sprzedaż i reklama</span><span class="sxs-lookup"><span data-stu-id="72fe5-119">5000: Sales and advertising</span></span>                                             |
| <span data-ttu-id="72fe5-120">5030: Reklama</span><span class="sxs-lookup"><span data-stu-id="72fe5-120">5030: Advertising</span></span>                                                     | <span data-ttu-id="72fe5-121">6390: Zakup zapasów\*</span><span class="sxs-lookup"><span data-stu-id="72fe5-121">6390: Stock purchase\*</span></span>                                                    | <span data-ttu-id="72fe5-122">7000: Wydatki na sprzątanie</span><span class="sxs-lookup"><span data-stu-id="72fe5-122">7000: Cleaning expenses</span></span>                                                 |
| <span data-ttu-id="72fe5-123">7001: Wydatki na sprzątanie</span><span class="sxs-lookup"><span data-stu-id="72fe5-123">7001: Cleaning expenses</span></span>                                               | <span data-ttu-id="72fe5-124">7001: Wydatki na podróże służbowe</span><span class="sxs-lookup"><span data-stu-id="72fe5-124">7001: Travel expense</span></span>                                                      | <span data-ttu-id="72fe5-125">7001: Wydatki na podróżne służbowe</span><span class="sxs-lookup"><span data-stu-id="72fe5-125">7001: Travel expenses</span></span>                                                   |

<span data-ttu-id="72fe5-126">\*Francuski element członkowski wymiaru składników kosztów Zakup zapasów nie jest mapowany.</span><span class="sxs-lookup"><span data-stu-id="72fe5-126">\*The Stock purchase French cost element dimension member isn't mapped.</span></span>

## <a name="currency-conversion"></a><span data-ttu-id="72fe5-127">Konwersja walut</span><span class="sxs-lookup"><span data-stu-id="72fe5-127">Currency conversion</span></span>
<span data-ttu-id="72fe5-128">Konfiguracja różnych używanych planów kont może określać wykorzystywanie różnych walut.</span><span class="sxs-lookup"><span data-stu-id="72fe5-128">The various charts of accounts that you use might be set up to use different currencies.</span></span> <span data-ttu-id="72fe5-129">W takim przypadku koniecznie określ konwersję walut, tak aby dane kosztów były przetwarzane we właściwej walucie, zgodnie z definicją w księdze rachunku kosztów, w której są używane elementy członkowskie wymiarów składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="72fe5-129">In this case, be sure to specify a currency conversion, so that cost data is processed by using the correct currency, as defined in the cost accounting ledger where the cost element dimension members are used.</span></span> <span data-ttu-id="72fe5-130">W przykładzie powyżej jeśli w księdze rachunku kosztów są używane dolary amerykańskie (USD), należy utworzyć konwersję waluty z USD na euro (EUR) na potrzeby przetwarzania transakcji, z których wynikają mapowane elementy członkowskie wymiarów składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="72fe5-130">In the preceding example, if US dollars (USD) are used in the cost accounting ledger, you must create a currency conversion from USD to euros (EUR) to process transactions for the mapped cost element dimension members.</span></span>

## <a name="update-mappings-at-any-time"></a><span data-ttu-id="72fe5-131">Aktualizowanie mapowań w dowolnym momencie</span><span class="sxs-lookup"><span data-stu-id="72fe5-131">Update mappings at any time</span></span>
<span data-ttu-id="72fe5-132">Definicje mapowania wymiarów składników kosztów można w każdej chwili zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="72fe5-132">You can update the mapping definitions for a cost element dimension at any time.</span></span> <span data-ttu-id="72fe5-133">Ponieważ mapowania nie mają daty obowiązywania, zmiany zostaną zastosowane przy następnym przetwarzaniu transakcji kosztowych lub wykonywaniu obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="72fe5-133">Because mappings aren't date-effective, changes are applied the next time that you process cost transactions or run cost calculations.</span></span>



