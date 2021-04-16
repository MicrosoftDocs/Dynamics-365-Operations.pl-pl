---
title: LISTOFFIELDS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LISTOFFIELDS w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 4f394a557beaeb558f5c7065eefe16f4aadce6ac
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743782"
---
# <a name="listoffields-er-function"></a><span data-ttu-id="58586-103">LISTOFFIELDS, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="58586-103">LISTOFFIELDS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58586-104">Funkcja `LISTOFFIELDS` zwraca wartość typu *Lista rekordów*, która jest tworzona na podstawie struktury określonego argumentu typu *Wyliczenie* lub *Kontener (rekord)*.</span><span class="sxs-lookup"><span data-stu-id="58586-104">The `LISTOFFIELDS` function returns a *Record list* value that is created based on the structure of the specified argument of the *Enumeration* or *Container (record)* type.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="58586-105">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="58586-105">Syntax 1</span></span>

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a><span data-ttu-id="58586-106">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="58586-106">Syntax 2</span></span>

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a><span data-ttu-id="58586-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="58586-107">Arguments</span></span>

<span data-ttu-id="58586-108">`path`: odwołanie do źródła danych</span><span class="sxs-lookup"><span data-stu-id="58586-108">`path`: Data source reference</span></span>

<span data-ttu-id="58586-109">Prawidłowa ścieżka odwołania źródła danych jednego z następujących typów danych:</span><span class="sxs-lookup"><span data-stu-id="58586-109">The valid reference path of a data source of one of the following data types:</span></span>

- <span data-ttu-id="58586-110">Wyliczenie modeli</span><span class="sxs-lookup"><span data-stu-id="58586-110">Model enumeration</span></span>
- <span data-ttu-id="58586-111">Wyliczenie formatów</span><span class="sxs-lookup"><span data-stu-id="58586-111">Format enumeration</span></span>
- <span data-ttu-id="58586-112">Wyliczenie aplikacji</span><span class="sxs-lookup"><span data-stu-id="58586-112">Application enumeration</span></span>
- <span data-ttu-id="58586-113">Kontener (rekord)</span><span class="sxs-lookup"><span data-stu-id="58586-113">Container (record)</span></span>

<span data-ttu-id="58586-114">`language`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="58586-114">`language`: *String*</span></span>

<span data-ttu-id="58586-115">Tekst, który reprezentuje kod języka.</span><span class="sxs-lookup"><span data-stu-id="58586-115">Text that represents a language code.</span></span>

## <a name="return-values"></a><span data-ttu-id="58586-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="58586-116">Return values</span></span>

<span data-ttu-id="58586-117">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="58586-117">*Record list*</span></span>

<span data-ttu-id="58586-118">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="58586-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="58586-119">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="58586-119">Usage notes</span></span>

<span data-ttu-id="58586-120">Utworzona lista składa się z rekordów zawierających następujące pola:</span><span class="sxs-lookup"><span data-stu-id="58586-120">The list that is created consists of records that have the following fields:</span></span>

- <span data-ttu-id="58586-121">**Nazwa** (typ danych *Ciąg*)</span><span class="sxs-lookup"><span data-stu-id="58586-121">**Name** (*String* data type)</span></span>
- <span data-ttu-id="58586-122">**Etykieta** (typ danych *Ciąg*)</span><span class="sxs-lookup"><span data-stu-id="58586-122">**Label** (*String* data type)</span></span>
- <span data-ttu-id="58586-123">**Opis** (typ danych *Ciąg*)</span><span class="sxs-lookup"><span data-stu-id="58586-123">**Description** (*String* data type)</span></span>
- <span data-ttu-id="58586-124">**Przetłumaczone** (typ danych *Wartość logiczna*)</span><span class="sxs-lookup"><span data-stu-id="58586-124">**IsTranslated** (*Boolean* data type)</span></span>

<span data-ttu-id="58586-125">Jeśli argument `path` odwołuje się do źródła danych typu *Kontener (rekord)*, dla każdego przywołanego pola rekordu kontenera do utworzonej listy dodawany jest nowy rekord.</span><span class="sxs-lookup"><span data-stu-id="58586-125">If the `path` argument refers to a data source of the *Container (Record)* type, for every field of the referenced container record, a new record is added to the list that is created.</span></span> <span data-ttu-id="58586-126">Dla każdego utworzonego rekordu pole **nazwa** zwraca nazwę pola przywołanego rekordu kontenera, dla którego utworzono bieżący rekord.</span><span class="sxs-lookup"><span data-stu-id="58586-126">For every record that is created, the **Name** field returns the name of the field of the referenced container record that the current record was created for.</span></span>

<span data-ttu-id="58586-127">Jeśli argument `path` odwołuje się do źródła danych jednego z typów *Wyliczenie*, dla każdej wartości przywołanego wyliczenia do utworzonej listy dodawany jest nowy rekord.</span><span class="sxs-lookup"><span data-stu-id="58586-127">If the `path` argument refers to a data source of one of the *Enumeration* types, for every enumeration value of the referenced enumeration, a new record is added to the list that is created.</span></span> <span data-ttu-id="58586-128">Dla każdego utworzonego rekordu pole **Nazwa** zwraca wartość przywołanego wyliczenia, dla którego utworzono bieżący rekord, pole **Opis** zwraca opis tego wyliczenia, a pole **Etykieta** — jego etykietę.</span><span class="sxs-lookup"><span data-stu-id="58586-128">For every record that is created, the **Name** field returns the value of the referenced enumeration that the current record was created for, the **Description** field returns the description of that enumeration, and the **Label** field returns the label of that enumeration.</span></span>

<span data-ttu-id="58586-129">W czasie wykonywania, gdy jest używana składnia 1, pola **Etykieta** i **Opis** muszą zwracać wartości, które są oparte na ustawieniach językowych uruchomionego formatu modułu Raportowanie elektroniczne (ER):</span><span class="sxs-lookup"><span data-stu-id="58586-129">At runtime, when syntax 1 is used, the **Label** and **Description** fields must return values that are based on the language settings of the Electronic reporting (ER) format that is running:</span></span>

- <span data-ttu-id="58586-130">Jeśli etykiety i opisy dla żądanego języka są dostępne, pola **Etykieta** i **Opis** zwracają wartości oparte na tym języku, a pole **Przetłumaczone** zwraca wartość **True**.</span><span class="sxs-lookup"><span data-stu-id="58586-130">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="58586-131">Jeśli etykiety i opisy dla żądanego języka są niedostępne, pola **Etykieta** i **Opis** zwracają wartości oparte na domyślnym języku **EN-US**, a pole **Przetłumaczone** zwraca wartość **False**.</span><span class="sxs-lookup"><span data-stu-id="58586-131">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the default **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

<span data-ttu-id="58586-132">W czasie wykonywania, gdy jest używana składnia 2, pola **Etykieta** i **Opis** muszą zwracać wartości, które są oparte na języku zdefiniowanym jako drugi argument wywołanej funkcji:</span><span class="sxs-lookup"><span data-stu-id="58586-132">At runtime, when syntax 2 is used, the **Label** and **Description** fields must return values that are based on the language that is defined as the second argument of the called function:</span></span>

- <span data-ttu-id="58586-133">Jeśli etykiety i opisy dla żądanego języka są dostępne, pola **Etykieta** i **Opis** zwracają wartości oparte na tym języku, a pole **Przetłumaczone** zwraca wartość **True**.</span><span class="sxs-lookup"><span data-stu-id="58586-133">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="58586-134">Jeśli etykiety i opisy dla żądanego języka są niedostępne, pola **Etykieta** i **Opis** zwracają wartości oparte na języku **EN-US**, a pole **Przetłumaczone** zwraca wartość **False**.</span><span class="sxs-lookup"><span data-stu-id="58586-134">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

## <a name="example-1"></a><span data-ttu-id="58586-135">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="58586-135">Example 1</span></span>

<span data-ttu-id="58586-136">Na poniższej ilustracji wyliczenie zostało wprowadzone do modelu danych ER.</span><span class="sxs-lookup"><span data-stu-id="58586-136">In the following illustration, an enumeration is introduced in an ER data model.</span></span>

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

<span data-ttu-id="58586-137">Na ilustracji przedstawiono następujące szczegóły:</span><span class="sxs-lookup"><span data-stu-id="58586-137">The following illustration shows these details:</span></span>

- <span data-ttu-id="58586-138">Wartość stałotekstowa modelu wstawiona do raportu jako źródło danych.</span><span class="sxs-lookup"><span data-stu-id="58586-138">The model enumeration is inserted into a report as a data source.</span></span>
- <span data-ttu-id="58586-139">W wyrażeniu ER wyliczenie modelu jest używane jako parametr funkcji `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="58586-139">An ER expression uses the model enumeration as a parameter of the `LISTOFFIELDS` function.</span></span>
- <span data-ttu-id="58586-140">Źródło danych typu *Lista rekordów* jest wstawiane do raportu przy użyciu utworzonego wyrażenia ER.</span><span class="sxs-lookup"><span data-stu-id="58586-140">A data source of the *Record list* type is inserted into a report by using the ER expression that is created.</span></span>

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

<span data-ttu-id="58586-141">W poniższym przykładzie pokazano elementy formatu ER, które są powiązane ze źródłem danych typu *Lista rekordów* utworzonym przy użyciu funkcji `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="58586-141">The following example shows the ER format elements that are bound to the data source of the *Record list* type that was created by using the `LISTOFFIELDS` function.</span></span>

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

<span data-ttu-id="58586-142">Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.</span><span class="sxs-lookup"><span data-stu-id="58586-142">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> <span data-ttu-id="58586-143">Zgodnie z ustawieniami języka nadrzędnych elementów formatu **PLIK** i **FOLDER** przetłumaczone teksty etykiet i opisów są wprowadzane do danych wyjściowych formatu ER.</span><span class="sxs-lookup"><span data-stu-id="58586-143">Based on the language settings of the parent **FILE** and **FOLDER** format elements, translated text for labels and descriptions is entered in the output of the ER format.</span></span>

## <a name="example-2"></a><span data-ttu-id="58586-144">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="58586-144">Example 2</span></span>

<span data-ttu-id="58586-145">Typ źródła danych *Pole obliczeniowe* jest używane do konfigurowania źródeł danych **enumType\_de** i **enumType\_deCH** dla wyliczenia modelu danych **enumType**:</span><span class="sxs-lookup"><span data-stu-id="58586-145">You use the *Calculated field* data source type to configure **enumType\_de** and **enumType\_deCH** data sources for the **enumType** data model enumeration:</span></span>

- <span data-ttu-id="58586-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span><span class="sxs-lookup"><span data-stu-id="58586-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span></span>
- <span data-ttu-id="58586-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span><span class="sxs-lookup"><span data-stu-id="58586-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span></span>

<span data-ttu-id="58586-148">W tym przypadku można użyć następującego wyrażenia, aby otrzymać etykietę wyliczenia w języku niemieckim (Szwajcaria), jeśli takie tłumaczenie jest dostępne.</span><span class="sxs-lookup"><span data-stu-id="58586-148">In this case, you can use the following expression to get the label of the enumeration value in Swiss German, if that translation is available.</span></span> <span data-ttu-id="58586-149">Jeśli tłumaczenie na język niemiecki (Szwajcaria) nie jest dostępne, etykieta pozostaje w języku niemieckim.</span><span class="sxs-lookup"><span data-stu-id="58586-149">If the Swiss German translation isn't available, the label is in German.</span></span>

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a><span data-ttu-id="58586-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="58586-150">Additional resources</span></span>

[<span data-ttu-id="58586-151">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="58586-151">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]