---
title: Stan konserwacji
description: W tym temacie wyjaśniono, jak obliczyć stan konserwacji w Zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetStatusCalculate, EntAssetStatus
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f3d6f86c5052c845c9c8aad1e4437f4196f78b50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808623"
---
# <a name="maintenance-status"></a><span data-ttu-id="89ee3-103">Stan konserwacji</span><span class="sxs-lookup"><span data-stu-id="89ee3-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="89ee3-104">W module Zarządzanie składnikami majątku można wykonać obliczenia dla określonego okresu w celu przejrzenia informacji o nowych, aktywnych i zakończonych żądaniach obsługi, zleceniach i czynnościach związanych z konserwacją.</span><span class="sxs-lookup"><span data-stu-id="89ee3-104">In Asset Management, you can make an overview calculation for a specific period for new, active, and completed maintenance requests, work orders, and maintenance downtime activities.</span></span> <span data-ttu-id="89ee3-105">Można również wyświetlić liczbę zakończonych ocen stanu dla tego samego okresu.</span><span class="sxs-lookup"><span data-stu-id="89ee3-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="89ee3-106">To obliczenie umożliwia uzyskanie przeglądu obciążenia pracą dla przychodzących i zakończonych żądań obsługi oraz zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="89ee3-106">Use this calculation to get an overview of workload for incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="89ee3-107">Dokonaj obliczenia stan konserwacji</span><span class="sxs-lookup"><span data-stu-id="89ee3-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="89ee3-108">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Stan konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="89ee3-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="89ee3-109">W oknie dialogowym **Oblicz stan** wybierz zakres czasu, dla którego chcesz dokonać obliczeń w polach **Od dnia** i **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="89ee3-109">In the **Calculate status** dialog, select the time range that you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="89ee3-110">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wierszekonserwacji dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="89ee3-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> 

  <span data-ttu-id="89ee3-111">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze konserwacji dla lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="89ee3-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> 
  
  <span data-ttu-id="89ee3-112">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze konserwacji na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.</span><span class="sxs-lookup"><span data-stu-id="89ee3-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="89ee3-113">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="89ee3-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="89ee3-114">Kliknij przyciski **Grupuj wg...**, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="89ee3-114">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="89ee3-115">Wybrane przyciski grupy **Grupuj wg...** są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="89ee3-115">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="89ee3-116">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="89ee3-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="89ee3-117">Pamiętaj o kliknięciu przycisku **Aktualizuj**, aby zaktualizować obliczenia za każdym razem, gdy dokonywane są zmiany, aktywując lub dezaktywując przyciski **Grupuj wg...** lub przez wykonianie obliczenia dla nowego okresu.</span><span class="sxs-lookup"><span data-stu-id="89ee3-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="89ee3-118">Kliknij przycisk **stan**, jeśli chcesz utworzyć nowe Obliczanie stanu eksploatacji.</span><span class="sxs-lookup"><span data-stu-id="89ee3-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="89ee3-119">Wyniki wyświetlane w **stanie konserwacji** obejmują tylko żądania obsługi i zlecenia, które mają rzeczywistą datę i godzinę rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="89ee3-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="89ee3-120">Data i godzina zakończenia mogą być puste</span><span class="sxs-lookup"><span data-stu-id="89ee3-120">End date and time may be blank.</span></span>

## <a name="example-1"></a><span data-ttu-id="89ee3-121">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="89ee3-121">Example 1</span></span>

<span data-ttu-id="89ee3-122">Na poniższym zrzucie ekranu aktywowano przyciski **rok** i **miesiąc**.</span><span class="sxs-lookup"><span data-stu-id="89ee3-122">In the screenshot below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="89ee3-123">Po wybraniu opcji **Grupuj wg...** można uzyskać ogólny przegląd informacji na temat miesięcznego obciążenia pracą i produktywności związanych z żądaniami obsługi i zleceniami produkcyjnymi.</span><span class="sxs-lookup"><span data-stu-id="89ee3-123">With these **Group by** options selected, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![Przykład miesięcznego obciążenia pracą](media/13-controlling-and-reporting.png)

## <a name="example-2"></a><span data-ttu-id="89ee3-125">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="89ee3-125">Example 2</span></span>

<span data-ttu-id="89ee3-126">Na poniższym zrzucie ekranu zostały dodane informacje o lokalizacjach czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="89ee3-126">In the screenshot below, information about functional locations has been added.</span></span> <span data-ttu-id="89ee3-127">Teraz możliwe jest porównanie obciążenia i przepływności między lokalizacjami czynności konserwacyjnych, które mogą reprezentować lokalizacje geograficzne, fabryki lub obszary robocze.</span><span class="sxs-lookup"><span data-stu-id="89ee3-127">Now it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![Przykład miesięcznego obciążenia pracą z lokalizacjami czynności konserwacyjnych](media/14-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]