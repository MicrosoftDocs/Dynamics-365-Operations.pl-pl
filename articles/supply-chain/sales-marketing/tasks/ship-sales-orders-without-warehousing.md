---
title: Wysyłanie towarów z zamówień sprzedaży bez przekazywania do magazynu
description: W tym podręczniku zilustrowano sposób aktualizacji zamówienia sprzedaży, gdy produkty są wysyłane do odbiorcy.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae70e09dbc4da90b7d1802d076384eae2d00da0e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555800"
---
# <a name="ship-sales-orders-without-warehousing"></a><span data-ttu-id="8c725-103">Wysyłanie towarów z zamówień sprzedaży bez przekazywania do magazynu</span><span class="sxs-lookup"><span data-stu-id="8c725-103">Ship sales orders without warehousing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8c725-104">W tym podręczniku zilustrowano sposób aktualizacji zamówienia sprzedaży, gdy produkty są wysyłane do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="8c725-104">This guide demonstrates how to update a sales order when products are shipped to the customer.</span></span> <span data-ttu-id="8c725-105">Przewodnik ma zastosowanie do przepływu realizacji, który nie jest skonfigurowany dla zarządzania magazynem (podstawowego ani zaawansowanego), a zatem nie wymaga, aby przed wysyłką zostało zarejestrowane pobranie produktu.</span><span class="sxs-lookup"><span data-stu-id="8c725-105">The guide is applicable to the fulfillment flow that is not set up for warehouse management (neither basic or advanced warehousing), and therefore does not require product picking to be registered before shipment.</span></span> <span data-ttu-id="8c725-106">Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="8c725-106">You can run this procedure on your own data or in demo data company USMF.</span></span> <span data-ttu-id="8c725-107">W obu przypadkach przed rozpoczęciem tego zadania utwórz zamówienie sprzedaży na produkty magazynowe z ilością większą od 1.</span><span class="sxs-lookup"><span data-stu-id="8c725-107">In both cases, before you start this task, create a sales order for an inventoried product with a quantity of greater than 1.</span></span> <span data-ttu-id="8c725-108">Aby uniknąć błędu księgowania, należy sprawdzić, czy ilość dostępnych zapasów produktu w oddziale i magazynie wybranych w zamówieniu pokrywa ilość zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8c725-108">To avoid a posting error, you need to check that the product's on-hand quantity in the site and warehouse that you’ve selected on the order covers the order quantity.</span></span>


## <a name="post-packing-slip-for-an-order"></a><span data-ttu-id="8c725-109">Księgowanie dokumentu dostawy dla zamówienia</span><span class="sxs-lookup"><span data-stu-id="8c725-109">Post packing slip for an order</span></span>
1. <span data-ttu-id="8c725-110">Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8c725-110">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="8c725-111">Na liście znajdź i zaznacz zamówienie utworzone dla tego zadania.</span><span class="sxs-lookup"><span data-stu-id="8c725-111">In the list, find and select the order you have created for this task.</span></span>
3. <span data-ttu-id="8c725-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8c725-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8c725-113">W okienku akcji kliknij opcję Pobierz i zapakuj.</span><span class="sxs-lookup"><span data-stu-id="8c725-113">On the Action Pane, click Pick and pack.</span></span>
5. <span data-ttu-id="8c725-114">Kliknij opcję Księguj dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="8c725-114">Click Post packing slip.</span></span>
6. <span data-ttu-id="8c725-115">Rozwiń lub zwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="8c725-115">Expand or collapse the Parameters section.</span></span>
7. <span data-ttu-id="8c725-116">W polu Ilość zaznacz opcję Wszystko.</span><span class="sxs-lookup"><span data-stu-id="8c725-116">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="8c725-117">Inne dostępne opcje to Dostawa teraz i Pobrane.</span><span class="sxs-lookup"><span data-stu-id="8c725-117">Other options include Deliver now and Picked.</span></span> <span data-ttu-id="8c725-118">Jeśli towary z wiersza zamówienia mają zostać wysłane częściowo, a w wierszu zamówienia pole Dostawa teraz zawiera ilość, należałoby zaznaczyć opcję Dostawa teraz.</span><span class="sxs-lookup"><span data-stu-id="8c725-118">If the order line is to be shipped partially and the Deliver now field on the order line contains a quantity, you would select Deliver now.</span></span> <span data-ttu-id="8c725-119">Jeśli przepływ realizacji w firmie obejmuje pobranie jako oddzielny proces zarządzany i rejestrowany za pomocą listy pobrania, należałoby wybrać opcję Pobrane.</span><span class="sxs-lookup"><span data-stu-id="8c725-119">If your organization's fulfillment flow includes picking as a separate process that is managed by and registered with a picking list, you would select Picked.</span></span>  
    * <span data-ttu-id="8c725-120">Sprawdź, czy w opcji Księgowanie jest ustawiona wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="8c725-120">Check that the Posting option is set to Yes.</span></span>  
8. <span data-ttu-id="8c725-121">W opcji Drukowanie dokumentu dostawy zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="8c725-121">Set the Print packing slip option to Yes.</span></span>
    * <span data-ttu-id="8c725-122">Karta Przegląd zawiera listę dokumentów dostawy, jakie mają zostać wygenerowane w tym księgowaniu.</span><span class="sxs-lookup"><span data-stu-id="8c725-122">The Overview tab contains a list of packing slips to be generated in this posting.</span></span> <span data-ttu-id="8c725-123">Jeśli wysyłasz towary z jednego zamówienia, zwykle będzie jeden dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="8c725-123">If you are shipping an individual order, there will typically be one packing slip.</span></span> <span data-ttu-id="8c725-124">Jeśli jednak wiersze tego zamówienia mają być wysyłane z różnych oddziałów, księgowanie będzie automatycznie dzielone na odpowiednią liczbę dokumentów.</span><span class="sxs-lookup"><span data-stu-id="8c725-124">However, if that order's lines are to be shipped from different sites, posting will automatically be split into the appropriate number of documents.</span></span> <span data-ttu-id="8c725-125">To jest obowiązkowy warunek, którego nie można zmieniać.</span><span class="sxs-lookup"><span data-stu-id="8c725-125">This is a mandatory condition that cannot be changed.</span></span> <span data-ttu-id="8c725-126">Podobnie księgowanie zostanie podzielone na wiele dokumentów, jeśli wiersze zamówienia mają zostać wysłane pod różne adresy dostawy, a zasady wysyłki określają wymaganie podziału.</span><span class="sxs-lookup"><span data-stu-id="8c725-126">Similarly, the posting will also be split into multiple documents if the order’s lines are to be shipped to different delivery addresses, and the shipping policy is set up to require a split.</span></span>  
9. <span data-ttu-id="8c725-127">Na karcie Wiersze zaznacz wiersz dla wiersza zamówienia, który ma zostać wysłany.</span><span class="sxs-lookup"><span data-stu-id="8c725-127">On the Lines tab, select the row for the order line to be shipped.</span></span>
10. <span data-ttu-id="8c725-128">W polu Aktualizacja wprowadź liczbę mniejszą niż ilość oryginalna.</span><span class="sxs-lookup"><span data-stu-id="8c725-128">In the Update field, enter a number lower than the original quantity.</span></span>
11. <span data-ttu-id="8c725-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8c725-129">Click OK.</span></span>
12. <span data-ttu-id="8c725-130">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="8c725-130">Click Yes.</span></span>
13. <span data-ttu-id="8c725-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8c725-131">Close the page.</span></span>
14. <span data-ttu-id="8c725-132">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="8c725-132">On the Action Pane, click Options.</span></span>
15. <span data-ttu-id="8c725-133">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="8c725-133">Click Change view.</span></span>
16. <span data-ttu-id="8c725-134">Kliknij opcję Widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="8c725-134">Click Header view.</span></span>
    * <span data-ttu-id="8c725-135">Gdy wszystkie wiersze zamówienia zostaną całkowicie wydane, stan zamówienia zmienia się z Otwarte na Dostarczone.</span><span class="sxs-lookup"><span data-stu-id="8c725-135">If all of the lines on the order have been fully shipped, the order status changes from Open to Delivered.</span></span>  
    * <span data-ttu-id="8c725-136">W tym przykładzie wiersz zamówienia został wysłany częściowo.</span><span class="sxs-lookup"><span data-stu-id="8c725-136">In this example, the order line has been shipped partially.</span></span> <span data-ttu-id="8c725-137">Dlatego zamówienie pozostaje w stanie Otwarte.</span><span class="sxs-lookup"><span data-stu-id="8c725-137">This is why the the order status remains Open.</span></span>     
    * <span data-ttu-id="8c725-138">W polu Stan dokumentu jest ustawiona wartość Dokument dostawy, ponieważ co najmniej jeden wiersz zamówienia został wysłany.</span><span class="sxs-lookup"><span data-stu-id="8c725-138">The Document status field is set to Packing slip because at least one of the order lines have been shipped.</span></span>  
17. <span data-ttu-id="8c725-139">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="8c725-139">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="8c725-140">Kliknij opcję Ilość w wierszu.</span><span class="sxs-lookup"><span data-stu-id="8c725-140">Click Line quantity.</span></span>
19. <span data-ttu-id="8c725-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8c725-141">Close the page.</span></span>
20. <span data-ttu-id="8c725-142">W okienku akcji kliknij opcję Pobierz i zapakuj.</span><span class="sxs-lookup"><span data-stu-id="8c725-142">On the Action Pane, click Pick and pack.</span></span>
21. <span data-ttu-id="8c725-143">Kliknij opcję Dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="8c725-143">Click Packing slip.</span></span>
    * <span data-ttu-id="8c725-144">Strona Arkusz dokumentu dostawy zawiera wszystkie dokumenty dostawy, które zostały wygenerowane dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8c725-144">The Packing slip journal page contains all the packing slip documents that were generated for your order.</span></span> <span data-ttu-id="8c725-145">W razie potrzeby można przejrzeć szczegóły każdego dokumentu i je wydrukować.</span><span class="sxs-lookup"><span data-stu-id="8c725-145">You can review details of each document and print them, if you wish.</span></span>  

