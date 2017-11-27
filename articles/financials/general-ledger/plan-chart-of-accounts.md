---
title: Planowanie planu kont
description: "Ten artykuł zawiera informacje, które pomogą zaprojektować plan kont w organizacji."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 038886f0a6e1c133a33ee34725eb20352e64341a
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="fb3e9-103">Planowanie planu kont</span><span class="sxs-lookup"><span data-stu-id="fb3e9-103">Plan your chart of accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="fb3e9-104">Ten artykuł zawiera informacje, które pomogą zaprojektować plan kont w organizacji.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-104">This article provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="fb3e9-105">Do śledzenia i obsługi informacji finansowych w organizacji można skonfigurować plan kont.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="fb3e9-106">Plan kont jest to zbiór kont, które definiują ramy finansowe.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="fb3e9-107">Aby jeszcze dokładniej śledzić transakcje na tych kontach, można dodawać segmenty nazywane wymiarami finansowymi.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-107">To further track the transactions in these accounts, you can add segments, which are known as financial dimensions.</span></span> <span data-ttu-id="fb3e9-108">Na przykład, konto wydatków może zawierać wymiary finansowe o nazwie Dział, MPK oraz Cel.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-108">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="fb3e9-109">Zdefiniowane przez użytkownika reguły, nazywane strukturami kont i regułami zaawansowanymi, decydują o tym, jak te wymiary finansowe są dołączane do kont głównych i innych wymiarów finansowych, i jak wprowadzane są transakcje.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-109">User-defined rules, which are known as account structures and advanced rules, determine how financial dimensions are attached to the main accounts and other financial dimensions, and also how transactions are entered.</span></span> 

<span data-ttu-id="fb3e9-110">Plan kont jest to ustrukturalizowana lista kont księgi głównej firmy.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-110">The chart of accounts is a structured list of a legal entity’s general ledger accounts.</span></span> <span data-ttu-id="fb3e9-111">Lista służy do przygotowywania raportów finansowych dla urzędów i właścicieli.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-111">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="fb3e9-112">Konta są pogrupowane w typy i połączone w większe kategorie.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-112">The accounts are grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="fb3e9-113">Na poziomie najbardziej ogólnym, konta są pogrupowane jako przychody i koszty (konta operacyjne) oraz jako aktywa i pasywa (konta bilansowe).</span><span class="sxs-lookup"><span data-stu-id="fb3e9-113">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span> 

<span data-ttu-id="fb3e9-114">Plan kont może być udostępniany i używany przez dowolną firmę w organizacji.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-114">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="fb3e9-115">Plan kont używany przez firmę definiuje się na stronie **Księga**.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-115">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span> 

<span data-ttu-id="fb3e9-116">Oto kilka czynników, które należy uwzględnić podczas planowania struktury planu kont w organizacji:</span><span class="sxs-lookup"><span data-stu-id="fb3e9-116">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

-   <span data-ttu-id="fb3e9-117">Wymagania dotyczące raportowania w kraju/regionie, w którym mieści się organizacja</span><span class="sxs-lookup"><span data-stu-id="fb3e9-117">The reporting requirements of the country/region where your organization is based</span></span>
-   <span data-ttu-id="fb3e9-118">Wymagania dotyczące raportowania firmy</span><span class="sxs-lookup"><span data-stu-id="fb3e9-118">The reporting requirements of your legal entity</span></span>
-   <span data-ttu-id="fb3e9-119">Poziom wymaganej specyfikacji zarówno dla zewnętrznych organizacji, jak i dla Twojej organizacji</span><span class="sxs-lookup"><span data-stu-id="fb3e9-119">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="fb3e9-120">Plan kont tworzy się na stronie **Plan kont**.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-120">Create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="fb3e9-121">Konta główne można tworzyć na stronie **Plan kont** lub na stronie **Konta główne**.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-121">Main accounts can be created from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="fb3e9-122">Na kontach głównych nie należy używać żadnych znaków specjalnych, które są używane jako separatory planów kont.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-122">Your main accounts shouldn't use any special characters that are used as chart of accounts delimiters.</span></span> <span data-ttu-id="fb3e9-123">Jeśli masz znak specjalny, który jest taki sam jak separator planu kont, może wystąpić niestabilność systemu, albo do wprowadzania konta w połączeniu z wymiarem będzie trzeba zawsze używać wyszukiwania lub okna wysuwanego.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-123">If you do have a special character that is the same as your chart of accounts delimiter, you may experience instability, or the need to always use lookups or the flyout when entering account and dimension combinations.</span></span> <span data-ttu-id="fb3e9-124">Aby uzyskać więcej informacji, zobacz [Tworzenie konta głównego](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="fb3e9-124">For more information, see [Create a main account](tasks/create-account-structures.md).</span></span>


<span data-ttu-id="fb3e9-125">Dobrze jest połączyć konta główne z kategoriami konta głównego, by móc korzystać z domyślnych raportów finansowych bez konieczności wprowadzania żadnych zmian.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-125">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="fb3e9-126">Dzięki temu tworzenie i obsługa raportów staje się łatwiejsza.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-126">Therefore, you can more quickly and easily design and maintain reports.</span></span> 

<span data-ttu-id="fb3e9-127">Strona **Skonfiguruj strukturę konta** służy do tworzenia struktur kont.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-127">Use the **Configure account structures** page to create account structures.</span></span> <span data-ttu-id="fb3e9-128">Struktury kont definiują prawidłowe kombinacje.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-128">Account structures define valid combinations.</span></span> <span data-ttu-id="fb3e9-129">Kombinacje, łącznie z kontami głównymi, tworzą plan kont.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-129">The combinations, together with main accounts, form a chart of accounts.</span></span>  <span data-ttu-id="fb3e9-130">Aby uzyskać więcej informacji, zobacz [Tworzenie struktur kont](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="fb3e9-130">For more information, see [Create account structures](tasks/create-main-account.md).</span></span>

<span data-ttu-id="fb3e9-131">**Firma zastępuje**</span><span class="sxs-lookup"><span data-stu-id="fb3e9-131">**Legal entity overrides**</span></span> 

<span data-ttu-id="fb3e9-132">Nie wszystkie konta są prawidłowe dla wszystkich firm, a niektóre mogą być dostępne tylko w określonym przedziale czasu.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-132">Not all main accounts are valid for all legal entities and some may only be relevant for a specific time period.</span></span> <span data-ttu-id="fb3e9-133">W tym scenariuszu sekcja Firma zastępuje może służyć do identyfikowania firm, dla których konto główne powinno być zawieszone, właściciela oraz okresu aktywności wymiaru.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-133">In this scenario the Legal entity overrides section can be used to identify which companies the main account should be suspended for, who the owner is and the time period the dimension is active.</span></span> <span data-ttu-id="fb3e9-134">Zastąpienia na poziomie wspólnym nie mogą być bardziej restrykcyjne niż zastąpienia na poziomie firmy.</span><span class="sxs-lookup"><span data-stu-id="fb3e9-134">The overrides at the shared level cannot be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="fb3e9-135">Aby uzyskać więcej informacji, zobacz następujące tematy: [Wymiary finansowe](financial-dimensions.md)
[Tworzenie i przypisywanie struktur reguł zaawansowanych](tasks/create-assign-advanced-rule-structures.md)</span><span class="sxs-lookup"><span data-stu-id="fb3e9-135">For more information, see the following topics: [Financial dimensions](financial-dimensions.md)
[Create and assign advanced rule structures](tasks/create-assign-advanced-rule-structures.md)</span></span>




