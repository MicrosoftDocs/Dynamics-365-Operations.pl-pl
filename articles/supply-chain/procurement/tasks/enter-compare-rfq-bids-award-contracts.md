---
title: Wprowadzanie i porównywanie ofert dla ZO oraz udzielanie zamówień
description: W tej procedurze pokazano sposób wprowadzania odpowiedzi na ZO, oceniania i porównywania ofert, a następnie przyznawania realizacji oferty jednemu z dostawców.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7cd4876acfebcc9595abb358cfc9b355e93041d6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "350005"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a><span data-ttu-id="38318-103">Wprowadzanie i porównywanie ofert dla ZO oraz udzielanie zamówień</span><span class="sxs-lookup"><span data-stu-id="38318-103">Enter and compare RFQ bids, and award contracts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38318-104">W tej procedurze pokazano sposób wprowadzania odpowiedzi na ZO, oceniania i porównywania ofert, a następnie przyznawania realizacji oferty jednemu z dostawców.</span><span class="sxs-lookup"><span data-stu-id="38318-104">This procedure shows you how to enter replies to an RFQ, score and compare bids, and then award the bid to one of the vendors.</span></span> <span data-ttu-id="38318-105">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="38318-105">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="38318-106">Przed rozpoczęciem trzeba mieć ZO z dwoma wierszami, które zostało wysłane co najmniej do dwóch dostawców.</span><span class="sxs-lookup"><span data-stu-id="38318-106">Before you start, you must have an RFQ with two lines that has been sent to at least two vendors.</span></span> <span data-ttu-id="38318-107">Można utworzyć takie niezbędne ZO za pomocą procedury „Tworzenie zapytania ofertowego”.</span><span class="sxs-lookup"><span data-stu-id="38318-107">You can run the "Create a request for quotation" procedure as a prerequisite to create this.</span></span> <span data-ttu-id="38318-108">Przed wykonaniem tej procedury należy skonfigurować kryteria punktowania.</span><span class="sxs-lookup"><span data-stu-id="38318-108">You need to have set up scoring criteria before you can run this procedure.</span></span>


## <a name="enter-a-reply-from-a-vendor"></a><span data-ttu-id="38318-109">Wprowadzanie odpowiedzi od dostawcy</span><span class="sxs-lookup"><span data-stu-id="38318-109">Enter a reply from a vendor</span></span>
1. <span data-ttu-id="38318-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapytania ofertowe > Wszystkie zapytania ofertowe.</span><span class="sxs-lookup"><span data-stu-id="38318-110">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="38318-111">Zaznacz ZO o stanie Wysłane, a następnie kliknij łącze na numerze sprawy zapytania ofertowego.</span><span class="sxs-lookup"><span data-stu-id="38318-111">Select an RFQ that has a status of Sent and click the link on the Request for quotation case number.</span></span>
    * <span data-ttu-id="38318-112">ZO powinno było zostać wysłane co najmniej do 2 dostawców.</span><span class="sxs-lookup"><span data-stu-id="38318-112">The RFQ should have been sent to at least 2 vendors.</span></span>  
3. <span data-ttu-id="38318-113">Kliknij nagłówek i przejdź do listy dostawców.</span><span class="sxs-lookup"><span data-stu-id="38318-113">Click Header to go to the list of vendors.</span></span>
4. <span data-ttu-id="38318-114">Wybierz dostawcę, dla którego chcesz wprowadzić odpowiedź na ZO.</span><span class="sxs-lookup"><span data-stu-id="38318-114">Select the vendor for whom you want to enter a response on the RFQ.</span></span>
5. <span data-ttu-id="38318-115">Kliknij opcję Wprowadź odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="38318-115">Click Enter reply.</span></span>
6. <span data-ttu-id="38318-116">W okienku akcji kliknij pozycję Odpowiedz.</span><span class="sxs-lookup"><span data-stu-id="38318-116">On the Action Pane, click Reply.</span></span>
7. <span data-ttu-id="38318-117">Kliknij opcję Kopiuj dane do odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="38318-117">Click Copy data to reply.</span></span>
    * <span data-ttu-id="38318-118">Ta akcja spowoduje skopiowanie wybranych danych, na przykład ilości ze sprawy ZO do odpowiedzi na ZO.</span><span class="sxs-lookup"><span data-stu-id="38318-118">This action will copy selected data, for example, the quantity from the RFQ case to the RFQ reply.</span></span> <span data-ttu-id="38318-119">Alternatywnie można pominąć tę akcję i wypełnić wszystkie pola odpowiedzi ręcznie podczas edytowania odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="38318-119">Alternatively you can skip this action and fill in all the response fields manually when you edit the reply.</span></span>  
8. <span data-ttu-id="38318-120">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="38318-120">Click Edit.</span></span>
9. <span data-ttu-id="38318-121">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="38318-121">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="38318-122">Wybierz drugi wiersz oferty.</span><span class="sxs-lookup"><span data-stu-id="38318-122">Choose the other quotation line.</span></span>
11. <span data-ttu-id="38318-123">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="38318-123">In the Unit price field, enter a number.</span></span>

## <a name="score-the-bid"></a><span data-ttu-id="38318-124">Ocenianie oferty</span><span class="sxs-lookup"><span data-stu-id="38318-124">Score the bid</span></span>
1. <span data-ttu-id="38318-125">Kliknij nagłówek i przejdź do punktacji oferty.</span><span class="sxs-lookup"><span data-stu-id="38318-125">Click Header to go to the scoring of the bid.</span></span>
2. <span data-ttu-id="38318-126">Rozwiń sekcję Punktowanie oferty.</span><span class="sxs-lookup"><span data-stu-id="38318-126">Expand the Bid scoring section.</span></span>
3. <span data-ttu-id="38318-127">W polu Punktacja wprowadź liczbę dla jednego z kryteriów punktowania.</span><span class="sxs-lookup"><span data-stu-id="38318-127">In the Score field, enter a number for one of the scoring criteria.</span></span>
    * <span data-ttu-id="38318-128">Po umieszczeniu wskaźnika myszy nad jednym z kryteriów punktowania pojawia się etykietka narzędzia pokazująca zakres punktów, w którym trzeba się zmieścić.</span><span class="sxs-lookup"><span data-stu-id="38318-128">If you hover over one of the scoring criteria a tooltip shows the range that you have to score within.</span></span> <span data-ttu-id="38318-129">W tej demonstracji można dodać liczbę z zakresu od 1 do 5 do każdego z kryteriów.</span><span class="sxs-lookup"><span data-stu-id="38318-129">In this demo you can add a number between 1 and 5 to any of the criteria.</span></span>  
4. <span data-ttu-id="38318-130">Zaznacz inne kryterium punktowania.</span><span class="sxs-lookup"><span data-stu-id="38318-130">Select another scoring criterion.</span></span>
5. <span data-ttu-id="38318-131">W polu Punktacja wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="38318-131">In the Score field, enter a number.</span></span>
6. <span data-ttu-id="38318-132">Rozwiń sekcję Kwestionariusze.</span><span class="sxs-lookup"><span data-stu-id="38318-132">Expand the Questionnaires section.</span></span>
    * <span data-ttu-id="38318-133">Jeśli sprawa ZO zawiera kwestionariusz, który został wysłany do dostawców, można wprowadzić ich odpowiedzi w sekcji kwestionariuszy.</span><span class="sxs-lookup"><span data-stu-id="38318-133">If the RFQ case has a questionnaire that was sent to the vendors, you can enter their responses in the questionnaire section.</span></span>  
7. <span data-ttu-id="38318-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38318-134">Close the page.</span></span>

## <a name="enter-a-reply-for-another-vendor"></a><span data-ttu-id="38318-135">Wprowadzanie odpowiedzi od innego dostawcy</span><span class="sxs-lookup"><span data-stu-id="38318-135">Enter a reply for another vendor</span></span>
1. <span data-ttu-id="38318-136">Wybierz następnego dostawcę, usuwając zaznaczenie dostawcy, dla którego właśnie wprowadzono odpowiedź, a następnie zaznaczając wiersz następnego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="38318-136">Select the next vendor by clearing the vendor you have just entered the reply for and then selecting the row for the next vendor.</span></span>
2. <span data-ttu-id="38318-137">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="38318-137">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="38318-138">Kliknij opcję Wprowadź odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="38318-138">Click Enter reply.</span></span>
4. <span data-ttu-id="38318-139">Kliknij opcję Kopiuj dane do odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="38318-139">Click Copy data to reply.</span></span>
5. <span data-ttu-id="38318-140">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="38318-140">Click Edit.</span></span>
6. <span data-ttu-id="38318-141">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="38318-141">In the Unit price field, enter a number.</span></span>
7. <span data-ttu-id="38318-142">Wybierz drugi wiersz oferty.</span><span class="sxs-lookup"><span data-stu-id="38318-142">Choose the other quotation line.</span></span>
8. <span data-ttu-id="38318-143">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="38318-143">In the Unit price field, enter a number.</span></span>

## <a name="score-the-second-bid"></a><span data-ttu-id="38318-144">Ocenianie drugiej oferty</span><span class="sxs-lookup"><span data-stu-id="38318-144">Score the second bid</span></span>
1. <span data-ttu-id="38318-145">Kliknij nagłówek i przejdź do punktacji oferty.</span><span class="sxs-lookup"><span data-stu-id="38318-145">Click Header to go to scoring of the bid.</span></span>
2. <span data-ttu-id="38318-146">W polu Punktacja wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="38318-146">In the Score field, enter a number.</span></span>
3. <span data-ttu-id="38318-147">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="38318-147">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="38318-148">W polu Punktacja wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="38318-148">In the Score field, enter a number.</span></span>

## <a name="compare-the-replies"></a><span data-ttu-id="38318-149">Porównywanie odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="38318-149">Compare the replies</span></span>
1. <span data-ttu-id="38318-150">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="38318-150">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="38318-151">Kliknij opcję Porównaj odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="38318-151">Click Compare replies.</span></span>
3. <span data-ttu-id="38318-152">W polu Ranga wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="38318-152">In the Rank field, enter a number.</span></span>
    * <span data-ttu-id="38318-153">Ta strona pokazuje oferty z nagłówkami i wierszami oraz łączny wynik punktowy na poziomie nagłówka.</span><span class="sxs-lookup"><span data-stu-id="38318-153">This page shows the bids with the header and lines, and the total score on the header level.</span></span> <span data-ttu-id="38318-154">Wiersze można porównywać poprzez sortowanie ich w siatce, tak aby porównywalne wiersze znalazły się obok siebie.</span><span class="sxs-lookup"><span data-stu-id="38318-154">You can compare the lines by sorting in the grid so that comparable lines are next to each other.</span></span> <span data-ttu-id="38318-155">Znajdują się tu również następujące informacje:   Ilość: Ilość oferowana przez dostawcę.</span><span class="sxs-lookup"><span data-stu-id="38318-155">The information also includes:   Quantity: The quantity quoted by the vendor.</span></span> <span data-ttu-id="38318-156">Ta ilość może nie być równa ilości określonej w ZO.</span><span class="sxs-lookup"><span data-stu-id="38318-156">This might not equal the quantity specified in the RFQ.</span></span>   <span data-ttu-id="38318-157">Kwota netto: Cena wskazana przez dostawcę, po odjęciu rabatów dla towarów w wierszu.</span><span class="sxs-lookup"><span data-stu-id="38318-157">Net amount: The price quoted by a vendor, after subtracting any discounts, for the items on the line.</span></span>   <span data-ttu-id="38318-158">Odchylenie: Liczba dni różnicy między datą dostawy w ofercie lub wierszu a wymaganą datą dostawy w nagłówku lub wierszu zapytania ofertowego.</span><span class="sxs-lookup"><span data-stu-id="38318-158">Deviation: The number of days that the delivery date in the bid header or line deviates from the requested delivery date in the RFQ header or RFQ line.</span></span>   <span data-ttu-id="38318-159">Dla każdej oferty można wprowadzić rangę.</span><span class="sxs-lookup"><span data-stu-id="38318-159">You can enter a rank for each bid.</span></span>  
4. <span data-ttu-id="38318-160">Zaznacz wiersz nagłówka dla drugiej oferty, którą chcesz sklasyfikować.</span><span class="sxs-lookup"><span data-stu-id="38318-160">Select the header line for the other bid that you want to rank.</span></span>
5. <span data-ttu-id="38318-161">W polu Ranga wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="38318-161">In the Rank field, enter a number.</span></span>
6. <span data-ttu-id="38318-162">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="38318-162">Click Save.</span></span>

## <a name="reject-a-bid"></a><span data-ttu-id="38318-163">Odrzucanie oferty</span><span class="sxs-lookup"><span data-stu-id="38318-163">Reject a bid</span></span>
1. <span data-ttu-id="38318-164">Zaznacz wiersz nagłówka dla oferty, którą odrzucić.</span><span class="sxs-lookup"><span data-stu-id="38318-164">Select the header line for the bid that you want to reject.</span></span>
    * <span data-ttu-id="38318-165">Można zaakceptować, odrzucić albo zwrócić tylko jedną ofertę lub wiersz jednej oferty na raz.</span><span class="sxs-lookup"><span data-stu-id="38318-165">You can only accept, reject, or return one bid or lines within one bid at a time.</span></span>  
2. <span data-ttu-id="38318-166">Zaznacz pole wyboru Zaznacz.</span><span class="sxs-lookup"><span data-stu-id="38318-166">Select the Mark check box.</span></span>
    * <span data-ttu-id="38318-167">Zaznaczenie pola wyboru Zaznacz w nagłówku oferty spowoduje oznaczenie również wszystkich wierszy.</span><span class="sxs-lookup"><span data-stu-id="38318-167">If you select the Mark check box on the Header of the bid then all the lines will be marked as well.</span></span> <span data-ttu-id="38318-168">Można również oznaczyć podzbiór wierszy oferty, aby odrzucić lub zaakceptować tylko je.</span><span class="sxs-lookup"><span data-stu-id="38318-168">You could also choose to mark a subset of the lines within the bid to reject or accept those.</span></span> <span data-ttu-id="38318-169">Można zaakceptować ofertę jednego dostawcy dla niektórych wierszy ZO, a następnie przyznać realizację pozostałych wierszy ZO innemu dostawcy. Trzeba to jednak zrobić w 2 krokach, po jednej ofercie na raz.</span><span class="sxs-lookup"><span data-stu-id="38318-169">It’s possible to accept one vendor’s bid for some lines of an RFQ, and then award other RFQ lines to a different vendor, however you need to do this in 2 steps, one bid at a time.</span></span> <span data-ttu-id="38318-170">Jeśli istnieją wiersze alternatywne, można zaakceptować jedynie oryginalny wiersz oferty lub jego alternatywę, ale nie oba.</span><span class="sxs-lookup"><span data-stu-id="38318-170">If alternate lines are present, you can only accept either the original bid line or its alternate, but not both.</span></span>  
3. <span data-ttu-id="38318-171">Kliknij przycisk Odrzuć.</span><span class="sxs-lookup"><span data-stu-id="38318-171">Click Reject.</span></span>
4. <span data-ttu-id="38318-172">Kliknij przycisk Parametry, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="38318-172">Click Parameters to open the drop dialog.</span></span>
5. <span data-ttu-id="38318-173">W polu Przyczyna odrzucenia wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="38318-173">In the Reason reject field, enter or select a value.</span></span>
    * <span data-ttu-id="38318-174">Przyczyna odrzucenia będzie przechowywana w odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="38318-174">The reason for rejection will be stored on the reply.</span></span>  
6. <span data-ttu-id="38318-175">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="38318-175">Click OK.</span></span>
7. <span data-ttu-id="38318-176">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="38318-176">Click OK.</span></span>
8. <span data-ttu-id="38318-177">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38318-177">Close the page.</span></span>
9. <span data-ttu-id="38318-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38318-178">Close the page.</span></span>
10. <span data-ttu-id="38318-179">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="38318-179">Refresh the page.</span></span>

## <a name="accept-a-bid"></a><span data-ttu-id="38318-180">Akceptowanie oferty</span><span class="sxs-lookup"><span data-stu-id="38318-180">Accept a bid</span></span>
1. <span data-ttu-id="38318-181">Wybierz ofertę, którą chcesz zaakceptować, a następnie kliknij łącze w polu Zapytanie ofertowe.</span><span class="sxs-lookup"><span data-stu-id="38318-181">Select the bid that you want to accept and then click the link in the Request for quotation field.</span></span>
2. <span data-ttu-id="38318-182">W okienku akcji kliknij pozycję Odpowiedz.</span><span class="sxs-lookup"><span data-stu-id="38318-182">On the Action Pane, click Reply.</span></span>
3. <span data-ttu-id="38318-183">Kliknij przycisk Akceptuj.</span><span class="sxs-lookup"><span data-stu-id="38318-183">Click Accept.</span></span>
    * <span data-ttu-id="38318-184">Po oznaczeniu określonych wierszy czynność akceptacji obejmie tylko te wiersze.</span><span class="sxs-lookup"><span data-stu-id="38318-184">If you have marked specific lines and not others then the accept action will only include the marked lines.</span></span> <span data-ttu-id="38318-185">Jeśli chcesz zaakceptować wszystkie wiersze oferty, nie trzeba oznaczać wierszy.</span><span class="sxs-lookup"><span data-stu-id="38318-185">If you want to accept all lines on the bid then you do not have to mark the lines.</span></span>  
4. <span data-ttu-id="38318-186">Kliknij przycisk Parametry, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="38318-186">Click Parameters to open the drop dialog.</span></span>
    * <span data-ttu-id="38318-187">Dzięki temu można zarejestrować przyczynę zaakceptowania oferty.</span><span class="sxs-lookup"><span data-stu-id="38318-187">This allows you to record a reason for accepting the bid.</span></span> <span data-ttu-id="38318-188">Przyczyna będzie przechowywana w ofercie.</span><span class="sxs-lookup"><span data-stu-id="38318-188">The reason will be stored on the bid.</span></span>  
5. <span data-ttu-id="38318-189">W polu Przyczyna akceptacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="38318-189">In the Reason accept field, enter or select a value.</span></span>
6. <span data-ttu-id="38318-190">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="38318-190">Click OK.</span></span>
7. <span data-ttu-id="38318-191">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="38318-191">Click OK.</span></span>
    * <span data-ttu-id="38318-192">Po kliknięciu przycisku OK zostanie wygenerowane zamówienie zakupu na podstawie wierszy objętych akceptacją ZO.</span><span class="sxs-lookup"><span data-stu-id="38318-192">When you click OK this generates a purchase order based on the lines that are included in the RFQ acceptance.</span></span> <span data-ttu-id="38318-193">Jeśli istnieją inne oferty, które nie zostały przetworzone (zaakceptowane, odrzucone lub zwrócone), system wyświetli monit o odrzucenie pozostałych ofert.</span><span class="sxs-lookup"><span data-stu-id="38318-193">If there are other bids that have not been processed (accepted, rejected, or returned) then the system will prompt you to reject the remaining bids.</span></span>  

## <a name="view-the-purchase-order-thats-been-generated"></a><span data-ttu-id="38318-194">Wyświetlanie wygenerowanego zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="38318-194">View the purchase order that's been generated</span></span>
1. <span data-ttu-id="38318-195">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="38318-195">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="38318-196">Kliknij opcję Zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="38318-196">Click Purchase order.</span></span>
    * <span data-ttu-id="38318-197">Tutaj widać zamówienie zakupu wygenerowane w momencie akceptacji oferty.</span><span class="sxs-lookup"><span data-stu-id="38318-197">Here you can see the purchase order that was generated when you accepted the bid.</span></span>  
3. <span data-ttu-id="38318-198">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38318-198">Close the page.</span></span>
4. <span data-ttu-id="38318-199">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38318-199">Close the page.</span></span>
5. <span data-ttu-id="38318-200">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38318-200">Close the page.</span></span>
6. <span data-ttu-id="38318-201">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38318-201">Close the page.</span></span>

