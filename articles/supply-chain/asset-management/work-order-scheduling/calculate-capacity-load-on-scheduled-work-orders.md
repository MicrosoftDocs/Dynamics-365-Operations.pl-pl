---
title: Obliczanie obciążenia zdolności produkcyjnych na zaplanowanych zleceniach pracy
description: W tym temacie opisano sposób obliczania obciążenia zdolności produkcyjnych w zaplanowanych zleceniach pracy w module Zarządzanie składnikami majątku
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 0c0dd1e306c54d3f99b86ad6f1816d5acabe6c18
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887166"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a><span data-ttu-id="7aacd-103">Obliczanie obciążenia zdolności produkcyjnych na zaplanowanych zleceniach pracy</span><span class="sxs-lookup"><span data-stu-id="7aacd-103">Calculate capacity load on scheduled work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="7aacd-104">Można obliczyć obciążenie zdolności produkcyjnych w zaplanowanych zleceniach pracy, aby uzyskać przegląd obciążenia pracą dla zasobów w danym okresie.</span><span class="sxs-lookup"><span data-stu-id="7aacd-104">You can calculate capacity load on scheduled work orders to get an overview of the work load on resources for a specific period.</span></span> <span data-ttu-id="7aacd-105">Można wykonywać obliczenia dla następujących zasobów: konserwatorzy, grupy pracowników, narzędzia i składniki majątku.</span><span class="sxs-lookup"><span data-stu-id="7aacd-105">Calculations can be made for the following resources: Maintenance workers, worker groups, tools, and assets.</span></span>

1. <span data-ttu-id="7aacd-106">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Harmonogram** > **Obciążenie wydajności**.</span><span class="sxs-lookup"><span data-stu-id="7aacd-106">Click **Asset management** > **Inquiries** > **Schedule** > **Capacity load**.</span></span>

2. <span data-ttu-id="7aacd-107">W oknie dialogowym **Obliczanie obciążenia zdolności produkcyjnych** > pole **Pokaż** i wybierz typ ładunku, który chcesz obliczyć: „zdolności produkcyjne”, „zarezerwowane” lub „pozostała”.</span><span class="sxs-lookup"><span data-stu-id="7aacd-107">In the **Calculate capacity load** dialog > **Show** field, select which load type you want to calculate: "Capacity", "Reserved", or "Remainder".</span></span>

3. <span data-ttu-id="7aacd-108">Wybierz wartość „tak” w przełączniku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z kosztem zerowym.</span><span class="sxs-lookup"><span data-stu-id="7aacd-108">Select "Yes" on the **Skip zero** toggle button if you do not want to show results containing zero.</span></span>

4. <span data-ttu-id="7aacd-109">Wybierz typy zasobów, dla których chcesz obliczyć obciążenie zdolności produkcyjnych, wybierając wartość „tak” w odpowiednich przełącznikach **Pracownik**, **Grupa konserwatorów**, **Narzędzie** i **Składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="7aacd-109">Select the resource types for which you want to calculate capacity load by selecting "Yes" on the relevant toggle buttons: **Worker**, **Maintenance worker group**, **Tool**, and **Asset**.</span></span>

5. <span data-ttu-id="7aacd-110">Wybierz datę początkową obliczeń w polu **Od dnia**.</span><span class="sxs-lookup"><span data-stu-id="7aacd-110">Select the start date for the calculation in the **From date** field.</span></span>

6. <span data-ttu-id="7aacd-111">W polu **Typ zakresu** wybierz zakres dla obliczania: „dzień”, „tydzień”, „miesiąc” lub „kwartał”.</span><span class="sxs-lookup"><span data-stu-id="7aacd-111">In the **Interval type** field, select the interval for the calculation: "Day", "Week", "Month", or "Quarter".</span></span>

7. <span data-ttu-id="7aacd-112">W polu **Częstotliwość okresu** wstaw liczbę zakresów, które mają zostać obliczone.</span><span class="sxs-lookup"><span data-stu-id="7aacd-112">In the **Period frequency** field, insert the number of intervals you want to calculate.</span></span> <span data-ttu-id="7aacd-113">Jeśli na przykład jako typ zakresu wybrano „dzień”, a w tym polu zostanie wstawiony numer „5”, zostanie wykonane obliczenie okresu pięciu dni od daty rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="7aacd-113">For example, if you have selected "Day" as the interval type, and you insert the number "5" in this field, a calculation of five days from the start date will be made.</span></span>

8. <span data-ttu-id="7aacd-114">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="7aacd-114">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="7aacd-115">Na poniższym rysunku przedstawiono wynik obliczeń obejmujących trzy tygodnie dla typu ładunku „zarezerwowane”.</span><span class="sxs-lookup"><span data-stu-id="7aacd-115">The figure below shows the result of a calculation covering three weeks for the load type "Reserved".</span></span>

![Rysunek 1](media/08-work-order-scheduling.png)

>[!NOTE]
><span data-ttu-id="7aacd-117">Jeśli w obliczeniach zostanie wybrana opcja „zdolności produkcyjne” lub „pozostała”, zostanie wyświetlony ten sam wynik, jeśli nie wykonano rezerwacji dla zasobów w wybranym okresie.</span><span class="sxs-lookup"><span data-stu-id="7aacd-117">If you select the load types "Capacity" or "Remainder" for your calculation, the same result will be displayed if no reservations have been made for the resources in the selected period.</span></span>

<span data-ttu-id="7aacd-118">Zapoznaj się z informacjami w [Obliczanie obciążenia zdolności produkcyjnych](../capacity-planning/calculate-capacity-load.md), aby dowiedzieć się jak obliczać obciążenia zdolności produkcyjnych w wierszach harmonogramu konserwacji i nieplanowanych zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="7aacd-118">Refer to [Calculate capacity load](../capacity-planning/calculate-capacity-load.md) for information on how to calculate capacity load on maintenance schedule lines and not scheduled work orders.</span></span>

