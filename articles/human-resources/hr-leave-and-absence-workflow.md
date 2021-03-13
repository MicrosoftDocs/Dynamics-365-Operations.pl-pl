---
title: Tworzenie przepływu pracy wniosku urlopowego
description: W programie Dynamics 365 Human Resources można utworzyć przepływ pracy wniosków o urlopy i nieobecności, aby konsekwentnie zarządzać wnioskami urlopowymi.
author: andreabichsel
manager: tfehr
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e1907ca9cc578737341e52f89453e3d6ae3d0bec
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115059"
---
# <a name="create-a-leave-request-workflow"></a><span data-ttu-id="c7390-103">Tworzenie przepływu pracy wniosku urlopowego</span><span class="sxs-lookup"><span data-stu-id="c7390-103">Create a leave request workflow</span></span>

<span data-ttu-id="c7390-104">W programie Dynamics 365 Human Resources można utworzyć przepływ pracy, aby spójnie zarządzać wnioskami o urlopy i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="c7390-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your leave and absence requests.</span></span> <span data-ttu-id="c7390-105">Przepływ pracy **Urlopy i nieobecności** umożliwia:</span><span class="sxs-lookup"><span data-stu-id="c7390-105">A **Leave and absence** workflow lets you:</span></span>

- <span data-ttu-id="c7390-106">Definiowanie zadań</span><span class="sxs-lookup"><span data-stu-id="c7390-106">Define tasks</span></span>
- <span data-ttu-id="c7390-107">Określanie, kto musi wykonać te zadania</span><span class="sxs-lookup"><span data-stu-id="c7390-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="c7390-108">Określanie, kto może zatwierdzać lub odrzucać wnioski</span><span class="sxs-lookup"><span data-stu-id="c7390-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-leave-and-absence-request-workflow"></a><span data-ttu-id="c7390-109">Tworzenie przepływu pracy wniosków o urlopy i nieobecności</span><span class="sxs-lookup"><span data-stu-id="c7390-109">Create a Leave and absence request workflow</span></span>

1. <span data-ttu-id="c7390-110">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="c7390-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="c7390-111">W obszarze **Konfiguracja** wybierz opcję **Przepływy pracy modułu zasobów ludzkich**.</span><span class="sxs-lookup"><span data-stu-id="c7390-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="c7390-112">Wybierz kolejno opcje **Nowy** i **Wniosek o urlop i nieobecność**.</span><span class="sxs-lookup"><span data-stu-id="c7390-112">Select **New**, and then select **Leave and absence request**.</span></span> 

4. <span data-ttu-id="c7390-113">Gdy pojawi się okno komunikatu **Otworzyć ten plik?**, kliknij przycisk **Otwórz** i zaloguj się przy użyciu firmowych poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="c7390-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="c7390-114">Za pomocą edytora przepływu pracy utwórz przepływ pracy dla wniosków urlopowych.</span><span class="sxs-lookup"><span data-stu-id="c7390-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="c7390-115">Więcej informacji na temat pracy z przepływami pracy zawiera temat [Omówienie tworzenia przepływów pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="c7390-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="c7390-116">Elementy danych przepływu pracy wniosków o urlopy i nieobecności</span><span class="sxs-lookup"><span data-stu-id="c7390-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="c7390-117">Poniższe elementy danych mogą służyć do tworzenia warunkowych lub automatycznych zatwierdzeń w przepływach pracy dotyczących wniosków o urlopy i nieobecności:</span><span class="sxs-lookup"><span data-stu-id="c7390-117">You can use the following data elements to create conditional or automatic approvals in workflows for leave and absence requests:</span></span>

- <span data-ttu-id="c7390-118">**Ilość**</span><span class="sxs-lookup"><span data-stu-id="c7390-118">**Amount**</span></span>
- <span data-ttu-id="c7390-119">**Komentarz**</span><span class="sxs-lookup"><span data-stu-id="c7390-119">**Comment**</span></span>
- <span data-ttu-id="c7390-120">**Firma**</span><span class="sxs-lookup"><span data-stu-id="c7390-120">**Company**</span></span>
- <span data-ttu-id="c7390-121">**Utworzony przez**</span><span class="sxs-lookup"><span data-stu-id="c7390-121">**Created by**</span></span>
- <span data-ttu-id="c7390-122">**Data i godzina utworzenia**</span><span class="sxs-lookup"><span data-stu-id="c7390-122">**Created date and time**</span></span>
- <span data-ttu-id="c7390-123">**Data końcowa**</span><span class="sxs-lookup"><span data-stu-id="c7390-123">**End date**</span></span>
- <span data-ttu-id="c7390-124">**Typ urlopu**</span><span class="sxs-lookup"><span data-stu-id="c7390-124">**Leave type**</span></span>
- <span data-ttu-id="c7390-125">**Zmodyfikowane przez**</span><span class="sxs-lookup"><span data-stu-id="c7390-125">**Modified by**</span></span>
- <span data-ttu-id="c7390-126">**Data i godzina modyfikacji**</span><span class="sxs-lookup"><span data-stu-id="c7390-126">**Modified date and time**</span></span>
- <span data-ttu-id="c7390-127">**Kod przyczyny**</span><span class="sxs-lookup"><span data-stu-id="c7390-127">**Reason code**</span></span>
- <span data-ttu-id="c7390-128">**Identyfikator wniosku**</span><span class="sxs-lookup"><span data-stu-id="c7390-128">**Request ID**</span></span>
- <span data-ttu-id="c7390-129">**d. rozpoczęcia**</span><span class="sxs-lookup"><span data-stu-id="c7390-129">**Start date**</span></span>
- <span data-ttu-id="c7390-130">**Stan**</span><span class="sxs-lookup"><span data-stu-id="c7390-130">**Status**</span></span> 
- <span data-ttu-id="c7390-131">**Data przesłania**</span><span class="sxs-lookup"><span data-stu-id="c7390-131">**Submission date**</span></span>
- <span data-ttu-id="c7390-132">**Przesłane przez**</span><span class="sxs-lookup"><span data-stu-id="c7390-132">**Submitted by**</span></span>
- <span data-ttu-id="c7390-133">**Przesłane przez dział kadr**</span><span class="sxs-lookup"><span data-stu-id="c7390-133">**Submitted by Human resources**</span></span>
- <span data-ttu-id="c7390-134">**Przesłane przez menedżera**</span><span class="sxs-lookup"><span data-stu-id="c7390-134">**Submitted by Manager**</span></span>
- <span data-ttu-id="c7390-135">**Przesłane w imieniu**</span><span class="sxs-lookup"><span data-stu-id="c7390-135">**Submitted on behalf**</span></span>
- <span data-ttu-id="c7390-136">**Pracownik**</span><span class="sxs-lookup"><span data-stu-id="c7390-136">**Worker**</span></span>
- <span data-ttu-id="c7390-137">**Typ pracownika**</span><span class="sxs-lookup"><span data-stu-id="c7390-137">**Worker type**</span></span>

<span data-ttu-id="c7390-138">Poniższe przykłady pokazują, jak można tworzyć różne typy warunków przepływu pracy za pomocą następujących elementów danych:</span><span class="sxs-lookup"><span data-stu-id="c7390-138">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="c7390-139">**Kod przyczyny** jest używany w instrukcji warunkowej do przekierowywania wniosków o urlop zdrowotny z kodem przyczyny **Operacja** do zatwierdzenia przez dział kadr oraz do przekierowywania wszystkich innych kodów przyczyn do menedżera.</span><span class="sxs-lookup"><span data-stu-id="c7390-139">Use **Reason code** in a conditional statement to route sick leave requests with the reason code **Surgery** to HR for approval, while routing all other reason codes to the manager.</span></span> <span data-ttu-id="c7390-140">Aby uzyskać więcej informacji na temat instrukcji warunkowych, zobacz temat [Konfigurowanie decyzji warunkowych w przepływie pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span><span class="sxs-lookup"><span data-stu-id="c7390-140">For more information about conditional statements, see [Configure conditional decisions in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span></span> 

- <span data-ttu-id="c7390-141">Opcje **Przesłanych przez dział kadr** i **Przesłane przez menedżera** są używane w ramach akcji automatycznej w celu automatycznego zatwierdzania wniosków o urlop przesyłanych przez te role w imieniu pracowników.</span><span class="sxs-lookup"><span data-stu-id="c7390-141">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="c7390-142">Aby uzyskać więcej informacji o akcjach automatycznych, zobacz temat [Konfigurowanie procesów zatwierdzania w przepływie pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="c7390-142">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="c7390-143">**Typ urlopu** jest używany w instrukcji warunkowej lub akcji automatycznej do kontrolowania sposobu, w jaki przepływ pracy kieruje wnioski do określonych typów urlopów.</span><span class="sxs-lookup"><span data-stu-id="c7390-143">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7390-144">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="c7390-144">See also</span></span>

- [<span data-ttu-id="c7390-145">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="c7390-145">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
