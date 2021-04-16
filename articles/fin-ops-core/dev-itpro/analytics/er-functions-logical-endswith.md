---
title: Funkcja ENDSWITH ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ENDSWITH w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: bdd2f364e2d0b80d3df20592ec827dcabf99a06c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745408"
---
# <a name="endswith-er-function"></a><span data-ttu-id="c42ae-103">Funkcja ENDSWITH ER</span><span class="sxs-lookup"><span data-stu-id="c42ae-103">ENDSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c42ae-104">Funkcja `ENDSWITH` określa, czy określone wejście kończy się określonym tekstem.</span><span class="sxs-lookup"><span data-stu-id="c42ae-104">The `ENDSWITH` function determines whether the specified input ends with the specified text.</span></span> <span data-ttu-id="c42ae-105">Zwraca wartość *logiczną* **TRUE**, jeśli określone dane wejściowe kończą się określonym tekstem.</span><span class="sxs-lookup"><span data-stu-id="c42ae-105">It returns a *Boolean* value of **TRUE** if the specified input ends with the specified text.</span></span> <span data-ttu-id="c42ae-106">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="c42ae-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="c42ae-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="c42ae-107">Syntax</span></span>

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a><span data-ttu-id="c42ae-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c42ae-108">Arguments</span></span>

<span data-ttu-id="c42ae-109">`input`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c42ae-109">`input`: *String*</span></span>

<span data-ttu-id="c42ae-110">Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może kończyć się na drugim argumentze.</span><span class="sxs-lookup"><span data-stu-id="c42ae-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might end with the second argument.</span></span>

<span data-ttu-id="c42ae-111">`start text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c42ae-111">`start text`: *String*</span></span>

<span data-ttu-id="c42ae-112">Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może znajdować się na końcu pierwszego argumentu.</span><span class="sxs-lookup"><span data-stu-id="c42ae-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the end of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="c42ae-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c42ae-113">Return values</span></span>

<span data-ttu-id="c42ae-114">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="c42ae-114">*Boolean*</span></span>

<span data-ttu-id="c42ae-115">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="c42ae-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c42ae-116">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="c42ae-116">Usage notes</span></span>

<span data-ttu-id="c42ae-117">Ta funkcja może służyć do określania wyrażenia warunku funkcji [FILTER](er-functions-list-filter.md) tylko wtedy, gdy odpowiednie mapowanie jest skonfigurowane w [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) w celu uzyskania dostępu do [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="c42ae-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="c42ae-118">W przeciwnym razie podczas projektowania zgłaszany jest wyjątek.</span><span class="sxs-lookup"><span data-stu-id="c42ae-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="c42ae-119">Odebrany komunikat zaleca użycie funkcji [WHERE](er-functions-list-where.md) zamiast funkcji `FILTER`, ponieważ działa ona sprawniej.</span><span class="sxs-lookup"><span data-stu-id="c42ae-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="c42ae-120">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="c42ae-120">Example 1</span></span>

<span data-ttu-id="c42ae-121">Wyrażenie zwraca `ENDSWITH ("abc", "d")` wartość **FALSE**, podczas gdy wyrażenie zwraca `ENDSWITH ("abc", "C")`wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="c42ae-121">The expression `ENDSWITH ("abc", "d")` returns **FALSE**, whereas the expression `ENDSWITH ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c42ae-122">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="c42ae-122">Example 2</span></span>

<span data-ttu-id="c42ae-123">Wyrażenie `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` zwraca wartość **TRUE**, jeśli wartość w polu **Adres** źródła danych **modelu** kończy się ciągiem **USA**.</span><span class="sxs-lookup"><span data-stu-id="c42ae-123">The expression `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` returns **TRUE** if the value of the **Address** field of the **model** data source ends with the string **USA**.</span></span> <span data-ttu-id="c42ae-124">W przeciwnym jest zwracana wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="c42ae-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c42ae-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c42ae-125">Additional resources</span></span>

[<span data-ttu-id="c42ae-126">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="c42ae-126">Logical functions</span></span>](er-functions-category-logical.md)
