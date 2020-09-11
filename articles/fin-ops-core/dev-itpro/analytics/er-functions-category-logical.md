---
title: Lista funkcji modułu ER w kategorii funkcji logicznych
description: Ten temat zawiera ogólne informacje o funkcjach logicznych obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 08/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e622778c60646e5cc84cd6e23a5d4954a0fe0bb3
ms.sourcegitcommit: 38ad6f791c3d5688a5dc201a234ba89f155f7f03
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "3705102"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="b86a9-103">Lista funkcji modułu ER w kategorii funkcji logicznych</span><span class="sxs-lookup"><span data-stu-id="b86a9-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b86a9-104">Funkcje logiczne w module raportowania elektronicznego (ER) mogą służyć do pracy z wartościami logicznymi w celu wykonania więcej niż jednego porównania w pojedynczym wyrażeniu lub przetestowania wielu warunków.</span><span class="sxs-lookup"><span data-stu-id="b86a9-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="b86a9-105">Ten temat zawiera podsumowanie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="b86a9-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="b86a9-106">Lista obsługiwanych funkcji</span><span class="sxs-lookup"><span data-stu-id="b86a9-106">List of supported functions</span></span>

| <span data-ttu-id="b86a9-107">Funkcja</span><span class="sxs-lookup"><span data-stu-id="b86a9-107">Function</span></span> | <span data-ttu-id="b86a9-108">Opis</span><span class="sxs-lookup"><span data-stu-id="b86a9-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="b86a9-109">i</span><span class="sxs-lookup"><span data-stu-id="b86a9-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="b86a9-110">Ta funkcja zwraca wartość *logiczną* **TRUE**, jeśli wszystkie wybrane warunki zostaną spełnione.</span><span class="sxs-lookup"><span data-stu-id="b86a9-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="b86a9-111">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="b86a9-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="b86a9-112">Skrzynka</span><span class="sxs-lookup"><span data-stu-id="b86a9-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="b86a9-113">Ta funkcja oblicza wartość określonego wyrażenia względem określonych alternatywnych opcji i zwraca wynik pierwszej opcji, która jest równa wartości określonego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b86a9-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="b86a9-114">W przeciwnym razie zwraca ona domyślny wynik opcjonalny, jeśli domyślny wynik jest określony jako ostatni argument wywołanej funkcji, który nie jest poprzedzony opcją.</span><span class="sxs-lookup"><span data-stu-id="b86a9-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="b86a9-115">Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych.</span><span class="sxs-lookup"><span data-stu-id="b86a9-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="b86a9-116">Jeśli</span><span class="sxs-lookup"><span data-stu-id="b86a9-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="b86a9-117">Ta funkcja zwraca pierwszą określoną wartość, jeśli jest spełniony podany warunek.</span><span class="sxs-lookup"><span data-stu-id="b86a9-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="b86a9-118">W przeciwnym razie zwraca ona drugą określoną wartość.</span><span class="sxs-lookup"><span data-stu-id="b86a9-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="b86a9-119">Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych.</span><span class="sxs-lookup"><span data-stu-id="b86a9-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="b86a9-120">Nie</span><span class="sxs-lookup"><span data-stu-id="b86a9-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="b86a9-121">Ta funkcja zwraca odwróconą wartość logiczną określonego warunku jako wartość *logiczną*.</span><span class="sxs-lookup"><span data-stu-id="b86a9-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="b86a9-122">Or</span><span class="sxs-lookup"><span data-stu-id="b86a9-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="b86a9-123">Ta funkcja zwraca wartość *logiczną* **FALSE**, jeśli żadne wybrane warunki nie zostały spełnione.</span><span class="sxs-lookup"><span data-stu-id="b86a9-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="b86a9-124">Jeśli dowolny wybrany warunek został spełniony, ta funkcja zwraca wartość *logiczną* **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="b86a9-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="b86a9-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="b86a9-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="b86a9-126">Ta funkcja określa, czy podane dane wejściowe pasują do którejkolwiek wartości określonego elementu na podanej liście.</span><span class="sxs-lookup"><span data-stu-id="b86a9-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="b86a9-127">Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy.</span><span class="sxs-lookup"><span data-stu-id="b86a9-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="b86a9-128">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="b86a9-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="b86a9-129">ValueInLarge</span><span class="sxs-lookup"><span data-stu-id="b86a9-129">ValueInLarge</span></span>](er-functions-logical-valueinlarge.md)     | <span data-ttu-id="b86a9-130">Ta funkcja określa, czy podane dane wejściowe typu *Int64* lub *Integer* pasują do którejkolwiek wartości określonego elementu na podanej liście.</span><span class="sxs-lookup"><span data-stu-id="b86a9-130">This function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="b86a9-131">Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy.</span><span class="sxs-lookup"><span data-stu-id="b86a9-131">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="b86a9-132">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="b86a9-132">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |


## <a name="additional-resources"></a><span data-ttu-id="b86a9-133">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b86a9-133">Additional resources</span></span>

[<span data-ttu-id="b86a9-134">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="b86a9-134">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="b86a9-135">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="b86a9-135">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="b86a9-136">Język formuł raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="b86a9-136">Electronic reporting formula language</span></span>](er-formula-language.md)
