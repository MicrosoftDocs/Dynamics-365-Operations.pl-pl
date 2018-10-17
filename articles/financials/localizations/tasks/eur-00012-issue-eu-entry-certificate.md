--- 
title: "EUR-00012 Wystawianie świadectwa wywozowego UE"
description: "Ta procedura poprowadzi przez proces włączania obsługi świadectw wywozowych UE, konfigurowania konta odbiorcy do obsługi świadectw oraz wystawiania świadectw."
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 5a566b1d25064e3fccc8953dc883aa63bd16a301
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a><span data-ttu-id="3a9a1-103">EUR-00012 Wystawianie świadectwa wywozowego UE</span><span class="sxs-lookup"><span data-stu-id="3a9a1-103">EUR-00012 Issue an EU entry certificate</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3a9a1-104">Ta procedura poprowadzi przez proces włączania obsługi świadectw wywozowych UE, konfigurowania konta odbiorcy do obsługi świadectw oraz wystawiania świadectw.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-104">This procedure walks you through enabling an EU entry certificate, configuring a customer account to use entry certificates and issue a certificate.</span></span> <span data-ttu-id="3a9a1-105">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="enable-entry-certificate-management"></a><span data-ttu-id="3a9a1-106">Włącz zarządzanie świadectwami wywozowymi</span><span class="sxs-lookup"><span data-stu-id="3a9a1-106">Enable entry certificate management</span></span>
1. <span data-ttu-id="3a9a1-107">Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia > Parametry modułu rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-107">Go to Accounts receivable > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="3a9a1-108">Kliknij kartę Wysyłki.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-108">Click the Shipments tab.</span></span>
3. <span data-ttu-id="3a9a1-109">Rozwinięcie sekcję Świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-109">Expand the Entry certificate section.</span></span>
4. <span data-ttu-id="3a9a1-110">W polu Włącz zarządzanie świadectwami wywozowymi zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-110">Select Yes in the Enable entry certificate management field.</span></span>
5. <span data-ttu-id="3a9a1-111">W polu Włącz opcję wystawiania świadectwa wywozowego zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-111">Select Yes in the Enable entry certificate issuing field.</span></span>
6. <span data-ttu-id="3a9a1-112">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-112">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="3a9a1-113">Na liście znajdź i zaznacz wiersz Świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-113">In the list, find and select Entry certificate row.</span></span>
8. <span data-ttu-id="3a9a1-114">W polu Kod sekwencji numerów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-114">In the Number sequence code field, enter or select a value.</span></span>

## <a name="set-up-a-customer"></a><span data-ttu-id="3a9a1-115">Konfigurowanie odbiorcy</span><span class="sxs-lookup"><span data-stu-id="3a9a1-115">Set up a customer</span></span>
1. <span data-ttu-id="3a9a1-116">Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-116">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="3a9a1-117">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3a9a1-118">Na przykład wyfiltruj według pola Konto z wartością „DE-015”.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-118">For example, filter on the Account field with a value of 'DE-015'.</span></span>
3. <span data-ttu-id="3a9a1-119">Otwórz szczegóły konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-119">Open customer account details.</span></span>
4. <span data-ttu-id="3a9a1-120">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-120">Click Edit.</span></span>
5. <span data-ttu-id="3a9a1-121">Rozwiń sekcję Faktura i dostawa.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-121">Expand the Invoice and delivery section.</span></span>
6. <span data-ttu-id="3a9a1-122">W polu Wymagane jest świadectwo wywozowe zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-122">Select Yes in the Entry certificate required field.</span></span>
7. <span data-ttu-id="3a9a1-123">W polu Wystaw świadectwo wywozowe zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-123">Select Yes in the Issue entry certificate field.</span></span>
8. <span data-ttu-id="3a9a1-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-124">Click Save.</span></span>

## <a name="create-an-eu-entry-certificate-automatically"></a><span data-ttu-id="3a9a1-125">Automatyczne tworzenie świadectwa wywozowego UE</span><span class="sxs-lookup"><span data-stu-id="3a9a1-125">Create an EU entry certificate automatically</span></span>
1. <span data-ttu-id="3a9a1-126">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="3a9a1-127">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-127">Click New.</span></span>
3. <span data-ttu-id="3a9a1-128">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-128">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="3a9a1-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-129">Click OK.</span></span>
5. <span data-ttu-id="3a9a1-130">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-130">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="3a9a1-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-131">Click Save.</span></span>
7. <span data-ttu-id="3a9a1-132">W okienku akcji kliknij opcję Pobierz i zapakuj.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-132">On the Action Pane, click Pick and pack.</span></span>
8. <span data-ttu-id="3a9a1-133">Kliknij opcję Księguj dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-133">Click Post packing slip.</span></span>
9. <span data-ttu-id="3a9a1-134">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-134">Expand the Parameters section.</span></span>
10. <span data-ttu-id="3a9a1-135">W polu Ilość zaznacz opcję Wszystko.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-135">In the Quantity field, select 'All'.</span></span>
11. <span data-ttu-id="3a9a1-136">Wyczyść pole wyboru Wystaw świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-136">Clear the Issue entry certificate check box.</span></span>
    * <span data-ttu-id="3a9a1-137">Świadectwo wywozowe może zostać wystawione podczas księgowania dokumentu dostawy lub podczas fakturowania zamówienia.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-137">An entry certificate can be issued during packing slip posting or during order invoicing.</span></span> <span data-ttu-id="3a9a1-138">Aby wystawić je później, pozostaw niezaznaczone pole wyboru Wystaw świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-138">Leave the Issue entry certificate checkbox unchecked to issue it later.</span></span>  
12. <span data-ttu-id="3a9a1-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-139">Click OK.</span></span>
13. <span data-ttu-id="3a9a1-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-140">Click OK.</span></span>
14. <span data-ttu-id="3a9a1-141">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-141">On the Action Pane, click Invoice.</span></span>
15. <span data-ttu-id="3a9a1-142">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-142">Click Invoice.</span></span>
    * <span data-ttu-id="3a9a1-143">Sprawdź, czy w sekcji Przegląd są zaznaczone pola wyboru Wymagane jest świadectwo wywozowe i Wystaw świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-143">Verify that the Entry certificate required and Issue entry certificate checkboxes in the Overview section are marked.</span></span>  <span data-ttu-id="3a9a1-144">Można również zaznaczyć pole wyboru Drukuj świadectwo wywozowe, aby pozwolić na drukowanie certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-144">You can also select the Print entry certificate check box to allow printing of the certificate.</span></span>  
16. <span data-ttu-id="3a9a1-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-145">Click OK.</span></span>
17. <span data-ttu-id="3a9a1-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-146">Click OK.</span></span>
18. <span data-ttu-id="3a9a1-147">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-147">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="3a9a1-148">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-148">Click Invoice.</span></span>
20. <span data-ttu-id="3a9a1-149">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-149">On the Action Pane, click Invoice.</span></span>
21. <span data-ttu-id="3a9a1-150">Kliknij opcję Wyświetl wystawione świadectwa wywozowe.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-150">Click View issued entry certificates.</span></span>
22. <span data-ttu-id="3a9a1-151">Kliknij przycisk Drukuj.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-151">Click Print.</span></span>
23. <span data-ttu-id="3a9a1-152">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-152">Close the page.</span></span>
24. <span data-ttu-id="3a9a1-153">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-153">Click Change status.</span></span>
25. <span data-ttu-id="3a9a1-154">W polu Nowy stan wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-154">In the New status field, select an option.</span></span>
26. <span data-ttu-id="3a9a1-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-155">Click OK.</span></span>
27. <span data-ttu-id="3a9a1-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-156">Close the page.</span></span>

## <a name="create-an-eu-entry-certificate-manually"></a><span data-ttu-id="3a9a1-157">Ręczne tworzenie świadectwa wywozowego UE</span><span class="sxs-lookup"><span data-stu-id="3a9a1-157">Create an EU entry certificate manually</span></span>
1. <span data-ttu-id="3a9a1-158">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-158">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="3a9a1-159">Kliknij opcję Utwórz świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-159">Click Create entry certificate.</span></span>
3. <span data-ttu-id="3a9a1-160">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-160">Click OK.</span></span>
4. <span data-ttu-id="3a9a1-161">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-161">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="3a9a1-162">Kliknij opcję Wyświetl wystawione świadectwa wywozowe.</span><span class="sxs-lookup"><span data-stu-id="3a9a1-162">Click View issued entry certificates.</span></span>


