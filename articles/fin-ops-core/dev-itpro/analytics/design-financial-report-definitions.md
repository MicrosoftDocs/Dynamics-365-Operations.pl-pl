---
title: Definicje raportów w Projektancie raportów finansowych
description: Ten artykuł zawiera informacje o definicjach raportów.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 52322453328814b06bacefb4829bb10bf9953186
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755451"
---
# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="7b338-103">Definicje raportów w Projektancie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="7b338-103">Report definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7b338-104">Ten artykuł zawiera informacje o definicjach raportów.</span><span class="sxs-lookup"><span data-stu-id="7b338-104">This article provides information about report definitions.</span></span> <span data-ttu-id="7b338-105">Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu.</span><span class="sxs-lookup"><span data-stu-id="7b338-105">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="7b338-106">Definicja raportu zawiera również opcje i ustawienia umożliwiające dostosowywanie raportu.</span><span class="sxs-lookup"><span data-stu-id="7b338-106">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="7b338-107">Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu.</span><span class="sxs-lookup"><span data-stu-id="7b338-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="7b338-108">Definicja raportu zawiera także opcje i ustawienia umożliwiające dostosowanie raportu.</span><span class="sxs-lookup"><span data-stu-id="7b338-108">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="7b338-109">Po zdefiniowaniu definicji wierszy i kolumn trzeba połączyć je w definicji raportu.</span><span class="sxs-lookup"><span data-stu-id="7b338-109">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="7b338-110">Na tym etapie można też zdefiniować inne aspekty definicji, np. poziom szczegółowości i data raportu.</span><span class="sxs-lookup"><span data-stu-id="7b338-110">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="7b338-111">Następnie można zapisać i wygenerować raport.</span><span class="sxs-lookup"><span data-stu-id="7b338-111">You can then save and generate a report.</span></span> <span data-ttu-id="7b338-112">Funkcja sprawozdawczości finansowej oferuje następujące poziomy szczegółowości:</span><span class="sxs-lookup"><span data-stu-id="7b338-112">Financial reporting offers the following levels of detail:</span></span>

- <span data-ttu-id="7b338-113">Finanse</span><span class="sxs-lookup"><span data-stu-id="7b338-113">Financial</span></span>
- <span data-ttu-id="7b338-114">Finanse i Konto</span><span class="sxs-lookup"><span data-stu-id="7b338-114">Financial and Account</span></span>
- <span data-ttu-id="7b338-115">Finanse, Konto i Transakcja</span><span class="sxs-lookup"><span data-stu-id="7b338-115">Financial, Account, and Transaction</span></span>

<span data-ttu-id="7b338-116">Jednak w zależności od sposobu przechowywania danych w systemie Microsoft Dynamics ERP, szczegóły transakcji mogą być niedostępne w raportach.</span><span class="sxs-lookup"><span data-stu-id="7b338-116">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="7b338-117">Tworzenie definicji raportu</span><span class="sxs-lookup"><span data-stu-id="7b338-117">Create a report definition</span></span>
1. <span data-ttu-id="7b338-118">W Projektancie raportów w menu **Plik** kliknij przycisk **Nowy**, a następnie wybierz opcję **Definicja raportu**.</span><span class="sxs-lookup"><span data-stu-id="7b338-118">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2. <span data-ttu-id="7b338-119">Podaj odpowiednie informacje na kartach **Raport**, **Produkcja i dystrybucja**, **Nagłówki i stopki** i **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="7b338-119">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="7b338-120">Zawartość definicji raportu</span><span class="sxs-lookup"><span data-stu-id="7b338-120">Contents of a report definition</span></span>
<span data-ttu-id="7b338-121">W poniższej tabeli opisano karty w definicji raportu oraz sposób wykorzystania informacji.</span><span class="sxs-lookup"><span data-stu-id="7b338-121">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7b338-122">Tabulator</span><span class="sxs-lookup"><span data-stu-id="7b338-122">Tab</span></span></th>
<th><span data-ttu-id="7b338-123">Opis</span><span class="sxs-lookup"><span data-stu-id="7b338-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7b338-124">Raport</span><span class="sxs-lookup"><span data-stu-id="7b338-124">Report</span></span></td>
<td><span data-ttu-id="7b338-125">Tworzenie raportu, konfigurowanie raportu lub modyfikowanie istniejącego raportu.</span><span class="sxs-lookup"><span data-stu-id="7b338-125">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7b338-126">Produkcja i dystrybucja</span><span class="sxs-lookup"><span data-stu-id="7b338-126">Output and Distribution</span></span></td>
<td><span data-ttu-id="7b338-127">Zmienianie typu produkcji i dystrybucji raportu.</span><span class="sxs-lookup"><span data-stu-id="7b338-127">Change the output type and destination of the report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7b338-128">Nagłówek i stopki</span><span class="sxs-lookup"><span data-stu-id="7b338-128">Headers and Footers</span></span></td>
<td><span data-ttu-id="7b338-129">Definiowanie i formatowanie nagłówków i stopek raportu.</span><span class="sxs-lookup"><span data-stu-id="7b338-129">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="7b338-130">Na przykład można dodać tekst lub obrazy w nagłówku lub stopce.</span><span class="sxs-lookup"><span data-stu-id="7b338-130">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="7b338-131">Funkcja sprawozdawczości finansowej obsługuje pliki obrazów w formacie .bmp, .jpg i .png.</span><span class="sxs-lookup"><span data-stu-id="7b338-131">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="7b338-132">Można również dodać kody autotekstu do wstawiania innych informacji, takich jak nazwa firmy, nazwa raportu czy numer strony.</span><span class="sxs-lookup"><span data-stu-id="7b338-132">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7b338-133">Ustawienia</span><span class="sxs-lookup"><span data-stu-id="7b338-133">Settings</span></span></td>
<td><span data-ttu-id="7b338-134">Określanie ustawień definicji raportu, na przykład następujących ustawień:</span><span class="sxs-lookup"><span data-stu-id="7b338-134">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="7b338-135">Formatowanie i zaokrąglanie kwot</span><span class="sxs-lookup"><span data-stu-id="7b338-135">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="7b338-136">Formatowanie raportów szczegółów</span><span class="sxs-lookup"><span data-stu-id="7b338-136">Format detail reports</span></span></li>
<li><span data-ttu-id="7b338-137">Formatowanie drzewek raportowania</span><span class="sxs-lookup"><span data-stu-id="7b338-137">Format reporting trees</span></span></li>
<li><span data-ttu-id="7b338-138">Generowanie raportu wyjątków</span><span class="sxs-lookup"><span data-stu-id="7b338-138">Generate an exception report</span></span></li>
<li><span data-ttu-id="7b338-139">Określanie konwersja waluty</span><span class="sxs-lookup"><span data-stu-id="7b338-139">Specify currency conversion</span></span></li>
<li><span data-ttu-id="7b338-140">Szczegóły sumy częściowej i filtrowanie szczegółów</span><span class="sxs-lookup"><span data-stu-id="7b338-140">Subtotal and filter account details</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="7b338-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7b338-141">Additional resources</span></span>

[<span data-ttu-id="7b338-142">Raporty finansowe</span><span class="sxs-lookup"><span data-stu-id="7b338-142">Financial reporting</span></span>](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]