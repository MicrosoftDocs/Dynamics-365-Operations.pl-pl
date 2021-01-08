---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (7 lutego 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 002dcd8253a0ab753ac9002e7027441db6d0b858
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462253"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-7-2019"></a><span data-ttu-id="bfb0e-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (7 lutego 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="bfb0e-103">What's new or changed in Dynamics 365 Talent (February 7, 2019)</span></span>

<span data-ttu-id="bfb0e-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Talent.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="bfb0e-105">Zmiany w Attract</span><span class="sxs-lookup"><span data-stu-id="bfb0e-105">Changes in Attract</span></span>

### <a name="interview-scheduling-enhancements"></a><span data-ttu-id="bfb0e-106">Rozszerzenia do Planowania rozmów kwalifikacyjnych</span><span class="sxs-lookup"><span data-stu-id="bfb0e-106">Interview scheduling enhancements</span></span>
<span data-ttu-id="bfb0e-107">Wprowadzono udoskonalenia całego procesu planowania rozmowy kwalifikacyjnej.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-107">Improvements have been made to the end-to-end interview scheduling experience.</span></span> <span data-ttu-id="bfb0e-108">Teraz można wyświetlić informacje o dostępności w kalendarzu kandydata wewnętrznego i użyć kalendarza wewnętrznego kandydata, aby zaproponować harmonogram.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-108">You can now see the calendar availability of an internal candidate and use the internal candidate’s calendar for schedule recommendations.</span></span> <span data-ttu-id="bfb0e-109">Aby uzyskać więcej informacji, zobacz [Planowanie rozmów kwalifikacyjnych i informacji zwrotnych](interview-scheduling-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="bfb0e-109">For more information, see [Interview scheduling and feedback](interview-scheduling-feedback.md).</span></span>

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a><span data-ttu-id="bfb0e-110">Publikowanie ofert pracy na LinkedIn — naprawiony problem niezgodności firmy</span><span class="sxs-lookup"><span data-stu-id="bfb0e-110">Job posting to LinkedIn – company mismatch issue fixed</span></span>
<span data-ttu-id="bfb0e-111">Został rozwiązany problem polegający na tym, że oferty pracy na LinkedIn wysyłane z Attract były publikowane z nieprawidłową nazwą firmy.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-111">An issue has been fixed where jobs posted to LinkedIn from Attract were appearing under the wrong company name.</span></span> <span data-ttu-id="bfb0e-112">Aby uzyskać więcej informacji, zobacz [tworzenie, zatwierdzanie i publikowanie ofert pracy w Attract](creating-jobs-attract.md).</span><span class="sxs-lookup"><span data-stu-id="bfb0e-112">For more information, see [Create, approve, and post jobs in Attract](creating-jobs-attract.md).</span></span>

### <a name="career-site-url-displayed-in-admin-settings"></a><span data-ttu-id="bfb0e-113">Adres URL witryny kariery zawodowej wyświetlany w ustawieniach administratora</span><span class="sxs-lookup"><span data-stu-id="bfb0e-113">Career site URL displayed in Admin settings</span></span>
<span data-ttu-id="bfb0e-114">Adres URL strony głównej kariery jest teraz wyświetlany w **ustawieniach administratora** w obszarze **Zarządzanie witryną kariery zawodowej**.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-114">The career site home page URL is now displayed in **Admin Settings** under **Career Site management**.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="bfb0e-115">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="bfb0e-115">Changes in Core HR</span></span>

<span data-ttu-id="bfb0e-116">**Kompilacja 8.1.2134**</span><span class="sxs-lookup"><span data-stu-id="bfb0e-116">**Build 8.1.2134**</span></span>

### <a name="multiple-compensation-levels-supported-on-jobs"></a><span data-ttu-id="bfb0e-117">Obsługa wielu poziomów wynagrodzeń na stanowisku</span><span class="sxs-lookup"><span data-stu-id="bfb0e-117">Multiple compensation levels supported on jobs</span></span>
<span data-ttu-id="bfb0e-118">Ta zmiana zezwala na zdefiniowanie dla stanowiska więcej niż jednego poziomu wynagrodzenia, co pozwala stosować zakresy stałych wynagrodzeń pracownika, które mogą się różnić między planami na tym samym stanowisku.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-118">This change allows for more than one compensation level to be defined on a job, enabling employee fixed compensation ranges which may differ between plans when using the same job.</span></span> 

<span data-ttu-id="bfb0e-119">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="bfb0e-119">For example:</span></span>    
<span data-ttu-id="bfb0e-120">*Stanowisko* - Kierownik ds. klienta *Skojarzone poziomy wynagrodzenia:* B1 i B2 - każdy poziom ma określony zakres wartości.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-120">*Job* - Account Manager *Associated compensation levels:* B1 and B2 - Each level has a defined range of values.</span></span> <span data-ttu-id="bfb0e-121">B1 = minimum 50 000, środkowy 60 000, Maks 75 000 i B2 = Min 65 000, środkowy 74 000, maksymalna liczba 85 000.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-121">B1 = Min 50,000, Mid 60,000, Max 75,000 and B2 = Min 65,000, Mid 74,000, Max 85,000.</span></span> <span data-ttu-id="bfb0e-122">Podczas tworzenia stałych wynagrodzeń dla pracowników, zgodnie ze zdefiniowanymi regułami uprawnienia, każdy plan stałych wynagrodzeń może wskazywać to samo stanowisko i różne poziomy stanowiska.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-122">When creating fixed compensation for employees, based on the eligibility rules defined, each fixed plan can now point to the same job and to different levels on the job.</span></span> <span data-ttu-id="bfb0e-123">Pozwala to na różnicowanie planów dla różnych regionów/firm na tym samym stanowisku z różnymi zakresami płac, ale bez konieczności duplikowania stanowisk, tak aby odzwierciedlały te różnice.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-123">This allows for plans to be defined in different regions/companies and point to the same job but different ranges without duplicating jobs to account for these differences.</span></span>

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a><span data-ttu-id="bfb0e-124">Pole poziom wynagrodzeń zostało dodane wpisu stałego wynagrodzenia pracownika</span><span class="sxs-lookup"><span data-stu-id="bfb0e-124">Compensation level field has been added to the Employee fixed compensation entity</span></span> 
<span data-ttu-id="bfb0e-125">Dzięki tej aktualizacji wpis stałego wynagrodzenia pracownika zawiera teraz pole **poziomu wynagrodzenia**.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-125">With this update, the employee fixed compensation entity has been updated to include the **Compensation level** field.</span></span> <span data-ttu-id="bfb0e-126">Ten dodatek pozwala łatwiej aktualizować plany stałych wynagrodzeń pracowników.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-126">This addition makes it easier to update employee fixed compensation plans.</span></span> 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a><span data-ttu-id="bfb0e-127">Aktualizowanie rodziny stanowisk przy aktualizowaniu i tworzeniu nowych stanowisk</span><span class="sxs-lookup"><span data-stu-id="bfb0e-127">Update Job family when updating and creating new positions</span></span>
<span data-ttu-id="bfb0e-128">Podczas zmieniania zadania na stanowisku **rodzina zadań** będzie teraz domyślna na podstawie wybranego zadania.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-128">When changing the job on a position, **Job family** will now default based on the job selected.</span></span>

### <a name="performance-improvements-when-rendering-workspaces"></a><span data-ttu-id="bfb0e-129">Poprawa wydajności podczas renderowania obszarów roboczych</span><span class="sxs-lookup"><span data-stu-id="bfb0e-129">Performance improvements when rendering workspaces</span></span>
<span data-ttu-id="bfb0e-130">Karty analityczne w obszarze roboczym będą teraz wczytywane tylko w przypadku otwierania tych stron.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-130">Analytics tabs on workspaces will now load only when accessing those pages.</span></span> <span data-ttu-id="bfb0e-131">Podczas początkowego renderowania strony w lewym górnym rogu będzie widoczny wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="bfb0e-131">An indicator will display during the initial rendering of the page in the upper-left corner of the page.</span></span>
