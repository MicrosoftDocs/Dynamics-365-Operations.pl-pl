--- 
title: "Wprowadzanie umów sprzedaży"
description: "W tej procedurze pokazano sposób tworzenia umowy sprzedaży, która zobowiązuje jednego odbiorcę do zakupu produktu na ustaloną kwotę w określonym czasie w zamian za specjalne rabaty."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8c11164f7edb8e05b93f3c58b9707c0bf2482228
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="enter-sales-agreements"></a><span data-ttu-id="b15aa-103">Wprowadzanie umów sprzedaży</span><span class="sxs-lookup"><span data-stu-id="b15aa-103">Enter sales agreements</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b15aa-104">W tej procedurze pokazano sposób tworzenia umowy sprzedaży, która zobowiązuje jednego odbiorcę do zakupu produktu na</span><span class="sxs-lookup"><span data-stu-id="b15aa-104">This procedure shows you how to create a sales agreement that commits one of your customers to buy a product for an</span></span>

<span data-ttu-id="b15aa-105">ustaloną kwotę w określonym czasie w zamian za specjalne rabaty.</span><span class="sxs-lookup"><span data-stu-id="b15aa-105">agreed amount over time in exchange for special discounts.</span></span> <span data-ttu-id="b15aa-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="b15aa-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-sales-agreement-header"></a><span data-ttu-id="b15aa-107">Konfigurowanie nagłówka umowy sprzedaży</span><span class="sxs-lookup"><span data-stu-id="b15aa-107">Set up sales agreement header</span></span>
1. <span data-ttu-id="b15aa-108">Wybierz kolejno opcje Sprzedaż i marketing > Umowy sprzedaży > Umowy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b15aa-108">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="b15aa-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b15aa-109">Click New.</span></span>
3. <span data-ttu-id="b15aa-110">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="b15aa-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b15aa-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b15aa-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="b15aa-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b15aa-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="b15aa-113">W polu Klasyfikacja umowy sprzedaży kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="b15aa-113">In the Sales agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b15aa-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b15aa-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="b15aa-115">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="b15aa-115">Expand the General section.</span></span>
9. <span data-ttu-id="b15aa-116">W polu Domyślne zobowiązanie wybierz opcję „Zobowiązanie co do wartości produktu”.</span><span class="sxs-lookup"><span data-stu-id="b15aa-116">In the Default commitment field, select 'Product value commitment'.</span></span>
    * <span data-ttu-id="b15aa-117">Typ zobowiązania to wymagane kryterium, które należy przypisać do umowy, aby zdefiniować sposób realizacji umowy.</span><span class="sxs-lookup"><span data-stu-id="b15aa-117">A commitment type is a mandatory criterion that you must assign to the agreement to define how the agreement contract will be fulfilled.</span></span> <span data-ttu-id="b15aa-118">Cztery wstępnie zdefiniowane typy umożliwiają skonfigurowanie przedmiotu zobowiązania dla odbiorcy, wyrażonego jako ilość lub wartość.</span><span class="sxs-lookup"><span data-stu-id="b15aa-118">The four predefined types let you set up the customer's commitment target, expressed as a quantity or a value.</span></span> <span data-ttu-id="b15aa-119">Zobowiązanie co do ilości można zastosować tylko do określonego produktu, ale typy oparte na wartości mają zastosowanie do sprzedaży produktów określonych i nieokreślonych.</span><span class="sxs-lookup"><span data-stu-id="b15aa-119">The quantity commitment type can only be applied to a specific product, but the value-based types are applicable to sales of both specific and non-specific products.</span></span>  
10. <span data-ttu-id="b15aa-120">W polu Data wygaśnięcia ustaw przyszłą datę, kiedy umowa ma wygasnąć.</span><span class="sxs-lookup"><span data-stu-id="b15aa-120">In the Expiration date field, set the date to a future date when you want the agreement to expire.</span></span>
11. <span data-ttu-id="b15aa-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b15aa-121">Click OK.</span></span>

## <a name="set-up-product-value-commitment-lines"></a><span data-ttu-id="b15aa-122">Konfigurowanie wierszy zobowiązania co do wartości produktu</span><span class="sxs-lookup"><span data-stu-id="b15aa-122">Set up product value commitment lines</span></span>
1. <span data-ttu-id="b15aa-123">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="b15aa-123">Click Add line.</span></span>
2. <span data-ttu-id="b15aa-124">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="b15aa-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b15aa-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b15aa-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b15aa-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b15aa-126">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b15aa-127">Typ zobowiązania wybrany dla umowy wpływa na rodzaj informacji, które można wprowadzać w wierszach umowy.</span><span class="sxs-lookup"><span data-stu-id="b15aa-127">The type of commitment that you have chosen for the agreement affects the kind of information you can enter for the agreement lines.</span></span> <span data-ttu-id="b15aa-128">Na przykład w umowie opartej na wartości trzeba określić łączną kwotę netto (w uzgodnionej walucie), za którą odbiorca zobowiązuje się kupić towary od Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="b15aa-128">For example, for a value-based agreement you must specify the total net amount (in the agreed currency) for which the customer commits to buys goods from you.</span></span> <span data-ttu-id="b15aa-129">W tym przykładzie pola Ilość i Jednostka w wierszu są niedostępne, ponieważ tworzysz umowę dotycząca kupna produktów na określoną wartość przez odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="b15aa-129">In this example the Quantity and Unit fields on the line are unavailable because you’re creating an agreement for the customer to buy a specific value of a product.</span></span>   
5. <span data-ttu-id="b15aa-130">W polu Kwota netto wprowadź kwotę pieniężną, za jaką odbiorca zobowiązał się kupić.</span><span class="sxs-lookup"><span data-stu-id="b15aa-130">In the Net amount field, enter the monetary amount that the customer has committed to buying.</span></span>
6. <span data-ttu-id="b15aa-131">W polu Procent rabatu wprowadź wartość procentową, która będzie stosowana do wierszy zamówienia sprzedaży odbiorcy połączonych z tą umową.</span><span class="sxs-lookup"><span data-stu-id="b15aa-131">In the Discount percent field, enter a percentage value that will apply to the customer's sales order lines that are linked to this agreement.</span></span>
7. <span data-ttu-id="b15aa-132">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="b15aa-132">Expand the Line details section.</span></span>
8. <span data-ttu-id="b15aa-133">W polu Wymuszono maks. wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b15aa-133">Select Yes in the Max is enforced field.</span></span>
    * <span data-ttu-id="b15aa-134">Wybór opcji Wymuszono maks. oznacza, że łączna ilość we wszystkich wierszach zamówienia sprzedaży, które używają specjalnych cen, rabatów i/lub warunków płatności zobowiązania, nie może przekraczać kwoty określonej w zobowiązaniu.</span><span class="sxs-lookup"><span data-stu-id="b15aa-134">Selecting Max is enforced means that the total amount of all the sales order lines that use the commitment's special prices, discounts and/or payment terms must not exceed the amount specified on the commitment.</span></span>  
    * <span data-ttu-id="b15aa-135">Kwoty zwolnienia minimalna i maksymalna określają zakres wartości, na które należy wykonać sprzedaż w każdym zamówieniu sprzedaży korzystającym z wybranej umowy.</span><span class="sxs-lookup"><span data-stu-id="b15aa-135">The minimum and maximum release amounts specify a range of values that must be sold on each sales order that uses the selected agreement.</span></span>   
9. <span data-ttu-id="b15aa-136">Rozwiń sekcję Nagłówek umowy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b15aa-136">Expand the Sales agreement header section.</span></span>
    * <span data-ttu-id="b15aa-137">Jeśli umowa ma stan inny niż Obowiązuje, zamówienia sprzedaży nie mogą być kojarzone z umową i w związku z tym nie mogą się przyczyniać do realizacji umowy.</span><span class="sxs-lookup"><span data-stu-id="b15aa-137">Unless the status of the agreement is set to Effective, sales orders cannot be associated with the agreement and can therefore not contribute to the fulfilment of that agreement.</span></span> <span data-ttu-id="b15aa-138">Stan można zmienić ręcznie na tym etapie.</span><span class="sxs-lookup"><span data-stu-id="b15aa-138">You can change the status manually at this stage.</span></span> <span data-ttu-id="b15aa-139">Jednak stan zazwyczaj zmienia się podczas potwierdzania umowy dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b15aa-139">However, the status would normally be changed when you confirm the agreement for the customer.</span></span>  
10. <span data-ttu-id="b15aa-140">W okienku akcji kliknij opcję Umowa sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b15aa-140">On the Action Pane, click Sales agreement.</span></span>
11. <span data-ttu-id="b15aa-141">Kliknij opcję Potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="b15aa-141">Click Confirmation.</span></span>
    * <span data-ttu-id="b15aa-142">Upewnij się, że w opcji Oznaczenie umowy jako obowiązującej zaznaczono wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="b15aa-142">Make sure that the Mark agreement as effective option is set to Yes.</span></span>  
12. <span data-ttu-id="b15aa-143">W polu Drukuj raport zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b15aa-143">Select Yes in the Print report field.</span></span>
13. <span data-ttu-id="b15aa-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b15aa-144">Click OK.</span></span>
14. <span data-ttu-id="b15aa-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b15aa-145">Close the page.</span></span>
    * <span data-ttu-id="b15aa-146">Umowa teraz obowiązuje i można rozpocząć łączenie zamówień odbiorcy z umową w celu umożliwienia realizacji zadeklarowanego celu zakupowego.</span><span class="sxs-lookup"><span data-stu-id="b15aa-146">The agreement is now effective and you can start linking the customer's orders to the agreement, to offset against the committed target.</span></span>  


