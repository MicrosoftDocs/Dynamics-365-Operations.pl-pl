---
title: ALLITEMS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ALLITEMS w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 5ddcf989bdfd1d1f5d0a412a2ffefe0e3037ca79
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746730"
---
# <a name="allitems-er-function"></a><span data-ttu-id="0dcf6-103">ALLITEMS, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="0dcf6-103">ALLITEMS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0dcf6-104">Funkcja `ALLITEMS` jest uruchamiana jako wybór w pamięci i zwraca nową spłaszczoną wartość *Lista rekordów* jako listę rekordów, który reprezentuje wszystkie elementy, które odpowiadają określonej ścieżce.</span><span class="sxs-lookup"><span data-stu-id="0dcf6-104">The `ALLITEMS` function runs as an in-memory selection and returns a new flattened *Record list* value as a list of records that represents all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="0dcf6-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0dcf6-105">Syntax</span></span>

```vb
ALLITEMS (path)
```

## <a name="arguments"></a><span data-ttu-id="0dcf6-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="0dcf6-106">Arguments</span></span>

<span data-ttu-id="0dcf6-107">`path`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="0dcf6-107">`path`: *Record list*</span></span>

<span data-ttu-id="0dcf6-108">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="0dcf6-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="0dcf6-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="0dcf6-109">Return values</span></span>

<span data-ttu-id="0dcf6-110">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="0dcf6-110">*Record list*</span></span>

<span data-ttu-id="0dcf6-111">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="0dcf6-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0dcf6-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="0dcf6-112">Usage notes</span></span>

<span data-ttu-id="0dcf6-113">Ścieżka musi być zdefiniowana jako prawidłowa ścieżka źródła danych do elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="0dcf6-113">The path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="0dcf6-114">Elementy danych, takie jak ciąg i data ścieżki, powinny powodować zgłaszanie błędu w konstruktorze wyrażeń modułu Raportowanie elektroniczne (ER) w czasie projektowania.</span><span class="sxs-lookup"><span data-stu-id="0dcf6-114">Data elements such as the path string and date should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="0dcf6-115">Nie zaleca się używania tej funkcji dla źródeł danych transakcyjnych, które mogą zawierać dużą ilość danych.</span><span class="sxs-lookup"><span data-stu-id="0dcf6-115">We don't recommend that you use this function for transactional data sources that might contain a large volume of data.</span></span> <span data-ttu-id="0dcf6-116">Zamiast tego należy rozważyć użycie funkcji [ALLTEMSQUERY](er-functions-list-allitemsquery.md).</span><span class="sxs-lookup"><span data-stu-id="0dcf6-116">Instead, consider using the [ALLTEMSQUERY](er-functions-list-allitemsquery.md) function.</span></span>

## <a name="example-1"></a><span data-ttu-id="0dcf6-117">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="0dcf6-117">Example 1</span></span>

<span data-ttu-id="0dcf6-118">Jeśli wprowadzisz `SPLIT("abcdef" , 2)` jako źródło danych **DS**, wyrażenie `COUNT( ALLITEMS (DS))` zwraca wartość **3**.</span><span class="sxs-lookup"><span data-stu-id="0dcf6-118">If you enter `SPLIT("abcdef" , 2)` as data source **DS**, the expression `COUNT( ALLITEMS (DS))` returns **3**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0dcf6-119">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="0dcf6-119">Example 2</span></span>

<span data-ttu-id="0dcf6-120">Jeśli wprowadzisz **Vend** jako źródło danych z typem danych *Lista rekordów*, które odwołuje się do tabeli aplikacji VendTable, wyrażenie `ALLITEMS (Vend.'<Relations'.ContactPerson)` zwraca spłaszczoną listę rekordów, które ma strukturę tabeli **ContactPerson** i zawiera wszystkie osoby kontaktowe dostępne za pośrednictwem relacji **ContactPerson.ContactForParty == VendTable.Party**. Lista ta jest dostępna dla wszystkich dostawców z poziomu przywołanej tablicy dostawców.</span><span class="sxs-lookup"><span data-stu-id="0dcf6-120">If you enter **Vend** as the data source of the *Record list* data type that refers to the VendTable application table, the expression `ALLITEMS (Vend.'<Relations'.ContactPerson)` returns a flattened list of records that has the **ContactPerson** table structure and contains all contact persons that can be accessed by using the **ContactPerson.ContactForParty == VendTable.Party** relation, and that is available for all vendors from the referenced vendor table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0dcf6-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0dcf6-121">Additional resources</span></span>

[<span data-ttu-id="0dcf6-122">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="0dcf6-122">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]