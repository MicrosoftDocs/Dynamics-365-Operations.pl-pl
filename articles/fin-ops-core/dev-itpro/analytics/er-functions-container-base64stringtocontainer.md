---
title: Base64StringToContainer, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji Base64StringToContainer w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 612590dacc1887b87677c12eddaef42660a7a154
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561549"
---
# <a name="base64stringtocontainer-er-function"></a><span data-ttu-id="f8ea9-103">Base64StringToContainer, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="f8ea9-103">Base64StringToContainer ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8ea9-104">[Funkcja](er-formula-language.md#functions) `BASE64STRINGTOCONTAINER` przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *[Kontener](er-functions-category-container.md)*.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-104">The `BASE64STRINGTOCONTAINER` [function](er-formula-language.md#functions) converts the specified input of the *String* type to a data item of the *[Container](er-functions-category-container.md)* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="f8ea9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f8ea9-105">Syntax</span></span>

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a><span data-ttu-id="f8ea9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f8ea9-106">Arguments</span></span>

<span data-ttu-id="f8ea9-107">`input`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f8ea9-107">`input`: *String*</span></span>

<span data-ttu-id="f8ea9-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="f8ea9-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="f8ea9-109">Return values</span></span>

<span data-ttu-id="f8ea9-110">*Kontener*</span><span class="sxs-lookup"><span data-stu-id="f8ea9-110">*Container*</span></span>

<span data-ttu-id="f8ea9-111">Wynikowa wartość binarna w formacie binarnym large object (BLOB).</span><span class="sxs-lookup"><span data-stu-id="f8ea9-111">The resulting binary value in binary large object (BLOB) format.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f8ea9-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="f8ea9-112">Usage notes</span></span>

<span data-ttu-id="f8ea9-113">Wyjątek „Parametr jest nieprawidłowy” występuje, jeśli ciąg wejściowy nie dostarcza prawidłowej grupy Base64 schematów kodowania binarnego na tekst.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-113">The "Parameter is not valid" exception is thrown if the input string doesn't provide a correct Base64 group of binary-to-text encoding schemes.</span></span>

## <a name="example"></a><span data-ttu-id="f8ea9-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="f8ea9-114">Example</span></span>

<span data-ttu-id="f8ea9-115">Definiuje się następujące źródła danych w mapowaniu modelu:</span><span class="sxs-lookup"><span data-stu-id="f8ea9-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="f8ea9-116">Główne źródło danych **DocuTypeGroupEnum** typu *Dynamics 365 for Operations /Wyliczenie*, które odwołuje się do wyliczenia aplikacji **DocuTypeGroup**</span><span class="sxs-lookup"><span data-stu-id="f8ea9-116">The root **DocuTypeGroupEnum** data source of the *Dynamics 365 for Operations / Enumeration* type that refers to the **DocuTypeGroup** application enumeration</span></span>
- <span data-ttu-id="f8ea9-117">Główne źródło danych **Klient** typu *Dynamics 365 for Operations / rekordy tabeli* odwołujące się do tabeli aplikacji **CustTable**</span><span class="sxs-lookup"><span data-stu-id="f8ea9-117">The root **Customer** data source of the *Dynamics 365 for Operations / Table records* type that refers to the **CustTable** application table</span></span>
- <span data-ttu-id="f8ea9-118">Źródło **\#Multimedia** dla typu *Pole obliczeniowe* skonfigurowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f8ea9-118">The **\#Media** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="f8ea9-119">Jest ono dodawane jako podrzędne źródło danych źródła danych **Klient**.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-119">It's added as a child data source of the **Customer** data source.</span></span>
    - <span data-ttu-id="f8ea9-120">Zawiera wyrażenie `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-120">It contains the expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span></span>

- <span data-ttu-id="f8ea9-121">Źródło **\#MediaAsBase64String** dla typu *Pole obliczeniowe* skonfigurowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f8ea9-121">The **\#MediaAsBase64String** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="f8ea9-122">Jest ono dodawane jako podrzędne źródło danych źródła danych **Klient.'\#Multimedia**.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-122">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="f8ea9-123">Zawiera wyrażenie `Customer.'#Media'.'getFileContentAsBase64String()'`.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-123">It contains the expression `Customer.'#Media'.'getFileContentAsBase64String()'`.</span></span>

- <span data-ttu-id="f8ea9-124">Źródło **\#BlobFomBase64** dla typu *Pole obliczeniowe* skonfigurowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f8ea9-124">The **\#BlobFomBase64** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="f8ea9-125">Jest ono dodawane jako podrzędne źródło danych źródła danych **Klient.'\#Multimedia**.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-125">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="f8ea9-126">Zawiera wyrażenie `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-126">It contains the expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span></span>

<span data-ttu-id="f8ea9-127">W tym przykładzie źródło danych **\#MediaAsBase64String** koduje zawartość binarną bieżącego załącznika multimediów jako tekst reprezentujący grupę Base64 schematów kodowania binarnego na tekst.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-127">In this example, the **\#MediaAsBase64String** data source encodes the binary content of the current media attachment as text that represents a Base64 group of binary-to-text encoding schemes.</span></span> <span data-ttu-id="f8ea9-128">Źródło danych **\#BlobFomBase64** dekoduje ciąg Base64 i zwraca wartość binarną w formacie obiektu BLOB.</span><span class="sxs-lookup"><span data-stu-id="f8ea9-128">The **\#BlobFomBase64** data source decodes the Base64 string and returns a binary value in BLOB format.</span></span>

![Przykładowe źródła danych na stronie projektanta mapowania modelu ER](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a><span data-ttu-id="f8ea9-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f8ea9-130">Additional resources</span></span>

[<span data-ttu-id="f8ea9-131">Funkcje kontenera</span><span class="sxs-lookup"><span data-stu-id="f8ea9-131">Container functions</span></span>](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]