---
title: GETENUMVALUEBYNAME, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GETENUMVALUEBYNAME w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 09/23/2020
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
ms.openlocfilehash: 722ea8ea233d617b0584e21e98073428f16c0801
ms.sourcegitcommit: ad5b7676fc1213316e478afcffbfaee7d813f3bb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "3885234"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="d5243-103">GETENUMVALUEBYNAME, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="d5243-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d5243-104">Funkcja `GETENUMVALUEBYNAME` wyszukuje określoną wartość *wyliczenia* w źródle danych określonego wyliczenia przy użyciu nazwy wyliczenia, która jest określona jako wartość typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="d5243-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="d5243-105">W przypadku znalezienia wartości typu *Wyliczenie* funkcja zwraca tę wartość.</span><span class="sxs-lookup"><span data-stu-id="d5243-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="d5243-106">W przeciwnym razie funkcja zwraca wartość **null** wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="d5243-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5243-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="d5243-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="d5243-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d5243-108">Arguments</span></span>

<span data-ttu-id="d5243-109">`enumeration data source path`: *Wyliczenie*</span><span class="sxs-lookup"><span data-stu-id="d5243-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="d5243-110">Prawidłowa ścieżka źródła danych jednego z następujących typów wyliczenia:</span><span class="sxs-lookup"><span data-stu-id="d5243-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="d5243-111">Wyliczanie modelu raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="d5243-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="d5243-112">Wyliczenie formatu ER</span><span class="sxs-lookup"><span data-stu-id="d5243-112">ER format enumeration</span></span>
- <span data-ttu-id="d5243-113">Wyliczenie aplikacji Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="d5243-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="d5243-114">`enumeration value text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d5243-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="d5243-115">Wartość ciągu, która reprezentuje nazwę pojedynczej wartości wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="d5243-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="d5243-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="d5243-116">Return values</span></span>

<span data-ttu-id="d5243-117">*Wyliczenie* z dopuszczalną wartością null</span><span class="sxs-lookup"><span data-stu-id="d5243-117">Nullable *Enum*</span></span>

<span data-ttu-id="d5243-118">Wyjściowa wartość wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="d5243-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d5243-119">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="d5243-119">Usage notes</span></span>

<span data-ttu-id="d5243-120">Wyjątek nie jest zgłaszany, jeśli wartość *wyliczenia* nie zostanie znaleziona przy użyciu nazwy wartości wyliczenia określonej jako wartość typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="d5243-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="d5243-121">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="d5243-121">Example 1</span></span>

<span data-ttu-id="d5243-122">Na poniższej ilustracji wartość stałotekstowa **ReportDirection** została wprowadzona do modelu danych.</span><span class="sxs-lookup"><span data-stu-id="d5243-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="d5243-123">Zauważ, że etykiety są zdefiniowane dla wartości wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="d5243-123">Notice that labels are defined for the enumeration values.</span></span>

![Dostępne wartości dla wyliczenia modelu danych](./media/ER-data-model-enumeration-values.PNG)

<span data-ttu-id="d5243-125">Na ilustracji przedstawiono następujące szczegóły:</span><span class="sxs-lookup"><span data-stu-id="d5243-125">The following illustration shows these details:</span></span>

- <span data-ttu-id="d5243-126">Źródło danych **$Direction** jest skonfigurowane w raporcie ER.</span><span class="sxs-lookup"><span data-stu-id="d5243-126">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="d5243-127">To źródło danych jest skonfigurowane na podstawie wyliczenia modelu **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="d5243-127">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="d5243-128">Wyrażenie `$IsArrivals` jest zaprojektowane tak, aby używało źródła danych **$Direction** opartego na wyliczeniu modelu jako parametru tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="d5243-128">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="d5243-129">Wartością tego wyrażenia porównania jest **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="d5243-129">The value of this comparison expression is **TRUE**.</span></span>

![Przykład wyliczenia modelu danych](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a><span data-ttu-id="d5243-131">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="d5243-131">Example 2</span></span>

<span data-ttu-id="d5243-132">Funkcje `GETENUMVALUEBYNAME` i [`LISTOFFIELDS`](er-functions-list-listoffields.md) umożliwiają pobieranie wartości i etykiet obsługiwanych wyliczeń jako wartości tekstowe.</span><span class="sxs-lookup"><span data-stu-id="d5243-132">The `GETENUMVALUEBYNAME` and [`LISTOFFIELDS`](er-functions-list-listoffields.md) functions let you fetch values and labels of supported enumerations as text values.</span></span> <span data-ttu-id="d5243-133">(Obsługiwane wyliczenia to wyliczenia aplikacji, wyliczenia modeli danych i wyliczenia formatów.)</span><span class="sxs-lookup"><span data-stu-id="d5243-133">(The supported enumerations are application enumerations, data model enumerations, and format enumerations.)</span></span>

<span data-ttu-id="d5243-134">Na poniższej ilustracji źródło danych **TransType** zostało wprowadzone w odwzorowaniu modelu.</span><span class="sxs-lookup"><span data-stu-id="d5243-134">In the following illustration, the **TransType** data source is introduced in a model mapping.</span></span> <span data-ttu-id="d5243-135">To źródło danych odwołuje się do wyliczenia aplikacji **LedgerTransType**.</span><span class="sxs-lookup"><span data-stu-id="d5243-135">This data source refers to the **LedgerTransType** application enumeration.</span></span>

![Źródło danych mapowania modelu, które odwołuje się do wyliczenia aplikacji](./media/er-functions-text-getenumvaluebyname-example2-1.png)

<span data-ttu-id="d5243-137">Na poniższej ilustracji przedstawiono źródło danych **TransTypeList** skonfigurowane w odwzorowaniu modelu.</span><span class="sxs-lookup"><span data-stu-id="d5243-137">The following illustration shows the **TransTypeList** data source that is configured in a model mapping.</span></span> <span data-ttu-id="d5243-138">To źródło danych jest skonfigurowane na podstawie wyliczenia aplikacji **TransType**.</span><span class="sxs-lookup"><span data-stu-id="d5243-138">This data source is configured based on the **TransType** application enumeration.</span></span> <span data-ttu-id="d5243-139">Funkcja `LISTOFFIELDS` służy do zwracania wszystkich wartości wyliczenia jako listy rekordów zawierających pola.</span><span class="sxs-lookup"><span data-stu-id="d5243-139">The `LISTOFFIELDS` function is used to return all enumeration values as a list of records that contain fields.</span></span> <span data-ttu-id="d5243-140">W ten sposób szczegóły wszystkich wartości wyliczenia są ujawniane.</span><span class="sxs-lookup"><span data-stu-id="d5243-140">In this way, the details of every enumeration value are exposed.</span></span>

> [!NOTE]
> <span data-ttu-id="d5243-141">Pole **EnumValue** jest skonfigurowane dla źródła danych **TransTypeList** za pomocą wyrażenia `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`.</span><span class="sxs-lookup"><span data-stu-id="d5243-141">The **EnumValue** field is configured for the **TransTypeList** data source by using the `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` expression.</span></span> <span data-ttu-id="d5243-142">To pole zwraca wartość wyliczenia dla każdego rekordu na liście.</span><span class="sxs-lookup"><span data-stu-id="d5243-142">This field returns an enumeration value for every record in this list.</span></span>

![Źródło danych mapowania modelu, które zwraca wszystkie wartości wyliczenia wybranego wyliczenia jako listę rekordów](./media/er-functions-text-getenumvaluebyname-example2-2.png)

<span data-ttu-id="d5243-144">Na poniższej ilustracji przedstawiono źródło danych **VendTrans** skonfigurowane w odwzorowaniu modelu.</span><span class="sxs-lookup"><span data-stu-id="d5243-144">The following illustration shows the **VendTrans** data source that is configured in a model mapping.</span></span> <span data-ttu-id="d5243-145">To źródło danych zwraca rekordy transakcji dostawcy z tabeli aplikacji **VendTrans**.</span><span class="sxs-lookup"><span data-stu-id="d5243-145">This data source returns vendor transaction records from the **VendTrans** application table.</span></span> <span data-ttu-id="d5243-146">Typ księgi każdej transakcji jest określony przez wartość pola **VendTrans**.</span><span class="sxs-lookup"><span data-stu-id="d5243-146">The ledger type of every transaction is defined by the value of the **TransType** field.</span></span>

> [!NOTE]
> <span data-ttu-id="d5243-147">Pole **TransTypeTitle** jest skonfigurowane dla źródła danych **VendTrans** za pomocą wyrażenia `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`.</span><span class="sxs-lookup"><span data-stu-id="d5243-147">The **TransTypeTitle** field is configured for the **VendTrans** data source by using the `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` expression.</span></span> <span data-ttu-id="d5243-148">To pole zwraca etykietę wartości wyliczenia bieżącej transakcji jako tekst, jeśli ta wartość jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="d5243-148">This field returns the label of an enumeration value of the current transaction as text, if this enumeration value is available.</span></span> <span data-ttu-id="d5243-149">W przeciwnym razie zwraca pustą wartość ciągu.</span><span class="sxs-lookup"><span data-stu-id="d5243-149">Otherwise, it returns a blank string value.</span></span>
>
> <span data-ttu-id="d5243-150">Pole **TransTypeTitle** jest powiązane z polem **LedgerType** modelu danych, które umożliwia używanie tych informacji w każdym formacie ER, który używa modelu danych jako źródła danych.</span><span class="sxs-lookup"><span data-stu-id="d5243-150">The **TransTypeTitle** field is bound to the **LedgerType** field of a data model that enables this information to be used in every ER format that uses the data model as a source of data.</span></span>

![Źródło danych mapowania modelu, które zwraca transakcje dostawcy](./media/er-functions-text-getenumvaluebyname-example2-3.png)

<span data-ttu-id="d5243-152">Na poniższej ilustracji przedstawiono sposób użycia [debugera źródła danych](er-debug-data-sources.md) do testowania skonfigurowanego mapowania modelu.</span><span class="sxs-lookup"><span data-stu-id="d5243-152">The following illustration shows how you can use the [data source debugger](er-debug-data-sources.md) to test the configured model mapping.</span></span>

![Użycie debugera źródła danych do testowania skonfigurowanego mapowania modelu](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

<span data-ttu-id="d5243-154">Pole **LedgerType** model danych udostępnia etykiety typów transakcji zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="d5243-154">The **LedgerType** field of a data model exposes labels of transaction types as expected.</span></span>

<span data-ttu-id="d5243-155">Jeśli to rozwiązanie ma być używane w przypadku dużej ilości danych transakcyjnych, należy wziąć pod uwagę wydajność wykonania.</span><span class="sxs-lookup"><span data-stu-id="d5243-155">If you plan to use this approach for a large amount of transactional data, you must consider execution performance.</span></span> <span data-ttu-id="d5243-156">Aby uzyskać więcej informacji, zobacz [Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="d5243-156">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d5243-157">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d5243-157">Additional resources</span></span>

[<span data-ttu-id="d5243-158">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="d5243-158">Text functions</span></span>](er-functions-category-text.md)

[<span data-ttu-id="d5243-159">Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością</span><span class="sxs-lookup"><span data-stu-id="d5243-159">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)

[<span data-ttu-id="d5243-160">LISTOFFIELDS, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="d5243-160">LISTOFFIELDS ER function</span></span>](er-functions-list-listoffields.md)

[<span data-ttu-id="d5243-161">FIRSTORNULL, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="d5243-161">FIRSTORNULL ER function</span></span>](er-functions-list-firstornull.md)

[<span data-ttu-id="d5243-162">WHERE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="d5243-162">WHERE ER function</span></span>](er-functions-list-where.md)
