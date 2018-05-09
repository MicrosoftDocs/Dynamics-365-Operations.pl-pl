---
title: "Definicje księgowania"
description: "Ten artykuł zawiera przykłady pokazujące, jak definicje księgowania są używane dla przyszłych zobowiązań wiążących w zamówieniach zakupu i dla asygnat budżetu."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b7d4b94e9c0ea27b8a78ea4ed6bbde6bec19ef6e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="posting-definition-examples"></a><span data-ttu-id="042bf-103">Szablony definicji księgowania</span><span class="sxs-lookup"><span data-stu-id="042bf-103">Posting definition examples</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="042bf-104">Ten artykuł zawiera przykłady pokazujące, jak definicje księgowania są używane dla przyszłych zobowiązań wiążących w zamówieniach zakupu i dla asygnat budżetu.</span><span class="sxs-lookup"><span data-stu-id="042bf-104">This article provides examples that show how posting definitions are used for purchase order encumbrances and budget appropriations.</span></span>

<span data-ttu-id="042bf-105">Zanim przeczytasz ten temat, zapoznaj się z definicjami księgowania i definicjami księgowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="042bf-105">Before you read this topic, you should be familiar with posting definitions and transaction posting definitions.</span></span> <span data-ttu-id="042bf-106">Więcej informacji znajdziesz w temacie [Definicje księgowania](posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="042bf-106">For information, see [Posting definitions](posting-definitions.md).</span></span> <span data-ttu-id="042bf-107">Poniższe przykłady można skonfigurować na stronie **Definicje księgowania**.</span><span class="sxs-lookup"><span data-stu-id="042bf-107">The following examples can be set up on the **Posting definitions** page.</span></span> <span data-ttu-id="042bf-108">Każdy przykład zawiera następujące sekcje:</span><span class="sxs-lookup"><span data-stu-id="042bf-108">Each example contains these sections:</span></span>

-   <span data-ttu-id="042bf-109">Definicja księgowania — kryteria uzgadniania</span><span class="sxs-lookup"><span data-stu-id="042bf-109">Posting definition – Match criteria</span></span>
-   <span data-ttu-id="042bf-110">Definicja księgowania — wygenerowane zapisy</span><span class="sxs-lookup"><span data-stu-id="042bf-110">Posting definition – Generated entries</span></span>
-   <span data-ttu-id="042bf-111">Transakcje z kontami, wartości wymiarów i kwoty</span><span class="sxs-lookup"><span data-stu-id="042bf-111">Transactions with the accounts, dimension values, and amounts</span></span>
-   <span data-ttu-id="042bf-112">Wpisy w księdze wygenerowane z definicji księgowania</span><span class="sxs-lookup"><span data-stu-id="042bf-112">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="042bf-113">Kiedy wystąpi dopasowanie między wartościami kont i wymiarów w okienku **Kryteria dopasowania** dla definicji księgowania i wartościami kont i wymiarów w transakcji, generowane są zapisy księgi na podstawie okienka **Wygenerowane zapisy** dla danej definicji księgowania.</span><span class="sxs-lookup"><span data-stu-id="042bf-113">When a match occurs between the accounts and dimension values in the **Match criteria** pane for the posting definition and the accounts and dimension values on the transaction, ledger entries are generated based on the **Generated entries** pane for the posting definition.</span></span> 
> [!NOTE]
> <span data-ttu-id="042bf-114">Definicję księgowania można skojarzyć z konkretnym typem transakcji na stronie **Definicje księgowania transakcji**.</span><span class="sxs-lookup"><span data-stu-id="042bf-114">To associate a posting definition with a specific transaction type, use the **Transaction posting definitions** page.</span></span> <span data-ttu-id="042bf-115">Po skojarzeniu definicji księgowania z typem transakcji i wybraniu opcji **Użyj definicji księgowania** na stronie **Parametry księgi głównej** wszystkie transakcje wybranego typu muszą korzystać z definicji księgowania.</span><span class="sxs-lookup"><span data-stu-id="042bf-115">After you associate a posting definition with a transaction type and select **Use posting definitions** on the **General ledger parameters** page, all transactions of the selected transaction type must use posting definitions.</span></span>

## <a name="example-purchase-order-encumbrances"></a><span data-ttu-id="042bf-116">Przykład: Przyszłe zobowiązania wiążące dla zamówień zakupu</span><span class="sxs-lookup"><span data-stu-id="042bf-116">Example: Purchase order encumbrances</span></span>
<span data-ttu-id="042bf-117">Po włączeniu przetwarzania przyszłych zobowiązań wiążących przez zaznaczenie opcji **Włącz przetwarzanie przyszłych zobowiązań wiążących** na stronie **Parametry księgi głównej**, definicje księgowania muszą zostać użyte do rejestrowania przyszłych zobowiązań wiążących w księdze głównej dla dowolnych kont, które powinny być rezerwowane.</span><span class="sxs-lookup"><span data-stu-id="042bf-117">When you enable encumbrance processing by selecting **Enable encumbrance process** on the **General ledger parameters** page, posting definitions must be used to record encumbrances to the general ledger for any accounts that should be reserved.</span></span> <span data-ttu-id="042bf-118">W większości przypadków wszystkie konta wydatków są rezerwowane w bilansie.</span><span class="sxs-lookup"><span data-stu-id="042bf-118">In most cases, all expense accounts are reserved on the balance sheet.</span></span> 

<span data-ttu-id="042bf-119">Definicje księgowania dla przyszłych zobowiązań wiążących ustawia się dla modułu **Zakupy** na stronie **Definicje księgowania**.</span><span class="sxs-lookup"><span data-stu-id="042bf-119">Posting definitions for encumbrances are set up for the **Purchasing** module on the **Posting definitions** page.</span></span> <span data-ttu-id="042bf-120">Następnie w obszarze **Zakupy** na stronie **Definicji księgowania transakcji** można wybrać typ transakcji **Zamówienie zakupu**, aby skojarzyć definicję księgowania z zamówieniami zakupu.</span><span class="sxs-lookup"><span data-stu-id="042bf-120">Then, in the **Purchasing** area of the **Transaction posting definitions** page, you can select the **Purchase order** transaction type to associate the posting definition with purchase orders.</span></span> 

<span data-ttu-id="042bf-121">Wszystkie transakcje załącznika dla przyszłych zobowiązań wiążących z zamówień zakupu muszą się bilansować (tj. strony „winien” i „ma” muszą się równoważyć) w każdym niepowtarzalnym wymiarze załącznika.</span><span class="sxs-lookup"><span data-stu-id="042bf-121">All voucher transactions for purchase order encumbrances must balance (that is, debits must equal credits) in each unique dimension on a voucher.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="042bf-122">Definicja księgowania — kryteria uzgadniania</span><span class="sxs-lookup"><span data-stu-id="042bf-122">Posting definition – Match criteria</span></span>

| <span data-ttu-id="042bf-123">Struktura konta</span><span class="sxs-lookup"><span data-stu-id="042bf-123">Account structure</span></span>       | <span data-ttu-id="042bf-124">Dopasuj numer konta</span><span class="sxs-lookup"><span data-stu-id="042bf-124">Match account number</span></span> | <span data-ttu-id="042bf-125">Priorytet </span><span class="sxs-lookup"><span data-stu-id="042bf-125">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="042bf-126">Struktura konta — zyski i straty</span><span class="sxs-lookup"><span data-stu-id="042bf-126">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="042bf-127">1</span><span class="sxs-lookup"><span data-stu-id="042bf-127">1</span></span>        |

<span data-ttu-id="042bf-128"><em>Pusta wartość w polu \**Dopasuj numer konta oznacza</em>*, że wszystkie pasujące konta w definiowanej strukturze konta są częścią reguły uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="042bf-128"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="042bf-129">Definicja księgowania — wygenerowane zapisy</span><span class="sxs-lookup"><span data-stu-id="042bf-129">Posting definition – Generated entries</span></span>

| <span data-ttu-id="042bf-130">Struktura konta</span><span class="sxs-lookup"><span data-stu-id="042bf-130">Account structure</span></span> | <span data-ttu-id="042bf-131">Wygenerowany numer konta</span><span class="sxs-lookup"><span data-stu-id="042bf-131">Generated account number</span></span>                    | <span data-ttu-id="042bf-132">Wygenerowany debet/kredyt</span><span class="sxs-lookup"><span data-stu-id="042bf-132">Generated debit/credit</span></span> |
|-------------------|---------------------------------------------|------------------------|
| <span data-ttu-id="042bf-133">Saldo</span><span class="sxs-lookup"><span data-stu-id="042bf-133">Balance</span></span>           | <span data-ttu-id="042bf-134">300143 - -(Konto przyszłego zobowiązania wiążącego)</span><span class="sxs-lookup"><span data-stu-id="042bf-134">300143 - -(Encumbrance account)</span></span>             | <span data-ttu-id="042bf-135">To samo</span><span class="sxs-lookup"><span data-stu-id="042bf-135">Same</span></span>                   |
| <span data-ttu-id="042bf-136">Saldo</span><span class="sxs-lookup"><span data-stu-id="042bf-136">Balance</span></span>           | <span data-ttu-id="042bf-137">300144 - -(Rezerwa dla konta przyszłego zobowiązania wiążącego)</span><span class="sxs-lookup"><span data-stu-id="042bf-137">300144 - -(Reserve for encumbrance account)</span></span> | <span data-ttu-id="042bf-138">Balansowanie</span><span class="sxs-lookup"><span data-stu-id="042bf-138">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="042bf-139">Transakcje z kontami, wartości wymiarów i kwoty</span><span class="sxs-lookup"><span data-stu-id="042bf-139">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="042bf-140">Kont i wartości wymiarów pochodzą z zasad podziału księgowań wprowadzonych dla wiersza zamówienia zakupu lub z kont i wymiarów, które są generowane automatycznie na podstawie wartości domyślnych dla dostawców, towarów, kategorii i szablonów wymiaru.</span><span class="sxs-lookup"><span data-stu-id="042bf-140">The accounts and dimension values come either from the accounting distributions that you enter for a purchase order line, or from the accounts and dimensions that are automatically generated based on the default settings for vendors, items, categories, and dimension templates.</span></span>

| <span data-ttu-id="042bf-141">Konto + wymiary</span><span class="sxs-lookup"><span data-stu-id="042bf-141">Account + dimensions</span></span>           | <span data-ttu-id="042bf-142">Strona debetowa</span><span class="sxs-lookup"><span data-stu-id="042bf-142">Debit</span></span>  | <span data-ttu-id="042bf-143">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="042bf-143">Credit</span></span> | <span data-ttu-id="042bf-144">Komentarz</span><span class="sxs-lookup"><span data-stu-id="042bf-144">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="042bf-145">606400-OU\_1-OU\_3566-Szkolenie</span><span class="sxs-lookup"><span data-stu-id="042bf-145">606400-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="042bf-146">250.00</span><span class="sxs-lookup"><span data-stu-id="042bf-146">250.00</span></span> |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="042bf-147">Wpisy w księdze wygenerowane z definicji księgowania</span><span class="sxs-lookup"><span data-stu-id="042bf-147">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="042bf-148">Wygenerowane zapisy księgi są tworzone w celu rejestracji przyszłych zobowiązań wiążących.</span><span class="sxs-lookup"><span data-stu-id="042bf-148">Generated ledger entries are created to record the encumbrances.</span></span>

| <span data-ttu-id="042bf-149">Konto + wymiary</span><span class="sxs-lookup"><span data-stu-id="042bf-149">Account + dimensions</span></span>           | <span data-ttu-id="042bf-150">Strona debetowa</span><span class="sxs-lookup"><span data-stu-id="042bf-150">Debit</span></span>  | <span data-ttu-id="042bf-151">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="042bf-151">Credit</span></span> | <span data-ttu-id="042bf-152">Komentarz</span><span class="sxs-lookup"><span data-stu-id="042bf-152">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="042bf-153">300143-OU\_1-OU\_3566-Szkolenie</span><span class="sxs-lookup"><span data-stu-id="042bf-153">300143-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="042bf-154">250.00</span><span class="sxs-lookup"><span data-stu-id="042bf-154">250.00</span></span> |        |         |
| <span data-ttu-id="042bf-155">300144-OU\_1-OU\_3566-Szkolenie</span><span class="sxs-lookup"><span data-stu-id="042bf-155">300144-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="042bf-156">250.00</span><span class="sxs-lookup"><span data-stu-id="042bf-156">250.00</span></span> |         |

<span data-ttu-id="042bf-157">W tym przykładzie dowolne konto będące częścią Struktury konta — zyski i straty spełnia kryteria definicji księgowania.</span><span class="sxs-lookup"><span data-stu-id="042bf-157">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="042bf-158">Dlatego podczas szacowania 606500-OU\_1-OU\_3566-Szkolenie wygenerowane zapisy są tworzone dla kont, które są zdefiniowane w okienku **Wygenerowane zapisy** dla definicji księgowania.</span><span class="sxs-lookup"><span data-stu-id="042bf-158">Therefore, when 606500-OU\_1-OU\_3566-Training is evaluated, generated entries are created for the accounts that are defined in the **Generated entries** pane for the posting definition.</span></span>

## <a name="example-budget-appropriations"></a><span data-ttu-id="042bf-159">Przykład: asygnaty budżetu</span><span class="sxs-lookup"><span data-stu-id="042bf-159">Example: Budget appropriations</span></span>
<span data-ttu-id="042bf-160">Po włączeniu asygnaty budżetu przez zaznaczenie opcji **Włączanie asygnaty budżetu** na stronie **Parametry księgi głównej** definicje księgowania muszą być używane do rejestrowania wpisów do rejestru budżetu w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="042bf-160">When you enable budget appropriation by selecting **Enable budget appropriation** on the **General ledger parameters** page, posting definitions must be used to record budget register entries to the general ledger.</span></span> <span data-ttu-id="042bf-161">Jeśli konfiguracji kontroli budżetu jest aktywna i włączona, definicje księgowania i definicje księgowania transakcji mogą być używane do obsługi rejestracji zapisów dla asygnat, korekt, przeniesień, projektów, środków trwałych i prognoz popytu i dostaw w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="042bf-161">When a budget control configuration is active and is turned on, posting definitions and transaction posting definitions can be used to support the recording of entries for appropriations, revisions, transfers, projects, fixed assets, and supply and demand forecasts to the general ledger.</span></span> 

<span data-ttu-id="042bf-162">Aby skonfigurować definicję księgowania dla wpisów do rejestru budżetu, która ma typ budżetu **Budżet pierwotny** i która ma włączone asygnaty, wybierz moduł **Budżet** na stronie **Definicje księgowania**.</span><span class="sxs-lookup"><span data-stu-id="042bf-162">To set up a posting definition for budget register entries that has a budget type of **Original budget**, and that has appropriations enabled, select the **Budget** module on the **Posting definitions** page.</span></span> <span data-ttu-id="042bf-163">Następnie w obszarze **Budżet** na stronie **Definicje księgowania transakcji** można użyć kodów budżetu do skojarzenia definicji księgowania z wpisów do rejestru budżetu o typie **Budżet pierwotny**.</span><span class="sxs-lookup"><span data-stu-id="042bf-163">Then, in the **Budget** area of the **Transaction posting definitions** page, you can use budget codes to associate the posting definition with budget register entries that have a budget type of **Original budget**.</span></span> 

<span data-ttu-id="042bf-164">Jeśli asygnaty budżetu i definicje księgowania są włączone, wpisy do rejestru budżetu są rejestrowane dla kontroli budżetu i w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="042bf-164">When budget appropriations and posting definitions are enabled, the budget register entries are recorded for budget control and in the general ledger.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="042bf-165">Definicja księgowania — kryteria uzgadniania</span><span class="sxs-lookup"><span data-stu-id="042bf-165">Posting definition – Match criteria</span></span>

| <span data-ttu-id="042bf-166">Struktura konta</span><span class="sxs-lookup"><span data-stu-id="042bf-166">Account structure</span></span>       | <span data-ttu-id="042bf-167">Dopasuj numer konta</span><span class="sxs-lookup"><span data-stu-id="042bf-167">Match account number</span></span> | <span data-ttu-id="042bf-168">Priorytet </span><span class="sxs-lookup"><span data-stu-id="042bf-168">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="042bf-169">Struktura konta — zyski i straty</span><span class="sxs-lookup"><span data-stu-id="042bf-169">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="042bf-170">1</span><span class="sxs-lookup"><span data-stu-id="042bf-170">1</span></span>        |

<span data-ttu-id="042bf-171"><em>Pusta wartość w polu \**Dopasuj numer konta oznacza</em>*, że wszystkie pasujące konta w definiowanej strukturze konta są częścią reguły uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="042bf-171"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="042bf-172">Definicja księgowania — wygenerowane zapisy</span><span class="sxs-lookup"><span data-stu-id="042bf-172">Posting definition – Generated entries</span></span>

| <span data-ttu-id="042bf-173">Struktura konta</span><span class="sxs-lookup"><span data-stu-id="042bf-173">Account structure</span></span> | <span data-ttu-id="042bf-174">Wygenerowany numer konta</span><span class="sxs-lookup"><span data-stu-id="042bf-174">Generated account number</span></span>              | <span data-ttu-id="042bf-175">Wygenerowany debet/kredyt</span><span class="sxs-lookup"><span data-stu-id="042bf-175">Generated debit/credit</span></span> |
|-------------------|---------------------------------------|------------------------|
| <span data-ttu-id="042bf-176">Struktura konta</span><span class="sxs-lookup"><span data-stu-id="042bf-176">Account structure</span></span> | <span data-ttu-id="042bf-177">300145 - -(Szacowane konto przychodów)</span><span class="sxs-lookup"><span data-stu-id="042bf-177">300145 - -(Estimated revenue account)</span></span> | <span data-ttu-id="042bf-178">To samo</span><span class="sxs-lookup"><span data-stu-id="042bf-178">Same</span></span>                   |
| <span data-ttu-id="042bf-179">Struktura konta</span><span class="sxs-lookup"><span data-stu-id="042bf-179">Account structure</span></span> | <span data-ttu-id="042bf-180">300146 - -(Konto asygnaty)</span><span class="sxs-lookup"><span data-stu-id="042bf-180">300146 - -(Appropriation account)</span></span>     | <span data-ttu-id="042bf-181">Balansowanie</span><span class="sxs-lookup"><span data-stu-id="042bf-181">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="042bf-182">Transakcje z kontami, wartości wymiarów i kwoty</span><span class="sxs-lookup"><span data-stu-id="042bf-182">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="042bf-183">Konta, wartości wymiarów i kwoty dla zapisu na koncie budżetu wprowadza się na stronie **Wpis do rejestru budżetu**.</span><span class="sxs-lookup"><span data-stu-id="042bf-183">You enter the accounts, dimension values, and amounts for the budget account entry on the **Budget register entry** page.</span></span>

| <span data-ttu-id="042bf-184">Konto + wymiary</span><span class="sxs-lookup"><span data-stu-id="042bf-184">Account + dimensions</span></span>           | <span data-ttu-id="042bf-185">Strona debetowa</span><span class="sxs-lookup"><span data-stu-id="042bf-185">Debit</span></span> | <span data-ttu-id="042bf-186">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="042bf-186">Credit</span></span> | <span data-ttu-id="042bf-187">Komentarz</span><span class="sxs-lookup"><span data-stu-id="042bf-187">Comment</span></span> |
|--------------------------------|-------|--------|---------|
| <span data-ttu-id="042bf-188">606400-OU\_1-OU\_3566-Szkolenie</span><span class="sxs-lookup"><span data-stu-id="042bf-188">606400-OU\_1-OU\_3566-Training</span></span> |       | <span data-ttu-id="042bf-189">250.00</span><span class="sxs-lookup"><span data-stu-id="042bf-189">250.00</span></span> |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="042bf-190">Wpisy w księdze wygenerowane z definicji księgowania</span><span class="sxs-lookup"><span data-stu-id="042bf-190">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="042bf-191">Wygenerowane zapisy księgi są tworzone w celu rejestracji pierwotnego budżetu w każdym wymiarze.</span><span class="sxs-lookup"><span data-stu-id="042bf-191">Generated ledger entries are created to record the original budget in each dimension.</span></span>

| <span data-ttu-id="042bf-192">Konto + wymiary</span><span class="sxs-lookup"><span data-stu-id="042bf-192">Account + dimensions</span></span>           | <span data-ttu-id="042bf-193">Strona debetowa</span><span class="sxs-lookup"><span data-stu-id="042bf-193">Debit</span></span>  | <span data-ttu-id="042bf-194">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="042bf-194">Credit</span></span> | <span data-ttu-id="042bf-195">Komentarz</span><span class="sxs-lookup"><span data-stu-id="042bf-195">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="042bf-196">300145-OU\_1-OU\_3566-Szkolenie</span><span class="sxs-lookup"><span data-stu-id="042bf-196">300145-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="042bf-197">250.00</span><span class="sxs-lookup"><span data-stu-id="042bf-197">250.00</span></span> |         |
| <span data-ttu-id="042bf-198">300146-OU\_1-OU\_3566-Szkolenie</span><span class="sxs-lookup"><span data-stu-id="042bf-198">300146-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="042bf-199">250.00</span><span class="sxs-lookup"><span data-stu-id="042bf-199">250.00</span></span> |        |         |

<span data-ttu-id="042bf-200">W tym przykładzie dowolne konto będące częścią Struktury konta — zyski i straty spełnia kryteria definicji księgowania.</span><span class="sxs-lookup"><span data-stu-id="042bf-200">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="042bf-201">Dlatego podczas szacowania 606400-OU\_1-OU\_3566-Szkolenie tworzone są wygenerowane zapisy księgi.</span><span class="sxs-lookup"><span data-stu-id="042bf-201">Therefore, when 606400-OU\_1-OU\_3566-Training is evaluated, the generated ledger entries are created.</span></span>






