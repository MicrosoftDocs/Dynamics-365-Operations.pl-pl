---
title: SPLITLISTBYLIMIT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SPLITLISTBYLIMIT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 119ad3c363913ddaf3d6b890e36989d03e91b3c0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565111"
---
# <a name="splitlistbylimit-er-function"></a><span data-ttu-id="cbb49-103">SPLITLISTBYLIMIT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="cbb49-103">SPLITLISTBYLIMIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbb49-104">Funkcja `SPLITLISTBYLIMIT` dzieli określoną listę na nową listę list podrzędnych (partii).</span><span class="sxs-lookup"><span data-stu-id="cbb49-104">The `SPLITLISTBYLIMIT` function splits the specified list into a new list of sublists (batches).</span></span> <span data-ttu-id="cbb49-105">Liczba rekordów w każdej partii jest obliczana dynamicznie.</span><span class="sxs-lookup"><span data-stu-id="cbb49-105">The number of records in each batch is dynamically calculated.</span></span> <span data-ttu-id="cbb49-106">Funkcja zwraca wynik jako nową wartość typu *Lista rekordów*, która składa się z partii.</span><span class="sxs-lookup"><span data-stu-id="cbb49-106">The function then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbb49-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="cbb49-107">Syntax</span></span>

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a><span data-ttu-id="cbb49-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="cbb49-108">Arguments</span></span>

<span data-ttu-id="cbb49-109">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="cbb49-109">`list`: *Record list*</span></span>

<span data-ttu-id="cbb49-110">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="cbb49-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="cbb49-111">`limit value`: *Liczba całkowita* lub *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="cbb49-111">`limit value`: *Integer* or *Real*</span></span>

<span data-ttu-id="cbb49-112">Maksymalna wartość limitu, który jest używany do dzielenia oryginalnej listy na partie.</span><span class="sxs-lookup"><span data-stu-id="cbb49-112">The maximum value of the limit that is used to split the original list into batches.</span></span>

<span data-ttu-id="cbb49-113">`limit source`: *Pole*</span><span class="sxs-lookup"><span data-stu-id="cbb49-113">`limit source`: *Field*</span></span>

<span data-ttu-id="cbb49-114">Prawidłowa ścieżka pola typu *Liczba całkowita* lub *Liczba rzeczywista* na określonej liście.</span><span class="sxs-lookup"><span data-stu-id="cbb49-114">The valid path of a field of the *Integer* or *Real* type in the specified list.</span></span> <span data-ttu-id="cbb49-115">Wartość tego pola określa krok, w którym całkowita suma jest zwiększana.</span><span class="sxs-lookup"><span data-stu-id="cbb49-115">The value of this field defines the step that the total sum is increased on.</span></span>

## <a name="return-values"></a><span data-ttu-id="cbb49-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="cbb49-116">Return values</span></span>

<span data-ttu-id="cbb49-117">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="cbb49-117">*Record list*</span></span>

<span data-ttu-id="cbb49-118">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="cbb49-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cbb49-119">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="cbb49-119">Usage notes</span></span>

<span data-ttu-id="cbb49-120">Zwracana jest lista partii zawierająca następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="cbb49-120">The list of batches that is returned contains the following elements:</span></span>

- <span data-ttu-id="cbb49-121">**Value**: *Lista*</span><span class="sxs-lookup"><span data-stu-id="cbb49-121">**Value**: *List*</span></span>

    <span data-ttu-id="cbb49-122">Lista rekordów należących do bieżącej partii.</span><span class="sxs-lookup"><span data-stu-id="cbb49-122">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="cbb49-123">**BatchNumber**: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="cbb49-123">**BatchNumber**: *Integer*</span></span>

    <span data-ttu-id="cbb49-124">Numer bieżącej partii na zwróconej liście.</span><span class="sxs-lookup"><span data-stu-id="cbb49-124">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="cbb49-125">Limit nie jest stosowany do pojedynczego elementu oryginalnej listy, jeżeli źródło limitu przekracza zdefiniowany limit.</span><span class="sxs-lookup"><span data-stu-id="cbb49-125">The limit isn't applied to a single item of the original list if the limit source exceeds the defined limit.</span></span>

## <a name="example"></a><span data-ttu-id="cbb49-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="cbb49-126">Example</span></span>

<span data-ttu-id="cbb49-127">Na poniższej ilustracji przedstawiono format raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="cbb49-127">The following illustration shows an Electronic reporting (ER) format.</span></span>

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

<span data-ttu-id="cbb49-128">Na poniższej ilustracji pokazano źródła danych używane dla formatu.</span><span class="sxs-lookup"><span data-stu-id="cbb49-128">The following illustration shows the data sources that are used for the format.</span></span>

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

<span data-ttu-id="cbb49-129">Na ilustracji poniżej widać wynik uruchomienia formatu.</span><span class="sxs-lookup"><span data-stu-id="cbb49-129">The following illustration shows the result when the format is run.</span></span> <span data-ttu-id="cbb49-130">W tym przypadku danymi wyjściowymi jest niezhierarchizowana lista towarów asortymentowych.</span><span class="sxs-lookup"><span data-stu-id="cbb49-130">In this case, the output is a flat list of commodity items.</span></span>

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

<span data-ttu-id="cbb49-131">Na poniższej ilustracji ten sam format został skorygowany w taki sposób, aby pokazywał listę towarów asortymentowych w partiach, jeśli jedna partia musi zawierać towary o łącznej wadze nieprzekraczającej limitu 9.</span><span class="sxs-lookup"><span data-stu-id="cbb49-131">In the following illustrations, the same format has been adjusted so that it presents the list of commodity items in batches if a single batch must include commodities and the total weight should not exceed a limit of 9.</span></span>

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

<span data-ttu-id="cbb49-132">Na ilustracji poniżej widać wynik uruchomienia zmodyfikowanego formatu.</span><span class="sxs-lookup"><span data-stu-id="cbb49-132">The following illustration shows the result when the adjusted format is run.</span></span>

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> <span data-ttu-id="cbb49-133">Limit nie obowiązuje do ostatniej pozycji oryginalnej listy, ponieważ wartość (**11**) jej źródła limitu (**waga**) przekracza zdefiniowany limit (**9**).</span><span class="sxs-lookup"><span data-stu-id="cbb49-133">The limit isn't applied to the last item of the original list, because the value (**11**) of the limit source (**weight**) exceeds the defined limit (**9**).</span></span> <span data-ttu-id="cbb49-134">Aby zignorować listy podrzędne podczas generowania raportu, w razie potrzeby użyj funkcji `WHERE` albo wyrażenia **Enabled** odpowiedniego elementu formatu.</span><span class="sxs-lookup"><span data-stu-id="cbb49-134">To ignore sublists during report generation, use either the `WHERE` function or the **Enabled** expression of the corresponding format element, as you require.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cbb49-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cbb49-135">Additional resources</span></span>

[<span data-ttu-id="cbb49-136">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="cbb49-136">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]