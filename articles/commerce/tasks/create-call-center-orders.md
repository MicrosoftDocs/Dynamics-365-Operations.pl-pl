---
title: Tworzenie zamówień dla biur obsługi
description: Ta procedura zawiera instruktaż wyszukiwania odbiorcy, tworzenia nowego zamówienia, wyszukiwania produktu i inkasowania płatności od odbiorcy.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dce2fdd9d91c2bd867f0455573733aefb0796fa7
ms.sourcegitcommit: 776758a0ff95c3c7398986095104d1d2b9814514
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2020
ms.locfileid: "4107359"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="a2b61-103">Tworzenie zamówień dla biur obsługi</span><span class="sxs-lookup"><span data-stu-id="a2b61-103">Create call center orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2b61-104">Ta procedura zawiera instruktaż wyszukiwania odbiorcy, tworzenia nowego zamówienia, wyszukiwania produktu i inkasowania płatności od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="a2b61-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="a2b61-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT i jest przeznaczona dla pracownika ds. zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a2b61-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="a2b61-106">Warunki wstępne: Użytkownik wykonujący tę procedurę musi być skonfigurowany jako użytkownik biura obsługi, a półroczny katalog firmy Fabrikam musi być opublikowany i zawierać co najmniej jeden kod źródłowy.</span><span class="sxs-lookup"><span data-stu-id="a2b61-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="a2b61-107">Wybierz kolejno opcje **Handel detaliczny i inny \> Odbiorcy \> Obsługa klienta**.</span><span class="sxs-lookup"><span data-stu-id="a2b61-107">Go to **Retail and Commerce \> Customers \> Customer service**.</span></span>
2. <span data-ttu-id="a2b61-108">W polu **SearchText** wprowadź kryteria wyszukiwania, aby znaleźć odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="a2b61-108">For **SearchText** , enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="a2b61-109">W tej przykładowej procedurze wpisz „Karen”, a następnie naciśnij klawisz **Tab**.</span><span class="sxs-lookup"><span data-stu-id="a2b61-109">For this example procedure, enter "Karen" and select **Tab**.</span></span>  
3. <span data-ttu-id="a2b61-110">Wybierz opcję Wyszukaj.</span><span class="sxs-lookup"><span data-stu-id="a2b61-110">Select Search.</span></span>
    * <span data-ttu-id="a2b61-111">Ponieważ w danych demonstracyjnych jest tylko jeden klient o imieniu „Karen”, wynik zostanie wybrany automatycznie.</span><span class="sxs-lookup"><span data-stu-id="a2b61-111">Since there is only one customer named "Karen" in demo data, the result will be automatically selected.</span></span>  
4. <span data-ttu-id="a2b61-112">Wybierz opcję **Nowe zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="a2b61-112">Select **New sales order**.</span></span>
5. <span data-ttu-id="a2b61-113">Rozwiń lub zwiń sekcję nagłówek **Zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="a2b61-113">Expand or collapse the **Sales order** header section.</span></span>
6. <span data-ttu-id="a2b61-114">Wybierz kod źródłowy dla katalogu.</span><span class="sxs-lookup"><span data-stu-id="a2b61-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="a2b61-115">Jeśli nie ma żadnych aktywnych kodów źródłowych, można pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="a2b61-115">If there are no active source codes you can skip this step.</span></span>  
7. <span data-ttu-id="a2b61-116">Wybierz **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="a2b61-116">Select **Add line**.</span></span>
8. <span data-ttu-id="a2b61-117">W polu **Numer towaru** wpisz wyszukiwany termin, przy użyciu którego chcesz znaleźć towar.</span><span class="sxs-lookup"><span data-stu-id="a2b61-117">For **Item number** , enter the item search term.</span></span>
    * <span data-ttu-id="a2b61-118">W tej przykładowej procedurze wprowadź częściowy numer pozycji „8111” i naciśnij klawisz tab. Ta czynność spowoduje wyświetlenie okna wyszukiwania przedmiotów.</span><span class="sxs-lookup"><span data-stu-id="a2b61-118">For this sample procedure, enter a partial item number of '8111' and press tab. This action will bring up the item search window.</span></span>  
9. <span data-ttu-id="a2b61-119">Wybierz produkt, który chcesz dodać do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a2b61-119">Select the product to add to the sales order.</span></span>
10. <span data-ttu-id="a2b61-120">Wprowadź ilość sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a2b61-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="a2b61-121">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="a2b61-121">Select **Create**.</span></span>
12. <span data-ttu-id="a2b61-122">Wybierz **Gotowe** , aby zarejestrować informacje o płatności od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="a2b61-122">Select **Complete** to capture the customer payment.</span></span>
13. <span data-ttu-id="a2b61-123">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a2b61-123">Select **Add**.</span></span>
    * <span data-ttu-id="a2b61-124">Łącze Dodaj znajduje się na karcie Płatności. Jeśli karta Płatności jest zwinięta, rozwiń ją.</span><span class="sxs-lookup"><span data-stu-id="a2b61-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="a2b61-125">Wybierz metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="a2b61-125">Select the payment method.</span></span>
    * <span data-ttu-id="a2b61-126">W tej procedurze wybierz płatność gotówką.</span><span class="sxs-lookup"><span data-stu-id="a2b61-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="a2b61-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a2b61-127">Close the page.</span></span>
16. <span data-ttu-id="a2b61-128">Wpisz kwotę.</span><span class="sxs-lookup"><span data-stu-id="a2b61-128">Enter the amount.</span></span>
    * <span data-ttu-id="a2b61-129">W tej procedurze wprowadź kwotę równą saldu zamówienia, które widać na stronie Podsumowanie zamówienia sprzedaży na lewo od pola kwoty.</span><span class="sxs-lookup"><span data-stu-id="a2b61-129">For this procedure, enter an amount equal to the order balance that can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="a2b61-130">Ta czynność pozwoli Ci zrealizować zamówienie jako w pełni opłacone.</span><span class="sxs-lookup"><span data-stu-id="a2b61-130">This action will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="a2b61-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2b61-131">Select **OK**.</span></span>
18. <span data-ttu-id="a2b61-132">Wybierz opcję **Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="a2b61-132">Select **Submit**.</span></span>

