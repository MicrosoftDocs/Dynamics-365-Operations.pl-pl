---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (13 maja 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/13/2019
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
ms.search.validFrom: 2019-05-13
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ab201e099a5075760c038d819759162682874a33
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896928"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-13-2019"></a><span data-ttu-id="50196-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (13 maja 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="50196-103">What's new or changed in Dynamics 365 Talent (May 13, 2019)</span></span>

<span data-ttu-id="50196-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="50196-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="coming-soon-in-attract"></a><span data-ttu-id="50196-105">Wkrótce w aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="50196-105">Coming soon in Attract</span></span>

### <a name="job-approvals-on-home-page"></a><span data-ttu-id="50196-106">Zatwierdzenia zadań na stronie głównej</span><span class="sxs-lookup"><span data-stu-id="50196-106">Job approvals on home page</span></span>

<span data-ttu-id="50196-107">Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym.</span><span class="sxs-lookup"><span data-stu-id="50196-107">Approvals appear in an **Approvals** section on the dashboard.</span></span> <span data-ttu-id="50196-108">Osoby zatwierdzające mogą przeglądać swoje zatwierdzenia w obszarze **Przypisane do Ciebie**, w którym jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające i data przypisania.</span><span class="sxs-lookup"><span data-stu-id="50196-108">Approvers can review their approvals under **Assigned to you**, which displays the job ID, title, other approvers, and date assigned.</span></span> <span data-ttu-id="50196-109">Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania w obszarze **Żądane przez Ciebie**, w którym są wyświetlane osoby zatwierdzające, które muszą jeszcze zatwierdzić przesłane zadanie.</span><span class="sxs-lookup"><span data-stu-id="50196-109">Users who submit a job for approval can review their jobs under **Requested by you**, which displays the approvers who still need to approve the submitted job.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="50196-110">Zmiany w Onboard</span><span class="sxs-lookup"><span data-stu-id="50196-110">Changes in Onboard</span></span>

<span data-ttu-id="50196-111">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="50196-111">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="50196-112">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="50196-112">Changes in Core HR</span></span>

<span data-ttu-id="50196-113">Zmiany opisane w tej części dotyczą kompilacji 8.1.2297.</span><span class="sxs-lookup"><span data-stu-id="50196-113">Changes described in this section apply to build number 8.1.2297.</span></span> <span data-ttu-id="50196-114">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="50196-114">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="indicate-instance-type-when-provisioning-talent"></a><span data-ttu-id="50196-115">Wskaż typ wystąpienia podczas inicjowania obsługi administracyjnej w aplikacji Talent</span><span class="sxs-lookup"><span data-stu-id="50196-115">Indicate instance type when provisioning Talent</span></span>

<span data-ttu-id="50196-116">Podczas inicjowania obsługi nowego wystąpienia aplikacji Talent można wskazać, czy typ wystąpienia to **Produkcja** czy **Piaskownica**, co pozwala na wczesne testowanie nowych funkcji.</span><span class="sxs-lookup"><span data-stu-id="50196-116">When provisioning a new instance of Talent, you can indicate whether the instance type is **Production** or **Sandbox**, which allows for early testing of new features.</span></span> <span data-ttu-id="50196-117">Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**.</span><span class="sxs-lookup"><span data-stu-id="50196-117">All existing Talent instances will be updated to the **Production** instance type.</span></span> <span data-ttu-id="50196-118">Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.</span><span class="sxs-lookup"><span data-stu-id="50196-118">If you want one of your existing instances to be updated to the **Sandbox** instance type, please contact [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) to initiate the change request.</span></span>

### <a name="common-data-service-entity-support-for-custom-fields"></a><span data-ttu-id="50196-119">Obsługa jednostek w Common Data Service dla pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="50196-119">Common Data Service entity support for custom fields</span></span>

<span data-ttu-id="50196-120">W wydaniu z tego tygodnia następujące jednostki Common Data Service obsługują obecnie niestandardowe pola: zatrudnienie, częstotliwość obliczania świadczeń, stawka obliczania świadczeń, kalendarz pracy, dzień wolny i typy identyfikacji.</span><span class="sxs-lookup"><span data-stu-id="50196-120">In this week's release, the following Common Data Service entities now support custom fields: Employment, Benefit calc frequency, Benefit calc rate, Work calendar holiday, and Identification type.</span></span>

### <a name="common-data-service-integration-page"></a><span data-ttu-id="50196-121">Strona integracji Common Data Service</span><span class="sxs-lookup"><span data-stu-id="50196-121">Common Data Service integration page</span></span>

<span data-ttu-id="50196-122">W tej wersji znajduje się nowa opcja na stronie **Administrowanie systemem > Łącza > Integracje > Konfiguracja Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="50196-122">This release provides a new option in **System Administration > Links > Integrations > Common Data Service configuration**.</span></span> <span data-ttu-id="50196-123">Opcja **Konfiguracja Common Data Service** umożliwia administratorowi lub administratorowi zarządzania danymi pewną elastyczność i wgląd w działanie Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="50196-123">The **Common Data Service configuration** option allows an administrator or data management administrator some flexibility and insights with the Common Data Service.</span></span> <span data-ttu-id="50196-124">Za pomocą tej opcji można włączyć lub wyłączyć integrację Common Data Service z wystąpieniem aplikacji Talent i wyświetlić szczegóły synchronizacji między wystąpieniem aplikacji Talent a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="50196-124">With this option, you can enable or disable Common Data Service integration with a Talent instance and view the sync details between the Talent instance and the Common Data Service.</span></span>

### <a name="import-performance-data-with-final-employee-rating-316710"></a><span data-ttu-id="50196-125">Importowanie danych dotyczących wydajności z ostateczną oceną pracownika (316710)</span><span class="sxs-lookup"><span data-stu-id="50196-125">Import performance data with final employee rating (316710)</span></span>

<span data-ttu-id="50196-126">W tej wersji można zaimportować historyczne dane dotyczące oceny pracownika.</span><span class="sxs-lookup"><span data-stu-id="50196-126">In this release, you can import historical employee rating data.</span></span> <span data-ttu-id="50196-127">Pole **FinalEmployeeRatingId** ma teraz uprawnienia do zapisywania.</span><span class="sxs-lookup"><span data-stu-id="50196-127">The **FinalEmployeeRatingId** field now has write permission.</span></span>

### <a name="cant-create-worker-address-in-common-data-service-and-sync-it-with-talent-317555"></a><span data-ttu-id="50196-128">Nie można utworzyć adresu pracownika w Common Data Service i zsynchronizować go z aplikacją Talent (317555)</span><span class="sxs-lookup"><span data-stu-id="50196-128">Can't create Worker address in Common Data Service and sync it with Talent (317555)</span></span>

<span data-ttu-id="50196-129">Ta zmiana umożliwia synchronizowanie danych adresowych utworzonych w Common Data Service z aplikacją Talent.</span><span class="sxs-lookup"><span data-stu-id="50196-129">This change allows address data created in Common Data Service to sync with Talent.</span></span>

## <a name="in-preview"></a><span data-ttu-id="50196-130">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="50196-130">In preview</span></span>

### <a name="new-page-to-validate-position-hierarchy-data"></a><span data-ttu-id="50196-131">Nowa strona do sprawdzania poprawności danych hierarchii stanowisk</span><span class="sxs-lookup"><span data-stu-id="50196-131">New page to validate position hierarchy data</span></span>

<span data-ttu-id="50196-132">Zasoby ludzkie (HR) i administratorzy mogą sprawdzać hierarchię kadry kierowniczej dla wszystkich odwołań cyklicznych, które mogły zostać przypadkowo zaimportowane.</span><span class="sxs-lookup"><span data-stu-id="50196-132">Human resources (HR) and administrators can validate the managerial hierarchy for any circular references that might have been inadvertently imported.</span></span> <span data-ttu-id="50196-133">Dostęp do tej nowej strony można uzyskać z menu **Administracja organizacyjna > Łącza > Stanowiska > Sprawdzanie poprawności hierarchii stanowisk**.</span><span class="sxs-lookup"><span data-stu-id="50196-133">You can access this new page from **Organizational administration > Links > Positions > Position hierarchy validation**.</span></span>

### <a name="specify-reason-codes-on-leave-types"></a><span data-ttu-id="50196-134">Określ kody przyczyn dla typów urlopów</span><span class="sxs-lookup"><span data-stu-id="50196-134">Specify reason codes on leave types</span></span>

<span data-ttu-id="50196-135">Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop.</span><span class="sxs-lookup"><span data-stu-id="50196-135">Organizations might require additional information about time-off requests.</span></span> <span data-ttu-id="50196-136">Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.</span><span class="sxs-lookup"><span data-stu-id="50196-136">You can now specify reason codes for leave types and let employees select a reason code on their time-off requests.</span></span>

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a><span data-ttu-id="50196-137">Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.</span><span class="sxs-lookup"><span data-stu-id="50196-137">Require reason codes for specific leave types on time-off requests</span></span>

<span data-ttu-id="50196-138">Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy.</span><span class="sxs-lookup"><span data-stu-id="50196-138">Organizations might require reason codes for specific leave types when employees submit time-off requests.</span></span> <span data-ttu-id="50196-139">To wymaganie może obowiązywać z powodu zasad dotyczących firmy lub przepisów prawa.</span><span class="sxs-lookup"><span data-stu-id="50196-139">This requirement might exist because of company policy or regulatory requirements.</span></span> <span data-ttu-id="50196-140">Istnieje możliwość określenia typów urlopów wymagających podania kodu przyczyny i wymagania, aby pracownicy podawali powód dla typu urlopu we wniosku o urlop.</span><span class="sxs-lookup"><span data-stu-id="50196-140">You can specify which leave types require a reason code, and you can require that employees provide a reason code for the leave type on their time-off requests.</span></span>

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a><span data-ttu-id="50196-141">Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich</span><span class="sxs-lookup"><span data-stu-id="50196-141">Provide a leave and absence transaction list for HR</span></span>

<span data-ttu-id="50196-142">Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny.</span><span class="sxs-lookup"><span data-stu-id="50196-142">The ability to track employee time off and understand how time off is calculated not only helps HR answer employee questions, but also helps ensure accurate time-off awards for employees.</span></span> <span data-ttu-id="50196-143">Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldami czasu wolnego.</span><span class="sxs-lookup"><span data-stu-id="50196-143">HR now has a new view into the transactions (grants, accruals, adjustments, and requests), so that HR staff can view the reasons behind time-off balances.</span></span>
