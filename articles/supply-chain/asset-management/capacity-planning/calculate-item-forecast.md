---
title: Oblicz prognozę pozycji
description: W tym temacie wyjaśniono, jak obliczać prognozę pozycji w Zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9392245abe5858b03b8324dcb471f5652aed7cd6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813900"
---
# <a name="calculate-item-forecast"></a><span data-ttu-id="ddcf1-103">Oblicz prognozę pozycji</span><span class="sxs-lookup"><span data-stu-id="ddcf1-103">Calculate item forecast</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ddcf1-104">Podobnie jak w przypadku obliczeń obciążenia zdolności produkcyjnych, które opisano w poprzedniej sekcji, można również ustawić obliczenia prognozy pozycji dla:</span><span class="sxs-lookup"><span data-stu-id="ddcf1-104">Just as you can make capacity load calculations, which are described in the previous section, you can also make item forecast calculations on:</span></span>

- <span data-ttu-id="ddcf1-105">wierszy harmonogramu konserwacji</span><span class="sxs-lookup"><span data-stu-id="ddcf1-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="ddcf1-106">zleceń pracy, które nie zostały jeszcze zaplanowane</span><span class="sxs-lookup"><span data-stu-id="ddcf1-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="ddcf1-107">zaplanowanych zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="ddcf1-107">scheduled work orders</span></span>

<span data-ttu-id="ddcf1-108">Jest to przydatne w przypadku, gdy użytkownik chce uzyskać przegląd oczekiwanego zużycia towarów (części zamiennych oraz innych towarów wymaganych do ukończenia zleceń pracy) w określonym okresie.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-108">This is useful if you want to get an overview of expected item consumption (spare parts as well as other items required for completing work orders) for a specific period.</span></span> <span data-ttu-id="ddcf1-109">Obliczanie prognozy pozycji można wykonać dla wszystkich składników majątku lub wybranych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-109">Calculation of item forecast can be done on all assets or selected assets.</span></span> <span data-ttu-id="ddcf1-110">Można również dokonać obliczeń dotyczących działania dotyczącego przestojów związanych z konserwacją(**Wszystkie działania w ramach przerwy konserwacyjnej** lub **Aktywne działania w ramach przerwy konserwacyjnej**) lub pulą zleceń pracy (**Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy**).</span><span class="sxs-lookup"><span data-stu-id="ddcf1-110">You can also make a calculation on a maintenance downtime activity (**All maintenance downtime activities** or **Active maintenance downtime activities**), or on a work order pool (**All work order pools** or **Active work order pools**).</span></span>

1. <span data-ttu-id="ddcf1-111">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Prognoza dla pozycji** lub **Zarządzanie składnikami majątku** > **Wspólne** > **Pule zleceń pracy** > **Wszystkie pule zleceń pracy** / **Aktywne pule zleceń pracy** > na liście wybierz pulę zleceń pracy > przycisk **Prognoza dla pozycji** lub **Zarządzanie składnikami majątku** > **Wspólne** > **Działania w ramach przerwy konserwacyjnej** > **Wszystkie działania w ramach przerwy konserwacyjnej** / **Aktywne działania w ramach przerwy konserwacyjnej** > wybierz czynność w ramach przerwy konserwacyjnej z listy > przycisk **Prognoza dla pozycji**.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-111">Click **Asset management** > **Inquiries** > **Item forecast**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Item forecast** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance downtime activity in the list > **Item forecast** button.</span></span>

2. <span data-ttu-id="ddcf1-112">W oknie dialogowym **Oblicz prognozę dla pozycji** wybierz okres, w którym zostaną wykonane obliczenia w polach **Data/godzina rozpoczęcia** i **Data/godzina zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-112">In the **Calculate item forecast** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="ddcf1-113">Należy wybrać wartość „tak” na przełączniku **Uwzględnij harmonogram konserwacji**, jeśli wiersze obsługi harmonogramu konserwacji mają zostać uwzględnione w obliczeniach prognozy.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the forecast calculation.</span></span>

4. <span data-ttu-id="ddcf1-114">Należy wybrać wartość „tak” na przełączniku **Uwzględnij zlecenie pracy**, jeśli zadania zlecenia pracy mają zostać uwzględnione w obliczeniach prognozy.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the forecast calculation.</span></span>

5. <span data-ttu-id="ddcf1-115">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze prognozy dla pozycji dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-115">You can use the **Level** field to indicate how detailed you want the item forecast lines to be regarding functional locations.</span></span> 

      <span data-ttu-id="ddcf1-116">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli harmonogramu konserwacji i zlecenia pracy w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
  
      <span data-ttu-id="ddcf1-117">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze harmonogramu konserwacji i wszystkie zlecenia pracy na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="ddcf1-118">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="ddcf1-119">W grupach **Grupuj wg...** kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="ddcf1-120">Na poniższym zrzucie ekranu wybrane przyciski **Grupuj wg** są wyróżniane kolorem niebieskim.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="ddcf1-121">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-121">Click on a button to activate or deactivate it.</span></span>

8. <span data-ttu-id="ddcf1-122">Kliknij przycisk **Wyświetl wymiary**, jeśli chcesz wyświetlić wymiary produktu, magazynu lub śledzenia związane z towarami.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-122">Click the **Display dimensions** button if you want to see the product, storage, or tracking dimensions related to the items.</span></span> <span data-ttu-id="ddcf1-123">Wybierz odpowiednie pola wyboru i kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddcf1-123">Select the relevant check boxes, and click **OK**.</span></span>

![Rysunek 1](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]