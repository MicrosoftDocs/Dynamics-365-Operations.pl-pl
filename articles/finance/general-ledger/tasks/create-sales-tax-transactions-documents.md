---
title: Tworzenie transakcji podatku w dokumentach
description: Podatek od dokumentu oblicza się poprzez określenie grupy podatków i grupy podatków dla towaru w wierszach dokumentu.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bdc4b5c31d9a478a5226ae6b5e8c776de3b661dd
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144842"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="03406-103">Tworzenie transakcji podatku w dokumentach</span><span class="sxs-lookup"><span data-stu-id="03406-103">Create sales tax transactions on documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="03406-104">Podatek od dokumentu oblicza się poprzez określenie grupy podatków i grupy podatków dla towaru w wierszach dokumentu.</span><span class="sxs-lookup"><span data-stu-id="03406-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="03406-105">Dane te są domyślnie pobierane z danych głównych, ale można je zmienić ręcznie, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="03406-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="03406-106">Obliczony podatek można sprawdzać na poziomie wiersza i dokumentu.</span><span class="sxs-lookup"><span data-stu-id="03406-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="03406-107">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="03406-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="03406-108">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="03406-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="03406-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="03406-109">Click New.</span></span>
3. <span data-ttu-id="03406-110">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="03406-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="03406-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="03406-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="03406-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="03406-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="03406-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="03406-113">Click OK.</span></span>
7. <span data-ttu-id="03406-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="03406-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="03406-115">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="03406-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="03406-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="03406-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="03406-117">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="03406-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="03406-118">Rozwiń lub zwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="03406-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="03406-119">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="03406-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="03406-120">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="03406-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="03406-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="03406-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="03406-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="03406-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="03406-123">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="03406-123">Click Financials.</span></span>
17. <span data-ttu-id="03406-124">Kliknij opcję Podatek.</span><span class="sxs-lookup"><span data-stu-id="03406-124">Click Sales tax.</span></span>
18. <span data-ttu-id="03406-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="03406-125">Click OK.</span></span>
19. <span data-ttu-id="03406-126">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="03406-126">Click Add line.</span></span>
20. <span data-ttu-id="03406-127">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="03406-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="03406-128">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="03406-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="03406-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="03406-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="03406-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="03406-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="03406-131">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="03406-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="03406-132">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="03406-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="03406-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="03406-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="03406-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="03406-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="03406-135">W okienku akcji kliknij pozycję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="03406-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="03406-136">Kliknij opcję Podatek.</span><span class="sxs-lookup"><span data-stu-id="03406-136">Click Sales tax.</span></span>
30. <span data-ttu-id="03406-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="03406-137">Click OK.</span></span>

