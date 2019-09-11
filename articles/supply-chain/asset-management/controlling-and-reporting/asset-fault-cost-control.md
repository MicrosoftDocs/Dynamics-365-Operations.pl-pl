---
title: Formant kosztów usterki składnika majątku
description: W tym temacie wyjaśniono kontrolę kosztów usterek składników majątku w module Zarządzanie składnikami majątku.
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
ms.openlocfilehash: 2fe75c327cdc2bdd76173430ed551895f5941c7b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918310"
---
# <a name="asset-fault-cost-control"></a><span data-ttu-id="0fcd5-103">Formant kosztów usterki składnika majątku</span><span class="sxs-lookup"><span data-stu-id="0fcd5-103">Asset fault cost control</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="0fcd5-104">W module Zarządzanie składnikami majątku można obliczać koszty rejestracji usterek składników majątku, aby uzyskać przegląd kosztów rzeczywistych w porównaniu z kosztami budżetowymi dotyczącymi usterek.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-104">In Asset Management, you can calculate costs on asset fault registrations to get an overview of actual costs compared to budget costs on faults.</span></span> <span data-ttu-id="0fcd5-105">Koszty rzeczywiste są oparte na zaksięgowanych transakcjach.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="0fcd5-106">Data jest datą usterki, w której objaw został zarejestrowany.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-106">The date is the fault date on which the symptom was recorded.</span></span>

1. <span data-ttu-id="0fcd5-107">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Formant kosztów usterki składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-107">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault cost control**.</span></span>

2. <span data-ttu-id="0fcd5-108">W oknie dialogowym **Formant kosztów usterki składnika majątku** wybierz wymiar finansowy, który ma zostać uwzględniony w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-108">In the **Asset fault cost control** dialog, select a financial dimension set to be included in the calculation, if required.</span></span>

4. <span data-ttu-id="0fcd5-109">Wybierz wartość „tak” w przycisku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z kosztem zerowym.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-109">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="0fcd5-110">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze kontroli kosztów dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-110">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> <span data-ttu-id="0fcd5-111">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli kosztów usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="0fcd5-112">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze kontroli kosztów usterek składnika majątku na każdym poziomie lokalizacji czynności konserwacyjnych, z którym jest powiązany.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault cost control lines on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="0fcd5-113">Aby ograniczyć wyszukiwanie, można wybrać określone składniki majątku, daty usterek i przyczyny usterek w skróconej karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-113">If you want to limit the search, you can select specific assets, fault dates, and fault causes on the **Records to include** FastTab.</span></span>

7. <span data-ttu-id="0fcd5-114">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-114">Click **OK** to start the calculation.</span></span>

8. <span data-ttu-id="0fcd5-115">W **Grupuj wg...** grupach okienka akcji, kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-115">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="0fcd5-116">Wybrane przyciski okienka akcji są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-116">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="0fcd5-117">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-117">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="0fcd5-118">Na poniższym rysunku pokazano przykład obliczania kontroli kosztów usterek składników majątku.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-118">The figure below shows an example of an asset fault cost control calculation.</span></span>

![Rysunek 1](media/05-controlling-and-reporting.png)

<span data-ttu-id="0fcd5-120">W sekcji [Zarządzanie usterkami](../setup-for-work-orders/fault-management.md) można znaleźć w informacje na temat konfigurowania usterek.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-120">Refer to the [Fault management](../setup-for-work-orders/fault-management.md) section for information on how to set up faults.</span></span>

>[!NOTE]
><span data-ttu-id="0fcd5-121">W polu **Budżet pierwotny** są wyświetlane koszty budżetowe z prognozy zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-121">The **Original budget** field shows budget costs from the work order forecast.</span></span> <span data-ttu-id="0fcd5-122">W polu **Koszt rzeczywisty** są wyświetlane zaksięgowane koszty w zleceniach pracy.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-122">The **Actual cost** field shows posted costs on work orders.</span></span> <span data-ttu-id="0fcd5-123">W polu **Ustalony koszt** są wyświetlane łączne koszty, na które firma jest zobowiązana w związku ze zleceniami pracy.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-123">The **Committed cost** field shows total costs that your company is committed to in relation to work orders.</span></span>

