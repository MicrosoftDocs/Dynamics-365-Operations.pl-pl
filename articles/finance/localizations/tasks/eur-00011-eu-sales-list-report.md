---
title: EUR-00011 Generowanie raportu listy sprzedaży do UE
description: Ta procedura prowadzi przez proces generowania raportu o liście sprzedaży do UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  EUSalesList, EUSalesListSelection, SysQueryForm, SysLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d2f2b0232666694788abb08b05408f725a1f8e5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009084"
---
# <a name="eur-00011-generate-the-eu-sales-list-report"></a><span data-ttu-id="4a8ad-103">EUR-00011 Generowanie raportu listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="4a8ad-103">EUR-00011 Generate the EU sales list report</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4a8ad-104">Ta procedura prowadzi przez proces generowania raportu o liście sprzedaży do UE.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-104">This procedure walks you through generating the EU sales list report.</span></span> <span data-ttu-id="4a8ad-105">Obejmuje to przeniesienie wewnątrzwspólnotowych transakcji handlowych na listę sprzedaży do UE i wykonanie raportu.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-105">This includes transferring intra-community trade transactions to the EU sales list and running the report.</span></span> <span data-ttu-id="4a8ad-106">Elementem procedury jest także utworzenie wewnątrzwspólnotowego transakcji handlowej dla celów demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-106">This procedure also includes creating an intra-community trade transaction for demo purposes.</span></span> <span data-ttu-id="4a8ad-107">Aby uzyskać więcej informacji na temat raportowania list sprzedaży do UE, w tym o wymaganiach wstępnych, zobacz Pomoc.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-107">For more information about EU Sales list reporting, including required prerequisites, refer to Help.</span></span>

<span data-ttu-id="4a8ad-108">Ta procedura dotyczy wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-108">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="4a8ad-109">Procedura została utworzona przy użyciu danych firmy demonstracyjnej DEMF i w związku z tym Niemiec jako przykładowego lokalnego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-109">The procedure was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="4a8ad-110">W procedurze jest również używana Portugalia jako przykładowy kraj/region UE.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-110">The procedure also uses Portugal as an exemplar EU country/region.</span></span> <span data-ttu-id="4a8ad-111">Zanim będzie można wykonać tę procedurę, trzeba skonfigurować funkcję raportowania listy sprzedaży do UE.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-111">Before you can complete this procedure, you must configure EU sales list reporting.</span></span>

<span data-ttu-id="4a8ad-112">Procedura jest przeznaczona dla księgowych.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-112">This procedure is intended for accountants.</span></span>


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a><span data-ttu-id="4a8ad-113">Tworzenie wewnątrzwspólnotowej transakcji sprzedaży dla celów demonstracyjnych</span><span class="sxs-lookup"><span data-stu-id="4a8ad-113">Create an intra-community sales transaction for demo purposes</span></span>
1. <span data-ttu-id="4a8ad-114">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-114">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4a8ad-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-115">Click New.</span></span>
3. <span data-ttu-id="4a8ad-116">W polu Konto odbiorcy wpisz „PRT-001”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-116">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="4a8ad-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-117">Click OK.</span></span>
5. <span data-ttu-id="4a8ad-118">W polu Numer pozycji wpisz „D0001”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-118">In the Item number field, type 'D0001'.</span></span>
6. <span data-ttu-id="4a8ad-119">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-119">Expand the Line details section.</span></span>
7. <span data-ttu-id="4a8ad-120">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-120">Click the Setup tab.</span></span>
8. <span data-ttu-id="4a8ad-121">W polu Grupa podatków dla towaru wpisz wartość „PEŁNE”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-121">In the Item sales tax group field, type 'FULL'.</span></span>
9. <span data-ttu-id="4a8ad-122">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-122">Click Add line.</span></span>
10. <span data-ttu-id="4a8ad-123">W polu Numer pozycji wpisz „D0003”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-123">In the Item number field, type 'D0003'.</span></span>
11. <span data-ttu-id="4a8ad-124">W polu Grupa podatków dla towaru wpisz wartość „CZERWONE”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-124">In the Item sales tax group field, type 'RED'.</span></span>
12. <span data-ttu-id="4a8ad-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-125">Click Save.</span></span>
13. <span data-ttu-id="4a8ad-126">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-126">On the Action Pane, click Invoice.</span></span>
14. <span data-ttu-id="4a8ad-127">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-127">Click Invoice.</span></span>
15. <span data-ttu-id="4a8ad-128">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-128">Expand the Parameters section.</span></span>
16. <span data-ttu-id="4a8ad-129">W polu Ilość zaznacz opcję Wszystko.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-129">In the Quantity field, select 'All'.</span></span>
17. <span data-ttu-id="4a8ad-130">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-130">Expand the Setup section.</span></span>
18. <span data-ttu-id="4a8ad-131">W polu Data faktury ustaw datę „01/11/2016”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-131">In the Invoice date field, set the date to '01/11/2016'.</span></span>
19. <span data-ttu-id="4a8ad-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-132">Click OK.</span></span>
20. <span data-ttu-id="4a8ad-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-133">Click OK.</span></span>

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a><span data-ttu-id="4a8ad-134">Przenoszenie wewnątrzwspólnotowych transakcji handlowych na listę sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="4a8ad-134">Transfer intra-community trade transactions to the EU sales list</span></span>
1. <span data-ttu-id="4a8ad-135">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Lista sprzedaży do UE.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-135">Go to Tax > Declarations > Foreign trade > EU sales list.</span></span>
2. <span data-ttu-id="4a8ad-136">Kliknij przycisk Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-136">Click Transfer.</span></span>
3. <span data-ttu-id="4a8ad-137">W polu Towar wybierz opcję Tak, aby przenieść transakcje dotyczące towaru.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-137">Select Yes in the Item field to transfer item transactions.</span></span>
4. <span data-ttu-id="4a8ad-138">W polu Usługa wybierz opcję Tak, aby przenieść transakcje dotyczące usług.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-138">Select Yes in the Service field to transfer service transactions.</span></span>
    * <span data-ttu-id="4a8ad-139">Można również określić dodatkowe filtry dla wewnątrzwspólnotowych transakcji handlowych w celu ich przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-139">You can also specify additional filters on intra-community trade transactions to transfer.</span></span>  
5. <span data-ttu-id="4a8ad-140">Kliknij przycisk Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-140">Click Transfer.</span></span>
    * <span data-ttu-id="4a8ad-141">Sprawdź, czy wewnątrzwspólnotowa transakcja sprzedaży została pomyślnie przeniesiona na listę sprzedaży do UE.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-141">Verify that the intra-community sales transaction is successfully transferred to the EU sales list.</span></span>  

## <a name="generate-the-eu-sales-list-report"></a><span data-ttu-id="4a8ad-142">Generowanie raportu listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="4a8ad-142">Generate the EU sales list report</span></span>
1. <span data-ttu-id="4a8ad-143">Kliknij opcję Raportowanie.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-143">Click Reporting.</span></span>
2. <span data-ttu-id="4a8ad-144">W polu Okres raportowania wybierz opcję „Miesięcznie”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-144">In the Reporting period field, select 'Monthly'.</span></span>
3. <span data-ttu-id="4a8ad-145">W polu Od dnia ustaw wartość daty równą „01/01/2016”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-145">In the From date field, set the date to '01/01/2016'.</span></span>
4. <span data-ttu-id="4a8ad-146">W polu Generuj plik zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-146">Select Yes in the Generate file field.</span></span>
5. <span data-ttu-id="4a8ad-147">W polu Generuj raport zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-147">Select Yes in the Generate report field.</span></span>
6. <span data-ttu-id="4a8ad-148">W polu Nazwa pliku wpisz „EUSalesList”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-148">In the File name field, type 'EUSalesList'.</span></span>
7. <span data-ttu-id="4a8ad-149">W polu Nazwa pliku raportu wpisz „EUSalesList”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-149">In the Report file name field, type 'EUSalesList'.</span></span>
8. <span data-ttu-id="4a8ad-150">W polu Identyfikator rejestracji listy sprzedaży do UE wpisz „123”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-150">In the EU Sales List Registration ID field, type '123'.</span></span>
    * <span data-ttu-id="4a8ad-151">To pole jest dostępne jedynie dla Niemiec.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-151">This field is only available for Germany.</span></span>  
    * <span data-ttu-id="4a8ad-152">Można również określić dodatkowe filtry dla wewnątrzwspólnotowych transakcji handlowych w celu ich umieszczenia w raporcie.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-152">You can also specify additional filters on intra-community trade transactions to include in the report.</span></span>  
9. <span data-ttu-id="4a8ad-153">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-153">Click OK.</span></span>
    * <span data-ttu-id="4a8ad-154">Sprawdź, czy pojawia się wyskakujące okienko z potwierdzeniem, że plik i raport kontrolny są pobierane.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-154">Verify that pop-up windows appear to confirm that the file and the control report are being downloaded.</span></span>  

## <a name="mark-eu-sales-list-lines-as-reported"></a><span data-ttu-id="4a8ad-155">Oznaczanie wierszy listy sprzedaży do UE jako zgłoszonych</span><span class="sxs-lookup"><span data-stu-id="4a8ad-155">Mark EU sales list lines as Reported</span></span>
1. <span data-ttu-id="4a8ad-156">Kliknij opcję Zaznacz.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-156">Click Mark.</span></span>
2. <span data-ttu-id="4a8ad-157">Kliknij opcję Zaznacz jako zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-157">Click Mark as reported.</span></span>
3. <span data-ttu-id="4a8ad-158">Na liście zaznacz wiersz z polem Data faktury.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-158">In the list, select the row for the Invoice date field.</span></span>
4. <span data-ttu-id="4a8ad-159">W polu Kryteria wpisz „01/01/2016..01/31/2016”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-159">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="4a8ad-160">Na liście zaznacz wiersz z polem Stan raportowania.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-160">In the list, select the row for the Reporting status field.</span></span>
6. <span data-ttu-id="4a8ad-161">W polu Kryteria wybierz opcję „Uwzględnione”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-161">In the Criteria field, select 'Included'.</span></span>
    * <span data-ttu-id="4a8ad-162">Można również określić dodatkowe filtry dla wewnątrzwspólnotowych transakcji handlowych w celu ich oznaczenia jako Raportowany.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-162">You can also specify additional filters on intra-community trade transactions to mark as Reported.</span></span>  
7. <span data-ttu-id="4a8ad-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-163">Click OK.</span></span>
8. <span data-ttu-id="4a8ad-164">W polu Wybór wybierz opcję „Raportowany”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-164">In the Selection field, select 'Reported'.</span></span>

## <a name="mark-eu-sales-list-lines-as-closed"></a><span data-ttu-id="4a8ad-165">Oznaczanie wierszy listy sprzedaży do UE jako zamkniętych</span><span class="sxs-lookup"><span data-stu-id="4a8ad-165">Mark EU sales list lines as Closed</span></span>
1. <span data-ttu-id="4a8ad-166">Kliknij opcję Zaznacz.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-166">Click Mark.</span></span>
2. <span data-ttu-id="4a8ad-167">Kliknij opcję Zaznacz jako zamknięty.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-167">Click Mark as closed.</span></span>
3. <span data-ttu-id="4a8ad-168">Na liście zaznacz wiersz z polem Data faktury.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-168">In the list, mark the row for the Invoice date field.</span></span>
4. <span data-ttu-id="4a8ad-169">W polu Kryteria wpisz „01/01/2016..01/31/2016”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-169">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="4a8ad-170">Na liście zaznacz wiersz z polem Stan raportowania.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-170">In the list, mark the row for the Reporting status field.</span></span>
6. <span data-ttu-id="4a8ad-171">W polu Kryteria wybierz opcję „Zgłoszono”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-171">In the Criteria field, select 'Reported'.</span></span>
    * <span data-ttu-id="4a8ad-172">Można również określić dodatkowe filtry dla wewnątrzwspólnotowych transakcji handlowych w celu ich oznaczenia jako Zamknięte.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-172">You can also specify additional filters on intra-community trade transactions to mark as Closed.</span></span>  
7. <span data-ttu-id="4a8ad-173">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-173">Click OK.</span></span>
8. <span data-ttu-id="4a8ad-174">W polu Wybór wybierz opcję „Zamknięte”.</span><span class="sxs-lookup"><span data-stu-id="4a8ad-174">In the Selection field, select 'Closed'.</span></span>

