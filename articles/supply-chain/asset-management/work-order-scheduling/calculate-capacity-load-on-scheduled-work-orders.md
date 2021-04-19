---
title: Obliczanie obciążenia zdolności produkcyjnych na zaplanowanych zleceniach pracy
description: W tym temacie opisano sposób obliczania obciążenia zdolności produkcyjnych w zaplanowanych zleceniach pracy w module Zarządzanie składnikami majątku
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 09e0fc17a288a278b7b1feaba8c7b73425aa2d52
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808167"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a><span data-ttu-id="3905b-103">Obliczanie obciążenia zdolności produkcyjnych na zaplanowanych zleceniach pracy</span><span class="sxs-lookup"><span data-stu-id="3905b-103">Calculate capacity load on scheduled work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="3905b-104">Można obliczyć obciążenie zdolności produkcyjnych w zaplanowanych zleceniach pracy, aby uzyskać przegląd obciążenia pracą dla zasobów w danym okresie.</span><span class="sxs-lookup"><span data-stu-id="3905b-104">You can calculate capacity load on scheduled work orders to get an overview of the work load on resources for a specific period.</span></span> <span data-ttu-id="3905b-105">Można wykonywać obliczenia dla następujących zasobów: konserwatorzy, grupy pracowników, narzędzia i składniki majątku.</span><span class="sxs-lookup"><span data-stu-id="3905b-105">Calculations can be made for the following resources: Maintenance workers, worker groups, tools, and assets.</span></span>

1. <span data-ttu-id="3905b-106">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Harmonogram** > **Obciążenie wydajności**.</span><span class="sxs-lookup"><span data-stu-id="3905b-106">Click **Asset management** > **Inquiries** > **Schedule** > **Capacity load**.</span></span>

2. <span data-ttu-id="3905b-107">W oknie dialogowym **Obliczanie obciążenia zdolności produkcyjnych** > pole **Pokaż** wybierz typ obciążenia pracą do obliczenia: **Zdolności produkcyjne**, **Zarezerwowane**” lub **Pozostałe**.</span><span class="sxs-lookup"><span data-stu-id="3905b-107">In the **Calculate capacity load** dialog > **Show** field, select which load type you want to calculate: **Capacity**, **Reserved**, or **Remainder**.</span></span>

3. <span data-ttu-id="3905b-108">Wybierz wartość **Tak**” w przełączniku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z kosztem zerowym.</span><span class="sxs-lookup"><span data-stu-id="3905b-108">Select **Yes** on the **Skip zero** toggle button if you do not want to show results containing zero.</span></span>

4. <span data-ttu-id="3905b-109">Wybierz typy zasobów, dla których chcesz obliczyć obciążenie zdolności produkcyjnych, wybierając wartość **Tak** w odpowiednich przełącznikach **Pracownik**, **Grupa konserwatorów**, **Narzędzie** i **Składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="3905b-109">Select the resource types for which you want to calculate capacity load by selecting **Yes** on the relevant toggle buttons: **Worker**, **Maintenance worker group**, **Tool**, and **Asset**.</span></span>

5. <span data-ttu-id="3905b-110">Wybierz datę początkową obliczeń w polu **Od dnia**.</span><span class="sxs-lookup"><span data-stu-id="3905b-110">Select the start date for the calculation in the **From date** field.</span></span>

6. <span data-ttu-id="3905b-111">W polu **Typ zakresu** wybierz zakres dla obliczania: **Dzień**, **Tydzień**, **Miesiąc** lub **Kwartał**.</span><span class="sxs-lookup"><span data-stu-id="3905b-111">In the **Interval type** field, select the interval for the calculation: **Day**, **Week**, **Month**, or **Quarter**.</span></span>

7. <span data-ttu-id="3905b-112">W polu **Częstotliwość okresu** wstaw liczbę zakresów, które mają zostać obliczone.</span><span class="sxs-lookup"><span data-stu-id="3905b-112">In the **Period frequency** field, insert the number of intervals you want to calculate.</span></span> <span data-ttu-id="3905b-113">Jeśli na przykład jako typ zakresu wybrano **Dzień**, a w tym polu zostanie wprowadzona liczba „5”, zostanie wykonane obliczenie okresu pięciu dni od daty rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="3905b-113">For example, if you have selected **Day** as the interval type, and you enter the number "5" in this field, a calculation of five days from the start date will be made.</span></span>

8. <span data-ttu-id="3905b-114">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="3905b-114">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="3905b-115">Na poniższym rysunku przedstawiono wynik obliczeń obejmujących trzy tygodnie dla typu ładunku **Zarezerwowane**.</span><span class="sxs-lookup"><span data-stu-id="3905b-115">The figure below shows the result of a calculation covering three weeks for the load type **Reserved**.</span></span>

![Rysunek 1](media/08-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="3905b-117">Jeśli w obliczeniach zostanie wybrana opcja **Zdolności produkcyjne** lub **Pozostałe**, zostanie wyświetlony ten sam wynik, jeśli nie wykonano rezerwacji dla zasobów w wybranym okresie.</span><span class="sxs-lookup"><span data-stu-id="3905b-117">If you select the load types **Capacity** or **Remainder** for your calculation, the same result will be displayed if no reservations have been made for the resources in the selected period.</span></span>

<span data-ttu-id="3905b-118">Aby dowiedzieć się, jak obliczać obciążenia zdolności produkcyjnych w wierszach harmonogramu konserwacji i nieplanowanych zleceniach pracy, zapoznaj się z informacjami w temacie [Obliczanie obciążenia zdolności produkcyjnych](../capacity-planning/calculate-capacity-load.md).</span><span class="sxs-lookup"><span data-stu-id="3905b-118">For information about how to calculate capacity load on maintenance schedule lines and not scheduled work orders, refer to [Calculate capacity load](../capacity-planning/calculate-capacity-load.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]