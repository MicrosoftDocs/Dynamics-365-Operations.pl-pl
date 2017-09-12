--- 
title: "Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą faktury od dostawcy"
description: "Ten przewodnik zadania pomoże utworzyć fakturę od dostawcy na podstawie zamówienia zakupu oraz wyświetlić wyniki uzgadniania zamówienia zakupu, przyjęcia i faktury (uzgadnianie trzyelementowe)."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 48535a283cbdfdc7343a20105b139c527cac85f4
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-a-vendor-invoice"></a><span data-ttu-id="4fce8-103">Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="4fce8-103">Key invoice data into accounts payable using a vendor invoice</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4fce8-104">Ten przewodnik zadania pomoże utworzyć fakturę od dostawcy na podstawie zamówienia zakupu oraz wyświetlić wyniki uzgadniania zamówienia zakupu, przyjęcia i faktury (uzgadnianie trzyelementowe).</span><span class="sxs-lookup"><span data-stu-id="4fce8-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="4fce8-105">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="4fce8-105">Create a purchase order</span></span>
1. <span data-ttu-id="4fce8-106">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="4fce8-106">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="4fce8-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4fce8-107">Click New.</span></span>
3. <span data-ttu-id="4fce8-108">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="4fce8-108">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="4fce8-109">Znajdź dostawcę do wybrania.</span><span class="sxs-lookup"><span data-stu-id="4fce8-109">Find a vendor to select.</span></span> <span data-ttu-id="4fce8-110">Na przykład przewiń w dół do dostawcy US-104.</span><span class="sxs-lookup"><span data-stu-id="4fce8-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="4fce8-111">Wybierz dostawcę US-104.</span><span class="sxs-lookup"><span data-stu-id="4fce8-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="4fce8-112">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4fce8-112">Click OK.</span></span>
7. <span data-ttu-id="4fce8-113">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="4fce8-113">In the Item number field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="4fce8-114">Wybierz pozycję magazynową.</span><span class="sxs-lookup"><span data-stu-id="4fce8-114">Select an inventory item.</span></span> <span data-ttu-id="4fce8-115">Na przykład zaznacz numer towaru 1000.</span><span class="sxs-lookup"><span data-stu-id="4fce8-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="4fce8-116">Rozwiń lub zwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="4fce8-116">Expand or collapse the Line details section.</span></span>
10. <span data-ttu-id="4fce8-117">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="4fce8-117">Click the Setup tab.</span></span>
    * <span data-ttu-id="4fce8-118">Można ręcznie zastąpić zasady uzgadniania i określić nieużywanie uzgadniania, używanie uzgadniania dwuelementowego lub używanie uzgadniania trzyelementowego.</span><span class="sxs-lookup"><span data-stu-id="4fce8-118">You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="4fce8-119">Rozwiń lub zwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="4fce8-119">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="4fce8-120">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="4fce8-120">On the Action Pane, click Purchase.</span></span>
13. <span data-ttu-id="4fce8-121">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="4fce8-121">Click Confirm.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="4fce8-122">Odbieranie produktów</span><span class="sxs-lookup"><span data-stu-id="4fce8-122">Receive the products</span></span>
1. <span data-ttu-id="4fce8-123">W okienku akcji kliknij pozycję Odbierz.</span><span class="sxs-lookup"><span data-stu-id="4fce8-123">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="4fce8-124">Kliknij opcję Dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="4fce8-124">Click Product receipt.</span></span>
3. <span data-ttu-id="4fce8-125">W polu Dokument przyjęcia produktów wprowadź numer dokumentu przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="4fce8-125">In the Product receipt field, enter the product receipt number.</span></span> <span data-ttu-id="4fce8-126">Na przykład wpisz PR123.</span><span class="sxs-lookup"><span data-stu-id="4fce8-126">For example, enter PR123.</span></span>
4. <span data-ttu-id="4fce8-127">Kliknij przycisk OK, aby zaksięgować dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="4fce8-127">Click OK to post the product receipt.</span></span>
5. <span data-ttu-id="4fce8-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4fce8-128">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="4fce8-129">Tworzenie faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="4fce8-129">Create a vendor invoice</span></span>
1. <span data-ttu-id="4fce8-130">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Niezafakturowane zamówienia zakupu o stanie Otrzymano.</span><span class="sxs-lookup"><span data-stu-id="4fce8-130">Go to Accounts payable > Purchase orders > Purchase orders received but not invoiced.</span></span>
2. <span data-ttu-id="4fce8-131">Zaznacz utworzone przez siebie zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="4fce8-131">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="4fce8-132">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="4fce8-132">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="4fce8-133">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="4fce8-133">Click Invoice.</span></span>
5. <span data-ttu-id="4fce8-134">W polu Numer wprowadź numer faktury.</span><span class="sxs-lookup"><span data-stu-id="4fce8-134">In the Number field, enter the invoice number.</span></span>
6. <span data-ttu-id="4fce8-135">Wypełnij pole Opis faktury.</span><span class="sxs-lookup"><span data-stu-id="4fce8-135">In the Invoice description field, type a value.</span></span>
7. <span data-ttu-id="4fce8-136">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="4fce8-136">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="4fce8-137">W polu Cena jednostkowa wpisz 1200.</span><span class="sxs-lookup"><span data-stu-id="4fce8-137">In the Unit price field, enter 1200.</span></span>
9. <span data-ttu-id="4fce8-138">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="4fce8-138">Click Add line.</span></span>
10. <span data-ttu-id="4fce8-139">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="4fce8-139">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="4fce8-140">Na liście znajdź numer towaru opłaty instalacyjnej.</span><span class="sxs-lookup"><span data-stu-id="4fce8-140">In the list, find the installation charge item number.</span></span> <span data-ttu-id="4fce8-141">Na przykład S0001.</span><span class="sxs-lookup"><span data-stu-id="4fce8-141">For example, S0001</span></span>
12. <span data-ttu-id="4fce8-142">Zaznacz numer towaru opłaty instalacyjnej.</span><span class="sxs-lookup"><span data-stu-id="4fce8-142">Select the installation charge item number.</span></span>
    * <span data-ttu-id="4fce8-143">Zwróć uwagę, że po wprowadzeniu zmian nie wykonano uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="4fce8-143">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="4fce8-144">Kliknij przycisk Aktualizuj stan uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="4fce8-144">Click Update match status.</span></span>
14. <span data-ttu-id="4fce8-145">W okienku akcji kliknij pozycję Przegląd.</span><span class="sxs-lookup"><span data-stu-id="4fce8-145">On the Action Pane, click Review.</span></span>
15. <span data-ttu-id="4fce8-146">Kliknij przycisk Szczegóły uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="4fce8-146">Click Matching details.</span></span>
    * <span data-ttu-id="4fce8-147">Nowy wiersz z usługami nie musi być uzgadniany, dlatego pozostaje stan „Nie wykonano”.</span><span class="sxs-lookup"><span data-stu-id="4fce8-147">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="4fce8-148">Zaznacz dokument przyjęcia produktów dla otrzymanej pozycji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="4fce8-148">Select the product receipt for the inventory item that you received.</span></span>
    * <span data-ttu-id="4fce8-149">Wiersz z dokumentem przyjęcia produktów został uzgodniony, ale występuje niezgodność ilości lub ceny, dlatego operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="4fce8-149">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="4fce8-150">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="4fce8-150">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="4fce8-151">Teraz, gdy cena jednostkowa jest zgodna, stan został zaktualizowany na Powodzenie.</span><span class="sxs-lookup"><span data-stu-id="4fce8-151">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="4fce8-152">Jeśli zasady pozwalają na rozbieżności lub gdy uzgadnianie jest traktowane jedynie jako ostrzeżenie, można zaksięgować fakturę.</span><span class="sxs-lookup"><span data-stu-id="4fce8-152">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="4fce8-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4fce8-153">Close the page.</span></span>
19. <span data-ttu-id="4fce8-154">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="4fce8-154">Click Post.</span></span>
20. <span data-ttu-id="4fce8-155">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="4fce8-155">Close the form.</span></span>
    * <span data-ttu-id="4fce8-156">Zwróć uwagę, że zamówienie zakupu nie jest już wyświetlane jako otrzymane, ale niezafakturowane.</span><span class="sxs-lookup"><span data-stu-id="4fce8-156">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  


