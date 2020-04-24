---
title: Realizacja umów sprzedaży
description: W tej procedurze pokazano, jak zrealizować zamówienie sprzedaży poprzez skojarzenie z nim umowy sprzedaży.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51ea8afc7c2f683790f697185d6637e0d24462fc
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204316"
---
# <a name="fulfill-sales-agreements"></a><span data-ttu-id="4c090-103">Realizacja umów sprzedaży</span><span class="sxs-lookup"><span data-stu-id="4c090-103">Fulfill sales agreements</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4c090-104">W tej procedurze pokazano, jak zrealizować zamówienie sprzedaży poprzez skojarzenie z nim umowy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-104">This procedure shows you how to fulfill a sales agreement by associating sales orders with it.</span></span> <span data-ttu-id="4c090-105">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="4c090-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="4c090-106">Przed rozpoczęciem tego przewodnika upewnij się, że masz obowiązującą umowę sprzedaży typu „Zobowiązanie co do wartości produktu”.</span><span class="sxs-lookup"><span data-stu-id="4c090-106">Before starting this guide, make sure you have an effective sales agreement of type "Product value commitment".</span></span> <span data-ttu-id="4c090-107">Można także uruchomić przewodnik po zadaniach o nazwie „Tworzenie umów sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="4c090-107">Alternatively, you can run the task guide called "Create sales agreements".</span></span>  




## <a name="release-a-sales-order-from-the-agreement"></a><span data-ttu-id="4c090-108">Zwalnianie zamówienia sprzedaży z poziomu umowy</span><span class="sxs-lookup"><span data-stu-id="4c090-108">Release a sales order from the agreement</span></span>
1. <span data-ttu-id="4c090-109">Wybierz kolejno opcje Sprzedaż i marketing > Umowy sprzedaży > Umowy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-109">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="4c090-110">Na liście otwórz umowę, dla której chcesz zwolnić zamówienie.</span><span class="sxs-lookup"><span data-stu-id="4c090-110">In the list, open the agreement against which you want to release the order.</span></span>
3. <span data-ttu-id="4c090-111">W okienku akcji kliknij opcję Umowa sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-111">On the Action Pane, click Sales agreement.</span></span>
4. <span data-ttu-id="4c090-112">Kliknij opcję Zwolnij zamówienie.</span><span class="sxs-lookup"><span data-stu-id="4c090-112">Click Release order.</span></span>
    * <span data-ttu-id="4c090-113">Jak wskazuje tekst u góry strony Tworzenie zlecenia wydania, szczegóły wymagane w wierszach zamówienia sprzedaży będą się różnić w zależności od tego, czy umowa jest oparta na ilości czy wartości.</span><span class="sxs-lookup"><span data-stu-id="4c090-113">As the text on top of the  Create release order page points out, the details required for the sales order lines will differ depending on whether the agreement is quantity- or value-based.</span></span>  
    * <span data-ttu-id="4c090-114">Umowy w tym przewodniku jest typu „Zobowiązanie co do wartości produktu”.</span><span class="sxs-lookup"><span data-stu-id="4c090-114">The agreement in this guide is of type "Product value commitment".</span></span> <span data-ttu-id="4c090-115">To dlatego na tej stronie sekcja Wiersze jest pusta.</span><span class="sxs-lookup"><span data-stu-id="4c090-115">This is why the Lines section of this page is blank.</span></span> <span data-ttu-id="4c090-116">Gdyby zobowiązanie było oparte na ilości, informacje w wierszach zostałyby skopiowane z umowy.</span><span class="sxs-lookup"><span data-stu-id="4c090-116">If the commitment was based on quantity, the line information would be copied from the agreement.</span></span>  
5. <span data-ttu-id="4c090-117">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="4c090-117">Click Create.</span></span>
    * <span data-ttu-id="4c090-118">Komunikat informuje, że zamówienia sprzedaży zostało utworzone.</span><span class="sxs-lookup"><span data-stu-id="4c090-118">The message informs you that a sales order has been created.</span></span> <span data-ttu-id="4c090-119">Ponieważ zamówienie nie zawiera żadnych wierszy, w celu ukończenia procesu zwalniania należy dodać szczegóły wierszy zamówienia.</span><span class="sxs-lookup"><span data-stu-id="4c090-119">Since the order does not contain any lines, you must add order line details to complete the release process.</span></span>   
6. <span data-ttu-id="4c090-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c090-120">Close the page.</span></span>
7. <span data-ttu-id="4c090-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c090-121">Close the page.</span></span>
8. <span data-ttu-id="4c090-122">Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-122">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
9. <span data-ttu-id="4c090-123">Na liście znajdź i otwórz zamówienie, które zostało utworzone w wyniku zwolnienia zamówienia w poprzednim zadaniu.</span><span class="sxs-lookup"><span data-stu-id="4c090-123">In the list, find and open the order that was created as the result of the order release in the previous task.</span></span>
10. <span data-ttu-id="4c090-124">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="4c090-124">Click Add line.</span></span>
11. <span data-ttu-id="4c090-125">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="4c090-125">In the Item number field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="4c090-126">W polu Numer towaru wpisz lub wybierz towar, który znajduje się w skojarzonej umowie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-126">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
13. <span data-ttu-id="4c090-127">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="4c090-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="4c090-128">Upewnij się, że wprowadzisz taką ilość, że pole Kwota netto będzie zawierało wartość niższą niż w skojarzonej umowie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-128">Make sure that you enter a quantity that brings the Net amount under the value of the associated sales agreement.</span></span>  
    * <span data-ttu-id="4c090-129">Należy zauważyć, że ponieważ zamówienie sprzedaży jest połączone z umową, wynegocjowany procent rabatu jest stosowany do wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="4c090-129">Notice that because the sales order is linked to the agreement, the negotiated discount percent is applied to the order line.</span></span>  
14. <span data-ttu-id="4c090-130">Kliknij opcję Aktualizuj wiersz.</span><span class="sxs-lookup"><span data-stu-id="4c090-130">Click Update line.</span></span>
15. <span data-ttu-id="4c090-131">Kliknij opcję Powiązany.</span><span class="sxs-lookup"><span data-stu-id="4c090-131">Click Attached.</span></span>
    * <span data-ttu-id="4c090-132">Strona Dołączona umowa zawiera identyfikator i warunki umowy, z której wiersz jest zwalniany.</span><span class="sxs-lookup"><span data-stu-id="4c090-132">The Attached agreement page shows the ID and terms of the agreement from which the line is released.</span></span>  
16. <span data-ttu-id="4c090-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c090-133">Close the page.</span></span>
17. <span data-ttu-id="4c090-134">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="4c090-134">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="4c090-135">Kliknij opcję Dołączona umowa sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-135">Click Attached sales agreement.</span></span>
19. <span data-ttu-id="4c090-136">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="4c090-136">Expand the Line details section.</span></span>
20. <span data-ttu-id="4c090-137">Kliknij kartę Realizacja.</span><span class="sxs-lookup"><span data-stu-id="4c090-137">Click the Fulfillment tab.</span></span>
    * <span data-ttu-id="4c090-138">Karta Realizacja zawiera podsumowanie wszystkich wierszy zamówienia sprzedaży, które są skojarzone z tym zobowiązaniem, oraz ich stany realizacji, a także kwotę lub ilość, która nie została jeszcze zwolniona.</span><span class="sxs-lookup"><span data-stu-id="4c090-138">The Fulfillment tab shows a summary of all the sales order lines that are associated with this commitment, and their fulfillment state, as well as the amount or quantity that has not yet been released.</span></span>   
21. <span data-ttu-id="4c090-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c090-139">Close the page.</span></span>
22. <span data-ttu-id="4c090-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c090-140">Close the page.</span></span>
23. <span data-ttu-id="4c090-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c090-141">Close the page.</span></span>

## <a name="apply-sales-agreement-in-the-order-process"></a><span data-ttu-id="4c090-142">Stosowanie umowy sprzedaży w procesie zamawiania</span><span class="sxs-lookup"><span data-stu-id="4c090-142">Apply sales agreement in the order process</span></span>
1. <span data-ttu-id="4c090-143">Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-143">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="4c090-144">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4c090-144">Click New.</span></span>
3. <span data-ttu-id="4c090-145">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="4c090-145">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="4c090-146">Na liście znajdź i wybierz odbiorcę podanego w umowie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-146">In the list, find and select the customer specified on the sales agreement.</span></span>
5. <span data-ttu-id="4c090-147">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c090-147">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4c090-148">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="4c090-148">Expand the General section.</span></span>
7. <span data-ttu-id="4c090-149">W polu Identyfikator umowy sprzedaży kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="4c090-149">In the Sales agreement ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="4c090-150">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c090-150">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="4c090-151">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="4c090-151">Click Yes.</span></span>
10. <span data-ttu-id="4c090-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c090-152">Click OK.</span></span>
11. <span data-ttu-id="4c090-153">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="4c090-153">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="4c090-154">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="4c090-154">In the Item number field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="4c090-155">W polu Numer towaru wpisz lub wybierz towar, który znajduje się w skojarzonej umowie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-155">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
14. <span data-ttu-id="4c090-156">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c090-156">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="4c090-157">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="4c090-157">Click Save.</span></span>
16. <span data-ttu-id="4c090-158">W okienku akcji kliknij opcję Pobierz i zapakuj.</span><span class="sxs-lookup"><span data-stu-id="4c090-158">On the Action Pane, click Pick and pack.</span></span>
17. <span data-ttu-id="4c090-159">Kliknij opcję Księguj dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="4c090-159">Click Post packing slip.</span></span>
18. <span data-ttu-id="4c090-160">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="4c090-160">Expand the Parameters section.</span></span>
19. <span data-ttu-id="4c090-161">W polu Księgowanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="4c090-161">Select Yes in the Posting field.</span></span>
20. <span data-ttu-id="4c090-162">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c090-162">Click OK.</span></span>
21. <span data-ttu-id="4c090-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c090-163">Click OK.</span></span>
22. <span data-ttu-id="4c090-164">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="4c090-164">On the Action Pane, click General.</span></span>
23. <span data-ttu-id="4c090-165">Kliknij opcję Dołączona umowa sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c090-165">Click Attached sales agreement.</span></span>
24. <span data-ttu-id="4c090-166">Kliknij kartę Realizacja.</span><span class="sxs-lookup"><span data-stu-id="4c090-166">Click the Fulfillment tab.</span></span>

