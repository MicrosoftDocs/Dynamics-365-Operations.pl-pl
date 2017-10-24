--- 
title: "Tworzenie zapotrzebowania wykorzystującego ZO"
description: "W tym przewodniku przedstawiono sposób dodawania informacji o cenie i dostawcy do zapotrzebowania na zakup z procesu ZO."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d97ccd15031b2f7398486eee4a716ecef5e9dafd
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="a8d23-103">Tworzenie zapotrzebowania wykorzystującego ZO</span><span class="sxs-lookup"><span data-stu-id="a8d23-103">Create a requisition that uses an RFQ</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a8d23-104">W tym przewodniku przedstawiono sposób dodawania informacji o cenie i dostawcy do zapotrzebowania na zakup z procesu ZO.</span><span class="sxs-lookup"><span data-stu-id="a8d23-104">This guide shows how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="a8d23-105">Przykład opisany w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. Aby wykonać wszystkie czynności, trzeba być zalogowanym jako administrator.</span><span class="sxs-lookup"><span data-stu-id="a8d23-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="a8d23-106">Zadania w tym przewodniku zazwyczaj wykonują pracownicy działu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="a8d23-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="a8d23-107">Tworzenie zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="a8d23-107">Create a requisition</span></span>
1. <span data-ttu-id="a8d23-108">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Zapotrzebowania na zakup przygotowane przeze mnie.</span><span class="sxs-lookup"><span data-stu-id="a8d23-108">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="a8d23-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a8d23-109">Click New.</span></span>
3. <span data-ttu-id="a8d23-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a8d23-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="a8d23-111">W polu Data wymagalności wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-111">In the Requested date field, enter a date.</span></span>
5. <span data-ttu-id="a8d23-112">W polu Data księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-112">In the Accounting date field, enter a date.</span></span>
6. <span data-ttu-id="a8d23-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a8d23-113">Click OK.</span></span>
7. <span data-ttu-id="a8d23-114">W polu Przyczyna wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a8d23-114">In the Reason field, enter or select a value.</span></span>
8. <span data-ttu-id="a8d23-115">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="a8d23-115">Click Add line.</span></span>
9. <span data-ttu-id="a8d23-116">W polu Kategoria zaopatrzenia wybierz kategorię w drzewie, a następnie kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a8d23-116">In the Procurement category field, select a category in the tree, and then click OK.</span></span>
10. <span data-ttu-id="a8d23-117">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a8d23-117">In the Product name field, type a value.</span></span>
11. <span data-ttu-id="a8d23-118">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="a8d23-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="a8d23-119">W polu Jednostka wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a8d23-119">In the Unit field, enter or select a value.</span></span>
13. <span data-ttu-id="a8d23-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a8d23-120">Click Save.</span></span>
14. <span data-ttu-id="a8d23-121">Kliknij opcję Przepływ pracy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="a8d23-121">Click Workflow to open the drop dialog.</span></span>
15. <span data-ttu-id="a8d23-122">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="a8d23-122">Click Submit.</span></span>
16. <span data-ttu-id="a8d23-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-123">Close the page.</span></span>
17. <span data-ttu-id="a8d23-124">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="a8d23-124">Click Submit.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="a8d23-125">Zmiana przypisania zadania przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="a8d23-125">Reassign a workflow task</span></span>
    * <span data-ttu-id="a8d23-126">Następne zadanie polega na utworzeniu ZO w celu uzyskania od dostawców ofert na produkt.</span><span class="sxs-lookup"><span data-stu-id="a8d23-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="a8d23-127">W danych firmy demonstracyjnej USMF przepływ pracy zapotrzebowania ma skonfigurowaną regułę, która stanowi, że jeśli dostawca nie zostanie wybrany lub cena jednostkowa dla wiersza jest równa 0, konkretnemu pracownikowi zostanie przypisane zadanie utworzenia ZO.</span><span class="sxs-lookup"><span data-stu-id="a8d23-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="a8d23-128">Aby kontynuować pracę w tym przewodniku, musisz przypisać to zadanie innemu użytkownikowi (sobie).</span><span class="sxs-lookup"><span data-stu-id="a8d23-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="a8d23-129">Możesz to zrobić tylko wtedy, gdy logujesz się jako administrator.</span><span class="sxs-lookup"><span data-stu-id="a8d23-129">You can only do this if you are logged in as an Admin.</span></span>  
1. <span data-ttu-id="a8d23-130">Kliknij opcję Przepływ pracy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="a8d23-130">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="a8d23-131">Kliknij opcję Wyświetl historię.</span><span class="sxs-lookup"><span data-stu-id="a8d23-131">Click View history.</span></span>
3. <span data-ttu-id="a8d23-132">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-132">Refresh the page.</span></span>
4. <span data-ttu-id="a8d23-133">Rozwiń sekcję Szczegóły śledzenia.</span><span class="sxs-lookup"><span data-stu-id="a8d23-133">Expand the Tracking details section.</span></span>
5. <span data-ttu-id="a8d23-134">W drzewie zaznacz wiersz zaczyna się fragmentem „Uruchomiono przepływ pracy dla pozycji dnia”.</span><span class="sxs-lookup"><span data-stu-id="a8d23-134">In the tree, select 'the line that starts with “Line workflow activated on”'.</span></span>
6. <span data-ttu-id="a8d23-135">Kliknij opcję Wyświetl szczegóły przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a8d23-135">Click View workflow details.</span></span>
7. <span data-ttu-id="a8d23-136">Rozwiń sekcję Elementy robocze.</span><span class="sxs-lookup"><span data-stu-id="a8d23-136">Expand the Work items section.</span></span>
8. <span data-ttu-id="a8d23-137">Kliknij przycisk Przypisz ponownie.</span><span class="sxs-lookup"><span data-stu-id="a8d23-137">Click Reassign.</span></span>
9. <span data-ttu-id="a8d23-138">W polu Użytkownik wybierz opcję „Administrator”.</span><span class="sxs-lookup"><span data-stu-id="a8d23-138">In the User field, select Admin.</span></span>
10. <span data-ttu-id="a8d23-139">Kliknij przycisk Przypisz ponownie.</span><span class="sxs-lookup"><span data-stu-id="a8d23-139">Click Reassign.</span></span>
11. <span data-ttu-id="a8d23-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-140">Close the page.</span></span>
12. <span data-ttu-id="a8d23-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-141">Close the page.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="a8d23-142">Tworzenie ZO</span><span class="sxs-lookup"><span data-stu-id="a8d23-142">Create an RFQ</span></span>
1. <span data-ttu-id="a8d23-143">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-143">Refresh the page.</span></span>
2. <span data-ttu-id="a8d23-144">Kliknij opcję Zapytanie ofertowe.</span><span class="sxs-lookup"><span data-stu-id="a8d23-144">Click Request for quotation.</span></span>
3. <span data-ttu-id="a8d23-145">W polu Firma dokonująca zakupu zaznacz wartość USMF.</span><span class="sxs-lookup"><span data-stu-id="a8d23-145">In the Buying legal entity field, select USMF.</span></span>
    * <span data-ttu-id="a8d23-146">Należy zaznaczyć tę samą firmę, jak w wierszu zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="a8d23-146">You must select the same legal entity that’s on the requisition line.</span></span>  
4. <span data-ttu-id="a8d23-147">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="a8d23-147">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a8d23-148">Jeśli masz wiele wierszy w zapotrzebowaniu na zakup, zaznacz wszystkie wiersze, które chcesz dodać do zapytania ofertowego.</span><span class="sxs-lookup"><span data-stu-id="a8d23-148">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="a8d23-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a8d23-149">Click OK.</span></span>
6. <span data-ttu-id="a8d23-150">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-150">Refresh the page.</span></span>
7. <span data-ttu-id="a8d23-151">Otwórz pole informacji, a następnie rozwiń sekcję Dokumenty powiązane.</span><span class="sxs-lookup"><span data-stu-id="a8d23-151">Open the FactBox and then expand the Related documents section.</span></span>
    * <span data-ttu-id="a8d23-152">Być może już jest otwarte pole informacji.</span><span class="sxs-lookup"><span data-stu-id="a8d23-152">You may already have the FactBox open.</span></span> <span data-ttu-id="a8d23-153">Poszukaj ikony ze strzałką, na prawo od przycisków przełączników Wiersze/nagłówek.</span><span class="sxs-lookup"><span data-stu-id="a8d23-153">Look for the icon with an arrow on it, to the right of the Lines/Header toggle buttons.</span></span> <span data-ttu-id="a8d23-154">Jeśli strzałka wskazuje w prawo, pole informacji jest już otwarte.</span><span class="sxs-lookup"><span data-stu-id="a8d23-154">If the arrow is pointing to the right, the FactBox is already open.</span></span> <span data-ttu-id="a8d23-155">Jeżeli strzałka wskazuje w lewo, kliknij ją, aby otworzyć pole informacji.</span><span class="sxs-lookup"><span data-stu-id="a8d23-155">If the arrow points to the left, click it to open the FactBox.</span></span>  
8. <span data-ttu-id="a8d23-156">Kliknij łącze w polu Zapytanie ofertowe i otwórz ZO, która zostało właśnie utworzone.</span><span class="sxs-lookup"><span data-stu-id="a8d23-156">Click the link in the Request for quotation field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="a8d23-157">Kliknij nagłówek.</span><span class="sxs-lookup"><span data-stu-id="a8d23-157">Click Header.</span></span>
10. <span data-ttu-id="a8d23-158">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a8d23-158">Click Add.</span></span>
11. <span data-ttu-id="a8d23-159">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a8d23-159">In the Vendor account field, enter or select a value.</span></span>
12. <span data-ttu-id="a8d23-160">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a8d23-160">Click Add.</span></span>
13. <span data-ttu-id="a8d23-161">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a8d23-161">In the Vendor account field, enter or select a value.</span></span>
14. <span data-ttu-id="a8d23-162">Kliknij przycisk Wyślij.</span><span class="sxs-lookup"><span data-stu-id="a8d23-162">Click Send.</span></span>
15. <span data-ttu-id="a8d23-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a8d23-163">Click OK.</span></span>
16. <span data-ttu-id="a8d23-164">Kliknij opcję Wprowadź odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="a8d23-164">Click Enter reply.</span></span>
17. <span data-ttu-id="a8d23-165">W okienku akcji kliknij pozycję Odpowiedz.</span><span class="sxs-lookup"><span data-stu-id="a8d23-165">On the Action Pane, click Reply.</span></span>
18. <span data-ttu-id="a8d23-166">Kliknij opcję Kopiuj dane do odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="a8d23-166">Click Copy data to reply.</span></span>
    * <span data-ttu-id="a8d23-167">Spowoduje to skopiowanie danych, takich jak ilości i daty, z ZO do odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="a8d23-167">This copies data, such as the quantity and dates, from the RFQ to the reply .</span></span>  
19. <span data-ttu-id="a8d23-168">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="a8d23-168">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="a8d23-169">Jest to cena otrzymana od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="a8d23-169">This is the price that you’ve received from the vendor.</span></span> <span data-ttu-id="a8d23-170">Można także wprowadzić dodatkowe informacje od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="a8d23-170">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="a8d23-171">Kliknij przycisk Akceptuj.</span><span class="sxs-lookup"><span data-stu-id="a8d23-171">Click Accept.</span></span>
21. <span data-ttu-id="a8d23-172">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a8d23-172">Click OK.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="a8d23-173">Sprawdzanie, czy informacje o dostawcy i cenie zostały przeniesione do zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="a8d23-173">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="a8d23-174">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-174">Close the page.</span></span>
2. <span data-ttu-id="a8d23-175">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="a8d23-175">Click Lines.</span></span>
3. <span data-ttu-id="a8d23-176">Kliknij opcję Informacje pokrewne.</span><span class="sxs-lookup"><span data-stu-id="a8d23-176">Click Related information.</span></span>
4. <span data-ttu-id="a8d23-177">Kliknij opcję Zapotrzebowanie na zakup.</span><span class="sxs-lookup"><span data-stu-id="a8d23-177">Click Purchase requisition.</span></span>
5. <span data-ttu-id="a8d23-178">Zaznacz wiersz, który został przeniesiony do zapytania ofertowego.</span><span class="sxs-lookup"><span data-stu-id="a8d23-178">Select the line that was transferred to the RFQ.</span></span>
    * <span data-ttu-id="a8d23-179">Sprawdź, czy informacje o cenie i dostawcy zostały skopiowane do zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="a8d23-179">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="a8d23-180">Kliknij opcję Przepływ pracy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="a8d23-180">Click Workflow to open the drop dialog.</span></span>
7. <span data-ttu-id="a8d23-181">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="a8d23-181">Click Complete.</span></span>
8. <span data-ttu-id="a8d23-182">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a8d23-182">Close the page.</span></span>
9. <span data-ttu-id="a8d23-183">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="a8d23-183">Click Complete.</span></span>


