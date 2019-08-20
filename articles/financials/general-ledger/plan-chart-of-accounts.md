---
title: Planowanie planu kont
description: Ten temat zawiera informacje, które pomogą zaprojektować plan kont w organizacji.
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26f7ca1fa539fb0cf69a7759e92c5e735bd41211
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846782"
---
# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="0cbd0-103">Planowanie planu kont</span><span class="sxs-lookup"><span data-stu-id="0cbd0-103">Plan your chart of accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0cbd0-104">Ten temat zawiera informacje, które pomogą zaprojektować plan kont w organizacji.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-104">This topic provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="0cbd0-105">Do śledzenia i obsługi informacji finansowych w organizacji można skonfigurować plan kont.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="0cbd0-106">Plan kont jest to zbiór kont, które definiują ramy finansowe.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="0cbd0-107">Aby jeszcze dokładniej śledzić transakcje na tych kontach, można dodawać</span><span class="sxs-lookup"><span data-stu-id="0cbd0-107">To further track the transactions in these accounts, you can add segments.</span></span> <span data-ttu-id="0cbd0-108">segmenty nazywane wymiarami finansowymi.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-108">These segments are known as financial dimensions.</span></span> <span data-ttu-id="0cbd0-109">Na przykład, konto wydatków może zawierać wymiary finansowe o nazwie Dział, MPK oraz Cel.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-109">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="0cbd0-110">Zdefiniowane przez użytkownika reguły decydują o tym, jak te wymiary finansowe są dołączane do kont głównych i innych wymiarów finansowych, i jak wprowadzane są transakcje.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-110">User-defined rules determine how financial dimensions are attached to the main accounts and to other financial dimensions, and also how transactions are entered.</span></span> <span data-ttu-id="0cbd0-111">Te zdefiniowane przez użytkownika reguły są nazywane strukturami kont i regułami zaawansowanymi.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-111">These user-defined rules are known as account structures and advanced rules.</span></span>

<span data-ttu-id="0cbd0-112">Plan kont jest to usystematyzowana lista kont księgi głównej firmy.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-112">The chart of accounts is a structured list of a legal entity's general ledger accounts.</span></span> <span data-ttu-id="0cbd0-113">Lista służy do przygotowywania raportów finansowych dla urzędów i właścicieli.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-113">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="0cbd0-114">Konta są najpierw grupowane w typy, a następnie łączone w większe kategorie.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-114">The accounts are first grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="0cbd0-115">Na poziomie najbardziej ogólnym, konta są pogrupowane jako przychody i koszty (konta operacyjne) oraz jako aktywa i pasywa (konta bilansowe).</span><span class="sxs-lookup"><span data-stu-id="0cbd0-115">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span>

<span data-ttu-id="0cbd0-116">Plan kont może być udostępniany i używany przez dowolną firmę w organizacji.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-116">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="0cbd0-117">Plan kont używany przez firmę definiuje się na stronie **Księga**.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-117">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span>

<span data-ttu-id="0cbd0-118">Oto kilka czynników, które należy uwzględnić podczas planowania struktury planu kont w organizacji:</span><span class="sxs-lookup"><span data-stu-id="0cbd0-118">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

- <span data-ttu-id="0cbd0-119">Wymagania dotyczące raportowania w kraju lub regionie, w którym mieści się organizacja</span><span class="sxs-lookup"><span data-stu-id="0cbd0-119">The reporting requirements of the country or region where your organization is based</span></span>
- <span data-ttu-id="0cbd0-120">Wymagania dotyczące raportowania firmy</span><span class="sxs-lookup"><span data-stu-id="0cbd0-120">The reporting requirements of your legal entity</span></span>
- <span data-ttu-id="0cbd0-121">Poziom wymaganej specyfikacji zarówno dla zewnętrznych organizacji, jak i dla Twojej organizacji</span><span class="sxs-lookup"><span data-stu-id="0cbd0-121">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="0cbd0-122">Plan kont tworzy się na stronie **Plan kont**.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-122">You create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="0cbd0-123">Konta główne można tworzyć na stronie **Plan kont** lub na stronie **Konta główne**.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-123">You can create main accounts from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="0cbd0-124">Na kontach głównych nie należy używać żadnych znaków specjalnych, które są używane jako separatory planów kont.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-124">Your main accounts shouldn't use any special characters that are used as delimiters for chart of accounts.</span></span> <span data-ttu-id="0cbd0-125">W przeciwnym razie może wystąpić niestabilność lub zawsze trzeba będzie używać wyszukiwań albo okna dialogowego podczas wprowadzania kombinacji kont i wymiarów.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-125">Otherwise, you might experience instability, or you might always have to use lookups or the dialog box when you enter combinations of accounts and dimensions.</span></span> <span data-ttu-id="0cbd0-126">Aby uzyskać więcej informacji, zobacz [Tworzenie konta głównego](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="0cbd0-126">For more information, see [Create a main account](tasks/create-main-account.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0cbd0-127">W programie Microsoft Dynamics for Finance and Operations w wersji 8.0 (z kwietnia 2018 r.) można zmodyfikować separator planu kont ze strony **Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-127">In Microsoft Dynamics for Finance and Operations version 8.0 (April 2018), you can modify the chart of accounts delimiter from the **General ledger parameters** page.</span></span>

<span data-ttu-id="0cbd0-128">Dobrze jest połączyć konta główne z kategoriami konta głównego, by móc korzystać z domyślnych raportów finansowych bez konieczności wprowadzania żadnych zmian.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-128">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="0cbd0-129">Dzięki temu tworzenie i obsługa raportów staje się łatwiejsza.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-129">Therefore, you can more quickly and easily design and maintain reports.</span></span>

<span data-ttu-id="0cbd0-130">Struktury kont tworzy się na stronie **Skonfiguruj strukturę konta**.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-130">You create account structures on the **Configure account structures** page.</span></span> <span data-ttu-id="0cbd0-131">Struktury kont definiują prawidłowe kombinacje.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-131">Account structures define valid combinations.</span></span> <span data-ttu-id="0cbd0-132">Te kombinacje, łącznie z kontami głównymi, tworzą plan kont.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-132">These combinations, together with main accounts, form a chart of accounts.</span></span> <span data-ttu-id="0cbd0-133">Aby uzyskać więcej informacji, zobacz [Tworzenie struktur kont](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="0cbd0-133">For more information, see [Create account structures](tasks/create-account-structures.md).</span></span>

<span data-ttu-id="0cbd0-134">**Firma zastępuje**</span><span class="sxs-lookup"><span data-stu-id="0cbd0-134">**Legal entity overrides**</span></span>

<span data-ttu-id="0cbd0-135">Nie wszystkie konta główne są prawidłowe dla wszystkich firm, a niektóre konta główne mogą działać tylko w określonym przedziale czasu.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-135">Not all main accounts are valid for all legal entities, and some main account might be relevant only for a specific period.</span></span> <span data-ttu-id="0cbd0-136">W tym scenariuszu można w sekcji **Firma zastępuje** wskazać firmy, dla których konto główne powinno być zawieszone, właściciela oraz okres aktywności wymiaru.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-136">In this scenario, you can use the **Legal entity overrides** section to identify the companies that the main account should be suspended for, the owner, and the period when the dimension is active.</span></span> <span data-ttu-id="0cbd0-137">Zastąpienia na poziomie wspólnym nie mogą być bardziej restrykcyjne niż zastąpienia na poziomie firmy.</span><span class="sxs-lookup"><span data-stu-id="0cbd0-137">The overrides at the shared level can't be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="0cbd0-138">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="0cbd0-138">For more information, see the following topics:</span></span>

- [<span data-ttu-id="0cbd0-139">Wymiary finansowe</span><span class="sxs-lookup"><span data-stu-id="0cbd0-139">Financial dimensions</span></span>](financial-dimensions.md)
- [<span data-ttu-id="0cbd0-140">Tworzenie i przypisywanie struktur reguł zaawansowanych</span><span class="sxs-lookup"><span data-stu-id="0cbd0-140">Create and assign advanced rule structures</span></span>](tasks/create-assign-advanced-rule-structures.md)
