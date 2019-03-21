---
title: Funkcjonalność witryny rozwoju kariery w aplikacji Attract
description: Ten temat zawiera omówienie funkcji witryny kariery zawodowej w aplikacji Attract dostępne dla kandydatów.
author: josaw1
manager: AnnBe
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 087ab4034a1e601e7f3514c77d56ef54b0c5c52d
ms.sourcegitcommit: 1ee613a88edddab036d145f27f19d071a4b8ad24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/13/2019
ms.locfileid: "389980"
---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="e11b8-103">Funkcjonalność witryny rozwoju kariery w aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="e11b8-103">Career site functionality in Attract</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e11b8-104">Ten temat zawiera omówienie funkcji witryny kariery zawodowej w Microsoft Dynamics 365 for Talent: Attract dostępne dla kandydatów.</span><span class="sxs-lookup"><span data-stu-id="e11b8-104">This topic provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="e11b8-105">Wyjaśniono również, jak skonfigurować tę funkcjonalność.</span><span class="sxs-lookup"><span data-stu-id="e11b8-105">It also explains how to set up this functionality.</span></span>

<span data-ttu-id="e11b8-106">Aplikacja Attract udostępnia jedną witrynę rozwoju kariery dla każdego środowiska w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="e11b8-106">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="e11b8-107">Na przykład jeśli organizacja ma środowiska projektowe i testowe, dla każdego z nich jest generowana osobna witryna rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="e11b8-107">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="e11b8-108">Każda witryna rozwoju kariery jest całkowicie odizolowana i ma własny mechanizm uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="e11b8-108">Each career site is completely isolated and has its own authentication mechanism.</span></span> <span data-ttu-id="e11b8-109">Funkcje i profile kandydatów nie są udostępniane między witrynami rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="e11b8-109">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="e11b8-110">Domyślnie witryna rozwoju kariery jest publiczna.</span><span class="sxs-lookup"><span data-stu-id="e11b8-110">By default, the career site is public.</span></span> <span data-ttu-id="e11b8-111">Z tego względu kandydaci mogą wyświetlić wszystkie funkcje oznaczone jako zewnętrzne bez konieczności logowania się.</span><span class="sxs-lookup"><span data-stu-id="e11b8-111">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="e11b8-112">Jednak wszystkie pozostałe czynności wymagają, aby kandydaci się zalogowali.</span><span class="sxs-lookup"><span data-stu-id="e11b8-112">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="e11b8-113">Zarządzanie witryną rozwoju kariery</span><span class="sxs-lookup"><span data-stu-id="e11b8-113">Career site management</span></span>

<span data-ttu-id="e11b8-114">Aby ustawić wartości następujących elementów, zaloguj się w aplikacji Attract jako administrator, wybierz opcję **Centrum administracyjne** w menu **Ustawienia** (symbol koła zębatego), a następnie wybierz kartę **Informacje o firmie**.</span><span class="sxs-lookup"><span data-stu-id="e11b8-114">To set the values for the following items, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

-   <span data-ttu-id="e11b8-115">**Nazwa organizacji:** Nazwa organizacji jest wyświetlana na pasku nawigacji u góry witryny rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="e11b8-115">**Organization name** - The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="e11b8-116">Gdy kandydat kliknie nazwę organizacji, przejdzie do strony, która zawiera listę wszystkich otwartych funkcji.</span><span class="sxs-lookup"><span data-stu-id="e11b8-116">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>

-   <span data-ttu-id="e11b8-117">**Logo organizacji:** Obraz logo organizacji pojawia się w lewym górnym rogu witryny rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="e11b8-117">**Organization logo** - An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="e11b8-118">Gdy kandydat kliknie obraz logo, przejdzie do strony, która zawiera listę wszystkich otwartych funkcji.</span><span class="sxs-lookup"><span data-stu-id="e11b8-118">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

    >   [!NOTE] 
    >   <span data-ttu-id="e11b8-119">Obraz logo wyświetlany w witrynie rozwoju kariery ma stałą wysokość 20 pikseli (px).</span><span class="sxs-lookup"><span data-stu-id="e11b8-119">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="e11b8-120">Obraz dodany w Centrum administracyjnym zostanie wyskalowany, tak aby pasował do tego limitu.</span><span class="sxs-lookup"><span data-stu-id="e11b8-120">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="e11b8-121">W związku z tym w zależności od obrazu szerokość może się zmienić.</span><span class="sxs-lookup"><span data-stu-id="e11b8-121">Therefore, depending on the image, the width might change.</span></span>
 
<span data-ttu-id="e11b8-122">Aby ustawić wartości następujących elementów, zaloguj się w aplikacji Attract jako administrator, wybierz opcję **Centrum administracyjne** w menu **Ustawienia**, a następnie wybierz kartę **Zarządzanie witryną rozwoju kariery**.</span><span class="sxs-lookup"><span data-stu-id="e11b8-122">To set the values for the following items, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu, and then select the **Career site management** tab.</span></span>

-   <span data-ttu-id="e11b8-123">**Optymalizacja aparatu wyszukiwania:** Po włączeniu tej opcji wszystkie publicznie dostępne oferty w witrynie rozwoju kariery Attract będzie można znaleźć za pomocą wyszukiwarek, takich jak Bing i Google.</span><span class="sxs-lookup"><span data-stu-id="e11b8-123">**Search Engine Optimization** - When enabled, all public jobs posted to Attract career site will be searchable using search engines like Bing and Google.</span></span>

    >   [!NOTE] 
    >   <span data-ttu-id="e11b8-124">Może wystąpić opóźnienie między włączeniem tego ustawienia, a uwzględnianiem ofert w wynikach wyszukiwania, w zależności od używanego aparatu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="e11b8-124">There might be a delay between turning this setting on and search results appearing, depending on the search engine that you are using.</span></span>
         
## <a name="career-site-urls"></a><span data-ttu-id="e11b8-125">Adresu URL witryny rozwoju kariery</span><span class="sxs-lookup"><span data-stu-id="e11b8-125">Career site URLs</span></span>

<span data-ttu-id="e11b8-126">Poniższa lista zawiera często używane adresy URL witryny rozwoju kariery i metody dostępu do nich.</span><span class="sxs-lookup"><span data-stu-id="e11b8-126">The following list contains the commonly used career site URLs and how to access them.</span></span>

-   <span data-ttu-id="e11b8-127">**Adres URL strony głównej witryny kariery zawodowej** — Aby wyświetlić adres URL strony głównej witryny kariery zawodowej, zaloguj się w Attract jako administrator, wybierz opcję **Centrum administracyjne** w menu **ustawienia**, a następnie wybierz opcję **Zarządzanie witryną kariery zawodowej**.</span><span class="sxs-lookup"><span data-stu-id="e11b8-127">**Career site home page URL** - To view the career site home page URL, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu, and then select the **Career site management** tab.</span></span>

-   <span data-ttu-id="e11b8-128">**Indywidualny adres URL zgłoszenia na ofertę pracy**Gdy [publikujesz ofertę](Creating-jobs-Attract.md#postings) dla kandydatów zewnętrznych po raz pierwszy, możesz skopiować łącze **Zgłoś się** z aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="e11b8-128">**Individual job post apply URL** - When you [post an external job](Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="e11b8-129">Adres URL tego łącza będzie miał następujący format: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)</span><span class="sxs-lookup"><span data-stu-id="e11b8-129">The URL for this link will be in the following format: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)</span></span>

-   <span data-ttu-id="e11b8-130">**Indywidualny adres URL oferty pracy** adres URL oferty pracy jest podciągiem adresu URL zgłoszenia.</span><span class="sxs-lookup"><span data-stu-id="e11b8-130">**Individual job post URL** - The URL of the job post is a substring of the Apply URL.</span></span> <span data-ttu-id="e11b8-131">Zawiera wszystkie elementy aż do numeru stanowiska włącznie.</span><span class="sxs-lookup"><span data-stu-id="e11b8-131">It consists of everything up through the job number.</span></span> <span data-ttu-id="e11b8-132">Z tego względu w podanym wyżej adresie URL Zgłoś się adresem URL oferty pracy jest [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e).</span><span class="sxs-lookup"><span data-stu-id="e11b8-132">Therefore, for the preceding Apply URL, the job post URL is [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)</span></span>

## <a name="authentication-options"></a><span data-ttu-id="e11b8-133">Opcje uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="e11b8-133">Authentication options</span></span>

<span data-ttu-id="e11b8-134">Kandydaci mają do dyspozycji następujące opcje logowania do witryny rozwoju kariery w aplikacji Attract:</span><span class="sxs-lookup"><span data-stu-id="e11b8-134">Candidates have the following sign-in options for an Attract career site:</span></span>

-   <span data-ttu-id="e11b8-135">Konto osobiste:</span><span class="sxs-lookup"><span data-stu-id="e11b8-135">Personal account:</span></span>

    -   <span data-ttu-id="e11b8-136">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e11b8-136">LinkedIn</span></span>

    -   <span data-ttu-id="e11b8-137">Microsoft</span><span class="sxs-lookup"><span data-stu-id="e11b8-137">Microsoft</span></span>

    -   <span data-ttu-id="e11b8-138">Google</span><span class="sxs-lookup"><span data-stu-id="e11b8-138">Google</span></span>

    -   <span data-ttu-id="e11b8-139">Facebook</span><span class="sxs-lookup"><span data-stu-id="e11b8-139">Facebook</span></span>

-   <span data-ttu-id="e11b8-140">Konto służbowe lub szkolne:</span><span class="sxs-lookup"><span data-stu-id="e11b8-140">Work or school account:</span></span>

    -   <span data-ttu-id="e11b8-141">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e11b8-141">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="e11b8-142">Azure AD Logowanie przez usługę Azure AD jest przeznaczone tylko dla kandydatów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="e11b8-142">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="e11b8-143">Z tego względu działa tylko dla kandydatów wewnętrznych, którzy używają firmowych poświadczeń dostępu do usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e11b8-143">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="e11b8-144">Na przykład kandydat, który jest obecnie pracownikiem firmy Contoso Ltd., chce ubiegać się o pracę w niepowiązanej firmie Alpine Ski House.</span><span class="sxs-lookup"><span data-stu-id="e11b8-144">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="e11b8-145">W takim przypadku logowanie się nie powiedzie, jeśli pracownik spróbuje użyć swoich poświadczeń dostępu do usługi Azure AD z firmy Contoso Ltd.</span><span class="sxs-lookup"><span data-stu-id="e11b8-145">In this case, the sign-in will be unsuccessful if the employee tries to use Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="e11b8-146">Tworzenie profilu i zarządzanie nim</span><span class="sxs-lookup"><span data-stu-id="e11b8-146">Create and maintain a profile</span></span>

<span data-ttu-id="e11b8-147">Gdy kandydaci logują się do witryny rozwoju kariery, mogą wybrać opcję **Mój profil** na pasku nawigacji u góry strony, aby utworzyć sobie profil i nim zarządzać.</span><span class="sxs-lookup"><span data-stu-id="e11b8-147">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span>
<span data-ttu-id="e11b8-148">Profil zawiera informacje osobiste, informacje o doświadczeniu zawodowym, szczegóły wykształcenia, dokumenty, łącza oraz informacji o umiejętnościach.</span><span class="sxs-lookup"><span data-stu-id="e11b8-148">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="e11b8-149">Po utworzeniu profilu można go używać do ubiegania się o funkcje interesujące kandydata.</span><span class="sxs-lookup"><span data-stu-id="e11b8-149">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="e11b8-150">Profile pomagają również aplikacji Attract rekomendować odpowiednie stanowiska dla kandydatów.</span><span class="sxs-lookup"><span data-stu-id="e11b8-150">Profiles also help Attract recommend the right jobs to candidates.</span></span>

>   [!NOTE]
>   <span data-ttu-id="e11b8-151">Jeśli kandydat używa identyfikatora e-mail, aby zalogować się przy użyciu jednego z dostawców uwierzytelniania wymienionych powyżej, ten identyfikator e-mail zostanie ustawiony jako domyślny dla kontaktowego adresu e-mail skojarzonego z profilem.</span><span class="sxs-lookup"><span data-stu-id="e11b8-151">If a candidate uses an email ID to sign in using one of the authentication providers listed above, that email ID will default to the contact email ID associated with the profile.</span></span> <span data-ttu-id="e11b8-152">Jednak to ostatnie można zmienić w dowolnym momencie i jest to całkowicie niezależne od pierwszego.</span><span class="sxs-lookup"><span data-stu-id="e11b8-152">However, the latter can be changed at any time and is completely independent of the former.</span></span> <span data-ttu-id="e11b8-153">Attract będzie zawsze używać Identyfikatora e-mail osoby kontaktowej do skojarzenia go z Twoim profilem dla całej komunikacji e-mail.</span><span class="sxs-lookup"><span data-stu-id="e11b8-153">Attract will always use the contact email ID to associate with your profile for all email communications.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="e11b8-154">Znajdowanie odpowiedniej funkcji</span><span class="sxs-lookup"><span data-stu-id="e11b8-154">Find the right job</span></span>

<span data-ttu-id="e11b8-155">Na stronie listy funkcji kandydaci mogą wyszukiwać konkretne funkcje, wpisując konkretne terminy.</span><span class="sxs-lookup"><span data-stu-id="e11b8-155">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="e11b8-156">Funkcjonalność wyszukiwania szuka kryteriów wyszukiwania w tytułach funkcji i opisach funkcji, a następnie pokazuje pasujące funkcje jako wyniki.</span><span class="sxs-lookup"><span data-stu-id="e11b8-156">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="e11b8-157">Kandydaci mogą filtrować wyniki w dowolnym momencie według lokalizacji funkcji lub czynności związanych z funkcją.</span><span class="sxs-lookup"><span data-stu-id="e11b8-157">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="e11b8-158">Kandydaci mogą również w witrynie rozwoju kariery przeglądać zestaw zalecanych funkcji.</span><span class="sxs-lookup"><span data-stu-id="e11b8-158">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="e11b8-159">Funkcje rekomendowane kandydatowi bazują na poprzednich zgłoszeniach, profilu i życiorysie kandydata.</span><span class="sxs-lookup"><span data-stu-id="e11b8-159">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

>   [!NOTE] 
>   <span data-ttu-id="e11b8-160">Rekomendacje funkcji są wyświetlane tylko wtedy, gdy co najmniej 10 funkcji jest opublikowanych w witrynie rozwoju kariery, a kandydat ma uzupełniony profil.</span><span class="sxs-lookup"><span data-stu-id="e11b8-160">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed a profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="e11b8-161">Ubieganie się o pracę</span><span class="sxs-lookup"><span data-stu-id="e11b8-161">Apply for jobs</span></span>

<span data-ttu-id="e11b8-162">Gdy kandydat znajdzie odpowiednią funkcję, może złożyć podanie, klikając przycisk **Zgłoś** się na stronie **szczegółów stanowiska**.</span><span class="sxs-lookup"><span data-stu-id="e11b8-162">After candidates find the right job, they can apply by using the **Apply** button on the **Job details** page.</span></span> <span data-ttu-id="e11b8-163">W tym momencie kandydat może utworzyć całkowicie nowy profil lub przejrzeć informacje w swoim istniejącym profilu.</span><span class="sxs-lookup"><span data-stu-id="e11b8-163">At this point, candidates can either create a new profile or review the information in their existing profile.</span></span>
<span data-ttu-id="e11b8-164">Kandydat może także w razie potrzeby przekazać życiorys, a następnie przesłać zgłoszenie na funkcję (podanie o pracę).</span><span class="sxs-lookup"><span data-stu-id="e11b8-164">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="e11b8-165">Sprawdzanie stanu zgłoszenia</span><span class="sxs-lookup"><span data-stu-id="e11b8-165">Check application status</span></span>

<span data-ttu-id="e11b8-166">Gdy kandydat prześle zgłoszenie na jedną lub więcej funkcji, może wybrać opcję **Zgłoszenia** na pasku nawigacji u góry strony i wyświetlić swoje otwarte i zamknięte zgłoszenia.</span><span class="sxs-lookup"><span data-stu-id="e11b8-166">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="e11b8-167">Gdy kandydat otworzy jedno ze swoich zgłoszeń, zobaczy jego obecny etap oraz wszelkie oczekujące czynności, jakie musi wykonać.</span><span class="sxs-lookup"><span data-stu-id="e11b8-167">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="e11b8-168">Na przykład jeśli kandydat musi zaproponować daty osobistej rozmowy kwalifikacyjnej, na stronie będą widoczne dostępne opcje.</span><span class="sxs-lookup"><span data-stu-id="e11b8-168">For example, if a candidate must provide potential dates for an in-person interview, the page shows the available options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="e11b8-169">Funkcje wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="e11b8-169">Internal jobs</span></span>

<span data-ttu-id="e11b8-170">Obecnie funkcje oznaczone jako wewnętrzne i opublikowane w witrynie rozwoju kariery w aplikacji Attract nie są wyświetlane w witrynie rozwoju kariery.</span><span class="sxs-lookup"><span data-stu-id="e11b8-170">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="e11b8-171">Są one dostępne wyłącznie za pośrednictwem bezpośredniego adresu URL **Zgłoś się**, który można skopiować z aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="e11b8-171">They are only accessible using the direct **Apply** URL that can be copied from the Attract application.</span></span>
