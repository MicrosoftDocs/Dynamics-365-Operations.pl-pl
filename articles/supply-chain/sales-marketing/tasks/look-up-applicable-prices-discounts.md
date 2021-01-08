---
title: Wyszukiwanie odpowiednich cen i rabatów
description: W tej procedurze pokazano sposób wyszukiwania ceny i/lub rabatu na produkt, który jest aktualnie dostępny dla określonego odbiorcy, bez tworzenia zamówienia sprzedaży.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cfdbda55c2f83ee2b470cab8a5e4f9ce728b852
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435024"
---
# <a name="look-up-applicable-prices-and-discounts"></a><span data-ttu-id="d2d02-103">Wyszukiwanie odpowiednich cen i rabatów</span><span class="sxs-lookup"><span data-stu-id="d2d02-103">Look up applicable prices and discounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d2d02-104">W tej procedurze pokazano sposób wyszukiwania ceny i/lub rabatu na produkt, który jest aktualnie dostępny dla określonego odbiorcy, bez tworzenia zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d2d02-104">This procedure shows how to find the price and/or discount for a product which is currently valid for a specific customer, without creating a sales order.</span></span> <span data-ttu-id="d2d02-105">Procedura prowadzi przez konkretny przykład. W celu wybierania niezbędnych wartości należy wykonać przykład z użyciem danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d2d02-105">The procedure walks through a specific example, and you need follow the example using the USMF demo company in order to select the necessary values.</span></span>


## <a name="find-the-applicable-price"></a><span data-ttu-id="d2d02-106">Wyszukiwanie odpowiedniej ceny</span><span class="sxs-lookup"><span data-stu-id="d2d02-106">Find the applicable price</span></span>
1. <span data-ttu-id="d2d02-107">Wybierz kolejno opcje Sprzedaż i marketing > Ceny i rabaty > Znajdź ceny.</span><span class="sxs-lookup"><span data-stu-id="d2d02-107">Go to Sales and marketing > Prices and discounts > Find prices.</span></span>
2. <span data-ttu-id="d2d02-108">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d2d02-108">In the Customer account field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d2d02-109">Na liście znajdź i zaznacz odbiorcę US-001.</span><span class="sxs-lookup"><span data-stu-id="d2d02-109">In the list, find and select customer US-001.</span></span>
4. <span data-ttu-id="d2d02-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d2d02-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d2d02-111">W polu Numer pozycji wpisz „T0004”.</span><span class="sxs-lookup"><span data-stu-id="d2d02-111">In the Item number field, type 'T0004'.</span></span>
    * <span data-ttu-id="d2d02-112">Domyślnie w polu Ilość jest ustawiona wartość 1.</span><span class="sxs-lookup"><span data-stu-id="d2d02-112">By default, the Quantity field is set to 1.</span></span> <span data-ttu-id="d2d02-113">Jednak jeśli jest znany rozmiar zamówienia, jakie odbiorca zamierza złożyć na dany produkt, wprowadź tę wartość.</span><span class="sxs-lookup"><span data-stu-id="d2d02-113">However, if you know the size of the order that the customer intends to place for the product in question, then enter this value instead.</span></span> <span data-ttu-id="d2d02-114">Ta informacja jest istotna, jeśli umowy handlowe z odbiorcą zawierają przedziały ilości, tzn. cena produktu zależy od zakupionej ilości minimalnej.</span><span class="sxs-lookup"><span data-stu-id="d2d02-114">This information is relevant if the trade agreements with the customer have quantity breaks, that is, the product's price depends on the minimum quantity purchased.</span></span>  
6. <span data-ttu-id="d2d02-115">W polu Data wprowadź datę, kiedy odbiorca zamierza złożyć zamówienie.</span><span class="sxs-lookup"><span data-stu-id="d2d02-115">In the Date field, enter a date for when the customer expects to place an order.</span></span> 
    * <span data-ttu-id="d2d02-116">Data może być datą dzisiejszą lub dowolnym dniem w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="d2d02-116">The date can be today's date or any date in the future.</span></span>  
    * <span data-ttu-id="d2d02-117">Teraz system zwróci cenę, która jest prawidłowa dla wybranego produktu podczas kupowania przez wybranego odbiorcę w wybranym dniu w określonej ilości.</span><span class="sxs-lookup"><span data-stu-id="d2d02-117">The system now returns the price that is valid for the selected product when bought by the selected customer on the selected date with a specified quantity.</span></span> <span data-ttu-id="d2d02-118">W tym przykładzie jeśli US-001 odbiorca kupi 1 jednostkę produktu T0004 dzisiaj, zostanie obciążony kwotą 350 CAD.</span><span class="sxs-lookup"><span data-stu-id="d2d02-118">In this example, if the customer US-001 bought 1 unit of product T0004 today, they would be charged 350 CAD a unit.</span></span> <span data-ttu-id="d2d02-119">Ta cena pochodzi z istniejącej i aktywnej umowy handlowej z odbiorcą.</span><span class="sxs-lookup"><span data-stu-id="d2d02-119">This price comes from an existing and active trade agreement with the customer.</span></span>      <span data-ttu-id="d2d02-120">Inne pola na stronie zawierają szczegółowe informacje o cenie produktu i koszcie produktu (jeżeli je skonfigurowano w produkcie głównym) oraz obliczoną rentowność.</span><span class="sxs-lookup"><span data-stu-id="d2d02-120">Other fields on the page provide more details about the product price and product cost (if set up on the product master), and calculated profitability.</span></span>  
    * <span data-ttu-id="d2d02-121">Jeśli jest zaznaczona Pokaż pokrewne warianty produktu, oznacza to, że istnieją dodatkowe umowy handlowe na warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="d2d02-121">If the Show related product variants option is selected, it means that there are additional trade agreements for product's variants.</span></span>  
7. <span data-ttu-id="d2d02-122">Zaznacz pole wyboru Pokaż pokrewne warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="d2d02-122">Click the Show related product variants checkbox.</span></span>
    * <span data-ttu-id="d2d02-123">Jest wyświetlana lista wariantów produktu wraz z informacjami o ich wymiarach.</span><span class="sxs-lookup"><span data-stu-id="d2d02-123">A list of the product variants is shown, with information about their dimensions.</span></span>  
8. <span data-ttu-id="d2d02-124">Na liście zaznacz wiersz reprezentujący kolor biały.</span><span class="sxs-lookup"><span data-stu-id="d2d02-124">In the list, mark the line representing color White.</span></span>
    * <span data-ttu-id="d2d02-125">Należy zauważyć, że cena produktu jest teraz inna niż wyświetlana poprzednio, gdy nie była określona dla wymiaru.</span><span class="sxs-lookup"><span data-stu-id="d2d02-125">Notice, that the product price is now different from the one displayed previously when it was not specified per dimension.</span></span>  
9. <span data-ttu-id="d2d02-126">Kliknij przycisk Wyświetl ceny sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d2d02-126">Click View sales prices.</span></span>
    * <span data-ttu-id="d2d02-127">Na stronie Cena (sprzedaż) są wyświetlane wszystkie umowy handlowe mające zastosowanie do produktu, w tym jego wariantów.</span><span class="sxs-lookup"><span data-stu-id="d2d02-127">The Price (sales) page displays all the trade agreements applicable to the product, including its variants.</span></span>  
10. <span data-ttu-id="d2d02-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2d02-128">Close the page.</span></span>

## <a name="find-the-applicable-discount"></a><span data-ttu-id="d2d02-129">Wyszukiwanie odpowiedniego rabatu</span><span class="sxs-lookup"><span data-stu-id="d2d02-129">Find the applicable discount</span></span>
<span data-ttu-id="d2d02-130">Upewnij się, że pole Konto odbiorcy zawiera numer odbiorcy US-001. </span><span class="sxs-lookup"><span data-stu-id="d2d02-130">Make sure the Customer account field contains customer number US-001</span></span>   
1. <span data-ttu-id="d2d02-131">W polu Numer pozycji wpisz „T0012”.</span><span class="sxs-lookup"><span data-stu-id="d2d02-131">In the Item number field, type 'T0012'.</span></span>
    * <span data-ttu-id="d2d02-132">Upewnij się, że pole Ilość zawiera wartość 1.</span><span class="sxs-lookup"><span data-stu-id="d2d02-132">Make sure the Quantity field is set to 1.</span></span>  
    * <span data-ttu-id="d2d02-133">Poniższe szczegóły cen wyświetlane dla produktu T0012 pochodzą z jednej lub kilku umów handlowych: cena jednostkowa wynosi 1000 CAD, a procent rabatu wynosi 5.</span><span class="sxs-lookup"><span data-stu-id="d2d02-133">The following pricing details shown for product T0012 come from one or more trade agreements: The unit price is 1,000 CAD and the discount percentage is 5.</span></span>  
2. <span data-ttu-id="d2d02-134">W polu Ilość wpisz wartość 20.</span><span class="sxs-lookup"><span data-stu-id="d2d02-134">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="d2d02-135">Zwiększona ilość w zamówieniu powoduje, że rabat wiersza, który będzie oferowany odbiorcy, zmienia się z 5 na 7 procent.</span><span class="sxs-lookup"><span data-stu-id="d2d02-135">The increased order quantity causes the line discount that will be offered to the customer to change from 5 to 7 percent.</span></span>  
    * <span data-ttu-id="d2d02-136">Kwota netto jest obliczana automatycznie na podstawie ceny jednostkowej, rabatu i ilości całkowitej.</span><span class="sxs-lookup"><span data-stu-id="d2d02-136">The Net amount is calculated based on the unit price, discount and the total quantity.</span></span>  
3. <span data-ttu-id="d2d02-137">Kliknij opcję Wyświetl rabat wiersza.</span><span class="sxs-lookup"><span data-stu-id="d2d02-137">Click View line discount.</span></span>
    * <span data-ttu-id="d2d02-138">Istnieją dwie umowy rabatu wiersza na produkt T0012, określając 5 procent rabatu za ilość wiersza zamówienia od 1 do 10 oraz 7 procent rabatu dla ilości w zamówieniu powyżej 10.</span><span class="sxs-lookup"><span data-stu-id="d2d02-138">There are two line discount agreements for product T0012, specifying a 5 percent discount for an order line quantity from 1 to 10, and 7 percent discount for order quantities above 10.</span></span> <span data-ttu-id="d2d02-139">Należy zwrócić uwagę, że rabaty są stosowane do grupy produktów, w tym przykładzie grupy o kodzie 01, do której należy produkt T0012.</span><span class="sxs-lookup"><span data-stu-id="d2d02-139">Note that the discounts are applied to a group of products, in this example, Group code 01, of which product T0012 is a member.</span></span>  
4. <span data-ttu-id="d2d02-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2d02-140">Close the page.</span></span>

