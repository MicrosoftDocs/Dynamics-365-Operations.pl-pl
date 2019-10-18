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
ms.openlocfilehash: 653b93744f5b891655cade0cb669d34179fca9cd
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186148"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="7dfad-103">Tworzenie transakcji podatku w dokumentach</span><span class="sxs-lookup"><span data-stu-id="7dfad-103">Create sales tax transactions on documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7dfad-104">Podatek od dokumentu oblicza się poprzez określenie grupy podatków i grupy podatków dla towaru w wierszach dokumentu.</span><span class="sxs-lookup"><span data-stu-id="7dfad-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="7dfad-105">Dane te są domyślnie pobierane z danych głównych, ale można je zmienić ręcznie, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="7dfad-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="7dfad-106">Obliczony podatek można sprawdzać na poziomie wiersza i dokumentu.</span><span class="sxs-lookup"><span data-stu-id="7dfad-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="7dfad-107">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="7dfad-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="7dfad-108">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="7dfad-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="7dfad-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7dfad-109">Click New.</span></span>
3. <span data-ttu-id="7dfad-110">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7dfad-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7dfad-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7dfad-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="7dfad-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7dfad-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7dfad-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7dfad-113">Click OK.</span></span>
7. <span data-ttu-id="7dfad-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7dfad-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="7dfad-115">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7dfad-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="7dfad-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7dfad-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="7dfad-117">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7dfad-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="7dfad-118">Rozwiń lub zwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="7dfad-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="7dfad-119">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="7dfad-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="7dfad-120">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7dfad-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="7dfad-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7dfad-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="7dfad-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7dfad-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="7dfad-123">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="7dfad-123">Click Financials.</span></span>
17. <span data-ttu-id="7dfad-124">Kliknij opcję Podatek.</span><span class="sxs-lookup"><span data-stu-id="7dfad-124">Click Sales tax.</span></span>
18. <span data-ttu-id="7dfad-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7dfad-125">Click OK.</span></span>
19. <span data-ttu-id="7dfad-126">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="7dfad-126">Click Add line.</span></span>
20. <span data-ttu-id="7dfad-127">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7dfad-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="7dfad-128">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7dfad-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="7dfad-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7dfad-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="7dfad-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7dfad-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="7dfad-131">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7dfad-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="7dfad-132">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7dfad-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="7dfad-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7dfad-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="7dfad-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7dfad-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="7dfad-135">W okienku akcji kliknij pozycję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="7dfad-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="7dfad-136">Kliknij opcję Podatek.</span><span class="sxs-lookup"><span data-stu-id="7dfad-136">Click Sales tax.</span></span>
30. <span data-ttu-id="7dfad-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7dfad-137">Click OK.</span></span>

