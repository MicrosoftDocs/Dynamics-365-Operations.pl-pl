---
title: Tworzenie zapotrzebowania wykorzystującego ZO
description: W tym temacie przedstawiono sposób dodawania informacji o cenie i dostawcy do zapotrzebowania na zakup z procesu ZO.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e67dafd02a3b2a38832d8a4f0e9809adffcbb80
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211845"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="faec7-103">Tworzenie zapotrzebowania wykorzystującego ZO</span><span class="sxs-lookup"><span data-stu-id="faec7-103">Create a requisition that uses an RFQ</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="faec7-104">W tym temacie przedstawiono sposób dodawania informacji o cenie i dostawcy do zapotrzebowania na zakup z procesu ZO.</span><span class="sxs-lookup"><span data-stu-id="faec7-104">This topic explains how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="faec7-105">Przykład opisany w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. Aby wykonać wszystkie czynności, trzeba być zalogowanym jako administrator.</span><span class="sxs-lookup"><span data-stu-id="faec7-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="faec7-106">Zadania w tym przewodniku zazwyczaj wykonują pracownicy działu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="faec7-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="faec7-107">Tworzenie zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="faec7-107">Create a requisition</span></span>
1. <span data-ttu-id="faec7-108">W okienku nawigacji wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Zapotrzebowania na zakup przygotowane przeze mnie**.</span><span class="sxs-lookup"><span data-stu-id="faec7-108">In the navigation pane, go to **Modules > Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me**.</span></span>
2. <span data-ttu-id="faec7-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="faec7-109">Select **New**.</span></span>
3. <span data-ttu-id="faec7-110">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="faec7-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="faec7-111">W polu **Data wymagalności** wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="faec7-111">In the **Requested date** field, enter a date.</span></span>
5. <span data-ttu-id="faec7-112">W polu **Data księgowania** wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="faec7-112">In the **Accounting date** field, enter a date.</span></span>
6. <span data-ttu-id="faec7-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="faec7-113">Select **OK**.</span></span>
7. <span data-ttu-id="faec7-114">W polu **Przyczyna** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="faec7-114">In the **Reason** field, enter or select a value.</span></span>
8. <span data-ttu-id="faec7-115">Wybierz **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="faec7-115">Select **Add line**.</span></span>
9. <span data-ttu-id="faec7-116">W polu **Kategoria zaopatrzenia** wybierz kategorię w drzewie, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="faec7-116">In the **Procurement category** field, select a category in the tree, and then select **OK**.</span></span>
10. <span data-ttu-id="faec7-117">W polu **Nazwa produktu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="faec7-117">In the **Product name** field, type a value.</span></span>
11. <span data-ttu-id="faec7-118">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="faec7-118">In the **Quantity** field, enter a number.</span></span>
12. <span data-ttu-id="faec7-119">W polu **Jednostka** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="faec7-119">In the **Unit** field, enter or select a value.</span></span>
13. <span data-ttu-id="faec7-120">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="faec7-120">Select **Save**.</span></span>
14. <span data-ttu-id="faec7-121">Wybierz opcję **Przepływ pracy**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="faec7-121">Select **Workflow** to open the drop dialog.</span></span>
15. <span data-ttu-id="faec7-122">Wybierz opcję **Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="faec7-122">Select **Submit**.</span></span>
16. <span data-ttu-id="faec7-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="faec7-123">Close the page.</span></span>
17. <span data-ttu-id="faec7-124">Wybierz opcję **Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="faec7-124">Select **Submit**.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="faec7-125">Zmiana przypisania zadania przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="faec7-125">Reassign a workflow task</span></span>
<span data-ttu-id="faec7-126">Następne zadanie polega na utworzeniu ZO w celu uzyskania od dostawców ofert na produkt.</span><span class="sxs-lookup"><span data-stu-id="faec7-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="faec7-127">W danych firmy demonstracyjnej USMF przepływ pracy zapotrzebowania ma skonfigurowaną regułę, która stanowi, że jeśli dostawca nie zostanie wybrany lub cena jednostkowa dla wiersza jest równa 0, konkretnemu pracownikowi zostanie przypisane zadanie utworzenia ZO.</span><span class="sxs-lookup"><span data-stu-id="faec7-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="faec7-128">Aby kontynuować pracę w tym przewodniku, musisz przypisać to zadanie innemu użytkownikowi (sobie).</span><span class="sxs-lookup"><span data-stu-id="faec7-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="faec7-129">Możesz to zrobić tylko wtedy, gdy logujesz się jako administrator.</span><span class="sxs-lookup"><span data-stu-id="faec7-129">You can only do this if you are logged in as an Admin.</span></span>  

1. <span data-ttu-id="faec7-130">Wybierz opcję **Przepływ pracy**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="faec7-130">Select **Workflow** to open the drop dialog.</span></span>
2. <span data-ttu-id="faec7-131">Wybierz **Wyświetl historię**.</span><span class="sxs-lookup"><span data-stu-id="faec7-131">Select **View history**.</span></span>
3. <span data-ttu-id="faec7-132">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="faec7-132">Refresh the page.</span></span>
4. <span data-ttu-id="faec7-133">Rozwiń sekcję **Szczegóły śledzenia**.</span><span class="sxs-lookup"><span data-stu-id="faec7-133">Expand the **Tracking details** section.</span></span>
5. <span data-ttu-id="faec7-134">W drzewie zaznacz wiersz, który zaczyna się fragmentem „Uruchomiono przepływ pracy dla pozycji dnia”.</span><span class="sxs-lookup"><span data-stu-id="faec7-134">In the tree, select the line that starts with "Line workflow activated on".</span></span>
6. <span data-ttu-id="faec7-135">Wybierz **Wyświetl szczegóły przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="faec7-135">Select **View workflow details**.</span></span>
7. <span data-ttu-id="faec7-136">Rozwiń sekcję **Elementy robocze**.</span><span class="sxs-lookup"><span data-stu-id="faec7-136">Expand the **Work items** section.</span></span>
8. <span data-ttu-id="faec7-137">Wybierz opcję **Przypisz ponownie**.</span><span class="sxs-lookup"><span data-stu-id="faec7-137">Select **Reassign**.</span></span>
9. <span data-ttu-id="faec7-138">W polu **Użytkownik** wybierz opcję **Administrator**.</span><span class="sxs-lookup"><span data-stu-id="faec7-138">In the **User** field, select **Admin**.</span></span>
10. <span data-ttu-id="faec7-139">Wybierz opcję **Przypisz ponownie**.</span><span class="sxs-lookup"><span data-stu-id="faec7-139">Select **Reassign**.</span></span>
11. <span data-ttu-id="faec7-140">Zamknij obie strony.</span><span class="sxs-lookup"><span data-stu-id="faec7-140">Close the two pages.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="faec7-141">Tworzenie ZO</span><span class="sxs-lookup"><span data-stu-id="faec7-141">Create an RFQ</span></span>

1. <span data-ttu-id="faec7-142">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="faec7-142">Refresh the page.</span></span>
2. <span data-ttu-id="faec7-143">Wybierz **Zapytanie ofertowe**.</span><span class="sxs-lookup"><span data-stu-id="faec7-143">Select **Request for quotation**.</span></span>
3. <span data-ttu-id="faec7-144">W polu **Firma dokonująca zakupu** zaznacz wartość **USMF**.</span><span class="sxs-lookup"><span data-stu-id="faec7-144">In the **Buying legal entity** field, select **USMF**.</span></span> <span data-ttu-id="faec7-145">Należy zaznaczyć tę samą firmę, jak w wierszu zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="faec7-145">You must select the same legal entity that's on the requisition line.</span></span>  
4. <span data-ttu-id="faec7-146">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="faec7-146">In the list, mark the selected row.</span></span> <span data-ttu-id="faec7-147">Jeśli masz wiele wierszy w zapotrzebowaniu na zakup, zaznacz wszystkie wiersze, które chcesz dodać do zapytania ofertowego.</span><span class="sxs-lookup"><span data-stu-id="faec7-147">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="faec7-148">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="faec7-148">Select **OK**.</span></span>
6. <span data-ttu-id="faec7-149">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="faec7-149">Refresh the page.</span></span>
7. <span data-ttu-id="faec7-150">Upewnij się, że pole informacji jest otwarte, a następnie rozwiń sekcję **Dokumenty powiązane**.</span><span class="sxs-lookup"><span data-stu-id="faec7-150">Ensure that the FactBox is open, then expand the **Related documents** section.</span></span>
8. <span data-ttu-id="faec7-151">Kliknij łącze w polu **Zapytanie ofertowe** i otwórz ZO, które zostało właśnie utworzone.</span><span class="sxs-lookup"><span data-stu-id="faec7-151">Select the link in the **Request for quotation** field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="faec7-152">Wybierz **Nagłówek**.</span><span class="sxs-lookup"><span data-stu-id="faec7-152">Select **Header**.</span></span>
10. <span data-ttu-id="faec7-153">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="faec7-153">Select **Add**.</span></span>
11. <span data-ttu-id="faec7-154">W polu **Konto dostawcy** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="faec7-154">In the **Vendor account** field, enter or select a value.</span></span>
12. <span data-ttu-id="faec7-155">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="faec7-155">Select **Add**.</span></span>
13. <span data-ttu-id="faec7-156">W polu **Konto dostawcy** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="faec7-156">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="faec7-157">Wybierz opcję **Wyślij**.</span><span class="sxs-lookup"><span data-stu-id="faec7-157">Select **Send**.</span></span>
15. <span data-ttu-id="faec7-158">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="faec7-158">Select **OK**.</span></span>
16. <span data-ttu-id="faec7-159">Wybierz opcję **Wprowadź odpowiedź**.</span><span class="sxs-lookup"><span data-stu-id="faec7-159">Select **Enter reply**.</span></span>
17. <span data-ttu-id="faec7-160">W okienku akcji kliknij pozycję **Odpowiedz**.</span><span class="sxs-lookup"><span data-stu-id="faec7-160">On the Action Pane, select **Reply**.</span></span>
18. <span data-ttu-id="faec7-161">Wybierz **Kopiuj dane do odpowiedzi**.</span><span class="sxs-lookup"><span data-stu-id="faec7-161">Select **Copy data to reply**.</span></span> <span data-ttu-id="faec7-162">Spowoduje to skopiowanie danych, takich jak ilości i daty, z ZO do odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="faec7-162">This copies data, such as the quantity and dates, from the RFQ to the reply.</span></span>  
19. <span data-ttu-id="faec7-163">W polu **Cena jednostkowa** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="faec7-163">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="faec7-164">Jest to cena otrzymana od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="faec7-164">This is the price that you've received from the vendor.</span></span> <span data-ttu-id="faec7-165">Można także wprowadzić dodatkowe informacje od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="faec7-165">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="faec7-166">Wybierz **Akceptuj**.</span><span class="sxs-lookup"><span data-stu-id="faec7-166">Select **Accept**.</span></span>
21. <span data-ttu-id="faec7-167">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="faec7-167">Select **OK**.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="faec7-168">Sprawdzanie, czy informacje o dostawcy i cenie zostały przeniesione do zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="faec7-168">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="faec7-169">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="faec7-169">Close the page.</span></span>
2. <span data-ttu-id="faec7-170">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="faec7-170">Select **Lines**.</span></span>
3. <span data-ttu-id="faec7-171">Wybierz **Informacje pokrewne**.</span><span class="sxs-lookup"><span data-stu-id="faec7-171">Select **Related information**.</span></span>
4. <span data-ttu-id="faec7-172">Wybierz **Zapotrzebowanie na zakup**.</span><span class="sxs-lookup"><span data-stu-id="faec7-172">Select **Purchase requisition**.</span></span>
5. <span data-ttu-id="faec7-173">Zaznacz wiersz, który został przeniesiony do zapytania ofertowego.</span><span class="sxs-lookup"><span data-stu-id="faec7-173">Select the line that was transferred to the RFQ.</span></span> <span data-ttu-id="faec7-174">Sprawdź, czy informacje o cenie i dostawcy zostały skopiowane do zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="faec7-174">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="faec7-175">Wybierz opcję **Przepływ pracy**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="faec7-175">Select **Workflow** to open the drop dialog.</span></span>
7. <span data-ttu-id="faec7-176">Wybierz opcję Zakończone.</span><span class="sxs-lookup"><span data-stu-id="faec7-176">Select Complete.</span></span>
8. <span data-ttu-id="faec7-177">Wybierz stronę.</span><span class="sxs-lookup"><span data-stu-id="faec7-177">Select the page.</span></span>
9. <span data-ttu-id="faec7-178">Wybierz opcję Zakończone.</span><span class="sxs-lookup"><span data-stu-id="faec7-178">Select Complete.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]