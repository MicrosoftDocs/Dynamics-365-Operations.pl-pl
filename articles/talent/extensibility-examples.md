---
title: Rozszerz aplikację Talent o usługi Power Apps i Power Automate
description: W tym artykule opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Talent - Attract używanych przez Microsoft Power Apps i Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: cfdf36e9486aa4853d3bf674afa73ec3a4d1c161
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529641"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a><span data-ttu-id="cb3e2-103">Rozszerz aplikację Talent o usługi Power Apps i Power Automate</span><span class="sxs-lookup"><span data-stu-id="cb3e2-103">Extend Talent with Power Apps and Power Automate</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="cb3e2-104">W tym artykule opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Talent: Attract - Attract używanych przez Microsoft Power Apps i Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Talent: Attract that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="cb3e2-105">Można zaimportować pakiet rozwiązań skojarzony z każdym przykładem do środowiska Power Apps.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="cb3e2-106">Następnie można używać pakietów jako pomocy lub punktów początkowych do implementacji scenariuszy odpowiednich dla Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb3e2-107">Jeśli chcesz korzystać z szablonów i aplikacji, które zostały opisane w tym artykule „tak jak są”, sprawdź je, aby upewnić się, że będą one obejmować wszystkie scenariusze, które są specyficzne dla danej implementacji.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-107">If you want to use the templates and app that are described in this article "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="cb3e2-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="cb3e2-108">Prerequisites</span></span>

- <span data-ttu-id="cb3e2-109">Aby zaimportować pakiety, użytkownicy muszą mieć uprawnienie **Twórca środowisk**.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="cb3e2-110">Aby eksportować lub importować aplikacje, musisz mieć licencję Power Apps plan 2 lub licencję próbną Power Apps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="power-automate--form-connect"></a><span data-ttu-id="cb3e2-111">Power Automate — połączenie formularza</span><span class="sxs-lookup"><span data-stu-id="cb3e2-111">Power Automate – Form Connect</span></span>

<span data-ttu-id="cb3e2-112">**Power Automate — połączenie** formularza może być używany do odczytu danych z programu Microsoft Forms i zapisania ich w jednostce Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-112">The **Power Automate – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="cb3e2-113">Ten szablon może zostać rozszerzony, tak aby można było go używać w innych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="cb3e2-114">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="cb3e2-114">Here are some examples:</span></span>

- <span data-ttu-id="cb3e2-115">Przechwytywanie ocen kandydata.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="cb3e2-116">Przechwytywanie wyników z kwestionariuszy na kursie.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="cb3e2-117">Kompilowanie biblioteki pytań na rozmowy kwalifikacyjne dla administratorów zasobów ludzkich (HR).</span><span class="sxs-lookup"><span data-stu-id="cb3e2-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="cb3e2-118">Przechwytywania oceny kandydata po rozmowie kwalifikacyjnej</span><span class="sxs-lookup"><span data-stu-id="cb3e2-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="cb3e2-119">W Microsoft Dynamics 365: Attract, można używać formularzy w portalu dla kandydatów, gdzie kandydaci mogą wypełniać szczegóły.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-119">In Microsoft Dynamics 365: Attract, you can use forms in the candidate portal, where candidates fill in details.</span></span> <span data-ttu-id="cb3e2-120">Formularze mogą być również osadzone jako działania w szablonie stanowiska.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-120">You can also embed forms as activities in a job template.</span></span>

<span data-ttu-id="cb3e2-121">Po przesłaniu formularza przez kandydata Microsoft Power Automate przechwytuje przesłanie formularza, odczytuje dane i zapisuje je w jednostce Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-121">When a candidate submits a form, Microsoft Power Automate captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="cb3e2-122">Aby pobrać szablon **Power Automate— połączenie formularza** i strukturę jednostki niestandardowej, przejdź do sekcji [Power Automate — połączenie formularza](https://go.microsoft.com/fwlink/?linkid=2081988) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-122">To download the **Power Automate – Form Connect** template and Custom Entity Structure, go to [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sharepoint-integration"></a><span data-ttu-id="cb3e2-123">Power Automate – Integracja SharePoint</span><span class="sxs-lookup"><span data-stu-id="cb3e2-123">Power Automate – SharePoint Integration</span></span>

<span data-ttu-id="cb3e2-124">**Power Automate — integracja z SharePoint** może służyć do odczytywania danych z listy Microsoft SharePoint, porównywania listy z wartościami pól dla jednostek Common Data Service i wysyłania wyników porównań w wiadomości e-mail z powiadomieniem.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-124">The **Power Automate – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="cb3e2-125">Organizacja może mieć zestaw umiejętności, które są pilnie wymagane.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-125">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="cb3e2-126">Te kwalifikacje można przechowywać w SharePoint jako listy SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-126">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="cb3e2-127">Gdy kandydat złoży podanie o pracę na stanowisku, dla którego jest lista wymaganych kwalifikacji, jeśli jest dostateczny poziom dopasowania między kwalifikacjami kandydata a kwalifikacjami zapisanymi w SharePoint, zostanie wysłane powiadomienie e-mail.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-127">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="cb3e2-128">W ten sposób stanowiska, które wymagają pilnego obsadzenia, są obsadzane szybciej, ponieważ powiadomienia pomagają rekruterom znajdować i zatrudniać kandydatów wewnątrz organizacji.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-128">This helps fill positions that are urgently required faster, because the notifications help recruiters cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="cb3e2-129">Ten szablon może zostać rozszerzony tak, aby można go było używać w dowolnych scenariuszach uwzględniających integrację SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-129">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="cb3e2-130">Aby pobrać **Power Automate – SharePoint integracja**, przejdź do [Power Automate – integracja SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-130">To download the **Power Automate – SharePoint Integration** template, go to [Power Automate – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="cb3e2-131">Aplikacja Poleceń</span><span class="sxs-lookup"><span data-stu-id="cb3e2-131">Referral App</span></span>

<span data-ttu-id="cb3e2-132">Za pomocą aplikacji Poleceń można dodawać kandydatów do udostępnionej puli talentów.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-132">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="cb3e2-133">Osoba polecająca może wprowadzić wartość **Imię**, **Nazwisko**, **Adres e-mail** i **Linkedln URL** podczas przesyłania kandydata.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-133">The referrer can enter **Firstname**, **Lastname**, **Email**, and **LinkedIn URL** when submitting a candidate.</span></span> <span data-ttu-id="cb3e2-134">Metadane źródła kandydata są następnie wypełniane informacjami osoby polecającej.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-134">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="cb3e2-135">Tę aplikację można osadzić w module Samoobsługa pracownika (ESS) w celu przesłania polecenia lub można używać jej jako hiperłącza w portalu korporacyjnym i uruchamiać jako autonomiczną aplikację.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-135">You can embed this app in Employee self service for submitting referrals, or you can use it as a hyperlink in the corporate portal and run it as a stand-alone app.</span></span>

<span data-ttu-id="cb3e2-136">Aby pobrać **Aplikację Poleceń**, przejdź do [Dynamics 365 Talent do rozwiązania rozszerzalności: Aplikacja Poleceń](https://www.microsoft.com/download/details.aspx?id=58497) w Microsoft — Centrum pobierania.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-136">To download **Referral App**, go to [Dynamics 365 Talent extensibility solution: Referral App](https://www.microsoft.com/download/details.aspx?id=58497) on the Microsoft Download Center.</span></span> <span data-ttu-id="cb3e2-137">Możesz zaimportować tę aplikację i dostosować ją w celu dodania dodatkowych funkcji.</span><span class="sxs-lookup"><span data-stu-id="cb3e2-137">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb3e2-138">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cb3e2-138">Additional resources</span></span>

[<span data-ttu-id="cb3e2-139">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="cb3e2-139">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="cb3e2-140">Migracja aplikacji między dzierżawcami i środowiskami</span><span class="sxs-lookup"><span data-stu-id="cb3e2-140">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
