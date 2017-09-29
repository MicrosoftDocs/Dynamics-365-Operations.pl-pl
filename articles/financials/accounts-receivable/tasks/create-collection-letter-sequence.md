--- 
title: "Tworzenie kolejności ponagleń"
description: "Ten przewodnik po zadaniach umożliwia tworzenie kolejki ponagleń."
author: mikefalkner
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6331c3680169b305c4bfbfada4ba106b619be092
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-collection-letter-sequence"></a><span data-ttu-id="2bf73-103">Tworzenie kolejności ponagleń</span><span class="sxs-lookup"><span data-stu-id="2bf73-103">Create a collection letter sequence</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2bf73-104">Ten przewodnik po zadaniach umożliwia tworzenie kolejki ponagleń.</span><span class="sxs-lookup"><span data-stu-id="2bf73-104">Use this task guide to create a collection letter sequence.</span></span> <span data-ttu-id="2bf73-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="2bf73-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="2bf73-106">Wybierz kolejno opcje Kredyty i windykacja > Ustawienia > Konfiguruj kolejność ponagleń.</span><span class="sxs-lookup"><span data-stu-id="2bf73-106">Go to Credit and collections > Setup > Set up collection letter sequence.</span></span>
2. <span data-ttu-id="2bf73-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2bf73-107">Click New.</span></span>
3. <span data-ttu-id="2bf73-108">W polu Kolejność ponagleń wpisz identyfikator kolejności, który będzie reprezentował kolejność.</span><span class="sxs-lookup"><span data-stu-id="2bf73-108">In the Collection letter sequence field, enter a sequence ID that will represent the sequence.</span></span> <span data-ttu-id="2bf73-109">Będzie on używany podczas konfigurowania profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="2bf73-109">It will be used when you set up a posting profile.</span></span>
4. <span data-ttu-id="2bf73-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="2bf73-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="2bf73-111">Warunki płatności są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="2bf73-111">The terms of payment is optional.</span></span> <span data-ttu-id="2bf73-112">Jeśli wprowadzisz wartość w tym polu, faktura za opłaty z ponaglenia będzie używała tych warunków płatności zamiast warunków płatności zapisanych dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2bf73-112">If you enter a value here, the collection letter fee invoice will use these terms of payment instead of the terms of payment stored with the customer.</span></span>  
5. <span data-ttu-id="2bf73-113">W polu Kod ponaglenia wybierz kod pierwszego ponaglenia, które ma zostać wysłane.</span><span class="sxs-lookup"><span data-stu-id="2bf73-113">In the collection letter code field, select the code for the first collection letter that you want to send.</span></span>
    * <span data-ttu-id="2bf73-114">Pierwsze ponaglenie jest tworzone na podstawie terminu zapłaty na fakturze, wartości okresu prolongaty wprowadzonej w polu Dni w tym wierszu oraz innych informacji wprowadzonych w tym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bf73-114">The first collection letter is created according to the due date on the invoice, the value that you enter for the grace period in the Days field on this line, and other information that you enter on this line.</span></span>  
6. <span data-ttu-id="2bf73-115">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="2bf73-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="2bf73-116">Domyślnie walutą opłaty będzie waluta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2bf73-116">The currency for the fee defaults to the customer currency.</span></span> <span data-ttu-id="2bf73-117">Ten kod waluty może się różnić od kodu waluty faktury.</span><span class="sxs-lookup"><span data-stu-id="2bf73-117">This currency code can be different than the invoice currency.</span></span>  
7. <span data-ttu-id="2bf73-118">Kliknij przycisk Dodaj, aby dodać następne ponaglenie w kolejności, które zostanie wysłane.</span><span class="sxs-lookup"><span data-stu-id="2bf73-118">Click Add to add the next collection letter that will be sent in the sequence</span></span>
    * <span data-ttu-id="2bf73-119">W wielu przypadkach pierwsze ponaglenie jest tylko ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="2bf73-119">In many cases, the first collection letter is just a warning.</span></span> <span data-ttu-id="2bf73-120">W razie potrzeby można dodać opłaty.</span><span class="sxs-lookup"><span data-stu-id="2bf73-120">You can add fees if needed.</span></span>  
8. <span data-ttu-id="2bf73-121">W polu Kod ponaglenia wybierz kod następnego w kolei ponaglenia, które ma zostać wysłane.</span><span class="sxs-lookup"><span data-stu-id="2bf73-121">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
9. <span data-ttu-id="2bf73-122">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bf73-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="2bf73-123">W polu konta głównego wybierz konto przychodów, które będzie używane dla opłat.</span><span class="sxs-lookup"><span data-stu-id="2bf73-123">In the main account field, select the revenue account that will be used for fees.</span></span>
11. <span data-ttu-id="2bf73-124">Wprowadź opłatę, która będzie naliczana podczas księgowania tego ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="2bf73-124">Enter the fee that will be charged when this collection letter is posted.</span></span>
12. <span data-ttu-id="2bf73-125">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bf73-125">In the Item sales tax group field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="2bf73-126">Zaznacz grupę podatków dla towaru, jeśli należy obliczyć podatki od opłaty.</span><span class="sxs-lookup"><span data-stu-id="2bf73-126">Select an item sales tax group if sales taxes must be calculated on the fee.</span></span>  
13. <span data-ttu-id="2bf73-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bf73-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="2bf73-128">Wprowadź minimalne saldo zaległości, jakie jest wymagane, zanim zostanie wysłane ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="2bf73-128">Enter the minimum overdue balance required before a collection letter is sent.</span></span>
15. <span data-ttu-id="2bf73-129">Wprowadź liczbę dni prolongaty, na jaką chcesz pozwolić.</span><span class="sxs-lookup"><span data-stu-id="2bf73-129">Enter the number of grace days that you will allow.</span></span>
    * <span data-ttu-id="2bf73-130">Jest to liczba dni po terminie płatności, kiedy można wygenerować ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="2bf73-130">This is the number of days after the due date that a collection letter can be generated.</span></span> <span data-ttu-id="2bf73-131">Termin płatności używany do obliczania zależy od miejsca ponaglenia w kolejce ponagleń:   ⦁    Okres prolongaty ponaglenia 1 jest względny wobec terminu płatności na fakturze.</span><span class="sxs-lookup"><span data-stu-id="2bf73-131">The due date that is used for the calculation depends on the position of the collection letter in the collection letter sequence:   ⦁    The grace period for collection letter 1 is relative to the due date on the invoice.</span></span>  <span data-ttu-id="2bf73-132">⦁ Okres prolongaty ponaglenia 2 i kolejnych jest względny wobec daty zaksięgowania lub wydrukowania poprzedniego ponaglenia, zależnie od opcji wybranej w polu Aktualizacja kodu ponaglenia na stronie Parametry modułu rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="2bf73-132">⦁ The grace period for collection letters 2 and higher is relative to the date that the previous collection letter is posted or printed, depending on the selection in the Update collection letter code field in the Accounts receivable parameters page.</span></span>  
16. <span data-ttu-id="2bf73-133">Kliknij przycisk Dodaj, aby dodać ostatnie ponaglenie w kolejności.</span><span class="sxs-lookup"><span data-stu-id="2bf73-133">Click Add to add the last collection letter in the sequence.</span></span>
    * <span data-ttu-id="2bf73-134">W kolejce ponagleń można dodać maksymalnie pięć kodów ponagleń.</span><span class="sxs-lookup"><span data-stu-id="2bf73-134">You can add up to five collection letter codes for a collection letter sequence.</span></span>  
17. <span data-ttu-id="2bf73-135">W polu Kod ponaglenia wybierz kod następnego w kolei ponaglenia, które ma zostać wysłane.</span><span class="sxs-lookup"><span data-stu-id="2bf73-135">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
18. <span data-ttu-id="2bf73-136">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bf73-136">In the Description field, type a value.</span></span>
19. <span data-ttu-id="2bf73-137">W polu Konto główne podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="2bf73-137">In the Main account field, specify the desired values.</span></span>
20. <span data-ttu-id="2bf73-138">W polu Opłata w walucie wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="2bf73-138">In the Fee in currency field, enter a number.</span></span>
21. <span data-ttu-id="2bf73-139">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bf73-139">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="2bf73-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bf73-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="2bf73-141">W polu Minimalne saldo zaległości wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="2bf73-141">In the Minimum overdue balance field, enter a number.</span></span>
24. <span data-ttu-id="2bf73-142">W polu Dni wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="2bf73-142">In the Days field, enter a number.</span></span>
25. <span data-ttu-id="2bf73-143">To pole wyboru należy zaznaczyć, aby zablokować możliwość tworzenia kolejnych dostaw i faktur dla danego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2bf73-143">Select this check box to stop the customer from additional deliveries and invoicing.</span></span>
    * <span data-ttu-id="2bf73-144">Aby odblokować konto, wybierz Nie w Fakturowanie i dostawy zablokowane na stronie Klientów.</span><span class="sxs-lookup"><span data-stu-id="2bf73-144">To unblock the account, select No in the Invoicing and delivery on hold field in the Customers page.</span></span>  
26. <span data-ttu-id="2bf73-145">Rozwiń skróconą kartę Notatka.</span><span class="sxs-lookup"><span data-stu-id="2bf73-145">Expand the Note fasttab.</span></span>
27. <span data-ttu-id="2bf73-146">Wprowadź tekst, jaki ma być wyświetlany dla ponaglenia o wybranym kodzie.</span><span class="sxs-lookup"><span data-stu-id="2bf73-146">Enter the text to appear on the collection letter for the selected collection letter code.</span></span>
    * <span data-ttu-id="2bf73-147">Ten tekst można przetłumaczyć na wiele języków za pomocą menu Tłumaczenia widocznego nad polem notatki.</span><span class="sxs-lookup"><span data-stu-id="2bf73-147">You can translate this text in to multiple languages using the Translations menu above the note box.</span></span>  


