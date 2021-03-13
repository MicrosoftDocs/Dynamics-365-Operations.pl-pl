---
title: Formant kosztów usterki składnika majątku
description: W tym temacie wyjaśniono kontrolę kosztów usterek składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 597e30db346e882a7002709be52ad1c2d0576099
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019960"
---
# <a name="asset-fault-cost-control"></a><span data-ttu-id="b7310-103">Formant kosztów usterki składnika majątku</span><span class="sxs-lookup"><span data-stu-id="b7310-103">Asset fault cost control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b7310-104">W module Zarządzanie składnikami majątku można obliczać koszty rejestracji usterek składników majątku, aby uzyskać przegląd kosztów rzeczywistych w porównaniu z kosztami budżetowymi.</span><span class="sxs-lookup"><span data-stu-id="b7310-104">In Asset Management, you can calculate costs on asset fault registrations to get an overview of actual costs compared to budget costs.</span></span> <span data-ttu-id="b7310-105">Koszty rzeczywiste są oparte na zaksięgowanych transakcjach.</span><span class="sxs-lookup"><span data-stu-id="b7310-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="b7310-106">Data jest datą usterki, w której objaw został zarejestrowany.</span><span class="sxs-lookup"><span data-stu-id="b7310-106">The date is the fault date on which the symptom was recorded.</span></span>

1. <span data-ttu-id="b7310-107">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Formant kosztów usterki składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="b7310-107">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault cost control**.</span></span>

2. <span data-ttu-id="b7310-108">W oknie dialogowym **Formant kosztów usterki składnika majątku** wybierz wymiar finansowy, który ma zostać uwzględniony w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="b7310-108">In the **Asset fault cost control** dialog, select a financial dimension set to be included in the calculation, if required.</span></span>

4. <span data-ttu-id="b7310-109">Wybierz wartość „tak” w przycisku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z kosztem zerowym.</span><span class="sxs-lookup"><span data-stu-id="b7310-109">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="b7310-110">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze kontroli kosztów dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="b7310-110">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="b7310-111">Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli kosztów usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="b7310-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="b7310-112">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze kontroli kosztów usterek składnika majątku na każdym poziomie lokalizacji czynności konserwacyjnych, z którym jest powiązany.</span><span class="sxs-lookup"><span data-stu-id="b7310-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault cost control lines on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="b7310-113">Aby ograniczyć wyszukiwanie, można wybrać określone składniki majątku, daty usterek i przyczyny usterek w skróconej karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="b7310-113">If you want to limit the search, you can select specific assets, fault dates, and fault causes on the **Records to include** FastTab.</span></span>

7. <span data-ttu-id="b7310-114">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="b7310-114">Click **OK** to start the calculation.</span></span>

8. <span data-ttu-id="b7310-115">Kliknij przyciski **Grupuj wg...**, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="b7310-115">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="b7310-116">Wybrane przyciski grupy **Grupuj wg...** są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="b7310-116">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="b7310-117">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="b7310-117">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="b7310-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="b7310-118">Example</span></span>

<span data-ttu-id="b7310-119">W tym przykładzie przedstawiono obliczenia dotyczące kontroli kosztów usterki składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b7310-119">This example shows an asset fault cost control calculation.</span></span>

- <span data-ttu-id="b7310-120">W polu **Budżet pierwotny** są wyświetlane koszty budżetowe z prognozy zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="b7310-120">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="b7310-121">W polu **Koszt rzeczywisty** są wyświetlane zaksięgowane koszty w zleceniach pracy.</span><span class="sxs-lookup"><span data-stu-id="b7310-121">The **Actual cost** field shows posted costs on work orders.</span></span> 
- <span data-ttu-id="b7310-122">W polu **Ustalony koszt** są wyświetlane łączne koszty, na które firma jest zobowiązana w związku ze zleceniami pracy.</span><span class="sxs-lookup"><span data-stu-id="b7310-122">The **Committed cost** field shows total costs that your company is committed to in relation to work orders.</span></span>

    ![Rysunek 1](media/05-controlling-and-reporting.png)

<span data-ttu-id="b7310-124">Informacje na temat konfigurowania usterek można znaleźć w temacie [Zarządzanie usterkami](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="b7310-124">For information about how to set up faults, see the [Fault management](../setup-for-work-orders/fault-management.md) topic.</span></span>
