---
title: QRCODE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji QRCODE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 8a52dbce29140591baf4be97baef237dce1f2511
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040855"
---
# <span data-ttu-id="dce4a-103"><a name="QRCODE">QRCODE, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="dce4a-103"><a name="QRCODE">QRCODE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dce4a-104">Funkcja `QRCODE` zwraca wartość typu *Kontener*, która przedstawia obraz kodu szybkiej odpowiedzi (kod QR) dla określonego ciągu w formacie binarnym.</span><span class="sxs-lookup"><span data-stu-id="dce4a-104">The `QRCODE` function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span>

## <a name="syntax"></a><span data-ttu-id="dce4a-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="dce4a-105">Syntax</span></span>

```vb
QRCODE (text)
```

## <a name="arguments"></a><span data-ttu-id="dce4a-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="dce4a-106">Arguments</span></span>

<span data-ttu-id="dce4a-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="dce4a-107">`text`: *String*</span></span>

<span data-ttu-id="dce4a-108">Wartość *ciągu* reprezentująca oryginalny tekst.</span><span class="sxs-lookup"><span data-stu-id="dce4a-108">A *String* value that represents the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="dce4a-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="dce4a-109">Return values</span></span>

<span data-ttu-id="dce4a-110">*Kontener*</span><span class="sxs-lookup"><span data-stu-id="dce4a-110">*Container*</span></span>

<span data-ttu-id="dce4a-111">Wynikowy strumień binarny.</span><span class="sxs-lookup"><span data-stu-id="dce4a-111">The resulting binary stream.</span></span>

## <a name="example"></a><span data-ttu-id="dce4a-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="dce4a-112">Example</span></span>

<span data-ttu-id="dce4a-113">Można skonfigurować format modułu Raportowanie elektroniczne (ER) do generowania dokumentu wychodzącego w formacie pakietu Microsoft Office (skoroszyty programu Excel lub dokumenty programu Word) przy użyciu wstępnie zdefiniowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="dce4a-113">You can configure an Electronic reporting (ER) format to generate an outbound document in Microsoft Office format (Excel workbooks or Word documents) by using a predefined template.</span></span> <span data-ttu-id="dce4a-114">Ten szablon może zawierać obiekt **Obraz** (skoroszyt programu Excel) lub **kontrolkę zawartości obrazu** (dokument programu Word) jako symbol zastępczy obrazu kodu QR.</span><span class="sxs-lookup"><span data-stu-id="dce4a-114">This template may contain a **Picture** object (Excel workbook) or a **Picture Content Control** (Word document) as a placeholder for a QR code image.</span></span> <span data-ttu-id="dce4a-115">Musisz dodać do skonfigurowanego formatu ER element **Komórka**, który będzie używany do wypełnienia tego symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="dce4a-115">You need to add to the configured ER format a **Cell** element that will be used to fill this placeholder in.</span></span> <span data-ttu-id="dce4a-116">Aby określić, jakie informacje będą przechowywane w kodzie QR, należy zdefiniować powiązanie dla tego elementu **Komórka**.</span><span class="sxs-lookup"><span data-stu-id="dce4a-116">To specify what information will be stored in a QR code, you need to define a binding for this **Cell** element.</span></span> <span data-ttu-id="dce4a-117">Na przykład można skonfigurować takie powiązanie jako zawierające następujące wyrażenie:</span><span class="sxs-lookup"><span data-stu-id="dce4a-117">For example, you can configure such binding as containing the following expression:</span></span>

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

<span data-ttu-id="dce4a-118">Po uruchomieniu skonfigurowanego formatu ER wartość tekstowa pola **LabelText** źródła danych **model.ListOfShelfLabels** będzie używana do generowania obrazu kodu QR.</span><span class="sxs-lookup"><span data-stu-id="dce4a-118">When you run the configured ER format, the text value of the **LabelText** field of the **model.ListOfShelfLabels** data source will be used to generate a QR code image.</span></span> <span data-ttu-id="dce4a-119">Ten obraz zastąpi symbol zastępczy obrazu kodu QR w szablonie dokumentu używanym do wygenerowania dokumentu wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="dce4a-119">This image will replace a QR code image placeholder in the document template using to generate an outbound document.</span></span> <span data-ttu-id="dce4a-120">Po zeskanowaniu tego obrazu wygenerowanego dokumentu jest zwracany tekst pobrany z pola **LabelText** źródła danych **model.ListOfShelfLabels**.</span><span class="sxs-lookup"><span data-stu-id="dce4a-120">When this image of the generated document is scanned, it returns the text that was taken from the **LabelText** field of the **model.ListOfShelfLabels** data source.</span></span> <span data-ttu-id="dce4a-121">Aby uzyskać więcej informacji, zobacz [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md)</span><span class="sxs-lookup"><span data-stu-id="dce4a-121">For more information, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dce4a-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="dce4a-122">Additional resources</span></span>

[<span data-ttu-id="dce4a-123">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="dce4a-123">Text functions</span></span>](er-functions-category-text.md)
