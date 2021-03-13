---
title: Tworzenie raportu zużycia
description: W tym temacie wyjaśniono, jak utworzyć raporty zużycia w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e32924c71fd221caee4a7f413908120014ec8c5
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022540"
---
# <a name="create-consumption-reports"></a><span data-ttu-id="45316-103">Tworzenie raportu zużycia</span><span class="sxs-lookup"><span data-stu-id="45316-103">Create consumption reports</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="45316-104">Po utworzeniu i zaksięgowaniu rejestracji zużycia w zleceniach pracy w module Zarządzanie składnikami majątku dostępne są dwa raporty umożliwiające wyświetlenie szczegółów zużycia.</span><span class="sxs-lookup"><span data-stu-id="45316-104">When you've created and posted consumption registrations on work orders in Asset Management, two reports are available to display consumption details.</span></span>


## <a name="asset-consumption-report"></a><span data-ttu-id="45316-105">Raport zużycia składnika majątku</span><span class="sxs-lookup"><span data-stu-id="45316-105">Asset consumption report</span></span>

<span data-ttu-id="45316-106">Po zaksięgowaniu zużycia w zleceniach pracy można wydrukować raport dotyczący zużycia składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="45316-106">When you have posted consumption on work orders, you can print an asset consumption report.</span></span> <span data-ttu-id="45316-107">W raporcie są wyświetlane godziny, koszty godzinowe, koszty towarów i wydatki zaksięgowane dla składników majątku.</span><span class="sxs-lookup"><span data-stu-id="45316-107">The report displays hours, hour costs, item costs, and expenses posted on assets.</span></span>

1. <span data-ttu-id="45316-108">Kliknij **Zarządzanie składnikami majątku** > **Raporty** > **Składniki majątku** > **Zużycie składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="45316-108">Click **Asset management** > **Reports** > **Assets** > **Asset consumption**.</span></span>

2. <span data-ttu-id="45316-109">W oknie dialogowym **Zużycie składnika majątku** wybierz parametry i poziom szczegółów, które chcesz wyświetlić, wybierając w odpowiednich przyciskach opcję **Tak**, a następnie wstawiając poziom lokalizacji czynności konserwacyjnych w sekcji **Pokaż**.</span><span class="sxs-lookup"><span data-stu-id="45316-109">In the **Asset consumption** dialog, select the parameters and detail level you want to see by selecting **Yes** on the relevant toggle buttons, and inserting a functional location level in the **Show** section.</span></span>
    - <span data-ttu-id="45316-110">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze składnika majątku dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="45316-110">You can use the **Levels** field to indicate how detailed you want the asset lines to be regarding functional locations.</span></span> 
    
        <span data-ttu-id="45316-111">Jeśli na przykład w polu wprowadzono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie składniki majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego wartości w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="45316-111">For example, if you enter the number "1" in the field, and you have a multi-level functional location structure, all assets for a functional location will be shown on the top level, and therefore a line may be added up from functional locations located at a lower level.</span></span> 
        
        <span data-ttu-id="45316-112">W przypadku wprowadzenia liczby „0” w polu **Poziomy** zostanie wyświetlony szczegółowy wynik zawierający wszystkie składniki majątku na każdym poziomie lokalizacji czynności konserwacyjnych, z którym są one powiązane.</span><span class="sxs-lookup"><span data-stu-id="45316-112">If you enter the number "0" in the **Levels** field, you will see a detailed result showing all assets on all the functional location levels to which they are related.</span></span> 
        
    - <span data-ttu-id="45316-113">Wybierz wartość **Tak** na przycisku **Suma wszystkich podrzędnych składników majątku**, aby wyświetlić sumy dla poszczególnych podrzędnych składników majątku w raporcie.</span><span class="sxs-lookup"><span data-stu-id="45316-113">Select **Yes** on the **Sum on all sub assets** toggle button to see sums for each sub asset in the report.</span></span>

3. <span data-ttu-id="45316-114">Wybierz interwał dat w sekcji **Daty**.</span><span class="sxs-lookup"><span data-stu-id="45316-114">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="45316-115">Na skróconej karcie **Miejsce docelowe** wybierz opcję, czy raport ma być wyświetlany na ekranie, wydrukowany lub zapisany jako plik lub wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="45316-115">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="45316-116">W razie potrzeby można wybrać określone składniki majątku, które mają być wyświetlane w raporcie.</span><span class="sxs-lookup"><span data-stu-id="45316-116">If required, you can select specific assets to be displayed in the report.</span></span> <span data-ttu-id="45316-117">Na skróconej karcie **Rekordy do uwzględnienia** kliknij **Filtruj**, a następnie dodaj składniki majątku, które mają zostać uwzględnione w raporcie.</span><span class="sxs-lookup"><span data-stu-id="45316-117">On the **Records to include** FastTab, click **Filter**, and add the assets you want to include in the report.</span></span>

6. <span data-ttu-id="45316-118">Kliknij przycisk **OK**. Raport zostanie wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="45316-118">Click **OK** to generate the report.</span></span>


## <a name="work-order-consumption-report"></a><span data-ttu-id="45316-119">Raport zużycia zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="45316-119">Work order consumption report</span></span>

<span data-ttu-id="45316-120">Po zaksięgowaniu zużycia w zleceniach pracy można wydrukować raport dotyczący zużycia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="45316-120">When you have posted consumption on work orders, you can print a work order consumption report.</span></span> <span data-ttu-id="45316-121">W raporcie są wyświetlane godziny, koszty godzinowe, koszty towarów i wydatki zaksięgowane dla zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="45316-121">The report displays hours, hour costs, item costs, and expenses posted on work orders.</span></span>

1. <span data-ttu-id="45316-122">Kliknij kolejno **Zarządzanie składnikami majątku** > **Reporty** > **Zlecenia pracy** > **Zużycie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="45316-122">Click **Asset management** > **Reports** > **Work orders** > **Work order consumption**.</span></span>

2. <span data-ttu-id="45316-123">W oknie dialogowym **Zużycie zlecenia pracy** wybierz parametry, które mają zostać uwzględnione w raporcie, klikając opcję **Tak** w odpowiednich przyciskach w sekcji **Pokaż**.</span><span class="sxs-lookup"><span data-stu-id="45316-123">In the **Work order consumption** dialog, select the parameters you want to include in the report by selecting **Yes** on the relevant toggle buttons in the **Show** section.</span></span>

3. <span data-ttu-id="45316-124">Wybierz interwał dat w sekcji **Daty**.</span><span class="sxs-lookup"><span data-stu-id="45316-124">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="45316-125">Na skróconej karcie **Miejsce docelowe** wybierz opcję, czy raport ma być wyświetlany na ekranie, wydrukowany lub zapisany jako plik lub wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="45316-125">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="45316-126">W razie potrzeby można wybrać określone zlecenia pracy, które mają być wyświetlane w raporcie.</span><span class="sxs-lookup"><span data-stu-id="45316-126">If required, you can select specific work orders to be displayed in the report.</span></span> <span data-ttu-id="45316-127">Na skróconej karcie **Rekordy do uwzględnienia** kliknij **Filtruj**, a następnie dodaj zlecenia pracy, które mają zostać uwzględnione w raporcie.</span><span class="sxs-lookup"><span data-stu-id="45316-127">On the **Records to include** FastTab, click **Filter**, and add the work orders you want to include in the report.</span></span>

6. <span data-ttu-id="45316-128">Kliknij przycisk **OK**. Raport zostanie wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="45316-128">Click **OK** to generate the report.</span></span>


>[!NOTE]
><span data-ttu-id="45316-129">Można również wygenerować [raport zlecenia pracy](../work-orders/work-order-report.md) zawierający więcej szczegółów zlecenia.</span><span class="sxs-lookup"><span data-stu-id="45316-129">You can also generate a [work order report](../work-orders/work-order-report.md), which contains more work order details.</span></span>

