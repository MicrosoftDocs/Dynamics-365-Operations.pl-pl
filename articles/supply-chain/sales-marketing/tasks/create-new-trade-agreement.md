---
title: Tworzenie nowej umowy handlowej
description: Ta procedura przedstawia sposób tworzenia umowy handlowej, w której jest rejestrowana nowa ceny sprzedaży produktu uzgodniona z określonym odbiorcą.
author: omulvad
manager: AnnBe
ms.date: 11/16/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e132cd20437b7929e81fcaa123d70bb57fb320c8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549274"
---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="a5ffe-103">Tworzenie nowej umowy handlowej</span><span class="sxs-lookup"><span data-stu-id="a5ffe-103">Create a new trade agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a5ffe-104">Ta procedura przedstawia sposób tworzenia umowy handlowej, w której jest rejestrowana nowa ceny sprzedaży produktu uzgodniona z określonym odbiorcą.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="a5ffe-105">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="a5ffe-106">Jeśli używasz własnych danych, przed rozpoczęciem czynności z tego przewodnika upewnij się, że istnieje arkusz umów handlowych, w którym relacja domyślna jest ustawiony na „Cena (sprzedaż)”.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-106">If you’re using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to “Price (sales)”.</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="a5ffe-107">Tworzenie i księgowanie nowego arkusza umów handlowych</span><span class="sxs-lookup"><span data-stu-id="a5ffe-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="a5ffe-108">Wybierz kolejno opcje Sprzedaż i marketing > Ceny i rabaty > Arkusze umów handlowych.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-108">Go to Sales and marketing > Prices and discounts > Trade agreement journals.</span></span>
2. <span data-ttu-id="a5ffe-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-109">Click New.</span></span>
3. <span data-ttu-id="a5ffe-110">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a5ffe-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="a5ffe-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="a5ffe-113">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-113">Click Lines.</span></span>
7. <span data-ttu-id="a5ffe-114">W polu Kod konta wybierz opcję „Tabela”.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-114">In the Account code field, select 'Table'.</span></span>
    * <span data-ttu-id="a5ffe-115">W tym przykładzie zaktualizujesz cenę dla określonego odbiorcy, co oznacza, że musisz wybrać opcję Tabela.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-115">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="a5ffe-116">Cena byłaby aktualizowana cena katalogowa produktu, należałoby zaznaczyć opcję Wszystko, tak aby nowa cena obowiązywała dla wszystkich odbiorców.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-116">If you were updating the product's list price, you would select All, so that the new price is valid for all customers.</span></span> <span data-ttu-id="a5ffe-117">Zostały ceny byłyby różnicowane między segmentami odbiorców, należałoby wybrać opcję Grupa.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-117">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="a5ffe-118">Aby można było zaznaczyć opcję Grupa, muszą być skonfigurowane grupy cenowe dla odbiorców.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-118">To select Group, you must have set up Customer price groups.</span></span>  
8. <span data-ttu-id="a5ffe-119">W polu Wybór konta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-119">In the Account selection field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="a5ffe-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-120">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="a5ffe-121">W polu Kod towaru wybierz opcję „Tabela”.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-121">In the Item code field, select 'Table'.</span></span>
    * <span data-ttu-id="a5ffe-122">Podczas wprowadzania umowy handlowej typu „Cena (sprzedaż)” można w polu Kod towaru zaznaczyć tylko opcję „Tabela”.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-122">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the Item code field.</span></span> <span data-ttu-id="a5ffe-123">Jest tak, ponieważ cena jest wartością bezwzględną i nie może być taka sama dla wszystkich produktów lub grupy produktów.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-123">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>  
11. <span data-ttu-id="a5ffe-124">W polu Relacja towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-124">In the Item relation field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="a5ffe-125">Na liście zaznacz produkt, który chcesz umieścić w umowie.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-125">In the list, select the product you want to include in the agreement.</span></span>
    * <span data-ttu-id="a5ffe-126">Odnotuj, który produkt został wybrany.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-126">Make a note of which product you've selected.</span></span>  
13. <span data-ttu-id="a5ffe-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="a5ffe-128">W polu Od wprowadź ilość minimalną.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-128">In the From field, enter a minimum quantity.</span></span>
    * <span data-ttu-id="a5ffe-129">Jeśli odbiorca musi zamówić minimalną ilość, aby uzyskać nową cenę, trzeba w tym miejscu określić tę ilość.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-129">If the customer has to order a minimum quantity  before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    * <span data-ttu-id="a5ffe-130">Wprowadź wartość w polu Do, aby określić maksymalną ilość, powyżej której cena umowy nie będzie obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-130">Enter a value in the To field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="a5ffe-131">Jeśli oferujesz ceny i rabaty oparte na wielu przedziałach ilości, określ każdy przedział ilości za pomocą pary ilości minimalnej i maksymalnej odpowiednio w polach „Od” i „Do”.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-131">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the 'From' and 'To' fields respectively.</span></span>  
15. <span data-ttu-id="a5ffe-132">W polu Kwota w walucie wpisz cenę.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-132">In the Amount in currency field, enter a price.</span></span>
16. <span data-ttu-id="a5ffe-133">W polu Od dnia wprowadź datę, od kiedy umowa będzie obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-133">In the From date field, enter a date from which this agreement will be valid.</span></span>
17. <span data-ttu-id="a5ffe-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-134">Click Save.</span></span>
18. <span data-ttu-id="a5ffe-135">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-135">Click Validate.</span></span>
19. <span data-ttu-id="a5ffe-136">Kliknij przycisk Zweryfikuj zaznaczone wiersze.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-136">Click Validate selected lines.</span></span>
20. <span data-ttu-id="a5ffe-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-137">Click OK.</span></span>
21. <span data-ttu-id="a5ffe-138">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-138">Click Post.</span></span>
22. <span data-ttu-id="a5ffe-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-139">Click OK.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="a5ffe-140">Wyświetlanie umów handlowych na produkt</span><span class="sxs-lookup"><span data-stu-id="a5ffe-140">View trade agreements for a product</span></span>
1. <span data-ttu-id="a5ffe-141">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-141">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="a5ffe-142">Na liście znajdź i zaznacz produkt, którego cena została właśnie zaktualizowana.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-142">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="a5ffe-143">W okienku akcji kliknij pozycję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-143">On the Action Pane, click Sell.</span></span>
4. <span data-ttu-id="a5ffe-144">Kliknij opcję Wyświetl umowy handlowe.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-144">Click View trade agreements.</span></span>
    * <span data-ttu-id="a5ffe-145">Przejrzyj szczegóły utworzonej właśnie umowy handlowej dotyczącej cen.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-145">Review the details of the price trade agreement you have just created.</span></span>    
5. <span data-ttu-id="a5ffe-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a5ffe-146">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5ffe-147">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a5ffe-147">Additional resources</span></span>
### <a name="community-blogs"></a><span data-ttu-id="a5ffe-148">Blogi społeczności</span><span class="sxs-lookup"><span data-stu-id="a5ffe-148">Community blogs</span></span>
- [<span data-ttu-id="a5ffe-149">Ceny sprzedaży w Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a5ffe-149">Sales prices in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
