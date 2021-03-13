---
title: Definicje raportów w Projektancie raportów finansowych
description: Ten artykuł zawiera informacje o definicjach raportów.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 7d5531112cfb803912849af3af785b2a69a79f3d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093421"
---
# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="7fa6f-103">Definicje raportów w Projektancie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="7fa6f-103">Report definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7fa6f-104">Ten artykuł zawiera informacje o definicjach raportów.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-104">This article provides information about report definitions.</span></span> <span data-ttu-id="7fa6f-105">Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-105">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="7fa6f-106">Definicja raportu zawiera również opcje i ustawienia umożliwiające dostosowywanie raportu.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-106">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="7fa6f-107">Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="7fa6f-108">Definicja raportu zawiera także opcje i ustawienia umożliwiające dostosowanie raportu.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-108">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="7fa6f-109">Po zdefiniowaniu definicji wierszy i kolumn trzeba połączyć je w definicji raportu.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-109">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="7fa6f-110">Na tym etapie można też zdefiniować inne aspekty definicji, np. poziom szczegółowości i data raportu.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-110">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="7fa6f-111">Następnie można zapisać i wygenerować raport.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-111">You can then save and generate a report.</span></span> <span data-ttu-id="7fa6f-112">Funkcja sprawozdawczości finansowej oferuje następujące poziomy szczegółowości:</span><span class="sxs-lookup"><span data-stu-id="7fa6f-112">Financial reporting offers the following levels of detail:</span></span>

- <span data-ttu-id="7fa6f-113">Finanse</span><span class="sxs-lookup"><span data-stu-id="7fa6f-113">Financial</span></span>
- <span data-ttu-id="7fa6f-114">Finanse i Konto</span><span class="sxs-lookup"><span data-stu-id="7fa6f-114">Financial and Account</span></span>
- <span data-ttu-id="7fa6f-115">Finanse, Konto i Transakcja</span><span class="sxs-lookup"><span data-stu-id="7fa6f-115">Financial, Account, and Transaction</span></span>

<span data-ttu-id="7fa6f-116">Jednak w zależności od sposobu przechowywania danych w systemie Microsoft Dynamics ERP, szczegóły transakcji mogą być niedostępne w raportach.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-116">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="7fa6f-117">Tworzenie definicji raportu</span><span class="sxs-lookup"><span data-stu-id="7fa6f-117">Create a report definition</span></span>
1. <span data-ttu-id="7fa6f-118">W Projektancie raportów w menu **Plik** kliknij przycisk **Nowy**, a następnie wybierz opcję **Definicja raportu**.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-118">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2. <span data-ttu-id="7fa6f-119">Podaj odpowiednie informacje na kartach **Raport**, **Produkcja i dystrybucja**, **Nagłówki i stopki** i **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-119">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="7fa6f-120">Zawartość definicji raportu</span><span class="sxs-lookup"><span data-stu-id="7fa6f-120">Contents of a report definition</span></span>
<span data-ttu-id="7fa6f-121">W poniższej tabeli opisano karty w definicji raportu oraz sposób wykorzystania informacji.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-121">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fa6f-122">Tabulator</span><span class="sxs-lookup"><span data-stu-id="7fa6f-122">Tab</span></span></th>
<th><span data-ttu-id="7fa6f-123">Opis</span><span class="sxs-lookup"><span data-stu-id="7fa6f-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fa6f-124">Raport</span><span class="sxs-lookup"><span data-stu-id="7fa6f-124">Report</span></span></td>
<td><span data-ttu-id="7fa6f-125">Tworzenie raportu, konfigurowanie raportu lub modyfikowanie istniejącego raportu.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-125">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fa6f-126">Produkcja i dystrybucja</span><span class="sxs-lookup"><span data-stu-id="7fa6f-126">Output and Distribution</span></span></td>
<td><span data-ttu-id="7fa6f-127">Zmienianie typu produkcji i dystrybucji raportu.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-127">Change the output type and destination of the report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fa6f-128">Nagłówek i stopki</span><span class="sxs-lookup"><span data-stu-id="7fa6f-128">Headers and Footers</span></span></td>
<td><span data-ttu-id="7fa6f-129">Definiowanie i formatowanie nagłówków i stopek raportu.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-129">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="7fa6f-130">Na przykład można dodać tekst lub obrazy w nagłówku lub stopce.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-130">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="7fa6f-131">Funkcja sprawozdawczości finansowej obsługuje pliki obrazów w formacie .bmp, .jpg i .png.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-131">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="7fa6f-132">Można również dodać kody autotekstu do wstawiania innych informacji, takich jak nazwa firmy, nazwa raportu czy numer strony.</span><span class="sxs-lookup"><span data-stu-id="7fa6f-132">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fa6f-133">Ustawienia</span><span class="sxs-lookup"><span data-stu-id="7fa6f-133">Settings</span></span></td>
<td><span data-ttu-id="7fa6f-134">Określanie ustawień definicji raportu, na przykład następujących ustawień:</span><span class="sxs-lookup"><span data-stu-id="7fa6f-134">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="7fa6f-135">Formatowanie i zaokrąglanie kwot</span><span class="sxs-lookup"><span data-stu-id="7fa6f-135">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="7fa6f-136">Formatowanie raportów szczegółów</span><span class="sxs-lookup"><span data-stu-id="7fa6f-136">Format detail reports</span></span></li>
<li><span data-ttu-id="7fa6f-137">Formatowanie drzewek raportowania</span><span class="sxs-lookup"><span data-stu-id="7fa6f-137">Format reporting trees</span></span></li>
<li><span data-ttu-id="7fa6f-138">Generowanie raportu wyjątków</span><span class="sxs-lookup"><span data-stu-id="7fa6f-138">Generate an exception report</span></span></li>
<li><span data-ttu-id="7fa6f-139">Określanie konwersja waluty</span><span class="sxs-lookup"><span data-stu-id="7fa6f-139">Specify currency conversion</span></span></li>
<li><span data-ttu-id="7fa6f-140">Szczegóły sumy częściowej i filtrowanie szczegółów</span><span class="sxs-lookup"><span data-stu-id="7fa6f-140">Subtotal and filter account details</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="7fa6f-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7fa6f-141">Additional resources</span></span>

[<span data-ttu-id="7fa6f-142">Raporty finansowe</span><span class="sxs-lookup"><span data-stu-id="7fa6f-142">Financial reporting</span></span>](financial-reporting-intro.md)
