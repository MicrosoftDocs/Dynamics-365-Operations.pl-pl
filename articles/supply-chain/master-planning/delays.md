---
title: Opóźnienia
description: Ten temat zawiera informacje o datach opóźnień w planowaniu głównym. Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data.
author: roxanadiaconu
manager: AnnBe
ms.date: 03/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c26fedf15118a304469604527c33a25871356be
ms.sourcegitcommit: 8eac5eee94bb32143df44c82a2dfdbe903967af8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/20/2019
ms.locfileid: "878317"
---
# <a name="delays"></a><span data-ttu-id="c97af-104">Opóźnienia</span><span class="sxs-lookup"><span data-stu-id="c97af-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c97af-105">Ten temat zawiera informacje o datach opóźnień w planowaniu głównym.</span><span class="sxs-lookup"><span data-stu-id="c97af-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="c97af-106">Data opóźnienia to realistyczny termin przypisywany transakcji, jeśli najwcześniejsza data realizacji obliczona w planowaniu głównym jest późniejsza niż wnioskowana data.</span><span class="sxs-lookup"><span data-stu-id="c97af-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="c97af-107">Planowanie główne pozwala obliczać najwcześniejszą datę realizacji transakcji na podstawie czasów realizacji, dostępności materiałów, dostępności zdolności produkcyjnych i różnych parametrów planowania.</span><span class="sxs-lookup"><span data-stu-id="c97af-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="c97af-108">Jeżeli funkcja planowania głównego obliczy datę zamówienia, która będzie wcześniejsza niż data bieżąca, zamówienia nie da się zrealizować w terminie.</span><span class="sxs-lookup"><span data-stu-id="c97af-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="c97af-109">Takie zamówienie jest opóźnione.</span><span class="sxs-lookup"><span data-stu-id="c97af-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="c97af-110">W takim przypadku planowanie główne planuje zamówienie w przyszłość od daty bieżącej i uwzględnia czasy realizacji.</span><span class="sxs-lookup"><span data-stu-id="c97af-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="c97af-111">Te czasy realizacji zaczynają się od dowolnego składnika niższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="c97af-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="c97af-112">Następnie zamówienie otrzymuje datę opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="c97af-112">The order then receives a delayed date.</span></span> <span data-ttu-id="c97af-113">Data opóźnienia jest realistyczną datą realizacji obliczaną na podstawie bieżących danych.</span><span class="sxs-lookup"><span data-stu-id="c97af-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="c97af-114">Planowanie główne oblicza również liczbę dni opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="c97af-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="c97af-115">W niektórych przypadkach można wybrać, by nie do obliczać opóźnienia, np. kiedy wiadomo, że czas realizacji można przyspieszyć, wybierając alternatywne metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="c97af-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="c97af-116">Można skonfigurować sposób obliczania opóźnienia dla grupy zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="c97af-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="c97af-117">Następnie można dołączyć grupę zaopatrzenia do towaru później.</span><span class="sxs-lookup"><span data-stu-id="c97af-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="c97af-118">Na stronie **Parametry planowania głównego** można ustawić czas rozpoczęcia dla obliczania opóźnień.</span><span class="sxs-lookup"><span data-stu-id="c97af-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="c97af-119">Jeżeli zamówienie zostało zamknięte po tym czasie, do daty opóźnienia zamówienia dodawany jest jeden dzień opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="c97af-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> <span data-ttu-id="c97af-120">[!Uwaga}: We wcześniejszych wersjach obliczane opóźnienia były nazywane *komunikatami prognoz*, data opóźniona była nazywana *datą prognozy*, a transakcja opóźnienia była nazywana *transakcją z datą w przyszłości*.</span><span class="sxs-lookup"><span data-stu-id="c97af-120">[!NOTE} In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="desired-date"></a><span data-ttu-id="c97af-121">Wymagana data</span><span class="sxs-lookup"><span data-stu-id="c97af-121">Desired date</span></span>

<span data-ttu-id="c97af-122">Na stronie **zamówienia planowanego** na karcie **opóźnień** jest **Żądana data** dla tego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c97af-122">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="c97af-123">Wymagana data planowanego zamówienia jest podstawową datą dla opóźnień, która jest obliczona i jest równa **Żądanej dacie** obliczonej ze **zapotrzebowania netto**.</span><span class="sxs-lookup"><span data-stu-id="c97af-123">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="c97af-124">Jeśli planowane zamówienie jest wierszem BOM, wierszem produkcji lub wierszem na karcie kanban, wymagana data opiera się na **Dacie zapotrzebowania** i żądana data nie będzie wyświetlana na stronie **zamówienia planowanego**.</span><span class="sxs-lookup"><span data-stu-id="c97af-124">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="c97af-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c97af-125">Additional resources</span></span>
--------

[<span data-ttu-id="c97af-126">Ustawienia zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="c97af-126">Coverage settings</span></span>](coverage-settings.md)
