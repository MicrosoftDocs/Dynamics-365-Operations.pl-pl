---
title: Tworzenie nowej umowy handlowej
description: Ta procedura przedstawia sposób tworzenia umowy handlowej, w której jest rejestrowana nowa ceny sprzedaży produktu uzgodniona z określonym odbiorcą.
author: omulvad
manager: AnnBe
ms.date: 06/25/2019
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
ms.openlocfilehash: e42383b237a60d41d3b4e09ffbbe1c1bb5ebbfd7
ms.sourcegitcommit: 33e98f89294086334fe9c0a350abb6a52ef9dacb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/28/2019
ms.locfileid: "1711208"
---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="66aac-103">Tworzenie nowej umowy handlowej</span><span class="sxs-lookup"><span data-stu-id="66aac-103">Create a new trade agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="66aac-104">Ta procedura przedstawia sposób tworzenia umowy handlowej, w której jest rejestrowana nowa ceny sprzedaży produktu uzgodniona z określonym odbiorcą.</span><span class="sxs-lookup"><span data-stu-id="66aac-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="66aac-105">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="66aac-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="66aac-106">Jeśli używasz własnych danych, przed rozpoczęciem czynności z tego przewodnika upewnij się, że istnieje arkusz umów handlowych, w którym relacja domyślna jest ustawiony na „Cena (sprzedaż)”.</span><span class="sxs-lookup"><span data-stu-id="66aac-106">If you’re using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to “Price (sales)”.</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="66aac-107">Tworzenie i księgowanie nowego arkusza umów handlowych</span><span class="sxs-lookup"><span data-stu-id="66aac-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="66aac-108">Przejdź do **Okienko nawigacyji > Moduły > Sprzedaż i marketing > Ceny i rabaty > Czasopisma dotyczące umów handlowych**.</span><span class="sxs-lookup"><span data-stu-id="66aac-108">Go to **Navigation pane > Modules > Sales and marketing > Prices and discounts > Trade agreement journals**.</span></span>
2. <span data-ttu-id="66aac-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="66aac-109">Click **New**.</span></span>
3. <span data-ttu-id="66aac-110">W polu **Nazwa** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="66aac-110">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="66aac-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="66aac-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="66aac-112">W **Panelu akcji** kliknij **Linie**.</span><span class="sxs-lookup"><span data-stu-id="66aac-112">On **Action pane**, click **Lines**.</span></span>
6. <span data-ttu-id="66aac-113">W polu **Kod konta** wybierz „Tabela”.</span><span class="sxs-lookup"><span data-stu-id="66aac-113">In the **Account code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="66aac-114">W tym przykładzie zaktualizujesz cenę dla określonego odbiorcy, co oznacza, że musisz wybrać opcję Tabela.</span><span class="sxs-lookup"><span data-stu-id="66aac-114">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="66aac-115">Jeśli aktualizujesz cenę katalogową produktów, wybierz „Wszystko”, aby nowa cena została zmieniona dla wszystkich klientów.</span><span class="sxs-lookup"><span data-stu-id="66aac-115">If you were updating the product's list price, you would select 'All', so that the new price is valid for all customers.</span></span> <span data-ttu-id="66aac-116">Zostały ceny byłyby różnicowane między segmentami odbiorców, należałoby wybrać opcję Grupa.</span><span class="sxs-lookup"><span data-stu-id="66aac-116">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="66aac-117">Aby można było zaznaczyć opcję Grupa, muszą być skonfigurowane grupy cenowe dla odbiorców.</span><span class="sxs-lookup"><span data-stu-id="66aac-117">To select Group, you must have set up Customer price groups.</span></span>  

7. <span data-ttu-id="66aac-118">W polu **Wybór konta** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="66aac-118">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="66aac-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="66aac-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="66aac-120">W polu **Kod przedmiotu** wybierz „Tabela”.</span><span class="sxs-lookup"><span data-stu-id="66aac-120">In the **Item code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="66aac-121">Podczas zawierania umowy handlowej typu „Cena (sprzedaż)” należy wybrać tylko „Tabela” w polu **Kod przedmiotu**.</span><span class="sxs-lookup"><span data-stu-id="66aac-121">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the **Item code** field.</span></span> <span data-ttu-id="66aac-122">Jest tak, ponieważ cena jest wartością bezwzględną i nie może być taka sama dla wszystkich produktów lub grupy produktów.</span><span class="sxs-lookup"><span data-stu-id="66aac-122">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>
    
10. <span data-ttu-id="66aac-123">W polu **Powiązanie produktu** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="66aac-123">In the **Item relation** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="66aac-124">Na liście zaznacz produkt, który chcesz umieścić w umowie.</span><span class="sxs-lookup"><span data-stu-id="66aac-124">In the list, select the product you want to include in the agreement.</span></span> <span data-ttu-id="66aac-125">Odnotuj, który produkt został wybrany.</span><span class="sxs-lookup"><span data-stu-id="66aac-125">Make a note of which product you've selected.</span></span>  
12. <span data-ttu-id="66aac-126">W polu **Od** wpisz minimalną ilość.</span><span class="sxs-lookup"><span data-stu-id="66aac-126">In the **From** field, enter a minimum quantity.</span></span>
    - <span data-ttu-id="66aac-127">Jeśli odbiorca musi zamówić minimalną ilość, aby uzyskać nową cenę, trzeba w tym miejscu określić tę ilość.</span><span class="sxs-lookup"><span data-stu-id="66aac-127">If the customer has to order a minimum quantity before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    - <span data-ttu-id="66aac-128">Wpisz wartość w polu **Do**, żeby ustalić maksymalną ilość powyżej której cena zawarta w umowie nie będzie obowiązywała.</span><span class="sxs-lookup"><span data-stu-id="66aac-128">Enter a value in the **To** field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="66aac-129">Jeśli oferujesz ceny i rabaty na podstawie wielokrotnych podziałów ilościowych, określ każdy przedział ilościowy jako parę minimalnej i maksymalnej ilości odpowiednio w polach **Od** i **Do**.</span><span class="sxs-lookup"><span data-stu-id="66aac-129">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the **From** and **To** fields respectively.</span></span>
13. <span data-ttu-id="66aac-130">W polu **Ilość w walucie** wprowadź cenę.</span><span class="sxs-lookup"><span data-stu-id="66aac-130">In the **Amount in currency field**, enter a price.</span></span>
14. <span data-ttu-id="66aac-131">W sekcji **Szczegóły** w polu **Od daty** wpisz datę, od której ta umowa będzie ważna.</span><span class="sxs-lookup"><span data-stu-id="66aac-131">Under the **Details** section, in the **From date** field, enter a date from which this agreement will be valid.</span></span>
15. <span data-ttu-id="66aac-132">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="66aac-132">Click **Save**.</span></span>
16. <span data-ttu-id="66aac-133">Kliknij **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="66aac-133">Click **Validate**.</span></span>
17. <span data-ttu-id="66aac-134">Kliknij **Potwierdź wybrane linie**.</span><span class="sxs-lookup"><span data-stu-id="66aac-134">Click **Validate selected lines**.</span></span>
18. <span data-ttu-id="66aac-135">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="66aac-135">Click **OK**.</span></span>
19. <span data-ttu-id="66aac-136">Kliknij przycisk **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="66aac-136">Click **Post**.</span></span>
20. <span data-ttu-id="66aac-137">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="66aac-137">Click **OK**.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="66aac-138">Wyświetlanie umów handlowych na produkt</span><span class="sxs-lookup"><span data-stu-id="66aac-138">View trade agreements for a product</span></span>
1. <span data-ttu-id="66aac-139">Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.</span><span class="sxs-lookup"><span data-stu-id="66aac-139">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="66aac-140">Na liście znajdź i zaznacz produkt, którego cena została właśnie zaktualizowana.</span><span class="sxs-lookup"><span data-stu-id="66aac-140">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="66aac-141">W **Panelu akcji** kliknij **Sprzedaj**.</span><span class="sxs-lookup"><span data-stu-id="66aac-141">On the **Action Pane**, click **Sell**.</span></span>
4. <span data-ttu-id="66aac-142">Kliknij **Zobacz umowy handlowe**.</span><span class="sxs-lookup"><span data-stu-id="66aac-142">Click **View trade agreements**.</span></span>
    
    <span data-ttu-id="66aac-143">Przejrzyj szczegóły utworzonej właśnie umowy handlowej dotyczącej cen.</span><span class="sxs-lookup"><span data-stu-id="66aac-143">Review the details of the price trade agreement you have just created.</span></span>    

5. <span data-ttu-id="66aac-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="66aac-144">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="66aac-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="66aac-145">Additional resources</span></span>
### <a name="community-blogs"></a><span data-ttu-id="66aac-146">Blogi społeczności</span><span class="sxs-lookup"><span data-stu-id="66aac-146">Community blogs</span></span>
- [<span data-ttu-id="66aac-147">Ceny sprzedaży w Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="66aac-147">Sales prices in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
