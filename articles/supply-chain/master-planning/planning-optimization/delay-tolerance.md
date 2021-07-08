---
title: Tolerancja opóźnienia (dni z ujemnym opóźnieniem)
description: Ten temat zawiera informacje na temat obliczania tolerancji opóźnienia i jej wpływu na tworzenie planowanych zleceń w optymalizacji planowania.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 748e047e89747f2eabccc04a40c79bcb1e6f3dea
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306470"
---
# <a name="delay-tolerance-negative-days"></a><span data-ttu-id="9e36e-103">Tolerancja opóźnienia (dni z ujemnym opóźnieniem)</span><span class="sxs-lookup"><span data-stu-id="9e36e-103">Delay tolerance (negative days)</span></span>

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="9e36e-104">Funkcja tolerancji opóźnienia umożliwia optymalizacji planowania uwzględnienie wartości **Ujemne dni** , która jest ustawiona dla grup pokrycia.</span><span class="sxs-lookup"><span data-stu-id="9e36e-104">The delay tolerance functionality enables Planning Optimization to consider the **Negative days** value that is set for coverage groups.</span></span> <span data-ttu-id="9e36e-105">Służy do przedłużenia okresu tolerancji opóźnienia stosowanego podczas planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="9e36e-105">It's used to extend the delay tolerance period that is applied during master planning.</span></span> <span data-ttu-id="9e36e-106">Pozwoli to uniknąć tworzenia nowych zamówień dostaw, jeśli istniejąca podaż będzie w stanie pokryć popyt w krótkim czasie.</span><span class="sxs-lookup"><span data-stu-id="9e36e-106">In this way, you can avoid creating new supply orders if existing supply will be able to cover the demand after a short delay.</span></span> <span data-ttu-id="9e36e-107">Celem tej funkcji jest określenie, czy tworzenie nowego zamówienia podażowego dla danego popytu ma sens.</span><span class="sxs-lookup"><span data-stu-id="9e36e-107">The purpose of the functionality is to determine whether it makes sense to create a new supply order for a given demand.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="9e36e-108">Włączanie funkcji w systemie</span><span class="sxs-lookup"><span data-stu-id="9e36e-108">Turn on the feature in your system</span></span>

<span data-ttu-id="9e36e-109">Aby udostępnić funkcję w systemie, przejdź do modułu [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Ujemne dni w optymalizacji planowania*.</span><span class="sxs-lookup"><span data-stu-id="9e36e-109">To make the delay tolerance functionality available in your system, go to [Feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Negative days for Planning Optimization* feature.</span></span>

## <a name="delay-tolerance-in-planning-optimization"></a><span data-ttu-id="9e36e-110">Tolerancja opóźnienia w optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="9e36e-110">Delay tolerance in Planning Optimization</span></span>

<span data-ttu-id="9e36e-111">Tolerancja opóźnienia reprezentuje liczbę dni poza czasem realizacji, którą jesteś skłonny odczekać przed zamówieniem nowego uzupełnienia, gdy istniejąca dostawa jest już zaplanowana.</span><span class="sxs-lookup"><span data-stu-id="9e36e-111">Delay tolerance represents the number of days beyond the lead time that you're willing to wait before you order new replenishment when existing supply is already planned.</span></span> <span data-ttu-id="9e36e-112">Tolerancja opóźnień jest określana przy użyciu dni kalendarzowych, a nie dni roboczych.</span><span class="sxs-lookup"><span data-stu-id="9e36e-112">Delay tolerance is defined by using calendar days, not business days.</span></span>

<span data-ttu-id="9e36e-113">W planowaniu głównym, podczas obliczania przez system tolerancji opóźnienia, jest ono rozważane przy ustawieniu **Liczby dni z ujemnym czasem**.</span><span class="sxs-lookup"><span data-stu-id="9e36e-113">At the time of master planning, when the system calculates the delay tolerance, it considers the **Negative days** setting.</span></span> <span data-ttu-id="9e36e-114">**Liczbę dni z ujemnym stanem** można określić albo na stronie **Zapotrzebowanie na towar**, albo na stronie **Grupy zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="9e36e-114">You can set the **Negative days** value on either the **Coverage groups** page or the **Item coverage** page.</span></span>

<span data-ttu-id="9e36e-115">System łączy obliczenia tolerancji opóźnienia z *najbliższą datą uzupełnienia*, która jest równa dzisiejszej dacie plus czas realizacji.</span><span class="sxs-lookup"><span data-stu-id="9e36e-115">The system links the delay tolerance calculation to the *earliest replenishment date*, which equals today's date plus the lead time.</span></span> <span data-ttu-id="9e36e-116">Tolerancja opóźnienia jest obliczana przy użyciu następującej formuły, w której wartość *max()* to większa z dwóch wartości:</span><span class="sxs-lookup"><span data-stu-id="9e36e-116">The delay tolerance is calculated by using following formula, where *max()* finds the larger of two values:</span></span>

<span data-ttu-id="9e36e-117">*maks.(Najwcześniejsza data uzupełnienia, Termin realizacji zapotrzebowania)* - *Termin realizacji zapotrzebowania* + *Dni ujemne*</span><span class="sxs-lookup"><span data-stu-id="9e36e-117">*max(Earliest replenishment date, Demand due date)* – *Demand due date* + *Negative days*</span></span>

<span data-ttu-id="9e36e-118">Formuła gwarantuje, że planowanie główne nie będzie tworzyć nowych zamówień dostaw, jeśli w czasie realizacji produktu będzie istniała wystarczająca dostawa.</span><span class="sxs-lookup"><span data-stu-id="9e36e-118">This formula ensures that master planning doesn't create new supply orders when enough supply exists during the product lead time.</span></span>

> [!NOTE]
> <span data-ttu-id="9e36e-119">Obliczanie tolerancji opóźnienia w optymalizacji planowania wykorzystuje zawsze dynamiczne obliczanie dni ujemnych z wbudowanego planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="9e36e-119">The delay tolerance calculation in Planning Optimization always uses the dynamic negative days calculation from built-in master planning.</span></span> <span data-ttu-id="9e36e-120">Ustawienie **Użyj dynamicznej liczby dni ujemnych** na stronie **Parametry planowania głównego** nie ma wpływu na to zachowanie.</span><span class="sxs-lookup"><span data-stu-id="9e36e-120">The **Use dynamic negative days** setting on the **Master planning parameters** page has no effect on this behavior.</span></span>

<span data-ttu-id="9e36e-121">Jeśli istniejąca podaż implikuje opóźnienie popytu, które jest mniejsze lub równe obliczonej tolerancji opóźnienia, optymalizacja planowania łączy istniejącą podaż z popytem.</span><span class="sxs-lookup"><span data-stu-id="9e36e-121">If the existing supply implies a demand delay that is less than or equal to the calculated delay tolerance, Planning Optimization pegs existing supply with the demand.</span></span> <span data-ttu-id="9e36e-122">W niektórych przypadkach lepiej jest opóźnić popyt niż skończyć z nadpodażą.</span><span class="sxs-lookup"><span data-stu-id="9e36e-122">In some cases, it's better to delay the demand than to end up with oversupply.</span></span>

<span data-ttu-id="9e36e-123">Poniższe podrozdziały przedstawiają przykłady, które pokazują, jak tolerancja opóźnień wpływa na tworzenie planowanych zleceń w optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="9e36e-123">The following subsections provide examples that show how delay tolerance affects the creation of planned orders in Planning Optimization.</span></span>

### <a name="example-1"></a><span data-ttu-id="9e36e-124">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="9e36e-124">Example 1</span></span>

<span data-ttu-id="9e36e-125">Produkt ma następującą konfigurację:</span><span class="sxs-lookup"><span data-stu-id="9e36e-125">A product has the following configuration:</span></span>

- <span data-ttu-id="9e36e-126">**Czas realizacji:** *10*</span><span class="sxs-lookup"><span data-stu-id="9e36e-126">**Lead time:** *10*</span></span>
- <span data-ttu-id="9e36e-127">**Ilość dni z ujemnym stanem magazynu:** *2*</span><span class="sxs-lookup"><span data-stu-id="9e36e-127">**Negative days:** *2*</span></span>

<span data-ttu-id="9e36e-128">W przypadku tego produktu istnieje następująca podaż i popyt:</span><span class="sxs-lookup"><span data-stu-id="9e36e-128">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="9e36e-129">**Popyt dzisiaj:** Zamówienie sprzedaży na ilość 10</span><span class="sxs-lookup"><span data-stu-id="9e36e-129">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="9e36e-130">**Dostawa w ciągu 12 dni:** Zamówienie zakupu na ilość 10</span><span class="sxs-lookup"><span data-stu-id="9e36e-130">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="9e36e-131">Istniejąca podaż może pokryć zapotrzebowanie w ciągu 12 dni, a okres ten jest równy tolerancji opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="9e36e-131">Existing supply can cover the demand within 12 days, and that period equals the delay tolerance.</span></span> <span data-ttu-id="9e36e-132">W związku z tym podczas pracy planowania głównego nie są tworzone żadne planowane zlecenia.</span><span class="sxs-lookup"><span data-stu-id="9e36e-132">Therefore, when master planning runs, no planned orders are created.</span></span>

### <a name="example-2"></a><span data-ttu-id="9e36e-133">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="9e36e-133">Example 2</span></span>

<span data-ttu-id="9e36e-134">Produkt ma następującą konfigurację:</span><span class="sxs-lookup"><span data-stu-id="9e36e-134">A product has the following configuration:</span></span>

- <span data-ttu-id="9e36e-135">**Czas realizacji:** *10*</span><span class="sxs-lookup"><span data-stu-id="9e36e-135">**Lead time:** *10*</span></span>
- <span data-ttu-id="9e36e-136">**Ilość dni z ujemnym stanem magazynu:** *0*</span><span class="sxs-lookup"><span data-stu-id="9e36e-136">**Negative days:** *0*</span></span>

<span data-ttu-id="9e36e-137">W przypadku tego produktu istnieje następująca podaż i popyt:</span><span class="sxs-lookup"><span data-stu-id="9e36e-137">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="9e36e-138">**Popyt dzisiaj:** Zamówienie sprzedaży na ilość 10</span><span class="sxs-lookup"><span data-stu-id="9e36e-138">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="9e36e-139">**Dostawa w ciągu 12 dni:** Zamówienie zakupu na ilość 10</span><span class="sxs-lookup"><span data-stu-id="9e36e-139">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="9e36e-140">Istniejąca podaż może pokrywać popyt tylko po 12 dniach.</span><span class="sxs-lookup"><span data-stu-id="9e36e-140">Existing supply can cover the demand only after 12 days.</span></span> <span data-ttu-id="9e36e-141">Jednak tolerancja opóźnienia wynosi 10 dni.</span><span class="sxs-lookup"><span data-stu-id="9e36e-141">However, the delay tolerance is 10 days.</span></span> <span data-ttu-id="9e36e-142">Dlatego podczas planowania głównego tworzone jest zamówienie planowane na ilość 10.</span><span class="sxs-lookup"><span data-stu-id="9e36e-142">Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>

### <a name="example-3"></a><span data-ttu-id="9e36e-143">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="9e36e-143">Example 3</span></span>

<span data-ttu-id="9e36e-144">Produkt ma następującą konfigurację:</span><span class="sxs-lookup"><span data-stu-id="9e36e-144">A product has the following configuration:</span></span>

- <span data-ttu-id="9e36e-145">**Czas realizacji:** *10*</span><span class="sxs-lookup"><span data-stu-id="9e36e-145">**Lead time:** *10*</span></span>
- <span data-ttu-id="9e36e-146">**Ilość dni z ujemnym stanem magazynu:** *2*</span><span class="sxs-lookup"><span data-stu-id="9e36e-146">**Negative days:** *2*</span></span>

<span data-ttu-id="9e36e-147">W przypadku tego produktu istnieje następująca podaż i popyt:</span><span class="sxs-lookup"><span data-stu-id="9e36e-147">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="9e36e-148">**Popyt za 11 dni:** Zamówienie sprzedaży na ilość 10</span><span class="sxs-lookup"><span data-stu-id="9e36e-148">**Demand in 11 days:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="9e36e-149">**Dostawa w ciągu 14 dni:** Zamówienie zakupu na ilość 10</span><span class="sxs-lookup"><span data-stu-id="9e36e-149">**Supply in 14 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="9e36e-150">Istniejąca podaż może pokrywać popyt tylko po 3 dniach.</span><span class="sxs-lookup"><span data-stu-id="9e36e-150">Existing supply can cover the demand only after three days.</span></span> <span data-ttu-id="9e36e-151">Jednak tolerancja opóźnienia wynosi 2 dni.</span><span class="sxs-lookup"><span data-stu-id="9e36e-151">However, the delay tolerance is two days.</span></span> <span data-ttu-id="9e36e-152">(W tym przypadku tolerancja opóźnienia obejmuje tylko dwa dni ujemne.</span><span class="sxs-lookup"><span data-stu-id="9e36e-152">(In this case, the delay tolerance includes only the two negative days.</span></span> <span data-ttu-id="9e36e-153">Data zapotrzebowania nie jest uwzględniana, ponieważ jest po czasie realizacji produktu). Dlatego przy uruchomieniu planowania głównego zostanie utworzone planowane zamówienie na ilość 10 sztuk.</span><span class="sxs-lookup"><span data-stu-id="9e36e-153">The demand date isn't included because it's after the product lead time.) Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>
