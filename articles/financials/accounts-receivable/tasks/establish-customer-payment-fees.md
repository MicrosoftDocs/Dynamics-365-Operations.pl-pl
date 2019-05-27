---
title: Definiowanie opłat od płatności odbiorcy
description: Utwórz opłaty od płatności dla płatności odbiorców.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5acb202d46ef39376a01ca592f60926786d11186
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572981"
---
# <a name="establish-customer-payment-fees"></a><span data-ttu-id="62ce9-103">Definiowanie opłat od płatności odbiorcy</span><span class="sxs-lookup"><span data-stu-id="62ce9-103">Establish customer payment fees</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="62ce9-104">Utwórz opłaty od płatności dla płatności odbiorców.</span><span class="sxs-lookup"><span data-stu-id="62ce9-104">Create payment fees for customer payments.</span></span>

<span data-ttu-id="62ce9-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="62ce9-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="62ce9-106">Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Opłata.</span><span class="sxs-lookup"><span data-stu-id="62ce9-106">Go to Accounts receivable > Payments setup > Payment fee.</span></span>
2. <span data-ttu-id="62ce9-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="62ce9-107">Click New.</span></span>
3. <span data-ttu-id="62ce9-108">W polu Identyfikator opłaty wpisz identyfikator opłaty.</span><span class="sxs-lookup"><span data-stu-id="62ce9-108">In the Fee ID field, enter a Fee ID.</span></span>
    * <span data-ttu-id="62ce9-109">Identyfikator opłaty jest wyświetlany w arkuszach płatności. Powinien być opisowy, aby użytkownicy rozumieli charakter opłaty.</span><span class="sxs-lookup"><span data-stu-id="62ce9-109">The Fee ID displays on payment journals, so make it descriptive to understand what fee is being assessed.</span></span>  
4. <span data-ttu-id="62ce9-110">W polu Nazwa nadaj opłacie nazwę.</span><span class="sxs-lookup"><span data-stu-id="62ce9-110">In the Name field, enter a fee Name.</span></span>
5. <span data-ttu-id="62ce9-111">W polu Opis opłaty wprowadź opis opłaty.</span><span class="sxs-lookup"><span data-stu-id="62ce9-111">In the Fee description field, enter a description for the fee.</span></span>
6. <span data-ttu-id="62ce9-112">Określ, czy opłata będzie obciążała odbiorcę czy konto księgowe.</span><span class="sxs-lookup"><span data-stu-id="62ce9-112">Select whether the fee will be charged to the Customer or a Ledger account.</span></span>
    * <span data-ttu-id="62ce9-113">Jeśli opłata będzie naliczana odbiorcy, zaznacz opcję Odbiorca.</span><span class="sxs-lookup"><span data-stu-id="62ce9-113">If the customer is assessed the fee, select Customer.</span></span> <span data-ttu-id="62ce9-114">Jeśli opłata będzie naliczana organizacji jako wydatek, zaznacz opcję Księga.</span><span class="sxs-lookup"><span data-stu-id="62ce9-114">If the fee will be assess to your organization as an expense, select Ledger.</span></span> <span data-ttu-id="62ce9-115">Dla tego zadania wybierz opcję Odbiorca.</span><span class="sxs-lookup"><span data-stu-id="62ce9-115">For this task, select Customer.</span></span>  
7. <span data-ttu-id="62ce9-116">Wybierz typ arkusza, w którym można używać tej opłaty od płatności.</span><span class="sxs-lookup"><span data-stu-id="62ce9-116">Select the type of  journal that can use this payment fee.</span></span>
    * <span data-ttu-id="62ce9-117">Jeśli te opłaty są używane dla płatności odbiorców, typem arkusza będzie prawdopodobnie Płatność od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="62ce9-117">If these fees are used for customer payments, the journal type will likely be Customer payment.</span></span>  
8. <span data-ttu-id="62ce9-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="62ce9-118">Click Save.</span></span>
9. <span data-ttu-id="62ce9-119">Kliknij opcję Ustawienia opłat.</span><span class="sxs-lookup"><span data-stu-id="62ce9-119">Click Payment fee setup.</span></span>
    * <span data-ttu-id="62ce9-120">Opcja Ustawienia opłat służy do definiowania kryteriów, według których będą naliczane opłaty od płatności.</span><span class="sxs-lookup"><span data-stu-id="62ce9-120">The Payment fee setup is used to define the criteria for when the payment fee will be assessed.</span></span>  <span data-ttu-id="62ce9-121">Na przykład można określić naliczanie opłaty, gdy kontem bankowym jest USMF OPER, a metodą płatności Czek.</span><span class="sxs-lookup"><span data-stu-id="62ce9-121">For example, you can define that the fee will be calculated if the bank account is USMF OPER, and the method of payment is check.</span></span>  
10. <span data-ttu-id="62ce9-122">Zaznacz opcję Tabela, Grupa lub Wszystko, aby określić, na których kontach bankowych będzie naliczana ta opłata.</span><span class="sxs-lookup"><span data-stu-id="62ce9-122">Select either Table, Group or All to define which bank accounts will be assessed this fee.</span></span>
    * <span data-ttu-id="62ce9-123">Jeśli zaznaczysz opcję Wszystko, ta opłata może być obliczana dla wszystkich kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="62ce9-123">If you select All, all bank accounts could be assessed this fee.</span></span>  <span data-ttu-id="62ce9-124">Jeśli wybierzesz opcję Tabela, opłata może być naliczana tylko dla wskazanego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="62ce9-124">If you select Table, only the bank account you select could be assessed this fee.</span></span> <span data-ttu-id="62ce9-125">Jeżeli zostanie wybrana opcja Grupa, opłata będzie naliczana tylko dla kont bankowych w wybranej grupie bankowej.</span><span class="sxs-lookup"><span data-stu-id="62ce9-125">If you select Group, only the bank accounts in the selected bank group could be assessed this fee.</span></span>  
11. <span data-ttu-id="62ce9-126">Zaznacz grupę bankową lub konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="62ce9-126">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="62ce9-127">Jeśli została wybrana opcja Tabela, wyszukiwanie spowoduje wyświetlenie kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="62ce9-127">If you selected Table, the lookup will display bank accounts.</span></span> <span data-ttu-id="62ce9-128">Jeśli została wybrana opcja Grupa, wyszukiwanie spowoduje wyświetlenie grup bankowej.</span><span class="sxs-lookup"><span data-stu-id="62ce9-128">If you selected Group, the lookup will display bank groups.</span></span>  
12. <span data-ttu-id="62ce9-129">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="62ce9-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="62ce9-130">Zaznacz metodę płatności, w której opłata będzie naliczana.</span><span class="sxs-lookup"><span data-stu-id="62ce9-130">Select the Method of payment for which this fee will be assessed.</span></span>
    * <span data-ttu-id="62ce9-131">Na przykład można naliczać opłatę odbiorcom, jeśli dokonują płatności czekami a nie drogą elektroniczną.</span><span class="sxs-lookup"><span data-stu-id="62ce9-131">For example, you may assess a fee to your customers if they send payments as a check, rather than as an electronic payment.</span></span>  
14. <span data-ttu-id="62ce9-132">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="62ce9-132">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="62ce9-133">W razie potrzeby wprowadź walutę płatności.</span><span class="sxs-lookup"><span data-stu-id="62ce9-133">If relevant, enter a payment currency.</span></span>
    * <span data-ttu-id="62ce9-134">Waluta płatności służy jako dodatkowe kryterium określania, czy opłata będzie naliczana.</span><span class="sxs-lookup"><span data-stu-id="62ce9-134">The payment currency is used as an additional criteria for whether the fee will be assessed.</span></span>  <span data-ttu-id="62ce9-135">Na przykład bank może obciążać dodatkową opłatą płatności otrzymywane w dolarach amerykańskich, ponieważ normalnie obsługuje transakcje tylko w euro.</span><span class="sxs-lookup"><span data-stu-id="62ce9-135">For example, your bank may charge an extra fee for payments received in USD currency, since they normally only transact in EUR currency.</span></span>  
16. <span data-ttu-id="62ce9-136">Określ, czy opłata będzie procentem, kwotą czy interwałem.</span><span class="sxs-lookup"><span data-stu-id="62ce9-136">Select whether the fee will be a percent, amount or interval.</span></span>
17. <span data-ttu-id="62ce9-137">Wprowadź procent lub kwotę opłaty.</span><span class="sxs-lookup"><span data-stu-id="62ce9-137">Enter either percentage or amount of the fee.</span></span>
    * <span data-ttu-id="62ce9-138">Jeśli pole Procent/Kwota zawiera wartość Procent, wartość wprowadzona w tym polu będzie wartością procentową.</span><span class="sxs-lookup"><span data-stu-id="62ce9-138">If the Percentage/Amount field is Percent, then the value enter here will be a percentage.</span></span> <span data-ttu-id="62ce9-139">Jeśli pole Procent/Kwota zawiera wartość Kwota, wartość wprowadzona w tym polu będzie kwotą.</span><span class="sxs-lookup"><span data-stu-id="62ce9-139">If the Percentage/Amount field is Amount, then the value you enter here will be an amount.</span></span> <span data-ttu-id="62ce9-140">Jeśli pole Procent/Kwota zawiera wartość Interwał, należy zdefiniować warstwy na karcie Interwał.</span><span class="sxs-lookup"><span data-stu-id="62ce9-140">If the Percentage/Amount field is Interval, use the Interval tab to define the tiers.</span></span>  
18. <span data-ttu-id="62ce9-141">W polu Waluta opłaty wybierz walutę opłaty.</span><span class="sxs-lookup"><span data-stu-id="62ce9-141">In the Fee currency field, select the currency of the fee.</span></span>
    * <span data-ttu-id="62ce9-142">Jest to waluta, w której zostanie utworzona opłata.</span><span class="sxs-lookup"><span data-stu-id="62ce9-142">This is the currency in which the fee will be created.</span></span>  
19. <span data-ttu-id="62ce9-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="62ce9-143">Click Save.</span></span>

