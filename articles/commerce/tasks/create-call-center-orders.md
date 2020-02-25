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
ms.openlocfilehash: d1675d21f1e4176839feace76359afdbdc336c99
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023676"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="829af-103">Tworzenie zamówień dla biur obsługi</span><span class="sxs-lookup"><span data-stu-id="829af-103">Create call center orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="829af-104">Ta procedura zawiera instruktaż wyszukiwania odbiorcy, tworzenia nowego zamówienia, wyszukiwania produktu i inkasowania płatności od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="829af-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="829af-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT i jest przeznaczona dla pracownika ds. zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="829af-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="829af-106">Warunki wstępne: Użytkownik wykonujący tę procedurę musi być skonfigurowany jako użytkownik biura obsługi, a półroczny katalog firmy Fabrikam musi być opublikowany i zawierać co najmniej jeden kod źródłowy.</span><span class="sxs-lookup"><span data-stu-id="829af-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="829af-107">Wybierz kolejno opcje Handel detaliczny i inny > Odbiorcy > Obsługa klienta.</span><span class="sxs-lookup"><span data-stu-id="829af-107">Go to Retail and Commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="829af-108">W polu SearchText wprowadź kryteria wyszukiwania, aby znaleźć odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="829af-108">In the SearchText field, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="829af-109">W tej przykładowej procedurze wpisz „karen”, a następnie naciśnij klawisz tab.</span><span class="sxs-lookup"><span data-stu-id="829af-109">For this example procedure type in 'karen' and press tab.</span></span>  
3. <span data-ttu-id="829af-110">Kliknij przycisk Wyszukaj.</span><span class="sxs-lookup"><span data-stu-id="829af-110">Click Search.</span></span>
    * <span data-ttu-id="829af-111">Ponieważ w danych demonstracyjnych jest tylko jeden odbiorca o nazwie Karen, zostanie on automatycznie zaznaczony.</span><span class="sxs-lookup"><span data-stu-id="829af-111">Since there is only one customer named Karen in demo data they will be automatically selected.</span></span>  
4. <span data-ttu-id="829af-112">Kliknij opcję Nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="829af-112">Click New sales order.</span></span>
5. <span data-ttu-id="829af-113">Rozwiń lub zwiń sekcję Nagłówek zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="829af-113">Expand or collapse the Sales order header section.</span></span>
6. <span data-ttu-id="829af-114">Wybierz kod źródłowy dla katalogu.</span><span class="sxs-lookup"><span data-stu-id="829af-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="829af-115">Jeśli nie ma żadnych aktywnych kodów źródłowych, można zamknąć pole Źródło i pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="829af-115">If there are no active Source codes you can close the Source field and skip this step.</span></span>  
7. <span data-ttu-id="829af-116">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="829af-116">Click Add line.</span></span>
8. <span data-ttu-id="829af-117">W polu Numer towaru wpisz wyszukiwany termin, przy użyciu którego chcesz znaleźć towar.</span><span class="sxs-lookup"><span data-stu-id="829af-117">In the Item number field, enter the item search term.</span></span>
    * <span data-ttu-id="829af-118">W tej przykładowej procedurze wprowadź część numeru towaru „8111”, a następnie naciśnij klawisz tab. Pojawi się wyskakujące okno wyszukiwania towaru.</span><span class="sxs-lookup"><span data-stu-id="829af-118">For this sample procedure enter a partial item number of '8111' and press tab. This will pop up the item search window.</span></span>  
9. <span data-ttu-id="829af-119">Wybierz produkt, który chcesz dodać do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="829af-119">Select the product to add to the sales order</span></span>
10. <span data-ttu-id="829af-120">Wprowadź ilość sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="829af-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="829af-121">Kliknij Utwórz.</span><span class="sxs-lookup"><span data-stu-id="829af-121">Click Create.</span></span>
12. <span data-ttu-id="829af-122">Kliknij przycisk Gotowe, aby zarejestrować informacje o płatności od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="829af-122">Click Complete to capture the customer payment.</span></span>
13. <span data-ttu-id="829af-123">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="829af-123">Click Add.</span></span>
    * <span data-ttu-id="829af-124">Łącze Dodaj znajduje się na karcie Płatności. Jeśli karta Płatności jest zwinięta, rozwiń ją.</span><span class="sxs-lookup"><span data-stu-id="829af-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="829af-125">Wybierz metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="829af-125">Select the payment method.</span></span>
    * <span data-ttu-id="829af-126">W tej procedurze wybierz płatność gotówką.</span><span class="sxs-lookup"><span data-stu-id="829af-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="829af-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="829af-127">Close the page.</span></span>
16. <span data-ttu-id="829af-128">Wpisz kwotę.</span><span class="sxs-lookup"><span data-stu-id="829af-128">Enter the amount.</span></span>
    * <span data-ttu-id="829af-129">W tej procedurze wprowadź kwotę równą saldu zamówienia, które widać na stronie Podsumowanie zamówienia sprzedaży na lewo od pola kwoty.</span><span class="sxs-lookup"><span data-stu-id="829af-129">For this procedure enter an amount equal to the order balance which can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="829af-130">Dzięki temu będzie można sfinalizować zamówienie jako w pełni opłacone.</span><span class="sxs-lookup"><span data-stu-id="829af-130">This will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="829af-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="829af-131">Click OK.</span></span>
18. <span data-ttu-id="829af-132">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="829af-132">Click Submit.</span></span>

