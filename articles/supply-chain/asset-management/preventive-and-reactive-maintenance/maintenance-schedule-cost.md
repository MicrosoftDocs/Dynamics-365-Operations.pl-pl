---
title: Koszt harmonogramu konserwacji
description: W tym temacie wyjaśniono harmonogram konserwacji w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 91c5b2e70ee083bf2741e245f1ca840ab939ad3f
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2020
ms.locfileid: "3382982"
---
# <a name="maintenance-schedule-cost"></a><span data-ttu-id="892cf-103">Koszt harmonogramu konserwacji</span><span class="sxs-lookup"><span data-stu-id="892cf-103">Maintenance schedule cost</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="892cf-104">W module Zarządzanie składnikami majątku można obliczać koszty budżetowe w wierszach harmonogramu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="892cf-104">In Asset Management, you can calculate budget costs on maintenance schedule lines.</span></span> <span data-ttu-id="892cf-105">Jest to przydatne w przypadku uzyskiwania przeglądu oczekiwanych kosztów, na przykład kosztów związanych z planowanymi zadaniami obsługi przeciwdziałania w przyszłym roku.</span><span class="sxs-lookup"><span data-stu-id="892cf-105">This is useful if you want to get an overview of expected costs, for example, costs relating to planned preventive maintenance jobs for the next year.</span></span> <span data-ttu-id="892cf-106">Obliczenia są oparte na istniejących wierszach harmonogramu konserwacji typu „plany konserwacji” i „liczba serii” oraz „żądania konserwacji”.</span><span class="sxs-lookup"><span data-stu-id="892cf-106">The calculations are based on existing maintenance schedule lines of type "Maintenance plans" and "Maintenance rounds" and "Maintenance requests".</span></span>

1. <span data-ttu-id="892cf-107">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Koszt harmonogramu konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="892cf-107">Click **Asset management** > **Inquiries** > **Assets** > **Maintenance schedule cost**.</span></span>

2. <span data-ttu-id="892cf-108">W oknie **Koszt harmonogramu konserwacji** można wybrać **Zestaw wymiarów finansowych**, jeśli koszty mają być wyświetlane w wymiarach finansowych.</span><span class="sxs-lookup"><span data-stu-id="892cf-108">In the **Maintenance schedule cost** dialog, you can select a **Financial dimension set** if you want to see costs grouped in financial dimensions.</span></span>

>[!NOTE]
><span data-ttu-id="892cf-109">Zestawy wymiarów finansowych są konfigurowane w **Księga główna** > **Plan kont** > **Wymairy** > **Zestawy wymiarów finansowych**.</span><span class="sxs-lookup"><span data-stu-id="892cf-109">Financial dimension sets are set up in **General ledger** > **Chart of accounts** > **Dimensions** > **Financial dimension sets**.</span></span>

3. <span data-ttu-id="892cf-110">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze harmonogramu konserwacji dla pozycji dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="892cf-110">You can use the **Level** field to indicate how detailed you want the maintenance schedule lines to be regarding functional locations.</span></span> <span data-ttu-id="892cf-111">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli harmonogramu konserwacji dla lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="892cf-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="892cf-112">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze harmonogramu konserwacji na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.</span><span class="sxs-lookup"><span data-stu-id="892cf-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="892cf-113">Jeśli chcesz przeprowadzić obliczenia dla konkretnych składników majątku, kliknij przycisk **Filtruj** na skróconej karcie **Rekordy do uwzględnienia** i wybierz odpowiednie składniki.</span><span class="sxs-lookup"><span data-stu-id="892cf-113">If you want to make a calculation for specific assets, click **Filter** on the **Records to include** FastTab, and select the relevant assets.</span></span> <span data-ttu-id="892cf-114">W razie potrzeby można również określić **Oczekiwane rozpoczęcie** dla obliczenia kosztu lub wybrać inny **Stan** dla obliczenia kosztu.</span><span class="sxs-lookup"><span data-stu-id="892cf-114">If required, you can also specify an **Expected start** date for the cost calculation or select a different **Status** for the cost calculation</span></span>

5. <span data-ttu-id="892cf-115">Kliknij przycisk **OK**, aby rozpocząć obliczanie kosztu.</span><span class="sxs-lookup"><span data-stu-id="892cf-115">Click **OK** to start the cost calculation.</span></span>

6. <span data-ttu-id="892cf-116">Na karcie **Koszt harmonogramu konserwacji** w grupach okienka akcji **Grupuj wg...** kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania kosztu.</span><span class="sxs-lookup"><span data-stu-id="892cf-116">On the **Maintenance schedule cost** tab > in the **Group by...** Action Pane groups, click the relevant buttons to show the required detail level of the cost calculation.</span></span> <span data-ttu-id="892cf-117">Wybrane przyciski grupy okienka akcji są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="892cf-117">The selected Action Pane group buttons are highlighted.</span></span> <span data-ttu-id="892cf-118">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="892cf-118">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="892cf-119">Kliknij przycisk **Oblicz koszt**, jeśli chcesz dokonać nowego obliczenia kosztu.</span><span class="sxs-lookup"><span data-stu-id="892cf-119">Click the **Calculate cost** button if you want to make a new cost calculation.</span></span>

<span data-ttu-id="892cf-120">Na poniższej ilustracji przedstawiono wyniki obliczenia kosztów harmonogramu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="892cf-120">The illustration below shows the results of a maintenance schedule cost calculation.</span></span>

![Rysunek 1](media/17-preventive-maintenance.png)

