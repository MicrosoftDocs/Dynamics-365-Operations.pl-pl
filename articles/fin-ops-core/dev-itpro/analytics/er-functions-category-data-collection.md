---
title: Lista funkcji modułu ER w kategorii kolekcji danych
description: Ten temat zawiera ogólne informacje o funkcjach kolekcji danych obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 0ec6092f2992df91433bb8aaa4212fca2a0abf7c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686300"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a><span data-ttu-id="0ad45-103">Lista funkcji modułu ER w kategorii kolekcji danych</span><span class="sxs-lookup"><span data-stu-id="0ad45-103">List of ER functions in the data collection category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ad45-104">Funkcje kolekcji danych w module Raportowanie elektroniczne (ER) służą do zliczania i sumowania w uruchamianym formacie ER na podstawie danych wyjściowych, które zostały już wygenerowane w formacie **Tekst** lub **XML**.</span><span class="sxs-lookup"><span data-stu-id="0ad45-104">Electronic reporting (ER) data collection functions are used to do counting and summing in an ER format that is being run, based on data of the output that has already been generated in **Text** or **Xml** format.</span></span> <span data-ttu-id="0ad45-105">To podejście umożliwia poprawę wydajności uruchamianego formatu ER w celu wprowadzenia wartości sum bieżących w wygenerowanych dokumentach i dla innych celów.</span><span class="sxs-lookup"><span data-stu-id="0ad45-105">This approach is used to help improve performance of an ER format that is run, to enter values of running totals in generated documents, and for other purposes.</span></span> <span data-ttu-id="0ad45-106">Ten temat zawiera podsumowanie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="0ad45-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="0ad45-107">Lista obsługiwanych funkcji</span><span class="sxs-lookup"><span data-stu-id="0ad45-107">List of supported functions</span></span>

| <span data-ttu-id="0ad45-108">Funkcja</span><span class="sxs-lookup"><span data-stu-id="0ad45-108">Function</span></span> | <span data-ttu-id="0ad45-109">Opis</span><span class="sxs-lookup"><span data-stu-id="0ad45-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="0ad45-110">CollectedList</span><span class="sxs-lookup"><span data-stu-id="0ad45-110">CollectedList</span></span>](er-functions-datacollection-collectedlist.md) | <span data-ttu-id="0ad45-111">Ta funkcja zwraca wartość typu *Lista rekordów*, która zawiera listę wartości zwróconych przez właściwość **Zebrane dane wartości klucza** elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="0ad45-111">This function returns a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="0ad45-112">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="0ad45-112">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="0ad45-113">CountIF</span><span class="sxs-lookup"><span data-stu-id="0ad45-113">CountIF</span></span>](er-functions-datacollection-countif.md) | <span data-ttu-id="0ad45-114">Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określony warunek.</span><span class="sxs-lookup"><span data-stu-id="0ad45-114">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="0ad45-115">Warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="0ad45-115">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="0ad45-116">CountIFs</span><span class="sxs-lookup"><span data-stu-id="0ad45-116">CountIFs</span></span>](er-functions-datacollection-countifs.md) | <span data-ttu-id="0ad45-117">Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="0ad45-117">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="0ad45-118">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="0ad45-118">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="0ad45-119">FormatElementName</span><span class="sxs-lookup"><span data-stu-id="0ad45-119">FormatElementName</span></span>](er-functions-datacollection-formatelementname.md) | <span data-ttu-id="0ad45-120">Ta funkcja zwraca wartość typu *Ciąg* reprezentującą nazwę bieżącego elementu formatu ER.</span><span class="sxs-lookup"><span data-stu-id="0ad45-120">This function returns a *String* value that represents the name of the current ER format's element.</span></span> |
| [<span data-ttu-id="0ad45-121">SumIF</span><span class="sxs-lookup"><span data-stu-id="0ad45-121">SumIF</span></span>](er-functions-datacollection-sumif.md) | <span data-ttu-id="0ad45-122">Ta funkcja zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określony warunek.</span><span class="sxs-lookup"><span data-stu-id="0ad45-122">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="0ad45-123">Warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="0ad45-123">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="0ad45-124">SumIFs</span><span class="sxs-lookup"><span data-stu-id="0ad45-124">SumIFs</span></span>](er-functions-datacollection-sumifs.md) | <span data-ttu-id="0ad45-125">Ta funkcja zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="0ad45-125">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="0ad45-126">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="0ad45-126">Each condition consists of a key range and a key value.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="0ad45-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0ad45-127">Additional resources</span></span>

[<span data-ttu-id="0ad45-128">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="0ad45-128">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="0ad45-129">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="0ad45-129">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="0ad45-130">Język formuł raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="0ad45-130">Electronic reporting formula language</span></span>](er-formula-language.md)
