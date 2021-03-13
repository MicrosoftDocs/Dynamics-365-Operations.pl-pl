---
title: Tworzenie przepływu pracy zakupu i sprzedawania urlopów
description: W programie Dynamics 365 Human Resources można utworzyć przepływ pracy wniosków o zakup i sprzedaż urlopów, aby konsekwentnie zarządzać wnioskami urlopowymi.
author: andreabichsel
manager: tfehr
ms.date: 08/20/2020
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
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4732b5dafc8074c5c59f10f02bbee7e22f51960a
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2021
ms.locfileid: "5116051"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="36cd0-103">Tworzenie przepływu pracy zakupu i sprzedawania urlopów</span><span class="sxs-lookup"><span data-stu-id="36cd0-103">Create a buy and sell leave request workflow</span></span>

<span data-ttu-id="36cd0-104">W programie Dynamics 365 Human Resources można utworzyć przepływ pracy, aby spójnie zarządzać wnioskami o sprzedaż i zakup urlopów.</span><span class="sxs-lookup"><span data-stu-id="36cd0-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your buy and sell leave requests.</span></span> <span data-ttu-id="36cd0-105">Przepływ pracy **Zakup i sprzedaż urlopu** umożliwia:</span><span class="sxs-lookup"><span data-stu-id="36cd0-105">A **Buy and sell leave** workflow lets you:</span></span>

- <span data-ttu-id="36cd0-106">Definiowanie zadań</span><span class="sxs-lookup"><span data-stu-id="36cd0-106">Define tasks</span></span>
- <span data-ttu-id="36cd0-107">Określanie, kto musi wykonać te zadania</span><span class="sxs-lookup"><span data-stu-id="36cd0-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="36cd0-108">Określanie, kto może zatwierdzać lub odrzucać wnioski</span><span class="sxs-lookup"><span data-stu-id="36cd0-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="36cd0-109">Tworzenie przepływu pracy zakupu i sprzedawania urlopów</span><span class="sxs-lookup"><span data-stu-id="36cd0-109">Create a buy and sell leave request workflow</span></span>

1. <span data-ttu-id="36cd0-110">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="36cd0-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="36cd0-111">W obszarze **Konfiguracja** wybierz opcję **Przepływy pracy modułu zasobów ludzkich**.</span><span class="sxs-lookup"><span data-stu-id="36cd0-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="36cd0-112">Wybierz kolejno opcje **Nowy** i **Wniosek o zakup i sprzedaż urlopu**.</span><span class="sxs-lookup"><span data-stu-id="36cd0-112">Select **New**, and then select **Buy and sell leave request**.</span></span> 

4. <span data-ttu-id="36cd0-113">Gdy pojawi się okno komunikatu **Otworzyć ten plik?**, kliknij przycisk **Otwórz** i zaloguj się przy użyciu firmowych poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="36cd0-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="36cd0-114">Za pomocą edytora przepływu pracy utwórz przepływ pracy dla wniosków urlopowych.</span><span class="sxs-lookup"><span data-stu-id="36cd0-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="36cd0-115">Więcej informacji na temat pracy z przepływami pracy zawiera temat [Omówienie tworzenia przepływów pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="36cd0-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="36cd0-116">Elementy danych przepływu pracy wniosków o urlopy i nieobecności</span><span class="sxs-lookup"><span data-stu-id="36cd0-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="36cd0-117">Poniższe elementy danych mogą służyć do tworzenia warunkowych lub automatycznych zatwierdzeń w przepływach pracy dotyczących wniosków o zakup lub sprzedaż urlopów:</span><span class="sxs-lookup"><span data-stu-id="36cd0-117">You can use the following data elements to create conditional or automatic approvals in workflows for buy and sell leave requests:</span></span>

- <span data-ttu-id="36cd0-118">**Ilość**</span><span class="sxs-lookup"><span data-stu-id="36cd0-118">**Amount**</span></span>
- <span data-ttu-id="36cd0-119">**Zasady zakupu i sprzedaży urlopu**</span><span class="sxs-lookup"><span data-stu-id="36cd0-119">**Buy and sell leave policy**</span></span>
- <span data-ttu-id="36cd0-120">**Firma**</span><span class="sxs-lookup"><span data-stu-id="36cd0-120">**Company**</span></span>
- <span data-ttu-id="36cd0-121">**Utworzony przez**</span><span class="sxs-lookup"><span data-stu-id="36cd0-121">**Created by**</span></span>
- <span data-ttu-id="36cd0-122">**Data i godzina utworzenia**</span><span class="sxs-lookup"><span data-stu-id="36cd0-122">**Created date and time**</span></span>
- <span data-ttu-id="36cd0-123">**Data końcowa**</span><span class="sxs-lookup"><span data-stu-id="36cd0-123">**End date**</span></span>
- <span data-ttu-id="36cd0-124">**Typ urlopu**</span><span class="sxs-lookup"><span data-stu-id="36cd0-124">**Leave type**</span></span>
- <span data-ttu-id="36cd0-125">**Zmodyfikowane przez**</span><span class="sxs-lookup"><span data-stu-id="36cd0-125">**Modified by**</span></span>
- <span data-ttu-id="36cd0-126">**Data i godzina modyfikacji**</span><span class="sxs-lookup"><span data-stu-id="36cd0-126">**Modified date and time**</span></span>
- <span data-ttu-id="36cd0-127">**Identyfikator wniosku**</span><span class="sxs-lookup"><span data-stu-id="36cd0-127">**Request ID**</span></span>
- <span data-ttu-id="36cd0-128">**Rozpoczęcie**</span><span class="sxs-lookup"><span data-stu-id="36cd0-128">**Start date**</span></span>
- <span data-ttu-id="36cd0-129">**Stan**</span><span class="sxs-lookup"><span data-stu-id="36cd0-129">**Status**</span></span> 
- <span data-ttu-id="36cd0-130">**Data przesłania**</span><span class="sxs-lookup"><span data-stu-id="36cd0-130">**Submission date**</span></span>
- <span data-ttu-id="36cd0-131">**Przesłano przez**</span><span class="sxs-lookup"><span data-stu-id="36cd0-131">**Submitted by**</span></span>
- <span data-ttu-id="36cd0-132">**Przesłane przez dział kadr**</span><span class="sxs-lookup"><span data-stu-id="36cd0-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="36cd0-133">**Przesłane przez menedżera**</span><span class="sxs-lookup"><span data-stu-id="36cd0-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="36cd0-134">**Przesłane w imieniu**</span><span class="sxs-lookup"><span data-stu-id="36cd0-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="36cd0-135">**Pracownik**</span><span class="sxs-lookup"><span data-stu-id="36cd0-135">**Worker**</span></span>

## <a name="workflow-examples"></a><span data-ttu-id="36cd0-136">Przykłady przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="36cd0-136">Workflow examples</span></span>

<span data-ttu-id="36cd0-137">Poniższe przykłady pokazują, jak można tworzyć różne typy warunków przepływu pracy za pomocą następujących elementów danych:</span><span class="sxs-lookup"><span data-stu-id="36cd0-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="36cd0-138">Opcje **Przesłanych przez dział kadr** i **Przesłane przez menedżera** są używane w ramach akcji automatycznej w celu automatycznego zatwierdzania wniosków o zakup lub sprzedaż urlopu przesyłanych przez te role w imieniu pracowników.</span><span class="sxs-lookup"><span data-stu-id="36cd0-138">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve buy and sell leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="36cd0-139">Aby uzyskać więcej informacji o akcjach automatycznych, zobacz temat [Konfigurowanie procesów zatwierdzania w przepływie pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="36cd0-139">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="36cd0-140">**Typ urlopu** jest używany w instrukcji warunkowej lub akcji automatycznej do kontrolowania sposobu, w jaki przepływ pracy kieruje wnioski do określonych typów urlopów.</span><span class="sxs-lookup"><span data-stu-id="36cd0-140">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="36cd0-141">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="36cd0-141">See also</span></span>

[<span data-ttu-id="36cd0-142">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="36cd0-142">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)<br>
[<span data-ttu-id="36cd0-143">Zarządzaj zasadami Kupowania i Sprzedawania urlopu</span><span class="sxs-lookup"><span data-stu-id="36cd0-143">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)

