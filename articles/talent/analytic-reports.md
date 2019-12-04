---
title: Używanie raportów analitycznych w aplikacji Attract
description: W tym temacie opisano raporty analityczne dotyczące szczegółowego procesu zatrudniania w aplikacji Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 4ae608bbca111313d8c77e63f6a7a95813f6e5cd
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2019
ms.locfileid: "2833238"
---
# <a name="use-analytic-reports-in-attract"></a><span data-ttu-id="b2d14-103">Używanie raportów analitycznych w aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="b2d14-103">Use analytic reports in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b2d14-104">Raporty analityczne w aplikacji Microsoft Dynamics 365 Talent: Attract oferują gotowe rozwiązanie (OOTB) do analizy danych w procesie zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="b2d14-104">Analytic reports in Microsoft Dynamics 365 Talent: Attract provide an out-of-the-box (OOTB) solution for hiring process insights.</span></span> <span data-ttu-id="b2d14-105">Dostępne są następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="b2d14-105">Availabe features include:</span></span>

- <span data-ttu-id="b2d14-106">**Analizy funkcji:** kliknij kartę **Analizy** w obszarze zadania, aby zobaczyć dane dotyczące kandydata.</span><span class="sxs-lookup"><span data-stu-id="b2d14-106">**Job analytics:** Click the **Analytics** tab within a job for metrics on the job's applicants.</span></span>
- <span data-ttu-id="b2d14-107">**Centrum analiz:** kliknij pozycję **analizy** w lewym okienku nawigacyjnym, aby uzyskać zagregowane dane w ramach zadań.</span><span class="sxs-lookup"><span data-stu-id="b2d14-107">**Analytics hub:** Click **Analytics** on the left navigation for aggregated metrics across jobs.</span></span>
- <span data-ttu-id="b2d14-108">**Zabezpieczenia na poziomie użytkownika** — dostęp do raportów jest kontrolowany przez Attract [rola](security-attract.md) i rolę uczestnika procesu rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="b2d14-108">**User-specific security:** Access to reports is controlled by Attract [role](security-attract.md) and job participant role.</span></span>
- <span data-ttu-id="b2d14-109">**Filtrowanie krzyżowe:** kliknij opcję elementy wizualne w raporcie, aby wyświetlić inne dane filtrowane według wybranych danych.</span><span class="sxs-lookup"><span data-stu-id="b2d14-109">**Cross-filtering:** Click visuals within a report to view other metrics filtered by selected data.</span></span>

>[!NOTE] 
>- <span data-ttu-id="b2d14-110">Ta funkcja jest obecnie w [wersjach zapoznawczych](access-preview-feature.md).</span><span class="sxs-lookup"><span data-stu-id="b2d14-110">This feature is currently in [preview](access-preview-feature.md).</span></span> <span data-ttu-id="b2d14-111">Aby go wypróbować, należy posiadać [**Dodatek kompleksowej obsługi rekrutacji**](attract-comprehensive-hiring.md).</span><span class="sxs-lookup"><span data-stu-id="b2d14-111">To try it, you must have the [**Comprehensive Hiring Add-On**](attract-comprehensive-hiring.md).</span></span>
>- <span data-ttu-id="b2d14-112">Wszystkie publiczne raporty poglądów są wyświetlane w języku angielskim.</span><span class="sxs-lookup"><span data-stu-id="b2d14-112">All public preview reports are displayed in English.</span></span>
>- <span data-ttu-id="b2d14-113">Raporty są odświeżane co 3 godziny.</span><span class="sxs-lookup"><span data-stu-id="b2d14-113">Reports refresh every 3 hours.</span></span> <span data-ttu-id="b2d14-114">Godzina ostatniego odświeżania (w lokalnej strefie czasowej) znajduje się u góry raportu.</span><span class="sxs-lookup"><span data-stu-id="b2d14-114">The last refresh time (in the local timezone) is located at the top of the report.</span></span> <span data-ttu-id="b2d14-115">Czasy odświeżania są podane w przybliżeniu i zależą od ilości danych oraz obciążenia pracą zasobów w Twoim regionie.</span><span class="sxs-lookup"><span data-stu-id="b2d14-115">Refresh times are an approximation and vary based on data volume and resource load in your region.</span></span>

## <a name="job-analytics"></a><span data-ttu-id="b2d14-116">Analizy funkcji</span><span class="sxs-lookup"><span data-stu-id="b2d14-116">Job Analytics</span></span>

<span data-ttu-id="b2d14-117">Raporty Analiza funkcji pokazują migawkę procesu rekrutacji na funkcję.</span><span class="sxs-lookup"><span data-stu-id="b2d14-117">Job Analytics reports are a snapshot of the hiring process for a job.</span></span>  <span data-ttu-id="b2d14-118">Kluczowe wskaźniki obejmują:</span><span class="sxs-lookup"><span data-stu-id="b2d14-118">Key metrics include:</span></span>

- <span data-ttu-id="b2d14-119">Aktywni kandydaci według etapów</span><span class="sxs-lookup"><span data-stu-id="b2d14-119">Active applicants by stage</span></span>
- <span data-ttu-id="b2d14-120">Źródła kandydatów</span><span class="sxs-lookup"><span data-stu-id="b2d14-120">Applicant source</span></span>
- <span data-ttu-id="b2d14-121">Typ kandydata (wewnętrzny lub zewnętrzny)</span><span class="sxs-lookup"><span data-stu-id="b2d14-121">Applicant type (internal or external)</span></span>

## <a name="analytics-hub"></a><span data-ttu-id="b2d14-122">Centrum analiz</span><span class="sxs-lookup"><span data-stu-id="b2d14-122">Analytics Hub</span></span>

<span data-ttu-id="b2d14-123">Raporty Centrum analiz agregują informacje o funkcjach w celu pokazania trendów w procesie rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="b2d14-123">Analytics Hub reports aggregate data across jobs to surface trends in the hiring process.</span></span> <span data-ttu-id="b2d14-124">Attract oferuje dwa raporty OOTB: Podsumowanie procesu i Analiza lejkowa.</span><span class="sxs-lookup"><span data-stu-id="b2d14-124">Attract includes two OOTB reports: Pipeline Summary and Funnel Analysis.</span></span>

### <a name="pipeline-summary"></a><span data-ttu-id="b2d14-125">Podsumowanie procesu</span><span class="sxs-lookup"><span data-stu-id="b2d14-125">Pipeline Summary</span></span>

<span data-ttu-id="b2d14-126">Raport Podsumowanie procesu umożliwia agregowanie danych dla otwartych zadań.</span><span class="sxs-lookup"><span data-stu-id="b2d14-126">The Pipeline Summary report aggregates data for open jobs.</span></span> <span data-ttu-id="b2d14-127">Kluczowe wskaźniki obejmują:</span><span class="sxs-lookup"><span data-stu-id="b2d14-127">Key metrics include:</span></span>

- <span data-ttu-id="b2d14-128">Kandydaci na wszystkie funkcje wg etapów</span><span class="sxs-lookup"><span data-stu-id="b2d14-128">Applicants across all jobs by stage</span></span>
- <span data-ttu-id="b2d14-129">Źródła kandydatów</span><span class="sxs-lookup"><span data-stu-id="b2d14-129">Applicant source</span></span>
- <span data-ttu-id="b2d14-130">Otwarte funkcje wg poziomu stażu pracy</span><span class="sxs-lookup"><span data-stu-id="b2d14-130">Open jobs by seniority level</span></span>

### <a name="funnel-analysis"></a><span data-ttu-id="b2d14-131">Analiza lejka</span><span class="sxs-lookup"><span data-stu-id="b2d14-131">Funnel Analysis</span></span>

<span data-ttu-id="b2d14-132">Raport analizy lejka agreguje dane dla zadań, które zostały zamknięte jako wypełnione.</span><span class="sxs-lookup"><span data-stu-id="b2d14-132">The Funnel Analysis report aggregates data for jobs that have been closed as filled.</span></span> <span data-ttu-id="b2d14-133">Kluczowe wskaźniki obejmują:</span><span class="sxs-lookup"><span data-stu-id="b2d14-133">Key metrics include:</span></span>

- <span data-ttu-id="b2d14-134">Czas do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="b2d14-134">Time to hire</span></span>
- <span data-ttu-id="b2d14-135">Metryka konwersji (po najechaniu kursorem)</span><span class="sxs-lookup"><span data-stu-id="b2d14-135">Conversion metrics (on hover)</span></span>
- <span data-ttu-id="b2d14-136">Współczynnik akceptacji ofert</span><span class="sxs-lookup"><span data-stu-id="b2d14-136">Offer acceptance rate</span></span>

<span data-ttu-id="b2d14-137">Uwaga: w celu uzyskania najdokładniejszego czasu na potrzeby raportów zatrudniania zaleca się korzystanie [Zarządzanie ofertami](offer-setup.md), dostępnej jako część dodatku kompleksowej obsługi rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="b2d14-137">Note: For the most accurate time to hire reporting, it is recommended that you use [Offer management](offer-setup.md), a feature available as part of the Comprehensive Hiring Add-On.</span></span>

>[!TIP] 
><span data-ttu-id="b2d14-138">Aby uzyskać dodatkowe informacje, spróbuj umieścić kursor nad wizualnymi informacjami.</span><span class="sxs-lookup"><span data-stu-id="b2d14-138">Try hovering over visuals for additional information.</span></span> <span data-ttu-id="b2d14-139">Na przykład umieszczenie wskaźnika myszy na **aktywnych kandydatach** powoduje wyświetlenie średniej liczby dni na etapie.</span><span class="sxs-lookup"><span data-stu-id="b2d14-139">For example, hovering over **Active applicants** visuals will display the average days in stage.</span></span> <span data-ttu-id="b2d14-140">Analiza tych informacji może zapewnić informacje niezbędne do skrócenia czasu zatrudniania i umożliwienia rekruterom skoncentrowania się na sposobach skrócenia czasu spędzanego na każdym etapie.</span><span class="sxs-lookup"><span data-stu-id="b2d14-140">Analyzing this information can provide insights critical to reducing time to hire and enable recruiters to focus on ways to reduce the time spent in each stage.</span></span>

## <a name="user-specific-security"></a><span data-ttu-id="b2d14-141">Zabezpieczenia na poziomie użytkownika</span><span class="sxs-lookup"><span data-stu-id="b2d14-141">User-specific security</span></span>

<span data-ttu-id="b2d14-142">Raporty Attract są dostępne dla ról Administrator, Przeczytaj wszystko, Rekruter i Menedżer zatrudnienia [role ](security-attract.md).</span><span class="sxs-lookup"><span data-stu-id="b2d14-142">Attract reports are accessible for Admin, Read All, Recruiter, and Hiring Manager [roles](security-attract.md).</span></span> <span data-ttu-id="b2d14-143">Nieprzypisani użytkownicy nie mają dostępu do stron raportów analitycznych Analiza funkcji i Centrum analiz.</span><span class="sxs-lookup"><span data-stu-id="b2d14-143">Unassigned users do not have access to either of the analytic report pages (Job Analytics or Analytics Hub).</span></span>

<span data-ttu-id="b2d14-144">Raporty Analiza funkcji pokazują dane wybranej funkcji.</span><span class="sxs-lookup"><span data-stu-id="b2d14-144">Job Analytics reports display data for the selected job.</span></span> <span data-ttu-id="b2d14-145">Raporty centrum analiz służą do agregowania danych dla wszystkich zadań, które użytkownik może wyświetlić.</span><span class="sxs-lookup"><span data-stu-id="b2d14-145">Analytics Hub reports aggregate data across all jobs a user can view.</span></span> <span data-ttu-id="b2d14-146">Użytkownicy, którzy mogą wyświetlać moje zadania i wszystkie zadania na stronie zadania, mają te same widoki w Centrum analiz.</span><span class="sxs-lookup"><span data-stu-id="b2d14-146">Users that can view both My jobs and All jobs on the Jobs page have the same views available in the Analytics Hub.</span></span>

## <a name="cross-filter"></a><span data-ttu-id="b2d14-147">Filtrowanie krzyżowe</span><span class="sxs-lookup"><span data-stu-id="b2d14-147">Cross-filter</span></span>

<span data-ttu-id="b2d14-148">Jedną z doskonałych funkcji tego Power BI jest sposób, w jaki są wzajemnie połączone wszystkie elementy wizualne na stronie raportu.</span><span class="sxs-lookup"><span data-stu-id="b2d14-148">One of the great features of Power BI is the way all visuals on a report page are interconnected.</span></span> <span data-ttu-id="b2d14-149">Jeśli wybierzesz punkt danych w jednym z elementów wizualnych, wszystkie pozostałe elementy wizualne na stronie zawierają tę zmianę danych, zależnie od wybranej opcji.</span><span class="sxs-lookup"><span data-stu-id="b2d14-149">If you select a data point on one of the visuals, all the other visuals on the page that contain that data change, based on that selection.</span></span> <span data-ttu-id="b2d14-150">Aby dowiedzieć się więcej i zobaczyć przykład, zajrzyj do [Jak elementy wizualne filtrują się krzyżowo nawzajem w raporcie Power BI ](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span><span class="sxs-lookup"><span data-stu-id="b2d14-150">Find out more and see an example in [How visuals cross-filter each other in a Power BI report](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span></span>

## <a name="export-to-excel"></a><span data-ttu-id="b2d14-151">Eksportuj do programu Excel</span><span class="sxs-lookup"><span data-stu-id="b2d14-151">Export to Excel</span></span>

<span data-ttu-id="b2d14-152">Aby wyświetlić dane raportu w programie Excel, można kliknąć menu Opcje (trzy kropki) w elemencie wizualnym i wybrać polecenie **Eksportuj dane źródłowe**.</span><span class="sxs-lookup"><span data-stu-id="b2d14-152">To view report data in Excel, you can click the options menu (three dots) on a visual and select **Export underlying data**.</span></span> <span data-ttu-id="b2d14-153">Eksportowane dane są eksportowane jako przefiltrowane, zgodnie z uprawnieniami użytkownika w Attract.</span><span class="sxs-lookup"><span data-stu-id="b2d14-153">Exported data will export as filtered, respecting user permissions in Attract.</span></span> <span data-ttu-id="b2d14-154">Aby uzyskać więcej informacji, zajrzyj do [Eksport danych z wizualizacji](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span><span class="sxs-lookup"><span data-stu-id="b2d14-154">For more information, see [Export data from visualizations](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span></span>
