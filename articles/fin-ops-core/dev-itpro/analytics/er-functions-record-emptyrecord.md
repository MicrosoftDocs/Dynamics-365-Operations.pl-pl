---
title: EMPTYRECORD, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji EMPTYRECORD w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: e614c06b4cfad628bbd8a966719ed994ce05b792
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746538"
---
# <a name="emptyrecord-er-function"></a><span data-ttu-id="e1a30-103">EMPTYRECORD, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="e1a30-103">EMPTYRECORD ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1a30-104">Funkcja `EMPTYRECORD` zwraca pustą wartość *Kontener (rekord)*, która ma tę samą strukturę, co wybrana lista rekordów lub rekord.</span><span class="sxs-lookup"><span data-stu-id="e1a30-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="e1a30-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="e1a30-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="e1a30-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="e1a30-106">Arguments</span></span>

<span data-ttu-id="e1a30-107">`list`: *Lista rekordów* lub *Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="e1a30-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="e1a30-108">Prawidłowa ścieżka elementu źródła danych typu *Lista rekordów* lub *Kontener (rekord)*.</span><span class="sxs-lookup"><span data-stu-id="e1a30-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="e1a30-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="e1a30-109">Return values</span></span>

<span data-ttu-id="e1a30-110">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="e1a30-110">*Container (record)*</span></span>

<span data-ttu-id="e1a30-111">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="e1a30-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e1a30-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="e1a30-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="e1a30-113">Rekord null jest rekordem, w którym wszystkie pola mają wartość pustą.</span><span class="sxs-lookup"><span data-stu-id="e1a30-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="e1a30-114">Wartość pusta to **0** (zero) w przypadku liczb, pusty ciąg w przypadku ciągów tekstowych, itd.</span><span class="sxs-lookup"><span data-stu-id="e1a30-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="e1a30-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="e1a30-115">Example</span></span>

<span data-ttu-id="e1a30-116">Funkcja `EMPTYRECORD (SPLIT ("abc", 1))` zwraca nowy pusty rekord, która ma taką samą strukturę jak lista zwracana przez używaną funkcję `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="e1a30-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="e1a30-117">Aby uzyskać więcej informacji, zobacz [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="e1a30-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e1a30-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e1a30-118">Additional resources</span></span>

[<span data-ttu-id="e1a30-119">Funkcje zapisu</span><span class="sxs-lookup"><span data-stu-id="e1a30-119">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]