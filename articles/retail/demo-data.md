---
title: "Układy ekranu danych demonstracyjnych w programie MPOS/CPOS"
description: "Ten temat zawiera informacje o układach ekranu zawartych w zestawie danych demonstracyjnych dla doświadczeń punktu sprzedaży w rozwiązaniu Microsoft Dynamics 365 for Retail."
author: zlinster
manager: AnnBe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: zlinster
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 797058bdbbdb63a08eb35034ffe3c913307f38df
ms.openlocfilehash: e812bb13c903e72e31e62effd0c70f9b9d62de55
ms.contentlocale: pl-pl
ms.lasthandoff: 03/06/2018

---

# <a name="demo-data-screen-layouts-in-mposcpos"></a><span data-ttu-id="65357-103">Układy ekranu danych demonstracyjnych w programie MPOS/CPOS</span><span class="sxs-lookup"><span data-stu-id="65357-103">Demo data screen layouts in MPOS/CPOS</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="65357-104">Ten temat zawiera informacje o układach ekranu zawartych w zestawie danych demonstracyjnych dla doświadczeń punktu sprzedaży w rozwiązaniu Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="65357-104">This topic provides information about the screen layouts that are included with the demo data set for the point of sale (POS) experiences in Microsoft Dynamics 365 for Retail.</span></span>

## <a name="overview"></a><span data-ttu-id="65357-105">Przegląd</span><span class="sxs-lookup"><span data-stu-id="65357-105">Overview</span></span>

<span data-ttu-id="65357-106">Przykładowe układy ekranu zawarte w danych demonstracyjnych programu Retail obejmują zawartość zoptymalizowaną dla różnych segmentów sprzedaży detalicznej, ról pracowników sklepu i urządzeń.</span><span class="sxs-lookup"><span data-stu-id="65357-106">The sample screen layouts that are included with Retail demo data provide content that is optimized for various retail segments, store worker roles, and devices.</span></span> <span data-ttu-id="65357-107">Jeden układ może zawierać kilka rozmiarów układu i kombinacji siatek przycisków, aby zapewnić możliwość obsługi, gdy pracownicy sklepu zmienią urządzenia i stacje.</span><span class="sxs-lookup"><span data-stu-id="65357-107">A single layout can contain several layout sizes and combinations of button grids, to help ensure coverage as store workers move between devices and stations.</span></span> <span data-ttu-id="65357-108">W tym temacie omówiono różnice między tymi układami, operacja, jakie udostępniają i ogólne zapewniane doświadczenia.</span><span class="sxs-lookup"><span data-stu-id="65357-108">This topic highlights the differences between these layouts, the operations that they provide, and the overall experiences that they deliver.</span></span>

![Układy danych demonstracyjnych działające między urządzeniami](../retail/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a><span data-ttu-id="65357-110">Struktura identyfikatora układu ekranu</span><span class="sxs-lookup"><span data-stu-id="65357-110">Anatomy of a screen layout ID</span></span>

<span data-ttu-id="65357-111">Aby znaleźć układy ekranu w rozwiązaniu Retail, przejdź do **Retail** > **Ustawienia kanału** > **Ustawienia punktu sprzedaży** > **Punkt sprzedaży** > **Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="65357-111">To find screen layouts in Retail, go to **Retail** > **Channel setup** > **POS setup** > **POS** > **Screen layouts**.</span></span>

![Strona układów ekranu w rozwiązaniu Retail](../retail/media/demo-screen-layouts-fig-2-1.png)

<span data-ttu-id="65357-113">Identyfikatory układu ekranu mogą mieć maksymalnie 10 znaków.</span><span class="sxs-lookup"><span data-stu-id="65357-113">Screen layout IDs can have a maximum of 10 characters.</span></span> <span data-ttu-id="65357-114">Identyfikator to ciąg składający się z trzech informacji w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="65357-114">The ID is a string that consists of three pieces of information, in this order:</span></span>

1. <span data-ttu-id="65357-115">Firma</span><span class="sxs-lookup"><span data-stu-id="65357-115">Company</span></span>
2. <span data-ttu-id="65357-116">Wersja układu</span><span class="sxs-lookup"><span data-stu-id="65357-116">Layout version</span></span>
3. <span data-ttu-id="65357-117">Osoba</span><span class="sxs-lookup"><span data-stu-id="65357-117">Persona</span></span>

### <a name="company"></a><span data-ttu-id="65357-118">Firma</span><span class="sxs-lookup"><span data-stu-id="65357-118">Company</span></span>

| <span data-ttu-id="65357-119">List</span><span class="sxs-lookup"><span data-stu-id="65357-119">Letter</span></span> | <span data-ttu-id="65357-120">Firma</span><span class="sxs-lookup"><span data-stu-id="65357-120">Company</span></span>         |
|--------|-----------------|
| <span data-ttu-id="65357-121">A</span><span class="sxs-lookup"><span data-stu-id="65357-121">A</span></span>      | <span data-ttu-id="65357-122">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="65357-122">Adventure Works</span></span> |
| <span data-ttu-id="65357-123">F</span><span class="sxs-lookup"><span data-stu-id="65357-123">F</span></span>      | <span data-ttu-id="65357-124">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="65357-124">Fabrikam</span></span>        |
| <span data-ttu-id="65357-125">F</span><span class="sxs-lookup"><span data-stu-id="65357-125">C</span></span>      | <span data-ttu-id="65357-126">Contoso</span><span class="sxs-lookup"><span data-stu-id="65357-126">Contoso</span></span>         |

### <a name="layout-version"></a><span data-ttu-id="65357-127">Wersja układu</span><span class="sxs-lookup"><span data-stu-id="65357-127">Layout version</span></span>

| <span data-ttu-id="65357-128">Numer wersji</span><span class="sxs-lookup"><span data-stu-id="65357-128">Version number</span></span> | <span data-ttu-id="65357-129">opis</span><span class="sxs-lookup"><span data-stu-id="65357-129">Description</span></span>                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| <span data-ttu-id="65357-130">3</span><span class="sxs-lookup"><span data-stu-id="65357-130">3</span></span>              | <span data-ttu-id="65357-131">Wersja podstawowa, która obsługuje wiele ekranów dla różnych urządzeń i współczynników proporcji</span><span class="sxs-lookup"><span data-stu-id="65357-131">The base version that supports multiple screen sizes for various devices and aspect ratios</span></span> |
| <span data-ttu-id="65357-132">3.1</span><span class="sxs-lookup"><span data-stu-id="65357-132">3.1</span></span>            | <span data-ttu-id="65357-133">Wersja podstawowa, która oferuje dodatkową obsługę panelu **Rekomendowane produkty**</span><span class="sxs-lookup"><span data-stu-id="65357-133">The base version that has additional support for the **Recommended products** panel</span></span>        |

### <a name="persona"></a><span data-ttu-id="65357-134">Osoba</span><span class="sxs-lookup"><span data-stu-id="65357-134">Persona</span></span>

| <span data-ttu-id="65357-135">Skrót</span><span class="sxs-lookup"><span data-stu-id="65357-135">Abbreviation</span></span> | <span data-ttu-id="65357-136">Osoba</span><span class="sxs-lookup"><span data-stu-id="65357-136">Persona</span></span>       | <span data-ttu-id="65357-137">Zawartość</span><span class="sxs-lookup"><span data-stu-id="65357-137">Contents</span></span> |
|--------------|---------------|----------|
| <span data-ttu-id="65357-138">CSH</span><span class="sxs-lookup"><span data-stu-id="65357-138">CSH</span></span>          | <span data-ttu-id="65357-139">Kasjer</span><span class="sxs-lookup"><span data-stu-id="65357-139">Cashier</span></span>       | <span data-ttu-id="65357-140">Układy kasjera zawierają wszystkie operacje dotyczące transakcji, takie jak zamówienia odbiorców, zwroty, rabaty, unieważnienia i karty upominkowe.</span><span class="sxs-lookup"><span data-stu-id="65357-140">Cashier layouts include all transaction-related operations, such as customer orders, returns, discounts, voids, and gift cards.</span></span> <span data-ttu-id="65357-141">Te układy zawierają także codzienne zadania do zarządzania zapasami, takie jak sprawdzenia ceny, wyszukiwanie zapasów i inwentaryzację.</span><span class="sxs-lookup"><span data-stu-id="65357-141">These layouts also include daily tasks for inventory management, such price checks, inventory lookups, and stock counts.</span></span> <span data-ttu-id="65357-142">Dostępne jest także podstawowe zarządzanie zmianami dla kwot początkowych, zawieszania zmian i zegara.</span><span class="sxs-lookup"><span data-stu-id="65357-142">Basic shift management is also provided for start amounts, suspending shifts, and time clock.</span></span> |
| <span data-ttu-id="65357-143">MGR</span><span class="sxs-lookup"><span data-stu-id="65357-143">MGR</span></span>          | <span data-ttu-id="65357-144">Kierownik sklepu</span><span class="sxs-lookup"><span data-stu-id="65357-144">Store Manager</span></span> | <span data-ttu-id="65357-145">Układy kierownika sklepu obejmują wszystkie operacje dotyczące transakcji dostępne w układach Kasjer, ale także zmiany podatków.</span><span class="sxs-lookup"><span data-stu-id="65357-145">Store Manager layouts include all transaction-related operations that are found in the Cashier layouts but also include tax overrides.</span></span> <span data-ttu-id="65357-146">Te układy zawierają także codzienne zadania do zarządzania zapasami, takie jak sprawdzenia ceny, wyszukiwanie zapasów i inwentaryzację.</span><span class="sxs-lookup"><span data-stu-id="65357-146">These layouts also include daily tasks for inventory management, such as price checks, inventory lookups, and stock counts.</span></span> <span data-ttu-id="65357-147">Dostępne jest zarządzanie zmianami na potrzeby rozpoczynania zawieszania i zamykania zmiany.</span><span class="sxs-lookup"><span data-stu-id="65357-147">Shift management is provided for starting, suspending, and closing shifts.</span></span> <span data-ttu-id="65357-148">Ponadto układy zawierają operacje z użyciem szuflady dla wpisów, usunięć, deklaracji środków płatniczych oraz przekazywania pieniędzy do sejfu i banku.</span><span class="sxs-lookup"><span data-stu-id="65357-148">Additionally, the layouts include drawer operations for entries, removals, tender declarations, and safe and bank drops.</span></span> <span data-ttu-id="65357-149">I wreszcie układy obejmują dostęp do raportu o wynikach i umożliwiają drukowanie częściowych i końcowych raportów sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="65357-149">Finally, these layouts include access to performance reports, and enable X and Z reports to be printed.</span></span> |
| <span data-ttu-id="65357-150">STK</span><span class="sxs-lookup"><span data-stu-id="65357-150">STK</span></span>          | <span data-ttu-id="65357-151">Magazynier</span><span class="sxs-lookup"><span data-stu-id="65357-151">Stock Clerk</span></span>   | <span data-ttu-id="65357-152">Układy Magazynier są zoptymalizowane pod kątem zarządzania zapasami.</span><span class="sxs-lookup"><span data-stu-id="65357-152">Stock Clerk layouts are optimized for inventory management.</span></span> <span data-ttu-id="65357-153">Umożliwiają dostęp do codziennych zadań sprawdzania ceny, wyszukiwania zapasów, pobieranie i przyjęcie, inwentaryzację i dekompletację zestawu.</span><span class="sxs-lookup"><span data-stu-id="65357-153">They include access to daily tasks for price checks, inventory lookups, picking and receiving, stock counts, and kit disassembly.</span></span> <span data-ttu-id="65357-154">Układy te udostępniają podstawowe operacje zmiany dla zegara i zawieszania zmian.</span><span class="sxs-lookup"><span data-stu-id="65357-154">These layouts also provide basic shift operations for time clock and suspending shifts.</span></span> <span data-ttu-id="65357-155">Mimo że te układy są przeznaczone głównie do zadań zaplecza, magazynierzy mogą wykonywać te same operacje co kasjerzy dla ekranów transakcji.</span><span class="sxs-lookup"><span data-stu-id="65357-155">Although these layouts are intended mainly for back-office tasks, stock clerks have the same operations as cashiers for transaction screens.</span></span> |

### <a name="example-layout"></a><span data-ttu-id="65357-156">Układ przykładowy</span><span class="sxs-lookup"><span data-stu-id="65357-156">Example layout</span></span>

<span data-ttu-id="65357-157">Poniżej przedstawiono przykładowy identyfikator układu ekranu dla firmy Fabrikam, wersja 3 układu i stanowiska Kierownik sklepu:</span><span class="sxs-lookup"><span data-stu-id="65357-157">Here is an example of a screen layout ID for the Fabrikam company, layout version 3, and the Store Manager persona:</span></span>

<span data-ttu-id="65357-158">F3MGR</span><span class="sxs-lookup"><span data-stu-id="65357-158">F3MGR</span></span>

<span data-ttu-id="65357-159">Poniższa ilustracja przedstawia przykładowy ekran powitalny kierownika sklepu firmy Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="65357-159">The following illustration shows an example of the Welcome screen for a Fabrikam store manager.</span></span>

![Ekran powitalny dla kierownika sklepu firmy Fabrikam](../retail/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a><span data-ttu-id="65357-161">Rozmiary układów</span><span class="sxs-lookup"><span data-stu-id="65357-161">Layout sizes</span></span>

### <a name="full-vs-compact-layouts"></a><span data-ttu-id="65357-162">Układ pełny a kompaktowy</span><span class="sxs-lookup"><span data-stu-id="65357-162">Full vs. compact layouts</span></span>

<span data-ttu-id="65357-163">Układ ekranu może mieć konfiguracje dla urządzeń pełnoekranowych i kompaktowych.</span><span class="sxs-lookup"><span data-stu-id="65357-163">A screen layout can have configurations for both full devices and compact devices.</span></span> <span data-ttu-id="65357-164">Dlatego można przypisać użytkownika do jednego układu ekranu, który będzie działał w urządzeniach o różnych rozmiarach i typach znajdujących się w sklepie.</span><span class="sxs-lookup"><span data-stu-id="65357-164">Therefore, a user can be assigned to a single screen layout that will work across various sizes and form factors in the store.</span></span>

- <span data-ttu-id="65357-165">**Modern POS - Pełna wersja** — Pełne układy zazwyczaj najlepiej nadają się do większych ekranów, takich jak w monitorach komputerów stacjonarnych i tabletach.</span><span class="sxs-lookup"><span data-stu-id="65357-165">**Modern POS - Full** – Typically, full layouts are best used for larger displays, such as desktop computer monitors or tablets.</span></span> <span data-ttu-id="65357-166">Użytkownicy mogą wybrać elementy interfejsu użytkownika zawarte w układzie, określić rozmiar i umieszczenie tych elementów oraz skonfigurować ich szczegółowe właściwości.</span><span class="sxs-lookup"><span data-stu-id="65357-166">Users can select the UI elements that the layout includes, specify the size and placement of those elements, and configure their detailed properties.</span></span> <span data-ttu-id="65357-167">Układy pełne obsługują konfiguracje poziome i pionowe.</span><span class="sxs-lookup"><span data-stu-id="65357-167">Full layouts support both portrait and landscape configurations.</span></span>
- <span data-ttu-id="65357-168">**Modern POS - Wersja kompaktowa** — Układy kompaktowe zazwyczaj najlepiej nadają się do telefonów lub małych tabletów.</span><span class="sxs-lookup"><span data-stu-id="65357-168">**Modern POS - Compact** – Typically, compact layouts are best used for phones or small tablets.</span></span> <span data-ttu-id="65357-169">Możliwości projektowania są ograniczone do urządzeń kompaktowych.</span><span class="sxs-lookup"><span data-stu-id="65357-169">Design possibilities are limited for compact devices.</span></span> <span data-ttu-id="65357-170">Użytkownicy mogą konfigurować kolumny i pola okienka pokwitowania i sum.</span><span class="sxs-lookup"><span data-stu-id="65357-170">Users can configure the columns and fields for the receipt pane and the totals pane.</span></span>

### <a name="screen-resolutions-that-are-provided"></a><span data-ttu-id="65357-171">Dostępne rozdzielczości ekranu</span><span class="sxs-lookup"><span data-stu-id="65357-171">Screen resolutions that are provided</span></span>

<span data-ttu-id="65357-172">Poniższa tabela przedstawia rozmiary układu dostępne dla typowych rozdzielczości ekranu.</span><span class="sxs-lookup"><span data-stu-id="65357-172">The following table shows the layout sizes that are provided for typical screen resolutions.</span></span>

| <span data-ttu-id="65357-173">Typ układu</span><span class="sxs-lookup"><span data-stu-id="65357-173">Layout type</span></span> | <span data-ttu-id="65357-174">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="65357-174">Resolution</span></span> | <span data-ttu-id="65357-175">Współczynnik proporcji</span><span class="sxs-lookup"><span data-stu-id="65357-175">Aspect ratio</span></span> | <span data-ttu-id="65357-176">Docelowy wyświetlacz</span><span class="sxs-lookup"><span data-stu-id="65357-176">Target display</span></span>          |
|-------------|------------|--------------|-------------------------|
| <span data-ttu-id="65357-177">Kompaktowanie\*</span><span class="sxs-lookup"><span data-stu-id="65357-177">Compact\*</span></span>   | <span data-ttu-id="65357-178">480 × 853</span><span class="sxs-lookup"><span data-stu-id="65357-178">480 × 853</span></span>  | <span data-ttu-id="65357-179">16:9</span><span class="sxs-lookup"><span data-stu-id="65357-179">16:9</span></span>         | <span data-ttu-id="65357-180">Telefony</span><span class="sxs-lookup"><span data-stu-id="65357-180">Phones</span></span>                  |
| <span data-ttu-id="65357-181">Pełny</span><span class="sxs-lookup"><span data-stu-id="65357-181">Full</span></span>        | <span data-ttu-id="65357-182">1024 × 768</span><span class="sxs-lookup"><span data-stu-id="65357-182">1024 × 768</span></span> | <span data-ttu-id="65357-183">4:3</span><span class="sxs-lookup"><span data-stu-id="65357-183">4:3</span></span>          | <span data-ttu-id="65357-184">Tablety</span><span class="sxs-lookup"><span data-stu-id="65357-184">Tablets</span></span>                 |
| <span data-ttu-id="65357-185">Pełny\*</span><span class="sxs-lookup"><span data-stu-id="65357-185">Full\*</span></span>      | <span data-ttu-id="65357-186">1280 × 720</span><span class="sxs-lookup"><span data-stu-id="65357-186">1280 × 720</span></span> | <span data-ttu-id="65357-187">16:9</span><span class="sxs-lookup"><span data-stu-id="65357-187">16:9</span></span>         | <span data-ttu-id="65357-188">Tablety</span><span class="sxs-lookup"><span data-stu-id="65357-188">Tablets</span></span>                 |
| <span data-ttu-id="65357-189">Pełny</span><span class="sxs-lookup"><span data-stu-id="65357-189">Full</span></span>        | <span data-ttu-id="65357-190">1366 × 768</span><span class="sxs-lookup"><span data-stu-id="65357-190">1366 × 768</span></span> | <span data-ttu-id="65357-191">16:9</span><span class="sxs-lookup"><span data-stu-id="65357-191">16:9</span></span>         | <span data-ttu-id="65357-192">Tablety, większe ekrany</span><span class="sxs-lookup"><span data-stu-id="65357-192">Tablets, larger screens</span></span> |
| <span data-ttu-id="65357-193">Pełny</span><span class="sxs-lookup"><span data-stu-id="65357-193">Full</span></span>        | <span data-ttu-id="65357-194">1440 × 960</span><span class="sxs-lookup"><span data-stu-id="65357-194">1440 × 960</span></span> | <span data-ttu-id="65357-195">3:2</span><span class="sxs-lookup"><span data-stu-id="65357-195">3:2</span></span>          | <span data-ttu-id="65357-196">Tablety, większe ekrany</span><span class="sxs-lookup"><span data-stu-id="65357-196">Tablets, larger screens</span></span> |

<span data-ttu-id="65357-197">\* Te dodatkowe rozmiary układów są dostępne tylko w układach firmy Adventure Works i Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="65357-197">\* These additional layout sizes are available only in Adventure Works and Fabrikam layouts.</span></span>


>[!TIP]
> <span data-ttu-id="65357-198">Punkt sprzedaży automatycznie wybiera rozmiary układu na podstawie najbliższego rozmiaru dostępnego dla rozdzielczości ekranu okna bieżącej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="65357-198">POS automatically selects layout sizes, based on the closest size that is available for the screen resolution of the current app window.</span></span> <span data-ttu-id="65357-199">Aby znaleźć aktualnie używany identyfikator układu ekranu i rozdzielczość układu, w module Retail Modern POS (MPOS) lub Retail Cloud POS (CPOS) otwórz stronę **Ustawienia** i sprawdź informacje w sekcji **Informacje o sesji**.</span><span class="sxs-lookup"><span data-stu-id="65357-199">To find the screen layout ID and layout resolution that are currently used, in Retail Modern POS (MPOS) or Retail Cloud POS (CPOS), open the **Settings** page, and look in the **Session information** section.</span></span> <span data-ttu-id="65357-200">Możesz także zobaczyć rzeczywistą rozdzielczość okna dla bieżącej aplikacji lub ramki przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="65357-200">You can also see the actual window resolution for your current application or browser frame.</span></span> <span data-ttu-id="65357-201">Po uzyskaniu tych informacji można znaleźć źródło zawartości układu w rozwiązaniu Retail, przechodząc do okna **Ustawienia kanału** > **Ustawienia punktu sprzedaży** > **Punkt sprzedaży** > **Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="65357-201">After you have this information, you can find the source of the layout content in Retail by going to **Channel setup** > **POS setup** > **POS** > **Screen layouts**.</span></span>


![Układy ekranu i rozdzielczości/rozmiary układu w rozwiązaniu Retail i punkcie sprzedaży](../retail/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a><span data-ttu-id="65357-203">Firmy i marki</span><span class="sxs-lookup"><span data-stu-id="65357-203">Companies and brands</span></span>

<span data-ttu-id="65357-204">Każda firma fikcyjna odnosi się do innego segmentu sprzedaży detalicznej i zawiera katalogi produktów dostosowane do rynku firmy.</span><span class="sxs-lookup"><span data-stu-id="65357-204">Each fictitious company is targeted to a different retail segment and includes product catalogs that are tuned for the company's market.</span></span> <span data-ttu-id="65357-205">Każda firma stosuje unikatowe elementy wizualne marki związane z jej produktami.</span><span class="sxs-lookup"><span data-stu-id="65357-205">Each company has a unique visual brand that accompanies its products.</span></span> <span data-ttu-id="65357-206">Elementy dotyczące marki obejmują kolor akcentu, ciemny lub jasny motyw i powiązane zdjęcia, zapewniające realizm doświadczeń.</span><span class="sxs-lookup"><span data-stu-id="65357-206">Branding elements include the accent color, dark or light theme, and accompanying photographs that provide realistic experiences.</span></span>

### <a name="company-segment-and-visual-characteristics"></a><span data-ttu-id="65357-207">Segment firmy i charakterystyka wizualna</span><span class="sxs-lookup"><span data-stu-id="65357-207">Company segment and visual characteristics</span></span>

| <span data-ttu-id="65357-208">Firma</span><span class="sxs-lookup"><span data-stu-id="65357-208">Company</span></span>         | <span data-ttu-id="65357-209">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="65357-209">Location</span></span> | <span data-ttu-id="65357-210">Segment</span><span class="sxs-lookup"><span data-stu-id="65357-210">Segment</span></span>        | <span data-ttu-id="65357-211">Akcent</span><span class="sxs-lookup"><span data-stu-id="65357-211">Accent</span></span> | <span data-ttu-id="65357-212">Motyw</span><span class="sxs-lookup"><span data-stu-id="65357-212">Theme</span></span> |
|-----------------|----------|----------------|--------|-------|
| <span data-ttu-id="65357-213">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="65357-213">Adventure Works</span></span> | <span data-ttu-id="65357-214">Seattle</span><span class="sxs-lookup"><span data-stu-id="65357-214">Seattle</span></span>  | <span data-ttu-id="65357-215">Artykuły sportowe</span><span class="sxs-lookup"><span data-stu-id="65357-215">Sporting Goods</span></span> | <span data-ttu-id="65357-216">Niebieski</span><span class="sxs-lookup"><span data-stu-id="65357-216">Blue</span></span>   | <span data-ttu-id="65357-217">Ciemny</span><span class="sxs-lookup"><span data-stu-id="65357-217">Dark</span></span>  |
| <span data-ttu-id="65357-218">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="65357-218">Fabrikam</span></span>        | <span data-ttu-id="65357-219">Houston</span><span class="sxs-lookup"><span data-stu-id="65357-219">Houston</span></span>  | <span data-ttu-id="65357-220">Moda</span><span class="sxs-lookup"><span data-stu-id="65357-220">Fashion</span></span>        | <span data-ttu-id="65357-221">Zielony</span><span class="sxs-lookup"><span data-stu-id="65357-221">Green</span></span>  | <span data-ttu-id="65357-222">Delikatny</span><span class="sxs-lookup"><span data-stu-id="65357-222">Light</span></span> |
| <span data-ttu-id="65357-223">Contoso</span><span class="sxs-lookup"><span data-stu-id="65357-223">Contoso</span></span>         | <span data-ttu-id="65357-224">Boston</span><span class="sxs-lookup"><span data-stu-id="65357-224">Boston</span></span>   | <span data-ttu-id="65357-225">Elektronika</span><span class="sxs-lookup"><span data-stu-id="65357-225">Electronics</span></span>    | <span data-ttu-id="65357-226">Czerwony</span><span class="sxs-lookup"><span data-stu-id="65357-226">Red</span></span>    | <span data-ttu-id="65357-227">Ciemny</span><span class="sxs-lookup"><span data-stu-id="65357-227">Dark</span></span>  |


>[!NOTE]
> <span data-ttu-id="65357-228">Adventure Works i Fabrikam to dwie marki flagowe.</span><span class="sxs-lookup"><span data-stu-id="65357-228">Adventure Works and Fabrikam are the two flagship brands.</span></span> <span data-ttu-id="65357-229">Firma Contoso jest dostępna, ale nie dostarczono wszystkich układów.</span><span class="sxs-lookup"><span data-stu-id="65357-229">Contoso is available, but not all layouts have been provided.</span></span>


<span data-ttu-id="65357-230">Poniższe ilustracje przedstawiają przykłady strony powitalnej i strony transakcji dla trzech fikcyjnych firm.</span><span class="sxs-lookup"><span data-stu-id="65357-230">The following illustrations show examples of the welcome page and transaction page for the three fictitious companies.</span></span>

### <a name="adventure-works"></a><span data-ttu-id="65357-231">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="65357-231">Adventure Works</span></span>

![Stron powitalna danych demonstracyjnych dla firmy Adventure Works](../retail/media/demo-screen-layouts-fig-4-1a.png)

![Stron transakcji danych demonstracyjnych dla firmy Adventure Works](../retail/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a><span data-ttu-id="65357-234">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="65357-234">Fabrikam</span></span>

![Stron powitalna danych demonstracyjnych dla firmy Fabrikam](../retail/media/demo-screen-layouts-fig-4-2a.png)

![Stron transakcji danych demonstracyjnych dla firmy Fabrikam](../retail/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a><span data-ttu-id="65357-237">Contoso</span><span class="sxs-lookup"><span data-stu-id="65357-237">Contoso</span></span>

![Układy danych demonstracyjnych dla firmy Contoso](../retail/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a><span data-ttu-id="65357-239">Macierz logowania użytkowników</span><span class="sxs-lookup"><span data-stu-id="65357-239">User sign in matrix</span></span>

<span data-ttu-id="65357-240">Użytkownikom udostępniono różne układy ekranu.</span><span class="sxs-lookup"><span data-stu-id="65357-240">Users have been provided for the various screen layouts.</span></span> <span data-ttu-id="65357-241">Korzystając z poniższej tabeli, można uzyskać dostęp do dowolnego ekranu.</span><span class="sxs-lookup"><span data-stu-id="65357-241">By using the following table, you should be able to access any of the screens.</span></span> <span data-ttu-id="65357-242">Wystarczy zalogować się, używając odpowiedniego identyfikatora operatora.</span><span class="sxs-lookup"><span data-stu-id="65357-242">Just sign in by using an appropriate operator ID.</span></span>

| <span data-ttu-id="65357-243">Firma</span><span class="sxs-lookup"><span data-stu-id="65357-243">Company</span></span>         | <span data-ttu-id="65357-244">Identyfikator układu ekranu</span><span class="sxs-lookup"><span data-stu-id="65357-244">Screen layout ID</span></span> | <span data-ttu-id="65357-245">Osoba</span><span class="sxs-lookup"><span data-stu-id="65357-245">Persona</span></span>          | <span data-ttu-id="65357-246">Identyfikatory operatora</span><span class="sxs-lookup"><span data-stu-id="65357-246">Operator IDs</span></span>           |
|-----------------|------------------|---------------   |------------------------|
| <span data-ttu-id="65357-247">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="65357-247">Adventure Works</span></span> | <span data-ttu-id="65357-248">A3MGR</span><span class="sxs-lookup"><span data-stu-id="65357-248">A3MGR</span></span>            | <span data-ttu-id="65357-249">Kierownik sklepu</span><span class="sxs-lookup"><span data-stu-id="65357-249">Store Manager</span></span>    | <span data-ttu-id="65357-250">000154, 000137, 000073</span><span class="sxs-lookup"><span data-stu-id="65357-250">000154, 000137, 000073</span></span> |
| <span data-ttu-id="65357-251">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="65357-251">Adventure Works</span></span> | <span data-ttu-id="65357-252">A3CSH</span><span class="sxs-lookup"><span data-stu-id="65357-252">A3CSH</span></span>            | <span data-ttu-id="65357-253">Kasjer</span><span class="sxs-lookup"><span data-stu-id="65357-253">Cashier</span></span>          | <span data-ttu-id="65357-254">000150, 000175, 000165</span><span class="sxs-lookup"><span data-stu-id="65357-254">000150, 000175, 000165</span></span> |
| <span data-ttu-id="65357-255">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="65357-255">Adventure Works</span></span> | <span data-ttu-id="65357-256">A3STK</span><span class="sxs-lookup"><span data-stu-id="65357-256">A3STK</span></span>            | <span data-ttu-id="65357-257">Magazynier</span><span class="sxs-lookup"><span data-stu-id="65357-257">Stock Clerk</span></span>      | <span data-ttu-id="65357-258">000155, 000181, 000152</span><span class="sxs-lookup"><span data-stu-id="65357-258">000155, 000181, 000152</span></span> |
| <span data-ttu-id="65357-259">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="65357-259">Fabrikam</span></span>        | <span data-ttu-id="65357-260">F3MGR</span><span class="sxs-lookup"><span data-stu-id="65357-260">F3MGR</span></span>            | <span data-ttu-id="65357-261">Kierownik sklepu</span><span class="sxs-lookup"><span data-stu-id="65357-261">Store Manager</span></span>    | <span data-ttu-id="65357-262">000160, 000168, 000163</span><span class="sxs-lookup"><span data-stu-id="65357-262">000160, 000168, 000163</span></span> |
| <span data-ttu-id="65357-263">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="65357-263">Fabrikam</span></span>        | <span data-ttu-id="65357-264">F3CSH</span><span class="sxs-lookup"><span data-stu-id="65357-264">F3CSH</span></span>            | <span data-ttu-id="65357-265">Kasjer</span><span class="sxs-lookup"><span data-stu-id="65357-265">Cashier</span></span>          | <span data-ttu-id="65357-266">000161, 000113, 000114</span><span class="sxs-lookup"><span data-stu-id="65357-266">000161, 000113, 000114</span></span> |
| <span data-ttu-id="65357-267">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="65357-267">Fabrikam</span></span>        | <span data-ttu-id="65357-268">F3STK</span><span class="sxs-lookup"><span data-stu-id="65357-268">F3STK</span></span>            | <span data-ttu-id="65357-269">Magazynier</span><span class="sxs-lookup"><span data-stu-id="65357-269">Stock Clerk</span></span>      | <span data-ttu-id="65357-270">000164, 000112, 000123</span><span class="sxs-lookup"><span data-stu-id="65357-270">000164, 000112, 000123</span></span> |
| <span data-ttu-id="65357-271">Contoso</span><span class="sxs-lookup"><span data-stu-id="65357-271">Contoso</span></span>         | <span data-ttu-id="65357-272">C3MGR</span><span class="sxs-lookup"><span data-stu-id="65357-272">C3MGR</span></span>            | <span data-ttu-id="65357-273">Kierownik sklepu</span><span class="sxs-lookup"><span data-stu-id="65357-273">Store Manager</span></span>    | <span data-ttu-id="65357-274">000100, 000111</span><span class="sxs-lookup"><span data-stu-id="65357-274">000100, 000111</span></span>         |
| <span data-ttu-id="65357-275">Contoso</span><span class="sxs-lookup"><span data-stu-id="65357-275">Contoso</span></span>         | <span data-ttu-id="65357-276">C3CSH</span><span class="sxs-lookup"><span data-stu-id="65357-276">C3CSH</span></span>            | <span data-ttu-id="65357-277">Kasjer</span><span class="sxs-lookup"><span data-stu-id="65357-277">Cashier</span></span>          | <span data-ttu-id="65357-278">000110, 000120</span><span class="sxs-lookup"><span data-stu-id="65357-278">000110, 000120</span></span>         |
| <span data-ttu-id="65357-279">Contoso</span><span class="sxs-lookup"><span data-stu-id="65357-279">Contoso</span></span>         | <span data-ttu-id="65357-280">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="65357-280">Not applicable</span></span>   | <span data-ttu-id="65357-281">Magazynier</span><span class="sxs-lookup"><span data-stu-id="65357-281">Stock Clerk</span></span>      | <span data-ttu-id="65357-282">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="65357-282">Not applicable</span></span>         |


>[!TIP]
> <span data-ttu-id="65357-283">Aby uzyskać najlepsze wyniki, uaktywnij kasę w odpowiedniej lokalizacji sklepu i ustaw firmę na dotyczącą osoby, której konta chcesz używać po zalogowaniu.</span><span class="sxs-lookup"><span data-stu-id="65357-283">For best results, activate a register in the corresponding store location, and set the company to the company of the persona that you plan to use when you sign in.</span></span> <span data-ttu-id="65357-284">Zapewnia to zgodność profilu wizualnego i obrazów marki z doświadczeniem.</span><span class="sxs-lookup"><span data-stu-id="65357-284">In this way, you help guarantee that the visual profile and branding images are aligned across the experience.</span></span> <span data-ttu-id="65357-285">Jeżeli na przykład chcesz zobaczyć układ Fabrikam dla kasjera, uaktywnij kasę w sklepie w Houston.</span><span class="sxs-lookup"><span data-stu-id="65357-285">For example, if you're interested in seeing a Fabrikam layout for a cashier, you should activate a register in the Houston store.</span></span>


<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail > Channel setup > POS setup > POS > Images**. -->

<!-- ![Images in Dynamics 365 for Retail](../retail/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../retail/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->

