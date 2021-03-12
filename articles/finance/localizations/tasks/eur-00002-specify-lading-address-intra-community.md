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
ms.openlocfilehash: 634f6cd840262895e6593c12dbe43923598241a5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962489"
---
# <a name="eur-00002-specifying-a-lading-address-for-an-intra-community-transaction"></a><span data-ttu-id="23fe3-103">EUR-00002 Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej</span><span class="sxs-lookup"><span data-stu-id="23fe3-103">EUR-00002 Specifying a lading address for an intra-community transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="23fe3-104">Ta procedura pokazuje, jak określić adres załadunku dla transakcji handlu wewnątrzwspólnotowego.</span><span class="sxs-lookup"><span data-stu-id="23fe3-104">This procedure shows how to specify a lading address for an intra-community trade transaction.</span></span> <span data-ttu-id="23fe3-105">Na przykład niemiecka firma zamawia towary od dostawcy z adresem służbowym w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="23fe3-105">For example, a Germany company orders items from a vendor with a German business address.</span></span> <span data-ttu-id="23fe3-106">Ten dostawca ma magazyn we Włoszech i wysyła towary stamtąd.</span><span class="sxs-lookup"><span data-stu-id="23fe3-106">This vendor has a warehouse in Italy and ships the items from there.</span></span> <span data-ttu-id="23fe3-107">Tę dostawę należy zgłosić w systemie Intrastat.</span><span class="sxs-lookup"><span data-stu-id="23fe3-107">This delivery must be reported in the Intrastat.</span></span> <span data-ttu-id="23fe3-108">To samo zachowanie obowiązuje w przypadku zwrotów od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="23fe3-108">The same behavior is valid for customer returns.</span></span>
<span data-ttu-id="23fe3-109">Ta procedura dotyczy wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="23fe3-109">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="23fe3-110">Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="23fe3-110">The task was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="23fe3-111">Zanim będzie można wykonać tę procedurę, trzeba skonfigurować funkcję raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="23fe3-111">Before you can complete this procedure, you must configure Intrastat reporting.</span></span> <span data-ttu-id="23fe3-112">Procedura jest przeznaczona dla księgowych.</span><span class="sxs-lookup"><span data-stu-id="23fe3-112">This procedure is intended for accountants.</span></span> <span data-ttu-id="23fe3-113">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="23fe3-113">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="23fe3-114">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="23fe3-114">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="23fe3-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="23fe3-115">Click New.</span></span>
3. <span data-ttu-id="23fe3-116">Wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="23fe3-116">Enter or select a value</span></span>
    * <span data-ttu-id="23fe3-117">Na przykład zaznacz DE-001.</span><span class="sxs-lookup"><span data-stu-id="23fe3-117">For example, select DE-001.</span></span> <span data-ttu-id="23fe3-118">Ten dostawca ma adres służbowy w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="23fe3-118">This vendor has a German business address.</span></span>  
4. <span data-ttu-id="23fe3-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="23fe3-119">Click OK.</span></span>
5. <span data-ttu-id="23fe3-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="23fe3-120">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="23fe3-121">W polu Numer towaru wprowadź lub wybierz wartość D0001.</span><span class="sxs-lookup"><span data-stu-id="23fe3-121">In the Item number field, enter or select a value D0001.</span></span>
7. <span data-ttu-id="23fe3-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="23fe3-122">Click Save.</span></span>
8. <span data-ttu-id="23fe3-123">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="23fe3-123">On the Action Pane, click Receive.</span></span>
9. <span data-ttu-id="23fe3-124">Kliknij opcję Szczegóły transportu.</span><span class="sxs-lookup"><span data-stu-id="23fe3-124">Click Transportation details.</span></span>
10. <span data-ttu-id="23fe3-125">W polu Data i godzina ładowania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="23fe3-125">In the Loading date and time field, enter a date and time.</span></span>
11. <span data-ttu-id="23fe3-126">Kliknij opcję Dodaj adres.</span><span class="sxs-lookup"><span data-stu-id="23fe3-126">Click Add address.</span></span>
12. <span data-ttu-id="23fe3-127">Kliknij przycisk Nowy i utwórz nowy adres z celem Załadunek.</span><span class="sxs-lookup"><span data-stu-id="23fe3-127">Click New and create new address with purpose Lading.</span></span>
13. <span data-ttu-id="23fe3-128">W polu Nazwa lub opis wpisz wartość „Włoski”.</span><span class="sxs-lookup"><span data-stu-id="23fe3-128">In the Name or description field, type 'Italian'.</span></span>
14. <span data-ttu-id="23fe3-129">Jako wartość wybierz Załadunek.</span><span class="sxs-lookup"><span data-stu-id="23fe3-129">Select Lading as the value.</span></span>
    * <span data-ttu-id="23fe3-130">Należy zwrócić uwagę, że celem adresu musi być Załadunek.</span><span class="sxs-lookup"><span data-stu-id="23fe3-130">Note that that address purpose must be Lading.</span></span>  
15. <span data-ttu-id="23fe3-131">W polu Kraj/region wprowadź lub wybierz wartość ITA.</span><span class="sxs-lookup"><span data-stu-id="23fe3-131">In the Country/region field, enter or select a value ITA.</span></span>
16. <span data-ttu-id="23fe3-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="23fe3-132">Click Save.</span></span>
17. <span data-ttu-id="23fe3-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="23fe3-133">Close the page.</span></span>
18. <span data-ttu-id="23fe3-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="23fe3-134">Click Save.</span></span>
    * <span data-ttu-id="23fe3-135">Sprawdź poprawność adresu załadunku.</span><span class="sxs-lookup"><span data-stu-id="23fe3-135">Verify that the lading address is correct.</span></span>  
19. <span data-ttu-id="23fe3-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="23fe3-136">Close the page.</span></span>
20. <span data-ttu-id="23fe3-137">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="23fe3-137">On the Action Pane, click Purchase.</span></span>
21. <span data-ttu-id="23fe3-138">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="23fe3-138">Click Confirm.</span></span>
22. <span data-ttu-id="23fe3-139">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="23fe3-139">On the Action Pane, click Invoice.</span></span>
23. <span data-ttu-id="23fe3-140">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="23fe3-140">Click Invoice.</span></span>
24. <span data-ttu-id="23fe3-141">W polu Numer wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="23fe3-141">In the Number field, type a value.</span></span>
25. <span data-ttu-id="23fe3-142">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="23fe3-142">In the Invoice date field, enter a date.</span></span>
26. <span data-ttu-id="23fe3-143">Na liście Domyślnie z zaznacz opcję Ilość z dokumentu przyjęcia produktów, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="23fe3-143">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
27. <span data-ttu-id="23fe3-144">W polu Domyślna ilość dla wierszy zaznacz wartość „Ilość zamówiona”.</span><span class="sxs-lookup"><span data-stu-id="23fe3-144">In the Default quantity for lines field, select 'Ordered quantity'.</span></span>
28. <span data-ttu-id="23fe3-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="23fe3-145">Click OK.</span></span>
29. <span data-ttu-id="23fe3-146">Kliknij opcję Szczegóły transportu.</span><span class="sxs-lookup"><span data-stu-id="23fe3-146">Click Transportation details.</span></span>
    * <span data-ttu-id="23fe3-147">Sprawdź, czy towary zostały wysłane z Włoch.</span><span class="sxs-lookup"><span data-stu-id="23fe3-147">Verify that goods were shipped from Italy.</span></span> <span data-ttu-id="23fe3-148">W razie potrzeby można edytować szczegóły załadunku.</span><span class="sxs-lookup"><span data-stu-id="23fe3-148">If necessary, you can edit the lading details.</span></span>  
30. <span data-ttu-id="23fe3-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="23fe3-149">Close the page.</span></span>
31. <span data-ttu-id="23fe3-150">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="23fe3-150">Click Post.</span></span>
32. <span data-ttu-id="23fe3-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="23fe3-151">Close the page.</span></span>
33. <span data-ttu-id="23fe3-152">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="23fe3-152">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
34. <span data-ttu-id="23fe3-153">Kliknij przycisk Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="23fe3-153">Click Transfer.</span></span>
35. <span data-ttu-id="23fe3-154">W polu Faktura dostawcy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="23fe3-154">Select Yes in the Vendor invoice field.</span></span>
36. <span data-ttu-id="23fe3-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="23fe3-155">Click OK.</span></span>
37. <span data-ttu-id="23fe3-156">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="23fe3-156">Click the General tab.</span></span>
    * <span data-ttu-id="23fe3-157">Znajdź nowo utworzony wiersz i upewnij się, że nadawca wysłał towary z Włoch.</span><span class="sxs-lookup"><span data-stu-id="23fe3-157">Find a newly created line and verify that the sender shipped the goods from Italy.</span></span>  

