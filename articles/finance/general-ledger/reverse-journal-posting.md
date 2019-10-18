---
title: Odwróć księgowanie arkusza
description: W tym temacie opisano możliwości wystornowania załączników z listy transakcji na załączniku lub z arkuszy finansowych.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
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
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248592"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="89778-103">Odwróć księgowanie arkusza</span><span class="sxs-lookup"><span data-stu-id="89778-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89778-104">W tym temacie opisano możliwości Microsoft Dynamics 365 Finance, które pozwalają wycofać cały arkusz lub wycofać jeden lub więcej załączników z listy transakcji załącznika bez względu na ich pochodzenie.</span><span class="sxs-lookup"><span data-stu-id="89778-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal or reverse one or more vouchers from the voucher transaction list regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="89778-105">Wycofywanie arkuszy</span><span class="sxs-lookup"><span data-stu-id="89778-105">Reversing journals</span></span>

<span data-ttu-id="89778-106">Wiersze arkusza można odwracać pojedynczo.</span><span class="sxs-lookup"><span data-stu-id="89778-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="89778-107">W przypadku księgowania wstecznego arkusza można również wycofywać cały arkusz finansowy.</span><span class="sxs-lookup"><span data-stu-id="89778-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="89778-108">Wycofywanie arkusza:</span><span class="sxs-lookup"><span data-stu-id="89778-108">To reverse a journal:</span></span> 
- <span data-ttu-id="89778-109">Umożliwia otwarcie arkusza finansowego i przefiltrowanie arkuszy w zaksięgowanych arkuszach</span><span class="sxs-lookup"><span data-stu-id="89778-109">Open the financial journal and filter on posted journals</span></span>
- <span data-ttu-id="89778-110">W menu w górnej części strony kliknij Odwróć</span><span class="sxs-lookup"><span data-stu-id="89778-110">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="89778-111">Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy</span><span class="sxs-lookup"><span data-stu-id="89778-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="89778-112">Wybierz opcję tak, aby zastosować istniejące daty transakcji lub nie, aby wprowadzić nową datę.</span><span class="sxs-lookup"><span data-stu-id="89778-112">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="89778-113">W niektórych przypadkach okres oryginalnej transakcji może zostać zamknięty i konieczne jest wprowadzenie nowej daty transakcji dla wycofania.</span><span class="sxs-lookup"><span data-stu-id="89778-113">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="89778-114">Jeśli wybrano opcję nie, wprowadź datę transakcji dla wycofania.</span><span class="sxs-lookup"><span data-stu-id="89778-114">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="89778-115">Umożliwia wprowadzenie komentarza, który ma zostać dodany do transakcji wycofania</span><span class="sxs-lookup"><span data-stu-id="89778-115">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="89778-116">Kliknij przycisk wycofaj</span><span class="sxs-lookup"><span data-stu-id="89778-116">Click the Reverse button</span></span>

<span data-ttu-id="89778-117">Transakcje zostaną wycofane.</span><span class="sxs-lookup"><span data-stu-id="89778-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="89778-118">Jeśli liczba wierszy załącznika przekracza 100 wierszy, proces wycofania zostanie uruchomiony przy użyciu procesu przetwarzania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="89778-118">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="89778-119">Wyniki wycofania można przejrzeć, przeglądając komentarze w uruchomionym zadaniu wsadowym.</span><span class="sxs-lookup"><span data-stu-id="89778-119">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="89778-120">Wszystkie błędy zostaną odnotowane w historii zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="89778-120">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="89778-121">Jeśli liczba wierszy załącznika nie przekracza 100 wierszy lub mniej, proces wycofywania zostanie uruchomiony natychmiast.</span><span class="sxs-lookup"><span data-stu-id="89778-121">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="89778-122">Wyniki zostaną przedstawione w oknie dialogowym, w którym jest wyświetlany dowolny załącznik, którego nie można wycofać, oraz powód, dla którego nie można go cofnąć.</span><span class="sxs-lookup"><span data-stu-id="89778-122">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="89778-123">Kliknij przycisk OK, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="89778-123">Click on Ok to close the dialog.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="89778-124">Wycofywanie załączników z listy transakcji na załączniku.</span><span class="sxs-lookup"><span data-stu-id="89778-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="89778-125">Można także wycofać załączniki z **listy transakcji na załączniku** do wszystkich ksiąg.</span><span class="sxs-lookup"><span data-stu-id="89778-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="89778-126">Ponadto można jednocześnie wycofać więcej niż jeden załącznik</span><span class="sxs-lookup"><span data-stu-id="89778-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="89778-127">Aby wycofać jeden lub więcej załączników:</span><span class="sxs-lookup"><span data-stu-id="89778-127">To reverse one or more vouchers:</span></span> 
- <span data-ttu-id="89778-128">W menu w górnej części strony kliknij Odwróć</span><span class="sxs-lookup"><span data-stu-id="89778-128">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="89778-129">Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy</span><span class="sxs-lookup"><span data-stu-id="89778-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="89778-130">Wybierz opcję tak, aby zastosować istniejące daty transakcji lub nie, aby wprowadzić nową datę.</span><span class="sxs-lookup"><span data-stu-id="89778-130">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="89778-131">W niektórych przypadkach okres oryginalnej transakcji może zostać zamknięty i konieczne jest wprowadzenie nowej daty transakcji dla wycofania.</span><span class="sxs-lookup"><span data-stu-id="89778-131">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="89778-132">Jeśli wybrano opcję nie, wprowadź datę transakcji dla wycofania.</span><span class="sxs-lookup"><span data-stu-id="89778-132">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="89778-133">Umożliwia wprowadzenie komentarza, który ma zostać dodany do transakcji wycofania</span><span class="sxs-lookup"><span data-stu-id="89778-133">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="89778-134">Kliknij przycisk wycofaj</span><span class="sxs-lookup"><span data-stu-id="89778-134">Click the Reverse button</span></span>

<span data-ttu-id="89778-135">Transakcje zostaną wycofane.</span><span class="sxs-lookup"><span data-stu-id="89778-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="89778-136">Jeśli liczba wierszy załącznika przekracza 100 wierszy, proces wycofania zostanie uruchomiony przy użyciu procesu przetwarzania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="89778-136">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="89778-137">Wyniki wycofania można przejrzeć, przeglądając komentarze w uruchomionym zadaniu wsadowym.</span><span class="sxs-lookup"><span data-stu-id="89778-137">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="89778-138">Wszystkie błędy zostaną odnotowane w historii zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="89778-138">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="89778-139">Jeśli liczba wierszy załącznika nie przekracza 100 wierszy lub mniej, proces wycofywania zostanie uruchomiony natychmiast.</span><span class="sxs-lookup"><span data-stu-id="89778-139">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="89778-140">Wyniki zostaną przedstawione w oknie dialogowym, w którym jest wyświetlany dowolny załącznik, którego nie można wycofać, oraz powód, dla którego nie można go cofnąć.</span><span class="sxs-lookup"><span data-stu-id="89778-140">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="89778-141">Kliknij przycisk OK, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="89778-141">Click on Ok to close the dialog.</span></span>

