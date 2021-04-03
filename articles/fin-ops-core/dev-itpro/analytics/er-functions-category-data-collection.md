---
title: Lista funkcji modułu ER w kategorii kolekcji danych
description: Ten temat zawiera ogólne informacje o funkcjach kolekcji danych obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: ba3a1f031a4a98592081b04a4128450aeb8218ef
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561741"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a><span data-ttu-id="88489-103">Lista funkcji modułu ER w kategorii kolekcji danych</span><span class="sxs-lookup"><span data-stu-id="88489-103">List of ER functions in the data collection category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88489-104">Funkcje kolekcji danych w module Raportowanie elektroniczne (ER) służą do zliczania i sumowania w uruchamianym formacie ER na podstawie danych wyjściowych, które zostały już wygenerowane w formacie **Tekst** lub **XML**.</span><span class="sxs-lookup"><span data-stu-id="88489-104">Electronic reporting (ER) data collection functions are used to do counting and summing in an ER format that is being run, based on data of the output that has already been generated in **Text** or **Xml** format.</span></span> <span data-ttu-id="88489-105">To podejście umożliwia poprawę wydajności uruchamianego formatu ER w celu wprowadzenia wartości sum bieżących w wygenerowanych dokumentach i dla innych celów.</span><span class="sxs-lookup"><span data-stu-id="88489-105">This approach is used to help improve performance of an ER format that is run, to enter values of running totals in generated documents, and for other purposes.</span></span> <span data-ttu-id="88489-106">Ten temat zawiera podsumowanie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="88489-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="88489-107">Lista obsługiwanych funkcji</span><span class="sxs-lookup"><span data-stu-id="88489-107">List of supported functions</span></span>

| <span data-ttu-id="88489-108">Funkcja</span><span class="sxs-lookup"><span data-stu-id="88489-108">Function</span></span> | <span data-ttu-id="88489-109">Opis</span><span class="sxs-lookup"><span data-stu-id="88489-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="88489-110">CollectedList</span><span class="sxs-lookup"><span data-stu-id="88489-110">CollectedList</span></span>](er-functions-datacollection-collectedlist.md) | <span data-ttu-id="88489-111">Ta funkcja zwraca wartość typu *Lista rekordów*, która zawiera listę wartości zwróconych przez właściwość **Zebrane dane wartości klucza** elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="88489-111">This function returns a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="88489-112">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="88489-112">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="88489-113">CountIF</span><span class="sxs-lookup"><span data-stu-id="88489-113">CountIF</span></span>](er-functions-datacollection-countif.md) | <span data-ttu-id="88489-114">Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określony warunek.</span><span class="sxs-lookup"><span data-stu-id="88489-114">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="88489-115">Warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="88489-115">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="88489-116">CountIFs</span><span class="sxs-lookup"><span data-stu-id="88489-116">CountIFs</span></span>](er-functions-datacollection-countifs.md) | <span data-ttu-id="88489-117">Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="88489-117">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="88489-118">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="88489-118">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="88489-119">FormatElementName</span><span class="sxs-lookup"><span data-stu-id="88489-119">FormatElementName</span></span>](er-functions-datacollection-formatelementname.md) | <span data-ttu-id="88489-120">Ta funkcja zwraca wartość typu *Ciąg* reprezentującą nazwę bieżącego elementu formatu ER.</span><span class="sxs-lookup"><span data-stu-id="88489-120">This function returns a *String* value that represents the name of the current ER format's element.</span></span> |
| [<span data-ttu-id="88489-121">SumIF</span><span class="sxs-lookup"><span data-stu-id="88489-121">SumIF</span></span>](er-functions-datacollection-sumif.md) | <span data-ttu-id="88489-122">Ta funkcja zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określony warunek.</span><span class="sxs-lookup"><span data-stu-id="88489-122">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="88489-123">Warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="88489-123">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="88489-124">SumIFs</span><span class="sxs-lookup"><span data-stu-id="88489-124">SumIFs</span></span>](er-functions-datacollection-sumifs.md) | <span data-ttu-id="88489-125">Ta funkcja zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="88489-125">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="88489-126">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="88489-126">Each condition consists of a key range and a key value.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="88489-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="88489-127">Additional resources</span></span>

[<span data-ttu-id="88489-128">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="88489-128">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="88489-129">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="88489-129">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="88489-130">Język formuł raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="88489-130">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]