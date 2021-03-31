---
title: EUR-00002 Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej
description: Ta procedura pokazuje, jak określić adres załadunku dla transakcji handlu wewnątrzwspólnotowego.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, TransportationDocument, LogisticsPostalAddress, SysLookupMultiSelectGrid,  VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9b657629e53488bbac222428cdb88c21deb2847c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228000"
---
# <a name="eur-00002-specifying-a-lading-address-for-an-intra-community-transaction"></a><span data-ttu-id="e7a06-103">EUR-00002 Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej</span><span class="sxs-lookup"><span data-stu-id="e7a06-103">EUR-00002 Specifying a lading address for an intra-community transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e7a06-104">Ta procedura pokazuje, jak określić adres załadunku dla transakcji handlu wewnątrzwspólnotowego.</span><span class="sxs-lookup"><span data-stu-id="e7a06-104">This procedure shows how to specify a lading address for an intra-community trade transaction.</span></span> <span data-ttu-id="e7a06-105">Na przykład niemiecka firma zamawia towary od dostawcy z adresem służbowym w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="e7a06-105">For example, a Germany company orders items from a vendor with a German business address.</span></span> <span data-ttu-id="e7a06-106">Ten dostawca ma magazyn we Włoszech i wysyła towary stamtąd.</span><span class="sxs-lookup"><span data-stu-id="e7a06-106">This vendor has a warehouse in Italy and ships the items from there.</span></span> <span data-ttu-id="e7a06-107">Tę dostawę należy zgłosić w systemie Intrastat.</span><span class="sxs-lookup"><span data-stu-id="e7a06-107">This delivery must be reported in the Intrastat.</span></span> <span data-ttu-id="e7a06-108">To samo zachowanie obowiązuje w przypadku zwrotów od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="e7a06-108">The same behavior is valid for customer returns.</span></span>
<span data-ttu-id="e7a06-109">Ta procedura dotyczy wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="e7a06-109">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="e7a06-110">Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="e7a06-110">The task was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="e7a06-111">Zanim będzie można wykonać tę procedurę, trzeba skonfigurować funkcję raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="e7a06-111">Before you can complete this procedure, you must configure Intrastat reporting.</span></span> <span data-ttu-id="e7a06-112">Procedura jest przeznaczona dla księgowych.</span><span class="sxs-lookup"><span data-stu-id="e7a06-112">This procedure is intended for accountants.</span></span> <span data-ttu-id="e7a06-113">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="e7a06-113">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="e7a06-114">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="e7a06-114">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="e7a06-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e7a06-115">Click New.</span></span>
3. <span data-ttu-id="e7a06-116">Wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e7a06-116">Enter or select a value</span></span>
    * <span data-ttu-id="e7a06-117">Na przykład zaznacz DE-001.</span><span class="sxs-lookup"><span data-stu-id="e7a06-117">For example, select DE-001.</span></span> <span data-ttu-id="e7a06-118">Ten dostawca ma adres służbowy w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="e7a06-118">This vendor has a German business address.</span></span>  
4. <span data-ttu-id="e7a06-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e7a06-119">Click OK.</span></span>
5. <span data-ttu-id="e7a06-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e7a06-120">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="e7a06-121">W polu Numer towaru wprowadź lub wybierz wartość D0001.</span><span class="sxs-lookup"><span data-stu-id="e7a06-121">In the Item number field, enter or select a value D0001.</span></span>
7. <span data-ttu-id="e7a06-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e7a06-122">Click Save.</span></span>
8. <span data-ttu-id="e7a06-123">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="e7a06-123">On the Action Pane, click Receive.</span></span>
9. <span data-ttu-id="e7a06-124">Kliknij opcję Szczegóły transportu.</span><span class="sxs-lookup"><span data-stu-id="e7a06-124">Click Transportation details.</span></span>
10. <span data-ttu-id="e7a06-125">W polu Data i godzina ładowania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="e7a06-125">In the Loading date and time field, enter a date and time.</span></span>
11. <span data-ttu-id="e7a06-126">Kliknij opcję Dodaj adres.</span><span class="sxs-lookup"><span data-stu-id="e7a06-126">Click Add address.</span></span>
12. <span data-ttu-id="e7a06-127">Kliknij przycisk Nowy i utwórz nowy adres z celem Załadunek.</span><span class="sxs-lookup"><span data-stu-id="e7a06-127">Click New and create new address with purpose Lading.</span></span>
13. <span data-ttu-id="e7a06-128">W polu Nazwa lub opis wpisz wartość „Włoski”.</span><span class="sxs-lookup"><span data-stu-id="e7a06-128">In the Name or description field, type 'Italian'.</span></span>
14. <span data-ttu-id="e7a06-129">Jako wartość wybierz Załadunek.</span><span class="sxs-lookup"><span data-stu-id="e7a06-129">Select Lading as the value.</span></span>
    * <span data-ttu-id="e7a06-130">Należy zwrócić uwagę, że celem adresu musi być Załadunek.</span><span class="sxs-lookup"><span data-stu-id="e7a06-130">Note that that address purpose must be Lading.</span></span>  
15. <span data-ttu-id="e7a06-131">W polu Kraj/region wprowadź lub wybierz wartość ITA.</span><span class="sxs-lookup"><span data-stu-id="e7a06-131">In the Country/region field, enter or select a value ITA.</span></span>
16. <span data-ttu-id="e7a06-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e7a06-132">Click Save.</span></span>
17. <span data-ttu-id="e7a06-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e7a06-133">Close the page.</span></span>
18. <span data-ttu-id="e7a06-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e7a06-134">Click Save.</span></span>
    * <span data-ttu-id="e7a06-135">Sprawdź poprawność adresu załadunku.</span><span class="sxs-lookup"><span data-stu-id="e7a06-135">Verify that the lading address is correct.</span></span>  
19. <span data-ttu-id="e7a06-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e7a06-136">Close the page.</span></span>
20. <span data-ttu-id="e7a06-137">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="e7a06-137">On the Action Pane, click Purchase.</span></span>
21. <span data-ttu-id="e7a06-138">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="e7a06-138">Click Confirm.</span></span>
22. <span data-ttu-id="e7a06-139">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="e7a06-139">On the Action Pane, click Invoice.</span></span>
23. <span data-ttu-id="e7a06-140">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="e7a06-140">Click Invoice.</span></span>
24. <span data-ttu-id="e7a06-141">W polu Numer wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e7a06-141">In the Number field, type a value.</span></span>
25. <span data-ttu-id="e7a06-142">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="e7a06-142">In the Invoice date field, enter a date.</span></span>
26. <span data-ttu-id="e7a06-143">Na liście Domyślnie z zaznacz opcję Ilość z dokumentu przyjęcia produktów, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="e7a06-143">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
27. <span data-ttu-id="e7a06-144">W polu Domyślna ilość dla wierszy zaznacz wartość „Ilość zamówiona”.</span><span class="sxs-lookup"><span data-stu-id="e7a06-144">In the Default quantity for lines field, select 'Ordered quantity'.</span></span>
28. <span data-ttu-id="e7a06-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e7a06-145">Click OK.</span></span>
29. <span data-ttu-id="e7a06-146">Kliknij opcję Szczegóły transportu.</span><span class="sxs-lookup"><span data-stu-id="e7a06-146">Click Transportation details.</span></span>
    * <span data-ttu-id="e7a06-147">Sprawdź, czy towary zostały wysłane z Włoch.</span><span class="sxs-lookup"><span data-stu-id="e7a06-147">Verify that goods were shipped from Italy.</span></span> <span data-ttu-id="e7a06-148">W razie potrzeby można edytować szczegóły załadunku.</span><span class="sxs-lookup"><span data-stu-id="e7a06-148">If necessary, you can edit the lading details.</span></span>  
30. <span data-ttu-id="e7a06-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e7a06-149">Close the page.</span></span>
31. <span data-ttu-id="e7a06-150">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="e7a06-150">Click Post.</span></span>
32. <span data-ttu-id="e7a06-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e7a06-151">Close the page.</span></span>
33. <span data-ttu-id="e7a06-152">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="e7a06-152">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
34. <span data-ttu-id="e7a06-153">Kliknij przycisk Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="e7a06-153">Click Transfer.</span></span>
35. <span data-ttu-id="e7a06-154">W polu Faktura dostawcy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e7a06-154">Select Yes in the Vendor invoice field.</span></span>
36. <span data-ttu-id="e7a06-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e7a06-155">Click OK.</span></span>
37. <span data-ttu-id="e7a06-156">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="e7a06-156">Click the General tab.</span></span>
    * <span data-ttu-id="e7a06-157">Znajdź nowo utworzony wiersz i upewnij się, że nadawca wysłał towary z Włoch.</span><span class="sxs-lookup"><span data-stu-id="e7a06-157">Find a newly created line and verify that the sender shipped the goods from Italy.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]