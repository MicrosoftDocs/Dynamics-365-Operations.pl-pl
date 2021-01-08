---
title: Kontrola kosztu i daty
description: W tym temacie wyjaśniono kontrolę kosztów i dat w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBICostControlWorkspace, EntAssetWorkOrderDateControl, EntAssetWorkOrderForecastCostInfoPart, EntAssetMaintenanceCostTrans, EntAssetWorkOrderDateControlCalcDialog, EntAssetCostControl, EntAssetCostObjectCalendar, EntAssetWorkOrderCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 18373ff16b63ea61a3a4bc38ee7fa0b5e33154b5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435121"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="fb87e-103">Kontrola kosztu i daty</span><span class="sxs-lookup"><span data-stu-id="fb87e-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="fb87e-104">W module Zarządzanie składnikami majątku można obliczać koszty rejestracji usterek składników majątku, aby uzyskać przegląd kosztów rzeczywistych w porównaniu z kosztami budżetowymi składników majątku, loklizacjami czynności konserwacyjnych i zleceniami pracy.</span><span class="sxs-lookup"><span data-stu-id="fb87e-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="fb87e-105">Koszty rzeczywiste są oparte na zaksięgowanych transakcjach.</span><span class="sxs-lookup"><span data-stu-id="fb87e-105">Actual costs are based on posted transactions.</span></span> 

<span data-ttu-id="fb87e-106">Można także wprowadzić obliczenie daty, aby porównać planowane daty rozpoczęcia i zakończenia według rzeczywistych dat rozpoczęcia i zakończenia w zleceniach pracy.</span><span class="sxs-lookup"><span data-stu-id="fb87e-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="fb87e-107">Kontrola kosztów składników majątku, lokalizacji czynności konserwacyjnych i zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="fb87e-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="fb87e-108">Obliczenia wykonane dla składników majątku, lokalizacji czynności konserwacyjnych i zleceń pracy są prawie identyczne.</span><span class="sxs-lookup"><span data-stu-id="fb87e-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="fb87e-109">Jedyna różnica polega na tym, że dla składników majątku i lokalizacji czynności konserwacyjnych można uwzględnić w obliczeniach także podrzędne składniki majątku i lokalizacje podrzędne.</span><span class="sxs-lookup"><span data-stu-id="fb87e-109">The only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="fb87e-110">Data jest datą transakcji, w której rejestracja została zarejestrowana.</span><span class="sxs-lookup"><span data-stu-id="fb87e-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="fb87e-111">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Formant kosztów składników majątku** or **Formant kosztów lokalizacji czynności konserwacyjnych**, or **Zarządzanie składnikami majątku** > **Zapytania** > **Zlecenia pracy** > **Formant kosztów zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="fb87e-112">W oknie dialogowym **Formant kosztów składników majątku** / **Formant kosztów lokalizacji czynności konserwacyjnych** / **Formant kosztów zlecenia pracy** wybierz przedział czasowy, który ma zostać obliczony.</span><span class="sxs-lookup"><span data-stu-id="fb87e-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a time range to be calculated.</span></span>

3. <span data-ttu-id="fb87e-113">W razie potrzeby wybierz zbiór wymiarów finansowych, który ma być uwzględniany w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="fb87e-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="fb87e-114">Wybierz wartość „tak” w przycisku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z kosztem zerowym.</span><span class="sxs-lookup"><span data-stu-id="fb87e-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="fb87e-115">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze kontroli kosztów dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="fb87e-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="fb87e-116">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa hierarchia lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli kosztów usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="fb87e-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="fb87e-117">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze kontroli kosztów na każdym poziomie lokalizacji czynności konserwacyjnych, z którym jest powiązany.</span><span class="sxs-lookup"><span data-stu-id="fb87e-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="fb87e-118">Należy wybrać wartość „tak” na przełączniku **Pokaż otwarty koszt ustalony**, jeśli ta kolumna ma zostać uwzględniona w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="fb87e-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="fb87e-119">Wybierz wartość „tak” na przycisku przełącznika **Uwzględnij środki trwałe**, aby wyświetlić koszty związane z środkami podrzędnymi w postaci oddzielnych wierszy.</span><span class="sxs-lookup"><span data-stu-id="fb87e-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="fb87e-120">Aby ograniczyć wyszukiwanie, można wybrać określone składniki majątku / lokalizacje czynności konserwacyjnych / zlecenia pracy w skróconej karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="fb87e-121">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="fb87e-121">Click **OK** to start the calculation.</span></span>

    <span data-ttu-id="fb87e-122">Na poniższym rysunku pokazano przykład okna dialogowego **Formant kosztów składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

    ![Okno dialogowe Formant kosztów składników majątku](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="fb87e-124">Na stronie **Formant kosztów składników majątku** kliknij przyciski **Grupuj wg**, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="fb87e-124">On the **Asset cost control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="fb87e-125">Wybrane przyciski grupy **Grupuj wg...** są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="fb87e-125">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="fb87e-126">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="fb87e-126">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="fb87e-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="fb87e-127">Example</span></span>

<span data-ttu-id="fb87e-128">Na poniższym zrzucie ekranu pokazano przykład wyniku obliczania w oknie **Formant kosztów składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-128">The screenshot below shows an example of calculation results in **Asset cost control**.</span></span>

- <span data-ttu-id="fb87e-129">W polu **Budżet pierwotny** są wyświetlane koszty budżetowe z prognozy zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="fb87e-129">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="fb87e-130">Pole **Ustalony koszt** pokazuje całkowitą kwota wydatków, które firma zobowiązała się zapłacić.</span><span class="sxs-lookup"><span data-stu-id="fb87e-130">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> 
- <span data-ttu-id="fb87e-131">W polu **Otwarty koszt ustalony** są wyświetlane zobowiązania do zapłaty za towary, godziny i usługi, które zostały zamówione lub przyjęte, ale jeszcze nie zapłacone.</span><span class="sxs-lookup"><span data-stu-id="fb87e-131">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> 
- <span data-ttu-id="fb87e-132">Pole **Koszt rzeczywisty** przedstawia powiązane koszty po zaksięgowaniu wszystkich rejestracji zużycia.</span><span class="sxs-lookup"><span data-stu-id="fb87e-132">The **Actual cost** field shows related costs after all consumption registrations have been posted.</span></span>

![Przykładowe wyniki obliczeń w oknie Formant kosztów składników majątku](media/02-controlling-and-reporting.png)

<span data-ttu-id="fb87e-134">Innym sposobem obliczenia kosztów jest wielokrotne wybranie składników majątku w **Wszystkie składniki majątku** lub **Aktywne składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-134">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="fb87e-135">Następnie kliknij przycisk **Kontrola kosztów** na karcie **Ogólne**. W oknie dialogowym **Formant kosztów składników majątku** wybrane składniki majątku są automatycznie umieszczane w polu **Składnik majątku** na karcie skróconej **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-135">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="fb87e-136">Kliknij **OK** i wyświetlona zostanie kalkulacja kosztów dla wybranych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="fb87e-136">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="fb87e-137">Tę samą procedurę można wykonać w odniesieniu do lokalizacji czynności konserwacyjnych we **Wszystkie lokalizacje czynności konserwacyjnych** lub **Aktywne lokalizacje czynności konserwacyjnych** lub przypadku zleceń pracy **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-137">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>


## <a name="work-order-date-control"></a><span data-ttu-id="fb87e-138">Kontrola dat zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="fb87e-138">Work order date control</span></span>

<span data-ttu-id="fb87e-139">Ta strona umożliwia uzyskanie przeglądu oczekiwanych dat rozpoczęcia i zakończenia w porównaniu z rzeczywistymi datami rozpoczęcia i zakończenia w zleceniach pracy.</span><span class="sxs-lookup"><span data-stu-id="fb87e-139">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="fb87e-140">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Zlecenia pracy** > **Kontrola dat zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-140">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="fb87e-141">Kliknij przycisk **Oblicz**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-141">Click **Calculate**.</span></span>

3. <span data-ttu-id="fb87e-142">Wybierz lokalizację czynności koserwacyjnych w polu **Lokalizacja czynności konserwacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-142">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="fb87e-143">Wstaw zakres, dla którego chcesz dokonać obliczeń w polach **Od dnia** i **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-143">Insert the range for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="fb87e-144">Wszystkie zlecenia pracy z oczekiwaną datą rozpoczęcia w zakresie zostaną uwzględnione.</span><span class="sxs-lookup"><span data-stu-id="fb87e-144">All work orders with expected start date within the range will be included.</span></span>

5. <span data-ttu-id="fb87e-145">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-145">Click **OK**.</span></span>

6. <span data-ttu-id="fb87e-146">Kliknij przyciski **Grupuj wg...**, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="fb87e-146">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="fb87e-147">Wybrane przyciski grupy **Grupuj wg...** są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="fb87e-147">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="fb87e-148">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="fb87e-148">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="fb87e-149">Przykład</span><span class="sxs-lookup"><span data-stu-id="fb87e-149">Example</span></span>

<span data-ttu-id="fb87e-150">Na poniższym zrzucie ekranu pokazano przykładowe wyniki obliczania w oknie **Kontrola dat zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="fb87e-150">The screenshot below shows an example of calculation results in **Work order date control**.</span></span>

- <span data-ttu-id="fb87e-151">Pole **Średnie opóźnienie rozpoczęcia** zawiera różnicę w dniach między planowaną datą rozpoczęcia zlecenia pracy w porównaniu z rzeczywistą datą rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="fb87e-151">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="fb87e-152">Jeśli na przykład rzeczywista data rozpoczęcia wypada na dwa dni przed zaplanowaną datą rozpoczęcia, w tym polu zostanie wyświetlona wartość „-2”.</span><span class="sxs-lookup"><span data-stu-id="fb87e-152">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="fb87e-153">Pole **Średnie opóźnienie zakończenia** zawiera różnicę w dniach między planowaną datą końca zlecenia pracy w porównaniu z rzeczywistą datą zakończenia.</span><span class="sxs-lookup"><span data-stu-id="fb87e-153">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="fb87e-154">Jeśli na przykład rzeczywista data zakończenia wypada na dwa dni przed zaplanowaną datą zakończenia, w tym polu zostanie wyświetlona wartość „3”.</span><span class="sxs-lookup"><span data-stu-id="fb87e-154">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="fb87e-155">W polach **Wystąpienia** jest wyświetlana liczba odchyleń w odniesieniu do daty planowanej i rzeczywistej oraz planowana i rzeczywista data zakończenia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="fb87e-155">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>

![Przykładowe wyniki obliczeń w oknie Kontrola dat zlecenia pracy](media/03-controlling-and-reporting.png)


