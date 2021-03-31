---
title: EUR-00012 Wystawianie świadectwa wywozowego UE
description: Ta procedura poprowadzi przez proces włączania obsługi świadectw wywozowych UE, konfigurowania konta odbiorcy do obsługi świadectw oraz wystawiania świadectw.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95c1f3f87175a2c2a2887a4ed2ebde1bd7d1c0b9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227970"
---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a><span data-ttu-id="95923-103">EUR-00012 Wystawianie świadectwa wywozowego UE</span><span class="sxs-lookup"><span data-stu-id="95923-103">EUR-00012 Issue an EU entry certificate</span></span>

[!include [banner](../../includes/banner.md)]
<span data-ttu-id="95923-104">Ta procedura poprowadzi przez proces włączania obsługi świadectw wywozowych UE, konfigurowania konta odbiorcy do obsługi świadectw oraz wystawiania świadectw.</span><span class="sxs-lookup"><span data-stu-id="95923-104">This procedure walks you through enabling an EU entry certificate, configuring a customer account to use entry certificates and issue a certificate.</span></span> <span data-ttu-id="95923-105">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="95923-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="enable-entry-certificate-management"></a><span data-ttu-id="95923-106">Włącz zarządzanie świadectwami wywozowymi</span><span class="sxs-lookup"><span data-stu-id="95923-106">Enable entry certificate management</span></span>
1. <span data-ttu-id="95923-107">Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia > Parametry modułu rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="95923-107">Go to Accounts receivable > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="95923-108">Kliknij kartę Wysyłki.</span><span class="sxs-lookup"><span data-stu-id="95923-108">Click the Shipments tab.</span></span>
3. <span data-ttu-id="95923-109">Rozwinięcie sekcję Świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="95923-109">Expand the Entry certificate section.</span></span>
4. <span data-ttu-id="95923-110">W polu Włącz zarządzanie świadectwami wywozowymi zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="95923-110">Select Yes in the Enable entry certificate management field.</span></span>
5. <span data-ttu-id="95923-111">W polu Włącz opcję wystawiania świadectwa wywozowego zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="95923-111">Select Yes in the Enable entry certificate issuing field.</span></span>
6. <span data-ttu-id="95923-112">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="95923-112">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="95923-113">Na liście znajdź i zaznacz wiersz Świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="95923-113">In the list, find and select Entry certificate row.</span></span>
8. <span data-ttu-id="95923-114">W polu Kod sekwencji numerów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="95923-114">In the Number sequence code field, enter or select a value.</span></span>

## <a name="set-up-a-customer"></a><span data-ttu-id="95923-115">Konfigurowanie odbiorcy</span><span class="sxs-lookup"><span data-stu-id="95923-115">Set up a customer</span></span>
1. <span data-ttu-id="95923-116">Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="95923-116">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="95923-117">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="95923-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="95923-118">Na przykład wyfiltruj według pola Konto z wartością „DE-015”.</span><span class="sxs-lookup"><span data-stu-id="95923-118">For example, filter on the Account field with a value of 'DE-015'.</span></span>
3. <span data-ttu-id="95923-119">Otwórz szczegóły konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="95923-119">Open customer account details.</span></span>
4. <span data-ttu-id="95923-120">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="95923-120">Click Edit.</span></span>
5. <span data-ttu-id="95923-121">Rozwiń sekcję Faktura i dostawa.</span><span class="sxs-lookup"><span data-stu-id="95923-121">Expand the Invoice and delivery section.</span></span>
6. <span data-ttu-id="95923-122">W polu Wymagane jest świadectwo wywozowe zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="95923-122">Select Yes in the Entry certificate required field.</span></span>
7. <span data-ttu-id="95923-123">W polu Wystaw świadectwo wywozowe zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="95923-123">Select Yes in the Issue entry certificate field.</span></span>
8. <span data-ttu-id="95923-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="95923-124">Click Save.</span></span>

## <a name="create-an-eu-entry-certificate-automatically"></a><span data-ttu-id="95923-125">Automatyczne tworzenie świadectwa wywozowego UE</span><span class="sxs-lookup"><span data-stu-id="95923-125">Create an EU entry certificate automatically</span></span>
1. <span data-ttu-id="95923-126">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="95923-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="95923-127">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="95923-127">Click New.</span></span>
3. <span data-ttu-id="95923-128">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="95923-128">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="95923-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="95923-129">Click OK.</span></span>
5. <span data-ttu-id="95923-130">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="95923-130">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="95923-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="95923-131">Click Save.</span></span>
7. <span data-ttu-id="95923-132">W okienku akcji kliknij opcję Pobierz i zapakuj.</span><span class="sxs-lookup"><span data-stu-id="95923-132">On the Action Pane, click Pick and pack.</span></span>
8. <span data-ttu-id="95923-133">Kliknij opcję Księguj dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="95923-133">Click Post packing slip.</span></span>
9. <span data-ttu-id="95923-134">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="95923-134">Expand the Parameters section.</span></span>
10. <span data-ttu-id="95923-135">W polu Ilość zaznacz opcję Wszystko.</span><span class="sxs-lookup"><span data-stu-id="95923-135">In the Quantity field, select 'All'.</span></span>
11. <span data-ttu-id="95923-136">Wyczyść pole wyboru Wystaw świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="95923-136">Clear the Issue entry certificate check box.</span></span>
    * <span data-ttu-id="95923-137">Świadectwo wywozowe może zostać wystawione podczas księgowania dokumentu dostawy lub podczas fakturowania zamówienia.</span><span class="sxs-lookup"><span data-stu-id="95923-137">An entry certificate can be issued during packing slip posting or during order invoicing.</span></span> <span data-ttu-id="95923-138">Aby wystawić je później, pozostaw niezaznaczone pole wyboru Wystaw świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="95923-138">Leave the Issue entry certificate checkbox unchecked to issue it later.</span></span>  
12. <span data-ttu-id="95923-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="95923-139">Click OK.</span></span>
13. <span data-ttu-id="95923-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="95923-140">Click OK.</span></span>
14. <span data-ttu-id="95923-141">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="95923-141">On the Action Pane, click Invoice.</span></span>
15. <span data-ttu-id="95923-142">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="95923-142">Click Invoice.</span></span>
    * <span data-ttu-id="95923-143">Sprawdź, czy w sekcji Przegląd są zaznaczone pola wyboru Wymagane jest świadectwo wywozowe i Wystaw świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="95923-143">Verify that the Entry certificate required and Issue entry certificate checkboxes in the Overview section are marked.</span></span>  <span data-ttu-id="95923-144">Można również zaznaczyć pole wyboru Drukuj świadectwo wywozowe, aby pozwolić na drukowanie certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="95923-144">You can also select the Print entry certificate check box to allow printing of the certificate.</span></span>  
16. <span data-ttu-id="95923-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="95923-145">Click OK.</span></span>
17. <span data-ttu-id="95923-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="95923-146">Click OK.</span></span>
18. <span data-ttu-id="95923-147">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="95923-147">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="95923-148">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="95923-148">Click Invoice.</span></span>
20. <span data-ttu-id="95923-149">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="95923-149">On the Action Pane, click Invoice.</span></span>
21. <span data-ttu-id="95923-150">Kliknij opcję Wyświetl wystawione świadectwa wywozowe.</span><span class="sxs-lookup"><span data-stu-id="95923-150">Click View issued entry certificates.</span></span>
22. <span data-ttu-id="95923-151">Kliknij przycisk Drukuj.</span><span class="sxs-lookup"><span data-stu-id="95923-151">Click Print.</span></span>
23. <span data-ttu-id="95923-152">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="95923-152">Close the page.</span></span>
24. <span data-ttu-id="95923-153">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="95923-153">Click Change status.</span></span>
25. <span data-ttu-id="95923-154">W polu Nowy stan wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="95923-154">In the New status field, select an option.</span></span>
26. <span data-ttu-id="95923-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="95923-155">Click OK.</span></span>
27. <span data-ttu-id="95923-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="95923-156">Close the page.</span></span>

## <a name="create-an-eu-entry-certificate-manually"></a><span data-ttu-id="95923-157">Ręczne tworzenie świadectwa wywozowego UE</span><span class="sxs-lookup"><span data-stu-id="95923-157">Create an EU entry certificate manually</span></span>
1. <span data-ttu-id="95923-158">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="95923-158">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="95923-159">Kliknij opcję Utwórz świadectwo wywozowe.</span><span class="sxs-lookup"><span data-stu-id="95923-159">Click Create entry certificate.</span></span>
3. <span data-ttu-id="95923-160">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="95923-160">Click OK.</span></span>
4. <span data-ttu-id="95923-161">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="95923-161">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="95923-162">Kliknij opcję Wyświetl wystawione świadectwa wywozowe.</span><span class="sxs-lookup"><span data-stu-id="95923-162">Click View issued entry certificates.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]