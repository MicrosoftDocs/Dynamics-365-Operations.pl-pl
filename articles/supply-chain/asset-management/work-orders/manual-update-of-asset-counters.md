---
title: Ręczna aktualizacja liczników zasobów
description: W tym temacie opisano ręczną aktualizację liczników składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6dfea7ca166948f507a1cdea20f3e4cce16080ce
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219492"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="aac8d-103">Ręczna aktualizacja liczników zasobów</span><span class="sxs-lookup"><span data-stu-id="aac8d-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="aac8d-104">Liczniki służą do tworzenia rejestracji na składnikach majątku, takich jak rejestracje dotyczące liczby godzin eksploatacji składnika majątku lub ilości, która została wyprodukowana.</span><span class="sxs-lookup"><span data-stu-id="aac8d-104">Counters are used to create registrations on an asset, such as registrations about the number of hours that the asset has been in operation or the quantity that has been produced.</span></span>

<span data-ttu-id="aac8d-105">Typ licznika wybrany dla licznika może być skonfigurowany do dziedziczenia wartości liczników.</span><span class="sxs-lookup"><span data-stu-id="aac8d-105">The counter type that is selected for a counter might be set to inherit counter values.</span></span> <span data-ttu-id="aac8d-106">Innymi słowy, opcja **Dziedzicz wartości licznika** ustawiona na wartość **Tak** na skróconej karcie **Ogólne** na stronie **Liczniki** (**Zarządzanie składnikami majątku** > **Konfiguracja** > **Typy składników majątku** > **Liczniki**).</span><span class="sxs-lookup"><span data-stu-id="aac8d-106">In other words, the **Inherit asset counter values** option is set to **Yes** on the **General** FastTab of the **Counters** page (**Asset management** > **Setup** > **Asset types** > **Counters**).</span></span> <span data-ttu-id="aac8d-107">W takim przypadku podczas tworzenia nowego wiersza licznika tego typu każdy podrzędny składnik, który używa tego samego typu licznika, jest automatycznie aktualizowany.</span><span class="sxs-lookup"><span data-stu-id="aac8d-107">In this case, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="aac8d-108">Na stronie **Wszystkie składniki majątku** można tworzyć godziny lub rejestracje liczników ilości dla składnika w oparciu o odczyty w składniku.</span><span class="sxs-lookup"><span data-stu-id="aac8d-108">On the **All assets** page, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="aac8d-109">Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="aac8d-109">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="aac8d-110">Wybierz środek trwały, a następnie w okienku akcji na karcie **Składnik majątku** w grupie **Zapobiegawcze** wybierz pozycję **Liczniki**.</span><span class="sxs-lookup"><span data-stu-id="aac8d-110">Select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span> <span data-ttu-id="aac8d-111">Na stronie **Liczniki składników majątku** zostanie wyświetlona lista wszystkich poprzednich rejestracji liczników, które zostały wykonane dla wybranego składnika.</span><span class="sxs-lookup"><span data-stu-id="aac8d-111">The **Asset counters** page shows a list of all previous counter registrations that have been made on the selected asset.</span></span>

3. <span data-ttu-id="aac8d-112">Wybierz pozycję **Nowy**, aby utworzyć nową rejestrację.</span><span class="sxs-lookup"><span data-stu-id="aac8d-112">Select **New** to create a registration.</span></span> <span data-ttu-id="aac8d-113">Identyfikator składnika majątku jest automatycznie wprowadzana w polu **Składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="aac8d-113">The asset ID is automatically entered in the **Asset** field.</span></span>

4. <span data-ttu-id="aac8d-114">W polu **Licznik** wybierz odpowiedni licznik.</span><span class="sxs-lookup"><span data-stu-id="aac8d-114">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="aac8d-115">Do wyboru dostępne są tylko liczniki powiązane z typem składnika wybranego w obszarze zawartości.</span><span class="sxs-lookup"><span data-stu-id="aac8d-115">Only counters that are related to the asset type selected on the asset are available for selection.</span></span> <span data-ttu-id="aac8d-116">Jednostka powiązana jest automatycznie wstawiana w polu **Jednostka**.</span><span class="sxs-lookup"><span data-stu-id="aac8d-116">The related unit is automatically entered in the **Unit** field.</span></span>

5. <span data-ttu-id="aac8d-117">W polu **Zarejestrowano** wybierz datę i godzinę rejestracji licznika.</span><span class="sxs-lookup"><span data-stu-id="aac8d-117">In the **Registered** field, select the date and time for the counter registration.</span></span>

6. <span data-ttu-id="aac8d-118">W polu **Wartość** wprowadź liczbę od ostatniej rejestracji licznika.</span><span class="sxs-lookup"><span data-stu-id="aac8d-118">In the **Value** field, enter the number since the last counter registration.</span></span> <span data-ttu-id="aac8d-119">Można również w polu **Zagregowana wartość** wprowadzić łączną liczbę.</span><span class="sxs-lookup"><span data-stu-id="aac8d-119">Alternatively, in the **Aggregated value** field, enter the total count number.</span></span>

<span data-ttu-id="aac8d-120">Należy uwzględnić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="aac8d-120">Note the following points:</span></span>

- <span data-ttu-id="aac8d-121">W przypadku fizycznego zainstalowania nowego licznika dla składnika majątku należy zarejestrować zmianę składnika majątku na stronie **Liczniki składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="aac8d-121">If you physically install a new counter on an asset, you must register the change on the asset on the **Asset counters** page.</span></span> <span data-ttu-id="aac8d-122">Następnie należy utworzyć dwa wiersze rejestracji o identycznych sygnaturach czasowych.</span><span class="sxs-lookup"><span data-stu-id="aac8d-122">Next, you must create two registration lines that have identical timestamps.</span></span> <span data-ttu-id="aac8d-123">Pierwszy wiersz musi dotyczyć zastępowanego licznika.</span><span class="sxs-lookup"><span data-stu-id="aac8d-123">The first line must be for the counter that you're replacing.</span></span> <span data-ttu-id="aac8d-124">W wierszu, który jest powiązany z nowym licznikiem, zaznacz pole wyboru **Resetuj licznik**.</span><span class="sxs-lookup"><span data-stu-id="aac8d-124">On the line that is related to the new counter, select the **Counter reset** check box.</span></span> <span data-ttu-id="aac8d-125">W polu **Sumy całkowite** wartość sumy całkowitej jest sumą wszystkich zarejestrowanych wartości licznika z danego typu licznika.</span><span class="sxs-lookup"><span data-stu-id="aac8d-125">In the **Totals** field, the total count number is the sum of the counter totals of all registered values on that counter type.</span></span>

- <span data-ttu-id="aac8d-126">Jeśli zaznaczono pole wyboru **Resetuj licznik** na składniku majątku, należy użyć planu konserwacji z typem interwału „jeden raz od...” lub „po osiągnięciu...”, licznik jest nadal aktywny w nowym wierszu licznika, ponieważ tworzona jest oddzielna linia licznika i rozpoczyna się od nowego licznika.</span><span class="sxs-lookup"><span data-stu-id="aac8d-126">If the **Counter reset** check box is selected on an asset using a maintenance plan that has a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line, because you create a separate counter line and start over with a new counter.</span></span>

<span data-ttu-id="aac8d-127">Na poniższej ilustracji przedstawiono przykład strony **Liczniki składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="aac8d-127">The illustration below shows an example of the **Asset counters** page.</span></span>

![Rysunek 1](media/11-work-orders.png)

<span data-ttu-id="aac8d-129">Na stronie **Liczniki składników majątku** (**Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Liczniki składników majątku**) można w tym samym czasie przeprowadzać rejestracje liczników dla kilku składników majątku wedle potrzeby.</span><span class="sxs-lookup"><span data-stu-id="aac8d-129">On the **Asset counters** page (**Asset management** > **Inquiries** > **Assets** > **Asset counters**), you can make counter registrations on several assets at the same time, as you require.</span></span>

>[!NOTE]
><span data-ttu-id="aac8d-130">Istnieje możliwość skonfigurowania zakresu w celu zdefiniowania odchyleń dla ręcznej rejestracji licznika.</span><span class="sxs-lookup"><span data-stu-id="aac8d-130">You can set up a range to define deviations in manual counter registrations.</span></span> <span data-ttu-id="aac8d-131">Można również określić typ komunikatu, który będzie wyświetlany, jeśli rejestracje znajdują się poza zdefiniowanym zakresem.</span><span class="sxs-lookup"><span data-stu-id="aac8d-131">You can also specify the type of message that is shown if registrations are outside the defined range.</span></span> <span data-ttu-id="aac8d-132">Aby uzyskać więcej informacji na temat sposobu konfigurowania liczników, zobacz [Liczniki](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="aac8d-132">For more information about how to set up counters, see [Counters](../setup-for-objects/counters.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]