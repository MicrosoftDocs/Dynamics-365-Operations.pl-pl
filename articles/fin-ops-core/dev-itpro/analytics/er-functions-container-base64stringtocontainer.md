---
title: Base64StringToContainer, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji Base64StringToContainer w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0e92ae41a3e0f03cb14d4791ab768f096f2a0523
ms.sourcegitcommit: e8a46e127d70986539c138b27a641bff6f6874d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2020
ms.locfileid: "4739104"
---
# <a name="base64stringtocontainer-er-function"></a><span data-ttu-id="8aab3-103">Base64StringToContainer, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="8aab3-103">Base64StringToContainer ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8aab3-104">[Funkcja](er-formula-language.md#functions) `BASE64STRINGTOCONTAINER` przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *[Kontener](er-functions-category-container.md)*.</span><span class="sxs-lookup"><span data-stu-id="8aab3-104">The `BASE64STRINGTOCONTAINER` [function](er-formula-language.md#functions) converts the specified input of the *String* type to a data item of the *[Container](er-functions-category-container.md)* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="8aab3-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="8aab3-105">Syntax</span></span>

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a><span data-ttu-id="8aab3-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="8aab3-106">Arguments</span></span>

<span data-ttu-id="8aab3-107">`input`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="8aab3-107">`input`: *String*</span></span>

<span data-ttu-id="8aab3-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="8aab3-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="8aab3-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="8aab3-109">Return values</span></span>

<span data-ttu-id="8aab3-110">*Kontener*</span><span class="sxs-lookup"><span data-stu-id="8aab3-110">*Container*</span></span>

<span data-ttu-id="8aab3-111">Wynikowa wartość binarna w formacie binarnym large object (BLOB).</span><span class="sxs-lookup"><span data-stu-id="8aab3-111">The resulting binary value in binary large object (BLOB) format.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8aab3-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="8aab3-112">Usage notes</span></span>

<span data-ttu-id="8aab3-113">Wyjątek „Parametr jest nieprawidłowy” występuje, jeśli ciąg wejściowy nie dostarcza prawidłowej grupy Base64 schematów kodowania binarnego na tekst.</span><span class="sxs-lookup"><span data-stu-id="8aab3-113">The "Parameter is not valid" exception is thrown if the input string doesn't provide a correct Base64 group of binary-to-text encoding schemes.</span></span>

## <a name="example"></a><span data-ttu-id="8aab3-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="8aab3-114">Example</span></span>

<span data-ttu-id="8aab3-115">Definiuje się następujące źródła danych w mapowaniu modelu:</span><span class="sxs-lookup"><span data-stu-id="8aab3-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="8aab3-116">Główne źródło danych **DocuTypeGroupEnum** typu *Dynamics 365 for Operations /Wyliczenie*, które odwołuje się do wyliczenia aplikacji **DocuTypeGroup**</span><span class="sxs-lookup"><span data-stu-id="8aab3-116">The root **DocuTypeGroupEnum** data source of the *Dynamics 365 for Operations / Enumeration* type that refers to the **DocuTypeGroup** application enumeration</span></span>
- <span data-ttu-id="8aab3-117">Główne źródło danych **Klient** typu *Dynamics 365 for Operations / rekordy tabeli* odwołujące się do tabeli aplikacji **CustTable**</span><span class="sxs-lookup"><span data-stu-id="8aab3-117">The root **Customer** data source of the *Dynamics 365 for Operations / Table records* type that refers to the **CustTable** application table</span></span>
- <span data-ttu-id="8aab3-118">Źródło **\#Multimedia** dla typu *Pole obliczeniowe* skonfigurowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8aab3-118">The **\#Media** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="8aab3-119">Jest ono dodawane jako podrzędne źródło danych źródła danych **Klient**.</span><span class="sxs-lookup"><span data-stu-id="8aab3-119">It's added as a child data source of the **Customer** data source.</span></span>
    - <span data-ttu-id="8aab3-120">Zawiera wyrażenie `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span><span class="sxs-lookup"><span data-stu-id="8aab3-120">It contains the expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span></span>

- <span data-ttu-id="8aab3-121">Źródło **\#MediaAsBase64String** dla typu *Pole obliczeniowe* skonfigurowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8aab3-121">The **\#MediaAsBase64String** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="8aab3-122">Jest ono dodawane jako podrzędne źródło danych źródła danych **Klient.'\#Multimedia**.</span><span class="sxs-lookup"><span data-stu-id="8aab3-122">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="8aab3-123">Zawiera wyrażenie `Customer.'#Media'.'getFileContentAsBase64String()'`.</span><span class="sxs-lookup"><span data-stu-id="8aab3-123">It contains the expression `Customer.'#Media'.'getFileContentAsBase64String()'`.</span></span>

- <span data-ttu-id="8aab3-124">Źródło **\#BlobFomBase64** dla typu *Pole obliczeniowe* skonfigurowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8aab3-124">The **\#BlobFomBase64** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="8aab3-125">Jest ono dodawane jako podrzędne źródło danych źródła danych **Klient.'\#Multimedia**.</span><span class="sxs-lookup"><span data-stu-id="8aab3-125">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="8aab3-126">Zawiera wyrażenie `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span><span class="sxs-lookup"><span data-stu-id="8aab3-126">It contains the expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span></span>

<span data-ttu-id="8aab3-127">W tym przykładzie źródło danych **\#MediaAsBase64String** koduje zawartość binarną bieżącego załącznika multimediów jako tekst reprezentujący grupę Base64 schematów kodowania binarnego na tekst.</span><span class="sxs-lookup"><span data-stu-id="8aab3-127">In this example, the **\#MediaAsBase64String** data source encodes the binary content of the current media attachment as text that represents a Base64 group of binary-to-text encoding schemes.</span></span> <span data-ttu-id="8aab3-128">Źródło danych **\#BlobFomBase64** dekoduje ciąg Base64 i zwraca wartość binarną w formacie obiektu BLOB.</span><span class="sxs-lookup"><span data-stu-id="8aab3-128">The **\#BlobFomBase64** data source decodes the Base64 string and returns a binary value in BLOB format.</span></span>

![Przykładowe źródła danych na stronie projektanta mapowania modelu ER](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a><span data-ttu-id="8aab3-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8aab3-130">Additional resources</span></span>

[<span data-ttu-id="8aab3-131">Funkcje kontenera</span><span class="sxs-lookup"><span data-stu-id="8aab3-131">Container functions</span></span>](er-functions-category-container.md)
