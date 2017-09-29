--- 
title: "Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej"
description: "Ta procedura pokazuje, jak określić adres załadunku dla transakcji handlu wewnątrzwspólnotowego."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fc54b59f6cf8aec8d489955c57cbcf34c4e6be0a
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="specify-a-lading-address-for-an-intra-community-transaction"></a><span data-ttu-id="8eb93-103">Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej</span><span class="sxs-lookup"><span data-stu-id="8eb93-103">Specify a lading address for an intra-community transaction</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8eb93-104">Ta procedura pokazuje, jak określić adres załadunku dla transakcji handlu wewnątrzwspólnotowego.</span><span class="sxs-lookup"><span data-stu-id="8eb93-104">This procedure shows how to specify a lading address for an intra-community trade transaction.</span></span> <span data-ttu-id="8eb93-105">Na przykład niemiecka firma zamawia towary od dostawcy z adresem służbowym w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="8eb93-105">For example, a Germany company orders items from a vendor with a German business address.</span></span> <span data-ttu-id="8eb93-106">Ten dostawca ma magazyn we Włoszech i wysyła towary stamtąd.</span><span class="sxs-lookup"><span data-stu-id="8eb93-106">This vendor has a warehouse in Italy and ships the items from there.</span></span> <span data-ttu-id="8eb93-107">Tę dostawę należy zgłosić w systemie Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8eb93-107">This delivery must be reported in the Intrastat.</span></span> <span data-ttu-id="8eb93-108">To samo zachowanie obowiązuje w przypadku zwrotów od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="8eb93-108">The same behavior is valid for customer returns.</span></span>
<span data-ttu-id="8eb93-109">Ta procedura dotyczy wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="8eb93-109">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="8eb93-110">Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="8eb93-110">The task was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="8eb93-111">Zanim będzie można wykonać tę procedurę, trzeba skonfigurować funkcję raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8eb93-111">Before you can complete this procedure, you must configure Intrastat reporting.</span></span> <span data-ttu-id="8eb93-112">Procedura jest przeznaczona dla księgowych.</span><span class="sxs-lookup"><span data-stu-id="8eb93-112">This procedure is intended for accountants.</span></span> <span data-ttu-id="8eb93-113">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="8eb93-113">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="8eb93-114">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="8eb93-114">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="8eb93-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8eb93-115">Click New.</span></span>
3. <span data-ttu-id="8eb93-116">Wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8eb93-116">Enter or select a value</span></span>
    * <span data-ttu-id="8eb93-117">Na przykład zaznacz DE-001.</span><span class="sxs-lookup"><span data-stu-id="8eb93-117">For example, select DE-001.</span></span> <span data-ttu-id="8eb93-118">Ten dostawca ma adres służbowy w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="8eb93-118">This vendor has a German business address.</span></span>  
4. <span data-ttu-id="8eb93-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8eb93-119">Click OK.</span></span>
5. <span data-ttu-id="8eb93-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="8eb93-120">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="8eb93-121">W polu Numer towaru wprowadź lub wybierz wartość D0001.</span><span class="sxs-lookup"><span data-stu-id="8eb93-121">In the Item number field, enter or select a value D0001.</span></span>
7. <span data-ttu-id="8eb93-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8eb93-122">Click Save.</span></span>
8. <span data-ttu-id="8eb93-123">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="8eb93-123">On the Action Pane, click Receive.</span></span>
9. <span data-ttu-id="8eb93-124">Kliknij opcję Szczegóły transportu.</span><span class="sxs-lookup"><span data-stu-id="8eb93-124">Click Transportation details.</span></span>
10. <span data-ttu-id="8eb93-125">W polu Data i godzina ładowania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="8eb93-125">In the Loading date and time field, enter a date and time.</span></span>
11. <span data-ttu-id="8eb93-126">Kliknij opcję Dodaj adres.</span><span class="sxs-lookup"><span data-stu-id="8eb93-126">Click Add address.</span></span>
12. <span data-ttu-id="8eb93-127">Kliknij przycisk Nowy i utwórz nowy adres z celem Załadunek.</span><span class="sxs-lookup"><span data-stu-id="8eb93-127">Click New and create new address with purpose Lading.</span></span>
13. <span data-ttu-id="8eb93-128">W polu Nazwa lub opis wpisz wartość „Włoski”.</span><span class="sxs-lookup"><span data-stu-id="8eb93-128">In the Name or description field, type 'Italian'.</span></span>
14. <span data-ttu-id="8eb93-129">Jako wartość wybierz Załadunek.</span><span class="sxs-lookup"><span data-stu-id="8eb93-129">Select Lading as the value.</span></span>
    * <span data-ttu-id="8eb93-130">Należy zwrócić uwagę, że celem adresu musi być Załadunek.</span><span class="sxs-lookup"><span data-stu-id="8eb93-130">Note that that address purpose must be Lading.</span></span>  
15. <span data-ttu-id="8eb93-131">W polu Kraj/region wprowadź lub wybierz wartość ITA.</span><span class="sxs-lookup"><span data-stu-id="8eb93-131">In the Country/region field, enter or select a value ITA.</span></span>
16. <span data-ttu-id="8eb93-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8eb93-132">Click Save.</span></span>
17. <span data-ttu-id="8eb93-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8eb93-133">Close the page.</span></span>
18. <span data-ttu-id="8eb93-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8eb93-134">Click Save.</span></span>
    * <span data-ttu-id="8eb93-135">Sprawdź poprawność adresu załadunku.</span><span class="sxs-lookup"><span data-stu-id="8eb93-135">Verify that the lading address is correct.</span></span>  
19. <span data-ttu-id="8eb93-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8eb93-136">Close the page.</span></span>
20. <span data-ttu-id="8eb93-137">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="8eb93-137">On the Action Pane, click Purchase.</span></span>
21. <span data-ttu-id="8eb93-138">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="8eb93-138">Click Confirm.</span></span>
22. <span data-ttu-id="8eb93-139">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="8eb93-139">On the Action Pane, click Invoice.</span></span>
23. <span data-ttu-id="8eb93-140">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="8eb93-140">Click Invoice.</span></span>
24. <span data-ttu-id="8eb93-141">W polu Numer wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8eb93-141">In the Number field, type a value.</span></span>
25. <span data-ttu-id="8eb93-142">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="8eb93-142">In the Invoice date field, enter a date.</span></span>
26. <span data-ttu-id="8eb93-143">Na liście Domyślnie z zaznacz opcję Ilość z dokumentu przyjęcia produktów, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="8eb93-143">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
27. <span data-ttu-id="8eb93-144">W polu Domyślna ilość dla wierszy zaznacz wartość „Ilość zamówiona”.</span><span class="sxs-lookup"><span data-stu-id="8eb93-144">In the Default quantity for lines field, select 'Ordered quantity'.</span></span>
28. <span data-ttu-id="8eb93-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8eb93-145">Click OK.</span></span>
29. <span data-ttu-id="8eb93-146">Kliknij opcję Szczegóły transportu.</span><span class="sxs-lookup"><span data-stu-id="8eb93-146">Click Transportation details.</span></span>
    * <span data-ttu-id="8eb93-147">Sprawdź, czy towary zostały wysłane z Włoch.</span><span class="sxs-lookup"><span data-stu-id="8eb93-147">Verify that goods were shipped from Italy.</span></span> <span data-ttu-id="8eb93-148">W razie potrzeby można edytować szczegóły załadunku.</span><span class="sxs-lookup"><span data-stu-id="8eb93-148">If necessary, you can edit the lading details.</span></span>  
30. <span data-ttu-id="8eb93-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8eb93-149">Close the page.</span></span>
31. <span data-ttu-id="8eb93-150">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="8eb93-150">Click Post.</span></span>
32. <span data-ttu-id="8eb93-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8eb93-151">Close the page.</span></span>
33. <span data-ttu-id="8eb93-152">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8eb93-152">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
34. <span data-ttu-id="8eb93-153">Kliknij przycisk Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="8eb93-153">Click Transfer.</span></span>
35. <span data-ttu-id="8eb93-154">W polu Faktura dostawcy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="8eb93-154">Select Yes in the Vendor invoice field.</span></span>
36. <span data-ttu-id="8eb93-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8eb93-155">Click OK.</span></span>
37. <span data-ttu-id="8eb93-156">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="8eb93-156">Click the General tab.</span></span>
    * <span data-ttu-id="8eb93-157">Znajdź nowo utworzony wiersz i upewnij się, że nadawca wysłał towary z Włoch.</span><span class="sxs-lookup"><span data-stu-id="8eb93-157">Find a newly created line and verify that the sender shipped the goods from Italy.</span></span>  


