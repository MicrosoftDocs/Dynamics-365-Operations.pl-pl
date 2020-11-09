---
title: Obszar roboczy zarządzania rachunkami bankowymi
description: Ten temat zawiera informacje o obszarze roboczym Zarządzanie rachunkami bankowymi. Ten obszar roboczy pokazuje informacje dotyczące firmowych kont bankowych. Zawiera widok Podsumowanie i stronę Analizy. Widok Podsumowanie zawiera kafelki podsumowań, informacje o rachunkach bankowych, wykres salda i pokrewne informacje. Strona Analizy wykorzystuje funkcje programu Microsoft Power BI, aby pokazywać wizualizacje dotyczące sald na rachunkach bankowych.
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 4b7d2da346880278f684a796f2d649e7da52b647
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097193"
---
# <a name="bank-management-workspace"></a><span data-ttu-id="eff48-106">Obszar roboczy zarządzania kontami bankowymi</span><span class="sxs-lookup"><span data-stu-id="eff48-106">Bank management workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eff48-107">Obszar roboczy **Zarządzanie rachunkami bankowymi** zawiera informacje dotyczące firmowych kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="eff48-107">The **Bank management** workspace shows information that is related to company bank accounts.</span></span> <span data-ttu-id="eff48-108">Ten obszar roboczy zawiera widok **Podsumowanie** i stronę **Analizy**.</span><span class="sxs-lookup"><span data-stu-id="eff48-108">This workspace includes a **Summary** view and an **Analytics** page.</span></span> <span data-ttu-id="eff48-109">Widok **Podsumowanie** zawiera kafelki podsumowań, informacje o rachunkach bankowych, wykres salda i pokrewne informacje.</span><span class="sxs-lookup"><span data-stu-id="eff48-109">The **Summary** view shows summary tiles, bank account information, a balance chart, and related information.</span></span> <span data-ttu-id="eff48-110">Strona **Analizy** wykorzystuje funkcje programu Microsoft Power BI, aby pokazywać wizualizacje dotyczące sald na rachunkach bankowych.</span><span class="sxs-lookup"><span data-stu-id="eff48-110">The **Analytics** page uses the capabilities of Microsoft Power BI to show visuals that are related to bank account balances.</span></span>

## <a name="summary-view"></a><span data-ttu-id="eff48-111">Widok Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="eff48-111">Summary view</span></span>

### <a name="summary"></a><span data-ttu-id="eff48-112">Sumarycznie</span><span class="sxs-lookup"><span data-stu-id="eff48-112">Summary</span></span>

<span data-ttu-id="eff48-113">Kafelki w sekcji **Podsumowanie** prezentują przegląd firmowych kont bankowych i umożliwiają szybki dostęp do najczęściej używanych stron.</span><span class="sxs-lookup"><span data-stu-id="eff48-113">The tiles in the **Summary** section give an overview of your bank accounts and provide quick access to the pages that you most often have to use.</span></span> <span data-ttu-id="eff48-114">Informacje o uzgodnieniach kont bankowych są specyficzne dla funkcjonalności Zaawansowane uzgadnianie konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="eff48-114">The bank reconciliation information is specific to the Advanced bank reconciliation functionality.</span></span> <span data-ttu-id="eff48-115">Informacje są podawane tylko dla tych kont bankowych, które na stronie **Konto bankowe** w opcji **Zaawansowane uzgadnianie konta bankowego** mają ustawioną opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="eff48-115">Information is included only for those bank accounts that have the **Advanced bank reconciliation** option set to **Yes** on the **Bank account** page.</span></span> <span data-ttu-id="eff48-116">Z sekcji **Podsumowanie** można importować elektroniczne pliki bankowe dla rachunków bankowych ze wszystkich firm.</span><span class="sxs-lookup"><span data-stu-id="eff48-116">From the **Summary** section, you can import electronic bank files for bank accounts across all legal entities.</span></span>

### <a name="bank-accounts"></a><span data-ttu-id="eff48-117">Konta bankowe</span><span class="sxs-lookup"><span data-stu-id="eff48-117">Bank accounts</span></span>

<span data-ttu-id="eff48-118">Każde konto bankowe w firmie jest reprezentowana przez kartę w sekcji **Konta bankowe**.</span><span class="sxs-lookup"><span data-stu-id="eff48-118">Each bank account in the legal entity is represented by a card in the **Bank accounts** section.</span></span> <span data-ttu-id="eff48-119">Jest wyświetlane bieżące saldo i możesz przejść do szczegółów transakcji, które składają się na sumaryczną wartość salda.</span><span class="sxs-lookup"><span data-stu-id="eff48-119">The current balance is shown, and you can drill down to the transactions that make up that summary balance amount.</span></span> <span data-ttu-id="eff48-120">Również z pola kwoty **Transakcje pomostowe** można przechodzić do szczegółów transakcji składających się na łączną kwotę.</span><span class="sxs-lookup"><span data-stu-id="eff48-120">The **Bridged transactions** amount also lets you drill down to the transactions that make up that summary amount.</span></span> <span data-ttu-id="eff48-121">Transakcjami pomostowymi są wszelkie transakcje oczekujące, które zostały zaksięgowane w za pomocą funkcji transakcji pomostowej, ale nie zostały jeszcze rozliczone.</span><span class="sxs-lookup"><span data-stu-id="eff48-121">Bridged transactions are any pending transactions that have been posted by using bridging functionality, but that haven't yet been cleared.</span></span> <span data-ttu-id="eff48-122">Kwota **Saldo oczekujące** jest bieżącym saldem pomniejszonym o kwoty z transakcji pomostowych (oczekujących).</span><span class="sxs-lookup"><span data-stu-id="eff48-122">The **Pending balance** amount is the current balance minus the bridged, or pending, transactions.</span></span>

<span data-ttu-id="eff48-123">Karta pokazuje także, kiedy konto bankowe było po raz ostatni uzgadniane.</span><span class="sxs-lookup"><span data-stu-id="eff48-123">The card also shows when the bank account was last reconciled.</span></span> <span data-ttu-id="eff48-124">Te informacje są wyświetlane tylko wtedy, gdy dla rachunku bankowego włączono opcję Zaawansowane uzgadnianie konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="eff48-124">This information is shown only if Advanced bank reconciliation is enabled for the bank account.</span></span>

### <a name="balance"></a><span data-ttu-id="eff48-125">Bilansowe</span><span class="sxs-lookup"><span data-stu-id="eff48-125">Balance</span></span>

<span data-ttu-id="eff48-126">Wykres **Saldo** przedstawia historyczne informacje o saldzie dla konta bankowego wybranego w sekcji **Konta bankowe** lub podsumowanie historycznych informacji o saldach dla wszystkich kont bankowych w firmie.</span><span class="sxs-lookup"><span data-stu-id="eff48-126">The **Balance** chart shows either historic balance information for the bank account that is selected in the **Bank accounts** section or a summary of historic balance information for all bank accounts in the legal entity.</span></span> <span data-ttu-id="eff48-127">Informacje te są dostępne dla różnych okresów: bieżącego tygodnia, bieżącego miesiąca, bieżącego roku, ostatnich pięciu lat i dla wszystkich okresów (pełna historia konta bankowego).</span><span class="sxs-lookup"><span data-stu-id="eff48-127">This information is available for various periods: the current week, the current month, the current year, the last five years, and all periods (the full history of the bank account).</span></span> 

<span data-ttu-id="eff48-128">Jeśli wyświetlasz wykres **Saldo** dla pojedynczego konta bankowego, salda historyczne są pokazywane w walucie konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="eff48-128">If you're viewing the **Balance** chart for a single bank account, the historic balances are shown in the bank account currency.</span></span> <span data-ttu-id="eff48-129">Jeśli wyświetlasz wykres dla wszystkich rachunków bankowych w firmie, salda historyczne są pokazywane w walucie rozliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="eff48-129">If you're viewing the chart for all bank accounts in the legal entity, the historic balances are shown in the accounting currency.</span></span>

<span data-ttu-id="eff48-130">Informacje o dacie ostatniej aktualizacji danych są wyświetlane w górnej części wykresu.</span><span class="sxs-lookup"><span data-stu-id="eff48-130">Information about when the data was last updated appears at the top of the chart.</span></span> <span data-ttu-id="eff48-131">W razie potrzeby można aktualizować dane.</span><span class="sxs-lookup"><span data-stu-id="eff48-131">You can update the data as you require.</span></span>

### <a name="related-information"></a><span data-ttu-id="eff48-132">Informacje pokrewne</span><span class="sxs-lookup"><span data-stu-id="eff48-132">Related information</span></span>

<span data-ttu-id="eff48-133">Z sekcji **Informacje pokrewne** można otworzyć stronę **Arkusz finansowy** , aby wykonać przelewy bankowe.</span><span class="sxs-lookup"><span data-stu-id="eff48-133">From the **Related information** section, you can open the **General journal** page to complete bank transfers.</span></span> <span data-ttu-id="eff48-134">Można także szybko otworzyć strony **Transakcje bankowe** i **Transakcje pomostowe**.</span><span class="sxs-lookup"><span data-stu-id="eff48-134">You can also quickly open the **Bank transactions** and **Bridged transactions** pages.</span></span>

## <a name="analytics-view"></a><span data-ttu-id="eff48-135">Widok Analizy</span><span class="sxs-lookup"><span data-stu-id="eff48-135">Analytics view</span></span>

<span data-ttu-id="eff48-136">Strona **Analizy** zawiera ważne wskaźniki dotyczące kont bankowych w bieżącej firmie.</span><span class="sxs-lookup"><span data-stu-id="eff48-136">The **Analytics** page provides important metrics about the bank accounts in the current company.</span></span> <span data-ttu-id="eff48-137">Na stronie są dostępne następujące wizualizacje:</span><span class="sxs-lookup"><span data-stu-id="eff48-137">The following visualizations are available on the page:</span></span>

-   <span data-ttu-id="eff48-138">Łączne saldo rachunków bankowych w walucie systemowej</span><span class="sxs-lookup"><span data-stu-id="eff48-138">Total bank balance in system currency</span></span>
-   <span data-ttu-id="eff48-139">Saldo wg firmy</span><span class="sxs-lookup"><span data-stu-id="eff48-139">Balance by legal entity</span></span>
-   <span data-ttu-id="eff48-140">Dzisiejsze saldo rzeczywiste w porównaniu z prognozowanym w walucie konta bankowego</span><span class="sxs-lookup"><span data-stu-id="eff48-140">Today’s actual vs forecasted balance in bank account currency</span></span>
-   <span data-ttu-id="eff48-141">Saldo wg konta bankowego</span><span class="sxs-lookup"><span data-stu-id="eff48-141">Balance by bank account</span></span>
-   <span data-ttu-id="eff48-142">Saldo wg waluty</span><span class="sxs-lookup"><span data-stu-id="eff48-142">Balance by currency</span></span>

<span data-ttu-id="eff48-143">Analizy rachunków bankowych ze wszystkich firm można przeglądać w obszarze roboczym **Przegląd środków pieniężnych — wszystkie firmy**.</span><span class="sxs-lookup"><span data-stu-id="eff48-143">You can view bank analytics across all companies from the **Cash overview – all companies** workspace.</span></span> <span data-ttu-id="eff48-144">Aby uzyskać więcej informacji, zobacz [Omówienie operacji gotówkowych - zawartość Power BI](Cash-Overview-Power-BI-content.md).</span><span class="sxs-lookup"><span data-stu-id="eff48-144">For more information, see [Cash overview Power BI content](Cash-Overview-Power-BI-content.md).</span></span>
