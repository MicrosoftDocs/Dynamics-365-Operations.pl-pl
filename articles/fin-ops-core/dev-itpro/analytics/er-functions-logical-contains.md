---
title: Funkcje CONTAINS ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CONTAINS w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a31d89f036a6e821bea2b6733c0c646145d2a47c
ms.sourcegitcommit: 17cee26b03f7b5afe8a089a0a9b2380e8d377d70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2021
ms.locfileid: "6048877"
---
# <a name="contains-er-function"></a><span data-ttu-id="e984e-103">Funkcje CONTAINS ER</span><span class="sxs-lookup"><span data-stu-id="e984e-103">CONTAINS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e984e-104">Ta funkcja `CONTAINS` określa, czy określone dane wejściowe zawierają określony tekst.</span><span class="sxs-lookup"><span data-stu-id="e984e-104">The `CONTAINS` function determines whether the specified input contains the specified text.</span></span> <span data-ttu-id="e984e-105">Zwraca wartość *logiczną* **TRUE**, jeśli określone dane wejściowe zawierają określony tekst.</span><span class="sxs-lookup"><span data-stu-id="e984e-105">It returns a *Boolean* value of **TRUE** if the specified input contains the specified text.</span></span> <span data-ttu-id="e984e-106">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="e984e-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="e984e-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="e984e-107">Syntax</span></span>

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a><span data-ttu-id="e984e-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="e984e-108">Arguments</span></span>

<span data-ttu-id="e984e-109">`input`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e984e-109">`input`: *String*</span></span>

<span data-ttu-id="e984e-110">Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może zawierać drugi argument.</span><span class="sxs-lookup"><span data-stu-id="e984e-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might contain the second argument.</span></span>

<span data-ttu-id="e984e-111">`search text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e984e-111">`search text`: *String*</span></span>

<span data-ttu-id="e984e-112">Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może znajdować się w pierwszym argumencie.</span><span class="sxs-lookup"><span data-stu-id="e984e-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be contained in the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="e984e-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="e984e-113">Return values</span></span>

<span data-ttu-id="e984e-114">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="e984e-114">*Boolean*</span></span>

<span data-ttu-id="e984e-115">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="e984e-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e984e-116">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="e984e-116">Usage notes</span></span>

<span data-ttu-id="e984e-117">Ta funkcja może służyć do określania wyrażenia warunku funkcji [FILTER](er-functions-list-filter.md) tylko wtedy, gdy odpowiednie mapowanie jest skonfigurowane w [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) w celu uzyskania dostępu do [Microsoft Dataverse](/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="e984e-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](/power-platform/admin/data-integrator).</span></span> <span data-ttu-id="e984e-118">W przeciwnym razie podczas projektowania zgłaszany jest wyjątek.</span><span class="sxs-lookup"><span data-stu-id="e984e-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="e984e-119">Odebrany komunikat zaleca użycie funkcji [WHERE](er-functions-list-where.md) zamiast funkcji `FILTER`, ponieważ działa ona sprawniej.</span><span class="sxs-lookup"><span data-stu-id="e984e-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="e984e-120">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="e984e-120">Example 1</span></span>

<span data-ttu-id="e984e-121">Wyrażenie zwraca `CONTAINS ("abc", "d")` wartość **FALSE**, podczas gdy wyrażenie zwraca `CONTAINS ("abc", "C")`wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="e984e-121">The expression `CONTAINS ("abc", "d")` returns **FALSE**, whereas the expression `CONTAINS ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="e984e-122">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="e984e-122">Example 2</span></span>

<span data-ttu-id="e984e-123">Wyrażenie `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` zwraca wartość **TRUE**, jeśli wartość w polu **Adres** źródła danych **modelu** zawiera ciąg **DEU**.</span><span class="sxs-lookup"><span data-stu-id="e984e-123">The expression `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` returns **TRUE** if the value of the **Address** field of the **model** data source contains the string **DEU**.</span></span> <span data-ttu-id="e984e-124">W przeciwnym jest zwracana wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="e984e-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e984e-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e984e-125">Additional resources</span></span>

[<span data-ttu-id="e984e-126">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="e984e-126">Logical functions</span></span>](er-functions-category-logical.md)
