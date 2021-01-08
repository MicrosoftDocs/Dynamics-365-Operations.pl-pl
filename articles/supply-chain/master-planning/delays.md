---
title: Opóźnienia
description: Ten temat zawiera informacje o datach opóźnień w planowaniu głównym. Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data.
author: roxanadiaconu
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da09d670fd952d885f013693b6362cf9002343ff
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435468"
---
# <a name="delays"></a><span data-ttu-id="209f7-104">Opóźnienia</span><span class="sxs-lookup"><span data-stu-id="209f7-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="209f7-105">Ten temat zawiera informacje o datach opóźnień w planowaniu głównym.</span><span class="sxs-lookup"><span data-stu-id="209f7-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="209f7-106">Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data.</span><span class="sxs-lookup"><span data-stu-id="209f7-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="209f7-107">Planowanie główne pozwala obliczać najwcześniejszą datę realizacji transakcji na podstawie czasów realizacji, dostępności materiałów, dostępności zdolności produkcyjnych i różnych parametrów planowania.</span><span class="sxs-lookup"><span data-stu-id="209f7-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="209f7-108">Jeżeli funkcja planowania głównego obliczy datę zamówienia, która będzie wcześniejsza niż data bieżąca, zamówienia nie da się zrealizować w terminie.</span><span class="sxs-lookup"><span data-stu-id="209f7-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="209f7-109">Takie zamówienie jest opóźnione.</span><span class="sxs-lookup"><span data-stu-id="209f7-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="209f7-110">W takim przypadku planowanie główne planuje zamówienie w przyszłość od daty bieżącej i uwzględnia czasy realizacji.</span><span class="sxs-lookup"><span data-stu-id="209f7-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="209f7-111">Te czasy realizacji zaczynają się od dowolnego składnika niższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="209f7-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="209f7-112">Następnie zamówienie otrzymuje datę opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="209f7-112">The order then receives a delayed date.</span></span> <span data-ttu-id="209f7-113">Data opóźnienia jest realistyczną datą realizacji obliczaną na podstawie bieżących danych.</span><span class="sxs-lookup"><span data-stu-id="209f7-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="209f7-114">Planowanie główne oblicza również liczbę dni opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="209f7-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="209f7-115">W niektórych przypadkach można wybrać, by nie do obliczać opóźnienia, np. kiedy wiadomo, że czas realizacji można przyspieszyć, wybierając alternatywne metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="209f7-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="209f7-116">Można skonfigurować sposób obliczania opóźnienia dla grupy zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="209f7-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="209f7-117">Następnie można dołączyć grupę zaopatrzenia do towaru później.</span><span class="sxs-lookup"><span data-stu-id="209f7-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="209f7-118">Na stronie **Parametry planowania głównego** można ustawić czas rozpoczęcia dla obliczania opóźnień.</span><span class="sxs-lookup"><span data-stu-id="209f7-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="209f7-119">Jeżeli zamówienie zostało zamknięte po tym czasie, do daty opóźnienia zamówienia dodawany jest jeden dzień opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="209f7-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> [!NOTE]
> <span data-ttu-id="209f7-120">We wcześniejszych wersjach obliczane opóźnienia były nazywane *komunikatami prognoz*, data opóźniona była nazywana *datą prognozy*, a transakcja opóźnienia była nazywana *transakcją z datą w przyszłości*.</span><span class="sxs-lookup"><span data-stu-id="209f7-120">In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a><span data-ttu-id="209f7-121">Ograniczone opóźnienia w konfiguracji produkcji z wieloma poziomami BOM</span><span class="sxs-lookup"><span data-stu-id="209f7-121">Limited delays in production setup with multiple BOM levels</span></span>
<span data-ttu-id="209f7-122">Podczas pracy z opóźnieniami w konfiguracji produkcji, która ma wiele poziomów BOM, należy zwrócić uwagę, że tylko towary znajdujące się bezpośrednio powyżej towaru (w strukturze BOM), które powodują opóźnienie, będą aktualizowane z opóźnieniem w ramach procesu planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="209f7-122">When you work with delays in a production setup that has multiple BOM levels, it is important to note that only the items directly above the item (in the BOM structure) causing the delay, will be updated with a delay as part of the master planning run.</span></span> <span data-ttu-id="209f7-123">Inne towary w strukturze BOM nie uzyskują opóźnień zastosowanych do momentu zaakceptowania lub zaakceptowania pierwszego planu głównego, gdy zamówienie planowane na najwyższy poziom jest potwierdzone lub wyprodukowane.</span><span class="sxs-lookup"><span data-stu-id="209f7-123">Other items in the BOM structure will not get the delay applied until the first master planning run, when the planned order for the top level is approved or firmed.</span></span> 

<span data-ttu-id="209f7-124">W celu obejścia tego znanego ograniczenia zlecenia produkcyjne w górnej części struktury BOM z opóźnieniami mogą zostać zatwierdzone (lub wyprodukowane) przed kolejnym uruchomieniem planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="209f7-124">To work around this known limitation, the production orders on the top of the BOM structure with delays can be approved (or firmed) prior to the next master planning run.</span></span> <span data-ttu-id="209f7-125">Dzięki temu opóźnienie z opóźnionych zatwierdzonych planowanych zleceń produkcyjnych zostanie zachowane, a wszystkie podskładniki zostaną odpowiednio zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="209f7-125">This way the delay from the delayed approved planned production order will be kept and all underlying components will be updated accordingly.</span></span>
<span data-ttu-id="209f7-126">Komunikaty akcji mogą być również używane do identyfikowania zamówień planowanych, które można przenieść do późniejszej daty z powodu innych opóźnień w strukturze BOM.</span><span class="sxs-lookup"><span data-stu-id="209f7-126">Action messages can also be used to identify planned orders that can be moved to a later date, due to other delays in the BOM structure.</span></span>

## <a name="desired-date"></a><span data-ttu-id="209f7-127">Wymagana data</span><span class="sxs-lookup"><span data-stu-id="209f7-127">Desired date</span></span>

<span data-ttu-id="209f7-128">Na stronie **zamówienia planowanego** na karcie **opóźnień** jest **Żądana data** dla tego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="209f7-128">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="209f7-129">Wymagana data planowanego zamówienia jest podstawową datą dla opóźnień, która jest obliczona i jest równa **Żądanej dacie** obliczonej ze **zapotrzebowania netto**.</span><span class="sxs-lookup"><span data-stu-id="209f7-129">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="209f7-130">Jeśli planowane zamówienie jest wierszem BOM, wierszem produkcji lub wierszem na karcie kanban, wymagana data opiera się na **Dacie zapotrzebowania** i żądana data nie będzie wyświetlana na stronie **zamówienia planowanego**.</span><span class="sxs-lookup"><span data-stu-id="209f7-130">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="209f7-131">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="209f7-131">Additional resources</span></span>
--------

[<span data-ttu-id="209f7-132">Ustawienia zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="209f7-132">Coverage settings</span></span>](coverage-settings.md)
