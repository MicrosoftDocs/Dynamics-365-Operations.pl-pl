---
title: Tabele Dataverse
description: Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Dataverse do obsługi scenariuszy rozszerzalności i integracji.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f075a8e96af55b1363d2d51db377c5b25c38775
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113890"
---
# <a name="dataverse-tables"></a><span data-ttu-id="973c7-103">Tabele Dataverse</span><span class="sxs-lookup"><span data-stu-id="973c7-103">Dataverse tables</span></span>

<span data-ttu-id="973c7-104">Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Dataverse do obsługi scenariuszy rozszerzalności i integracji.</span><span class="sxs-lookup"><span data-stu-id="973c7-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="973c7-105">Jednostki Human Resources odpowiadają tabelom Dataverse.</span><span class="sxs-lookup"><span data-stu-id="973c7-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="973c7-106">Aby uzyskać więcej informacji o Dataverse (poprzednio Common Data Service) i aktualizacjach terminologii, zobacz [Co to jest Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="973c7-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="973c7-107">Poniższe tabele Dataverse są dostępne w oparciu o encje Human Resources.</span><span class="sxs-lookup"><span data-stu-id="973c7-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="973c7-108">Tabele świadczeń</span><span class="sxs-lookup"><span data-stu-id="973c7-108">Benefit tables</span></span>

| <span data-ttu-id="973c7-109">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="973c7-109">Name</span></span> | <span data-ttu-id="973c7-110">Tabela</span><span class="sxs-lookup"><span data-stu-id="973c7-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="973c7-111">Częstotliwość obliczania świadczeń</span><span class="sxs-lookup"><span data-stu-id="973c7-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="973c7-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="973c7-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="973c7-113">Częstotliwość obliczania okresu płac dla świadczeń</span><span class="sxs-lookup"><span data-stu-id="973c7-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="973c7-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="973c7-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="973c7-115">Stawka obliczania świadczenia</span><span class="sxs-lookup"><span data-stu-id="973c7-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="973c7-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="973c7-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="973c7-117">Szczegół stawki obliczania świadczenia</span><span class="sxs-lookup"><span data-stu-id="973c7-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="973c7-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="973c7-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="973c7-119">Opcja świadczenia</span><span class="sxs-lookup"><span data-stu-id="973c7-119">Benefit Option</span></span> | <span data-ttu-id="973c7-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="973c7-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="973c7-121">Plan świadczeń</span><span class="sxs-lookup"><span data-stu-id="973c7-121">Benefit Plan</span></span> | <span data-ttu-id="973c7-122">cdm_benefitplan (niewłączone dla obsługi pól niestandardowych)</span><span class="sxs-lookup"><span data-stu-id="973c7-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="973c7-123">Typ świadczenia</span><span class="sxs-lookup"><span data-stu-id="973c7-123">Benefit Type</span></span> | <span data-ttu-id="973c7-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="973c7-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="973c7-125">Tabele zadań procesu biznesowego</span><span class="sxs-lookup"><span data-stu-id="973c7-125">Business process tasks tables</span></span>

| <span data-ttu-id="973c7-126">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="973c7-126">Name</span></span> | <span data-ttu-id="973c7-127">Tabela</span><span class="sxs-lookup"><span data-stu-id="973c7-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="973c7-128">Kalendarz procesu biznesowego</span><span class="sxs-lookup"><span data-stu-id="973c7-128">Business Process Calendar</span></span> | <span data-ttu-id="973c7-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="973c7-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="973c7-130">Przypisanie grupy procesu biznesowego</span><span class="sxs-lookup"><span data-stu-id="973c7-130">Business Process Group Assignment</span></span> | <span data-ttu-id="973c7-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="973c7-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="973c7-132">Grupa zadań biblioteki procesów biznesowych</span><span class="sxs-lookup"><span data-stu-id="973c7-132">Business Process Library Task Group</span></span> | <span data-ttu-id="973c7-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="973c7-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="973c7-134">Etap procesu biznesowego</span><span class="sxs-lookup"><span data-stu-id="973c7-134">Business Process Stage</span></span> | <span data-ttu-id="973c7-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="973c7-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="973c7-136">Nagłówek szablonu listy kontrolnej</span><span class="sxs-lookup"><span data-stu-id="973c7-136">Checklist Template Header</span></span> | <span data-ttu-id="973c7-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="973c7-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="973c7-138">Zadanie szablonu listy kontrolnej</span><span class="sxs-lookup"><span data-stu-id="973c7-138">Checklist Template Task</span></span> | <span data-ttu-id="973c7-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="973c7-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="973c7-140">Tabele Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="973c7-140">Compensation tables</span></span>

| <span data-ttu-id="973c7-141">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="973c7-141">Name</span></span> | <span data-ttu-id="973c7-142">Tabela</span><span class="sxs-lookup"><span data-stu-id="973c7-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="973c7-143">System stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="973c7-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="973c7-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="973c7-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="973c7-145">Siatka wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="973c7-145">Compensation Grid</span></span> | <span data-ttu-id="973c7-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="973c7-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="973c7-147">Poziom wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="973c7-147">Compensation Level</span></span> | <span data-ttu-id="973c7-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="973c7-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="973c7-149">Wynagrodzenie — częstotliwość wypłat</span><span class="sxs-lookup"><span data-stu-id="973c7-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="973c7-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="973c7-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="973c7-151">Ustawianie punktów odniesienia kompensacji</span><span class="sxs-lookup"><span data-stu-id="973c7-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="973c7-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="973c7-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="973c7-153">Wiersz ustawień punktów odniesienia kompensacji</span><span class="sxs-lookup"><span data-stu-id="973c7-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="973c7-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="973c7-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="973c7-155">Region wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="973c7-155">Compensation Region</span></span> | <span data-ttu-id="973c7-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="973c7-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="973c7-157">Struktura wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="973c7-157">Compensation Structure</span></span> | <span data-ttu-id="973c7-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="973c7-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="973c7-159">Plan wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="973c7-159">Compensation Variable Plan</span></span> | <span data-ttu-id="973c7-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="973c7-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="973c7-161">Poziom planu wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="973c7-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="973c7-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="973c7-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="973c7-163">Typ planu wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="973c7-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="973c7-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="973c7-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="973c7-165">Zdarzenie dotyczące stałego wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="973c7-165">Fixed Compensation Event</span></span> | <span data-ttu-id="973c7-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="973c7-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="973c7-167">Reguła wypłat</span><span class="sxs-lookup"><span data-stu-id="973c7-167">Vesting Rule</span></span> | <span data-ttu-id="973c7-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="973c7-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="973c7-169">Stałe wynagrodzenie pracownika</span><span class="sxs-lookup"><span data-stu-id="973c7-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="973c7-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="973c7-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="973c7-171">Tabele Organization</span><span class="sxs-lookup"><span data-stu-id="973c7-171">Organization tables</span></span>

| <span data-ttu-id="973c7-172">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="973c7-172">Name</span></span> | <span data-ttu-id="973c7-173">Tabela</span><span class="sxs-lookup"><span data-stu-id="973c7-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="973c7-174">Dział</span><span class="sxs-lookup"><span data-stu-id="973c7-174">Department</span></span> | <span data-ttu-id="973c7-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="973c7-175">cdm_department</span></span> |
| <span data-ttu-id="973c7-176">Zatrudnienie</span><span class="sxs-lookup"><span data-stu-id="973c7-176">Employment</span></span> | <span data-ttu-id="973c7-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="973c7-177">cdm_employment</span></span> |
| <span data-ttu-id="973c7-178">Firma</span><span class="sxs-lookup"><span data-stu-id="973c7-178">Company</span></span> | <span data-ttu-id="973c7-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="973c7-179">cdm_company</span></span> |
| <span data-ttu-id="973c7-180">Zadanie</span><span class="sxs-lookup"><span data-stu-id="973c7-180">Job</span></span> | <span data-ttu-id="973c7-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="973c7-181">cdm_job</span></span> |
| <span data-ttu-id="973c7-182">Czynności związane z funkcją</span><span class="sxs-lookup"><span data-stu-id="973c7-182">Job Function</span></span> | <span data-ttu-id="973c7-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="973c7-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="973c7-184">Stanowisko pracy</span><span class="sxs-lookup"><span data-stu-id="973c7-184">Job Position</span></span> | <span data-ttu-id="973c7-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="973c7-185">cdm_jobposition</span></span> |
| <span data-ttu-id="973c7-186">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="973c7-186">Position Type</span></span> | <span data-ttu-id="973c7-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="973c7-187">cdm_positiontype</span></span> |
| <span data-ttu-id="973c7-188">Przypisanie pracownika do stanowiska</span><span class="sxs-lookup"><span data-stu-id="973c7-188">Position Worker Assignment</span></span> | <span data-ttu-id="973c7-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="973c7-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="973c7-190">Wymiar stanowiska pracy</span><span class="sxs-lookup"><span data-stu-id="973c7-190">Job Position Dimension</span></span> | <span data-ttu-id="973c7-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="973c7-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="973c7-192">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="973c7-192">Job Type</span></span> | <span data-ttu-id="973c7-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="973c7-193">cdm_jobtype</span></span> |
| <span data-ttu-id="973c7-194">Język</span><span class="sxs-lookup"><span data-stu-id="973c7-194">Language</span></span> | <span data-ttu-id="973c7-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="973c7-195">cdm_language</span></span> |
| <span data-ttu-id="973c7-196">Nazwa</span><span class="sxs-lookup"><span data-stu-id="973c7-196">Title</span></span> | <span data-ttu-id="973c7-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="973c7-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="973c7-198">Wymiary finansowe dla **Typu stanowiska**, **Przypisania pracowników do stanowisk** i **Zatrudnienia** zapewniają integrację jednokierunkową do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="973c7-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="973c7-199">Aktualizacje wymiarów finansowych obecnie nie są synchronizowane z usługi Dataverse do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="973c7-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="973c7-200">Tabele Urlopy i nieobecności</span><span class="sxs-lookup"><span data-stu-id="973c7-200">Leave and absence tables</span></span>

| <span data-ttu-id="973c7-201">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="973c7-201">Name</span></span> | <span data-ttu-id="973c7-202">Tabela</span><span class="sxs-lookup"><span data-stu-id="973c7-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="973c7-203">Transakcja banku urlopów</span><span class="sxs-lookup"><span data-stu-id="973c7-203">Leave Bank Transaction</span></span> | <span data-ttu-id="973c7-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="973c7-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="973c7-205">Rejestracja urlopu</span><span class="sxs-lookup"><span data-stu-id="973c7-205">Leave Enrollment</span></span> | <span data-ttu-id="973c7-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="973c7-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="973c7-207">Plan urlopów</span><span class="sxs-lookup"><span data-stu-id="973c7-207">Leave Plan</span></span> | <span data-ttu-id="973c7-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="973c7-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="973c7-209">Wniosek urlopowy</span><span class="sxs-lookup"><span data-stu-id="973c7-209">Leave Request</span></span> | <span data-ttu-id="973c7-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="973c7-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="973c7-211">Szczegół wniosku urlopowego</span><span class="sxs-lookup"><span data-stu-id="973c7-211">Leave Request Detail</span></span> | <span data-ttu-id="973c7-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="973c7-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="973c7-213">Typ urlopu</span><span class="sxs-lookup"><span data-stu-id="973c7-213">Leave Type</span></span> | <span data-ttu-id="973c7-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="973c7-214">cdm_leavetype</span></span> |
| <span data-ttu-id="973c7-215">Kod przyczyny typu nieobecności</span><span class="sxs-lookup"><span data-stu-id="973c7-215">Leave Type Reason Code</span></span> | <span data-ttu-id="973c7-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="973c7-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="973c7-217">Tabele listy płac</span><span class="sxs-lookup"><span data-stu-id="973c7-217">Payroll tables</span></span>

| <span data-ttu-id="973c7-218">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="973c7-218">Name</span></span> | <span data-ttu-id="973c7-219">Tabela</span><span class="sxs-lookup"><span data-stu-id="973c7-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="973c7-220">Cykl kalkulacji płac</span><span class="sxs-lookup"><span data-stu-id="973c7-220">Pay Cycle</span></span> | <span data-ttu-id="973c7-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="973c7-221">cdm_paycycle</span></span> |
| <span data-ttu-id="973c7-222">Okres kalkulacji płac</span><span class="sxs-lookup"><span data-stu-id="973c7-222">Pay Period</span></span> | <span data-ttu-id="973c7-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="973c7-223">cdm_payperiod</span></span> |
| <span data-ttu-id="973c7-224">Kod zarobków dla listy płac</span><span class="sxs-lookup"><span data-stu-id="973c7-224">Payroll Earning Code</span></span> | <span data-ttu-id="973c7-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="973c7-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="973c7-226">Wypłata na konto bankowe</span><span class="sxs-lookup"><span data-stu-id="973c7-226">Bank Account Disbursement</span></span> | <span data-ttu-id="973c7-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="973c7-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="973c7-228">Region podatkowy</span><span class="sxs-lookup"><span data-stu-id="973c7-228">Tax Region</span></span> | <span data-ttu-id="973c7-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="973c7-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="973c7-230">Tabele pracowników</span><span class="sxs-lookup"><span data-stu-id="973c7-230">Worker tables</span></span>

| <span data-ttu-id="973c7-231">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="973c7-231">Name</span></span> | <span data-ttu-id="973c7-232">Tabela</span><span class="sxs-lookup"><span data-stu-id="973c7-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="973c7-233">Pracownik</span><span class="sxs-lookup"><span data-stu-id="973c7-233">Worker</span></span> | <span data-ttu-id="973c7-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="973c7-234">cdm_worker</span></span> |
| <span data-ttu-id="973c7-235">Adres pracownika</span><span class="sxs-lookup"><span data-stu-id="973c7-235">Worker Address</span></span> | <span data-ttu-id="973c7-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="973c7-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="973c7-237">Dane osobowe pracownika</span><span class="sxs-lookup"><span data-stu-id="973c7-237">Worker Personal Detail</span></span> | <span data-ttu-id="973c7-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="973c7-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="973c7-239">Numer dokumentu identyfikacyjnego pracownika</span><span class="sxs-lookup"><span data-stu-id="973c7-239">Worker Person Identification Number</span></span> | <span data-ttu-id="973c7-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="973c7-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="973c7-241">Typ dokumentu identyfikacyjnego pracownika</span><span class="sxs-lookup"><span data-stu-id="973c7-241">Worker Person Identification Type</span></span> | <span data-ttu-id="973c7-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="973c7-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="973c7-243">Kalendarz pracy</span><span class="sxs-lookup"><span data-stu-id="973c7-243">Work Calendar</span></span> | <span data-ttu-id="973c7-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="973c7-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="973c7-245">Dzień w kalendarzu roboczym</span><span class="sxs-lookup"><span data-stu-id="973c7-245">Work Calendar Day</span></span> | <span data-ttu-id="973c7-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="973c7-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="973c7-247">Święto w kalendarzu pracy</span><span class="sxs-lookup"><span data-stu-id="973c7-247">Work Calendar Holiday</span></span> |<span data-ttu-id="973c7-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="973c7-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="973c7-249">Wiersz dnia wolnego w kalendarzu roboczym</span><span class="sxs-lookup"><span data-stu-id="973c7-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="973c7-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="973c7-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="973c7-251">Zakres czasu w kalendarzu roboczym</span><span class="sxs-lookup"><span data-stu-id="973c7-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="973c7-252">cdm_workcalendartimeinterval (niewłączone dla obsługi pól niestandardowych)</span><span class="sxs-lookup"><span data-stu-id="973c7-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="973c7-253">Konto bankowe pracownika</span><span class="sxs-lookup"><span data-stu-id="973c7-253">Worker Bank Account</span></span> | <span data-ttu-id="973c7-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="973c7-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="973c7-255">Tabele ustawień pracownika</span><span class="sxs-lookup"><span data-stu-id="973c7-255">Worker setup tables</span></span>

| <span data-ttu-id="973c7-256">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="973c7-256">Name</span></span> | <span data-ttu-id="973c7-257">Tabela</span><span class="sxs-lookup"><span data-stu-id="973c7-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="973c7-258">Status kombatanta</span><span class="sxs-lookup"><span data-stu-id="973c7-258">Veteran Status</span></span> | <span data-ttu-id="973c7-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="973c7-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="973c7-260">Pochodzenie etniczne</span><span class="sxs-lookup"><span data-stu-id="973c7-260">Ethnic Origin</span></span> | <span data-ttu-id="973c7-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="973c7-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="973c7-262">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="973c7-262">Reason Code</span></span> | <span data-ttu-id="973c7-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="973c7-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="973c7-264">Agencja wystawiająca identyfikator osoby</span><span class="sxs-lookup"><span data-stu-id="973c7-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="973c7-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="973c7-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="973c7-266">Tabele kwalifikacji</span><span class="sxs-lookup"><span data-stu-id="973c7-266">Competency tables</span></span>

| <span data-ttu-id="973c7-267">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="973c7-267">Name</span></span> | <span data-ttu-id="973c7-268">Tabela</span><span class="sxs-lookup"><span data-stu-id="973c7-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="973c7-269">Typ kwalifikacji</span><span class="sxs-lookup"><span data-stu-id="973c7-269">Skill Type</span></span> | <span data-ttu-id="973c7-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="973c7-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="973c7-271">Tabele modeli relacji</span><span class="sxs-lookup"><span data-stu-id="973c7-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="973c7-272">Pracownik</span><span class="sxs-lookup"><span data-stu-id="973c7-272">Worker</span></span>

![Pracownik](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="973c7-274">Stanowisko i stanowisko funkcji</span><span class="sxs-lookup"><span data-stu-id="973c7-274">Job and Job Position</span></span>

![Stanowisko i stanowisko funkcji](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="973c7-276">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="973c7-276">Benefits</span></span>

![Świadczenia](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="973c7-278">Kompensacja</span><span class="sxs-lookup"><span data-stu-id="973c7-278">Compensation</span></span>

![Kompensacja](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="973c7-280">Opuść</span><span class="sxs-lookup"><span data-stu-id="973c7-280">Leave</span></span>

![Opuść](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="973c7-282">Kalendarz pracy</span><span class="sxs-lookup"><span data-stu-id="973c7-282">Work Calendar</span></span>

![Kalendarz pracy](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="973c7-284">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="973c7-284">See also</span></span>

[<span data-ttu-id="973c7-285">Wybieranie technologii integracji danych</span><span class="sxs-lookup"><span data-stu-id="973c7-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="973c7-286">Konfiguruj integrację z programem Dataverse</span><span class="sxs-lookup"><span data-stu-id="973c7-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="973c7-287">Konfiguruj tabele wirtualne usługi Dataverse</span><span class="sxs-lookup"><span data-stu-id="973c7-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="973c7-288">Często zadawanych pytań dotyczące tabel wirtualnych dla Human Resources</span><span class="sxs-lookup"><span data-stu-id="973c7-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="973c7-289">Co to jest usługa Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="973c7-289">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="973c7-290">Aktualizacje terminologii</span><span class="sxs-lookup"><span data-stu-id="973c7-290">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)
