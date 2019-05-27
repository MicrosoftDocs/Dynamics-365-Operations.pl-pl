---
title: Tworzenie płatności dla odbiorcy, który ma pozwolenie na polecenie zapłaty
description: W tej procedurze pokazano sposób generowania pliku płatności poleceniem zapłaty ISO20022 dla odbiorcy, który ma skonfigurowaną obsługę poleceń zapłaty i fakturę do zapłaty.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6781ac38fff6344bfc9546c3ffd2253fb3ef712c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570037"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="cab93-103">Tworzenie płatności dla odbiorcy, który ma pozwolenie na polecenie zapłaty</span><span class="sxs-lookup"><span data-stu-id="cab93-103">Create payments for a customer who have direct debit mandates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cab93-104">W tej procedurze pokazano sposób generowania pliku płatności poleceniem zapłaty ISO20022 dla odbiorcy, który ma skonfigurowaną obsługę poleceń zapłaty i fakturę do zapłaty.</span><span class="sxs-lookup"><span data-stu-id="cab93-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="cab93-105">Tworzenie i księgowanie faktury jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="cab93-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="cab93-106">Zamiast mieć fakturę do zapłaty można przed wygenerowaniem pliku płatności wybrać w arkuszu zgodę, aby umożliwić obsługę scenariusza przedpłaty od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="cab93-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="cab93-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="cab93-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="cab93-108">Jest to piąta z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="cab93-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="cab93-109">Przed wykonaniem tego zadania należy wykonać wcześniejsze zadania.</span><span class="sxs-lookup"><span data-stu-id="cab93-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="cab93-110">Najpierw należy zaimportować konfiguracje elektronicznego raportowania płatności od odbiorcy oraz skonfigurować metodę płatności, firmę i informacje o odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="cab93-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="cab93-111">Księgowanie faktury niezależnej z danymi polecenia zapłaty</span><span class="sxs-lookup"><span data-stu-id="cab93-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="cab93-112">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Wszystkie faktury niezależne.</span><span class="sxs-lookup"><span data-stu-id="cab93-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="cab93-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cab93-113">Click New.</span></span>
3. <span data-ttu-id="cab93-114">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cab93-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="cab93-115">Na przykład zaznacz DE-010.</span><span class="sxs-lookup"><span data-stu-id="cab93-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="cab93-116">W polu Metoda płatności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cab93-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="cab93-117">Na przykład</span><span class="sxs-lookup"><span data-stu-id="cab93-117">For example.</span></span> <span data-ttu-id="cab93-118">wybierz opcję Elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="cab93-118">select Electronic.</span></span>  
5. <span data-ttu-id="cab93-119">W polu Identyfikator zgody na polecenie zapłaty wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cab93-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="cab93-120">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="cab93-120">Click Add line.</span></span>
7. <span data-ttu-id="cab93-121">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cab93-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="cab93-122">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="cab93-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="cab93-123">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="cab93-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="cab93-124">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="cab93-124">Click Post.</span></span>
11. <span data-ttu-id="cab93-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cab93-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="cab93-126">Tworzenie płatności</span><span class="sxs-lookup"><span data-stu-id="cab93-126">Create a payment</span></span>
1. <span data-ttu-id="cab93-127">Wybierz kolejno opcje Rozrachunki z odbiorcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="cab93-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="cab93-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cab93-128">Click New.</span></span>
3. <span data-ttu-id="cab93-129">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cab93-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="cab93-130">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="cab93-130">Click Lines.</span></span>
5. <span data-ttu-id="cab93-131">Kliknij opcję Propozycja płatności.</span><span class="sxs-lookup"><span data-stu-id="cab93-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="cab93-132">Kliknij opcję Utwórz propozycję płatności.</span><span class="sxs-lookup"><span data-stu-id="cab93-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="cab93-133">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="cab93-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="cab93-134">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="cab93-134">Click Filter.</span></span>
9. <span data-ttu-id="cab93-135">Na liście zaznacz wiersz w tabeli Transakcje odbiorcy oraz pole Metoda płatności.</span><span class="sxs-lookup"><span data-stu-id="cab93-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="cab93-136">Można zastosować dowolne kryteria w celu wybrania transakcji z odbiorcą, które mają zostać opłacone.</span><span class="sxs-lookup"><span data-stu-id="cab93-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="cab93-137">W tym przykładzie należy użyć opcji Elektroniczne jako metody płatności do wyfiltrowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="cab93-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="cab93-138">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cab93-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="cab93-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cab93-139">Click OK.</span></span>
12. <span data-ttu-id="cab93-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cab93-140">Click OK.</span></span>
13. <span data-ttu-id="cab93-141">Kliknij opcję Utwórz płatności.</span><span class="sxs-lookup"><span data-stu-id="cab93-141">Click Create payments.</span></span>

## <a name="generate-a-payment-file"></a><span data-ttu-id="cab93-142">Generowanie pliku płatności</span><span class="sxs-lookup"><span data-stu-id="cab93-142">Generate a payment file</span></span>

