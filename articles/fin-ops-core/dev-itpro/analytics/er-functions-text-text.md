---
title: TEXT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TEXT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 20313133ce29b8d5048814ff78ce4ea4f5c54d4a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743695"
---
# <a name="text-er-function"></a><span data-ttu-id="b5c58-103">TEXT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="b5c58-103">TEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5c58-104">Funkcja `TEXT` zwraca określoną liczbę jako wartość typu *Ciąg* po przekształceniu na ciąg tekstowy, który jest sformatowany zgodnie z ustawieniami regionalnymi serwera bieżącego wystąpienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b5c58-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="b5c58-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b5c58-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="b5c58-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b5c58-106">Arguments</span></span>

<span data-ttu-id="b5c58-107">`number`: *Liczba całkowita* lub *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="b5c58-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="b5c58-108">Wartość numeryczna, która musi zostać przekonwertowana na ciąg tekstowy.</span><span class="sxs-lookup"><span data-stu-id="b5c58-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="b5c58-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="b5c58-109">Return values</span></span>

<span data-ttu-id="b5c58-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b5c58-110">*String*</span></span>

<span data-ttu-id="b5c58-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="b5c58-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b5c58-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="b5c58-112">Usage notes</span></span>

<span data-ttu-id="b5c58-113">Dla wartości typu *Liczba rzeczywista* konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="b5c58-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="b5c58-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="b5c58-114">Example</span></span>

<span data-ttu-id="b5c58-115">Jeśli ustawienia regionalne serwera wystąpienia aplikacji Microsoft Dynamics 365 Finance są określone jako **EN-US**, funkcja `TEXT (NOW ())` zwraca datę bieżącej sesji aplikacji, 17 grudnia 2015 roku, jako ciąg tekstowy **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="b5c58-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="b5c58-116">Funkcja `TEXT (1/3)` zwraca wartość **"0.33"**.</span><span class="sxs-lookup"><span data-stu-id="b5c58-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b5c58-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b5c58-117">Additional resources</span></span>

[<span data-ttu-id="b5c58-118">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="b5c58-118">Text functions</span></span>](er-functions-category-text.md)
