---
title: Konfigurowanie potrąceń
description: ''
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
ms.openlocfilehash: 7ee9e8f3bc0e9027e41d3aa91bd097a3f046cbb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010224"
---
# <a name="configure-deductions"></a><span data-ttu-id="654a0-102">Konfigurowanie potrąceń</span><span class="sxs-lookup"><span data-stu-id="654a0-102">Configure deductions</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="654a0-103">Funkcja potrąceń w programie Microsoft Dynamics 365 Human Resources pozwala określić, ile (jeśli w ogóle) należy potrącić z wynagrodzenia pracownika na każde świadczenie.</span><span class="sxs-lookup"><span data-stu-id="654a0-103">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="654a0-104">Potrącenia mają daty obowiązywania, więc można prowadzić historyczny rejestr informacji o potrąceniach.</span><span class="sxs-lookup"><span data-stu-id="654a0-104">Deductions are date effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="654a0-105">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Potrącenia**.</span><span class="sxs-lookup"><span data-stu-id="654a0-105">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="654a0-106">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="654a0-106">Select **New**.</span></span>

3. <span data-ttu-id="654a0-107">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="654a0-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="654a0-108">Pole</span><span class="sxs-lookup"><span data-stu-id="654a0-108">Field</span></span> | <span data-ttu-id="654a0-109">Opis</span><span class="sxs-lookup"><span data-stu-id="654a0-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="654a0-110">Potrącenie</span><span class="sxs-lookup"><span data-stu-id="654a0-110">Deduction</span></span> | <span data-ttu-id="654a0-111">Unikatowy identyfikator używany do identyfikowania potrącenia na świadczenie.</span><span class="sxs-lookup"><span data-stu-id="654a0-111">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="654a0-112">Opis</span><span class="sxs-lookup"><span data-stu-id="654a0-112">Description</span></span> | <span data-ttu-id="654a0-113">Opis potrącenia.</span><span class="sxs-lookup"><span data-stu-id="654a0-113">A description for the deduction.</span></span> |
   | <span data-ttu-id="654a0-114">Weszła w życie</span><span class="sxs-lookup"><span data-stu-id="654a0-114">Effective</span></span> | <span data-ttu-id="654a0-115">Data rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="654a0-115">The start date.</span></span> <span data-ttu-id="654a0-116">Domyślną wartością jest bieżąca data systemu.</span><span class="sxs-lookup"><span data-stu-id="654a0-116">The default value is the current system date.</span></span> |
   | <span data-ttu-id="654a0-117">Data ważności</span><span class="sxs-lookup"><span data-stu-id="654a0-117">Expiration</span></span> | <span data-ttu-id="654a0-118">Data zakończenia.</span><span class="sxs-lookup"><span data-stu-id="654a0-118">The end date.</span></span> <span data-ttu-id="654a0-119">Wartość domyślna to 31.12.2154, czyli nigdy.</span><span class="sxs-lookup"><span data-stu-id="654a0-119">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="654a0-120">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="654a0-120">Heading</span></span> | <span data-ttu-id="654a0-121">Kod nagłówka z systemu listy płac, który będzie używany przez to potrącenie dla części potrącenia opłacanej przez pracownika podczas przetwarzania świadczeń dla listy płac.</span><span class="sxs-lookup"><span data-stu-id="654a0-121">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="654a0-122">Jest używany w przypadku korzystania z zewnętrznego dostawcy listy płac.</span><span class="sxs-lookup"><span data-stu-id="654a0-122">This is used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="654a0-123">Odwołanie do potrącenia dla listy płac pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="654a0-123">Employee payroll deduction reference</span></span> | <span data-ttu-id="654a0-124">Kod potrącenia z systemu listy płac, którego to potrącenie będzie używane dla pracownika etatowego w części jego potrącenia podczas przetwarzania świadczeń dla listy płac.</span><span class="sxs-lookup"><span data-stu-id="654a0-124">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="654a0-125">Nagłówek kwoty</span><span class="sxs-lookup"><span data-stu-id="654a0-125">Amount heading</span></span> | <span data-ttu-id="654a0-126">Kod nagłówka z systemu listy płac, który będzie używany przez tę kwotę potrącenia dla części potrącenia opłacanej przez pracownika podczas przetwarzania świadczeń dla listy płac.</span><span class="sxs-lookup"><span data-stu-id="654a0-126">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="654a0-127">Zwykle jest używany w przypadku korzystania z zewnętrznego dostawcy listy płac.</span><span class="sxs-lookup"><span data-stu-id="654a0-127">This is normally used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="654a0-128">Można usunąć</span><span class="sxs-lookup"><span data-stu-id="654a0-128">Can delete</span></span> | <span data-ttu-id="654a0-129">Określa, czy wartość wyeksportowana z programu Dynamics 365 for Finance and Operations może powodować usunięcie wartości w systemie listy płac.</span><span class="sxs-lookup"><span data-stu-id="654a0-129">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="654a0-130">Kolumny sparowane</span><span class="sxs-lookup"><span data-stu-id="654a0-130">Paired columns</span></span> | <span data-ttu-id="654a0-131">Określa, czy nagłówek i kwota potrącenia mają być eksportowane w sparowanych sąsiadujących kolumnach do systemu listy płac.</span><span class="sxs-lookup"><span data-stu-id="654a0-131">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="654a0-132">Zmień datę wejścia w życie</span><span class="sxs-lookup"><span data-stu-id="654a0-132">Change effective date</span></span> | <span data-ttu-id="654a0-133">Dzień, w którym zmiana potrącenia na świadczenie wejdzie w życie.</span><span class="sxs-lookup"><span data-stu-id="654a0-133">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="654a0-134">W tym dniu po wykonaniu przetwarzania aktualizacji zmiany potrącenia system automatycznie zmieni potrącenie na świadczenie i zaktualizuje wszystkie plany świadczeń skojarzone z tym potrąceniem.</span><span class="sxs-lookup"><span data-stu-id="654a0-134">On this date the system will automatically change the benefit deduction and update all benefit plans associated with this deduction, as long as you run Deduction change update processing.</span></span> |
   | <span data-ttu-id="654a0-135">Zakończono zmianę potrącenia</span><span class="sxs-lookup"><span data-stu-id="654a0-135">Deduction change completed</span></span> | <span data-ttu-id="654a0-136">Pole wyboru Zakończono zmianę potrącenia zostanie automatycznie zaznaczone, gdy proces przetwarzania aktualizacji zmiany potrącenia wprowadzi wszystkie zmiany w potrąceniach na świadczenia.</span><span class="sxs-lookup"><span data-stu-id="654a0-136">The Deduction change completed check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="654a0-137">Aby śledzić zmiany konfiguracji stawki świadczenia i nimi zarządzać, wybierz opcję **Akcje**, a następnie wybierz opcję **Obsługuj wersje**.</span><span class="sxs-lookup"><span data-stu-id="654a0-137">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="654a0-138">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="654a0-138">Select **Save**.</span></span> 
