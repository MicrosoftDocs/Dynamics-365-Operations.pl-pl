---
title: Kontrola godzin pracy
description: W tym temacie opisano typy kontroli godzin pracy w module Zarządzanie składnikami majątku.
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
ms.openlocfilehash: 916e7b8d5d494dbae0659504957f7f0798a6834b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918379"
---
# <a name="work-hour-control"></a><span data-ttu-id="ddecd-103">Kontrola godzin pracy</span><span class="sxs-lookup"><span data-stu-id="ddecd-103">Work hour control</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="ddecd-104">W module Zarządzanie składnikami majątku możesz obliczyć godziny, aby uzyskać przegląd rzeczywistych godzin w porównaniu z godzinami budżetowymi dotyczącymi zasobów, lokalizacji czynności konserwacyjnych lub zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="ddecd-104">In Asset Management, you can calculate hours to get an overview of actual hours compared to budget hours on assets, functional locations, or work orders.</span></span> <span data-ttu-id="ddecd-105">Godziny rzeczywiste są oparte na zaksięgowanych transakcjach.</span><span class="sxs-lookup"><span data-stu-id="ddecd-105">Actual hours are based on posted transactions.</span></span>

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="ddecd-106">Kontrola godzin dla składników majątku, lokalizacji czynności konserwacyjnych i zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="ddecd-106">Work hour control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="ddecd-107">Obliczenia wykonane dla składników majątku, lokalizacji czynności konserwacyjnych i zleceń pracy są prawie identyczne.</span><span class="sxs-lookup"><span data-stu-id="ddecd-107">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="ddecd-108">Tylko różnica polega na tym, że dla składników i lokalizacji czynności konserwacyjnych można uwzględnić w obliczeniach także podpozycje i podlokalizacje.</span><span class="sxs-lookup"><span data-stu-id="ddecd-108">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="ddecd-109">Data jest datą transakcji, w której rejestracja została zarejestrowana.</span><span class="sxs-lookup"><span data-stu-id="ddecd-109">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="ddecd-110">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Formant godzin składnika majątku** lub **Formant godzin lokalizacji czynności konserwacyjnych** lub **Zarządzanie składnikami majątku** > **Zapytania** > **Zlecenia pracy** > **Formant godzin zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="ddecd-110">Click **Asset management** > **Inquiries** > **Assets** > **Asset hour control** or **Functional location hour control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order hour control**.</span></span>

2. <span data-ttu-id="ddecd-111">W oknie **Formant godzin składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="ddecd-111">In the **Asset hour control** dialog, .</span></span>

3. <span data-ttu-id="ddecd-112">W **Formant godzin składnika majątku** / **Formant godzin lokalizacji czynności konserwacyjnych** / **Formant godzin zlecenia pracy** oknie dialogowym wybierz okres, który ma zostać obliczony w polach **od dnia** i **do dnia**.</span><span class="sxs-lookup"><span data-stu-id="ddecd-112">In the **Asset hour control** / **Functional location hour control** / **Work order hour control** dialog, select a period to be calculated in the **From date** and **To date** fields.</span></span>

4. <span data-ttu-id="ddecd-113">W razie potrzeby wybierz **zbiór wymiarów finansowych**, który ma być uwzględniany w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="ddecd-113">If required, select a **Financial dimension set** to be included in the calculation.</span></span>

5. <span data-ttu-id="ddecd-114">Wybierz wartość „tak” w przełączniku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z zero godzin.</span><span class="sxs-lookup"><span data-stu-id="ddecd-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results containing zero hours.</span></span>

6. <span data-ttu-id="ddecd-115">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze kontroli godzin dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="ddecd-115">You can use the **Level** field to indicate how detailed you want the hour control lines to be regarding functional locations.</span></span> <span data-ttu-id="ddecd-116">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa hierarchia lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli godzin usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="ddecd-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all hour control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="ddecd-117">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze kontroli godzin na każdym poziomie lokalizacji czynności konserwacyjnych, z którym jest powiązany.</span><span class="sxs-lookup"><span data-stu-id="ddecd-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all hour control lines on all the functional location levels to which they are related.</span></span>

7. <span data-ttu-id="ddecd-118">Wybierz wartość „tak” na przycisku przełącznika **Uwzględnij środki trwałe**, aby wyświetlić koszty związane z środkami podrzędnymi w postaci oddzielnych wierszy.</span><span class="sxs-lookup"><span data-stu-id="ddecd-118">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="ddecd-119">Aby ograniczyć wyszukiwanie, można wybrać określone składniki majątku / lokalizacje czynności konserwacyjnych / zlecenia pracy w skróconej karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="ddecd-119">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="ddecd-120">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="ddecd-120">Click **OK** to start the calculation.</span></span>

10. <span data-ttu-id="ddecd-121">Na tronie **Formant godzin składnika majątku** w grupach okienka akcji **Grupuj wg...** na stronie Formant kosztów składników majątku kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="ddecd-121">On the **Asset hour control** page, in the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="ddecd-122">Wybrane przyciski okienka akcji są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="ddecd-122">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="ddecd-123">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="ddecd-123">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="ddecd-124">Na poniższym rysunku pokazano przykład obliczania **Formant godzin składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="ddecd-124">The figure below shows an example of an **Asset hour control** calculation.</span></span>

![Rysunek 1](media/04-controlling-and-reporting.png)

<span data-ttu-id="ddecd-126">Innym sposobem obliczenia godziny jest wielokrotne wybranie składników majątku w **Wszystkie składniki majątku** lub **Aktywne składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="ddecd-126">Another way of making an hour calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="ddecd-127">Następnie należy kliknąć przycisk **Formant godzin** w skróconej karcie **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="ddecd-127">Then, you click the **Hour control** button on the **General** FastTab.</span></span> <span data-ttu-id="ddecd-128">Wybrane środki trwałe są automatycznie wstawiane do pola **Składnik majątku** na skróconej karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="ddecd-128">The selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="ddecd-129">Kliknij **OK** woknie dialogowym **Formant godzin składnika majątku**, a następnie zostanie wyświetlona wartość obliczona dla wybranych składników.</span><span class="sxs-lookup"><span data-stu-id="ddecd-129">Click **OK** in the **Asset hour control** dialog, and the calculation for the selected assets is shown.</span></span> <span data-ttu-id="ddecd-130">Tę samą procedurę można wykonać w odniesieniu do lokalizacji czynności konserwacyjnych we **Wszystkie lokalizacje czynności konserwacyjnych** lub **Aktywne lokalizacje czynności konserwacyjnych** lub przypadku zleceń pracy **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="ddecd-130">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>

>[!NOTE]
><span data-ttu-id="ddecd-131">W polu **Budżet pierwotny** są wyświetlane godziny budżetowe z prognozy zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="ddecd-131">The **Original budget** field shows budget hours from the work order forecast.</span></span> <span data-ttu-id="ddecd-132">W polu **Rzeczywiste godziny** są wyświetlane zaksięgowane godziny w zleceniach pracy.</span><span class="sxs-lookup"><span data-stu-id="ddecd-132">The **Actual hours** field shows posted hours on work orders.</span></span> <span data-ttu-id="ddecd-133">W polu **Ustalone godziny** są wyświetlane łączne godziny, na które firma jest zobowiązana w związku ze zleceniami pracy.</span><span class="sxs-lookup"><span data-stu-id="ddecd-133">The **Committed hours** field shows total amount of hours that your company is committed to in relation to work orders.</span></span>

