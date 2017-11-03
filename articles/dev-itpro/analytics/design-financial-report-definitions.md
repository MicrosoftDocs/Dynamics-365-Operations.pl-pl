---
title: "Definicje raportów w Projektancie raportów finansowych"
description: "Ten artykuł zawiera informacje o definicjach raportów. Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu. Definicja raportu zawiera również opcje i ustawienia umożliwiające dostosowywanie raportu."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 58030df8db467f754ec93ecc3f41585b20f03893
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="705cc-105">Definicje raportów w Projektancie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="705cc-105">Report definitions in financial report designer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="705cc-106">Ten artykuł zawiera informacje o definicjach raportów.</span><span class="sxs-lookup"><span data-stu-id="705cc-106">This article provides information about report definitions.</span></span> <span data-ttu-id="705cc-107">Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu.</span><span class="sxs-lookup"><span data-stu-id="705cc-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="705cc-108">Definicja raportu zawiera również opcje i ustawienia umożliwiające dostosowywanie raportu.</span><span class="sxs-lookup"><span data-stu-id="705cc-108">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="705cc-109">Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu.</span><span class="sxs-lookup"><span data-stu-id="705cc-109">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="705cc-110">Definicja raportu zawiera także opcje i ustawienia umożliwiające dostosowanie raportu.</span><span class="sxs-lookup"><span data-stu-id="705cc-110">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="705cc-111">Po zdefiniowaniu definicji wierszy i kolumn trzeba połączyć je w definicji raportu.</span><span class="sxs-lookup"><span data-stu-id="705cc-111">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="705cc-112">Na tym etapie można też zdefiniować inne aspekty definicji, np. poziom szczegółowości i data raportu.</span><span class="sxs-lookup"><span data-stu-id="705cc-112">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="705cc-113">Następnie można zapisać i wygenerować raport.</span><span class="sxs-lookup"><span data-stu-id="705cc-113">You can then save and generate a report.</span></span> <span data-ttu-id="705cc-114">Funkcja sprawozdawczości finansowej oferuje następujące poziomy szczegółowości:</span><span class="sxs-lookup"><span data-stu-id="705cc-114">Financial reporting offers the following levels of detail:</span></span>

-   <span data-ttu-id="705cc-115">Finanse</span><span class="sxs-lookup"><span data-stu-id="705cc-115">Financial</span></span>
-   <span data-ttu-id="705cc-116">Finanse i Konto</span><span class="sxs-lookup"><span data-stu-id="705cc-116">Financial and Account</span></span>
-   <span data-ttu-id="705cc-117">Finanse, Konto i Transakcja</span><span class="sxs-lookup"><span data-stu-id="705cc-117">Financial, Account, and Transaction</span></span>

<span data-ttu-id="705cc-118">Jednak w zależności od tego, w jaki sposób dane są przechowywane w systemie ERP Microsoft Dynamics, szczegóły transakcji mogą nie być dostępne w raportach.</span><span class="sxs-lookup"><span data-stu-id="705cc-118">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="705cc-119">Tworzenie definicji raportu</span><span class="sxs-lookup"><span data-stu-id="705cc-119">Create a report definition</span></span>
1.  <span data-ttu-id="705cc-120">W Projektancie raportów w menu **Plik** kliknij przycisk **Nowy**, a następnie wybierz opcję **Definicja raportu**.</span><span class="sxs-lookup"><span data-stu-id="705cc-120">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2.  <span data-ttu-id="705cc-121">Podaj odpowiednie informacje na kartach **Raport**, **Produkcja i dystrybucja**, **Nagłówki i stopki** i **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="705cc-121">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="705cc-122">Zawartość definicji raportu</span><span class="sxs-lookup"><span data-stu-id="705cc-122">Contents of a report definition</span></span>
<span data-ttu-id="705cc-123">W poniższej tabeli opisano karty w definicji raportu oraz sposób wykorzystania informacji.</span><span class="sxs-lookup"><span data-stu-id="705cc-123">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="705cc-124">Tabulator</span><span class="sxs-lookup"><span data-stu-id="705cc-124">Tab</span></span></th>
<th><span data-ttu-id="705cc-125">Opis</span><span class="sxs-lookup"><span data-stu-id="705cc-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="705cc-126">Raport</span><span class="sxs-lookup"><span data-stu-id="705cc-126">Report</span></span></td>
<td><span data-ttu-id="705cc-127">Tworzenie raportu, konfigurowanie raportu lub modyfikowanie istniejącego raportu.</span><span class="sxs-lookup"><span data-stu-id="705cc-127">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="705cc-128">Produkcja i dystrybucja</span><span class="sxs-lookup"><span data-stu-id="705cc-128">Output and Distribution</span></span></td>
<td><span data-ttu-id="705cc-129">Zmienianie typu produkcji i dystrybucji raportu.</span><span class="sxs-lookup"><span data-stu-id="705cc-129">Change the output type and destination of the report.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="705cc-130">Nagłówek i stopki</span><span class="sxs-lookup"><span data-stu-id="705cc-130">Headers and Footers</span></span></td>
<td><span data-ttu-id="705cc-131">Definiowanie i formatowanie nagłówków i stopek raportu.</span><span class="sxs-lookup"><span data-stu-id="705cc-131">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="705cc-132">Na przykład można dodać tekst lub obrazy w nagłówku lub stopce.</span><span class="sxs-lookup"><span data-stu-id="705cc-132">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="705cc-133">Funkcja sprawozdawczości finansowej obsługuje pliki obrazów w formacie .bmp, .jpg i .png.</span><span class="sxs-lookup"><span data-stu-id="705cc-133">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="705cc-134">Można również dodać kody autotekstu do wstawiania innych informacji, takich jak nazwa firmy, nazwa raportu czy numer strony.</span><span class="sxs-lookup"><span data-stu-id="705cc-134">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="705cc-135">Ustawienia</span><span class="sxs-lookup"><span data-stu-id="705cc-135">Settings</span></span></td>
<td><span data-ttu-id="705cc-136">Określanie ustawień definicji raportu, na przykład następujących ustawień:</span><span class="sxs-lookup"><span data-stu-id="705cc-136">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="705cc-137">Formatowanie i zaokrąglanie kwot</span><span class="sxs-lookup"><span data-stu-id="705cc-137">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="705cc-138">Formatowanie raportów szczegółów</span><span class="sxs-lookup"><span data-stu-id="705cc-138">Format detail reports</span></span></li>
<li><span data-ttu-id="705cc-139">Formatowanie drzewek raportowania</span><span class="sxs-lookup"><span data-stu-id="705cc-139">Format reporting trees</span></span></li>
<li><span data-ttu-id="705cc-140">Generowanie raportu wyjątków</span><span class="sxs-lookup"><span data-stu-id="705cc-140">Generate an exception report</span></span></li>
<li><span data-ttu-id="705cc-141">Określanie konwersja waluty</span><span class="sxs-lookup"><span data-stu-id="705cc-141">Specify currency conversion</span></span></li>
<li><span data-ttu-id="705cc-142">Szczegóły sumy częściowej i filtrowanie szczegółów</span><span class="sxs-lookup"><span data-stu-id="705cc-142">Subtotal and filter account details</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="705cc-143">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="705cc-143">See also</span></span>
--------

[<span data-ttu-id="705cc-144">Raporty finansowe</span><span class="sxs-lookup"><span data-stu-id="705cc-144">Financial reporting</span></span>](financial-reporting-intro.md)




