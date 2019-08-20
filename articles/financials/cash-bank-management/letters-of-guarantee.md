---
title: Poręczenia
description: Ten artykuł zawiera informacje o poręczeniach. W poręczeniu bank zgadza się zapłacić określoną kwotę pieniędzy osobie, jeśli jeden z klientów banku nie ureguluje wobec tej osoby zobowiązania pieniężnego lub innego.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e7ab2e66c378388d002d2f2090f89bf6c96dac2
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842336"
---
# <a name="letters-of-guarantee"></a><span data-ttu-id="ef38b-104">Poręczenia</span><span class="sxs-lookup"><span data-stu-id="ef38b-104">Letters of guarantee</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef38b-105">Ten artykuł zawiera informacje o poręczeniach.</span><span class="sxs-lookup"><span data-stu-id="ef38b-105">This article provides information about letters of guarantee.</span></span> <span data-ttu-id="ef38b-106">W poręczeniu bank zgadza się zapłacić określoną kwotę pieniędzy osobie, jeśli jeden z klientów banku nie ureguluje wobec tej osoby zobowiązania pieniężnego lub innego.</span><span class="sxs-lookup"><span data-stu-id="ef38b-106">In a letter of guarantee, a bank agrees to pay a specific amount of money to a person if one of the bank's customers defaults on a payment or obligation to that person.</span></span> 

<span data-ttu-id="ef38b-107">Poręczenie to zobowiązanie się banku (gwaranta) do zapłaty określonej kwoty pieniędzy określonej osobie (beneficjentowi), jeśli bank odbiorca (podmiot zabezpieczeń) nie wywiąże się z realizacji płatności lub zobowiązania względem beneficjenta.</span><span class="sxs-lookup"><span data-stu-id="ef38b-107">A letter of guarantee is an agreement by a bank (the guarantor) to pay a set amount of money to some person (the beneficiary) if a bank customer (the principal) defaults on a payment or an obligation to the beneficiary.</span></span> <span data-ttu-id="ef38b-108">Poręczenia są niezbywalne.</span><span class="sxs-lookup"><span data-stu-id="ef38b-108">Letters of guarantee aren't transferable.</span></span> <span data-ttu-id="ef38b-109">Dotyczą one tylko beneficjenta wskazanego w umowie.</span><span class="sxs-lookup"><span data-stu-id="ef38b-109">They apply only to the beneficiary who is named in the agreement.</span></span> <span data-ttu-id="ef38b-110">Podmiot zabezpieczeń może wnioskować o zwiększenie lub zmniejszenie wartości poręczenia, zgodnie z warunkami umowy.</span><span class="sxs-lookup"><span data-stu-id="ef38b-110">The principal can request an increase or decrease in the value of a letter of guarantee, subject to the terms of the agreement.</span></span> 

<span data-ttu-id="ef38b-111">Aby zrealizować poręczenie, beneficjent musi przed upływem daty ważności przesłać oryginalne poręczenie i poinformować bank obsługujący zobowiązania podmiotu zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="ef38b-111">To liquidate a letter of guarantee, the beneficiary must submit the original letter of guarantee and inform the bank of the principal’s default before the expiration date.</span></span> <span data-ttu-id="ef38b-112">Bank następnie wypłaca kwotę należności na konto beneficjenta zgodnie z ustaleniami określonymi w poręczeniu.</span><span class="sxs-lookup"><span data-stu-id="ef38b-112">The bank then pays the amount that is due to the beneficiary's account, according to the terms in the letter of guarantee.</span></span> <span data-ttu-id="ef38b-113">Bank zatrzymuje procent płatności jako marżę.</span><span class="sxs-lookup"><span data-stu-id="ef38b-113">The bank reserves a percentage of the payment as a margin.</span></span> <span data-ttu-id="ef38b-114">Wartość procentowa jest uzgodniona z góry i zapisana w warunkach umowy.</span><span class="sxs-lookup"><span data-stu-id="ef38b-114">The percentage is agreed upon and specified in the terms of the agreement.</span></span> 

<span data-ttu-id="ef38b-115">Można utworzyć kod do śledzenia celu poręczenia.</span><span class="sxs-lookup"><span data-stu-id="ef38b-115">You can create a code to track the purpose of a letter of guarantee.</span></span> <span data-ttu-id="ef38b-116">Można również określić przyczyny, które będą skojarzone z poręczeniem w przypadku jego anulowania.</span><span class="sxs-lookup"><span data-stu-id="ef38b-116">You can also specify the reasons that can be associated with a letter of guarantee when the letter is canceled.</span></span> <span data-ttu-id="ef38b-117">Kody celów i przyczyny podane przez bank można wyświetlać na stronach **Kody celów płatności** i **Przyczyny transakcji bankowych**.</span><span class="sxs-lookup"><span data-stu-id="ef38b-117">You can view the purpose codes and bank reasons on the **Payment purpose codes** and **Bank reasons** pages.</span></span> 

<span data-ttu-id="ef38b-118">Na stronie **poręczenia** można wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="ef38b-118">You can use the **Letter of guarantee** page to complete these tasks:</span></span>

-   <span data-ttu-id="ef38b-119">Tworzenie poprawnych pozycji księgowania i eliminacja wprowadzania ręcznego.</span><span class="sxs-lookup"><span data-stu-id="ef38b-119">Create correct ledger entries, and eliminate manual entry.</span></span>
-   <span data-ttu-id="ef38b-120">Rejestrowanie wszystkich powiązanych transakcji pieniężnych i niepieniężnych i śledzenie sald poręczeń.</span><span class="sxs-lookup"><span data-stu-id="ef38b-120">Record all monetary and nonmonetary transactions, and track balances of letters of guarantee.</span></span>
-   <span data-ttu-id="ef38b-121">Rejestrowanie i śledzenie stanu i dat wygaśnięcia poręczenia.</span><span class="sxs-lookup"><span data-stu-id="ef38b-121">Record and track the status and expiration of letters of guarantee.</span></span>
-   <span data-ttu-id="ef38b-122">Generowanie raportu, który zawiera listę banków posiadających poręczenia.</span><span class="sxs-lookup"><span data-stu-id="ef38b-122">Generate a report that lists the banks that are holding letters of guarantee.</span></span>

<span data-ttu-id="ef38b-123">W poniższej tabeli opisano akcje, które można wykonywać w związku z poręczeniem.</span><span class="sxs-lookup"><span data-stu-id="ef38b-123">The following table describes the actions that you can perform on a letter of guarantee.</span></span>

| <span data-ttu-id="ef38b-124">Akcja</span><span class="sxs-lookup"><span data-stu-id="ef38b-124">Action</span></span>              | <span data-ttu-id="ef38b-125">Cel</span><span class="sxs-lookup"><span data-stu-id="ef38b-125">Purpose</span></span>                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ef38b-126">Prześlij do banku</span><span class="sxs-lookup"><span data-stu-id="ef38b-126">Submit to bank</span></span>      | <span data-ttu-id="ef38b-127">Przesłanie do banku wniosku o wystawienie poręczenia.</span><span class="sxs-lookup"><span data-stu-id="ef38b-127">Submit the letter of guarantee request to the bank.</span></span>                                                                       |
| <span data-ttu-id="ef38b-128">Otrzymaj z banku</span><span class="sxs-lookup"><span data-stu-id="ef38b-128">Receive from bank</span></span>   | <span data-ttu-id="ef38b-129">Gdy bank wyrazi zgodę na przesłany wniosek, można odebrać poręczenie.</span><span class="sxs-lookup"><span data-stu-id="ef38b-129">After the bank agrees to the submitted request, collect the letter of guarantee from the bank.</span></span>                            |
| <span data-ttu-id="ef38b-130">Przekaż beneficjentowi</span><span class="sxs-lookup"><span data-stu-id="ef38b-130">Give to beneficiary</span></span> | <span data-ttu-id="ef38b-131">Po otrzymaniu poręczenia z banku można je przekazać beneficjentowi.</span><span class="sxs-lookup"><span data-stu-id="ef38b-131">After you receive the letter of guarantee from the bank, provide the letter of guarantee to the beneficiary.</span></span>              |
| <span data-ttu-id="ef38b-132">Zwiększ wartość</span><span class="sxs-lookup"><span data-stu-id="ef38b-132">Increase value</span></span>      | <span data-ttu-id="ef38b-133">Jeśli beneficjent i podmiot zabezpieczeń wyrażą zgodę, można zwiększyć wartość pieniężną.</span><span class="sxs-lookup"><span data-stu-id="ef38b-133">If the beneficiary and the principal agree, increase the monetary value.</span></span>                                                  |
| <span data-ttu-id="ef38b-134">Zmniejsz wartość</span><span class="sxs-lookup"><span data-stu-id="ef38b-134">Decrease value</span></span>      | <span data-ttu-id="ef38b-135">Jeśli beneficjent i podmiot zabezpieczeń wyrażą zgodę, można zmniejszyć wartość pieniężną.</span><span class="sxs-lookup"><span data-stu-id="ef38b-135">If the beneficiary and the principal agree, decrease the monetary value.</span></span>                                                  |
| <span data-ttu-id="ef38b-136">Rozszerz</span><span class="sxs-lookup"><span data-stu-id="ef38b-136">Extend</span></span>              | <span data-ttu-id="ef38b-137">Po przedstawieniu beneficjentowi poręczenia można wydłużyć okres ważności, jeśli jego wydłużenie jest konieczne.</span><span class="sxs-lookup"><span data-stu-id="ef38b-137">After you provide the letter of guarantee to the beneficiary, extend the period of validity, if an extension is required.</span></span> |
| <span data-ttu-id="ef38b-138">Anuluj</span><span class="sxs-lookup"><span data-stu-id="ef38b-138">Cancel</span></span>              | <span data-ttu-id="ef38b-139">Jeśli cel poręczenia nie ma już zastosowania, można anulować umowę.</span><span class="sxs-lookup"><span data-stu-id="ef38b-139">When the purpose that the letter of guarantee was requested for no longer applies, cancel the agreement.</span></span>                  |
| <span data-ttu-id="ef38b-140">Zlikwiduj</span><span class="sxs-lookup"><span data-stu-id="ef38b-140">Liquidate</span></span>           | <span data-ttu-id="ef38b-141">Kiedy beneficjent okaże w banku poręczenie, można je spłacić.</span><span class="sxs-lookup"><span data-stu-id="ef38b-141">When the beneficiary presents the letter of guarantee to the bank, cash out the letter of guarantee.</span></span>                      |


<span data-ttu-id="ef38b-142">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="ef38b-142">For more information, see the following topics:</span></span>

[<span data-ttu-id="ef38b-143">Transakcja poręczenia</span><span class="sxs-lookup"><span data-stu-id="ef38b-143">Letter of guarantee transaction</span></span>](tasks/letter-guarantee-transaction.md)

[<span data-ttu-id="ef38b-144">Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczeń</span><span class="sxs-lookup"><span data-stu-id="ef38b-144">Set up bank facilities and posting profiles for letters of guarantee</span></span>](tasks/set-up-bank-facilities-posting-profiles.md)


