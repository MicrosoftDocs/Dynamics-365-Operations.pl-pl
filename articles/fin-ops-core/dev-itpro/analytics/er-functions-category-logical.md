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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a37b3341b05fde1283a21a0c52faec26cd1a7030
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686200"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="1f4db-103">Lista funkcji modułu ER w kategorii funkcji logicznych</span><span class="sxs-lookup"><span data-stu-id="1f4db-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f4db-104">Funkcje logiczne w module raportowania elektronicznego (ER) mogą służyć do pracy z wartościami logicznymi w celu wykonania więcej niż jednego porównania w pojedynczym wyrażeniu lub przetestowania wielu warunków.</span><span class="sxs-lookup"><span data-stu-id="1f4db-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="1f4db-105">Ten temat zawiera podsumowanie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="1f4db-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="1f4db-106">Lista obsługiwanych funkcji</span><span class="sxs-lookup"><span data-stu-id="1f4db-106">List of supported functions</span></span>

| <span data-ttu-id="1f4db-107">Funkcja</span><span class="sxs-lookup"><span data-stu-id="1f4db-107">Function</span></span> | <span data-ttu-id="1f4db-108">Opis</span><span class="sxs-lookup"><span data-stu-id="1f4db-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="1f4db-109">i</span><span class="sxs-lookup"><span data-stu-id="1f4db-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="1f4db-110">Ta funkcja zwraca wartość *logiczną* **TRUE**, jeśli wszystkie wybrane warunki zostaną spełnione.</span><span class="sxs-lookup"><span data-stu-id="1f4db-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="1f4db-111">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="1f4db-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="1f4db-112">Skrzynka</span><span class="sxs-lookup"><span data-stu-id="1f4db-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="1f4db-113">Ta funkcja oblicza wartość określonego wyrażenia względem określonych alternatywnych opcji i zwraca wynik pierwszej opcji, która jest równa wartości określonego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="1f4db-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="1f4db-114">W przeciwnym razie zwraca ona domyślny wynik opcjonalny, jeśli domyślny wynik jest określony jako ostatni argument wywołanej funkcji, który nie jest poprzedzony opcją.</span><span class="sxs-lookup"><span data-stu-id="1f4db-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="1f4db-115">Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych.</span><span class="sxs-lookup"><span data-stu-id="1f4db-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="1f4db-116">Jeśli</span><span class="sxs-lookup"><span data-stu-id="1f4db-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="1f4db-117">Ta funkcja zwraca pierwszą określoną wartość, jeśli jest spełniony podany warunek.</span><span class="sxs-lookup"><span data-stu-id="1f4db-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="1f4db-118">W przeciwnym razie zwraca ona drugą określoną wartość.</span><span class="sxs-lookup"><span data-stu-id="1f4db-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="1f4db-119">Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych.</span><span class="sxs-lookup"><span data-stu-id="1f4db-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="1f4db-120">Nie</span><span class="sxs-lookup"><span data-stu-id="1f4db-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="1f4db-121">Ta funkcja zwraca odwróconą wartość logiczną określonego warunku jako wartość *logiczną*.</span><span class="sxs-lookup"><span data-stu-id="1f4db-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="1f4db-122">Or</span><span class="sxs-lookup"><span data-stu-id="1f4db-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="1f4db-123">Ta funkcja zwraca wartość *logiczną* **FALSE**, jeśli żadne wybrane warunki nie zostały spełnione.</span><span class="sxs-lookup"><span data-stu-id="1f4db-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="1f4db-124">Jeśli dowolny wybrany warunek został spełniony, ta funkcja zwraca wartość *logiczną* **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="1f4db-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="1f4db-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="1f4db-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="1f4db-126">Ta funkcja określa, czy podane dane wejściowe pasują do którejkolwiek wartości określonego elementu na podanej liście.</span><span class="sxs-lookup"><span data-stu-id="1f4db-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="1f4db-127">Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy.</span><span class="sxs-lookup"><span data-stu-id="1f4db-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="1f4db-128">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="1f4db-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="1f4db-129">ValueInLarge</span><span class="sxs-lookup"><span data-stu-id="1f4db-129">ValueInLarge</span></span>](er-functions-logical-valueinlarge.md)     | <span data-ttu-id="1f4db-130">Ta funkcja określa, czy podane dane wejściowe typu *Int64* lub *Integer* pasują do którejkolwiek wartości określonego elementu na podanej liście.</span><span class="sxs-lookup"><span data-stu-id="1f4db-130">This function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="1f4db-131">Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy.</span><span class="sxs-lookup"><span data-stu-id="1f4db-131">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="1f4db-132">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="1f4db-132">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |


## <a name="additional-resources"></a><span data-ttu-id="1f4db-133">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1f4db-133">Additional resources</span></span>

[<span data-ttu-id="1f4db-134">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="1f4db-134">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="1f4db-135">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="1f4db-135">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="1f4db-136">Język formuł raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="1f4db-136">Electronic reporting formula language</span></span>](er-formula-language.md)
