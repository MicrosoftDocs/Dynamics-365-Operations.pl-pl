---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (6 maja 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6a4571abdb0e104af0a0657c75bf5a6b5764345a
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023868"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-6-2019"></a><span data-ttu-id="db4c5-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (6 maja 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="db4c5-103">What's new or changed in Dynamics 365 Talent (May 6, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="db4c5-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="db4c5-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="db4c5-105">Zmiany w Attract</span><span class="sxs-lookup"><span data-stu-id="db4c5-105">Changes in Attract</span></span>

### <a name="select-optional-documents-upon-offer-creation"></a><span data-ttu-id="db4c5-106">Wybierz opcjonalne dokumenty po utworzeniu oferty</span><span class="sxs-lookup"><span data-stu-id="db4c5-106">Select optional documents upon offer creation</span></span>

<span data-ttu-id="db4c5-107">Po wybraniu szablonu pakietu oferty Attract wyświetla teraz monit o wybranie odpowiednich, opcjonalnych dokumentów z tego szablonu pakietu.</span><span class="sxs-lookup"><span data-stu-id="db4c5-107">When you select an offer package template, Attract now prompts you to select the applicable, optional documents from that package template.</span></span> <span data-ttu-id="db4c5-108">Podczas przygotowywania oferty można dodawać inne opcjonalne dokumenty.</span><span class="sxs-lookup"><span data-stu-id="db4c5-108">You can add other optional documents while preparing the offer.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="db4c5-109">Zmiany w Onboard</span><span class="sxs-lookup"><span data-stu-id="db4c5-109">Changes in Onboard</span></span>

<span data-ttu-id="db4c5-110">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="db4c5-110">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="db4c5-111">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="db4c5-111">Changes in Core HR</span></span>

<span data-ttu-id="db4c5-112">Zmiany opisane w tej części dotyczą kompilacji 8.1.2282.</span><span class="sxs-lookup"><span data-stu-id="db4c5-112">Changes described in this section apply to build number 8.1.2282.</span></span> <span data-ttu-id="db4c5-113">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="db4c5-113">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="platform-update-26-for-finance-and-operations"></a><span data-ttu-id="db4c5-114">Aktualizacja Platform update 26 dla Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="db4c5-114">Platform update 26 for Finance and Operations</span></span>

<span data-ttu-id="db4c5-115">Aby uzyskać więcej informacji dotyczących 26. aktualizacji platformy dla rozwiązania Finance and Operations, zobacz [Podgląd funkcji w 26. aktualizacji platformy Dynamics 365 Finance and Operations (maj 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26).</span><span class="sxs-lookup"><span data-stu-id="db4c5-115">For additional details about Platform update 26 for Finance and Operations, see [Preview features in Dynamics 365 Finance and Operations platform update 26 (May 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26).</span></span> 

### <a name="common-data-service-entity-support-for-custom-fields"></a><span data-ttu-id="db4c5-116">Obsługa jednostek w Common Data Service dla pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="db4c5-116">Common Data Service entity support for custom fields</span></span>

<span data-ttu-id="db4c5-117">W wydaniu z tego tygodnia następujące jednostki obsługują obecnie niestandardowe pola: częstotliwość obliczania świadczeń, stawka obliczania świadczeń, typ świadczenia, kalendarz pracy, dzień wolny, cykl płac i typy identyfikacji pracowników.</span><span class="sxs-lookup"><span data-stu-id="db4c5-117">In this week's release, the following entities now support custom fields: Benefit calc frequency, Benefit calc rate, Benefit type, Work calendar, Work calendar holiday, Pay cycle, and Worker identification types.</span></span>

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a><span data-ttu-id="db4c5-118">Pozostawienie rejestracji grupowej przy zmianie podstawy warstwy na „Data stażu pracy” nie powoduje odświeżenia początkowej stawki naliczania (318526)</span><span class="sxs-lookup"><span data-stu-id="db4c5-118">Leave mass enrollment, changing the tier basis to "Seniority date" doesn't refresh the initial accrual rate (318526)</span></span>

<span data-ttu-id="db4c5-119">Po grupowym zarejestrowaniu pracowników i zmianie podstawy warstwy, początkowe naliczenie będzie teraz odzwierciedlać wybraną podstawę warstwy.</span><span class="sxs-lookup"><span data-stu-id="db4c5-119">When you mass enroll employees and change the tier basis, the initial accrual now reflects the tier basis that you selected.</span></span>

### <a name="workflow-showing-duplicate-place-holders-313636"></a><span data-ttu-id="db4c5-120">Przepływ pracy pokazujący zduplikowane symbole zastępcze (313636)</span><span class="sxs-lookup"><span data-stu-id="db4c5-120">Workflow showing duplicate place holders (313636)</span></span>

<span data-ttu-id="db4c5-121">Zmiany w tej wersji eliminują duplikowanie symboli zastępczych, gdy są wysyłane powiadomienia dotyczące przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="db4c5-121">Changes in this release eliminate duplication of placeholders when workflow notifications are sent.</span></span>

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a><span data-ttu-id="db4c5-122">Pola wymiaru nie są aktualizowane, gdy jest używane polecenie „Otwórz w programie Excel” (176261)</span><span class="sxs-lookup"><span data-stu-id="db4c5-122">Dimension fields aren't updated when using "Open in Excel" (176261)</span></span>

<span data-ttu-id="db4c5-123">W tej wersji można teraz zaktualizować wymiar finansowy za pomocą polecenia **Otwórz w programie Excel** ze strony **pracownik**.</span><span class="sxs-lookup"><span data-stu-id="db4c5-123">With this release, you can now update financial dimension using **Open in Excel** from the **Worker** page.</span></span> 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a><span data-ttu-id="db4c5-124">Adres pracownika utworzony w Common Data Service nie jest zsynchronizowany z aplikacją Talent (317555)</span><span class="sxs-lookup"><span data-stu-id="db4c5-124">Worker address created in Common Data Service isn't synced to Talent (317555)</span></span>

<span data-ttu-id="db4c5-125">Wraz z tą zmianą adresy utworzone w Common Data Service są aktualizowane w aplikacji Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="db4c5-125">With this change, addresses created in Common Data Service are updated in Talent: Core HR.</span></span>


## <a name="in-preview"></a><span data-ttu-id="db4c5-126">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="db4c5-126">In preview</span></span>

### <a name="new-page-to-validate-position-hierarchy-data"></a><span data-ttu-id="db4c5-127">Nowa strona do sprawdzania poprawności danych hierarchii stanowisk</span><span class="sxs-lookup"><span data-stu-id="db4c5-127">New page to validate position hierarchy data</span></span>

<span data-ttu-id="db4c5-128">Zasoby ludzkie (HR) i administratorzy mogą teraz sprawdzać hierarchię kadry kierowniczej dla wszystkich odwołań cyklicznych, które mogłyby zostać przypadkowo zaimportowane.</span><span class="sxs-lookup"><span data-stu-id="db4c5-128">Human resources (HR) and administrators can now validate the managerial hierarchy for any circular references that might have inadvertently been imported.</span></span> <span data-ttu-id="db4c5-129">Dostęp do tej nowej strony można uzyskać z menu **Administracja organizacyjna > Łącza > Stanowiska > Sprawdzanie poprawności hierarchii stanowisk**.</span><span class="sxs-lookup"><span data-stu-id="db4c5-129">You can access this new page from **Organizational administration > Links > Positions > Position hierarchy validation**.</span></span>

### <a name="specify-reason-codes-on-leave-types"></a><span data-ttu-id="db4c5-130">Określ kody przyczyn dla typów urlopów</span><span class="sxs-lookup"><span data-stu-id="db4c5-130">Specify reason codes on leave types</span></span>

<span data-ttu-id="db4c5-131">Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop.</span><span class="sxs-lookup"><span data-stu-id="db4c5-131">Organizations might require additional information about time-off requests.</span></span> <span data-ttu-id="db4c5-132">Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.</span><span class="sxs-lookup"><span data-stu-id="db4c5-132">You can now specify reason codes for leave types and let employees select a reason code on their time-off requests.</span></span>

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a><span data-ttu-id="db4c5-133">Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.</span><span class="sxs-lookup"><span data-stu-id="db4c5-133">Require reason codes for specific leave types on time-off requests</span></span>

<span data-ttu-id="db4c5-134">Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy.</span><span class="sxs-lookup"><span data-stu-id="db4c5-134">Organizations might require reason codes for specific leave types when employees submit time-off requests.</span></span> <span data-ttu-id="db4c5-135">To wymaganie może obowiązywać z powodu zasad dotyczących firmy lub przepisów prawa.</span><span class="sxs-lookup"><span data-stu-id="db4c5-135">This requirement might exist because of company policy or regulatory requirements.</span></span> <span data-ttu-id="db4c5-136">Teraz można określić typy urlopów wymagające podania kodu przyczyny i można wymagać, aby pracownicy podawali powód dla typu urlopu we wniosku.</span><span class="sxs-lookup"><span data-stu-id="db4c5-136">You can now specify which leave types require a reason code, and you can require that employees provide a reason code for the leave type on their time-off requests.</span></span>

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a><span data-ttu-id="db4c5-137">Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich</span><span class="sxs-lookup"><span data-stu-id="db4c5-137">Provide a leave and absence transaction list for HR</span></span>

<span data-ttu-id="db4c5-138">Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny.</span><span class="sxs-lookup"><span data-stu-id="db4c5-138">The ability to track employee time off and understand how time off is calculated not only helps HR answer employee questions, but also helps ensure accurate time-off awards for employees.</span></span> <span data-ttu-id="db4c5-139">Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldem.</span><span class="sxs-lookup"><span data-stu-id="db4c5-139">HR now has a new view into the transactions (grants, accruals, adjustments, and requests), so that HR staff can view the reasons behind balances.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="db4c5-140">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="db4c5-140">Coming soon</span></span>

### <a name="indicate-instance-type-when-provisioning-talent"></a><span data-ttu-id="db4c5-141">Wskaż typ wystąpienia podczas inicjowania obsługi administracyjnej w aplikacji Talent</span><span class="sxs-lookup"><span data-stu-id="db4c5-141">Indicate instance type when provisioning Talent</span></span>

<span data-ttu-id="db4c5-142">Podczas inicjowania obsługi nowego wystąpienia aplikacji Talent można wskazać, czy typ wystąpienia to **produkcja** czy **piaskownica**, co pozwala na wczesne testowanie nowych funkcji.</span><span class="sxs-lookup"><span data-stu-id="db4c5-142">When provisioning a new instance of Talent, you will be able to indicate whether the instance type is **Production** or **Sandbox**, allowing for early testing of new features.</span></span> <span data-ttu-id="db4c5-143">Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia produkcji.</span><span class="sxs-lookup"><span data-stu-id="db4c5-143">All existing Talent instances will be updated to the Production instance type.</span></span> <span data-ttu-id="db4c5-144">Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia piaskownicy, skontaktuj się z pomocą techniczną, aby zainicjować żądanie zmiany.</span><span class="sxs-lookup"><span data-stu-id="db4c5-144">If you want one of your existing instances to be updated to the Sandbox instance type, please contact Support to initiate the change request.</span></span>
