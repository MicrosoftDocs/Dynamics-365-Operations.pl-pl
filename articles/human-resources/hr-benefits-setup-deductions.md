---
title: Konfigurowanie potrąceń
description: Funkcja potrąceń w programie Microsoft Dynamics 365 Human Resources pozwala określić, ile (jeśli w ogóle) należy potrącić z wynagrodzenia pracownika na każde świadczenie.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 5e645c3f098163626cb686aba347897781d7ebc0
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230069"
---
# <a name="configure-deductions"></a><span data-ttu-id="2e85e-103">Konfigurowanie potrąceń</span><span class="sxs-lookup"><span data-stu-id="2e85e-103">Configure deductions</span></span>

<span data-ttu-id="2e85e-104">Funkcja potrąceń w programie Microsoft Dynamics 365 Human Resources pozwala określić, ile (jeśli w ogóle) należy potrącić z wynagrodzenia pracownika na każde świadczenie.</span><span class="sxs-lookup"><span data-stu-id="2e85e-104">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="2e85e-105">Potrącenia mają daty obowiązywania, więc można prowadzić historyczny rejestr informacji o potrąceniach.</span><span class="sxs-lookup"><span data-stu-id="2e85e-105">Deductions are date-effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="2e85e-106">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Potrącenia**.</span><span class="sxs-lookup"><span data-stu-id="2e85e-106">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="2e85e-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2e85e-107">Select **New**.</span></span>

3. <span data-ttu-id="2e85e-108">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="2e85e-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="2e85e-109">Pole</span><span class="sxs-lookup"><span data-stu-id="2e85e-109">Field</span></span> | <span data-ttu-id="2e85e-110">Opis</span><span class="sxs-lookup"><span data-stu-id="2e85e-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="2e85e-111">**Potrącenie**</span><span class="sxs-lookup"><span data-stu-id="2e85e-111">**Deduction**</span></span> | <span data-ttu-id="2e85e-112">Unikatowy identyfikator używany do identyfikowania potrącenia na świadczenie.</span><span class="sxs-lookup"><span data-stu-id="2e85e-112">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="2e85e-113">**Opis**</span><span class="sxs-lookup"><span data-stu-id="2e85e-113">**Description**</span></span> | <span data-ttu-id="2e85e-114">Opis potrącenia.</span><span class="sxs-lookup"><span data-stu-id="2e85e-114">A description for the deduction.</span></span> |
   | <span data-ttu-id="2e85e-115">**Weszła w życie**</span><span class="sxs-lookup"><span data-stu-id="2e85e-115">**Effective**</span></span> | <span data-ttu-id="2e85e-116">Data rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="2e85e-116">The start date.</span></span> <span data-ttu-id="2e85e-117">Domyślną wartością jest bieżąca data systemu.</span><span class="sxs-lookup"><span data-stu-id="2e85e-117">The default value is the current system date.</span></span> |
   | <span data-ttu-id="2e85e-118">**Data ważności**</span><span class="sxs-lookup"><span data-stu-id="2e85e-118">**Expiration**</span></span> | <span data-ttu-id="2e85e-119">Data zakończenia.</span><span class="sxs-lookup"><span data-stu-id="2e85e-119">The end date.</span></span> <span data-ttu-id="2e85e-120">Wartość domyślna to 31.12.2154, czyli nigdy.</span><span class="sxs-lookup"><span data-stu-id="2e85e-120">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="2e85e-121">**Nagłówek**</span><span class="sxs-lookup"><span data-stu-id="2e85e-121">**Heading**</span></span> | <span data-ttu-id="2e85e-122">Kod nagłówka z systemu listy płac, który będzie używany przez to potrącenie dla części potrącenia opłacanej przez pracownika podczas przetwarzania świadczeń dla listy płac.</span><span class="sxs-lookup"><span data-stu-id="2e85e-122">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="2e85e-123">Jest używany w przypadku korzystania z zewnętrznego dostawcy listy płac.</span><span class="sxs-lookup"><span data-stu-id="2e85e-123">This is used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="2e85e-124">**Odwołanie do potrącenia dla listy płac pracownika etatowego**</span><span class="sxs-lookup"><span data-stu-id="2e85e-124">**Employee payroll deduction reference**</span></span> | <span data-ttu-id="2e85e-125">Kod potrącenia z systemu listy płac, którego to potrącenie będzie używane dla pracownika etatowego w części jego potrącenia podczas przetwarzania świadczeń dla listy płac.</span><span class="sxs-lookup"><span data-stu-id="2e85e-125">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="2e85e-126">**Nagłówek kwoty**</span><span class="sxs-lookup"><span data-stu-id="2e85e-126">**Amount heading**</span></span> | <span data-ttu-id="2e85e-127">Kod nagłówka z systemu listy płac, który będzie używany przez tę kwotę potrącenia dla części potrącenia opłacanej przez pracownika podczas przetwarzania świadczeń dla listy płac.</span><span class="sxs-lookup"><span data-stu-id="2e85e-127">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="2e85e-128">Zwykle jest używany w przypadku korzystania z zewnętrznego dostawcy listy płac.</span><span class="sxs-lookup"><span data-stu-id="2e85e-128">This is normally used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="2e85e-129">**Można usunąć**</span><span class="sxs-lookup"><span data-stu-id="2e85e-129">**Can delete**</span></span> | <span data-ttu-id="2e85e-130">Określa, czy wartość wyeksportowana z programu Dynamics 365 for Finance and Operations może powodować usunięcie wartości w systemie listy płac.</span><span class="sxs-lookup"><span data-stu-id="2e85e-130">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="2e85e-131">**Kolumny sparowane**</span><span class="sxs-lookup"><span data-stu-id="2e85e-131">**Paired columns**</span></span> | <span data-ttu-id="2e85e-132">Określa, czy nagłówek i kwota potrącenia mają być eksportowane w sparowanych sąsiadujących kolumnach do systemu listy płac.</span><span class="sxs-lookup"><span data-stu-id="2e85e-132">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="2e85e-133">**Zmień datę wejścia w życie**</span><span class="sxs-lookup"><span data-stu-id="2e85e-133">**Change effective date**</span></span> | <span data-ttu-id="2e85e-134">Dzień, w którym zmiana potrącenia na świadczenie wejdzie w życie.</span><span class="sxs-lookup"><span data-stu-id="2e85e-134">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="2e85e-135">W tym dniu system automatycznie zmieni potrącenie na świadczenie i zaktualizuje wszystkie plany świadczeń skojarzone z tym potrąceniem, jeśli zostanie uruchomione przetwarzanie **Aktualizacja zmiany potrącenia**.</span><span class="sxs-lookup"><span data-stu-id="2e85e-135">On this date, the system automatically changes the benefit deduction and updates all benefit plans associated with this deduction, as long as you run **Deduction change update** processing.</span></span> |
   | <span data-ttu-id="2e85e-136">**Zakończono zmianę potrącenia**</span><span class="sxs-lookup"><span data-stu-id="2e85e-136">**Deduction change completed**</span></span> | <span data-ttu-id="2e85e-137">Pole wyboru **Zakończono zmianę potrącenia** zostanie automatycznie zaznaczone, gdy proces przetwarzania aktualizacji zmiany potrącenia wprowadzi wszystkie zmiany w potrąceniach na świadczenia.</span><span class="sxs-lookup"><span data-stu-id="2e85e-137">The **Deduction change completed** check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="2e85e-138">Aby śledzić zmiany konfiguracji stawki świadczenia i nimi zarządzać, wybierz opcję **Akcje**, a następnie wybierz opcję **Obsługuj wersje**.</span><span class="sxs-lookup"><span data-stu-id="2e85e-138">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="2e85e-139">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2e85e-139">Select **Save**.</span></span> 
