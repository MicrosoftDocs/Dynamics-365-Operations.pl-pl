--- 
title: "Tworzenie pozwolenia na polecenie zapłaty dla odbiorcy"
description: "W tym przewodniku po zadaniach pokazano, jak utworzyć zgodę na polecenie zapłaty, a następnie używać go na fakturze."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9b74ec988712fc85c96ad3945149597186bee4f9
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="416e9-103">Tworzenie pozwolenia na polecenie zapłaty dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="416e9-103">Create a direct debit mandate for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="416e9-104">W tym przewodniku po zadaniach pokazano, jak utworzyć zgodę na polecenie zapłaty, a następnie używać go na fakturze.</span><span class="sxs-lookup"><span data-stu-id="416e9-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="416e9-105">Tworzenie konta bankowego</span><span class="sxs-lookup"><span data-stu-id="416e9-105">Create a bank account</span></span>
1. <span data-ttu-id="416e9-106">Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="416e9-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="416e9-107">Na przykład zaznacz US-001.</span><span class="sxs-lookup"><span data-stu-id="416e9-107">For example, select US-001</span></span>
3. <span data-ttu-id="416e9-108">W okienku akcji kliknij pozycję Odbiorca.</span><span class="sxs-lookup"><span data-stu-id="416e9-108">On the Action Pane, click Customer.</span></span>
4. <span data-ttu-id="416e9-109">Kliknij przycisk konta bankowe</span><span class="sxs-lookup"><span data-stu-id="416e9-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="416e9-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="416e9-110">Click New.</span></span>
6. <span data-ttu-id="416e9-111">W polu Konto bankowe wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-111">In the Bank account field, type a value.</span></span>
7. <span data-ttu-id="416e9-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-112">In the Name field, type a value.</span></span>
8. <span data-ttu-id="416e9-113">W polu IBAN wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-113">In the IBAN field, type a value.</span></span>
9. <span data-ttu-id="416e9-114">W polu Waluta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-114">In the Currency field, type a value.</span></span>
10. <span data-ttu-id="416e9-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="416e9-115">Click Save.</span></span>
11. <span data-ttu-id="416e9-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="416e9-116">Close the page.</span></span>
12. <span data-ttu-id="416e9-117">Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.</span><span class="sxs-lookup"><span data-stu-id="416e9-117">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
13. <span data-ttu-id="416e9-118">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="416e9-118">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="416e9-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="416e9-119">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="416e9-120">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="416e9-120">Click Edit.</span></span>
16. <span data-ttu-id="416e9-121">Rozwiń sekcję Dodatkowa identyfikacja.</span><span class="sxs-lookup"><span data-stu-id="416e9-121">Expand the Additional identification section.</span></span>
17. <span data-ttu-id="416e9-122">W polu Identyfikator polecenia zapłaty wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-122">In the Direct debit ID field, type a value.</span></span>
18. <span data-ttu-id="416e9-123">W polu IBAN wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-123">In the IBAN field, type a value.</span></span>
19. <span data-ttu-id="416e9-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="416e9-124">Close the page.</span></span>
20. <span data-ttu-id="416e9-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="416e9-125">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="416e9-126">Konfigurowanie elektronicznej metody płatności</span><span class="sxs-lookup"><span data-stu-id="416e9-126">Define the electronic payment method</span></span>
1. <span data-ttu-id="416e9-127">Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Metody płatności.</span><span class="sxs-lookup"><span data-stu-id="416e9-127">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="416e9-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="416e9-128">Click New.</span></span>
3. <span data-ttu-id="416e9-129">W polu Metoda płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-129">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="416e9-130">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="416e9-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="416e9-131">Typem płatności dla zgody na płacenie poleceniem zapłaty musi być płatność elektroniczna.</span><span class="sxs-lookup"><span data-stu-id="416e9-131">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="416e9-132">W polu Wymaga zgody wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="416e9-132">Select Yes in the Require mandate field.</span></span>
7. <span data-ttu-id="416e9-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="416e9-133">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="416e9-134">Dodawanie zgody na polecenie zapłaty do odbiorcy</span><span class="sxs-lookup"><span data-stu-id="416e9-134">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="416e9-135">Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="416e9-135">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="416e9-136">Na przykład zaznacz US-001.</span><span class="sxs-lookup"><span data-stu-id="416e9-136">For example, select US-001</span></span>
3. <span data-ttu-id="416e9-137">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="416e9-137">Click Edit.</span></span>
4. <span data-ttu-id="416e9-138">Rozwiń sekcję Ustawienia domyślne płatności.</span><span class="sxs-lookup"><span data-stu-id="416e9-138">Expand the Payment defaults section.</span></span>
5. <span data-ttu-id="416e9-139">W polu Metoda płatności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-139">In the Method of payment field, enter or select a value.</span></span>
6. <span data-ttu-id="416e9-140">Rozwiń sekcję Ustawienia domyślne płatności.</span><span class="sxs-lookup"><span data-stu-id="416e9-140">Expand the Payment defaults section.</span></span>
7. <span data-ttu-id="416e9-141">Rozwiń sekcję Pozwolenia na polecenie zapłaty.</span><span class="sxs-lookup"><span data-stu-id="416e9-141">Expand the Direct debit mandates section.</span></span>
8. <span data-ttu-id="416e9-142">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="416e9-142">Click Add.</span></span>
9. <span data-ttu-id="416e9-143">W polu Konto bankowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-143">In the Bank account field, enter or select a value.</span></span>
10. <span data-ttu-id="416e9-144">W polu Konto bankowe wierzyciela wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-144">In the Creditor bank account field, enter or select a value.</span></span>
11. <span data-ttu-id="416e9-145">Wprowadź liczbę płatności, jaką oczekujesz przetwarzać w ramach tej zgody.</span><span class="sxs-lookup"><span data-stu-id="416e9-145">Enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="416e9-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="416e9-146">Click OK.</span></span>
13. <span data-ttu-id="416e9-147">Kliknij przycisk Drukuj.</span><span class="sxs-lookup"><span data-stu-id="416e9-147">Click Print.</span></span>
14. <span data-ttu-id="416e9-148">Kliknij opcję Raport dotyczący zgody.</span><span class="sxs-lookup"><span data-stu-id="416e9-148">Click Mandate report.</span></span>
15. <span data-ttu-id="416e9-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="416e9-149">Close the page.</span></span>
16. <span data-ttu-id="416e9-150">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="416e9-150">Click Edit.</span></span>
17. <span data-ttu-id="416e9-151">W polu Data podpisania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="416e9-151">In the Signature date field, enter a date.</span></span>
18. <span data-ttu-id="416e9-152">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="416e9-152">Click Yes.</span></span>
19. <span data-ttu-id="416e9-153">Wpisz miejsce, w którym zgoda została podpisana.</span><span class="sxs-lookup"><span data-stu-id="416e9-153">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="416e9-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="416e9-154">Click OK.</span></span>
21. <span data-ttu-id="416e9-155">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="416e9-155">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="416e9-156">Tworzenie faktury niezależnej ze zgodą</span><span class="sxs-lookup"><span data-stu-id="416e9-156">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="416e9-157">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Wszystkie faktury niezależne.</span><span class="sxs-lookup"><span data-stu-id="416e9-157">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="416e9-158">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="416e9-158">Click New.</span></span>
3. <span data-ttu-id="416e9-159">Zaznacz odbiorcę, dla którego dodano zgodę.</span><span class="sxs-lookup"><span data-stu-id="416e9-159">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="416e9-160">W polu Identyfikator zgody na polecenie zapłaty wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="416e9-160">In the Direct debit mandate ID field, enter or select a value.</span></span>


