---
title: Księga główna i strona główna raportów finansowych
description: Moduł Księga główna służy do definiowania rekordów finansowych dla firmy i zarządzania nimi.
author: ShylaThompson
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b6683107f4b2dbe36af78749612ce950ea19582
ms.sourcegitcommit: afab5269613d1d1dfd79cd39370b747dee13d3fc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2019
ms.locfileid: "403244"
---
# <a name="general-ledger"></a><span data-ttu-id="7e013-103">Księga główna</span><span class="sxs-lookup"><span data-stu-id="7e013-103">General ledger</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7e013-104">Moduł Księga główna służy do definiowania rekordów finansowych dla firmy i zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="7e013-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="7e013-105">Księga główna to rejestr zapisów debetowych i kredytowych.</span><span class="sxs-lookup"><span data-stu-id="7e013-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="7e013-106">Te wpisy są sklasyfikowane przy użyciu kont wymienionych w planie kont.</span><span class="sxs-lookup"><span data-stu-id="7e013-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="7e013-107">Planowanie planu kont</span><span class="sxs-lookup"><span data-stu-id="7e013-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="7e013-108">Typy kont głównych</span><span class="sxs-lookup"><span data-stu-id="7e013-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="7e013-109">Można przeprowadzić alokację lub dystrybucję kwot pieniężnych do jednego lub kilku kont albo do kombinacji kont i wymiarów opartych na regułach alokacji.</span><span class="sxs-lookup"><span data-stu-id="7e013-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="7e013-110">Istnieją dwa typy alokacji: stałe i zmienne.</span><span class="sxs-lookup"><span data-stu-id="7e013-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="7e013-111">Można również rozliczać transakcje między kontami księgowymi i przeszacować kwoty w walucie.</span><span class="sxs-lookup"><span data-stu-id="7e013-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="7e013-112">Na koniec roku obrachunkowego należy wygenerować transakcje zamknięcia i przygotować konta do nowego roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="7e013-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="7e013-113">Funkcja konsolidacji umożliwia połączenie wyników finansowych dla kilku oddziałów firmy w jedne wyniku dla skonsolidowanej organizacji.</span><span class="sxs-lookup"><span data-stu-id="7e013-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="7e013-114">Oddziały mogą znajdować się w tej samej bazie danych Microsoft Dynamics 365 for Finance and Operations lub w oddzielnych bazach danych.</span><span class="sxs-lookup"><span data-stu-id="7e013-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

- [<span data-ttu-id="7e013-115">Omówienie konsolidacji i eliminacji</span><span class="sxs-lookup"><span data-stu-id="7e013-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="7e013-116">Salda głównego konta księgowego</span><span class="sxs-lookup"><span data-stu-id="7e013-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="7e013-117">Wymiary finansowe</span><span class="sxs-lookup"><span data-stu-id="7e013-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="7e013-118">[![Proces biznesowy](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="7e013-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="7e013-119">Podatek</span><span class="sxs-lookup"><span data-stu-id="7e013-119">Sales tax</span></span>
<span data-ttu-id="7e013-120">Każda firma zbiera i płaci podatki w różnych urzędach.</span><span class="sxs-lookup"><span data-stu-id="7e013-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="7e013-121">Przepisy i stawki różnią się w zależności od kraju/regionu, województwa, powiatu i miasta.</span><span class="sxs-lookup"><span data-stu-id="7e013-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="7e013-122">Ponadto reguły muszą być aktualizowane okresowo, jeśli zmieniają się wymagania urzędów skarbowych.</span><span class="sxs-lookup"><span data-stu-id="7e013-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="7e013-123">Kody podatków zawierają podstawowe informacje o wysokości podatków pobranych i odprowadzonych do urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="7e013-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="7e013-124">Podczas konfigurowania kodów podatków można zdefiniować kwoty lub wartości procentowe, które muszą zostać pobrane.</span><span class="sxs-lookup"><span data-stu-id="7e013-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="7e013-125">Można również zdefiniować różne metody, za pomocą których te kwoty lub wartości procentowe są stosowane do kwoty transakcji.</span><span class="sxs-lookup"><span data-stu-id="7e013-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="7e013-126">Tematy w tej sekcji zawierają informacje o sposobie ustawiania kodów podatków dla metod i stawek wymaganych przez urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="7e013-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="7e013-127">Omówienie podatku</span><span class="sxs-lookup"><span data-stu-id="7e013-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="7e013-128">Stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania</span><span class="sxs-lookup"><span data-stu-id="7e013-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="7e013-129">Reguły płatności podatku i zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="7e013-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="7e013-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7e013-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="7e013-131">Nowe i opracowywane funkcje</span><span class="sxs-lookup"><span data-stu-id="7e013-131">What's new and in development</span></span>

<span data-ttu-id="7e013-132">Przejdź do [Informacji o wersji Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158), aby zobaczyć, jakie nowe funkcje zostały zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="7e013-132">Go to the [Microsoft Dynamics 365 Release Notes](https://go.microsoft.com/fwlink/?linkid=2010158) to see what new features have been planned.</span></span> 

#### <a name="blogs"></a><span data-ttu-id="7e013-133">Blogi</span><span class="sxs-lookup"><span data-stu-id="7e013-133">Blogs</span></span>

<span data-ttu-id="7e013-134">Opinie, wiadomości i inne informacje możesz znaleźć w blogu usługi [Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise)oraz blogu rozwiązania Financials usługi [Microsoft Dynamics 365 Finance and Operations](https://community.dynamics.com/365/financeandoperations/b/financials).</span><span class="sxs-lookup"><span data-stu-id="7e013-134">You can find opinions, news, and other information on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) and the [Microsoft Dynamics 365 Finance and Operations - Financials blog](https://community.dynamics.com/365/financeandoperations/b/financials).</span></span>

<span data-ttu-id="7e013-135">[Blog społeczności partnerów Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) stanowi doskonały zasób dla partnerów zajmujących się oprogramowaniem Microsoft Dynamics, który zawiera informacje o nowościach i popularnych rozwiązaniach działu MBS Operations.</span><span class="sxs-lookup"><span data-stu-id="7e013-135">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

### <a name="videos"></a><span data-ttu-id="7e013-136">Filmy</span><span class="sxs-lookup"><span data-stu-id="7e013-136">Videos</span></span>

<span data-ttu-id="7e013-137">Obejrzyj filmy instruktażowe w [kanale YouTube rozwiązania Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="7e013-137">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="7e013-138">Blogi społeczności</span><span class="sxs-lookup"><span data-stu-id="7e013-138">Community blogs</span></span>

- [<span data-ttu-id="7e013-139">Co należy wiedzieć o księdze w Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7e013-139">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)

