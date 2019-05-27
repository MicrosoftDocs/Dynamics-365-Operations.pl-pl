---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (5 marca 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
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
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e4ad32ef71c87f52e59959d80c21ae7fcd6d6524
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518875"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-5-2019"></a><span data-ttu-id="57ae3-103">Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (5 marca 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="57ae3-103">What's new or changed in Dynamics 365 for Talent (March 5, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="57ae3-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Talent</span><span class="sxs-lookup"><span data-stu-id="57ae3-104">This topic describes features that are either new or changed in Talent</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="57ae3-105">Zmiany w Attract</span><span class="sxs-lookup"><span data-stu-id="57ae3-105">Changes in Attract</span></span>

### <a name="extending-option-sets-in-attract"></a><span data-ttu-id="57ae3-106">Rozszerzanie zestawów opcji w Attract</span><span class="sxs-lookup"><span data-stu-id="57ae3-106">Extending option sets in Attract</span></span>

<span data-ttu-id="57ae3-107">W Attract jest wiele pól będących zestawami opcji w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="57ae3-107">In Attract, there are multiple fields that are option sets within the Common Data Service.</span></span> <span data-ttu-id="57ae3-108">Wprowadzono nowe możliwości rozszerzania zestawów opcji, począwszy od pola przyczyny **odrzucenia**, pola **Typ zatrudnienia** i pola **typu stażu pracy**.</span><span class="sxs-lookup"><span data-stu-id="57ae3-108">New capabilities have been introduced to extend the option sets, beginning with the **Rejection** reason field, **Employment type** field, and **Seniority type** field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57ae3-109">Dodawanie oferty pracy do funkcji LinkedIn wymaga stosowania pól **Typ zatrudnienia** i **typu stażu pracy** na stronie **Szczegóły stanowiska**.</span><span class="sxs-lookup"><span data-stu-id="57ae3-109">The job posting to LinkedIn functionality requires the use of the **Employment type** and **Seniority type** fields on the **Job details** page.</span></span> <span data-ttu-id="57ae3-110">Domyślne wartości tych pól nie są obsługiwane przez LinkedIn i są wyświetlane, gdy oferta jest publikowana.</span><span class="sxs-lookup"><span data-stu-id="57ae3-110">The default values in these fields are supported by LinkedIn and are displayed when the job is posted.</span></span> <span data-ttu-id="57ae3-111">Jeśli publikujesz ofertę pracy na LinkedIn i zmienisz istniejące zestawy wartości dla tych pól, oferta zostanie opublikowana, ale LinkedIn nie wyświetli wartości niestandardowych **Typ zatrudnienia** i **typu stażu pracy**.</span><span class="sxs-lookup"><span data-stu-id="57ae3-111">If you are posting jobs to LinkedIn and you modify the existing option set values for these fields, the job will still post, but LinkedIn will not display the custom **Employment type** and **Seniority type** values.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="57ae3-112">Zmiany we wdrażaniu do pracy</span><span class="sxs-lookup"><span data-stu-id="57ae3-112">Changes in Onboarding</span></span>

### <a name="private-preview-for-onboard-teams"></a><span data-ttu-id="57ae3-113">Podgląd prywatny zespołów wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="57ae3-113">Private preview for Onboard teams</span></span>
<span data-ttu-id="57ae3-114">Teraz można łatwo udostępniać i współpracować w szablonach w całej organizacji.</span><span class="sxs-lookup"><span data-stu-id="57ae3-114">You can now easily share and collaborate on templates across your entire organization.</span></span> <span data-ttu-id="57ae3-115">Aby uzyskać więcej informacji, zobacz [udostępnienia najlepszych praktyk w całej organizacji przy pomocy zespołów wdrażania do pracy](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span><span class="sxs-lookup"><span data-stu-id="57ae3-115">For more information, see [Share best practices across your organization using Onboard Teams](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span></span>

### <a name="private-preview-for-assignee-placeholders"></a><span data-ttu-id="57ae3-116">Prywatny podgląd symboli zastępczych wykonawcy</span><span class="sxs-lookup"><span data-stu-id="57ae3-116">Private preview for assignee placeholders</span></span>
<span data-ttu-id="57ae3-117">Szablony można wzbogacać przez przypisanie działania do ról, a nie osobom.</span><span class="sxs-lookup"><span data-stu-id="57ae3-117">You can enrich your templates by assigning activities to roles instead of individuals.</span></span> <span data-ttu-id="57ae3-118">Role są następnie przypisywane do osób w momencie utworzenia przewodnika.</span><span class="sxs-lookup"><span data-stu-id="57ae3-118">Roles are then assigned to individuals at the time of guide creation.</span></span> <span data-ttu-id="57ae3-119">Aby uzyskać więcej informacji, zobacz [tworzenie Przewodnika po administracji przez przypisanie działania do ról](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span><span class="sxs-lookup"><span data-stu-id="57ae3-119">For more information, see [Streamline guide administration by assigning activities to roles](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="57ae3-120">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="57ae3-120">Changes in Core HR</span></span>
<span data-ttu-id="57ae3-121">**Kompilacja 8.1.2178**</span><span class="sxs-lookup"><span data-stu-id="57ae3-121">**Build 8.1.2178**</span></span>

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a><span data-ttu-id="57ae3-122">Konfigurowanie przepływu pracy do automatycznego zatwierdzania lub śledzenia przepływu pracy, gdy HR lub kierownik linii prześle albo zaktualizuje żądania czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="57ae3-122">Configure workflow to auto-approve or follow workflow when an HR or line manager submits or updates time off requests</span></span>
<span data-ttu-id="57ae3-123">Dodano nowe warunki przepływu pracy zezwalające na automatyczne zatwierdzanie żądań urlopów przesłanych przez kierownika lub dział HR.</span><span class="sxs-lookup"><span data-stu-id="57ae3-123">New workflow conditions have been added to allow for leave requests to be automatically approved if submitted by an employee’s manager or by HR.</span></span> <span data-ttu-id="57ae3-124">Jednym ze sposobów korzystania z tego automatycznego zatwierdzania dla przepływu pracy jest włączenie automatycznej akcji w zatwierdzaniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="57ae3-124">One way to achieve this auto-approval on a workflow is to enable an automatic action on the workflow approval.</span></span>

<span data-ttu-id="57ae3-125">Do dodanych warunków należą:</span><span class="sxs-lookup"><span data-stu-id="57ae3-125">The conditions that have been added include:</span></span>

- <span data-ttu-id="57ae3-126">Przesłane przez: używany do oceny identyfikatora systemowego użytkownika, który przesłał żądanie do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="57ae3-126">Submitted by - Used to evaluate the system user ID of the user who submitted the request to workflow.</span></span>
- <span data-ttu-id="57ae3-127">Przesłane w imieniu — używany do oceny, czy wniosek o urlop został przesłany w imieniu pracownika skojarzonego z wnioskiem.</span><span class="sxs-lookup"><span data-stu-id="57ae3-127">Submitted on behalf of - Used to evaluate if the leave request was submitted on behalf of the worker associated to the request.</span></span>
- <span data-ttu-id="57ae3-128">Przesłane przez zasoby ludzkie — używany do oceny, czy użytkownik systemu, który przesłał wniosek do przepływu pracy jest rolą modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="57ae3-128">Submitted by human resources - Used to evaluate if the system user who submitted the request to workflow is in a Human Resources role.</span></span>
- <span data-ttu-id="57ae3-129">Przesłane przez menedżera — używany do oceny, czy użytkownik, który przesłał wniosek o urlop do przepływu pracy, jest menedżerem linii pracownika skojarzonego z wnioskiem.</span><span class="sxs-lookup"><span data-stu-id="57ae3-129">Submitted by manager - Used to evaluate if the user who submitted the leave request to workflow is a line hierarchy manager of the worker associated to the request.</span></span>

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a><span data-ttu-id="57ae3-130">Włącz stałe wynagrodzenie dla przyszłych przypisań stanowisk</span><span class="sxs-lookup"><span data-stu-id="57ae3-130">Enable employee fixed compensation for future position assignments</span></span>
<span data-ttu-id="57ae3-131">Jest to typowe dla pracowników, którzy dołączają do organizacji w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="57ae3-131">It is typical for employees to join an organization with a future start date.</span></span> <span data-ttu-id="57ae3-132">Ta zmiana umożliwia definiowanie stałych wynagrodzeń dla pracowników z przyszłym przypisaniem stanowisk.</span><span class="sxs-lookup"><span data-stu-id="57ae3-132">This change enables defining fixed compensation for employees with future position assignments.</span></span>

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a><span data-ttu-id="57ae3-133">Pola Pozycja listy płac są puste podczas edytowania stanowiska</span><span class="sxs-lookup"><span data-stu-id="57ae3-133">Position Payroll fields are blank when editing the position</span></span>
<span data-ttu-id="57ae3-134">Wraz z tą zmianą, podczas żądania zmiany istniejących stanowisk, pola listy zostaną domyślnie wypełnione obecnymi wartościami.</span><span class="sxs-lookup"><span data-stu-id="57ae3-134">With this change, when requesting changes to existing positions, the payroll fields will now default to the current values.</span></span>

### <a name="other-miscellaneous-bug-fixes"></a><span data-ttu-id="57ae3-135">Inne dodatkowe poprawki błędów</span><span class="sxs-lookup"><span data-stu-id="57ae3-135">Other miscellaneous bug fixes</span></span>
<span data-ttu-id="57ae3-136">Inne niewielkie poprawki są dołączone do tej wersji.</span><span class="sxs-lookup"><span data-stu-id="57ae3-136">Other minor bug fixes are included with this release.</span></span>

### <a name="upgrade-to-common-data-service"></a><span data-ttu-id="57ae3-137">Uaktualnianie do rozwiązania Common Data Service</span><span class="sxs-lookup"><span data-stu-id="57ae3-137">Upgrade to Common Data Service</span></span>
<span data-ttu-id="57ae3-138">Zbliżają się terminy uaktualniania do Common Data Service dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="57ae3-138">Deadlines to upgrade to Common Data Service are quickly approaching.</span></span> <span data-ttu-id="57ae3-139">Zaloguj się do Centrum administracyjnego usługi PowerApps, aby określić, czy baza danych wymaga uaktualnienia.</span><span class="sxs-lookup"><span data-stu-id="57ae3-139">Sign in to the PowerApps Admin center to determine if your database needs to be upgraded.</span></span> <span data-ttu-id="57ae3-140">Aby uzyskać więcej informacji dotyczących terminów i niezbędne kroki w celu uaktualnienia, zobacz [uaktualnienia do Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).</span><span class="sxs-lookup"><span data-stu-id="57ae3-140">For more information about deadlines and necessary steps to upgrade, see [Upgrade to Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).</span></span>

## <a name="coming-soon"></a><span data-ttu-id="57ae3-141">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="57ae3-141">Coming soon</span></span>

###  <a name="advanced-compensation-security-fixed-and-variable"></a><span data-ttu-id="57ae3-142">Zaawansowane zabezpieczenia wynagrodzeń (stałe i zmienne)</span><span class="sxs-lookup"><span data-stu-id="57ae3-142">Advanced compensation security (fixed and variable)</span></span>
<span data-ttu-id="57ae3-143">W wielu organizacjach menedżerowie ds. wynagrodzeń i świadczeń mają dostęp tylko do określonych rekordów wynagrodzeń, takich jak rekordy dla kadry zarządzającej i pracowników regionalnych.</span><span class="sxs-lookup"><span data-stu-id="57ae3-143">In many organizations, compensation and benefits managers can only access certain compensation records, such as records for executives or regional-based employees.</span></span> <span data-ttu-id="57ae3-144">W przypadku tej zmiany można zarządzać różnymi planami wynagrodzeń dla różnych grup pracowników w organizacji.</span><span class="sxs-lookup"><span data-stu-id="57ae3-144">With this change, you can manage and maintain the compensation plans for different employee populations in the organization.</span></span> <span data-ttu-id="57ae3-145">Stałe i zmienne plany mogą mieć przypisane role zabezpieczeń, które będą określały dostęp do planów i danych pracowników związanych z planami, takich jak rekordy płac i premii.</span><span class="sxs-lookup"><span data-stu-id="57ae3-145">Fixed and variable plans can be assigned security roles, which will determine the access to the plans and the employee data related to the plans, such as salary or bonus records.</span></span> <span data-ttu-id="57ae3-146">Tylko role z danym dostępem mogą przetwarzać wynagrodzenia dla tych pracowników.</span><span class="sxs-lookup"><span data-stu-id="57ae3-146">Only the roles with the given access will be able to process compensation for those employees.</span></span>

###  <a name="platform-update-24"></a><span data-ttu-id="57ae3-147">Aktualizacja platformy Update 24</span><span class="sxs-lookup"><span data-stu-id="57ae3-147">Platform update 24</span></span>
<span data-ttu-id="57ae3-148">Aby uzyskać dodatkowe szczegółowe informacje dotyczące Platform update 24, zobacz [nowe lub zmienione funkcje w Platform update 24 Finance and Operations (2019 marca)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span><span class="sxs-lookup"><span data-stu-id="57ae3-148">For additional details about Platform update 24, see [What's new or changed in Finance and Operations platform update 24 (March 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span></span>
