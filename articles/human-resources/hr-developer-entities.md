---
title: Jednostki usługi Common Data Service
description: Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Common Data Service do obsługi scenariuszy rozszerzalności i integracji.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 988fa0b6d39a49b973626a8a0abe83c546f42297
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4530013"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="c9ac1-103">Jednostki usługi Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c9ac1-103">Common Data Service entities</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c9ac1-104">Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Common Data Service do obsługi scenariuszy rozszerzalności i integracji.</span><span class="sxs-lookup"><span data-stu-id="c9ac1-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="c9ac1-105">Aby uzyskać więcej informacji dotyczących usługi Common Data Service, zobacz temat [Co to jest usługa Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="c9ac1-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="c9ac1-106">W usłudze Common Data Service są dostępne są następujące jednostki aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c9ac1-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="c9ac1-107">Jednostki dotyczące świadczeń</span><span class="sxs-lookup"><span data-stu-id="c9ac1-107">Benefit entities</span></span>

| <span data-ttu-id="c9ac1-108">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="c9ac1-108">Name</span></span> | <span data-ttu-id="c9ac1-109">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c9ac1-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c9ac1-110">Częstotliwość obliczania świadczeń</span><span class="sxs-lookup"><span data-stu-id="c9ac1-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="c9ac1-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="c9ac1-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="c9ac1-112">Częstotliwość obliczania okresu płac dla świadczeń</span><span class="sxs-lookup"><span data-stu-id="c9ac1-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="c9ac1-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="c9ac1-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="c9ac1-114">Stawka obliczania świadczenia</span><span class="sxs-lookup"><span data-stu-id="c9ac1-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="c9ac1-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="c9ac1-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="c9ac1-116">Szczegół stawki obliczania świadczenia</span><span class="sxs-lookup"><span data-stu-id="c9ac1-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="c9ac1-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="c9ac1-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="c9ac1-118">Opcja świadczenia</span><span class="sxs-lookup"><span data-stu-id="c9ac1-118">Benefit Option</span></span> | <span data-ttu-id="c9ac1-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="c9ac1-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="c9ac1-120">Plan świadczeń</span><span class="sxs-lookup"><span data-stu-id="c9ac1-120">Benefit Plan</span></span> | <span data-ttu-id="c9ac1-121">cdm_benefitplan (niewłączone dla obsługi pól niestandardowych)</span><span class="sxs-lookup"><span data-stu-id="c9ac1-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="c9ac1-122">Typ świadczenia</span><span class="sxs-lookup"><span data-stu-id="c9ac1-122">Benefit Type</span></span> | <span data-ttu-id="c9ac1-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="c9ac1-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="c9ac1-124">Jednostki zadań procesu biznesowego</span><span class="sxs-lookup"><span data-stu-id="c9ac1-124">Business process tasks entities</span></span>

| <span data-ttu-id="c9ac1-125">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="c9ac1-125">Name</span></span> | <span data-ttu-id="c9ac1-126">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c9ac1-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c9ac1-127">Kalendarz procesu biznesowego</span><span class="sxs-lookup"><span data-stu-id="c9ac1-127">Business Process Calendar</span></span> | <span data-ttu-id="c9ac1-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="c9ac1-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="c9ac1-129">Przypisanie grupy procesu biznesowego</span><span class="sxs-lookup"><span data-stu-id="c9ac1-129">Business Process Group Assignment</span></span> | <span data-ttu-id="c9ac1-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="c9ac1-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="c9ac1-131">Grupa zadań biblioteki procesów biznesowych</span><span class="sxs-lookup"><span data-stu-id="c9ac1-131">Business Process Library Task Group</span></span> | <span data-ttu-id="c9ac1-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="c9ac1-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="c9ac1-133">Etap procesu biznesowego</span><span class="sxs-lookup"><span data-stu-id="c9ac1-133">Business Process Stage</span></span> | <span data-ttu-id="c9ac1-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="c9ac1-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="c9ac1-135">Nagłówek szablonu listy kontrolnej</span><span class="sxs-lookup"><span data-stu-id="c9ac1-135">Checklist Template Header</span></span> | <span data-ttu-id="c9ac1-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="c9ac1-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="c9ac1-137">Zadanie szablonu listy kontrolnej</span><span class="sxs-lookup"><span data-stu-id="c9ac1-137">Checklist Template Task</span></span> | <span data-ttu-id="c9ac1-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="c9ac1-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="c9ac1-139">Jednostki kompensacji</span><span class="sxs-lookup"><span data-stu-id="c9ac1-139">Compensation entities</span></span>

| <span data-ttu-id="c9ac1-140">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="c9ac1-140">Name</span></span> | <span data-ttu-id="c9ac1-141">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c9ac1-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c9ac1-142">Stały plan wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="c9ac1-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="c9ac1-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="c9ac1-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="c9ac1-144">Siatka wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="c9ac1-144">Compensation Grid</span></span> | <span data-ttu-id="c9ac1-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="c9ac1-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="c9ac1-146">Poziom wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="c9ac1-146">Compensation Level</span></span> | <span data-ttu-id="c9ac1-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="c9ac1-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="c9ac1-148">Wynagrodzenie — częstotliwość wypłat</span><span class="sxs-lookup"><span data-stu-id="c9ac1-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="c9ac1-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="c9ac1-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="c9ac1-150">Ustawianie punktów odniesienia kompensacji</span><span class="sxs-lookup"><span data-stu-id="c9ac1-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="c9ac1-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="c9ac1-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="c9ac1-152">Wiersz ustawień punktów odniesienia kompensacji</span><span class="sxs-lookup"><span data-stu-id="c9ac1-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="c9ac1-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="c9ac1-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="c9ac1-154">Region wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="c9ac1-154">Compensation Region</span></span> | <span data-ttu-id="c9ac1-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="c9ac1-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="c9ac1-156">Struktura wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="c9ac1-156">Compensation Structure</span></span> | <span data-ttu-id="c9ac1-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="c9ac1-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="c9ac1-158">Plan wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="c9ac1-158">Compensation Variable Plan</span></span> | <span data-ttu-id="c9ac1-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="c9ac1-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="c9ac1-160">Poziom planu wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="c9ac1-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="c9ac1-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="c9ac1-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="c9ac1-162">Typ planu wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="c9ac1-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="c9ac1-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="c9ac1-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="c9ac1-164">Zdarzenie dotyczące stałego wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="c9ac1-164">Fixed Compensation Event</span></span> | <span data-ttu-id="c9ac1-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="c9ac1-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="c9ac1-166">Reguła wypłat</span><span class="sxs-lookup"><span data-stu-id="c9ac1-166">Vesting Rule</span></span> | <span data-ttu-id="c9ac1-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="c9ac1-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="c9ac1-168">Stałe wynagrodzenia pracowników</span><span class="sxs-lookup"><span data-stu-id="c9ac1-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="c9ac1-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="c9ac1-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="c9ac1-170">Jednostki dotyczące organizacji</span><span class="sxs-lookup"><span data-stu-id="c9ac1-170">Organization entities</span></span>

| <span data-ttu-id="c9ac1-171">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="c9ac1-171">Name</span></span> | <span data-ttu-id="c9ac1-172">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c9ac1-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c9ac1-173">Dział</span><span class="sxs-lookup"><span data-stu-id="c9ac1-173">Department</span></span> | <span data-ttu-id="c9ac1-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="c9ac1-174">cdm_department</span></span> |
| <span data-ttu-id="c9ac1-175">Zatrudnienie</span><span class="sxs-lookup"><span data-stu-id="c9ac1-175">Employment</span></span> | <span data-ttu-id="c9ac1-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="c9ac1-176">cdm_employment</span></span> |
| <span data-ttu-id="c9ac1-177">Firma</span><span class="sxs-lookup"><span data-stu-id="c9ac1-177">Company</span></span> | <span data-ttu-id="c9ac1-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="c9ac1-178">cdm_company</span></span> |
| <span data-ttu-id="c9ac1-179">Zadanie</span><span class="sxs-lookup"><span data-stu-id="c9ac1-179">Job</span></span> | <span data-ttu-id="c9ac1-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="c9ac1-180">cdm_job</span></span> |
| <span data-ttu-id="c9ac1-181">Czynności związane z funkcją</span><span class="sxs-lookup"><span data-stu-id="c9ac1-181">Job Function</span></span> | <span data-ttu-id="c9ac1-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="c9ac1-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="c9ac1-183">Stanowisko pracy</span><span class="sxs-lookup"><span data-stu-id="c9ac1-183">Job Position</span></span> | <span data-ttu-id="c9ac1-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="c9ac1-184">cdm_jobposition</span></span> |
| <span data-ttu-id="c9ac1-185">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="c9ac1-185">Position Type</span></span> | <span data-ttu-id="c9ac1-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="c9ac1-186">cdm_positiontype</span></span> |
| <span data-ttu-id="c9ac1-187">Przypisanie pracownika do stanowiska</span><span class="sxs-lookup"><span data-stu-id="c9ac1-187">Position Worker Assignment</span></span> | <span data-ttu-id="c9ac1-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="c9ac1-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="c9ac1-189">Wymiar stanowiska pracy</span><span class="sxs-lookup"><span data-stu-id="c9ac1-189">Job Position Dimension</span></span> | <span data-ttu-id="c9ac1-190">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="c9ac1-190">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="c9ac1-191">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="c9ac1-191">Job Type</span></span> | <span data-ttu-id="c9ac1-192">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="c9ac1-192">cdm_jobtype</span></span> |
| <span data-ttu-id="c9ac1-193">Język</span><span class="sxs-lookup"><span data-stu-id="c9ac1-193">Language</span></span> | <span data-ttu-id="c9ac1-194">cdm_language</span><span class="sxs-lookup"><span data-stu-id="c9ac1-194">cdm_language</span></span> |
| <span data-ttu-id="c9ac1-195">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c9ac1-195">Title</span></span> | <span data-ttu-id="c9ac1-196">cdm_title</span><span class="sxs-lookup"><span data-stu-id="c9ac1-196">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="c9ac1-197">Wymiary finansowe dla **Typu stanowiska**, **Przypisania pracowników do stanowisk** i **Zatrudnienia** zapewniają integrację jednokierunkową do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c9ac1-197">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Common Data Service.</span></span> <span data-ttu-id="c9ac1-198">Aktualizacje wymiarów finansowych obecnie nie są synchronizowane z usługi Common Data Service do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c9ac1-198">Financial dimensions updates currently can't synchronize from Common Data Service to Human Resources.</span></span> 

## <a name="leave-and-absence-entities"></a><span data-ttu-id="c9ac1-199">Jednostki dotyczące urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="c9ac1-199">Leave and absence entities</span></span>

| <span data-ttu-id="c9ac1-200">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="c9ac1-200">Name</span></span> | <span data-ttu-id="c9ac1-201">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c9ac1-201">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c9ac1-202">Transakcja banku urlopów</span><span class="sxs-lookup"><span data-stu-id="c9ac1-202">Leave Bank Transaction</span></span> | <span data-ttu-id="c9ac1-203">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="c9ac1-203">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="c9ac1-204">Rejestracja urlopów</span><span class="sxs-lookup"><span data-stu-id="c9ac1-204">Leave Enrollment</span></span> | <span data-ttu-id="c9ac1-205">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="c9ac1-205">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="c9ac1-206">Plan urlopów</span><span class="sxs-lookup"><span data-stu-id="c9ac1-206">Leave Plan</span></span> | <span data-ttu-id="c9ac1-207">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="c9ac1-207">cdm_leaveplan</span></span> |
| <span data-ttu-id="c9ac1-208">Wniosek urlopowy</span><span class="sxs-lookup"><span data-stu-id="c9ac1-208">Leave Request</span></span> | <span data-ttu-id="c9ac1-209">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="c9ac1-209">cdm_leaverequest</span></span> |
| <span data-ttu-id="c9ac1-210">Szczegół wniosku urlopowego</span><span class="sxs-lookup"><span data-stu-id="c9ac1-210">Leave Request Detail</span></span> | <span data-ttu-id="c9ac1-211">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="c9ac1-211">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="c9ac1-212">Typ urlopu</span><span class="sxs-lookup"><span data-stu-id="c9ac1-212">Leave Type</span></span> | <span data-ttu-id="c9ac1-213">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="c9ac1-213">cdm_leavetype</span></span> |
| <span data-ttu-id="c9ac1-214">Kod przyczyny typu nieobecności</span><span class="sxs-lookup"><span data-stu-id="c9ac1-214">Leave Type Reason Code</span></span> | <span data-ttu-id="c9ac1-215">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="c9ac1-215">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="c9ac1-216">Jednostki dotyczące listy płac</span><span class="sxs-lookup"><span data-stu-id="c9ac1-216">Payroll entities</span></span>

| <span data-ttu-id="c9ac1-217">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="c9ac1-217">Name</span></span> | <span data-ttu-id="c9ac1-218">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c9ac1-218">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c9ac1-219">Cykl płac</span><span class="sxs-lookup"><span data-stu-id="c9ac1-219">Pay Cycle</span></span> | <span data-ttu-id="c9ac1-220">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="c9ac1-220">cdm_paycycle</span></span> |
| <span data-ttu-id="c9ac1-221">Okres kalkulacji płac</span><span class="sxs-lookup"><span data-stu-id="c9ac1-221">Pay Period</span></span> | <span data-ttu-id="c9ac1-222">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="c9ac1-222">cdm_payperiod</span></span> |
| <span data-ttu-id="c9ac1-223">Kod zarobków dla listy płac</span><span class="sxs-lookup"><span data-stu-id="c9ac1-223">Payroll Earning Code</span></span> | <span data-ttu-id="c9ac1-224">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="c9ac1-224">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="c9ac1-225">Wypłata na konto bankowe</span><span class="sxs-lookup"><span data-stu-id="c9ac1-225">Bank Account Disbursement</span></span> | <span data-ttu-id="c9ac1-226">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="c9ac1-226">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="c9ac1-227">Region podatkowy</span><span class="sxs-lookup"><span data-stu-id="c9ac1-227">Tax Region</span></span> | <span data-ttu-id="c9ac1-228">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="c9ac1-228">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="c9ac1-229">Jednostki dotyczące pracownika</span><span class="sxs-lookup"><span data-stu-id="c9ac1-229">Worker entities</span></span>

| <span data-ttu-id="c9ac1-230">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="c9ac1-230">Name</span></span> | <span data-ttu-id="c9ac1-231">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c9ac1-231">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c9ac1-232">Pracownik</span><span class="sxs-lookup"><span data-stu-id="c9ac1-232">Worker</span></span> | <span data-ttu-id="c9ac1-233">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="c9ac1-233">cdm_worker</span></span> |
| <span data-ttu-id="c9ac1-234">Adres pracownika</span><span class="sxs-lookup"><span data-stu-id="c9ac1-234">Worker Address</span></span> | <span data-ttu-id="c9ac1-235">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="c9ac1-235">cdm_workeraddress</span></span> |
| <span data-ttu-id="c9ac1-236">Dane osobowe pracownika</span><span class="sxs-lookup"><span data-stu-id="c9ac1-236">Worker Personal Detail</span></span> | <span data-ttu-id="c9ac1-237">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="c9ac1-237">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="c9ac1-238">Numer dokumentu identyfikacyjnego pracownika</span><span class="sxs-lookup"><span data-stu-id="c9ac1-238">Worker Person Identification Number</span></span> | <span data-ttu-id="c9ac1-239">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="c9ac1-239">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="c9ac1-240">Typ dokumentu identyfikacyjnego pracownika</span><span class="sxs-lookup"><span data-stu-id="c9ac1-240">Worker Person Identification Type</span></span> | <span data-ttu-id="c9ac1-241">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="c9ac1-241">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="c9ac1-242">Kalendarz pracy</span><span class="sxs-lookup"><span data-stu-id="c9ac1-242">Work Calendar</span></span> | <span data-ttu-id="c9ac1-243">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="c9ac1-243">cdm_workcalendar</span></span> |
| <span data-ttu-id="c9ac1-244">Dzień w kalendarzu roboczym</span><span class="sxs-lookup"><span data-stu-id="c9ac1-244">Work Calendar Day</span></span> | <span data-ttu-id="c9ac1-245">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="c9ac1-245">cdm_workcalendarday</span></span> |
| <span data-ttu-id="c9ac1-246">Święto w kalendarzu pracy</span><span class="sxs-lookup"><span data-stu-id="c9ac1-246">Work Calendar Holiday</span></span> |<span data-ttu-id="c9ac1-247">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="c9ac1-247">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="c9ac1-248">Wiersz dnia wolnego w kalendarzu roboczym</span><span class="sxs-lookup"><span data-stu-id="c9ac1-248">Work Calendar Holiday Line</span></span> | <span data-ttu-id="c9ac1-249">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="c9ac1-249">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="c9ac1-250">Zakres czasu w kalendarzu roboczym</span><span class="sxs-lookup"><span data-stu-id="c9ac1-250">Work Calendar Time Interval</span></span> | <span data-ttu-id="c9ac1-251">cdm_workcalendartimeinterval (niewłączone dla obsługi pól niestandardowych)</span><span class="sxs-lookup"><span data-stu-id="c9ac1-251">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="c9ac1-252">Konto bankowe pracownika</span><span class="sxs-lookup"><span data-stu-id="c9ac1-252">Worker Bank Account</span></span> | <span data-ttu-id="c9ac1-253">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="c9ac1-253">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="c9ac1-254">Jednostki ustawień pracownika</span><span class="sxs-lookup"><span data-stu-id="c9ac1-254">Worker setup entities</span></span>

| <span data-ttu-id="c9ac1-255">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="c9ac1-255">Name</span></span> | <span data-ttu-id="c9ac1-256">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c9ac1-256">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c9ac1-257">Status kombatanta</span><span class="sxs-lookup"><span data-stu-id="c9ac1-257">Veteran Status</span></span> | <span data-ttu-id="c9ac1-258">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="c9ac1-258">cdm_veteranstatus</span></span> |
| <span data-ttu-id="c9ac1-259">Pochodzenie etniczne</span><span class="sxs-lookup"><span data-stu-id="c9ac1-259">Ethnic Origin</span></span> | <span data-ttu-id="c9ac1-260">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="c9ac1-260">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="c9ac1-261">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="c9ac1-261">Reason Code</span></span> | <span data-ttu-id="c9ac1-262">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="c9ac1-262">cdm_reasoncode</span></span> |
| <span data-ttu-id="c9ac1-263">Agencja wystawiająca dokument identyfikacyjny danej osoby</span><span class="sxs-lookup"><span data-stu-id="c9ac1-263">Person Identification Issuing Agency</span></span> | <span data-ttu-id="c9ac1-264">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="c9ac1-264">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="c9ac1-265">Jednostki kwalifikacji</span><span class="sxs-lookup"><span data-stu-id="c9ac1-265">Competency entities</span></span>

| <span data-ttu-id="c9ac1-266">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="c9ac1-266">Name</span></span> | <span data-ttu-id="c9ac1-267">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c9ac1-267">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="c9ac1-268">Typ kwalifikacji</span><span class="sxs-lookup"><span data-stu-id="c9ac1-268">Skill Type</span></span> | <span data-ttu-id="c9ac1-269">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="c9ac1-269">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="c9ac1-270">Modele relacji między jednostkami</span><span class="sxs-lookup"><span data-stu-id="c9ac1-270">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="c9ac1-271">Pracownik</span><span class="sxs-lookup"><span data-stu-id="c9ac1-271">Worker</span></span>

![Pracownik](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="c9ac1-273">Stanowisko i stanowisko funkcji</span><span class="sxs-lookup"><span data-stu-id="c9ac1-273">Job and Job Position</span></span>

![Stanowisko i stanowisko funkcji](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="c9ac1-275">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="c9ac1-275">Benefits</span></span>

![Świadczenia](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="c9ac1-277">Kompensacja</span><span class="sxs-lookup"><span data-stu-id="c9ac1-277">Compensation</span></span>

![Kompensacja](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="c9ac1-279">Opuść</span><span class="sxs-lookup"><span data-stu-id="c9ac1-279">Leave</span></span>

![Opuść](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="c9ac1-281">Kalendarz pracy</span><span class="sxs-lookup"><span data-stu-id="c9ac1-281">Work Calendar</span></span>

![Kalendarz pracy](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="c9ac1-283">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="c9ac1-283">See also</span></span>

[<span data-ttu-id="c9ac1-284">Wybieranie technologii integracji danych</span><span class="sxs-lookup"><span data-stu-id="c9ac1-284">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="c9ac1-285">Konfiguruj integrację z programem Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c9ac1-285">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)
