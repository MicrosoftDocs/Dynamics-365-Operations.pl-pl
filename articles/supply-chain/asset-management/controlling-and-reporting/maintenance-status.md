---
title: Stan konserwacji
description: W tym temacie wyjaśniono, jak obliczyć stan konserwacji w Zarządzaniu składnikami majątku.
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
ms.openlocfilehash: 516607c056125a16e075c33f3c2ad069efb396d9
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918356"
---
# <a name="maintenance-status"></a><span data-ttu-id="bc271-103">Stan konserwacji</span><span class="sxs-lookup"><span data-stu-id="bc271-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="bc271-104">W module Zarządzanie składnikami majątku można wykonać obliczenia w celu przejrzenia informacji o nowych, aktywnych i zakończonych żądaniach obsługi, zleceniach i czynnościach związanych z konserwacją w określonym okresie.</span><span class="sxs-lookup"><span data-stu-id="bc271-104">In Asset Management, you can make a calculation to see an overview of new, active, and completed maintenance requests, work orders, and maintenance downtime activities for a specific period.</span></span> <span data-ttu-id="bc271-105">Można również wyświetlić liczbę zakończonych ocen stanu dla tego samego okresu.</span><span class="sxs-lookup"><span data-stu-id="bc271-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="bc271-106">To obliczenie umożliwia uzyskanie przeglądu obciążenia pracą dotyczącą przychodzących i zakończonych żądań obsługi oraz zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="bc271-106">Use this calculation to get an overview of workload regarding incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="bc271-107">Dokonaj obliczenia stan konserwacji</span><span class="sxs-lookup"><span data-stu-id="bc271-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="bc271-108">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Stan konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="bc271-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="bc271-109">W oknie dialogowym **Oblicz stan** wstaw okres, dla którego chcesz dokonać obliczeń w polach **Od dnia** i **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="bc271-109">In the **Calculate status** dialog, select the period for which you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="bc271-110">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wierszekonserwacji dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="bc271-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> <span data-ttu-id="bc271-111">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze konserwacji dla lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="bc271-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="bc271-112">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze konserwacji na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.</span><span class="sxs-lookup"><span data-stu-id="bc271-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="bc271-113">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="bc271-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="bc271-114">W **Grupuj wg...** grupach okienka akcji, kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="bc271-114">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="bc271-115">Wybrane przyciski okienka akcji są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="bc271-115">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="bc271-116">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="bc271-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="bc271-117">Pamiętaj o kliknięciu przycisku **Aktualizuj**, aby zaktualizować obliczenia za każdym razem, gdy dokonywane są zmiany, aktywując lub dezaktywując przyciski **Grupuj wg...** lub przez obliczenie dla nowego okresu.</span><span class="sxs-lookup"><span data-stu-id="bc271-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by...** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="bc271-118">Kliknij przycisk **stan**, jeśli chcesz utworzyć nowe Obliczanie stanu eksploatacji.</span><span class="sxs-lookup"><span data-stu-id="bc271-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="bc271-119">Wyniki wyświetlane w **stanie konserwacji** obejmują tylko żądania obsługi i zlecenia, które mają rzeczywistą datę i godzinę rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="bc271-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="bc271-120">Data i godzina zakończenia mogą być puste</span><span class="sxs-lookup"><span data-stu-id="bc271-120">End date and time may be blank.</span></span>

<span data-ttu-id="bc271-121">*Przykład 1:*</span><span class="sxs-lookup"><span data-stu-id="bc271-121">*Example 1:*</span></span>

<span data-ttu-id="bc271-122">Na poniższym rysunku aktywowano przyciski **rok** i **miesiąc**.</span><span class="sxs-lookup"><span data-stu-id="bc271-122">In the figure below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="bc271-123">W tym miejscu można uzyskać ogólny przegląd informacji na temat miesięcznego obciążenia pracą i produktywności związanych z żądaniami obsługi i zleceniami produkcyjnymi.</span><span class="sxs-lookup"><span data-stu-id="bc271-123">Here, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![Rysunek 1](media/13-controlling-and-reporting.png)

<span data-ttu-id="bc271-125">*Przykład 2:*</span><span class="sxs-lookup"><span data-stu-id="bc271-125">*Example 2:*</span></span>

<span data-ttu-id="bc271-126">Na poniższym rysunku zostały dodane informacje o lokalizacjach czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="bc271-126">In the figure below, information about functional locations has been added.</span></span> <span data-ttu-id="bc271-127">Teraz możliwe jest porównanie obciążenia i przepływności między lokalizacjami czynności konserwacyjnych, które mogą reprezentować lokalizacje geograficzne, fabryki lub obszary robocze.</span><span class="sxs-lookup"><span data-stu-id="bc271-127">Now, it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![Rysunek 2](media/14-controlling-and-reporting.png)

