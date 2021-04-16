---
title: TEXT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TEXT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 0694480f5d6892d13fe0c0d9ad191cdf2332dfec
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746106"
---
# <a name="text-er-function"></a><span data-ttu-id="45ee1-103">TEXT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="45ee1-103">TEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45ee1-104">Funkcja `TEXT` zwraca określoną liczbę jako wartość typu *Ciąg* po przekształceniu na ciąg tekstowy, który jest sformatowany zgodnie z ustawieniami regionalnymi serwera bieżącego wystąpienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="45ee1-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="45ee1-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="45ee1-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="45ee1-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="45ee1-106">Arguments</span></span>

<span data-ttu-id="45ee1-107">`number`: *Liczba całkowita* lub *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="45ee1-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="45ee1-108">Wartość numeryczna, która musi zostać przekonwertowana na ciąg tekstowy.</span><span class="sxs-lookup"><span data-stu-id="45ee1-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="45ee1-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="45ee1-109">Return values</span></span>

<span data-ttu-id="45ee1-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="45ee1-110">*String*</span></span>

<span data-ttu-id="45ee1-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="45ee1-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="45ee1-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="45ee1-112">Usage notes</span></span>

<span data-ttu-id="45ee1-113">Dla wartości typu *Liczba rzeczywista* konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="45ee1-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="45ee1-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="45ee1-114">Example</span></span>

<span data-ttu-id="45ee1-115">Jeśli ustawienia regionalne serwera wystąpienia aplikacji Microsoft Dynamics 365 Finance są określone jako **EN-US**, funkcja `TEXT (NOW ())` zwraca datę bieżącej sesji aplikacji, 17 grudnia 2015 roku, jako ciąg tekstowy **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="45ee1-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="45ee1-116">Funkcja `TEXT (1/3)` zwraca wartość **"0.33"**.</span><span class="sxs-lookup"><span data-stu-id="45ee1-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45ee1-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="45ee1-117">Additional resources</span></span>

[<span data-ttu-id="45ee1-118">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="45ee1-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]