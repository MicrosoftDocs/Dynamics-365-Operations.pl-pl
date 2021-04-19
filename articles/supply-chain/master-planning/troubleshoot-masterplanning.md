---
title: Rozwiązywanie problemów dotyczących planowania głównego
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z planowaniem głównym.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8e78634c0efb1c401297559ce40b2ca30519f3bf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809477"
---
# <a name="troubleshoot-master-planning"></a><span data-ttu-id="f4b8a-103">Rozwiązywanie problemów dotyczących planowania głównego</span><span class="sxs-lookup"><span data-stu-id="f4b8a-103">Troubleshoot master planning</span></span>

<span data-ttu-id="f4b8a-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z planowaniem głównym.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-104">This topic describes how to fix issues that you might encounter while you work with master planning.</span></span>

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a><span data-ttu-id="f4b8a-105">Rozłożenie listy składowej zachowuje się inaczej w przypadku ustalonych zleceń produkcyjnych i szacowanych zleceń produkcyjnych dla ręcznie utworzonych prac.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-105">Bill of materials explosion behaves differently for firmed production orders and for estimated production orders for manually created work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f4b8a-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="f4b8a-106">Issue description</span></span>

<span data-ttu-id="f4b8a-107">Po utrwaleniu zlecenia produkcyjnego towary nie są rozkładane podczas rozkłądania listy składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="f4b8a-107">When a production order is firmed, the items aren't exploded when you explode the bill of materials (BOM).</span></span> <span data-ttu-id="f4b8a-108">Jednak podczas ręcznego tworzenia zlecenia produkcyjnego, a następnie szacowania zlecenia produkcyjnego, towary są rozkładane.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-108">However, when you manually create a work order and then estimate the production order, the items are exploded.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f4b8a-109">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="f4b8a-109">Issue resolution</span></span>

<span data-ttu-id="f4b8a-110">System działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-110">The system is working as expected.</span></span> <span data-ttu-id="f4b8a-111">Rozłożenie występujące podczas ustalania zlecenia produkcyjnego wskazuje zamówienie planowane, ale zamówienie planowane chyba nie jest obecnie ustalone w tym przypadku.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-111">The explosion that occurs when the production order is firmed will point to the planned order, but it doesn't appear that the planned order is currently firmed in this case.</span></span> <span data-ttu-id="f4b8a-112">Jeśli jednak zlecenie produkcyjne zostało oszacowane, rozłożenie jest wyzwalane ze zwolnionego zlecenia produkcyjnego, w którym nie istnieje planowane zamówienie</span><span class="sxs-lookup"><span data-stu-id="f4b8a-112">However, if the production order has been estimated, the explosion is triggered from the released production order where no planned order exists.</span></span>

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a><span data-ttu-id="f4b8a-113">Wartość Opóźnienia nie jest aktualizowana podczas ponownego planowania zamówienia planowanego.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-113">The Delay value isn't updated when I reschedule a planned order.</span></span>

<span data-ttu-id="f4b8a-114">Aby zaktualizować opóźnienie zamówień planowanych, otwórz okno dialogowe **Ponowne planowanie** dla zamówienia planowanego.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-114">To update the delay for planned orders, open the **Rescheduling** dialog box for the planned order.</span></span> <span data-ttu-id="f4b8a-115">Na skróconej karcie **Rozłożenie** należy upewnić się, że opcja **Wykonaj rozłożenie po zmianie harmonogramu** jest ustawiona na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-115">On the **Explosion** FastTab, make sure that the **Perform explosion after rescheduling** option is set to *Yes*.</span></span>

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a><span data-ttu-id="f4b8a-116">Planowanie produkcji nie uwzględnia marginesów bezpieczeństwa, które są ustawione dla pokrycia pozycji dla ustalonej dostawy.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-116">Production scheduling doesn't consider the safety margins that are set on the item coverage for pegged supply.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f4b8a-117">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="f4b8a-117">Issue description</span></span>

<span data-ttu-id="f4b8a-118">Planowanie główne uwzględnia marginesy bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-118">Master planning considers the safety margins.</span></span> <span data-ttu-id="f4b8a-119">Jednak marginesy bezpieczeństwa są ignorowane podczas planowania zaplanowanych zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-119">However, the safety margins are ignored when planned production orders are scheduled.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f4b8a-120">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="f4b8a-120">Issue resolution</span></span>

<span data-ttu-id="f4b8a-121">Marginesy są brane pod uwagę tylko podczas planowania głównego, a nie w planowaniu ręcznym.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-121">Margins are considered only during master planning, not during manual scheduling.</span></span> <span data-ttu-id="f4b8a-122">Marginesy są tak zaprojektowane, aby pełniły charakter buforu podczas fazy planowania, co umożliwia podanie pewnego „marginesu” dla właściwego procesu.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-122">Margins are designed to act as a buffer during the planning phase, to give some "margin" for the actual process.</span></span>

<span data-ttu-id="f4b8a-123">Aby uzyskać pożądany wynik, można usunąć margines.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-123">To get the desired result, you can remove the margin.</span></span> <span data-ttu-id="f4b8a-124">Następnie należy zaktualizować marszrutę, aby obejmowała ona żądany czas (np. jako czas oczekiwania).</span><span class="sxs-lookup"><span data-stu-id="f4b8a-124">The route must then be updated so that it includes the desired time (for example, as queue time).</span></span> <span data-ttu-id="f4b8a-125">Zarówno planowanie główne, jak i planowanie ręczne, powinny dawać ten sam wynik.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-125">Both master planning and manual scheduling should then produce the same result.</span></span>

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a><span data-ttu-id="f4b8a-126">Zamówienia planowane są generowane nawet wtedy, gdy istnieją towary w magazynie i istnieją już dla nich zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-126">Planned orders are generated even though we have items in stock and production orders already exist for them.</span></span>

<span data-ttu-id="f4b8a-127">Można rozwiązać ten problem, zwiększając wartość **Ilość dni z dodatnim stanem magazynu** dla odpowiednich grup na stronie **Grupa zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-127">You might be able to fix this issue by increasing the **Positive days** value for the relevant groups on the **Coverage group** page.</span></span> <span data-ttu-id="f4b8a-128">Ta zmiana spowoduje, że system określi, czy dla popytu można używać dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-128">This change will cause the system to determine whether on-hand inventory can be used for the demand.</span></span> <span data-ttu-id="f4b8a-129">Wtedy nowe zamówienie planowane nie zostanie wygenerowane dla towarów znajdujących się w magazynie.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-129">Then a new planned order won't be generated for the items that are in stock.</span></span>

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a><span data-ttu-id="f4b8a-130">Wydaje się, że planowanie główne nie uwzględnia ograniczeń zdolności produkcyjnej i obejmuje planowanie większe niż dostępna zdolność produkcyjna.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-130">Master planning doesn't seem to respect capacity limitations and is scheduling more than the available capacity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f4b8a-131">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="f4b8a-131">Issue description</span></span>

<span data-ttu-id="f4b8a-132">W przypadku korzystania z planowania operacji w przypadku, gdy wydajność jest ograniczona, a trasa określa mieszankę wymagań zarówno dla grupy zasobów, jak i dla poszczególnych zasobów, istnieje niewielka szansa na przepełnienie rezerwacji ze względu na sposób, w jaki algorytm sprawdza poprawność pod kątem konfliktów pojemności.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-132">When you use operation scheduling where there is finite capacity, and where the route specifies a mix of requirements for both a resource group and individual resources, there is a small chance of overbooking because of the way that the algorithm validates for capacity conflicts.</span></span> <span data-ttu-id="f4b8a-133">Taka rezerwacja ponad możliwości może wystąpić podczas używania pomocników w celu uruchomienia planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-133">This overbooking can occur when you use helpers to run master planning.</span></span> <span data-ttu-id="f4b8a-134">Najprawdopodobniej dzieje się tak, jeśli istnieje wiele zadań o stosunkowo krótkim czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-134">It's most likely to occur if there are many jobs that have a relatively short runtime.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f4b8a-135">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="f4b8a-135">Issue resolution</span></span>

<span data-ttu-id="f4b8a-136">Jeśli konieczne jest, aby w planowaniu operacji nie dochodziło do przepełnienia rezerwacji, można uczynić planowanie jednowątkową częścią planowania głównego, włączając opcję **Dokładne ograniczone zdolności produkcyjne do planowania operacji** na stronie **Parametry planowania głównego**.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-136">If it's essential that no overbooking occur for operation scheduling, you can make the scheduling part of master planning single-threaded by turning on the **Accurate finite capacity for Operation Scheduling** option on the **Master planning parameters** page.</span></span> <span data-ttu-id="f4b8a-137">Ta opcja jest domyślnie niedostępna.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-137">This option isn't available by default.</span></span> <span data-ttu-id="f4b8a-138">Musisz ręcznie dodać ją do strony, używając funkcji personalizacji.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-138">You must manually add it to the page by using personalization features.</span></span> <span data-ttu-id="f4b8a-139">W przypadku korzystania z tej opcji planowanie będzie działać wolniej z powodu braku równoległego przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-139">When you use this option, scheduling will run more slowly because of the lack of parallel processing.</span></span>

## <a name="planned-orders-take-a-long-time-to-update"></a><span data-ttu-id="f4b8a-140">Aktualizacja zamówień planowanych zajmuje dużo czasu.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-140">Planned orders take a long time to update.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f4b8a-141">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="f4b8a-141">Issue description</span></span>

<span data-ttu-id="f4b8a-142">Podczas aktualizowania ilości zapotrzebowania i/lub daty dostawy w planowanym zamówieniu zapisanie aktualizacji zajmuje zwykle co najmniej 30 sekund na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-142">When updating the requirement quantity and/or delivery date on a planned order, it typically takes at least 30 seconds per order to save the update.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f4b8a-143">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="f4b8a-143">Issue resolution</span></span>

<span data-ttu-id="f4b8a-144">Jest to znany błąd dotyczący wbudowanego aparatu planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-144">This is a known issue with the built-in master planning engine.</span></span> <span data-ttu-id="f4b8a-145">Jest to spowodowane przez podstawowe automatyczne rozłożenie przez strukturę BOM podczas edycji.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-145">It is caused by the underlying auto explosion through the BOM structure during edits.</span></span> <span data-ttu-id="f4b8a-146">Ten problem rozwiązano w optymalizacji planowania, w której planista może aktualizować i zatwierdzać odpowiednie zamówienia oraz, w razie potrzeby, uruchamiać przebieg planowania w celu zaktualizowania zamówień planowanych dla podstawowej struktury BOM.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-146">This issue is addressed in Planning Optimization, where a planner can update and approve the relevant orders and, when desired, trigger a planning run to update planned orders for the underlying BOM structure.</span></span>

<span data-ttu-id="f4b8a-147">Jednym ze sposobów poprawienia wydajności przy użyciu wbudowanego aparatu planowania głównego jest wykonanie następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="f4b8a-147">One way to improve performance with the built-in master planning engine is to do the following:</span></span>

1. <span data-ttu-id="f4b8a-148">Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-148">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="f4b8a-149">Wybierz plan.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-149">Select a plan.</span></span>
1. <span data-ttu-id="f4b8a-150">Rozwiń kartę skróconą **Horyzont czasowy w dniach**.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-150">Expand the **Time fence in days** FastTab.</span></span>
1. <span data-ttu-id="f4b8a-151">Ustawienie **Rozłożenie** na wartość *Tak* i ustawienie pola poniżej tego ustawienia na wartość 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="f4b8a-151">Set **Explosion** to *Yes*, and set the field below this setting to 0 (zero).</span></span>

> [!NOTE]
> <span data-ttu-id="f4b8a-152">Ograniczy to okres rozłożeń wykonywanych dla tego planu głównego do jednego dnia.</span><span class="sxs-lookup"><span data-stu-id="f4b8a-152">This will limit the period for explosions performed for this master plan to a single day.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]