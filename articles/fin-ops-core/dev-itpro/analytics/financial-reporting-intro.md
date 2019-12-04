---
title: Raportowanie finansowe
description: Funkcjonalność raportowania finansowego pozwala specjalistom finansowym i biznesowym tworzyć, obsługiwać, wdrażać i wyświetlać sprawozdania finansowe. Wychodzi poza tradycyjne ograniczenia sprawozdawczości, pomagając efektywne projektować różne rodzaje raportów.
author: aprilolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinanicalReportingSetup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 68813
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cdfa9ed24d0456d9beaec03ebac89098131d0675
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771149"
---
# <a name="financial-reporting"></a><span data-ttu-id="8a165-104">Raportowanie finansowe</span><span class="sxs-lookup"><span data-stu-id="8a165-104">Financial reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a165-105">Funkcjonalność raportowania finansowego w aplikacji pozwala specjalistom finansowym i biznesowym tworzyć, obsługiwać, wdrażać i wyświetlać sprawozdania finansowe.</span><span class="sxs-lookup"><span data-stu-id="8a165-105">Financial reporting for the application allows financial and business professionals to create, maintain, deploy, and view financial statements.</span></span> <span data-ttu-id="8a165-106">Wychodzi poza tradycyjne ograniczenia sprawozdawczości, pomagając efektywne projektować różne rodzaje raportów.</span><span class="sxs-lookup"><span data-stu-id="8a165-106">It moves beyond traditional reporting constraints to help you efficiently design various types of reports.</span></span>

<span data-ttu-id="8a165-107">Funkcjonalność sprawozdawczości finansowej obejmuje obsługę wymiarów.</span><span class="sxs-lookup"><span data-stu-id="8a165-107">Financial reporting includes dimension support.</span></span> <span data-ttu-id="8a165-108">W związku z tym segmenty i wymiary kont są od razu dostępne.</span><span class="sxs-lookup"><span data-stu-id="8a165-108">Therefore, account segments or dimensions are immediately available.</span></span> <span data-ttu-id="8a165-109">Nie są wymagane żadne dodatkowe narzędzia ani czynności konfiguracyjnych.</span><span class="sxs-lookup"><span data-stu-id="8a165-109">No additional tools or configuration steps are required.</span></span>

## <a name="financial-reporting-setup"></a><span data-ttu-id="8a165-110">Ustawienia raportowania finansowego</span><span class="sxs-lookup"><span data-stu-id="8a165-110">Financial reporting setup</span></span>
<span data-ttu-id="8a165-111">Strona **Ustawienia raportowania finansowego** zawiera listę wszystkich wymiarów finansowych w systemie.</span><span class="sxs-lookup"><span data-stu-id="8a165-111">The **Financial reporting setup** page has a list of all financial dimensions in the system.</span></span> <span data-ttu-id="8a165-112">**Księga główna** \> **Ustawienia księgi** \> **Ustawienia raportowania finansowego**.</span><span class="sxs-lookup"><span data-stu-id="8a165-112">**General ledger** \> **Ledger setup** \> **Financial reporting setup**.</span></span>

<span data-ttu-id="8a165-113">Strona **Ustawienia raportowania finansowego** zawiera dwie sekcje, które określają dane uwzględniane w raportowaniu finansowym:</span><span class="sxs-lookup"><span data-stu-id="8a165-113">The **Financial reporting setup** page has two sections that determine the data you report on in Financial reporting:</span></span>

- <span data-ttu-id="8a165-114">**Karta Wymiary** — różne firmy korzystają z różnych wymiarów i struktur kont, dlatego nie da się określić, w jakiej kolejności użytkownicy będą chwili wyświetlać wszystkie wymiary finansowe w raportach.</span><span class="sxs-lookup"><span data-stu-id="8a165-114">**Dimensions tab** - Because different companies use different dimensions and account structures, there is no way to determine the order in which users want to view all financial dimensions on reports.</span></span> <span data-ttu-id="8a165-115">Na tej stronie można ustawić kolejność wyświetlania wymiarów finansowych podczas tworzenia i wyświetlania raportu w module Raportowanie finansowe.</span><span class="sxs-lookup"><span data-stu-id="8a165-115">This page allows you set the order in which you want financial dimensions to appear when you build and view a report in Financial reporting.</span></span>
- <span data-ttu-id="8a165-116">**Karta Atrybuty** pozwala wybrać, czy kategorie **Dostawcy** i **Odbiorcy** mają być dostępne podczas filtrowania i projektowania raportów.</span><span class="sxs-lookup"><span data-stu-id="8a165-116">**Attributes tab** is where you can select whether you want the ability to use **Vendors** and **Customers** as attributes for filtering and report design.</span></span> <span data-ttu-id="8a165-117">Raportowanie według dostawcy i odbiorcy będzie przydatne tylko wówczas, jeśli podczas księgowania transakcji nie doda się wielu dostawców lub odbiorców.</span><span class="sxs-lookup"><span data-stu-id="8a165-117">Reporting on Vendor and Customer will only be valuable if you do not enter multiple vendors or customers in a single voucher when posting transactions.</span></span> <span data-ttu-id="8a165-118">Wybranie atrybutu Dostawca i/lub Odbiorca wydłuży czas integracji.</span><span class="sxs-lookup"><span data-stu-id="8a165-118">Choosing Vendor and/or Customer will add additional time to the integration.</span></span>

## <a name="financial-reporting-components"></a><span data-ttu-id="8a165-119">Składniki raportowania finansowego</span><span class="sxs-lookup"><span data-stu-id="8a165-119">Financial reporting components</span></span>
<span data-ttu-id="8a165-120">Następujące składniki aparatu sprawozdawczości finansowej zapewniają łatwe tworzenie, wyświetlanie i planowanie raportów.</span><span class="sxs-lookup"><span data-stu-id="8a165-120">The following components of financial reporting make it easy to create, view, and schedule reports.</span></span>

| <span data-ttu-id="8a165-121">Składnik</span><span class="sxs-lookup"><span data-stu-id="8a165-121">Component</span></span>        | <span data-ttu-id="8a165-122">Funkcje</span><span class="sxs-lookup"><span data-stu-id="8a165-122">Functions</span></span> | <span data-ttu-id="8a165-123">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="8a165-123">Additional information</span></span> |
|------------------|-----------|------------------------|
| <span data-ttu-id="8a165-124">Projektant raportów</span><span class="sxs-lookup"><span data-stu-id="8a165-124">Report Designer</span></span>  | <span data-ttu-id="8a165-125">Tworzenie bloków konstrukcyjnych raportów, które można łączyć w celu definiowania i generowania raportów.</span><span class="sxs-lookup"><span data-stu-id="8a165-125">Create report building blocks that can be combined to define and generate a report.</span></span> <span data-ttu-id="8a165-126">Kreator raportów prowadzi mniej doświadczonych użytkowników przez proces projektowania.</span><span class="sxs-lookup"><span data-stu-id="8a165-126">The report wizard guides less experienced users through the design process.</span></span> <span data-ttu-id="8a165-127">Użytkownicy zaawansowani mogą tworzyć nowe bloki konstrukcyjne raportów lub modyfikować istniejące bloki zgodnie z własnymi wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="8a165-127">Advanced users can create new report building blocks or modify existing building blocks to meet their requirements.</span></span> | |
| <span data-ttu-id="8a165-128">Harmonogramy raportu</span><span class="sxs-lookup"><span data-stu-id="8a165-128">Report schedules</span></span> | <span data-ttu-id="8a165-129">Planowanie regularnego generowania jednego raportu lub grupy raportów.</span><span class="sxs-lookup"><span data-stu-id="8a165-129">Schedule a single report or a group of reports so that it is generated on a regular basis.</span></span> | [<span data-ttu-id="8a165-130">Generowanie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="8a165-130">Generate financial reports</span></span>](generate-financial-report.md) |

## <a name="features"></a><span data-ttu-id="8a165-131">Cechy i funkcje</span><span class="sxs-lookup"><span data-stu-id="8a165-131">Features</span></span>
<table>
<thead>
<tr>
<th><span data-ttu-id="8a165-132">Funkcja</span><span class="sxs-lookup"><span data-stu-id="8a165-132">Feature</span></span></th>
<th><span data-ttu-id="8a165-133">Opis</span><span class="sxs-lookup"><span data-stu-id="8a165-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="8a165-134">Elastyczność projektowania raportu</span><span class="sxs-lookup"><span data-stu-id="8a165-134">Report design flexibility</span></span></td>
<td><span data-ttu-id="8a165-135">Projektant raportów oferuje następujące opcje raportowania podczas projektowania raportu:</span><span class="sxs-lookup"><span data-stu-id="8a165-135">Report Designer provides the following reporting options when you design a report:</span></span>
<ul>
<li><span data-ttu-id="8a165-136">Zapisywanie kombinacji wymiarów i ich ponowne wykorzystywanie dla wielu raportów.</span><span class="sxs-lookup"><span data-stu-id="8a165-136">Save dimension combinations, and reuse the dimensions for multiple reports.</span></span></li>
<li><span data-ttu-id="8a165-137">Kontrolowanie sposobu formatowania i wyświetlania opisów wymiarów.</span><span class="sxs-lookup"><span data-stu-id="8a165-137">Control how dimension descriptions are formatted and displayed.</span></span></li>
<li><span data-ttu-id="8a165-138">Identyfikowanie kont lub wymiarów, które zostały pominięte w elementach podstawowych raportu.</span><span class="sxs-lookup"><span data-stu-id="8a165-138">Identify accounts or dimensions that have been omitted from report building blocks.</span></span></li>
<li><span data-ttu-id="8a165-139">Format nagłówków dla prognoz kroczących.</span><span class="sxs-lookup"><span data-stu-id="8a165-139">Format headers for rolling forecasts.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="8a165-140">Współpraca dotycząca raportu finansowego</span><span class="sxs-lookup"><span data-stu-id="8a165-140">Financial report collaboration</span></span></td>
<td><span data-ttu-id="8a165-141">Następujące funkcje pomagają w zarządzaniu wytwarzaniem i dystrybucją raportów:</span><span class="sxs-lookup"><span data-stu-id="8a165-141">The following features help you manage the generation and distribution of reports:</span></span>
<ul>
<li><span data-ttu-id="8a165-142">Planowanie raportów, tak aby były generowane automatycznie codziennie, co tydzień, co miesiąc lub co rok.</span><span class="sxs-lookup"><span data-stu-id="8a165-142">Schedule reports so that they are automatically generated on a daily, weekly, monthly, or annual basis.</span></span></li>
<li><span data-ttu-id="8a165-143">Eksportowanie do formatu XPS tylko do odczytu, który zapewnia lepsze zabezpieczenie dokumentu poprzez używanie podpisów cyfrowych.</span><span class="sxs-lookup"><span data-stu-id="8a165-143">Export to the read-only XPS format, which provides better document security through digital signatures.</span></span></li>
<li><span data-ttu-id="8a165-144">Eksportuj do arkusza programu Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="8a165-144">Export to a Microsoft Excel worksheet.</span></span></li>
<li><span data-ttu-id="8a165-145">Aby udostępnić raporty, można utworzyć wiadomości e-mail zawierające łącza do raportów.</span><span class="sxs-lookup"><span data-stu-id="8a165-145">To share reports, you can create email messages that contain links to the reports.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="8a165-146">Wyświetlanie interaktywnego raportu</span><span class="sxs-lookup"><span data-stu-id="8a165-146">Interactive report viewing</span></span></td>
<td><span data-ttu-id="8a165-147">Funkcje interaktywne pozwalają wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="8a165-147">Interactive features let you perform the following tasks:</span></span>
<ul>
<li><span data-ttu-id="8a165-148">Zmiana daty przeglądanego raportu.</span><span class="sxs-lookup"><span data-stu-id="8a165-148">Change the report date for the report that you're viewing.</span></span></li>
<li><span data-ttu-id="8a165-149">Zmiana waluty przeglądanego raportu.</span><span class="sxs-lookup"><span data-stu-id="8a165-149">Change the currency of the report that you're viewing.</span></span></li>
<li><span data-ttu-id="8a165-150">Wyświetlanie raportu w widoku podsumowania lub szczegółów.</span><span class="sxs-lookup"><span data-stu-id="8a165-150">View the report in either a summary view or a detailed view.</span></span></li>
<li><span data-ttu-id="8a165-151">Dodawanie filtrów wymiarów w celu ograniczenia zawartość raportu do określonego wymiaru lub kombinacji wymiarów.</span><span class="sxs-lookup"><span data-stu-id="8a165-151">Add dimension filters to limit the report content to a specific dimension or combination of dimensions.</span></span></li>
<li><span data-ttu-id="8a165-152">Dodawanie filtrów atrybutów w celu ograniczenia zawartość raportu do określonego atrybutu lub kombinacji atrybutów.</span><span class="sxs-lookup"><span data-stu-id="8a165-152">Add attribute filters to limit the report content to a specific attribute or combination of attributes.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="8a165-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8a165-153">Additional resources</span></span>
[<span data-ttu-id="8a165-154">Generowanie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="8a165-154">Generate financial reports</span></span>](generate-financial-report.md)
