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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 31c801658004f771df6f1ddf70194de131314a64
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212162"
---
# <a name="post-periodic-journals"></a><span data-ttu-id="b2a2e-103">Księgowanie arkuszy okresowych</span><span class="sxs-lookup"><span data-stu-id="b2a2e-103">Post periodic journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b2a2e-104">Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas pobierania arkusza.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-104">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the periodic journal is retrieved.</span></span> <span data-ttu-id="b2a2e-105">Podczas tworzenia arkusza okresowego należy określić interwał okresu dla cyklu, taki jak dni lub miesiące.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-105">When you create the periodic journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="b2a2e-106">W Okienku nawigacji otwórz Moduły > Księga główna > Zadania okresowe > Generowanie arkuszy.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-106">This task guide will create a periodic journal with a monthly recurrence.</span></span>

1. <span data-ttu-id="b2a2e-107">W Okienku nawigacji otwórz **Moduły > Księga główna > Zadania okresowe > Arkusze okresowe**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-107">Go to **Navigation pane > Modules > General ledger > Periodic tasks > Periodic journals**.</span></span>
2. <span data-ttu-id="b2a2e-108">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-108">Click **New**.</span></span>
3. <span data-ttu-id="b2a2e-109">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-109">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="b2a2e-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b2a2e-111">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-111">In the **Description** field, type a value.</span></span> <span data-ttu-id="b2a2e-112">Opisem po późniejszym pobraniu będzie nazwa arkusza okresowego, dlatego nadaj mu nazwę charakterystyczną.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-112">The description will be the name of the Periodic journal when retrieved later so make sure to give it a relevant name.</span></span>
6. <span data-ttu-id="b2a2e-113">W **okienku akcji** kliknij pozycję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-113">On the **Action pane**, click **Lines**.</span></span> <span data-ttu-id="b2a2e-114">Arkusz okresowy zazwyczaj będzie zawierał kilka wierszy arkusza.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-114">A periodic journal will typically include several journal lines.</span></span> <span data-ttu-id="b2a2e-115">W tym przewodniku po zadaniach będzie jednak dodany tylko jeden wiersz.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-115">this task guide will however only add one line.</span></span>
7. <span data-ttu-id="b2a2e-116">W polu **Data** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-116">In the **Date** field, enter a date.</span></span> <span data-ttu-id="b2a2e-117">Pole **Data** zawiera datę księgowania następnego przeniesienia do arkusza dziennego.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-117">The **Date** field contains the posting date for the next transfer to the daily journal.</span></span> <span data-ttu-id="b2a2e-118">Dla arkuszy, które będą pobierane każdego miesiąca, zaleca się używanie daty w miesiącu księgowania, czyli zazwyczaj pierwszej lub ostatniej daty w okresie.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-118">For journals that will be retrieved each month it is recommended to use the date in the month when it will be posted, typically the first or last date in the period.</span></span> <span data-ttu-id="b2a2e-119">Istnieje możliwość pozostawienia pola Data pustego i podania daty w trakcie pobierania arkusza przy użyciu pola Pusta data.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-119">It is possible to leave the Date field blank and to give a date when the journal is retrieved, using the Empty date field.</span></span> <span data-ttu-id="b2a2e-120">To pole jest automatycznie aktualizowane o następną datę wynikającą z cyklu w trakcie pobierania transakcji.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-120">The field is automatically updated to the next recurring date when transactions are retrieved.</span></span> 
8. <span data-ttu-id="b2a2e-121">W polu **Konto** podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-121">In the **Account** field, specify the desired values.</span></span>
9. <span data-ttu-id="b2a2e-122">Wprowadź lub wybierz wartość w polu **Opis**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-122">In the **Description** field, select a value.</span></span>
10. <span data-ttu-id="b2a2e-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-123">Close the page.</span></span>
11. <span data-ttu-id="b2a2e-124">W polu **Debet** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-124">In the **Debit** field, enter a number.</span></span>
12. <span data-ttu-id="b2a2e-125">W polu **Konto przeciwstawne** podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-125">In the **Offset account** field, specify the desired values.</span></span>
13. <span data-ttu-id="b2a2e-126">W polu **Jednostka** zaznacz opcję „Miesiące”.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-126">In the **Unit** field, select 'Months'.</span></span>
14. <span data-ttu-id="b2a2e-127">W polu **Liczba jednostek** wpisz wartość „1”.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-127">In the **Number of units** field, enter '1'.</span></span>
15. <span data-ttu-id="b2a2e-128">W polu **Ostatnia data** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-128">In the **Last date** field, enter a date.</span></span> <span data-ttu-id="b2a2e-129">Wprowadzanie ostatniego dnia z poprzedniego okresu zapobiegnie omyłkowemu tworzeniu arkusza cyklicznego w nieprawidłowym okresie początkowym.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-129">Entering last date in the preceding period will prevent that the recurring journal by mistake is created in the wrong starting period.</span></span> <span data-ttu-id="b2a2e-130">Ostatni dzień będzie później aktualizowany każdorazowo podczas pobierania arkusza okresowego.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-130">Last date will later on be updated each time the periodic journal is retrieved.</span></span> 
16. <span data-ttu-id="b2a2e-131">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-131">Click **Save**.</span></span>
17. <span data-ttu-id="b2a2e-132">Otwórz **Okienko nawigacji > Moduły > Księga główna > Wpisy w arkuszu > Arkusze finansowe**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-132">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
18. <span data-ttu-id="b2a2e-133">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-133">Click **New**.</span></span>
19. <span data-ttu-id="b2a2e-134">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-134">In the **Name** field, enter or select a value.</span></span>
20. <span data-ttu-id="b2a2e-135">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-135">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="b2a2e-136">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-136">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="b2a2e-137">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-137">In the **Description** field, type a value.</span></span>
23. <span data-ttu-id="b2a2e-138">W **okienku akcji** kliknij pozycję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-138">On the **Action pane**, click **Lines**.</span></span>
24. <span data-ttu-id="b2a2e-139">W **Okienku akcji** kliknij **Arkusze okresowe**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-139">On the **Action pane**, click **Period journal**.</span></span>
25. <span data-ttu-id="b2a2e-140">Kliknij opcję **Wczytanie z arkusza okresowego**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-140">Click **Retrieve journal**.</span></span>
26. <span data-ttu-id="b2a2e-141">Wprowadź datę w polu **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-141">In the **To date** field, enter a date.</span></span> <span data-ttu-id="b2a2e-142">Pole **Do dnia** jest używane jako data graniczna dla okresowych wierszy załącznika.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-142">The **To date** serves as the cutoff date for the periodic voucher lines.</span></span> <span data-ttu-id="b2a2e-143">Zależnie od ustawienia cyklu wartości Ostatnia data i Do dnia dotyczące tego samego wiersza można umieścić więcej niż jeden raz w powstałym arkuszu.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-143">Based on the recurrence setting, the Last date and To date the same line might be included more than once in the resulting journal.</span></span> <span data-ttu-id="b2a2e-144">Pole Do dnia jest automatycznie aktualizowane na podstawie daty sesji z ostatniego razu, gdy wiersz okresowy był przenoszony do arkusza.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-144">To date is automatically updated based on  session date of the last time the periodic line was transferred to a journal.</span></span> 
27. <span data-ttu-id="b2a2e-145">W polu **Numer arkusza okresowego** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-145">In the **Periodic journal number** field, enter or select a value.</span></span>
28. <span data-ttu-id="b2a2e-146">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-146">In the list, click the link in the selected row.</span></span>
29. <span data-ttu-id="b2a2e-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-147">Click **OK**.</span></span> <span data-ttu-id="b2a2e-148">Arkusz okresowy może teraz zostać przejrzany, zatwierdzony lub zaksięgowany, w zależności od wymagań i konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="b2a2e-148">The period journal can now be reviewed, approved or posted depending on requirement and setup.</span></span>   


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]