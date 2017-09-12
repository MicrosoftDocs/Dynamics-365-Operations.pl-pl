--- 
title: Tworzenie transakcji podatku w dokumentach
description: "Podatek od dokumentu oblicza się poprzez określenie grupy podatków i grupy podatków dla towaru w wierszach dokumentu."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 27bf4ba33bd7d22443512d072572b9b1ffc164fa
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="9070b-103">Tworzenie transakcji podatku w dokumentach</span><span class="sxs-lookup"><span data-stu-id="9070b-103">Create sales tax transactions on documents</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9070b-104">Podatek od dokumentu oblicza się poprzez określenie grupy podatków i grupy podatków dla towaru w wierszach dokumentu.</span><span class="sxs-lookup"><span data-stu-id="9070b-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="9070b-105">Dane te są domyślnie pobierane z danych głównych, ale można je zmienić ręcznie, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="9070b-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="9070b-106">Obliczony podatek można sprawdzać na poziomie wiersza i dokumentu.</span><span class="sxs-lookup"><span data-stu-id="9070b-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="9070b-107">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="9070b-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="9070b-108">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9070b-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="9070b-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="9070b-109">Click New.</span></span>
3. <span data-ttu-id="9070b-110">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9070b-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9070b-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9070b-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="9070b-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9070b-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="9070b-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9070b-113">Click OK.</span></span>
7. <span data-ttu-id="9070b-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="9070b-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="9070b-115">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9070b-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="9070b-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9070b-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="9070b-117">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="9070b-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="9070b-118">Rozwiń lub zwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="9070b-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="9070b-119">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="9070b-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="9070b-120">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9070b-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="9070b-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9070b-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="9070b-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9070b-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="9070b-123">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="9070b-123">Click Financials.</span></span>
17. <span data-ttu-id="9070b-124">Kliknij opcję Podatek.</span><span class="sxs-lookup"><span data-stu-id="9070b-124">Click Sales tax.</span></span>
18. <span data-ttu-id="9070b-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9070b-125">Click OK.</span></span>
19. <span data-ttu-id="9070b-126">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="9070b-126">Click Add line.</span></span>
20. <span data-ttu-id="9070b-127">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="9070b-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="9070b-128">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9070b-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="9070b-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9070b-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="9070b-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9070b-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="9070b-131">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="9070b-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="9070b-132">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9070b-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="9070b-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9070b-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="9070b-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9070b-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="9070b-135">W okienku akcji kliknij pozycję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="9070b-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="9070b-136">Kliknij opcję Podatek.</span><span class="sxs-lookup"><span data-stu-id="9070b-136">Click Sales tax.</span></span>
30. <span data-ttu-id="9070b-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9070b-137">Click OK.</span></span>


