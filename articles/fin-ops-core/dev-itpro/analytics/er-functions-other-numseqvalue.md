---
title: NUMSEQVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMSEQVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: b513d04bfeb3a37aa0b1703d0fdde040885a5159
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680597"
---
# <a name="numseqvalue-er-function"></a><span data-ttu-id="b627a-103">NUMSEQVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="b627a-103">NUMSEQVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b627a-104">Funkcja `NUMSEQVALUE` zwraca wartość typu *Ciąg*, która reprezentuje nową wygenerowaną wartość sekwencji numerów na podstawie określonej sekwencji numerów, zakres i identyfikatora zakresu.</span><span class="sxs-lookup"><span data-stu-id="b627a-104">The `NUMSEQVALUE` function returns a *String* value that represents the new generated value of a number sequence, based on the specified number sequence, scope, and scope ID.</span></span> <span data-ttu-id="b627a-105">Identyfikator zakresu jest równy kodowi firmy podawanemu przez kontekst, w którym jest uruchamiany format modułu Raportowanie elektroniczne (ER).</span><span class="sxs-lookup"><span data-stu-id="b627a-105">The scope ID equals the company code that is supplied by the context that the Electronic reporting (ER) format is run under.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="b627a-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="b627a-106">Syntax 1</span></span>

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a><span data-ttu-id="b627a-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="b627a-107">Syntax 2</span></span>

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a><span data-ttu-id="b627a-108">Składnia 3</span><span class="sxs-lookup"><span data-stu-id="b627a-108">Syntax 3</span></span>

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a><span data-ttu-id="b627a-109">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b627a-109">Arguments</span></span>

<span data-ttu-id="b627a-110">`number sequence code`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b627a-110">`number sequence code`: *String*</span></span>

<span data-ttu-id="b627a-111">Wartość tekstowa reprezentująca kod sekwencji numerów, w którym jest wymagana nowa wartość.</span><span class="sxs-lookup"><span data-stu-id="b627a-111">A text value that represents the code of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="b627a-112">`number sequence record ID`: *Int64*</span><span class="sxs-lookup"><span data-stu-id="b627a-112">`number sequence record ID`: *Int64*</span></span>

<span data-ttu-id="b627a-113">Wartość *Int64* reprezentująca identyfikator rekordu w tabeli NumberSequenceTable zawierającej definicję sekwencji numerów, w której jest wymagana nowa wartość.</span><span class="sxs-lookup"><span data-stu-id="b627a-113">An *Int64* value that represents the record ID of a record in the NumberSequenceTable table that contains the definition of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="b627a-114">`scope type`: *Wartość wyliczenia*</span><span class="sxs-lookup"><span data-stu-id="b627a-114">`scope type`: *Enum value*</span></span>

<span data-ttu-id="b627a-115">Wartość wyliczenia **ERExpressionNumberSequenceScopeType**, która definiuje zakres sekwencji numerów, w której jest wymagana nowa wartość.</span><span class="sxs-lookup"><span data-stu-id="b627a-115">An enumeration value of the **ERExpressionNumberSequenceScopeType** enumeration that defines the scope of the number sequence that a new value is required in.</span></span> <span data-ttu-id="b627a-116">Dostępne typy zakresów to **Udostępnione**, **Podmiot prawny** i **Firma**.</span><span class="sxs-lookup"><span data-stu-id="b627a-116">The available scope types are **Shared**, **Legal entity**, and **Company**.</span></span>

<span data-ttu-id="b627a-117">`scope ID`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b627a-117">`scope ID`: *String*</span></span>

<span data-ttu-id="b627a-118">Wartość typu *Ciąg*, która identyfikuje zakres na podstawie określonego typu zakresu.</span><span class="sxs-lookup"><span data-stu-id="b627a-118">A *String* value that identifies the scope, based on the specified scope type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b627a-119">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="b627a-119">Return values</span></span>

<span data-ttu-id="b627a-120">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b627a-120">*String*</span></span>

<span data-ttu-id="b627a-121">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="b627a-121">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b627a-122">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="b627a-122">Usage notes</span></span>

<span data-ttu-id="b627a-123">Dla typu zakresu **Udostępnione** należy określić pusty ciąg jako identyfikator zakresu.</span><span class="sxs-lookup"><span data-stu-id="b627a-123">For the **Shared** scope type, specify an empty string as the scope ID.</span></span>

<span data-ttu-id="b627a-124">Dla typów zakresów **Firma** i **Podmiot prawny** należy podać kod firmy jako identyfikatora zakresu.</span><span class="sxs-lookup"><span data-stu-id="b627a-124">For the **Company** and **Legal entity** scope types, specify the company code as the scope ID.</span></span> <span data-ttu-id="b627a-125">Jeśli pusty ciąg jako identyfikator zakresu dla tych typów zakresów, zostanie użyty bieżący kod firmy.</span><span class="sxs-lookup"><span data-stu-id="b627a-125">If you specify an empty string as the scope ID for these scope types, the current company code is used.</span></span>

<span data-ttu-id="b627a-126">Gdy używana jest składnia 1, jest wymagana sekwencja numerów dla typu zakresu **Firma**, a kod firmy jest dostarczany przez kontekst, w którym jest uruchomiony format ER.</span><span class="sxs-lookup"><span data-stu-id="b627a-126">When syntax 1 is used, the number sequence is requested for the **Company** scope type, and the company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-1"></a><span data-ttu-id="b627a-127">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="b627a-127">Example 1</span></span>

<span data-ttu-id="b627a-128">W formacie ER definiujesz źródło danych **AskNumSeq** typu *Parametr wejściowy użytkownika*.</span><span class="sxs-lookup"><span data-stu-id="b627a-128">In your ER format, you define the **AskNumSeq** data source of the *User input parameter* type.</span></span> <span data-ttu-id="b627a-129">To źródło danych odwołuje się do rozszerzonego typu danych (EDT) **Opis**.</span><span class="sxs-lookup"><span data-stu-id="b627a-129">This data source refers to the **Description** extended data type (EDT).</span></span> <span data-ttu-id="b627a-130">Następnie definiujesz źródło danych **NumSeq** typu *Pole obliczeniowe*.</span><span class="sxs-lookup"><span data-stu-id="b627a-130">Next, you define the **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="b627a-131">To źródło danych zawiera wyrażenie `NUMSEQVALUE (AskNumSeq)`.</span><span class="sxs-lookup"><span data-stu-id="b627a-131">This data source contains the expression `NUMSEQVALUE (AskNumSeq)`.</span></span> <span data-ttu-id="b627a-132">Gdy następuje wywołanie źródła danych **NumSeq**, jest zwracana nowa wygenerowana wartość sekwencji numerów, która została określona w czasie wykonywania przez wprowadzenie kodu w oknie dialogowym.</span><span class="sxs-lookup"><span data-stu-id="b627a-132">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that was specified at runtime by entering its code in the dialog box.</span></span> <span data-ttu-id="b627a-133">Sekwencja numerów jest wymagana dla typu zakresu **Firma**.</span><span class="sxs-lookup"><span data-stu-id="b627a-133">The number sequence is requested for the **Company** scope type.</span></span> <span data-ttu-id="b627a-134">Kod firmy jest dostarczany przez kontekst, w którym jest uruchamiany format ER.</span><span class="sxs-lookup"><span data-stu-id="b627a-134">The company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-2"></a><span data-ttu-id="b627a-135">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="b627a-135">Example 2</span></span>

<span data-ttu-id="b627a-136">W mapowaniu modelu są definiowane następujące źródła danych:</span><span class="sxs-lookup"><span data-stu-id="b627a-136">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="b627a-137">Źródło danych **LedgerParms** typu *Tabela*.</span><span class="sxs-lookup"><span data-stu-id="b627a-137">The **LedgerParms** data source of the *Table* type.</span></span> <span data-ttu-id="b627a-138">To źródło danych odnosi się do tabeli LedgerParameters.</span><span class="sxs-lookup"><span data-stu-id="b627a-138">This data source refers to the LedgerParameters table.</span></span>
- <span data-ttu-id="b627a-139">Źródło danych **NumSeq** typu *Pole obliczeniowe*.</span><span class="sxs-lookup"><span data-stu-id="b627a-139">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="b627a-140">To źródło danych zawiera wyrażenie `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span><span class="sxs-lookup"><span data-stu-id="b627a-140">This data source contains the expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span></span>

<span data-ttu-id="b627a-141">Gdy zostanie wywołane źródło danych **NumSeq**, zwróci nowo wygenerowaną wartość numeracji skonfigurowanej w oknie Parametry księgi głównej dla firmy dostarczającej kontekst, w którym jest wykonywany format raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="b627a-141">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that has been configured in the General ledger parameters for the company that supplies the context that the ER format is run under.</span></span> <span data-ttu-id="b627a-142">Ta numeracja jednoznacznie identyfikuje arkusze i dostarcza numer partii, który łączy transakcje ze sobą.</span><span class="sxs-lookup"><span data-stu-id="b627a-142">This number sequence uniquely identifies journals and acts as a batch number that links the transactions together.</span></span>

## <a name="example-3"></a><span data-ttu-id="b627a-143">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="b627a-143">Example 3</span></span>

<span data-ttu-id="b627a-144">W mapowaniu modelu są definiowane następujące źródła danych:</span><span class="sxs-lookup"><span data-stu-id="b627a-144">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="b627a-145">Źródło danych **enumScope** w aplikacji Microsoft Dynamics 365 Finance typu *wyliczenie*.</span><span class="sxs-lookup"><span data-stu-id="b627a-145">The **enumScope** data source of the Microsoft Dynamics 365 Finance *enumeration* type.</span></span> <span data-ttu-id="b627a-146">To źródło danych odwołuje się do wyliczenia **ERExpressionNumberSequenceScopeType**.</span><span class="sxs-lookup"><span data-stu-id="b627a-146">This data source refers to the **ERExpressionNumberSequenceScopeType** enumeration.</span></span>
- <span data-ttu-id="b627a-147">Źródło danych **NumSeq** typu *Pole obliczeniowe*.</span><span class="sxs-lookup"><span data-stu-id="b627a-147">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="b627a-148">To źródło danych zawiera wyrażenie `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span><span class="sxs-lookup"><span data-stu-id="b627a-148">This data source contains the expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span></span>

<span data-ttu-id="b627a-149">Gdy zostanie wywołane źródło danych **NumSeq**, zwróci nowo wygenerowaną wartość numeracji **Gene\_1** skonfigurowanej dla firmy dostarczającej kontekst, w którym jest wykonywany format raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="b627a-149">When the **NumSeq** data source is called, it returns the new generated value of the **Gene\_1** number sequence that has been configured for the company that supplies the context that the ER format is run under.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b627a-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b627a-150">Additional resources</span></span>

[<span data-ttu-id="b627a-151">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="b627a-151">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
