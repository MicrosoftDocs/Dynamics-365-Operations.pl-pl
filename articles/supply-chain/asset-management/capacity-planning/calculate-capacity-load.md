---
title: Oblicz obciążenie wydajności
description: W tym temacie wyjaśniono, jak tworzyć obliczać obciążanie wydajności w Zarządzaniu składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
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
ms.openlocfilehash: c6d15861492a46ddb1222db2210f8c751ed38cb3
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886800"
---
# <a name="calculate-capacity-load"></a><span data-ttu-id="c8c4f-103">Oblicz obciążenie wydajności</span><span class="sxs-lookup"><span data-stu-id="c8c4f-103">Calculate capacity load</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="c8c4f-104">W module Zarządzanie składnikami majątku można obliczać wydajności</span><span class="sxs-lookup"><span data-stu-id="c8c4f-104">In Asset Management, you can calculate capacity load on</span></span>

- <span data-ttu-id="c8c4f-105">wierszy harmonogramu konserwacji</span><span class="sxs-lookup"><span data-stu-id="c8c4f-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="c8c4f-106">zleceń pracy, które nie zostały jeszcze zaplanowane</span><span class="sxs-lookup"><span data-stu-id="c8c4f-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="c8c4f-107">zaplanowanych zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="c8c4f-107">scheduled work orders</span></span>

<span data-ttu-id="c8c4f-108">Jest to przydatne w przypadku, gdy użytkownik chce uzyskać przegląd spodziewanego obciążenia wydajności w danym okresie.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-108">This is useful if you want to get an overview of expected capacity load for a specific period.</span></span> <span data-ttu-id="c8c4f-109">Obliczanie obciążenia wydajności można wykonać dla wszystkich składników majątku lub wybranych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-109">Calculation of capacity load can be done on all assets or selected assets.</span></span> <span data-ttu-id="c8c4f-110">Można również dokonać obliczeń dotyczących działań przestojów konserwacyjnych lub pul zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-110">You can also make a calculation on maintenance downtime activities or work order pools.</span></span>

1. <span data-ttu-id="c8c4f-111">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Obciążenie wydajności** lub **Zarządzanie składnikami majątku** > **Wspólne** > **Pule zleceń pracy** > **Wszystkie pule zleceń pracy** / **Aktywne pule zleceń pracy** > na liście wybierz pulę zleceń pracy > przycisk **Obciążenie wydajności** lub **Zarządzanie składnikami majątku** > **Wspólne** > **Działania w ramach przerwy konserwacyjnej** > **Wszystkie działania w ramach przerwy konserwacyjnej** / **Aktywne działania w ramach przerwy konserwacyjnej** > wybierz czynność konserwacyjną z listy > przycisk **Obciążenie wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-111">Click **Asset management** > **Inquiries** > **Capacity load**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Capacity load** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance activity in the list > **Capacity load** button.</span></span>

2. <span data-ttu-id="c8c4f-112">W oknie dialogowym **Oblicz obciążenie wydajności** wybierz okres, w którym zostaną wykonane obliczenia w polach **Data/godzina rozpoczęcia** i **Data/godzina zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-112">In the **Calculate capacity load** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="c8c4f-113">Należy wybrać wartość „tak” na przełączniku **Uwzględnij harmonogram konserwacji**, jeśli wiersze obsługi harmonogramu konserwacji mają zostać uwzględnione w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the calculation.</span></span>

4. <span data-ttu-id="c8c4f-114">Należy wybrać wartość „tak” na przełączniku **Uwzględnij zlecenie pracy**, jeśli zadania zlecenia pracy mają zostać uwzględnione w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the calculation.</span></span>

5. <span data-ttu-id="c8c4f-115">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze obciążenia wydajności dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-115">You can use the **Level** field to indicate how detailed you want the capacity load lines to be regarding functional locations.</span></span> <span data-ttu-id="c8c4f-116">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli harmonogramu konserwacji i zlecenia pracy w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="c8c4f-117">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze harmonogramu konserwacji i wszystkie zlecenia pracy na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="c8c4f-118">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="c8c4f-119">W **Grupuj wg...** grupach okienka akcji, kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-119">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="c8c4f-120">Wybrane przyciski okienka akcji są wyróżnione na niebiesko.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-120">The selected action pane group buttons are highlighted in blue color.</span></span> <span data-ttu-id="c8c4f-121">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-121">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="c8c4f-122">Na poniższym rysunku pokazano przykład interfejsu.</span><span class="sxs-lookup"><span data-stu-id="c8c4f-122">The figure below shows an example of the interface.</span></span>

![Rysunek 1](media/01-capacity-planning.png)

>[!NOTE]
><span data-ttu-id="c8c4f-124">Aby skoncentrować się tylko na planowaniu zdolności produkcyjnych w odniesieniu do zaplanowanych zleceń pracy, należy odwołać się do [Obliczanie obciążenia zdolności produkcyjnych na zaplanowanych zleceniach pracy](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span><span class="sxs-lookup"><span data-stu-id="c8c4f-124">If you want to focus only on capacity planning regarding scheduled work orders, refer to [Calculate capacity load on scheduled work orders](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span></span>

