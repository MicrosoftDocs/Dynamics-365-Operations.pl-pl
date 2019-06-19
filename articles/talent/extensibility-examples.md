---
title: Rozszerzanie rozwiązania Talent przy użyciu usług PowerApps i Microsoft Flow — przykładowe scenariusze
description: W tym temacie opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 for Talent używanych przez Microsoft PowerApps i Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: a9ebfd1f2621b8ad65d7623c37b6851cc0b5cb54
ms.sourcegitcommit: ffc37f7c2a63bada3055f37856a30424040bc9a3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/16/2019
ms.locfileid: "1577802"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="686bd-103">Rozszerzanie rozwiązania Talent przy użyciu usług PowerApps i Microsoft Flow — przykładowe scenariusze</span><span class="sxs-lookup"><span data-stu-id="686bd-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="686bd-104">W tym temacie opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 for Talent używanych przez Microsoft PowerApps i Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="686bd-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 for Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="686bd-105">Można zaimportować pakiet rozwiązań skojarzony z każdym przykładem do środowiska usługi PowerApps.</span><span class="sxs-lookup"><span data-stu-id="686bd-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="686bd-106">Następnie można używać pakietów jako pomocy lub punktów początkowych do implementacji scenariuszy odpowiednich dla Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="686bd-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="686bd-107">Jeśli chcesz korzystać z szablonów i aplikacji, które zostały opisane w tym temacie „tak jak są”, sprawdź je, aby upewnić się, że będą one obejmować wszystkie scenariusze, które są specyficzne dla danej implementacji.</span><span class="sxs-lookup"><span data-stu-id="686bd-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="686bd-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="686bd-108">Prerequisites</span></span>

- <span data-ttu-id="686bd-109">Aby zaimportować pakiety, użytkownicy muszą mieć uprawnienie **Twórca środowisk**.</span><span class="sxs-lookup"><span data-stu-id="686bd-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="686bd-110">Aby eksportować lub importować aplikacje, musisz mieć licencję PowerApps plan 2 lub licencję próbną PowerApps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="686bd-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="686bd-111">Przepływ — połączenie formularza</span><span class="sxs-lookup"><span data-stu-id="686bd-111">Flow – Form Connect</span></span>

<span data-ttu-id="686bd-112">Szablon **Przepływ — połączenie formularza** może być używany do odczytu danych z programu Microsoft Forms i zapisania ich w jednostce Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="686bd-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="686bd-113">Ten szablon może zostać rozszerzony, tak aby można było go używać w innych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="686bd-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="686bd-114">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="686bd-114">Here are some examples:</span></span>

- <span data-ttu-id="686bd-115">Przechwytywanie ocen kandydata.</span><span class="sxs-lookup"><span data-stu-id="686bd-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="686bd-116">Przechwytywanie wyników z kwestionariuszy na kursie.</span><span class="sxs-lookup"><span data-stu-id="686bd-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="686bd-117">Kompilowanie biblioteki pytań na rozmowy kwalifikacyjne dla administratorów zasobów ludzkich (HR).</span><span class="sxs-lookup"><span data-stu-id="686bd-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="686bd-118">Przechwytywania oceny kandydata po rozmowie kwalifikacyjnej</span><span class="sxs-lookup"><span data-stu-id="686bd-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="686bd-119">W Microsoft Dynamics 365: Attract, formularze mogą pojawiać się w portalu dla kandydatów i kandydaci mogą wypełniać szczegóły.</span><span class="sxs-lookup"><span data-stu-id="686bd-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="686bd-120">Formularze mogą być również osadzone jako działania w szablonie stanowiska.</span><span class="sxs-lookup"><span data-stu-id="686bd-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="686bd-121">Po przesłaniu formularza przez kandydata Microsoft Flow przechwytuje przesłanie formularza, odczytuje dane i zapisuje je w jednostce Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="686bd-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="686bd-122">Aby pobrać szablon **Przepływ — połączenie formularza** i strukturę jednostki niestandardowej, przejdź do sekcji [Przepływ — połączenie formularza](https://go.microsoft.com/fwlink/?linkid=2081988) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="686bd-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="686bd-123">Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps</span><span class="sxs-lookup"><span data-stu-id="686bd-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="686bd-124">Szablon **Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps** może być używany jako punkt początkowy dla dowolnych scenariuszy PowerApps charakterystycznych dla Attract.</span><span class="sxs-lookup"><span data-stu-id="686bd-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="686bd-125">Zawiera on wszystkie parametry domyślne, które są przekazywane przez Attract, takie jak **Podanie o pracę**, **identyfikator kandydata**, i **JobID**.</span><span class="sxs-lookup"><span data-stu-id="686bd-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="686bd-126">Za pomocą tego szablonu można pobrać formularz oceny kandydata, dzięki czemu menedżer zatrudniający może wyświetlić ocenę wypełnioną przez kandydata.</span><span class="sxs-lookup"><span data-stu-id="686bd-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="686bd-127">Aplikacje, które są tworzone przy użyciu usługi PowerApps mogą być osadzone w szablonie stanowiska w Attract.</span><span class="sxs-lookup"><span data-stu-id="686bd-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="686bd-128">Aby pobrać szablon **Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps** i strukturę jednostki niestandardowej, przejdź do [Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="686bd-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="686bd-129">Integracja z programem Office 365</span><span class="sxs-lookup"><span data-stu-id="686bd-129">Integration with Office 365</span></span>

<span data-ttu-id="686bd-130">Aplikacja **Integracja z Office 365** może być używana do pobierania danych zespołu dla zarejestrowanych użytkowników z Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="686bd-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="686bd-131">Odwołuje się ono do pracowników w Talent do wyodrębnienia szczegółów zarejestrowania i wyrejestrowania oraz nagrań wyjątku.</span><span class="sxs-lookup"><span data-stu-id="686bd-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="686bd-132">Szczegóły zarejestrowania i wyrejestrowania znajdują się w niestandardowych jednostkach Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="686bd-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="686bd-133">Zakłada się, że te szczegóły są wypełniane na podstawie informacji w systemach zewnętrznych poprzez integrację.</span><span class="sxs-lookup"><span data-stu-id="686bd-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="686bd-134">Ta aplikacja może zostać rozszerzona, tak aby można było jej używać w innych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="686bd-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="686bd-135">Na przykład może służyć do wyświetlania informacji dotyczących urlopu zespołu, zdarzeń kalendarza i zdarzeń specyficznych dla zespołu.</span><span class="sxs-lookup"><span data-stu-id="686bd-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="686bd-136">Aby pobrać aplikację **Integracja z Office 365** i strukturę jednostki niestandardowej, przejdź do [Integracja z Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="686bd-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="686bd-137">Przepływ — powiadomienie pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="686bd-137">Flow – Email Notification</span></span>

<span data-ttu-id="686bd-138">Szablon **Przepływ — powiadomienie pocztą e-mail** może być używany w scenariuszach powiadamiania pocztą e-mail.</span><span class="sxs-lookup"><span data-stu-id="686bd-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="686bd-139">Może służyć do wyzwalania wiadomości e-mail z powiadomieniem kandydatów, których zespół rekrutacyjny odrzuci na dowolnym etapie procesu rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="686bd-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="686bd-140">Ten szablon można rozszerzyć w celu śledzenia zmian w fazie kandydata w całym procesie rekrutacji i do wysyłania powiadomień do zespołu rekrutacyjnego oraz kandydata.</span><span class="sxs-lookup"><span data-stu-id="686bd-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="686bd-141">Generalnie, w przypadku jednostek zapisanych w Common Data Service, przepływy można ustawić tak, aby system wysyłał powiadomienia dotyczące zdarzeń w Core HR, Attract lub Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="686bd-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Dynamics 365 Talent: Onboard.</span></span>

<span data-ttu-id="686bd-142">Aby pobrać szablon **przepływ — powiadomienie pocztą e-mail**, przejdź do [przepływ — powiadomienie pocztą E-mail](https://go.microsoft.com/fwlink/?linkid=2082103) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="686bd-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="686bd-143">Przepływ — połączenie SQL i wykonywanie</span><span class="sxs-lookup"><span data-stu-id="686bd-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="686bd-144">Szablon **Przepływ — połączenie SQL i wykonywanie** łączy się z Microsoft SQL Server i umożliwia uruchamianie kwerend przez SQL.</span><span class="sxs-lookup"><span data-stu-id="686bd-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="686bd-145">Chociaż ten szablon jest przeznaczony do odczytu i aktualizowania tabel SQL, może zostać rozszerzony, tak aby można było z niego korzystać także w innych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="686bd-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="686bd-146">Na przykład, jego może służyć do wypełnienia tabeli tymczasowej Common Data Service rekordami z programu SQL Server i do okresowego synchronizowania tabeli tymczasowej przy użyciu wypychania przyrostowego z programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="686bd-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="686bd-147">Aby pobrać szablon **Przepływ — połączenie SQL i wykonywanie**, przejdź do sekcji [Przepływ — połączenie SQL i wykonywanie](https://go.microsoft.com/fwlink/?linkid=2081789) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="686bd-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="686bd-148">Przepływ — integracja z SharePoint</span><span class="sxs-lookup"><span data-stu-id="686bd-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="686bd-149">Szablon **Przepływ — integracja z SharePoint** może służyć do odczytywania danych z listy programu SharePoint, porównywania listy z wartościami pól dla jednostek Common Data Service i wysyłania wyników porównań w wiadomości e-mail z powiadomieniem.</span><span class="sxs-lookup"><span data-stu-id="686bd-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="686bd-150">Organizacja może mieć zestaw umiejętności, które są pilnie wymagane.</span><span class="sxs-lookup"><span data-stu-id="686bd-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="686bd-151">Te kwalifikacje można przechowywać w SharePoint jako listy SharePoint.</span><span class="sxs-lookup"><span data-stu-id="686bd-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="686bd-152">Gdy kandydat złoży podanie o pracę na stanowisku, dla którego jest lista wymaganych kwalifikacji, jeśli jest dostateczny poziom dopasowania między kwalifikacjami kandydata a kwalifikacjami zapisanymi w SharePoint, zostanie wysłane powiadomienie e-mail.</span><span class="sxs-lookup"><span data-stu-id="686bd-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="686bd-153">W ten sposób stanowiska, które wymagają pilnego obsadzenia, są obsadzane szybciej, ponieważ powiadomienia pomagają rekruterom znajdować i zatrudniać kandydatów wewnątrz organizacji.</span><span class="sxs-lookup"><span data-stu-id="686bd-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="686bd-154">Ten szablon może zostać rozszerzony tak, aby można go było używać w dowolnych scenariuszach uwzględniających integrację SharePoint.</span><span class="sxs-lookup"><span data-stu-id="686bd-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="686bd-155">Aby pobrać szablon **przepływ — integracja SharePoint**, przejdź do [przepływ — integracja SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="686bd-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="admin-console-to-manage-talent-pools"></a><span data-ttu-id="686bd-156">Konsola administracyjna do zarządzania pulami talentów</span><span class="sxs-lookup"><span data-stu-id="686bd-156">Admin console to manage talent pools</span></span>

<span data-ttu-id="686bd-157">Po włączeniu integracji z usługą LinkedIn Attract automatycznie tworzy pulę talentów w serwisie LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="686bd-157">When you enable integration with LinkedIn, Attract automatically createas a LinkedIn talent pool.</span></span> <span data-ttu-id="686bd-158">Kiedy osoba rekrutująca wymienia InMail z osobą rekrutowaną na LinkedIn, Attract tworzy profil osoby rekrutowanej i ta osoba staje się członkiem puli talentów serwisu LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="686bd-158">When a recruiter exchanges InMail with a recruit through LinkedIn, Attract creates a profile for the recruit, and the recruit becomes a member of the LinkedIn talent pool.</span></span> <span data-ttu-id="686bd-159">Ta aplikacja PowerApps jest przydatna do reorganizacji kandydatów w pulach talentów na podstawie kwalifikacji.</span><span class="sxs-lookup"><span data-stu-id="686bd-159">This PowerApps app is useful for reorganizing candidates in talent pools based on skill.</span></span>

<span data-ttu-id="686bd-160">Uruchom tę aplikację PowerApps jako konsolę administracyjną, aby wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="686bd-160">Run this PowerApps app as an admin console to perform the following tasks:</span></span>

- <span data-ttu-id="686bd-161">Sporządzenie listy kandydatów w puli talentów</span><span class="sxs-lookup"><span data-stu-id="686bd-161">List candidates in a talent pool</span></span>
- <span data-ttu-id="686bd-162">Dodawanie kandydatów do puli talentów i usuwanie</span><span class="sxs-lookup"><span data-stu-id="686bd-162">Add and remove candidates from a talent pool</span></span>
- <span data-ttu-id="686bd-163">Przenoszenie kandydatów z jednej puli talentów do drugiej</span><span class="sxs-lookup"><span data-stu-id="686bd-163">Move candidates from one talent pool to another</span></span>
- <span data-ttu-id="686bd-164">Przed przeniesieniem należy określić, czy kandydaci są już częścią puli talentów</span><span class="sxs-lookup"><span data-stu-id="686bd-164">Determine whether candidates are already part of a talent pool before moving them</span></span>
- <span data-ttu-id="686bd-165">Sprawdź umiejętności kandydatów przed przeniesieniem ich do innych pul talentów</span><span class="sxs-lookup"><span data-stu-id="686bd-165">Check the skills of candidates before moving them to other talent pools</span></span>

<span data-ttu-id="686bd-166">Ta aplikacja PowerApps używa relacji typu wiele-do-wielu, więc można jej użyć jako szablonu dla innych scenariuszy, w których jest konieczne wyodrębnienie rekordów z relacjami typu „wiele do wielu”.</span><span class="sxs-lookup"><span data-stu-id="686bd-166">This PowerApps app uses many-to-many relationships, so you can use it as a template for other scenarios where you need to extract records that have many-to-many relationships.</span></span>

<span data-ttu-id="686bd-167">Aby pobrać szablon **konsola administracyjna do zarządzania pulami talentów**, przejdź do [konsola administracyjna do zarządzania pulami talentów](https://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="686bd-167">To download the **Admin console to manage talent pools** template,  go to [Admin console to manage talent pools](https://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="686bd-168">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="686bd-168">Additional resources</span></span>

[<span data-ttu-id="686bd-169">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="686bd-169">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="686bd-170">Migracja aplikacji między dzierżawcami i środowiskami</span><span class="sxs-lookup"><span data-stu-id="686bd-170">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
