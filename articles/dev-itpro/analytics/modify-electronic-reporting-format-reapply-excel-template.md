---
title: Modyfikowanie formatu Raportowania elektronicznego przez ponowne zastosowanie szablonu programu Microsoft Excel
description: "Ten temat zawiera informacje o sposobie modyfikowania formatu Raportowanie elektroniczne (ER) używanego do generowania dokumentów biznesowych przez ponowne zastosowanie szablonu programu Excel."
author: NickSelin
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: af7f9a373496eee4df354d5dd9e5a25c51317c43
ms.openlocfilehash: fca7fb75b965886c2ebc06b12940434f2ffc2543
ms.contentlocale: pl-pl
ms.lasthandoff: 02/27/2018

---
# <a name="modify-an-electronic-reporting-format-by-reapplying-a-microsoft-excel-template"></a><span data-ttu-id="c9aea-103">Modyfikowanie formatu Raportowania elektronicznego przez ponowne zastosowanie szablonu programu Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="c9aea-103">Modify an Electronic reporting format by reapplying a Microsoft Excel template</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c9aea-104">Narzędzie Raportowanie elektroniczne (ER) służy do generowania dokumentów biznesowych w formacie elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="c9aea-104">The Electronic reporting (ER) tool is used to generate business documents in an electronic format.</span></span> <span data-ttu-id="c9aea-105">Aby wygenerować dokument biznesowy, należy utworzyć format ER, a następnie użyć projektanta ER w celu zdefiniowania układu dokumentu biznesowego i określenia danych, które powinien zawierać.</span><span class="sxs-lookup"><span data-stu-id="c9aea-105">To generate a business document, you must create an ER format, and then use the ER designer to define the layout of the business document and specify the data that should be included in it.</span></span> <span data-ttu-id="c9aea-106">Następnie można uruchomić format ER w celu wygenerowania dokumentu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="c9aea-106">You can then run the ER format to generate the business document.</span></span>

<span data-ttu-id="c9aea-107">Narzędzie ER może służyć do generowania dokumentów biznesowych w postaci plików programu Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="c9aea-107">The ER tool can be used to generate business documents as Microsoft Excel files.</span></span> <span data-ttu-id="c9aea-108">Dokumentu programu Excel można użyć jako szablonu dla tych dokumentów.</span><span class="sxs-lookup"><span data-stu-id="c9aea-108">You can use an Excel document as a template for these documents.</span></span> <span data-ttu-id="c9aea-109">Aby zdefiniować układ dokumentu w projektancie ER, można zaimportować zawartość dokumentu programu Excel, który ma zostać użyty jako szablon do zdefiniowanego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="c9aea-109">To define the document layout in the ER designer, you can import the contents of the Excel document that you want to use as a template into the defined ER format.</span></span> <span data-ttu-id="c9aea-110">Aby uzyskać szczegółowe informacje i przećwiczyć ten scenariusz obejrzyj przewodnik po zadaniu **ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML** (część procesu biznesowego 7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)).</span><span class="sxs-lookup"><span data-stu-id="c9aea-110">For more details, and to practice this scenario, play the task guide **ER Design a configuration for generating reports in OPENXML format** (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span>

<span data-ttu-id="c9aea-111">W przypadku edycji dokumentu programu Excel używanego jako szablon dokumentu biznesowego, nowa funkcja ER umożliwia ponowne zastosowanie zaktualizowanego szablonu do formatu ER.</span><span class="sxs-lookup"><span data-stu-id="c9aea-111">If you edit the Excel document that is used as a template for a business document, new ER functionality lets you reapply the updated template to the ER format.</span></span> <span data-ttu-id="c9aea-112">Format ER jest następnie aktualizowany, aby był zgodny ze zaktualizowanym szablonem.</span><span class="sxs-lookup"><span data-stu-id="c9aea-112">The ER format is then updated so that it adheres to the updated template.</span></span> <span data-ttu-id="c9aea-113">Aby uzyskać szczegółowe informacje o tej funkcji, odtwórz przewodnik po zadaniu **ER Modyfikowanie formatu przez ponowne zastosowanie szablonu programu Excel** (część procesu biznesowego 7.5.5.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10683)).</span><span class="sxs-lookup"><span data-stu-id="c9aea-113">For more details about this functionality, play the task guide **ER Modify a format by reapplying an Excel template** (part of the 7.5.5.3 Acquire/Develop IT service/solution components (10683) business process).</span></span> <span data-ttu-id="c9aea-114">W kroku przewodnika po zadaniu, w którym importujesz zaktualizowany szablon, użyj zmodyfikowanego szablonu pliku programu Excel Raport o płatnościach: SampleVendPaymWsReport2, jako szablonu.</span><span class="sxs-lookup"><span data-stu-id="c9aea-114">In the task guide step where you import an updated template, use the modified template of the Payment Report Excel file, SampleVendPaymWsReport2, as a template.</span></span>

