--- 
title: EEU 00047 Zaliczka dla pracownika
description: "Ta procedura pokazuje, jak skonfigurować i zarejestrować transakcje dla posiadacza zaliczki."
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RCashTable, LedgerJournalSetup, HcmWorkerGroup_RU, EmplPosting_RU, VendParameters, RCashPosting, BankParameters, PaymTerm, HcmWorker, HcmWorkerNewWorker, HcmWorkerAdvHolderTableListPage_RU, HcmWorkerAdvHolderTable_RU, PurchTable, PurchCreateOrder, HcmAdvHolderLookup_RU, InventItemIdLookupPurchase, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, EmplTrans_RU, EmplBalance_RU
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e3c07789bfa0839436caf32e428f3abeecb8f2b7
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="eeu-00047-advance-payment-to-employee"></a><span data-ttu-id="519c7-103">EEU 00047 Zaliczka dla pracownika</span><span class="sxs-lookup"><span data-stu-id="519c7-103">EEU-00047 Advance payment to employee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="519c7-104">Ta procedura pokazuje, jak skonfigurować i zarejestrować transakcje dla posiadacza zaliczki.</span><span class="sxs-lookup"><span data-stu-id="519c7-104">This procedure demonstrates how to set up and register transactions for an advance holder.</span></span> <span data-ttu-id="519c7-105">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się na Litwie.</span><span class="sxs-lookup"><span data-stu-id="519c7-105">This procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="519c7-106">To zadanie działa tylko dla firm, których adres podstawowy znajduje się w Polsce, na Litwie, na Łotwie, w Estonii, w Czechach lub na Węgrzech.</span><span class="sxs-lookup"><span data-stu-id="519c7-106">This task only works for legal entities with a primary address in Poland, Lithuania, Latvia, Estonia, Czech Republic, or Hungary.</span></span> <span data-ttu-id="519c7-107">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="519c7-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-new-cash-account"></a><span data-ttu-id="519c7-108">Tworzenie nowego konta kasowego</span><span class="sxs-lookup"><span data-stu-id="519c7-108">Create a new cash account</span></span>
1. <span data-ttu-id="519c7-109">Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta kasowe.</span><span class="sxs-lookup"><span data-stu-id="519c7-109">Go to Cash and bank management > Bank accounts > Cash accounts.</span></span>
2. <span data-ttu-id="519c7-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="519c7-110">Click New.</span></span>
3. <span data-ttu-id="519c7-111">W polu Kasa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-111">In the Cash field, type a value.</span></span>
4. <span data-ttu-id="519c7-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="519c7-113">W polu Grupa sekwencji numerów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-113">In the Number sequence group field, enter or select a value.</span></span>
6. <span data-ttu-id="519c7-114">Rozwiń sekcję Weryfikacja.</span><span class="sxs-lookup"><span data-stu-id="519c7-114">Expand the Validation section.</span></span>
7. <span data-ttu-id="519c7-115">W polu Waluta wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-115">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="519c7-116">W polu Ujemne saldo kasowe wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="519c7-116">Select Yes in the Negative cash field.</span></span>
9. <span data-ttu-id="519c7-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-117">Click Save.</span></span>

## <a name="create-a-new-journal"></a><span data-ttu-id="519c7-118">Tworzenie nowego arkusza</span><span class="sxs-lookup"><span data-stu-id="519c7-118">Create a new journal</span></span>
1. <span data-ttu-id="519c7-119">Wybierz kolejno opcje Księga główna > Konfiguracja arkusza > Nazwy arkuszy.</span><span class="sxs-lookup"><span data-stu-id="519c7-119">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="519c7-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="519c7-120">Click New.</span></span>
3. <span data-ttu-id="519c7-121">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-121">In the Name field, type a value.</span></span>
4. <span data-ttu-id="519c7-122">W polu Seria załączników wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-122">In the Voucher series field, enter or select a value.</span></span>
5. <span data-ttu-id="519c7-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-123">Click Save.</span></span>
6. <span data-ttu-id="519c7-124">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="519c7-124">Click New.</span></span>
7. <span data-ttu-id="519c7-125">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-125">In the Name field, type a value.</span></span>
8. <span data-ttu-id="519c7-126">W polu Typ arkusza wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="519c7-126">In the Journal type field, select an option.</span></span>
9. <span data-ttu-id="519c7-127">W polu Seria załączników wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-127">In the Voucher series field, enter or select a value.</span></span>
10. <span data-ttu-id="519c7-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-128">Click Save.</span></span>

## <a name="create-an-advance-holder-group"></a><span data-ttu-id="519c7-129">Tworzenie grupy posiadaczy zaliczek</span><span class="sxs-lookup"><span data-stu-id="519c7-129">Create an advance holder group</span></span>
1. <span data-ttu-id="519c7-130">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia > Posiadacze zaliczek > Grupy posiadaczy zaliczek.</span><span class="sxs-lookup"><span data-stu-id="519c7-130">Go to Accounts payable > Setup > Advance holders > Advance holder groups.</span></span>
2. <span data-ttu-id="519c7-131">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="519c7-131">Click New.</span></span>
3. <span data-ttu-id="519c7-132">W polu Grupa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-132">In the Group field, type a value.</span></span>
4. <span data-ttu-id="519c7-133">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="519c7-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="519c7-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-134">Click Save.</span></span>

## <a name="create-an-employee-posting-profile"></a><span data-ttu-id="519c7-135">Tworzenie profilu księgowania pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="519c7-135">Create an employee posting profile</span></span>
1. <span data-ttu-id="519c7-136">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia > Posiadacze zaliczek > Profile księgowania pracowników.</span><span class="sxs-lookup"><span data-stu-id="519c7-136">Go to Accounts payable > Setup > Advance holders > Employee posting profiles.</span></span>
2. <span data-ttu-id="519c7-137">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="519c7-137">Click New.</span></span>
3. <span data-ttu-id="519c7-138">W polu Profil księgowania wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-138">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="519c7-139">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="519c7-139">In the Description field, type a value.</span></span>
5. <span data-ttu-id="519c7-140">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="519c7-140">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="519c7-141">W polu Ważny dla wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="519c7-141">In the Valid for field, select an option.</span></span>
7. <span data-ttu-id="519c7-142">W polu Konto rozrachunkowe podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="519c7-142">In the Summary account field, specify the desired values.</span></span>
8. <span data-ttu-id="519c7-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-143">Click Save.</span></span>

## <a name="set-up-advance-holder-parameters"></a><span data-ttu-id="519c7-144">Konfigurowanie parametrów posiadaczy zaliczek</span><span class="sxs-lookup"><span data-stu-id="519c7-144">Set up advance holder parameters</span></span>
1. <span data-ttu-id="519c7-145">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="519c7-145">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="519c7-146">Kliknij kartę Posiadacze zaliczek.</span><span class="sxs-lookup"><span data-stu-id="519c7-146">Click the Advance holders tab.</span></span>
3. <span data-ttu-id="519c7-147">W polu Profil księgowania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-147">In the Posting profile field, enter or select a value.</span></span>
4. <span data-ttu-id="519c7-148">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-148">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="519c7-149">Wprowadź lub wybierz wartość w polu Kasa.</span><span class="sxs-lookup"><span data-stu-id="519c7-149">In the Cash field, enter or select a value.</span></span>
6. <span data-ttu-id="519c7-150">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-150">In the Name field, enter or select a value.</span></span>
7. <span data-ttu-id="519c7-151">W polu Typ konta zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="519c7-151">In the Account type field, select an option.</span></span>
8. <span data-ttu-id="519c7-152">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="519c7-152">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="519c7-153">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="519c7-153">Click the Number sequences tab.</span></span>
10. <span data-ttu-id="519c7-154">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-154">Click Save.</span></span>

## <a name="set-up-a-cash-posting-profile"></a><span data-ttu-id="519c7-155">Konfigurowanie profilu księgowania kasy</span><span class="sxs-lookup"><span data-stu-id="519c7-155">Set up a cash posting profile</span></span>
1. <span data-ttu-id="519c7-156">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Profile księgowania kasy.</span><span class="sxs-lookup"><span data-stu-id="519c7-156">Go to Cash and bank management > Setup > Cash posting profiles.</span></span>
2. <span data-ttu-id="519c7-157">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="519c7-157">Click New.</span></span>
3. <span data-ttu-id="519c7-158">W polu Księgowanie kasy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-158">In the Cash posting field, type a value.</span></span>
4. <span data-ttu-id="519c7-159">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="519c7-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="519c7-160">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="519c7-160">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="519c7-161">W polu Ważny dla wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="519c7-161">In the Valid for field, select an option.</span></span>
7. <span data-ttu-id="519c7-162">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="519c7-162">In the Main account field, specify the desired values.</span></span>
8. <span data-ttu-id="519c7-163">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-163">Click Save.</span></span>

## <a name="set-up-cash-and-bank-parameters"></a><span data-ttu-id="519c7-164">Konfigurowanie parametrów kasy i banku</span><span class="sxs-lookup"><span data-stu-id="519c7-164">Set up cash and bank parameters</span></span>
1. <span data-ttu-id="519c7-165">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="519c7-165">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="519c7-166">Kliknij kartę Kasa.</span><span class="sxs-lookup"><span data-stu-id="519c7-166">Click the Cash tab.</span></span>
3. <span data-ttu-id="519c7-167">Wprowadź lub wybierz wartość w polu Kasa.</span><span class="sxs-lookup"><span data-stu-id="519c7-167">In the Cash field, enter or select a value.</span></span>
4. <span data-ttu-id="519c7-168">Wprowadź lub wybierz wartość w polu Księgowanie kasy.</span><span class="sxs-lookup"><span data-stu-id="519c7-168">In the Cash posting field, enter or select a value.</span></span>
5. <span data-ttu-id="519c7-169">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-169">Click Save.</span></span>
6. <span data-ttu-id="519c7-170">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="519c7-170">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="519c7-171">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="519c7-171">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="519c7-172">W polu Kod sekwencji numerów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-172">In the Number sequence code field, enter or select a value.</span></span>
9. <span data-ttu-id="519c7-173">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="519c7-173">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="519c7-174">W polu Kod sekwencji numerów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-174">In the Number sequence code field, enter or select a value.</span></span>
11. <span data-ttu-id="519c7-175">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-175">Click Save.</span></span>

## <a name="set-up-terms-of-payment"></a><span data-ttu-id="519c7-176">Ustaw warunki płatności</span><span class="sxs-lookup"><span data-stu-id="519c7-176">Set up terms of payment</span></span>
1. <span data-ttu-id="519c7-177">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Warunki płatności.</span><span class="sxs-lookup"><span data-stu-id="519c7-177">Go to Accounts payable > Payment setup > Terms of payment.</span></span>
2. <span data-ttu-id="519c7-178">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="519c7-178">Click Edit.</span></span>
3. <span data-ttu-id="519c7-179">W polu Od posiadacza zaliczki wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="519c7-179">Select Yes in the From advance holder field.</span></span>
4. <span data-ttu-id="519c7-180">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-180">Click Save.</span></span>

## <a name="create-a-new-worker"></a><span data-ttu-id="519c7-181">Tworzenie nowego pracownika</span><span class="sxs-lookup"><span data-stu-id="519c7-181">Create a new worker</span></span>
1. <span data-ttu-id="519c7-182">Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Pracownicy.</span><span class="sxs-lookup"><span data-stu-id="519c7-182">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="519c7-183">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="519c7-183">Click New.</span></span>
3. <span data-ttu-id="519c7-184">W polu Imię wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-184">In the First name field, type a value.</span></span>
4. <span data-ttu-id="519c7-185">W polu Nazwisko wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-185">In the Last name field, type a value.</span></span>
5. <span data-ttu-id="519c7-186">W polu Identyfikator pracownika wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-186">In the Worker ID field, type a value.</span></span>
6. <span data-ttu-id="519c7-187">Kliknij przycisk Zatrudnij nowego pracownika.</span><span class="sxs-lookup"><span data-stu-id="519c7-187">Click Hire new worker.</span></span>
7. <span data-ttu-id="519c7-188">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-188">Click Save.</span></span>

## <a name="set-up-a-worker-as-an-advance-holder"></a><span data-ttu-id="519c7-189">Konfigurowanie pracownika jako posiadacza zaliczki</span><span class="sxs-lookup"><span data-stu-id="519c7-189">Set up a worker as an advance holder</span></span>
1. <span data-ttu-id="519c7-190">Wybierz kolejno opcje Rozrachunki z dostawcami > Posiadacze zaliczek > Posiadacze zaliczek.</span><span class="sxs-lookup"><span data-stu-id="519c7-190">Go to Accounts payable > Advance holders > Advance holders.</span></span>
2. <span data-ttu-id="519c7-191">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="519c7-191">Click Edit.</span></span>
3. <span data-ttu-id="519c7-192">W polu Grupa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-192">In the Group field, enter or select a value.</span></span>
4. <span data-ttu-id="519c7-193">W polu Posiadacz zaliczki wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="519c7-193">Select Yes in the Advance holder field.</span></span>
5. <span data-ttu-id="519c7-194">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-194">Click Save.</span></span>

## <a name="create-and-post-a-purchase-order-invoice"></a><span data-ttu-id="519c7-195">Tworzenie i księgowanie faktury zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="519c7-195">Create and post a purchase order invoice</span></span>
1. <span data-ttu-id="519c7-196">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="519c7-196">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="519c7-197">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="519c7-197">Click New.</span></span>
3. <span data-ttu-id="519c7-198">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-198">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="519c7-199">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="519c7-199">Click OK.</span></span>
5. <span data-ttu-id="519c7-200">W polu Wiersze lub nagłówek wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="519c7-200">In the Lines or header field, select an option.</span></span>
6. <span data-ttu-id="519c7-201">Rozwiń sekcję Cena i rabat.</span><span class="sxs-lookup"><span data-stu-id="519c7-201">Expand the Price and discount section.</span></span>
7. <span data-ttu-id="519c7-202">W polu Warunki płatności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-202">In the Terms of payment field, enter or select a value.</span></span>
8. <span data-ttu-id="519c7-203">Wprowadź lub wybierz wartość w polu Posiadacz zaliczki.</span><span class="sxs-lookup"><span data-stu-id="519c7-203">In the Advance holder field, enter or select a value.</span></span>
9. <span data-ttu-id="519c7-204">W polu Wiersze lub nagłówek wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="519c7-204">In the Lines or header field, select an option.</span></span>
10. <span data-ttu-id="519c7-205">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="519c7-205">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="519c7-206">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-206">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="519c7-207">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="519c7-207">In the Quantity field, enter a number.</span></span>
13. <span data-ttu-id="519c7-208">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="519c7-208">In the Unit price field, enter a number.</span></span>
14. <span data-ttu-id="519c7-209">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="519c7-209">Click Save.</span></span>
15. <span data-ttu-id="519c7-210">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="519c7-210">On the Action Pane, click Purchase.</span></span>
16. <span data-ttu-id="519c7-211">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="519c7-211">Click Confirm.</span></span>
17. <span data-ttu-id="519c7-212">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="519c7-212">On the Action Pane, click Invoice.</span></span>
18. <span data-ttu-id="519c7-213">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="519c7-213">Click Invoice.</span></span>
19. <span data-ttu-id="519c7-214">Na liście Domyślnie z zaznacz opcję Ilość z dokumentu przyjęcia produktów, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="519c7-214">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
20. <span data-ttu-id="519c7-215">W polu Domyślna ilość dla wierszy zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="519c7-215">In the Default quantity for lines field, select an option.</span></span>
21. <span data-ttu-id="519c7-216">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="519c7-216">Click OK.</span></span>
22. <span data-ttu-id="519c7-217">W polu Numer wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="519c7-217">In the Number field, type a value.</span></span>
23. <span data-ttu-id="519c7-218">Wypełnij pole Opis faktury.</span><span class="sxs-lookup"><span data-stu-id="519c7-218">In the Invoice description field, type a value.</span></span>
24. <span data-ttu-id="519c7-219">W polu Data faktury wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="519c7-219">In the Invoice date field, enter a date.</span></span>
25. <span data-ttu-id="519c7-220">W polu Data rejestru VAT wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="519c7-220">In the Date of VAT register field, enter a date.</span></span>
26. <span data-ttu-id="519c7-221">W polu Data otrzymania dokumentu wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="519c7-221">In the Receive document date field, enter a date.</span></span>
27. <span data-ttu-id="519c7-222">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="519c7-222">Click Post.</span></span>

## <a name="balance-and-close-advance-holders-transactions"></a><span data-ttu-id="519c7-223">Bilansowanie i zamykanie transakcji posiadaczy zaliczek</span><span class="sxs-lookup"><span data-stu-id="519c7-223">Balance and close advance holders transactions</span></span>
1. <span data-ttu-id="519c7-224">Wybierz kolejno opcje Rozrachunki z dostawcami > Posiadacze zaliczek > Posiadacze zaliczek.</span><span class="sxs-lookup"><span data-stu-id="519c7-224">Go to Accounts payable > Advance holders > Advance holders.</span></span>
2. <span data-ttu-id="519c7-225">Kliknij opcję Transakcje.</span><span class="sxs-lookup"><span data-stu-id="519c7-225">Click Transactions.</span></span>
3. <span data-ttu-id="519c7-226">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="519c7-226">Close the page.</span></span>
4. <span data-ttu-id="519c7-227">Kliknij opcję Saldo.</span><span class="sxs-lookup"><span data-stu-id="519c7-227">Click Balance.</span></span>
5. <span data-ttu-id="519c7-228">Kliknij opcję Zamknij — bank.</span><span class="sxs-lookup"><span data-stu-id="519c7-228">Click Close via bank.</span></span>
6. <span data-ttu-id="519c7-229">W polu Automatycznie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="519c7-229">Select Yes in the Automatic field.</span></span>
7. <span data-ttu-id="519c7-230">W polu Kwota do przeniesienia</span><span class="sxs-lookup"><span data-stu-id="519c7-230">In the Amount to be transferred.</span></span> <span data-ttu-id="519c7-231">wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="519c7-231">field, enter a number.</span></span>
8. <span data-ttu-id="519c7-232">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="519c7-232">Click OK.</span></span>
9. <span data-ttu-id="519c7-233">Kliknij opcję Zamknij — kasa.</span><span class="sxs-lookup"><span data-stu-id="519c7-233">Click Close via cash.</span></span>
10. <span data-ttu-id="519c7-234">W polu Automatycznie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="519c7-234">Select Yes in the Automatic field.</span></span>
11. <span data-ttu-id="519c7-235">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="519c7-235">Click OK.</span></span>
12. <span data-ttu-id="519c7-236">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="519c7-236">Close the page.</span></span>
13. <span data-ttu-id="519c7-237">Kliknij opcję Transakcje.</span><span class="sxs-lookup"><span data-stu-id="519c7-237">Click Transactions.</span></span>


