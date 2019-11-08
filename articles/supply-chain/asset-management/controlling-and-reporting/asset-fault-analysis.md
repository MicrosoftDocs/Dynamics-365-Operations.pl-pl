---
title: Analiza usterek składników majątku
description: W tym temacie wyjaśniono analizę usterek składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 43772903f6845409cb33c7f2a13a049a3e9aa208
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652409"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="5c31e-103">Analiza usterek składników majątku</span><span class="sxs-lookup"><span data-stu-id="5c31e-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="5c31e-104">W module Zarządzanie składnikami majątku można analizować rejestracje usterek składników majątku, aby uzyskać przegląd łącznej liczby usterek zarejestrowanych w danym okresie.</span><span class="sxs-lookup"><span data-stu-id="5c31e-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="5c31e-105">Rejestracje usterek mogą być analizowane z różnych perspektyw, na przykład z nastawieniem na składniki majątku, typy składników majątku, lokalizacje czynności konserwacyjnych, objawy usterek lub typy usterek.</span><span class="sxs-lookup"><span data-stu-id="5c31e-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="5c31e-106">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Analiza usterek składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="5c31e-107">W oknie **Obliczanie analizy usterek składników majątku** można użyć pola **Poziom**, aby określić, jak bardzo szczegółowe mają być wiersze błędów składniku majątku dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="5c31e-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="5c31e-108">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje struktura lokalizacji czynności konserwacyjnych wielopoziomowej, wszystkie wiersze usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji funkcjonalnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="5c31e-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
        
    <span data-ttu-id="5c31e-109">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze usterek składnika majątku na każdym poziomie lokalizacji czynności konserwacyjnych, z którym jest powiązany.</span><span class="sxs-lookup"><span data-stu-id="5c31e-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="5c31e-110">Aby ograniczyć wyszukiwanie, można wybrać określone składniki majątku, daty usterek, przyczyny usterek i środki zaradcze w skróconej karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="5c31e-111">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="5c31e-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="5c31e-112">Na karcie **Analiza usterek składników majątku** kliknij jeden lub więcej przycisków **Grupuj wg**, aby wyświetlić poziom szczegółowości, który ma być widoczny.</span><span class="sxs-lookup"><span data-stu-id="5c31e-112">On the **Asset fault analysis** tab, click one or more **Group by** buttons to display the detail level you want to see.</span></span> <span data-ttu-id="5c31e-113">Przyciski aktywne są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="5c31e-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="5c31e-114">Aby uaktywnić lub dezaktywować przycisk, należy kliknąć na niego.</span><span class="sxs-lookup"><span data-stu-id="5c31e-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="5c31e-115">Kliknij **Zaktualizuj obliczenia** obliczenia, aby wyświetlić wybrane opcje na ekranie.</span><span class="sxs-lookup"><span data-stu-id="5c31e-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="5c31e-116">Przy każdym aktywowaniu lub dezaktywowaniu przycisku **Grupuj wg** pamiętaj o kliknięciu przycisku **Zaktualizuj obliczenia**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-116">Every time you activate or deactivate a **Group by** button, remember to click the **Update calculations** button.</span></span> <span data-ttu-id="5c31e-117">Jest to wymagane, ponieważ podczas ponownego obliczania prawdopodobieństwa wystąpienia błędów jest przetwarzana duża ilość danych.</span><span class="sxs-lookup"><span data-stu-id="5c31e-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

## <a name="examples"></a><span data-ttu-id="5c31e-118">Przykłady</span><span class="sxs-lookup"><span data-stu-id="5c31e-118">Examples</span></span>

<span data-ttu-id="5c31e-119">Istnieje wiele sposobów analizowania rejestracji usterek.</span><span class="sxs-lookup"><span data-stu-id="5c31e-119">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="5c31e-120">Ta sekcja zawiera pięć przykładów pokazujących, jak różne wybory danych udostępniają więcej szczegółów i lepszy wgląd w informacje podczas analizowania rejestracji usterek.</span><span class="sxs-lookup"><span data-stu-id="5c31e-120">This section has five examples of how different data selections can provide more insight and detail when analyzing asset fault registrations.</span></span>

### <a name="group-by-symptoms"></a><span data-ttu-id="5c31e-121">Grupowanie według objawów</span><span class="sxs-lookup"><span data-stu-id="5c31e-121">Group by symptoms</span></span>

<span data-ttu-id="5c31e-122">Na poniższym zrzucie jest zaznaczony tylko przycisk **Objaw**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-122">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="5c31e-123">Przeprowadzono rejestracje błędów na trzech objawach usterek: „przeciek powietrza”, „przepalony bezpiecznik” i „wystąpiło zacięcie sprzętu”.</span><span class="sxs-lookup"><span data-stu-id="5c31e-123">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="5c31e-124">W kolumnie **Prawdopodobieństwo (%)** wszystkie wartości procentowe sumują się do 100%.</span><span class="sxs-lookup"><span data-stu-id="5c31e-124">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="5c31e-125">W tej analizie błędów prawdopodobieństwo jest oparte na wszystkich wpisach **Objawów**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-125">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![Rysunek 1](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a><span data-ttu-id="5c31e-127">Grupowanie według objawów i okresu</span><span class="sxs-lookup"><span data-stu-id="5c31e-127">Group by symptoms and time period</span></span>

<span data-ttu-id="5c31e-128">W poniższym zrzucie ekranu **Rok** i **Miesiąc** zostały dodane, aby pokazać jak można wyświetlić rejestracje usterek w wybranym okresie.</span><span class="sxs-lookup"><span data-stu-id="5c31e-128">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="5c31e-129">Objawy usterki są teraz widoczne jako rejestracje na rok/miesiąc.</span><span class="sxs-lookup"><span data-stu-id="5c31e-129">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="5c31e-130">Jeśli w kolumnie **Prawdopodobieństwo (%)** zostaną dodane wszystkie wartości procentowe dla każdego miesiąca, sumują się do 100%.</span><span class="sxs-lookup"><span data-stu-id="5c31e-130">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="5c31e-131">W tej analizie błędów prawdopodobieństwo jest oparte na wszystkich wpisach **Objawów**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-131">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="5c31e-132">Jeśli składnik majątku zawiera dużą liczbę wierszy, ale w wierszu znajduje się duża wartość procentowa, to znaczy, że jest to wskaźnik usterki służący do dokładnego zbadania, aby znaleźć sposób ograniczenia liczby rejestracji dla tego objawu usterki.</span><span class="sxs-lookup"><span data-stu-id="5c31e-132">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Rysunek 2](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a><span data-ttu-id="5c31e-134">Grupowanie według wielu objawów i składników majątku</span><span class="sxs-lookup"><span data-stu-id="5c31e-134">Group by multiple symptoms and assets</span></span>

<span data-ttu-id="5c31e-135">Połączenie składników majątku i typu składnika majątku jest używana jako podstawa dla obliczeń przedstawionych w trzech poniższych zrzutach, które spowodują zwiększenie poziomu szczegółowości.</span><span class="sxs-lookup"><span data-stu-id="5c31e-135">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  

<span data-ttu-id="5c31e-136">Na ogół przyciski w graupach w okienku akcji **Grupuj według dat**, **Grupuj według składników majątku**, **Grupuj według lokalizacji czynności konserwacyjnych**, a także przycisk **Usterka** (Identyfikator usterki) zawierają okresy lub relacje składników majątku.</span><span class="sxs-lookup"><span data-stu-id="5c31e-136">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** action pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="5c31e-137">Przyciski **Objaw**, **Obszar**, **Typ**, **Przyczyna** i **Środek zaradczy** są używane w module zarządzanie błędami do analizowania rejestracji usterek i okreaślania problematycznych obszarów.</span><span class="sxs-lookup"><span data-stu-id="5c31e-137">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="5c31e-138">**Grupowanie według objawu, składnika majątku i typu składnika majątku**</span><span class="sxs-lookup"><span data-stu-id="5c31e-138">**Group by symptom, asset, and asset type**</span></span>

<span data-ttu-id="5c31e-139">W poniższym zrzucie ekranu dodano **Składnik majątku** i **Typ składnika majątku**, co daje więcej szczegółowych informacji dotyczących rejestracji błędów.</span><span class="sxs-lookup"><span data-stu-id="5c31e-139">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="5c31e-140">Objawy błędów są teraz podzielone w kombinacjach **Składnik majątku** / **Typ składnika majątku** / **Objaw**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-140">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="5c31e-141">Jeśli w kolumnie **Prawdopodobieństwo (%)** zostaną dodane wszystkie wartości procentowe dla odpowiednich kombinacji **Składnik majątku** / **Typ składnika majątku** / **Objaw**, które sumują się do 100%.</span><span class="sxs-lookup"><span data-stu-id="5c31e-141">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="5c31e-142">W tej analizie błędów prawdopodobieństwo jest oparte na wszystkich rejestracjach **Objawów**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-142">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="5c31e-143">Jeśli składnik majątku zawiera dużą liczbę wierszy, ale w wierszu znajduje się duża wartość procentowa, to znaczy, że jest to wskaźnik usterki służący do dokładnego zbadania, aby znaleźć sposób ograniczenia liczby rejestracji dla tego objawu usterki.</span><span class="sxs-lookup"><span data-stu-id="5c31e-143">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Rysunek 3](media/08-controlling-and-reporting.png)

<span data-ttu-id="5c31e-145">**Grupowanie według dwóch objawów, składnika majątku i typu składnika majątku**</span><span class="sxs-lookup"><span data-stu-id="5c31e-145">**Group by two symptoms, asset, and asset type**</span></span>

<span data-ttu-id="5c31e-146">W poniższym zrzucie ekranu dodano **Obszar** do **Objaw**, **Składnik majątku** i **Typ składnika majątku**, co daje więcej szczegółowych informacji dotyczących rejestracji błędów.</span><span class="sxs-lookup"><span data-stu-id="5c31e-146">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="5c31e-147">Jeśli w kolumnie **Prawdopodobieństwo (%)** zostaną dodane wszystkie wartości procentowe dla odpowiednich kombinacji **Składnik majątku** / **Typ składnika majątku** / **Objaw** dla danego składnika majątku, to wartości sumują się do 100%.</span><span class="sxs-lookup"><span data-stu-id="5c31e-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="5c31e-148">W tej analizie błędów prawdopodobieństwo jest oparte na kombinacji **Objaw** i **Obszar**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-148">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="5c31e-149">Jeśli składnik majątku zawiera dużą liczbę wierszy, ale w wierszu wyróżnia się duża wartość procentowa, to znaczy, że jest to wskaźnik obszaru usterki służący do dokładnego zbadania, aby znaleźć sposób ograniczenia liczby rejestracji dla tego obszaru usterki.</span><span class="sxs-lookup"><span data-stu-id="5c31e-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![Rysunek 4](media/09-controlling-and-reporting.png)

<span data-ttu-id="5c31e-151">**Grupowanie według trzech objawów, składnika majątku i typu składnika majątku**</span><span class="sxs-lookup"><span data-stu-id="5c31e-151">**Group by three symptom, asset, and asset type**</span></span>

<span data-ttu-id="5c31e-152">W poniższym zrzutie ekranu dodano **Typ**, a w tym przykładzie jest pokazane najbardziej szczegółowe obliczenie.</span><span class="sxs-lookup"><span data-stu-id="5c31e-152">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="5c31e-153">Jeśli w kolumnie **Prawdopodobieństwo (%)** zostaną dodane wszystkie wartości procentowe dla odpowiednich kombinacji **Składnik majątku** / **Typ składnika majątku** / **Objaw** dla danego składnika majątku, to wartości sumują się do 100%.</span><span class="sxs-lookup"><span data-stu-id="5c31e-153">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="5c31e-154">W tej analizie błędów prawdopodobieństwo jest oparte na kombinacji **Objaw**, **Obszar** i **Typ**</span><span class="sxs-lookup"><span data-stu-id="5c31e-154">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="5c31e-155">Jeśli składnik majątku zawiera dużą liczbę wierszy, ale w wierszu wyróżnia się duża wartość procentowa, to znaczy, że jest to wskaźnik typu usterki służący do dokładnego zbadania, aby znaleźć sposób ograniczenia liczby rejestracji dla tego typu usterki.</span><span class="sxs-lookup"><span data-stu-id="5c31e-155">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![Rysunek 5](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="5c31e-157">Aby zapoznać się z omówieniem wszystkich rejestracji błędów utworzonych na zleceniach pracy i żądaniach konserwacji kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Usterki składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="5c31e-157">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="5c31e-158">Na stronie **Usterki składnika majątku** wybierz rejestrację usterek składnika majątku i rozwiń okienko **Informacje pokrewne**, aby wyświetlić informacje dotyczące powiązanego zlecenia pracy lub żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="5c31e-158">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>

