---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (08 lipiec 2020)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 8 lipca 2020 roku.
author: Darinkramer
manager: AnnBe
ms.date: 07/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2f542195693e825391b85efc4a7e91fdfea3944
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "3711899"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a><span data-ttu-id="1045e-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (8 lipiec 2020)</span><span class="sxs-lookup"><span data-stu-id="1045e-103">What's new or changed in Dynamics 365 Human Resources (July 8, 2020)</span></span>

<span data-ttu-id="1045e-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1045e-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="1045e-105">Zmiany dotyczą kompilacji o numerze 8.1.3382.</span><span class="sxs-lookup"><span data-stu-id="1045e-105">Changes apply to build number 8.1.3382.</span></span> <span data-ttu-id="1045e-106">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="1045e-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="database-logging"></a><span data-ttu-id="1045e-107">Logowanie do bazy danych</span><span class="sxs-lookup"><span data-stu-id="1045e-107">Database logging</span></span>

<span data-ttu-id="1045e-108">Rejestrowanie bazy danych umożliwia określenie, która tabele i pola mają być monitorowane.</span><span class="sxs-lookup"><span data-stu-id="1045e-108">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="1045e-109">Umożliwia również określenie zdarzeń, które powinny uruchamiać śledzenie zmian.</span><span class="sxs-lookup"><span data-stu-id="1045e-109">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="1045e-110">Korzystasz z możliwości rejestrowania bazy danych, aby zobaczyć te zmiany w czasie.</span><span class="sxs-lookup"><span data-stu-id="1045e-110">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="1045e-111">Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie i zarządzanie rejestrowaniem bazy danych](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="1045e-111">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="1045e-112">Konfigurowanie nazwy Samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="1045e-112">Configure the name of Employee self service</span></span>

<span data-ttu-id="1045e-113">W **parametrach Human Resources** można teraz zmienić nazwę obszaru roboczego **Samoobsługa pracownika etatowego** na **Samoobsługa**.</span><span class="sxs-lookup"><span data-stu-id="1045e-113">In **Human Resources parameters**, you can now change the name of the **Employee self service** workspace to **Self service**.</span></span> <span data-ttu-id="1045e-114">Aby uzyskać więcej informacji, zajrzyj do [Zmień nazwę obszaru roboczego samoobsługi pracownika etatowego](hr-employee-self-service-workspace-name.md)</span><span class="sxs-lookup"><span data-stu-id="1045e-114">For more information, see [Change Employee self service workspace name](hr-employee-self-service-workspace-name.md)</span></span>

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a><span data-ttu-id="1045e-115">Zarządzanie świadczeniami umożliwia otwarcie dostępu do rejestracji poza okresem</span><span class="sxs-lookup"><span data-stu-id="1045e-115">Benefits management open enrollment access outside of period</span></span>

<span data-ttu-id="1045e-116">Ta wersja rozwiązuje usterkę, na której pracownicy mogą uzyskać dostęp do świadczeń otwartych poza okresem rejestracji lub bez zdarzenia życiowego.</span><span class="sxs-lookup"><span data-stu-id="1045e-116">This release fixes a bug where employees could access benefits open enrollment outside of the enrollment period or without a life event.</span></span> <span data-ttu-id="1045e-117">W wyniku tego, jeśli zachodzi potrzeba pokazania rejestracji w module samoobsługi pracownika etatowego, należy skorygować otwarte daty rejestracji do dnia dzisiejszego (lub wcześniejszej), aby je udostępnić.</span><span class="sxs-lookup"><span data-stu-id="1045e-117">As a result, if you need to demo open enrollment in Employee self service, you must adjust the open enrollment dates to today (or earlier) to make it accessible.</span></span> <span data-ttu-id="1045e-118">To ustawienie można zmienić w obszarze **Zarządzanie świadczeniami > Reguły i okresy opcji**.</span><span class="sxs-lookup"><span data-stu-id="1045e-118">You can change this setting under **Benefits management > Rules and options periods**.</span></span>

## <a name="email-employee-enrollment-confirmation"></a><span data-ttu-id="1045e-119">Potwierdzenie rejestracji pracownika w wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="1045e-119">Email employee enrollment confirmation</span></span>

<span data-ttu-id="1045e-120">Możesz teraz wysyłać wiadomości e-mail do pracowników, którzy ukończyli wybór świadczeń.</span><span class="sxs-lookup"><span data-stu-id="1045e-120">You can now send emails to employees after they complete their benefits selection.</span></span> <span data-ttu-id="1045e-121">Można albo wysłać wiadomość domyślną, albo skorzystać z szablonu wiadomości e-mail organizacji.</span><span class="sxs-lookup"><span data-stu-id="1045e-121">You can either send a default message or use an organization email template.</span></span> <span data-ttu-id="1045e-122">Te ustawienia znajdują się w obszarze **Parametry zasobów ludzkich > Zarządzanie świadczeniami**.</span><span class="sxs-lookup"><span data-stu-id="1045e-122">These settings are under **Human resource parameters > Benefits management**.</span></span>

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a><span data-ttu-id="1045e-123">Anulowane urlopy nadal są wyświetlane w obszarze roboczym Osoby (441358) w nadchodzącym czasie</span><span class="sxs-lookup"><span data-stu-id="1045e-123">Canceled leave still appears in upcoming time off on People workspace (441358)</span></span>

<span data-ttu-id="1045e-124">Anulowany urlop nie jest już wyświetlany jako zbliżający się czas wolny na kartach urlopów w obszarze roboczym **Osoby**.</span><span class="sxs-lookup"><span data-stu-id="1045e-124">Canceled leave no longer displays as upcoming time off on the leave cards in the **People** workspace.</span></span>

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a><span data-ttu-id="1045e-125">Nie można skorzystać z właściwości jednostki dział w jednostce PositionV2 (456486)</span><span class="sxs-lookup"><span data-stu-id="1045e-125">Unable to use the department entity property in the PositionV2 entity (456486)</span></span>

<span data-ttu-id="1045e-126">Teraz można dodać dział bez tworzenia zduplikowanej relacji.</span><span class="sxs-lookup"><span data-stu-id="1045e-126">You can now add a department without creating a duplicate relation.</span></span>

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a><span data-ttu-id="1045e-127">PayrollWorkerEnrolledBenefitDetailEntity powinny używać tylko pola obliczeniowego dla planów emerytalnych (459779)</span><span class="sxs-lookup"><span data-stu-id="1045e-127">PayrollWorkerEnrolledBenefitDetailEntity should only use calculated field for retirement plans (459779)</span></span>

<span data-ttu-id="1045e-128">Podczas eksportowania jednostki **PayrollWorkerEnrolledBenefitDetailEntity** eksport określa, czy powinien on używać pola obliczeniowego na podstawie tabeli stawek, czy też należy używać pola **ContributionAmountCur** w tabeli zapasowej.</span><span class="sxs-lookup"><span data-stu-id="1045e-128">When exporting the **PayrollWorkerEnrolledBenefitDetailEntity** entity, the export determines whether it should use a calculated field based on a rate table or use the **ContributionAmountCur** field on the backing table.</span></span> <span data-ttu-id="1045e-129">Logika używana przez jednostkę danych używa tabeli stawek w sytuacjach, gdy aplikacja normalnie nie działa.</span><span class="sxs-lookup"><span data-stu-id="1045e-129">The logic used by the data entity uses the rate table in situations where the application normally doesn't.</span></span> <span data-ttu-id="1045e-130">Ta logika powoduje, że jednostka eksportuje w celu zwrócenia wartości zerowej dla tej kolumny, ponieważ nie istnieje tabela stawek obliczania, a produkt nie zezwala klientowi na określenie jednego z nich.</span><span class="sxs-lookup"><span data-stu-id="1045e-130">This logic causes the entity exports to return a zero value for this column, because there's no calculation rate table and the product doesn't allow the customer to specify one.</span></span>
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a><span data-ttu-id="1045e-131">Pomyłkowe tłumaczenia w języku czeskim w Zarządzanie personelem i Samoobsługa pracownika etatowego (400276)</span><span class="sxs-lookup"><span data-stu-id="1045e-131">Confusing translations in Czech language in Personnel management and Employee self service (400276)</span></span>

<span data-ttu-id="1045e-132">Ta wersja koryguje tłumaczenia **Katalogu firmy**, **Następny zarejestrowany kurs**, **Zadanie** i **Stanowiska**.</span><span class="sxs-lookup"><span data-stu-id="1045e-132">This release corrects the translations for **Company directory**, **Next registered course**, **Job**, and **Position**.</span></span>
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a><span data-ttu-id="1045e-133">W tabeli WorkCalendarEmployment nie są włączone utworzone i zmodyfikowane pola systemowe (460171)</span><span class="sxs-lookup"><span data-stu-id="1045e-133">The WorkCalendarEmployment table doesn't have the created and modified system fields enabled (460171)</span></span>

<span data-ttu-id="1045e-134">Utworzone i zmodyfikowane pola systemowe są teraz włączane w tabeli **WorkCalendarEmployment** w Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1045e-134">Created and modified system fields are now enabled on the **WorkCalendarEmployment** table in Human Resources.</span></span>
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a><span data-ttu-id="1045e-135">Wyjątek odwołania zerowego dla zatrudnienia i dodaj szczegóły dla przyszłego pracownika (455475)</span><span class="sxs-lookup"><span data-stu-id="1045e-135">Null reference exception for Hire and add details for future employee (455475)</span></span>

<span data-ttu-id="1045e-136">Ta wersja koryguje błąd (odwołanie o wartości null) w ulepszonym wpisie pracownika podczas zatrudniania pracownika przy użyciu opcji **Zatrudniania i dodawania szczegółów**.</span><span class="sxs-lookup"><span data-stu-id="1045e-136">This release corrects an error (null reference) in streamlined employee entry when you hire an employee using the option to **Hire and add details**.</span></span>

## <a name="changes-made-in-the-common-data-service-worker-entity-dont-reflect-in-human-resources-455652"></a><span data-ttu-id="1045e-137">Zmiany wprowadzone w jednostce pracownika Common Data Service nie są odzwierciedlane w Human Resources (455652)</span><span class="sxs-lookup"><span data-stu-id="1045e-137">Changes made in the Common Data Service Worker entity don't reflect in Human Resources (455652)</span></span>

<span data-ttu-id="1045e-138">Zmiany wprowadzone w poniższych polach w jednostce **Pracownik** w Common Data Service z ostaną teraz wyświetlone w Human Resources:</span><span class="sxs-lookup"><span data-stu-id="1045e-138">Changes made to the following fields in the **Worker** entity in Common Data Service will now show up in Human Resources:</span></span>

- <span data-ttu-id="1045e-139">**Pracuje z domu**</span><span class="sxs-lookup"><span data-stu-id="1045e-139">**Works from home**</span></span>
- <span data-ttu-id="1045e-140">**Data stażu pracy**</span><span class="sxs-lookup"><span data-stu-id="1045e-140">**Seniority date**</span></span>
- <span data-ttu-id="1045e-141">**Rocznica**</span><span class="sxs-lookup"><span data-stu-id="1045e-141">**Anniversary date**</span></span>
- <span data-ttu-id="1045e-142">**Pierwotna data zatrudnienia**</span><span class="sxs-lookup"><span data-stu-id="1045e-142">**Original hire date**</span></span>

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a><span data-ttu-id="1045e-143">Poprawny poziom wynagrodzeń nie jest domyślny na podstawie zadania przypisanego do stanowiska (394136)</span><span class="sxs-lookup"><span data-stu-id="1045e-143">Correct compensation level doesn't default based on the job assigned to the position (394136)</span></span>

<span data-ttu-id="1045e-144">W przypadku tej zmiany odpowiednie wartości domyślne poziomu wynagrodzeń są oparte na rekordach **Data wprowadzenia** dla **Szczegółów stanowiska** oraz w **Dacie początkowej** **Przypisania planu wynagrodzeń**.</span><span class="sxs-lookup"><span data-stu-id="1045e-144">With this change, the correct compensation level defaults based on the **Date effective** records for the **Position details** and the **Start date** of the **Compensation plan assignment**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="1045e-145">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="1045e-145">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="1045e-146">Pola obowiązkowe</span><span class="sxs-lookup"><span data-stu-id="1045e-146">Mandatory fields</span></span> 

<span data-ttu-id="1045e-147">Można teraz wprowadzać wymagane pola, korzystając z możliwości personalizacji zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="1045e-147">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="1045e-148">Ta funkcja wymaga **Zapisanych widoków**.</span><span class="sxs-lookup"><span data-stu-id="1045e-148">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="1045e-149">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="1045e-149">Human Resources application in Teams</span></span>

<span data-ttu-id="1045e-150">Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1045e-150">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="1045e-151">Mogą oni współpracować z botem, aby tworzyć żądania urlopu.</span><span class="sxs-lookup"><span data-stu-id="1045e-151">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="1045e-152">Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="1045e-152">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="1045e-153">Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami</span><span class="sxs-lookup"><span data-stu-id="1045e-153">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="1045e-154">Jednostki zarządzania świadczeniami są zwalniane.</span><span class="sxs-lookup"><span data-stu-id="1045e-154">Benefits management entities are releasing.</span></span> <span data-ttu-id="1045e-155">Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami.</span><span class="sxs-lookup"><span data-stu-id="1045e-155">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="1045e-156">Dostępny jest szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych.</span><span class="sxs-lookup"><span data-stu-id="1045e-156">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="1045e-157">Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych.</span><span class="sxs-lookup"><span data-stu-id="1045e-157">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="1045e-158">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="1045e-158">Buy and sell leave</span></span> 

<span data-ttu-id="1045e-159">Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy.</span><span class="sxs-lookup"><span data-stu-id="1045e-159">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="1045e-160">Ten proces jest często zarządzany ręcznie.</span><span class="sxs-lookup"><span data-stu-id="1045e-160">This process is often managed manually.</span></span> <span data-ttu-id="1045e-161">Ta funkcja automatyzuje Zarządzanie zasadami i wnioskami dotyczącymi działu kadr.</span><span class="sxs-lookup"><span data-stu-id="1045e-161">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="1045e-162">Upraszcza proces zarządzania urlopami i pomaga wyeliminować błędy.</span><span class="sxs-lookup"><span data-stu-id="1045e-162">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="1045e-163">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="1045e-163">For more information, see:</span></span>

- [<span data-ttu-id="1045e-164">Zarządzaj zasadami Kupowania i Sprzedawania urlopu</span><span class="sxs-lookup"><span data-stu-id="1045e-164">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="1045e-165">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="1045e-165">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="1045e-166">Pozostaw naliczenie dla jednej firmy lub pojedynczego planu</span><span class="sxs-lookup"><span data-stu-id="1045e-166">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="1045e-167">Odbiorcy mogą przetwarzać naliczenia dla jednej firmy lub jednego urlopu i planu nieobecności.</span><span class="sxs-lookup"><span data-stu-id="1045e-167">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="1045e-168">Ta możliwość jest dostępna dla procesu naliczania dla odbiorców o różnych latach urlopowych lub zasadach naliczania urlopu.</span><span class="sxs-lookup"><span data-stu-id="1045e-168">This ability provides clarity for the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="1045e-169">Aby uzyskać więcej informacji, zajrzyj do [Urlop naliczony według firmy lub planu urlopu](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="1045e-169">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="1045e-170">Dodawanie załączników do żądań czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="1045e-170">Add attachments to time-off requests</span></span>

<span data-ttu-id="1045e-171">Możliwość dodawania załączników do zatwierdzonych żądań urlopów jest krytyczna w bieżącym środowisku COVID-19.</span><span class="sxs-lookup"><span data-stu-id="1045e-171">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="1045e-172">Pracownicy mogą teraz dodawać te załączniki.</span><span class="sxs-lookup"><span data-stu-id="1045e-172">Employees can now add these attachments.</span></span> <span data-ttu-id="1045e-173">Ponadto mają więcej informacji na temat sposobu dokonywania aktualizacji żądań urlopów.</span><span class="sxs-lookup"><span data-stu-id="1045e-173">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="1045e-174">Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie załącznika do istniejącego żądania](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="1045e-174">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="1045e-175">Dodano kod przyczyny do wstrzymań naliczania</span><span class="sxs-lookup"><span data-stu-id="1045e-175">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="1045e-176">Kody przyczyn zostały dodane do wstrzymania naliczania.</span><span class="sxs-lookup"><span data-stu-id="1045e-176">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="1045e-177">Zasady przenoszenia na następny okres</span><span class="sxs-lookup"><span data-stu-id="1045e-177">Carry forward rules</span></span> 

<span data-ttu-id="1045e-178">Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu.</span><span class="sxs-lookup"><span data-stu-id="1045e-178">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="1045e-179">Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni.</span><span class="sxs-lookup"><span data-stu-id="1045e-179">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="1045e-180">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="1045e-180">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="1045e-181">Wstrzymanie naliczania urlopu dla określonych typów urlopów</span><span class="sxs-lookup"><span data-stu-id="1045e-181">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="1045e-182">Można utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny.</span><span class="sxs-lookup"><span data-stu-id="1045e-182">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="1045e-183">Urlop bezpłatny może być typem, ale nie musi.</span><span class="sxs-lookup"><span data-stu-id="1045e-183">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="1045e-184">Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="1045e-184">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="1045e-185">Jednostka DMF dostępna dla wstrzymań naliczania</span><span class="sxs-lookup"><span data-stu-id="1045e-185">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="1045e-186">Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.</span><span class="sxs-lookup"><span data-stu-id="1045e-186">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="1045e-187">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="1045e-187">Coming soon</span></span>

## <a name="checklist-entities-included-in-common-data-service"></a><span data-ttu-id="1045e-188">Jednostki listy kontrolnej uwzględnione w Common Data Service</span><span class="sxs-lookup"><span data-stu-id="1045e-188">Checklist entities included in Common Data Service</span></span>

<span data-ttu-id="1045e-189">Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1045e-189">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="1045e-190">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1045e-190">See also</span></span>

[<span data-ttu-id="1045e-191">Nowości i zmiany w rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="1045e-191">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="1045e-192">Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2</span><span class="sxs-lookup"><span data-stu-id="1045e-192">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="1045e-193">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="1045e-193">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="1045e-194">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="1045e-194">Manage features</span></span>](hr-admin-manage-features.md)
