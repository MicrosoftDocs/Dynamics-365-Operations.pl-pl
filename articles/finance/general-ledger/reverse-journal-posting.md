---
title: Odwróć księgowanie arkusza
description: W tym temacie opisano możliwości wystornowania załączników z listy transakcji na załączniku lub z arkuszy finansowych.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d18b71c1fc7f3f0c39172bd9edf19b4e60a2bf8
ms.sourcegitcommit: cfaad79bcb1460ee0e7ad5a2c596f9199e14c53a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/08/2020
ms.locfileid: "2944435"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="56d4c-103">Odwróć księgowanie arkusza</span><span class="sxs-lookup"><span data-stu-id="56d4c-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56d4c-104">W tym temacie opisano możliwości Microsoft Dynamics 365 Finance, które pozwalają wycofać cały arkusz lub wycofać jeden lub więcej załączników z listy transakcji załącznika bez względu na ich pochodzenie.</span><span class="sxs-lookup"><span data-stu-id="56d4c-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal, or reverse one or more vouchers from the voucher transaction list, regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="56d4c-105">Wycofywanie arkuszy</span><span class="sxs-lookup"><span data-stu-id="56d4c-105">Reversing journals</span></span>

<span data-ttu-id="56d4c-106">Wiersze arkusza można odwracać pojedynczo.</span><span class="sxs-lookup"><span data-stu-id="56d4c-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="56d4c-107">W przypadku księgowania wstecznego arkusza można również wycofywać cały arkusz finansowy.</span><span class="sxs-lookup"><span data-stu-id="56d4c-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="56d4c-108">Wycofywanie arkusza:</span><span class="sxs-lookup"><span data-stu-id="56d4c-108">To reverse a journal:</span></span> 

- <span data-ttu-id="56d4c-109">Umożliwia otwarcie arkusza finansowego i przefiltrowanie arkuszy w zaksięgowanych arkuszach.</span><span class="sxs-lookup"><span data-stu-id="56d4c-109">Open the financial journal and filter on posted journals.</span></span>
- <span data-ttu-id="56d4c-110">Wybierz menu **Wycofaj** w górnej części strony.</span><span class="sxs-lookup"><span data-stu-id="56d4c-110">Select the **Reverse** menu at the top of the page.</span></span>
- <span data-ttu-id="56d4c-111">Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy</span><span class="sxs-lookup"><span data-stu-id="56d4c-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="56d4c-112">Wybierz opcję **Tak**, aby zastosować istniejące daty transakcji lub **Nie**, aby wprowadzić nową datę.</span><span class="sxs-lookup"><span data-stu-id="56d4c-112">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="56d4c-113">W niektórych przypadkach okres oryginalnej transakcji może zostać zamknięty i konieczne jest wprowadzenie nowej daty transakcji dla wycofania.</span><span class="sxs-lookup"><span data-stu-id="56d4c-113">In some cases, the period of the original transaction may be closed and you must enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="56d4c-114">Jeśli wybrano opcję **Nie**, wprowadź datę transakcji dla wycofania.</span><span class="sxs-lookup"><span data-stu-id="56d4c-114">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="56d4c-115">Umożliwia wprowadzenie komentarza, który ma zostać dodany do transakcji wycofania.</span><span class="sxs-lookup"><span data-stu-id="56d4c-115">Enter a comment that you want added to the reversal transaction.</span></span>
- <span data-ttu-id="56d4c-116">Wybierz przycisk **Wycofaj**.</span><span class="sxs-lookup"><span data-stu-id="56d4c-116">Select the **Reverse** button.</span></span>

<span data-ttu-id="56d4c-117">Transakcje zostaną wycofane.</span><span class="sxs-lookup"><span data-stu-id="56d4c-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="56d4c-118">Jeśli załącznik zawiera więcej niż 100 wierszy, proces wycofania zostanie uruchomiony przy użyciu procesu przetwarzania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="56d4c-118">If the voucher contains more than 100 lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="56d4c-119">Wyniki wycofania można ocenić, przeglądając komentarze w zadaniu wsadowym.</span><span class="sxs-lookup"><span data-stu-id="56d4c-119">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="56d4c-120">Wszystkie transakcje, których nie można wycofać, będą wyświetlane w historii zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="56d4c-120">Any transactions that couldn't be reversed will be listed in the batch job history.</span></span>

<span data-ttu-id="56d4c-121">Jeśli załącznik zawiera 100 wierszy lub mniej, proces wycofywania zostanie uruchomiony natychmiast.</span><span class="sxs-lookup"><span data-stu-id="56d4c-121">If the voucher contains 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="56d4c-122">Wyniki zostaną przedstawione w oknie dialogowym, w którym jest wyświetlany dowolny załącznik, którego nie można wycofać, oraz powód, dla którego nie można go cofnąć.</span><span class="sxs-lookup"><span data-stu-id="56d4c-122">The results will be presented in a dialog box that shows any voucher that could not be reversed, along with the reason why it could not be reversed.</span></span> <span data-ttu-id="56d4c-123">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="56d4c-123">Select **OK** to close the dialog box.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="56d4c-124">Wycofywanie załączników z listy transakcji na załączniku.</span><span class="sxs-lookup"><span data-stu-id="56d4c-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="56d4c-125">Można także wycofać załączniki z **listy transakcji na załączniku** do wszystkich ksiąg.</span><span class="sxs-lookup"><span data-stu-id="56d4c-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="56d4c-126">Ponadto można jednocześnie wycofać więcej niż jeden załącznik</span><span class="sxs-lookup"><span data-stu-id="56d4c-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="56d4c-127">Aby wycofać jeden lub więcej załączników:</span><span class="sxs-lookup"><span data-stu-id="56d4c-127">To reverse one or more vouchers:</span></span> 

- <span data-ttu-id="56d4c-128">Wybierz menu **Wycofaj** w górnej części strony</span><span class="sxs-lookup"><span data-stu-id="56d4c-128">Select the **Reverse** menu at the top of the page</span></span>
- <span data-ttu-id="56d4c-129">Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy.</span><span class="sxs-lookup"><span data-stu-id="56d4c-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed.</span></span>
- <span data-ttu-id="56d4c-130">Wybierz opcję **Tak**, aby zastosować istniejące daty transakcji lub **Nie**, aby wprowadzić nową datę.</span><span class="sxs-lookup"><span data-stu-id="56d4c-130">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="56d4c-131">W niektórych przypadkach okres oryginalnej transakcji może zostać zamknięty i konieczne jest wprowadzenie nowej daty transakcji, aby ją wycofać.</span><span class="sxs-lookup"><span data-stu-id="56d4c-131">In some cases, the period of the original transaction may be closed and you must enter a new transaction date to reverse it.</span></span>
- <span data-ttu-id="56d4c-132">Jeśli wybrano opcję **Nie**, wprowadź datę transakcji dla wycofania.</span><span class="sxs-lookup"><span data-stu-id="56d4c-132">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="56d4c-133">Umożliwia wprowadzenie komentarza opisującego transakcję wycofania.</span><span class="sxs-lookup"><span data-stu-id="56d4c-133">Enter a comment to describe the reversal transaction.</span></span>
- <span data-ttu-id="56d4c-134">Wybierz przycisk **Wycofaj**.</span><span class="sxs-lookup"><span data-stu-id="56d4c-134">Select the **Reverse** button.</span></span>

<span data-ttu-id="56d4c-135">Transakcje zostaną wycofane.</span><span class="sxs-lookup"><span data-stu-id="56d4c-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="56d4c-136">Jeśli jest więcej niż 100 wierszy, proces wycofania zostanie uruchomiony przy użyciu procesu przetwarzania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="56d4c-136">If there are more than 100 voucher lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="56d4c-137">Wyniki wycofania można ocenić, przeglądając komentarze w zadaniu wsadowym.</span><span class="sxs-lookup"><span data-stu-id="56d4c-137">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="56d4c-138">Wszystkie transakcje, których nie można wycofać, będą zapisane w historii zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="56d4c-138">Any transactions that couldn't be reversed will be noted in the batch job history.</span></span>

<span data-ttu-id="56d4c-139">Jeśli liczba wierszy załącznika wynosi 100 wierszy lub mniej, proces wycofywania zostanie uruchomiony natychmiast.</span><span class="sxs-lookup"><span data-stu-id="56d4c-139">If the number of voucher lines is 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="56d4c-140">Wyniki zostaną wyświetlone w oknie dialogowym, w którym jest wyświetlany dowolny załącznik, którego nie można wycofać, wraz z powodem.</span><span class="sxs-lookup"><span data-stu-id="56d4c-140">The results will display in a dialog box that shows any voucher that couldn't be reversed, along with the reason why.</span></span> <span data-ttu-id="56d4c-141">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="56d4c-141">Select **OK** to close the dialog box.</span></span>

<span data-ttu-id="56d4c-142">Transakcje można wycofać tylko wtedy, gdy spełniają one reguły biznesowe w celu ich wycofania.</span><span class="sxs-lookup"><span data-stu-id="56d4c-142">Transactions can be reversed only if they meet the business rules for reversing them.</span></span> <span data-ttu-id="56d4c-143">Płatności dostawcy nie można wycofać przy użyciu funkcji opisanych w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="56d4c-143">Vendor payments cannot be reversed using the capability described in this topic.</span></span> <span data-ttu-id="56d4c-144">Płatności dostawcy należy wycofać, wykonując kroki opisane w [Cofanie płatności dla dostawcy](https://docs.microsoft.com/en-us/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span><span class="sxs-lookup"><span data-stu-id="56d4c-144">Vendor payments must be reversed by following the steps listed in [Reverse a vendor payment](https://docs.microsoft.com/en-us/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span></span>

