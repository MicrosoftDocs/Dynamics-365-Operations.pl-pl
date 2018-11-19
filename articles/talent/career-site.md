---
title: "Funkcjonalność witryny rozwoju kariery w aplikacji Attract"
description: "Ten artykuł zawiera omówienie funkcjonalności witryny rozwoju kariery dostępnej dla kandydatów w programie Microsoft Dynamics 365 for Talent - Attract. Wyjaśniono również, jak skonfigurować tę funkcjonalność."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: pl-pl
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="952e9-104">Funkcjonalność witryny rozwoju kariery w aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="952e9-104">Career site functionality in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="952e9-105">Ten artykuł zawiera omówienie funkcjonalności witryny rozwoju kariery dostępnej dla kandydatów w programie Microsoft Dynamics 365 for Talent Attract.</span><span class="sxs-lookup"><span data-stu-id="952e9-105">This article provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="952e9-106">Wyjaśniono również, jak skonfigurować tę funkcjonalność.</span><span class="sxs-lookup"><span data-stu-id="952e9-106">It also explains how to set up this functionality.</span></span>

## <a name="overview"></a><span data-ttu-id="952e9-107">Przegląd</span><span class="sxs-lookup"><span data-stu-id="952e9-107">Overview</span></span>

<span data-ttu-id="952e9-108">Aplikacja Attract udostępnia jedną witrynę rozwoju kariery dla każdego środowiska w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="952e9-108">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="952e9-109">Na przykład jeśli organizacja ma środowiska projektowe i testowe, dla każdego z nich jest generowana osobna witryna rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="952e9-109">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="952e9-110">Każda witryna rozwoju kariery jest **całkowicie odizolowana** i ma własny mechanizm uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="952e9-110">Each career site is **completely isolated** and has its own authentication mechanism.</span></span> <span data-ttu-id="952e9-111">Funkcje i profile kandydatów nie są udostępniane między witrynami rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="952e9-111">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="952e9-112">Domyślnie witryna rozwoju kariery jest publiczna.</span><span class="sxs-lookup"><span data-stu-id="952e9-112">By default, the career site is public.</span></span> <span data-ttu-id="952e9-113">Z tego względu kandydaci mogą wyświetlić wszystkie funkcje oznaczone jako zewnętrzne bez konieczności logowania się.</span><span class="sxs-lookup"><span data-stu-id="952e9-113">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="952e9-114">Jednak wszystkie pozostałe czynności wymagają, aby kandydaci się zalogowali.</span><span class="sxs-lookup"><span data-stu-id="952e9-114">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="952e9-115">Zarządzanie witryną rozwoju kariery</span><span class="sxs-lookup"><span data-stu-id="952e9-115">Career site management</span></span>

<span data-ttu-id="952e9-116">Następujące elementy w witrynie rozwoju kariery są kontrolowane przez ustawienia:</span><span class="sxs-lookup"><span data-stu-id="952e9-116">The following items on the career site are controlled by settings:</span></span>

- <span data-ttu-id="952e9-117">**Nazwa organizacji:** Nazwa organizacji jest wyświetlana na pasku nawigacji u góry witryny rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="952e9-117">**Organization name:** The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="952e9-118">Gdy kandydat kliknie nazwę organizacji, przejdzie do strony, która zawiera listę wszystkich otwartych funkcji.</span><span class="sxs-lookup"><span data-stu-id="952e9-118">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>
- <span data-ttu-id="952e9-119">**Logo organizacji:** Obraz logo organizacji pojawia się w lewym górnym rogu witryny rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="952e9-119">**Organization logo:** An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="952e9-120">Gdy kandydat kliknie obraz logo, przejdzie do strony, która zawiera listę wszystkich otwartych funkcji.</span><span class="sxs-lookup"><span data-stu-id="952e9-120">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

<span data-ttu-id="952e9-121">Aby ustawić wartości nazwy i logo organizacji, zaloguj się w aplikacji Attract jako administrator, wybierz opcję **Centrum administracyjne** w menu **Ustawienia** (symbol koła zębatego), a następnie wybierz kartę **Informacje o firmie**.</span><span class="sxs-lookup"><span data-stu-id="952e9-121">To set the values for the organization name and logo, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="952e9-122">Obraz logo wyświetlany w witrynie rozwoju kariery ma stałą wysokość 20 pikseli (px).</span><span class="sxs-lookup"><span data-stu-id="952e9-122">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="952e9-123">Obraz dodany w Centrum administracyjnym zostanie wyskalowany, tak aby pasował do tego limitu.</span><span class="sxs-lookup"><span data-stu-id="952e9-123">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="952e9-124">W związku z tym w zależności od obrazu szerokość może się zmienić.</span><span class="sxs-lookup"><span data-stu-id="952e9-124">Therefore, depending on the image, the width might change.</span></span>

## <a name="career-site-url"></a><span data-ttu-id="952e9-125">Adres URL witryny rozwoju kariery</span><span class="sxs-lookup"><span data-stu-id="952e9-125">Career site URL</span></span>

<span data-ttu-id="952e9-126">Gdy [publikujesz ofertę na funkcję dla kandydatów zewnętrznych](./Creating-jobs-Attract.md#postings) po raz pierwszy, możesz skopiować łącze **Zgłoś się** z aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="952e9-126">When you [post an external job](./Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="952e9-127">Adres URL tego łącza będzie miał następujący format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span><span class="sxs-lookup"><span data-stu-id="952e9-127">The URL for this link will be in the following format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span></span>

<span data-ttu-id="952e9-128">Adres URL witryny rozwoju kariery jest podciągiem adresu URL **Zgłoś się**.</span><span class="sxs-lookup"><span data-stu-id="952e9-128">The URL of the career site is a substring of the **Apply** URL.</span></span> <span data-ttu-id="952e9-129">Zawiera wszystkie elementy aż do nazwy firmy włącznie.</span><span class="sxs-lookup"><span data-stu-id="952e9-129">It consists of everything up through the company name.</span></span> <span data-ttu-id="952e9-130">Z tego względu w podanym wyżej adresie URL **Zgłoś się** adresem URL witryny rozwoju kariery jest `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span><span class="sxs-lookup"><span data-stu-id="952e9-130">Therefore, for the preceding **Apply** URL, the career site URL is `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span></span>

## <a name="authentication-options"></a><span data-ttu-id="952e9-131">Opcje uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="952e9-131">Authentication options</span></span>

<span data-ttu-id="952e9-132">Kandydaci mają do dyspozycji następujące opcje logowania do witryny rozwoju kariery w aplikacji Attract:</span><span class="sxs-lookup"><span data-stu-id="952e9-132">Candidates have the following sign-in options for an Attract career site:</span></span>

- <span data-ttu-id="952e9-133">Konto osobiste:</span><span class="sxs-lookup"><span data-stu-id="952e9-133">Personal account:</span></span>

    - <span data-ttu-id="952e9-134">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="952e9-134">LinkedIn</span></span>
    - <span data-ttu-id="952e9-135">Microsoft</span><span class="sxs-lookup"><span data-stu-id="952e9-135">Microsoft</span></span>
    - <span data-ttu-id="952e9-136">Google</span><span class="sxs-lookup"><span data-stu-id="952e9-136">Google</span></span>
    - <span data-ttu-id="952e9-137">Facebook</span><span class="sxs-lookup"><span data-stu-id="952e9-137">Facebook</span></span>

- <span data-ttu-id="952e9-138">Konto służbowe:</span><span class="sxs-lookup"><span data-stu-id="952e9-138">Work or school account:</span></span>

    - <span data-ttu-id="952e9-139">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="952e9-139">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="952e9-140">Logowanie przez usługę Azure AD jest przeznaczone tylko dla kandydatów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="952e9-140">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="952e9-141">Z tego względu działa tylko dla kandydatów wewnętrznych, którzy używają firmowych poświadczeń dostępu do usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="952e9-141">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="952e9-142">Na przykład kandydat, który jest obecnie pracownikiem firmy Contoso Ltd., chce ubiegać się o pracę w niepowiązanej firmie Alpine Ski House.</span><span class="sxs-lookup"><span data-stu-id="952e9-142">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="952e9-143">W takim przypadku logowanie się nie powiedzie, jeśli pracownik spróbuje użyć swoich poświadczeń dostępu do usługi Azure AD z firmy Contoso Ltd.</span><span class="sxs-lookup"><span data-stu-id="952e9-143">In this case, the sign-in will be unsuccessful if the employee tries to use his or her Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="952e9-144">Tworzenie profilu i zarządzanie nim</span><span class="sxs-lookup"><span data-stu-id="952e9-144">Create and maintain a profile</span></span>

<span data-ttu-id="952e9-145">Gdy kandydaci logują się do witryny rozwoju kariery, mogą wybrać opcję **Mój profil** na pasku nawigacji u góry strony, aby utworzyć sobie profil i nim zarządzać.</span><span class="sxs-lookup"><span data-stu-id="952e9-145">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span> <span data-ttu-id="952e9-146">Profil zawiera informacje osobiste, informacje o doświadczeniu zawodowym, szczegóły wykształcenia, dokumenty, łącza oraz informacji o umiejętnościach.</span><span class="sxs-lookup"><span data-stu-id="952e9-146">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="952e9-147">Po utworzeniu profilu można go używać do ubiegania się o funkcje interesujące kandydata.</span><span class="sxs-lookup"><span data-stu-id="952e9-147">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="952e9-148">Profile pomagają również aplikacji Attract rekomendować odpowiednie stanowiska dla kandydatów.</span><span class="sxs-lookup"><span data-stu-id="952e9-148">Profiles also help Attract recommend the right jobs to candidates.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="952e9-149">Znajdowanie odpowiedniej funkcji</span><span class="sxs-lookup"><span data-stu-id="952e9-149">Find the right job</span></span>

<span data-ttu-id="952e9-150">Na stronie listy funkcji kandydaci mogą wyszukiwać konkretne funkcje, wpisując konkretne terminy.</span><span class="sxs-lookup"><span data-stu-id="952e9-150">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="952e9-151">Funkcjonalność wyszukiwania szuka kryteriów wyszukiwania w tytułach funkcji i opisach funkcji, a następnie pokazuje pasujące funkcje jako wyniki.</span><span class="sxs-lookup"><span data-stu-id="952e9-151">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="952e9-152">Kandydaci mogą filtrować wyniki w dowolnym momencie według lokalizacji funkcji lub czynności związanych z funkcją.</span><span class="sxs-lookup"><span data-stu-id="952e9-152">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="952e9-153">Kandydaci mogą również w witrynie rozwoju kariery przeglądać zestaw zalecanych funkcji.</span><span class="sxs-lookup"><span data-stu-id="952e9-153">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="952e9-154">Funkcje rekomendowane kandydatowi bazują na poprzednich zgłoszeniach, profilu i życiorysie kandydata.</span><span class="sxs-lookup"><span data-stu-id="952e9-154">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

> [!NOTE]
> <span data-ttu-id="952e9-155">Rekomendacje funkcji są wyświetlane tylko wtedy, gdy co najmniej 10 funkcji jest opublikowanych w witrynie rozwoju kariery, a kandydat ma uzupełniony profil.</span><span class="sxs-lookup"><span data-stu-id="952e9-155">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed his or her profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="952e9-156">Ubieganie się o pracę</span><span class="sxs-lookup"><span data-stu-id="952e9-156">Apply for jobs</span></span>

<span data-ttu-id="952e9-157">Gdy kandydat znajdzie odpowiednią funkcję, może złożyć podanie, klikając przycisk **Zgłoś się** na stronie szczegółów funkcji.</span><span class="sxs-lookup"><span data-stu-id="952e9-157">After candidates find the right job, they can apply by using the **Apply** button on the job details page.</span></span> <span data-ttu-id="952e9-158">W tym momencie kandydat może utworzyć całkowicie nowy profil lub przejrzeć informacje w swoim istniejącym profilu.</span><span class="sxs-lookup"><span data-stu-id="952e9-158">At this point, candidates can either create a brand-new profile or review the information in their existing profile.</span></span> <span data-ttu-id="952e9-159">Kandydat może także w razie potrzeby przekazać życiorys, a następnie przesłać zgłoszenie na funkcję (podanie o pracę).</span><span class="sxs-lookup"><span data-stu-id="952e9-159">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="952e9-160">Sprawdzanie stanu zgłoszenia</span><span class="sxs-lookup"><span data-stu-id="952e9-160">Check application status</span></span>

<span data-ttu-id="952e9-161">Gdy kandydat prześle zgłoszenie na jedną lub więcej funkcji, może wybrać opcję **Zgłoszenia** na pasku nawigacji u góry strony i wyświetlić swoje otwarte i zamknięte zgłoszenia.</span><span class="sxs-lookup"><span data-stu-id="952e9-161">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="952e9-162">Gdy kandydat otworzy jedno ze swoich zgłoszeń, zobaczy jego obecny etap oraz wszelkie oczekujące czynności, jakie musi wykonać.</span><span class="sxs-lookup"><span data-stu-id="952e9-162">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="952e9-163">Na przykład jeśli kandydat musi zaproponować daty osobistej rozmowy kwalifikacyjnej, na stronie będą widoczne odpowiednie opcje.</span><span class="sxs-lookup"><span data-stu-id="952e9-163">For example, if a candidate must provide potential dates for an in-person interview, the page shows his or her options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="952e9-164">Funkcje wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="952e9-164">Internal jobs</span></span>

<span data-ttu-id="952e9-165">Obecnie funkcje oznaczone jako wewnętrzne i opublikowane w witrynie rozwoju kariery w aplikacji Attract nie są wyświetlane w witrynie rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="952e9-165">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="952e9-166">Są one dostępne wyłącznie za pośrednictwem bezpośredniego adresu URL **Zgłoś się**, który można skopiować z aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="952e9-166">They are accessible only via the direct **Apply** URL that can be copied from the Attract application.</span></span>

