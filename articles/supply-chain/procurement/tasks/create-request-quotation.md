--- 
title: Tworzenie zapytania ofertowego
description: "W tej procedurze pokazano sposób tworzenia zapytania ofertowego."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTableListPage, PurchCreateRFQCase, InventLocationIdLookup, PurchRFQCaseTable, InventItemIdLookupSimple, EcoResCategorySingleLookup, UnitOfMeasureLookup, PurchRFQEditLines, PurchRFQEditLinesPrintOptions, VendRFQJournal, SrsReportViewerForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 4c09149fcbe5731126c2e48a37fafdf71c1d49df
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-request-for-quotation"></a><span data-ttu-id="6804b-103">Tworzenie zapytania ofertowego</span><span class="sxs-lookup"><span data-stu-id="6804b-103">Create a request for quotation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6804b-104">W tej procedurze pokazano sposób tworzenia zapytania ofertowego.</span><span class="sxs-lookup"><span data-stu-id="6804b-104">This procedure shows you how to create a request for quotation.</span></span> <span data-ttu-id="6804b-105">Zazwyczaj robi to pracownik działu zakupów.</span><span class="sxs-lookup"><span data-stu-id="6804b-105">This would typically be done by a purchasing agent.</span></span> <span data-ttu-id="6804b-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="6804b-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="6804b-107">Przed rozpoczęciem trzeba mieć skonfigurowane typy zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="6804b-107">You need to have set up solicitation types before you start.</span></span> <span data-ttu-id="6804b-108">Po wykonaniu tego zadania i utworzeniu oraz wysłaniu ZO można wprowadzić odpowiedzi dla poszczególnych dostawców, porównać je, a następnie przyznać zamówienie.</span><span class="sxs-lookup"><span data-stu-id="6804b-108">Once you’ve completed this task and you’ve created and sent an RFQ you can then enter the replies per vendor, compare them, and award the contract.</span></span>


## <a name="prepare-a-new-rfq"></a><span data-ttu-id="6804b-109">Przygotowywanie nowego ZO</span><span class="sxs-lookup"><span data-stu-id="6804b-109">Prepare a new RFQ</span></span>
1. <span data-ttu-id="6804b-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapytania ofertowe > Wszystkie zapytania ofertowe.</span><span class="sxs-lookup"><span data-stu-id="6804b-110">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="6804b-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6804b-111">Click New.</span></span>
    * <span data-ttu-id="6804b-112">Dostępne są następujące typy zakupu: Zamówienie zakupu (jest to ustawienie domyślne): dokument potwierdzający ofertę kupna produktów lub zaakceptowanie oferty sprzedaży produktów w zamian za płatność.</span><span class="sxs-lookup"><span data-stu-id="6804b-112">The following purchase types are available: Purchase order (this is the default): a document that confirms the offer to buy products, or the acceptance of an offer to sell products in exchange for payment.</span></span> <span data-ttu-id="6804b-113">Zapotrzebowanie na zakup: ten typ jest zaznaczany automatycznie, jeśli zapytanie ofertowe jest tworzone bezpośrednio na podstawie zapotrzebowania zakupu.</span><span class="sxs-lookup"><span data-stu-id="6804b-113">Purchase requisition: this type is automatically selected if you create an RFQ directly from a purchase requisition.</span></span> <span data-ttu-id="6804b-114">W przypadku ręcznego zaznaczenia tej opcji pojawi się komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="6804b-114">If you manually select this option, you’ll get an error.</span></span> <span data-ttu-id="6804b-115">Umowa zakupu: umowa zakupu podanej ilości lub wartości produktu w określonym czasie.</span><span class="sxs-lookup"><span data-stu-id="6804b-115">Purchase agreement: an agreement to purchase a specific quantity or value of product over time.</span></span> <span data-ttu-id="6804b-116">Jeśli zostanie wybrana ta opcja, należy wybrać zakres dat, który ma zastosowanie do umowy zakupu.</span><span class="sxs-lookup"><span data-stu-id="6804b-116">If you select this option, you must select the date range that applies to the purchase agreement.</span></span>  
3. <span data-ttu-id="6804b-117">W polu Tytuł dokumentu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6804b-117">In the Document title field, type a value.</span></span>
4. <span data-ttu-id="6804b-118">W polu Typ zdobywania zamówień wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6804b-118">In the Solicitation type field, enter or select a value.</span></span>
    * <span data-ttu-id="6804b-119">Jeśli z typem zdobywania zamówień jest skojarzona metoda punktowania, będzie to domyślna metoda punktowania dla tworzonego ZO.</span><span class="sxs-lookup"><span data-stu-id="6804b-119">If a scoring method is associated with the solicitation type, this will be the default scoring method for the RFQ that you’re creating.</span></span> <span data-ttu-id="6804b-120">Później można zmienić metodę punktowania.</span><span class="sxs-lookup"><span data-stu-id="6804b-120">It is possible to change the scoring method later.</span></span>  
    * <span data-ttu-id="6804b-121">W polu Data dostawy wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="6804b-121">In the Delivery date field, enter a date.</span></span>  
    * <span data-ttu-id="6804b-122">Zaznacz datę, do kiedy chcesz otrzymać towary.</span><span class="sxs-lookup"><span data-stu-id="6804b-122">Select the date by which you want to receive the items.</span></span>  
    * <span data-ttu-id="6804b-123">W polu Data i godzina ważności wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="6804b-123">In the Expiration date and time field, enter a date and time.</span></span>  
    * <span data-ttu-id="6804b-124">Określ datę i godzinę, do kiedy dostawca musi odpowiedzieć na ZO.</span><span class="sxs-lookup"><span data-stu-id="6804b-124">Specify the date and time by which vendors must respond to the RFQ.</span></span>  
5. <span data-ttu-id="6804b-125">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6804b-125">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="6804b-126">Adresem dostawy będzie domyślnie adres magazynu.</span><span class="sxs-lookup"><span data-stu-id="6804b-126">The delivery address will default to the warehouse address.</span></span>  
6. <span data-ttu-id="6804b-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6804b-127">Click OK.</span></span>

## <a name="add-lines"></a><span data-ttu-id="6804b-128">Dodaj wiersze</span><span class="sxs-lookup"><span data-stu-id="6804b-128">Add lines</span></span>
    * <span data-ttu-id="6804b-129">Po określeniu podstawowych informacji o ZO, określ towary lub usługi, na które dostawcy mają złożyć oferty.</span><span class="sxs-lookup"><span data-stu-id="6804b-129">After you’ve specified the basic information about your RFQ, you specify the goods or services that you want vendors to bid on.</span></span> <span data-ttu-id="6804b-130">Domyślnym typem wiersza jest Towar.</span><span class="sxs-lookup"><span data-stu-id="6804b-130">Item is the default line type.</span></span>   
1. <span data-ttu-id="6804b-131">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6804b-131">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="6804b-132">Jeśli używasz firmy demonstracyjnej USMF, można wybrać towar T0020.</span><span class="sxs-lookup"><span data-stu-id="6804b-132">If you're using USMF, you can select T0020.</span></span>  
2. <span data-ttu-id="6804b-133">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="6804b-133">In the Quantity field, enter a number.</span></span>
3. <span data-ttu-id="6804b-134">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="6804b-134">Click Add line.</span></span>
4. <span data-ttu-id="6804b-135">W polu Typ wiersza wybierz opcję „Kategoria”.</span><span class="sxs-lookup"><span data-stu-id="6804b-135">In the Line type field, select 'Category'.</span></span>
    * <span data-ttu-id="6804b-136">Typ wiersza Kategoria może służyć do tworzenia ZO na pozamagazynowe towary lub usługi.</span><span class="sxs-lookup"><span data-stu-id="6804b-136">You can use the Category line type to create RFQs for non-inventory goods or services.</span></span> <span data-ttu-id="6804b-137">Następnie należy wybrać rodzaj towarów lub usług z hierarchii kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="6804b-137">You then need to select the type of goods or services from a hierarchy of procurement categories.</span></span>  
5. <span data-ttu-id="6804b-138">W polu Kategoria zaopatrzenia wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6804b-138">In the Procurement category field, enter or select a value.</span></span>
6. <span data-ttu-id="6804b-139">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6804b-139">In the Product name field, type a value.</span></span>
7. <span data-ttu-id="6804b-140">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="6804b-140">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="6804b-141">W polu Jednostka wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6804b-141">In the Unit field, enter or select a value.</span></span>

## <a name="add-vendors"></a><span data-ttu-id="6804b-142">Dodawanie dostawców</span><span class="sxs-lookup"><span data-stu-id="6804b-142">Add vendors</span></span>
1. <span data-ttu-id="6804b-143">Kliknij nagłówek i zmień widok z widoku wierszy na widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="6804b-143">Click Header to change from the Lines view to the Header view.</span></span> 
2. <span data-ttu-id="6804b-144">Rozwiń sekcję Dostawca.</span><span class="sxs-lookup"><span data-stu-id="6804b-144">Expand the Vendor section.</span></span>
3. <span data-ttu-id="6804b-145">Kliknij opcję Automatyczne dodawanie dostawców.</span><span class="sxs-lookup"><span data-stu-id="6804b-145">Click Auto-add vendors.</span></span>
    * <span data-ttu-id="6804b-146">Można dodać dostawców do ZO automatycznie na podstawie kategorii zaopatrzenia zamówionych towarów.</span><span class="sxs-lookup"><span data-stu-id="6804b-146">You can add vendors to the RFQ automatically, based on the procurement category of the items requested.</span></span> <span data-ttu-id="6804b-147">Jeśli nie ma dostawców zatwierdzonych dla kategorii zawartych w wierszach, można dodać dostawców ręcznie.</span><span class="sxs-lookup"><span data-stu-id="6804b-147">If there are no vendors approved for the categories included in the lines you can add vendors manually.</span></span>  
4. <span data-ttu-id="6804b-148">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="6804b-148">Click Add.</span></span>
5. <span data-ttu-id="6804b-149">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6804b-149">In the Vendor account field, enter or select a value.</span></span>
6. <span data-ttu-id="6804b-150">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="6804b-150">Click Add.</span></span>
7. <span data-ttu-id="6804b-151">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6804b-151">In the Vendor account field, enter or select a value.</span></span>
    * <span data-ttu-id="6804b-152">Po zaznaczeniu dostawcy jego stanem jest Utworzone.</span><span class="sxs-lookup"><span data-stu-id="6804b-152">Once you’ve selected a vendor, the status is Created.</span></span> <span data-ttu-id="6804b-153">Oznacza to, że dane dostawcy zostały zapisane w zapytaniu ofertowym, jednak zapytania nie wysyłano do dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6804b-153">This means that the vendor information has been saved in the RFQ, but you have not sent the RFQ to the vendor.</span></span> <span data-ttu-id="6804b-154">Można dodawać dostawcę do zapytania ofertowego niezależnie od stanu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6804b-154">You can add a vendor to an RFQ regardless of the vendor status.</span></span>  

## <a name="send-the-rfq-to-vendors"></a><span data-ttu-id="6804b-155">Wyślij ZO do dostawców</span><span class="sxs-lookup"><span data-stu-id="6804b-155">Send the RFQ to vendors</span></span>
1. <span data-ttu-id="6804b-156">Kliknij przycisk Wyślij.</span><span class="sxs-lookup"><span data-stu-id="6804b-156">Click Send.</span></span>
    * <span data-ttu-id="6804b-157">Na stronie Wysyłanie zapytania ofertowego sprawdź, czy dostawcy na liście są tymi, którzy powinni otrzymać ZO.</span><span class="sxs-lookup"><span data-stu-id="6804b-157">In the Sending request for quotation page, check that the vendors in the list are the ones that you want to receive the RFQ.</span></span>  
2. <span data-ttu-id="6804b-158">Kliknij przycisk Drukuj.</span><span class="sxs-lookup"><span data-stu-id="6804b-158">Click Print.</span></span>
    * <span data-ttu-id="6804b-159">To okno dialogowe umożliwia wydrukowanie ZO.</span><span class="sxs-lookup"><span data-stu-id="6804b-159">This dialog allows you to print the RFQ.</span></span> <span data-ttu-id="6804b-160">Jeśli chcesz wydrukować arkusz odpowiedzi, jego zawartość należy zdefiniować w oknie Parametry modułu Zaopatrzenie i sourcing.</span><span class="sxs-lookup"><span data-stu-id="6804b-160">If you choose to print a reply sheet, the contents of this are defined in Procurement and Sourcing parameters.</span></span> <span data-ttu-id="6804b-161">Aby wybrać sposób drukowania arkuszy odpowiedzi, po otwarciu okna dialogowego Drukowanie kliknij przycisk Zaawansowane opcje drukowania.</span><span class="sxs-lookup"><span data-stu-id="6804b-161">To choose how to print reply sheets, once you’ve opened the Print dialog, click Advanced printing options.</span></span> <span data-ttu-id="6804b-162">Zostanie wydrukowane jedno ZO dla każdego dostawcy zawierającego wiersze o stanie Utworzone lub Wysłane.</span><span class="sxs-lookup"><span data-stu-id="6804b-162">One RFQ will be printed for each vendor containing the lines that have the status of Created or Sent.</span></span> <span data-ttu-id="6804b-163">Wiersze anulowane i wiersze z zarejestrowanymi odpowiedziami nie są drukowane.</span><span class="sxs-lookup"><span data-stu-id="6804b-163">Canceled lines and lines with registered replies will not be printed.</span></span>   
3. <span data-ttu-id="6804b-164">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="6804b-164">Click Cancel.</span></span>
4. <span data-ttu-id="6804b-165">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6804b-165">Click OK.</span></span>
5. <span data-ttu-id="6804b-166">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6804b-166">Close the page.</span></span>
6. <span data-ttu-id="6804b-167">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6804b-167">Close the page.</span></span>

## <a name="view-the-rfq-journal"></a><span data-ttu-id="6804b-168">Wyświetlanie arkusza ZO</span><span class="sxs-lookup"><span data-stu-id="6804b-168">View the RFQ journal</span></span>
1. <span data-ttu-id="6804b-169">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapytania ofertowe > Kolejne działania dotyczące zapytania ofertowego > Arkusze zapytań ofertowych.</span><span class="sxs-lookup"><span data-stu-id="6804b-169">Go to Procurement and sourcing > Requests for quotations > Request for quotations follow-up > Request for quotation journals.</span></span>
2. <span data-ttu-id="6804b-170">Kliknij opcję Podgląd/drukuj.</span><span class="sxs-lookup"><span data-stu-id="6804b-170">Click Preview/Print.</span></span>
3. <span data-ttu-id="6804b-171">Kliknij opcję Podgląd oryginału.</span><span class="sxs-lookup"><span data-stu-id="6804b-171">Click Original preview.</span></span>
4. <span data-ttu-id="6804b-172">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6804b-172">Close the page.</span></span>
5. <span data-ttu-id="6804b-173">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6804b-173">Close the page.</span></span>


