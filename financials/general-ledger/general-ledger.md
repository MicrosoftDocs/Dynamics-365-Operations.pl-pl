---
title: "Księga główna i strona główna raportów finansowych"
description: "Moduł Księga główna służy do definiowania rekordów finansowych dla firmy i zarządzania nimi. Księga główna to rejestr zapisów debetowych i kredytowych. Te wpisy są sklasyfikowane przy użyciu kont wymienionych w planie kont."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 78f3d9c27767c089ac686f333cae3cb50c03ee18
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="general-ledger"></a><span data-ttu-id="ca5bf-105">Księga główna</span><span class="sxs-lookup"><span data-stu-id="ca5bf-105">General ledger</span></span> 

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ca5bf-106">Moduł Księga główna służy do definiowania rekordów finansowych dla firmy i zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-106">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="ca5bf-107">Księga główna to rejestr zapisów debetowych i kredytowych.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-107">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="ca5bf-108">Te wpisy są sklasyfikowane przy użyciu kont wymienionych w planie kont.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-108">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

<span data-ttu-id="ca5bf-109">Można przeprowadzić alokację lub dystrybucję kwot pieniężnych do jednego lub kilku kont albo do kombinacji kont i wymiarów opartych na regułach alokacji.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="ca5bf-110">Istnieją dwa typy alokacji: stałe i zmienne.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="ca5bf-111">Można również rozliczać transakcje między kontami księgowymi i przeszacować kwoty w walucie.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="ca5bf-112">Na koniec roku obrachunkowego należy wygenerować transakcje zamknięcia i przygotować konta do nowego roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="ca5bf-113">Funkcja konsolidacji umożliwia połączenie wyników finansowych dla kilku oddziałów firmy w jedne wyniku dla skonsolidowanej organizacji.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="ca5bf-114">Oddziały mogą znajdować się w tej samej bazie danych programu Microsoft Dynamics 365 for Finance and Operations lub w oddzielnych bazach danych.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

# <a name="sales-tax"></a><span data-ttu-id="ca5bf-115">Podatek</span><span class="sxs-lookup"><span data-stu-id="ca5bf-115">Sales tax</span></span>
<span data-ttu-id="ca5bf-116">Każda firma zbiera i płaci podatki w różnych urzędach.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-116">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="ca5bf-117">Przepisy i stawki różnią się w zależności od kraju/regionu, województwa, powiatu i miasta.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-117">The rules and rates vary by country/region, state, county, and city.</span></span> <span data-ttu-id="ca5bf-118">Ponadto reguły muszą być aktualizowane okresowo, jeśli zmieniają się wymagania urzędów skarbowych.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-118">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="ca5bf-119">Kody podatków zawierają podstawowe informacje o wysokości podatków pobranych i odprowadzonych do urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-119">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="ca5bf-120">Podczas konfigurowania kodów podatków można zdefiniować kwoty lub wartości procentowe, które muszą zostać pobrane.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-120">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="ca5bf-121">Można również zdefiniować różne metody, za pomocą których te kwoty lub wartości procentowe są stosowane do kwoty transakcji.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-121">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="ca5bf-122">Tematy w tej sekcji zawierają informacje o sposobie ustawiania kodów podatków dla metod i stawek wymaganych przez urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="ca5bf-122">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>







