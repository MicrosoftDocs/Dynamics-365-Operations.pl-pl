---
title: Księgowanie arkuszy okresowych
description: Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas pobierania arkusza.
author: aprilolson
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7f721a05c8b74f1cfcf43177b73129751483650e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446825"
---
# <a name="post-periodic-journals"></a><span data-ttu-id="0286f-103">Księgowanie arkuszy okresowych</span><span class="sxs-lookup"><span data-stu-id="0286f-103">Post periodic journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0286f-104">Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas pobierania arkusza.</span><span class="sxs-lookup"><span data-stu-id="0286f-104">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the periodic journal is retrieved.</span></span> <span data-ttu-id="0286f-105">Podczas tworzenia arkusza okresowego należy określić interwał okresu dla cyklu, taki jak dni lub miesiące.</span><span class="sxs-lookup"><span data-stu-id="0286f-105">When you create the periodic journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="0286f-106">W Okienku nawigacji otwórz Moduły > Księga główna > Zadania okresowe > Generowanie arkuszy.</span><span class="sxs-lookup"><span data-stu-id="0286f-106">This task guide will create a periodic journal with a monthly recurrence.</span></span>

1. <span data-ttu-id="0286f-107">W Okienku nawigacji otwórz **Moduły > Księga główna > Zadania okresowe > Arkusze okresowe**.</span><span class="sxs-lookup"><span data-stu-id="0286f-107">Go to **Navigation pane > Modules > General ledger > Periodic tasks > Periodic journals**.</span></span>
2. <span data-ttu-id="0286f-108">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0286f-108">Click **New**.</span></span>
3. <span data-ttu-id="0286f-109">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0286f-109">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="0286f-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0286f-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="0286f-111">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0286f-111">In the **Description** field, type a value.</span></span> <span data-ttu-id="0286f-112">Opisem po późniejszym pobraniu będzie nazwa arkusza okresowego, dlatego nadaj mu nazwę charakterystyczną.</span><span class="sxs-lookup"><span data-stu-id="0286f-112">The description will be the name of the Periodic journal when retrieved later so make sure to give it a relevant name.</span></span>
6. <span data-ttu-id="0286f-113">W **okienku akcji** kliknij pozycję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="0286f-113">On the **Action pane**, click **Lines**.</span></span> <span data-ttu-id="0286f-114">Arkusz okresowy zazwyczaj będzie zawierał kilka wierszy arkusza.</span><span class="sxs-lookup"><span data-stu-id="0286f-114">A periodic journal will typically include several journal lines.</span></span> <span data-ttu-id="0286f-115">W tym przewodniku po zadaniach będzie jednak dodany tylko jeden wiersz.</span><span class="sxs-lookup"><span data-stu-id="0286f-115">this task guide will however only add one line.</span></span>
7. <span data-ttu-id="0286f-116">W polu **Data** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="0286f-116">In the **Date** field, enter a date.</span></span> <span data-ttu-id="0286f-117">Pole **Data** zawiera datę księgowania następnego przeniesienia do arkusza dziennego.</span><span class="sxs-lookup"><span data-stu-id="0286f-117">The **Date** field contains the posting date for the next transfer to the daily journal.</span></span> <span data-ttu-id="0286f-118">Dla arkuszy, które będą pobierane każdego miesiąca, zaleca się używanie daty w miesiącu księgowania, czyli zazwyczaj pierwszej lub ostatniej daty w okresie.</span><span class="sxs-lookup"><span data-stu-id="0286f-118">For journals that will be retrieved each month it is recommended to use the date in the month when it will be posted, typically the first or last date in the period.</span></span> <span data-ttu-id="0286f-119">Istnieje możliwość pozostawienia pola Data pustego i podania daty w trakcie pobierania arkusza przy użyciu pola Pusta data.</span><span class="sxs-lookup"><span data-stu-id="0286f-119">It is possible to leave the Date field blank and to give a date when the journal is retrieved, using the Empty date field.</span></span> <span data-ttu-id="0286f-120">To pole jest automatycznie aktualizowane o następną datę wynikającą z cyklu w trakcie pobierania transakcji.</span><span class="sxs-lookup"><span data-stu-id="0286f-120">The field is automatically updated to the next recurring date when transactions are retrieved.</span></span> 
8. <span data-ttu-id="0286f-121">W polu **Konto** podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="0286f-121">In the **Account** field, specify the desired values.</span></span>
9. <span data-ttu-id="0286f-122">Wprowadź lub wybierz wartość w polu **Opis**.</span><span class="sxs-lookup"><span data-stu-id="0286f-122">In the **Description** field, select a value.</span></span>
10. <span data-ttu-id="0286f-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0286f-123">Close the page.</span></span>
11. <span data-ttu-id="0286f-124">W polu **Debet** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="0286f-124">In the **Debit** field, enter a number.</span></span>
12. <span data-ttu-id="0286f-125">W polu **Konto przeciwstawne** podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="0286f-125">In the **Offset account** field, specify the desired values.</span></span>
13. <span data-ttu-id="0286f-126">W polu **Jednostka** zaznacz opcję „Miesiące”.</span><span class="sxs-lookup"><span data-stu-id="0286f-126">In the **Unit** field, select 'Months'.</span></span>
14. <span data-ttu-id="0286f-127">W polu **Liczba jednostek** wpisz wartość „1”.</span><span class="sxs-lookup"><span data-stu-id="0286f-127">In the **Number of units** field, enter '1'.</span></span>
15. <span data-ttu-id="0286f-128">W polu **Ostatnia data** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="0286f-128">In the **Last date** field, enter a date.</span></span> <span data-ttu-id="0286f-129">Wprowadzanie ostatniego dnia z poprzedniego okresu zapobiegnie omyłkowemu tworzeniu arkusza cyklicznego w nieprawidłowym okresie początkowym.</span><span class="sxs-lookup"><span data-stu-id="0286f-129">Entering last date in the preceding period will prevent that the recurring journal by mistake is created in the wrong starting period.</span></span> <span data-ttu-id="0286f-130">Ostatni dzień będzie później aktualizowany każdorazowo podczas pobierania arkusza okresowego.</span><span class="sxs-lookup"><span data-stu-id="0286f-130">Last date will later on be updated each time the periodic journal is retrieved.</span></span> 
16. <span data-ttu-id="0286f-131">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0286f-131">Click **Save**.</span></span>
17. <span data-ttu-id="0286f-132">Otwórz **Okienko nawigacji > Moduły > Księga główna > Wpisy w arkuszu > Arkusze finansowe**.</span><span class="sxs-lookup"><span data-stu-id="0286f-132">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
18. <span data-ttu-id="0286f-133">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0286f-133">Click **New**.</span></span>
19. <span data-ttu-id="0286f-134">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0286f-134">In the **Name** field, enter or select a value.</span></span>
20. <span data-ttu-id="0286f-135">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0286f-135">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="0286f-136">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0286f-136">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="0286f-137">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0286f-137">In the **Description** field, type a value.</span></span>
23. <span data-ttu-id="0286f-138">W **okienku akcji** kliknij pozycję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="0286f-138">On the **Action pane**, click **Lines**.</span></span>
24. <span data-ttu-id="0286f-139">W **Okienku akcji** kliknij **Arkusze okresowe**.</span><span class="sxs-lookup"><span data-stu-id="0286f-139">On the **Action pane**, click **Period journal**.</span></span>
25. <span data-ttu-id="0286f-140">Kliknij opcję **Wczytanie z arkusza okresowego**.</span><span class="sxs-lookup"><span data-stu-id="0286f-140">Click **Retrieve journal**.</span></span>
26. <span data-ttu-id="0286f-141">Wprowadź datę w polu **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="0286f-141">In the **To date** field, enter a date.</span></span> <span data-ttu-id="0286f-142">Pole **Do dnia** jest używane jako data graniczna dla okresowych wierszy załącznika.</span><span class="sxs-lookup"><span data-stu-id="0286f-142">The **To date** serves as the cutoff date for the periodic voucher lines.</span></span> <span data-ttu-id="0286f-143">Zależnie od ustawienia cyklu wartości Ostatnia data i Do dnia dotyczące tego samego wiersza można umieścić więcej niż jeden raz w powstałym arkuszu.</span><span class="sxs-lookup"><span data-stu-id="0286f-143">Based on the recurrence setting, the Last date and To date the same line might be included more than once in the resulting journal.</span></span> <span data-ttu-id="0286f-144">Pole Do dnia jest automatycznie aktualizowane na podstawie daty sesji z ostatniego razu, gdy wiersz okresowy był przenoszony do arkusza.</span><span class="sxs-lookup"><span data-stu-id="0286f-144">To date is automatically updated based on  session date of the last time the periodic line was transferred to a journal.</span></span> 
27. <span data-ttu-id="0286f-145">W polu **Numer arkusza okresowego** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0286f-145">In the **Periodic journal number** field, enter or select a value.</span></span>
28. <span data-ttu-id="0286f-146">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0286f-146">In the list, click the link in the selected row.</span></span>
29. <span data-ttu-id="0286f-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0286f-147">Click **OK**.</span></span> <span data-ttu-id="0286f-148">Arkusz okresowy może teraz zostać przejrzany, zatwierdzony lub zaksięgowany, w zależności od wymagań i konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0286f-148">The period journal can now be reviewed, approved or posted depending on requirement and setup.</span></span>   
