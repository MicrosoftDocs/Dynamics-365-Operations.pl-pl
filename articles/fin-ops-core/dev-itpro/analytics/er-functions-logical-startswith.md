---
title: Funkcja STARTSWITH ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji STARTSWITH w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 50883bb604d2d1f2947545ce27fa02099e70b0e6
ms.sourcegitcommit: 17cee26b03f7b5afe8a089a0a9b2380e8d377d70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2021
ms.locfileid: "6048849"
---
# <a name="startswith-er-function"></a><span data-ttu-id="9d31c-103">Funkcja STARTSWITH ER</span><span class="sxs-lookup"><span data-stu-id="9d31c-103">STARTSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d31c-104">Funkcja `STARTSWITH` określa, czy określone wejście zaczyna się określonym tekstem.</span><span class="sxs-lookup"><span data-stu-id="9d31c-104">The `STARTSWITH` function determines whether the specified input starts with the specified text.</span></span> <span data-ttu-id="9d31c-105">Zwraca wartość *logiczną* **TRUE**, jeśli określone dane wejściowe zaczyna się określonym tekstem.</span><span class="sxs-lookup"><span data-stu-id="9d31c-105">It returns a *Boolean* value of **TRUE** if the specified input starts with the specified text.</span></span> <span data-ttu-id="9d31c-106">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="9d31c-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d31c-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="9d31c-107">Syntax</span></span>

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a><span data-ttu-id="9d31c-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="9d31c-108">Arguments</span></span>

<span data-ttu-id="9d31c-109">`input`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="9d31c-109">`input`: *String*</span></span>

<span data-ttu-id="9d31c-110">Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może zaczyna się na drugim argumencie.</span><span class="sxs-lookup"><span data-stu-id="9d31c-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might start with the second argument.</span></span>

<span data-ttu-id="9d31c-111">`start text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="9d31c-111">`start text`: *String*</span></span>

<span data-ttu-id="9d31c-112">Prawidłowa ścieżka elementu źródła danych typu *Ciąg* lub stałej ciągu, której wartość może znajdować się na początku pierwszego argumentu.</span><span class="sxs-lookup"><span data-stu-id="9d31c-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the beginning of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="9d31c-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="9d31c-113">Return values</span></span>

<span data-ttu-id="9d31c-114">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="9d31c-114">*Boolean*</span></span>

<span data-ttu-id="9d31c-115">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="9d31c-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9d31c-116">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="9d31c-116">Usage notes</span></span>

<span data-ttu-id="9d31c-117">Ta funkcja może służyć do określania wyrażenia warunku funkcji [FILTER](er-functions-list-filter.md) tylko wtedy, gdy odpowiednie mapowanie jest skonfigurowane w [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) w celu uzyskania dostępu do [Microsoft Dataverse](/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="9d31c-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](/power-platform/admin/data-integrator).</span></span> <span data-ttu-id="9d31c-118">W przeciwnym razie podczas projektowania zgłaszany jest wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9d31c-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="9d31c-119">Odebrany komunikat zaleca użycie funkcji [WHERE](er-functions-list-where.md) zamiast funkcji `FILTER`, ponieważ działa ona sprawniej.</span><span class="sxs-lookup"><span data-stu-id="9d31c-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="9d31c-120">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="9d31c-120">Example 1</span></span>

<span data-ttu-id="9d31c-121">Wyrażenie zwraca `STARTSWITH ("abc", "d")` wartość **FALSE**, podczas gdy wyrażenie zwraca `STARTSWITH ("abc", "A")`wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="9d31c-121">The expression `STARTSWITH ("abc", "d")` returns **FALSE**, whereas the expression `STARTSWITH ("abc", "A")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="9d31c-122">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="9d31c-122">Example 2</span></span>

<span data-ttu-id="9d31c-123">Wyrażenie `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` zwraca wartość **TRUE**, jeśli wartość w polu **Adres** źródła danych **modelu** zaczyna się ciągiem **123 Coffee Street**.</span><span class="sxs-lookup"><span data-stu-id="9d31c-123">The expression `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` returns **TRUE** if the value of the **Address** field of the **model** data source starts with the string **123 Coffee Street**.</span></span> <span data-ttu-id="9d31c-124">W przeciwnym jest zwracana wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="9d31c-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9d31c-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9d31c-125">Additional resources</span></span>

[<span data-ttu-id="9d31c-126">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="9d31c-126">Logical functions</span></span>](er-functions-category-logical.md)
