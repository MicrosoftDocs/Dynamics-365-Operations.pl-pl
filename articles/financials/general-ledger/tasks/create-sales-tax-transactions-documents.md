--- 
title: Tworzenie transakcji podatku w dokumentach
description: "Podatek od dokumentu oblicza się poprzez określenie grupy podatków i grupy podatków dla towaru w wierszach dokumentu."
author: twheeloc
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxTmpWorkTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 4e2edf0688224c6fcd0940f94801562440604d27
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="ea942-103">Tworzenie transakcji podatku w dokumentach</span><span class="sxs-lookup"><span data-stu-id="ea942-103">Create sales tax transactions on documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ea942-104">Podatek od dokumentu oblicza się poprzez określenie grupy podatków i grupy podatków dla towaru w wierszach dokumentu.</span><span class="sxs-lookup"><span data-stu-id="ea942-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="ea942-105">Dane te są domyślnie pobierane z danych głównych, ale można je zmienić ręcznie, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="ea942-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="ea942-106">Obliczony podatek można sprawdzać na poziomie wiersza i dokumentu.</span><span class="sxs-lookup"><span data-stu-id="ea942-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="ea942-107">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="ea942-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="ea942-108">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ea942-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="ea942-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ea942-109">Click New.</span></span>
3. <span data-ttu-id="ea942-110">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea942-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ea942-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea942-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ea942-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea942-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ea942-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ea942-113">Click OK.</span></span>
7. <span data-ttu-id="ea942-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ea942-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="ea942-115">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea942-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="ea942-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea942-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="ea942-117">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ea942-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="ea942-118">Rozwiń lub zwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="ea942-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="ea942-119">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="ea942-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="ea942-120">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea942-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="ea942-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea942-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="ea942-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea942-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="ea942-123">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="ea942-123">Click Financials.</span></span>
17. <span data-ttu-id="ea942-124">Kliknij opcję Podatek.</span><span class="sxs-lookup"><span data-stu-id="ea942-124">Click Sales tax.</span></span>
18. <span data-ttu-id="ea942-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ea942-125">Click OK.</span></span>
19. <span data-ttu-id="ea942-126">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="ea942-126">Click Add line.</span></span>
20. <span data-ttu-id="ea942-127">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ea942-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="ea942-128">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea942-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="ea942-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea942-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="ea942-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea942-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="ea942-131">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ea942-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="ea942-132">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea942-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="ea942-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea942-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="ea942-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea942-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="ea942-135">W okienku akcji kliknij pozycję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="ea942-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="ea942-136">Kliknij opcję Podatek.</span><span class="sxs-lookup"><span data-stu-id="ea942-136">Click Sales tax.</span></span>
30. <span data-ttu-id="ea942-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ea942-137">Click OK.</span></span>


