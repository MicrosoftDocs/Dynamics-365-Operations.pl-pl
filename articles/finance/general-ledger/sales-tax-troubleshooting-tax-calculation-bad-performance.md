---
title: Wydajność obliczania podatku wpływa na transakcje
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów związanych z wydajnością obliczeń podatku i ich wpływem na transakcje.
author: shtao
manager: beya
ms.date: 04/07/2021
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
ms.openlocfilehash: 7ff9d9b80172c3b337737b1cd53b4c56d1befe57
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947695"
---
# <a name="tax-calculation-performance-affects-transactions"></a><span data-ttu-id="c71de-103">Wydajność obliczania podatku wpływa na transakcje</span><span class="sxs-lookup"><span data-stu-id="c71de-103">Tax calculation performance affects transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c71de-104">Czasami na transakcję wpływają problemy z wydajnością dotyczące obliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="c71de-104">Sometimes, a transaction is affected by performance issues that tax calculation is having.</span></span> <span data-ttu-id="c71de-105">W razie potrzeby wykonaj kroki opisane w poniższych sekcjach, aby rozwiązać ten problem.</span><span class="sxs-lookup"><span data-stu-id="c71de-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="review-the-transaction-line-count"></a><span data-ttu-id="c71de-106">Weryfikacja liczby wierszy transakcji</span><span class="sxs-lookup"><span data-stu-id="c71de-106">Review the transaction line count</span></span>

<span data-ttu-id="c71de-107">Określ, czy transakcja ma dużą liczbę wierszy (na przykład więcej niż kilkaset).</span><span class="sxs-lookup"><span data-stu-id="c71de-107">Determine whether the transaction has a large number of lines (for example, more than several hundred).</span></span> <span data-ttu-id="c71de-108">Jeśli nie, przejdź do następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="c71de-108">If it doesn't, move on to the next section.</span></span> <span data-ttu-id="c71de-109">Jeśli transakcja ma kilkaset wierszy, opóźnij obliczanie podatku.</span><span class="sxs-lookup"><span data-stu-id="c71de-109">If the transaction does have several hundred lines, delay the tax calculation.</span></span> <span data-ttu-id="c71de-110">Aby uzyskać więcej informacji, zobacz temat [Włączanie opóźnionego obliczania podatku w arkuszach](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="c71de-110">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span> 

<span data-ttu-id="c71de-111">Następnie można określić, czy któryś z poniższych warunków jest spełniony:</span><span class="sxs-lookup"><span data-stu-id="c71de-111">Next, you can determine whether any of the following conditions are met:</span></span>

- <span data-ttu-id="c71de-112">Istnieją transakcje importu z dużych plików.</span><span class="sxs-lookup"><span data-stu-id="c71de-112">There are import transactions from large files.</span></span>
- <span data-ttu-id="c71de-113">W wielu sesjach jest jednocześnie przetwarzany ten sam podatek dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="c71de-113">Multiple sessions process the same transaction tax calculation at the same time.</span></span>
- <span data-ttu-id="c71de-114">Transakcja ma wiele wierszy, a widoki są aktualizowane w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="c71de-114">The transaction has multiple lines, and the views are updated in real time.</span></span> <span data-ttu-id="c71de-115">Na przykład pole **Obliczona kwota podatku** na stronie **Arkusz ogólny** jest aktualizowane w czasie rzeczywistym, gdy pola wiersza uległy zmianie.</span><span class="sxs-lookup"><span data-stu-id="c71de-115">For example, the **Calculated sales tax amount** field on the **General journal** page is updated in real time when a line's fields are changed.</span></span>

   <span data-ttu-id="c71de-116">[![Pole obliczonej kwoty podatku na stronie załącznika arkusza](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="c71de-116">[![Calculated sales tax amount field on the Jounal voucher page](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span></span>

<span data-ttu-id="c71de-117">Jeśli którykolwiek z tych warunków jest spełniony, opóźnij obliczanie podatku.</span><span class="sxs-lookup"><span data-stu-id="c71de-117">If any of these conditions are met, delay the tax calculation.</span></span>

## <a name="review-the-call-stack"></a><span data-ttu-id="c71de-118">Przeglądanie stosu wywołań</span><span class="sxs-lookup"><span data-stu-id="c71de-118">Review the call stack</span></span>

<span data-ttu-id="c71de-119">Przejrzyj stos wywołań, aby określić, czy obliczanie podatku jest wywoływane wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="c71de-119">Review the call stack to determine whether tax calculation is called multiple times.</span></span> <span data-ttu-id="c71de-120">Jeśli nie jest, przejdź do następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="c71de-120">If it isn't, move on to the next section.</span></span> <span data-ttu-id="c71de-121">Jeśli stos wywołań jest wywoływany wielokrotnie, należy wykonać następujące kroki, aby skrócić czas obliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="c71de-121">If the call stack is called multiple times, follow these steps to help reduce the tax calculation times.</span></span>

1. <span data-ttu-id="c71de-122">Jeśli arkusz uwzględnia transakcję, opóźnij obliczanie podatku.</span><span class="sxs-lookup"><span data-stu-id="c71de-122">If the journal has considered the transaction, delay the tax calculation.</span></span> <span data-ttu-id="c71de-123">Aby uzyskać więcej informacji, zobacz temat [Włączanie opóźnionego obliczania podatku w arkuszach](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="c71de-123">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span>
2. <span data-ttu-id="c71de-124">Jeśli transakcja jest zamówieniem zakupu, a wersja aplikacji jest nowsza niż 10.0.15, można opóźnić obliczanie podatku do czasu ostatecznego obliczenia, włączając flighting **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span><span class="sxs-lookup"><span data-stu-id="c71de-124">If the transaction is a purchase order, and the application version is later than 10.0.15, you can delay the tax calculation until the final calculation by enabling the flighting for **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span></span>

## <a name="review-the-call-stack-timeline"></a><span data-ttu-id="c71de-125">Przeglądanie osi czasu stosu wywołań</span><span class="sxs-lookup"><span data-stu-id="c71de-125">Review the call stack timeline</span></span>

<span data-ttu-id="c71de-126">Przejrzyj oś czasu stosu wywołań, aby określić, czy istnieją następujące problemy.</span><span class="sxs-lookup"><span data-stu-id="c71de-126">Review the call stack timeline to determine whether the following issues exist.</span></span> <span data-ttu-id="c71de-127">Jeśli tak, włącz flighting **TaxUncommittedDoIsolateScopeFlighting**, aby rozwiązać ten problem.</span><span class="sxs-lookup"><span data-stu-id="c71de-127">If they do, enable the flighting for **TaxUncommittedDoIsolateScopeFlighting** to fix the issue.</span></span>

- <span data-ttu-id="c71de-128">Transakcja powoduje, że system zawiesza się do końca sesji.</span><span class="sxs-lookup"><span data-stu-id="c71de-128">The transaction causes the system to stop responding until the session ends.</span></span> <span data-ttu-id="c71de-129">W związku z tym transakcja nie może obliczyć wyniku podatku.</span><span class="sxs-lookup"><span data-stu-id="c71de-129">Therefore, the transaction can't calculate the tax result.</span></span> <span data-ttu-id="c71de-130">Na poniższej ilustracji przedstawiono odbierane okno komunikatu „Sesja zakończona”.</span><span class="sxs-lookup"><span data-stu-id="c71de-130">The following illustration shows the "Session ended" message box that you receive.</span></span>

    <span data-ttu-id="c71de-131">[![Komunikat o zakończeniu sesji](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="c71de-131">[![Session ended message](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span></span>

- <span data-ttu-id="c71de-132">Metody **TaxUncommitted** zabierają więcej czasu niż inne metody.</span><span class="sxs-lookup"><span data-stu-id="c71de-132">The **TaxUncommitted** methods take more time than other methods.</span></span> <span data-ttu-id="c71de-133">Na przykład na poniższej ilustracji metoda **TaxUncommitted::updateTaxUncommitted()** zabiera 43 347,42 sekundy, a inne metody tylko 0,09 sekundy.</span><span class="sxs-lookup"><span data-stu-id="c71de-133">For example, in the following illustration, the **TaxUncommitted::updateTaxUncommitted()** method takes 43,347.42 seconds, but other methods take 0.09 seconds.</span></span>

    <span data-ttu-id="c71de-134">[![Czasy trwania metod](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="c71de-134">[![Method durations](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span></span>

## <a name="customizing-and-calling-tax-calculation"></a><span data-ttu-id="c71de-135">Dostosowywanie i wywoływanie obliczeń podatku</span><span class="sxs-lookup"><span data-stu-id="c71de-135">Customizing and calling tax calculation</span></span>

<span data-ttu-id="c71de-136">Podczas dostosowywania nie należy wywołać obliczania przy metodzie **insert()** lub **update()** w każdym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c71de-136">When you customize, don't call tax calculation at the **insert()** or **update()** method for each line.</span></span> <span data-ttu-id="c71de-137">Obliczanie podatku powinno być wywoływane na poziomie transakcji.</span><span class="sxs-lookup"><span data-stu-id="c71de-137">Tax calculation should be called at the transaction level.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="c71de-138">Określanie, czy dostosowanie istnieje</span><span class="sxs-lookup"><span data-stu-id="c71de-138">Determine whether customization exists</span></span>

<span data-ttu-id="c71de-139">Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie znaleziono problemu, określ, czy dostosowanie istnieje.</span><span class="sxs-lookup"><span data-stu-id="c71de-139">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="c71de-140">Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.</span><span class="sxs-lookup"><span data-stu-id="c71de-140">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
