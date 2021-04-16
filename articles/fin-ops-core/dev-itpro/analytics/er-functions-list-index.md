---
title: INDEX, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji INDEX w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 14f10359a3f20fb9d23639babce764b9ef64243d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750467"
---
# <a name="index-er-function"></a><span data-ttu-id="201e3-103">INDEX, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="201e3-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="201e3-104">Funkcja `INDEX` zwraca wartość typu *Kontener (rekord)*, która jest wybierana przy użyciu określonego indeksu liczbowego na określonej liście.</span><span class="sxs-lookup"><span data-stu-id="201e3-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="201e3-105">Jeśli indeks jest poza zakresem dla rekordów na określonej liście, zostanie zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="201e3-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="201e3-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="201e3-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="201e3-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="201e3-107">Arguments</span></span>

<span data-ttu-id="201e3-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="201e3-108">`list`: *Record list*</span></span>

<span data-ttu-id="201e3-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="201e3-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="201e3-110">`index`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="201e3-110">`index`: *Integer*</span></span>

<span data-ttu-id="201e3-111">Indeks liczbowy, który wskazuje pozycję żądanego rekordu na określonej liście.</span><span class="sxs-lookup"><span data-stu-id="201e3-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="201e3-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="201e3-112">Return values</span></span>

<span data-ttu-id="201e3-113">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="201e3-113">*Container (record)*</span></span>

<span data-ttu-id="201e3-114">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="201e3-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="201e3-115">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="201e3-115">Example 1</span></span>

<span data-ttu-id="201e3-116">Po wprowadzeniu źródła danych **DS** typu *Pole obliczeniowe* zawierającego wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `DS.Value` zwraca listę z tylko jednym rekordem, który zawiera wartość tekstową **"B"** dla drugiego rekordu n liście rekordów.</span><span class="sxs-lookup"><span data-stu-id="201e3-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="201e3-117">Wyrażenie `INDEX (SPLIT ("A|B|C", "|"), 2).Value` również zwraca wartość tekstową **"B"**.</span><span class="sxs-lookup"><span data-stu-id="201e3-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="201e3-118">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="201e3-118">Example 2</span></span>

<span data-ttu-id="201e3-119">Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `INDEX (SPLIT ("A|B|C", "|"), 4).Value` zgłasza wyjątek w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="201e3-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="201e3-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="201e3-120">Additional resources</span></span>

[<span data-ttu-id="201e3-121">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="201e3-121">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]