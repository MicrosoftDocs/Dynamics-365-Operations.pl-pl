---
title: LIST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LIST w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 50cb8858301c030df07ad4af9fe2a9513f41fead
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750419"
---
# <a name="list-er-function"></a><span data-ttu-id="8baee-103">LIST, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="8baee-103">LIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8baee-104">Funkcja `LIST` zwraca wartość typu *Lista rekordów*, która składa się z nowej listy rekordów utworzonej na podstawie określonych argumentów.</span><span class="sxs-lookup"><span data-stu-id="8baee-104">The `LIST` function returns a *Record list* value that consists of a new list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="8baee-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="8baee-105">Syntax</span></span>

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a><span data-ttu-id="8baee-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="8baee-106">Arguments</span></span>

<span data-ttu-id="8baee-107">`record 1`: *Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="8baee-107">`record 1`: *Container (record)*</span></span>

<span data-ttu-id="8baee-108">Odwołanie do źródła danych o typie danych *Rekord*.</span><span class="sxs-lookup"><span data-stu-id="8baee-108">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="8baee-109">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="8baee-109">This argument is required.</span></span>

<span data-ttu-id="8baee-110">`record N`: *Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="8baee-110">`record N`: *Container (record)*</span></span>

<span data-ttu-id="8baee-111">Odwołanie do źródła danych o typie danych *Rekord*.</span><span class="sxs-lookup"><span data-stu-id="8baee-111">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="8baee-112">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="8baee-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="8baee-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="8baee-113">Return values</span></span>

<span data-ttu-id="8baee-114">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="8baee-114">*Record list*</span></span>

<span data-ttu-id="8baee-115">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="8baee-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8baee-116">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="8baee-116">Usage notes</span></span>

<span data-ttu-id="8baee-117">Tworzona struktura listy zawiera tylko pola, które są prezentowane w strukturze każdego rekordu, wymienionego w argumentach.</span><span class="sxs-lookup"><span data-stu-id="8baee-117">The structure of the list that is created contains only the fields that are presented in the structure of every record that is mentioned in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="8baee-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="8baee-118">Example</span></span>

<span data-ttu-id="8baee-119">Wprowadź źródło danych **Rekord 1** typu *Kontener*.</span><span class="sxs-lookup"><span data-stu-id="8baee-119">You enter data source **Record 1** of the *Container* type.</span></span> <span data-ttu-id="8baee-120">To źródło danych zawiera następujące pola zagnieżdżone typu *Pole obliczeniowe*:</span><span class="sxs-lookup"><span data-stu-id="8baee-120">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="8baee-121">**Code:** to pole zawiera wyrażenie, które zwraca wartość typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="8baee-121">**Code:** This field contains an expression that returns a value of the *String* type.</span></span>
- <span data-ttu-id="8baee-122">**Amount:** to pole zawiera wyrażenie, które zwraca wartość typu *Liczba rzeczywista*.</span><span class="sxs-lookup"><span data-stu-id="8baee-122">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>

<span data-ttu-id="8baee-123">Następnie wprowadź źródło danych **Rekord 2** typu *Kontener*.</span><span class="sxs-lookup"><span data-stu-id="8baee-123">You then enter data source **Record 2** of the *Container* type.</span></span> <span data-ttu-id="8baee-124">To źródło danych zawiera następujące pola zagnieżdżone typu *Pole obliczeniowe*:</span><span class="sxs-lookup"><span data-stu-id="8baee-124">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="8baee-125">**Amount:** to pole zawiera wyrażenie, które zwraca wartość typu *Liczba rzeczywista*.</span><span class="sxs-lookup"><span data-stu-id="8baee-125">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>
- <span data-ttu-id="8baee-126">**IsValid:** to pole zawiera wyrażenie, które zwraca wartość *logiczną*.</span><span class="sxs-lookup"><span data-stu-id="8baee-126">**IsValid:** This field contains an expression that returns a value of the *Boolean* type.</span></span>

<span data-ttu-id="8baee-127">W takim przypadku wyrażenie `LIST('Record 1', 'Record 2')` zwraca nową listę zawierającą dwa rekordy.</span><span class="sxs-lookup"><span data-stu-id="8baee-127">In this case, the expression `LIST('Record 1', 'Record 2')` returns a new list that contains two records.</span></span> <span data-ttu-id="8baee-128">Struktura tej listy składa się z pojedynczego pola **Ilość** typu *Liczba rzeczywista*, ponieważ jest ono jedynym polem, które jest prezentowane w każdym argumencie wywołanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="8baee-128">The structure of this list consists of a single **Amount** field of the *Real* type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8baee-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8baee-129">Additional resources</span></span>

[<span data-ttu-id="8baee-130">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="8baee-130">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]