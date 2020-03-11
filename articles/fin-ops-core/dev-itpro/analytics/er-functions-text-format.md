---
title: FORMAT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FORMAT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 7ae688ef6b24f8d90c0354c8c6449adba1588bfa
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041085"
---
# <span data-ttu-id="14b2f-103"><a name="FORMAT">FORMAT, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="14b2f-103"><a name="FORMAT">FORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="14b2f-104">Funkcja `FORMAT` zwraca określoną wartość typu *Ciąg* po jej sformatowaniu przez zastąpienie wszystkich wystąpień elementu **%N** *N*-tym argumentem.</span><span class="sxs-lookup"><span data-stu-id="14b2f-104">The `FORMAT` function returns the specified string as a *String* value after it has been formatted by substituting any occurrences of **%N** with the *N*th argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="14b2f-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="14b2f-105">Syntax</span></span>

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a><span data-ttu-id="14b2f-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="14b2f-106">Arguments</span></span>

<span data-ttu-id="14b2f-107">`string`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="14b2f-107">`string`: *String*</span></span>

<span data-ttu-id="14b2f-108">Odwołanie do źródła danych typu *Ciąg*, które musi zostać sformatowany.</span><span class="sxs-lookup"><span data-stu-id="14b2f-108">A reference to a data source of the *String* type that must be formatted.</span></span> <span data-ttu-id="14b2f-109">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="14b2f-109">This argument is required.</span></span>

<span data-ttu-id="14b2f-110">`argument 1`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="14b2f-110">`argument 1`: *String*</span></span>

<span data-ttu-id="14b2f-111">Pierwszy argument, który jest używany do zastępowania wystąpień **%1**.</span><span class="sxs-lookup"><span data-stu-id="14b2f-111">The first argument, which is used to replace occurrences of **%1**.</span></span> <span data-ttu-id="14b2f-112">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="14b2f-112">This argument is required.</span></span>

<span data-ttu-id="14b2f-113">`argument N`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="14b2f-113">`argument N`: *String*</span></span>

<span data-ttu-id="14b2f-114">*N*-ty argument, który jest używany do zastępowania wystąpień **%2**, **%3** itd.</span><span class="sxs-lookup"><span data-stu-id="14b2f-114">The *N*th argument, which is used to replace occurrences of **%2**, **%3**, and so on.</span></span> <span data-ttu-id="14b2f-115">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="14b2f-115">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="14b2f-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="14b2f-116">Return values</span></span>

<span data-ttu-id="14b2f-117">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="14b2f-117">*String*</span></span>

<span data-ttu-id="14b2f-118">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="14b2f-118">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="14b2f-119">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="14b2f-119">Usage notes</span></span>

<span data-ttu-id="14b2f-120">Jeśli dla parametru nie podano argumentu, parametr jest zwracany w ciągu jako **"%N"**.</span><span class="sxs-lookup"><span data-stu-id="14b2f-120">If an argument isn't provided for a parameter, the parameter is returned as **"%N"** in the string.</span></span> <span data-ttu-id="14b2f-121">Dla wartości typu *Rzeczywista* domyślna konwersja ciągu jest ograniczona do dwóch miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="14b2f-121">For values of the *Real* type, the default string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="14b2f-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="14b2f-122">Example</span></span>

<span data-ttu-id="14b2f-123">Na poniższej ilustracji źródło danych **PaymentModel** zwraca listę rekordów klientów przy użyciu składnika **Klient**.</span><span class="sxs-lookup"><span data-stu-id="14b2f-123">In the following illustration, the **PaymentModel** data source returns a list of customer records by using the **Customer** component.</span></span> <span data-ttu-id="14b2f-124">Zwraca wartość daty przetwarzania przy użyciu pola **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="14b2f-124">It returns the processing date value by using the **ProcessingDate** field.</span></span>

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

<span data-ttu-id="14b2f-125">W formacie raportowania elektronicznego (ER) przeznaczonym do generowania pliku elektronicznego dla wybranych klientów **PaymentModel** jest wybrane jako źródło danych i kontroluje przebieg procesu.</span><span class="sxs-lookup"><span data-stu-id="14b2f-125">In the Electronic reporting (ER) format that is designed to generate an electronic file for selected customers, **PaymentModel** is selected as a data source, and it controls the process flow.</span></span> <span data-ttu-id="14b2f-126">Jeśli wybrany klient jest zablokowany w dniu generowania raportu, następuje zgłoszenie wyjątku w celu powiadomienia użytkownika.</span><span class="sxs-lookup"><span data-stu-id="14b2f-126">If a selected customer is stopped for the date when the report is processed, an exception is thrown to notify the user.</span></span> <span data-ttu-id="14b2f-127">Formuła przeznaczona dla tego typu kontroli przetwarzania może skorzystać z poniższych zasobów:</span><span class="sxs-lookup"><span data-stu-id="14b2f-127">The formula that is designed for this type of processing control can use the following resources:</span></span>

- <span data-ttu-id="14b2f-128">Etykieta SYS70894, która ma następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="14b2f-128">Label SYS70894, which has the following text:</span></span>

    - <span data-ttu-id="14b2f-129">**W języku polskim:** „Nie ma nic do wydrukowania”</span><span class="sxs-lookup"><span data-stu-id="14b2f-129">**For the EN-US language:** "Nothing to print"</span></span>
    - <span data-ttu-id="14b2f-130">**W języku niemieckim:** „Nichts zu drucken”</span><span class="sxs-lookup"><span data-stu-id="14b2f-130">**For the DE language:** "Nichts zu drucken"</span></span>

- <span data-ttu-id="14b2f-131">Etykieta SYS18389, która ma następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="14b2f-131">Label SYS18389, which has the following text:</span></span>

    - <span data-ttu-id="14b2f-132">**W języku polskim:** „Klient %1 jest zablokowany do %2”.</span><span class="sxs-lookup"><span data-stu-id="14b2f-132">**For the EN-US language:** "Customer %1 is stopped for %2."</span></span>
    - <span data-ttu-id="14b2f-133">**W języku niemieckim:** „Debitor '„%1” wird für %2 gesperrt”.</span><span class="sxs-lookup"><span data-stu-id="14b2f-133">**For the DE language:** "Debitor '%1' wird für %2 gesperrt."</span></span>

<span data-ttu-id="14b2f-134">Poniżej przedstawiono wyrażenie, które można zaprojektować.</span><span class="sxs-lookup"><span data-stu-id="14b2f-134">Here is the expression that can be designed.</span></span>

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

<span data-ttu-id="14b2f-135">Jeśli raport jest przetwarzany dla odbiorcy **Litware Retail** w dniu 17 grudnia 2015 r. w kulturze **PL** i języku **PL**, formuła zwraca następujący tekst, który może być prezentowany użytkownikowi jako komunikat o wyjątku:</span><span class="sxs-lookup"><span data-stu-id="14b2f-135">If a report is processed for the **Litware Retail** customer on December 17, 2015, in the **EN-US** culture and the **EN-US** language, this formula returns the following text, which can be presented to the user as an exception message:</span></span>

<span data-ttu-id="14b2f-136">*Nie ma nic do wydrukowania. Odbiorca Litware Retail jest zablokowany do 17.12.2015.*</span><span class="sxs-lookup"><span data-stu-id="14b2f-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span></span>

<span data-ttu-id="14b2f-137">Jeśli ten sam raport będzie przetwarzany dla odbiorcy **Litware Retail** w dniu 17 grudnia 2015 w języku **DE** i kulturze **DE**, formuła zwraca następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="14b2f-137">If the same report is processed for the **Litware Retail** customer on December 17, 2015, in the **DE** culture and the **DE** language, the formula returns the following text, which uses a different date format:</span></span>

<span data-ttu-id="14b2f-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span><span class="sxs-lookup"><span data-stu-id="14b2f-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span></span>

>[!NOTE]
> <span data-ttu-id="14b2f-139">W formułach raportowania elektronicznego dla etykiet jest stosowana następująca składnia:</span><span class="sxs-lookup"><span data-stu-id="14b2f-139">The following syntax is applied in ER formulas for labels:</span></span>
>
> - <span data-ttu-id="14b2f-140">**Etykiety aplikacji Microsoft Dynamics 365 Finance:** **\@X**, gdzie **X** oznacza identyfikator etykiety w drzewie obiektów aplikacji (AOT)</span><span class="sxs-lookup"><span data-stu-id="14b2f-140">**For labels from resources in the Microsoft Dynamics 365 Finance app:** **\@X**, where **X** is the label ID in the Application Object Tree (AOT)</span></span>
> - <span data-ttu-id="14b2f-141">**Etykiety, które znajdują się w konfiguracjach ER:** **@"GER_LABEL:X"**, gdzie **X** oznacza identyfikator etykiety w konfiguracji raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="14b2f-141">**For labels that reside in ER configurations:** **@"GER_LABEL:X"**, where **X** is the label ID in the ER configuration</span></span>

## <a name="additional-resources"></a><span data-ttu-id="14b2f-142">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="14b2f-142">Additional resources</span></span>

[<span data-ttu-id="14b2f-143">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="14b2f-143">Text functions</span></span>](er-functions-category-text.md)
