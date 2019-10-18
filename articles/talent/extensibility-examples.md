---
title: Rozszerzanie rozwiązania Talent przy użyciu usług PowerApps i Microsoft Flow — przykładowe scenariusze
description: W tym temacie opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Talent używanych przez Microsoft PowerApps i Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 Talent;PowerApps;Flow;Common Data Service
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
ms.openlocfilehash: 7bc3a18327f2d32770176eddcb7200681f0fb0da
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008066"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="0172b-103">Rozszerzanie rozwiązania Talent przy użyciu usług PowerApps i Microsoft Flow — przykładowe scenariusze</span><span class="sxs-lookup"><span data-stu-id="0172b-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="0172b-104">W tym temacie opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Talent używanych przez Microsoft PowerApps i Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="0172b-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="0172b-105">Można zaimportować pakiet rozwiązań skojarzony z każdym przykładem do środowiska PowerApps.</span><span class="sxs-lookup"><span data-stu-id="0172b-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="0172b-106">Następnie można używać pakietów jako pomocy lub punktów początkowych do implementacji scenariuszy odpowiednich dla Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="0172b-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0172b-107">Jeśli chcesz korzystać z szablonów i aplikacji, które zostały opisane w tym temacie „tak jak są”, sprawdź je, aby upewnić się, że będą one obejmować wszystkie scenariusze, które są specyficzne dla danej implementacji.</span><span class="sxs-lookup"><span data-stu-id="0172b-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="0172b-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="0172b-108">Prerequisites</span></span>

- <span data-ttu-id="0172b-109">Aby zaimportować pakiety, użytkownicy muszą mieć uprawnienie **Twórca środowisk**.</span><span class="sxs-lookup"><span data-stu-id="0172b-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="0172b-110">Aby eksportować lub importować aplikacje, musisz mieć licencję PowerApps plan 2 lub licencję próbną PowerApps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="0172b-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="0172b-111">Przepływ — połączenie formularza</span><span class="sxs-lookup"><span data-stu-id="0172b-111">Flow – Form Connect</span></span>

<span data-ttu-id="0172b-112">Szablon **Przepływ — połączenie formularza** może być używany do odczytu danych z programu Microsoft Forms i zapisania ich w jednostce Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0172b-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="0172b-113">Ten szablon może zostać rozszerzony, tak aby można było go używać w innych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="0172b-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="0172b-114">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="0172b-114">Here are some examples:</span></span>

- <span data-ttu-id="0172b-115">Przechwytywanie ocen kandydata.</span><span class="sxs-lookup"><span data-stu-id="0172b-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="0172b-116">Przechwytywanie wyników z kwestionariuszy na kursie.</span><span class="sxs-lookup"><span data-stu-id="0172b-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="0172b-117">Kompilowanie biblioteki pytań na rozmowy kwalifikacyjne dla administratorów zasobów ludzkich (HR).</span><span class="sxs-lookup"><span data-stu-id="0172b-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="0172b-118">Przechwytywania oceny kandydata po rozmowie kwalifikacyjnej</span><span class="sxs-lookup"><span data-stu-id="0172b-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="0172b-119">W Microsoft Dynamics 365: Attract, formularze mogą pojawiać się w portalu dla kandydatów i kandydaci mogą wypełniać szczegóły.</span><span class="sxs-lookup"><span data-stu-id="0172b-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="0172b-120">Formularze mogą być również osadzone jako działania w szablonie stanowiska.</span><span class="sxs-lookup"><span data-stu-id="0172b-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="0172b-121">Po przesłaniu formularza przez kandydata Microsoft Flow przechwytuje przesłanie formularza, odczytuje dane i zapisuje je w jednostce Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0172b-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="0172b-122">Aby pobrać szablon **Przepływ — połączenie formularza** i strukturę jednostki niestandardowej, przejdź do sekcji [Przepływ — połączenie formularza](https://go.microsoft.com/fwlink/?linkid=2081988) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0172b-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="0172b-123">Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps</span><span class="sxs-lookup"><span data-stu-id="0172b-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="0172b-124">Szablon **Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps** może być używany jako punkt początkowy dla dowolnych scenariuszy PowerApps charakterystycznych dla Attract.</span><span class="sxs-lookup"><span data-stu-id="0172b-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="0172b-125">Zawiera on wszystkie parametry domyślne, które są przekazywane przez Attract, takie jak **Podanie o pracę**, **identyfikator kandydata**, i **JobID**.</span><span class="sxs-lookup"><span data-stu-id="0172b-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="0172b-126">Za pomocą tego szablonu można pobrać formularz oceny kandydata, dzięki czemu menedżer zatrudniający może wyświetlić ocenę wypełnioną przez kandydata.</span><span class="sxs-lookup"><span data-stu-id="0172b-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="0172b-127">Aplikacje, które są tworzone przy użyciu PowerApps mogą być osadzone w szablonie stanowiska w Attract.</span><span class="sxs-lookup"><span data-stu-id="0172b-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="0172b-128">Aby pobrać szablon **Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps** i strukturę jednostki niestandardowej, przejdź do [Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0172b-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="0172b-129">Integracja z programem Office 365</span><span class="sxs-lookup"><span data-stu-id="0172b-129">Integration with Office 365</span></span>

<span data-ttu-id="0172b-130">Aplikacja **Integracja z Office 365** może być używana do pobierania danych zespołu dla zarejestrowanych użytkowników z Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="0172b-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="0172b-131">Odwołuje się ono do pracowników w Talent do wyodrębnienia szczegółów zarejestrowania i wyrejestrowania oraz nagrań wyjątku.</span><span class="sxs-lookup"><span data-stu-id="0172b-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="0172b-132">Szczegóły zarejestrowania i wyrejestrowania znajdują się w niestandardowych jednostkach Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0172b-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="0172b-133">Zakłada się, że te szczegóły są wypełniane na podstawie informacji w systemach zewnętrznych poprzez integrację.</span><span class="sxs-lookup"><span data-stu-id="0172b-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="0172b-134">Ta aplikacja może zostać rozszerzona, tak aby można było jej używać w innych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="0172b-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="0172b-135">Na przykład może służyć do wyświetlania informacji dotyczących urlopu zespołu, zdarzeń kalendarza i zdarzeń specyficznych dla zespołu.</span><span class="sxs-lookup"><span data-stu-id="0172b-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="0172b-136">Aby pobrać aplikację **Integracja z Office 365** i strukturę jednostki niestandardowej, przejdź do [Integracja z Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0172b-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="0172b-137">Przepływ — powiadomienie pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="0172b-137">Flow – Email Notification</span></span>

<span data-ttu-id="0172b-138">Szablon **Przepływ — powiadomienie pocztą e-mail** może być używany w scenariuszach powiadamiania pocztą e-mail.</span><span class="sxs-lookup"><span data-stu-id="0172b-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="0172b-139">Może służyć do wyzwalania wiadomości e-mail z powiadomieniem kandydatów, których zespół rekrutacyjny odrzuci na dowolnym etapie procesu rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="0172b-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="0172b-140">Ten szablon można rozszerzyć w celu śledzenia zmian w fazie kandydata w całym procesie rekrutacji i do wysyłania powiadomień do zespołu rekrutacyjnego oraz kandydata.</span><span class="sxs-lookup"><span data-stu-id="0172b-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="0172b-141">Generalnie, w przypadku jednostek zapisanych w Common Data Service, przepływy można ustawić tak, aby system wysyłał powiadomienia dotyczące zdarzeń w Core HR, Attract lub Onboard.</span><span class="sxs-lookup"><span data-stu-id="0172b-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Onboard.</span></span>

<span data-ttu-id="0172b-142">Aby pobrać szablon **przepływ — powiadomienie pocztą e-mail**, przejdź do [przepływ — powiadomienie pocztą E-mail](https://go.microsoft.com/fwlink/?linkid=2082103) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0172b-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="0172b-143">Przepływ — połączenie SQL i wykonywanie</span><span class="sxs-lookup"><span data-stu-id="0172b-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="0172b-144">Szablon **Przepływ — połączenie SQL i wykonywanie** łączy się z Microsoft SQL Server i umożliwia uruchamianie kwerend przez SQL.</span><span class="sxs-lookup"><span data-stu-id="0172b-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="0172b-145">Chociaż ten szablon jest przeznaczony do odczytu i aktualizowania tabel SQL, może zostać rozszerzony, tak aby można było z niego korzystać także w innych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="0172b-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="0172b-146">Na przykład, jego może służyć do wypełnienia tabeli tymczasowej Common Data Service rekordami z programu SQL Server i do okresowego synchronizowania tabeli tymczasowej przy użyciu wypychania przyrostowego z programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0172b-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="0172b-147">Aby pobrać szablon **Przepływ — połączenie SQL i wykonywanie**, przejdź do sekcji [Przepływ — połączenie SQL i wykonywanie](https://go.microsoft.com/fwlink/?linkid=2081789) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0172b-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="0172b-148">Przepływ — integracja z SharePoint</span><span class="sxs-lookup"><span data-stu-id="0172b-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="0172b-149">Szablon **Przepływ — integracja z SharePoint** może służyć do odczytywania danych z listy programu SharePoint, porównywania listy z wartościami pól dla jednostek Common Data Service i wysyłania wyników porównań w wiadomości e-mail z powiadomieniem.</span><span class="sxs-lookup"><span data-stu-id="0172b-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="0172b-150">Organizacja może mieć zestaw umiejętności, które są pilnie wymagane.</span><span class="sxs-lookup"><span data-stu-id="0172b-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="0172b-151">Te kwalifikacje można przechowywać w SharePoint jako listy SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0172b-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="0172b-152">Gdy kandydat złoży podanie o pracę na stanowisku, dla którego jest lista wymaganych kwalifikacji, jeśli jest dostateczny poziom dopasowania między kwalifikacjami kandydata a kwalifikacjami zapisanymi w SharePoint, zostanie wysłane powiadomienie e-mail.</span><span class="sxs-lookup"><span data-stu-id="0172b-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="0172b-153">W ten sposób stanowiska, które wymagają pilnego obsadzenia, są obsadzane szybciej, ponieważ powiadomienia pomagają rekruterom znajdować i zatrudniać kandydatów wewnątrz organizacji.</span><span class="sxs-lookup"><span data-stu-id="0172b-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="0172b-154">Ten szablon może zostać rozszerzony tak, aby można go było używać w dowolnych scenariuszach uwzględniających integrację SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0172b-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="0172b-155">Aby pobrać szablon **przepływ — integracja SharePoint**, przejdź do [przepływ — integracja SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0172b-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="0172b-156">Aplikacja Poleceń</span><span class="sxs-lookup"><span data-stu-id="0172b-156">Referral App</span></span>
<span data-ttu-id="0172b-157">Za pomocą aplikacji Poleceń można dodawać kandydatów do udostępnionej puli talentów.</span><span class="sxs-lookup"><span data-stu-id="0172b-157">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="0172b-158">Osoba polecająca może wprowadzić wartość **Imię**, **Nazwisko**, **Adres e-mail** i **Linkedln URL** podczas przesyłania kandydata.</span><span class="sxs-lookup"><span data-stu-id="0172b-158">The referrer can enter **Firstname**, **Lastname**, **Email**, and **Linkedln URL** when submitting a candidate.</span></span> <span data-ttu-id="0172b-159">Metadane źródła kandydata są następnie wypełniane informacjami osoby polecającej.</span><span class="sxs-lookup"><span data-stu-id="0172b-159">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="0172b-160">Tę aplikację można osadzić w module Samoobsługa pracownika (ESS) w celu przesłania polecenia lub można używać jej jako hiperłącza w portalu korporacyjnym i uruchamiać jako autonomiczną aplikację.</span><span class="sxs-lookup"><span data-stu-id="0172b-160">You can embed this app in Employee self-service (ESS) for submitting referrals, or you can be use it as a hyperlink in the Corporate Portal and run as a stand-alone app.</span></span>

<span data-ttu-id="0172b-161">Aby pobrać **Aplikację Poleceń**, przejdź do [Dynamics 365 Talent do rozwiązania rozszerzalności: Aplikacja Poleceń](http://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) w Microsoft — Centrum pobierania.</span><span class="sxs-lookup"><span data-stu-id="0172b-161">To download **Referral App**, go to [Dynamics 365 Talent extensibility solution: Referral App](http://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) on the Microsoft Download Center.</span></span> <span data-ttu-id="0172b-162">Możesz zaimportować tę aplikację i dostosować ją w celu dodania dodatkowych funkcji.</span><span class="sxs-lookup"><span data-stu-id="0172b-162">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0172b-163">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0172b-163">Additional resources</span></span>

[<span data-ttu-id="0172b-164">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="0172b-164">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="0172b-165">Migracja aplikacji między dzierżawcami i środowiskami</span><span class="sxs-lookup"><span data-stu-id="0172b-165">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
