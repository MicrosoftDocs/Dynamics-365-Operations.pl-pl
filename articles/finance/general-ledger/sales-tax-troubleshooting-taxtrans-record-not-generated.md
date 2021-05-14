---
title: Nie jest generowany rekord TaxTrans
description: Ten temat zawiera informacje na temat rozwiązywania problemów, które mogą pomóc w przypadku niewygenerowania rekordu TaxTrans.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0c7414cc39198ff4d5be9b4c41ca62f9c78c9250
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947691"
---
# <a name="taxtrans-record-isnt-generated"></a><span data-ttu-id="84b94-103">Nie jest generowany rekord TaxTrans</span><span class="sxs-lookup"><span data-stu-id="84b94-103">TaxTrans record isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84b94-104">Jeśli wybierzesz opcję **Zaksięgowany podatek** dla transakcji, ale na stronie **Zaksięgowany podatek** albo nie ma wierszy podatku albo brakuje wiersza podatku, być może rekord **TaxTrans** nie został wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="84b94-104">If you select **Posted sales tax** for a transaction, but the **Posted sales tax** page either shows no tax lines or is missing a tax line, the **TaxTrans** record might not have been generated.</span></span>

<span data-ttu-id="84b94-105">[![Strona Zaksięgowany podatek, która nie zawiera pozycji w wierszach](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="84b94-105">[![Posted sales tax page that has no line items](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span></span>

<span data-ttu-id="84b94-106">W razie potrzeby wykonaj kroki opisane w poniższych sekcjach, aby rozwiązać ten problem.</span><span class="sxs-lookup"><span data-stu-id="84b94-106">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a><span data-ttu-id="84b94-107">Sprawdzenie podatku przed zaksięgowaniem transakcji</span><span class="sxs-lookup"><span data-stu-id="84b94-107">Check the sales tax before you post the transaction</span></span>

1. <span data-ttu-id="84b94-108">Przed zaksięgowaniem transakcji, na stronie **Księgowanie faktury** wybierz opcję **Podatek**, aby sprawdzić obliczenie.</span><span class="sxs-lookup"><span data-stu-id="84b94-108">Before you post the transaction, on the **Posting invoice** page, select **Sales tax** to check the calculation.</span></span>

    <span data-ttu-id="84b94-109">[![Przycisk Podatek na stronie Księgowanie faktury](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="84b94-109">[![Sales tax button on the Posting invoice page](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span></span>

2. <span data-ttu-id="84b94-110">Na stronie **Tymczasowe transakcje podatkowe** przejrzyj wyniki obliczenia.</span><span class="sxs-lookup"><span data-stu-id="84b94-110">On the **Temporary sales tax transactions** page, review the result of the calculation.</span></span> <span data-ttu-id="84b94-111">Jeśli podatek nie jest obliczany, zobacz temat [Podatek nie jest obliczany lub kwota podatku wynosi zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span><span class="sxs-lookup"><span data-stu-id="84b94-111">If no tax is calculated, see [Tax isn't calculated or the tax amount is zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span></span>

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a><span data-ttu-id="84b94-112">Znajdowanie rekordu TaxTrans we wszystkich zaksięgowanych podatkach</span><span class="sxs-lookup"><span data-stu-id="84b94-112">Find the TaxTrans record in all posted sales tax</span></span>

1. <span data-ttu-id="84b94-113">Wybierz kolejno opcje **Podatek** \> **Zapytania i raporty** \> **Zapytania o podatki** > **Zaksięgowany podatek**.</span><span class="sxs-lookup"><span data-stu-id="84b94-113">Go to **Tax** \> **Inquiries and reports** \> **Sales tax inquiries** > **Posted sales tax**.</span></span>
2. <span data-ttu-id="84b94-114">W nagłówku kolumny **Załącznik** wybierz symbol filtru, aby znaleźć rekord **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="84b94-114">In the **Voucher** column heading, select the filter symbol to find the **TaxTrans** record.</span></span>
3. <span data-ttu-id="84b94-115">Jeśli znajdziesz rekordy podatku, których szukasz, sprawdź datę.</span><span class="sxs-lookup"><span data-stu-id="84b94-115">If you find the sales tax records that you're looking for, check the date.</span></span> <span data-ttu-id="84b94-116">Jeśli ta data różni się od daty nagłówka arkusza, utwórz żądanie obsługi do firmy Microsoft dotyczące dodatkowej pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="84b94-116">If the date differs from the date of the journal header, create a Microsoft service request for additional support.</span></span>

    <span data-ttu-id="84b94-117">[![Strona zaksięgowany podatek](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="84b94-117">[![Posted sales tax page](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span></span>

## <a name="debug-to-check-details"></a><span data-ttu-id="84b94-118">Debugowanie w celu sprawdzenia szczegółów</span><span class="sxs-lookup"><span data-stu-id="84b94-118">Debug to check details</span></span>

1. <span data-ttu-id="84b94-119">Aby uzyskać informacje dotyczące sposobu debugowania i określania, czy wartości **TmpTaxWorkTrans** i **TaxUncommitted** zostały poprawnie wygenerowane, zobacz temat [Niepoprawne wartości pola w rekordzie TaxTrans](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span><span class="sxs-lookup"><span data-stu-id="84b94-119">For information about how to debug and determine whether **TmpTaxWorkTrans** and **TaxUncommitted** are correctly generated, see [Field value in TaxTrans is incorrect](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span></span>
2. <span data-ttu-id="84b94-120">Jeśli **TaxTmpWorkTrans** lub **TaxUncommitted** został poprawnie wygenerowany, dodaj punkt przerwania w **TaxPost::SaveAndPost()** i **Tax::SaveAndPost**, aby debugować przyczynę niewstawienia rekordu **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="84b94-120">If **TaxTmpWorkTrans** or **TaxUncommitted** is correctly generated, add a breakpoint at **TaxPost::SaveAndPost()** and **Tax::SaveAndPost** to debug the reason why **TaxTrans** isn't inserted.</span></span>

    <span data-ttu-id="84b94-121">[![Punkty przerwania dodane w kodzie](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="84b94-121">[![Breakpoints added in code](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span></span>

    <span data-ttu-id="84b94-122">[![Wyniki dodanych punktów przerwania](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="84b94-122">[![Results of added breakpoints](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="84b94-123">Określanie, czy dostosowanie istnieje</span><span class="sxs-lookup"><span data-stu-id="84b94-123">Determine whether customization exists</span></span>

<span data-ttu-id="84b94-124">Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie znaleziono problemu, określ, czy dostosowanie istnieje.</span><span class="sxs-lookup"><span data-stu-id="84b94-124">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="84b94-125">Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.</span><span class="sxs-lookup"><span data-stu-id="84b94-125">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
