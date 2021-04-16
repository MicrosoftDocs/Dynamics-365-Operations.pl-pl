---
title: Ustaw kody przyczyn
description: W programie Dynamics 365 Human Resources kody przyczyn są używane do wyjaśniania, dlaczego świadczenia dla pracownika się zmieniają.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ee74cb8b11c9b72940448077ee485ade4c0b7a39
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801054"
---
# <a name="set-up-reason-codes"></a><span data-ttu-id="d4321-103">Ustaw kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="d4321-103">Set up reason codes</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d4321-104">W programie Dynamics 365 Human Resources kody przyczyn są używane do wyjaśniania, dlaczego świadczenia dla pracownika się zmieniają.</span><span class="sxs-lookup"><span data-stu-id="d4321-104">Dynamics 365 Human Resources uses reason codes to explain why an employee’s benefits are changing.</span></span>

> [!NOTE]
> <span data-ttu-id="d4321-105">W styczniu 2021 r. kody przyczyn są migrujące do obszaru roboczego **Zarządzanie pracownikami**, a nie do obszaru roboczego **Zarządzanie świadczeniami**.</span><span class="sxs-lookup"><span data-stu-id="d4321-105">As of January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="d4321-106">Aby uzyskać więcej informacji, zobacz [Ręczna migracja kodów przyczyny do zarządzania personelem](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span><span class="sxs-lookup"><span data-stu-id="d4321-106">For more information, see [Manually migrate reason codes to Personnel management](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span></span>

## <a name="create-reason-codes"></a><span data-ttu-id="d4321-107">Tworzenie kodów przyczyn</span><span class="sxs-lookup"><span data-stu-id="d4321-107">Create reason codes</span></span>

1. <span data-ttu-id="d4321-108">W obszarze roboczym **Zarządzanie pracownikami** (lub obszarze roboczym **Zarządzanie świadczeniami**, jeśli kody przyczyn nie zostały jeszcze poddane migracji), wybierz opcję **Łącza**, a następnie wybierz pozycję **Kody przyczyn**.</span><span class="sxs-lookup"><span data-stu-id="d4321-108">In the **Personnel management** workspace (or **Benefits management** workspace if your reason codes haven't yet migrated), select **Links**, and then select **Reason codes**.</span></span>

2. <span data-ttu-id="d4321-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d4321-109">Select **New**.</span></span>

3. <span data-ttu-id="d4321-110">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="d4321-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="d4321-111">Pole</span><span class="sxs-lookup"><span data-stu-id="d4321-111">Field</span></span> | <span data-ttu-id="d4321-112">Opis</span><span class="sxs-lookup"><span data-stu-id="d4321-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d4321-113">**Kod przyczyny**</span><span class="sxs-lookup"><span data-stu-id="d4321-113">**Reason code**</span></span> | <span data-ttu-id="d4321-114">Unikatowa nazwa identyfikująca przyczynę, dla której pracownik etatowy zmienia rejestrację na inny plan świadczeń.</span><span class="sxs-lookup"><span data-stu-id="d4321-114">A unique name to identify the reason an employee would change a benefit plan enrollment.</span></span> |
   | <span data-ttu-id="d4321-115">**Opis**</span><span class="sxs-lookup"><span data-stu-id="d4321-115">**Description**</span></span> | <span data-ttu-id="d4321-116">Opis kodu przyczyny.</span><span class="sxs-lookup"><span data-stu-id="d4321-116">A description of the reason code.</span></span> |

4. <span data-ttu-id="d4321-117">W **Odpowiednich scenariuszach** ustaw wartość **Zarządzanie świadczeniami** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d4321-117">Under **Applicable scenarios**, set **Benefits management** to **Yes**.</span></span> <span data-ttu-id="d4321-118">(Nie dotyczy, jeśli kody przyczyn nie zostały jeszcze zmigrowane do obszar roboczy **Zarządzanie pracownikami**.)</span><span class="sxs-lookup"><span data-stu-id="d4321-118">(Not applicable if your reason codes haven't yet migrated to the **Personnel management** workspace.)</span></span>

5. <span data-ttu-id="d4321-119">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d4321-119">Select **Save**.</span></span>

## <a name="manually-migrate-reason-codes-to-personnel-management"></a><span data-ttu-id="d4321-120">Ręczna migracja kodów przyczyny do zarządzania personelem</span><span class="sxs-lookup"><span data-stu-id="d4321-120">Manually migrate reason codes to Personnel management</span></span>

<span data-ttu-id="d4321-121">W styczniu 2021 r. kody przyczyn są migrujące do obszaru roboczego **Zarządzanie pracownikami**, a nie do obszaru roboczego **Zarządzanie świadczeniami**.</span><span class="sxs-lookup"><span data-stu-id="d4321-121">In January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="d4321-122">Większość danych kodu przyczyny zostanie automatycznie przeniesiona do Twojego środowiska.</span><span class="sxs-lookup"><span data-stu-id="d4321-122">Most reason code data will automatically migrate in your environment.</span></span> <span data-ttu-id="d4321-123">Niektóre dane kodu przyczyny mogą nie być przenoszone.</span><span class="sxs-lookup"><span data-stu-id="d4321-123">Some reason code data might not migrate.</span></span> <span data-ttu-id="d4321-124">Na przykład kody przyczyn mają teraz maksymalnie 15 znaków, więc żadne kody przyczyn dłuższe niż 15 znaków nie zostaną automatycznie przeniesione.</span><span class="sxs-lookup"><span data-stu-id="d4321-124">For example, reason codes now have a 15-character maximum, so any reason codes longer than 15 characters won't migrate automatically.</span></span>

<span data-ttu-id="d4321-125">Na stronie **Łącza** w obszarze roboczym **Zarządzanie świadczeniami** zostanie wyświetlony transparent informjący o migracji i o tym, czy jakieś kody przyczyn nie były migrowane.</span><span class="sxs-lookup"><span data-stu-id="d4321-125">You'll see a banner on the **Links** page of the **Benefits management** workspace informing you about the migration and whether any reason codes didn't migrate.</span></span>

1. <span data-ttu-id="d4321-126">Wybierz **Kody przyczyn**, aby uzyskać szczegółowe informacje o stanie migracji.</span><span class="sxs-lookup"><span data-stu-id="d4321-126">Select **Reason codes** for details about migration status.</span></span>

   <span data-ttu-id="d4321-127">[![Kody przyczyn](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span><span class="sxs-lookup"><span data-stu-id="d4321-127">[![Reason codes](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span></span>

2. <span data-ttu-id="d4321-128">Wybierz kod przyczyny, który nie został migrowany.</span><span class="sxs-lookup"><span data-stu-id="d4321-128">Select a reason code that failed to migrate.</span></span>

   <span data-ttu-id="d4321-129">[![Stan migracji kodu przyczyny](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span><span class="sxs-lookup"><span data-stu-id="d4321-129">[![Reason code migration status](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span></span>

3. <span data-ttu-id="d4321-130">Wybierz opcję **Migracja kodu przyczyny**.</span><span class="sxs-lookup"><span data-stu-id="d4321-130">Select **Migrate reason code**.</span></span>

   <span data-ttu-id="d4321-131">[![Dokonaj migracji kodu przyczyny](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span><span class="sxs-lookup"><span data-stu-id="d4321-131">[![Migrate reason code](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span></span>

4. <span data-ttu-id="d4321-132">W okienku **Migracja kodu przyczyny świadczenia** dostępne są dwie opcje mapowania na kod przyczyny zarządzania pracownikami:</span><span class="sxs-lookup"><span data-stu-id="d4321-132">In the **Benefit reason code migration** pane, you have two options for mapping to a Personnel management reason code:</span></span>

   - <span data-ttu-id="d4321-133">Aby użyć istniejącego kodu przyczyny w zarządzaniu pracownikami, wybierz go z listy rozwijanej **Użyj istniejącego kodu przyczyny**.</span><span class="sxs-lookup"><span data-stu-id="d4321-133">To use an existing reason code in Personnel management, choose one from the **Use existing reason code** dropdown.</span></span>
     > [!NOTE]
     > <span data-ttu-id="d4321-134">Możesz użyć istniejącego kodu przyczyny w zarządzaniu personelem tylko wtedy, gdy inny kod przyczyny zarządzania świadczeniami nie został już do niego migrowany.</span><span class="sxs-lookup"><span data-stu-id="d4321-134">You can only use an existing reason code in Personnel management if another Benefits management reason code hasn't already migrated to it.</span></span>
   - <span data-ttu-id="d4321-135">Aby utworzyć nowy kod przyczyny w zarządzaniu pracownikami, wprowadź nowy w polu **Nowy kod przyczyny**, a następnie wprowadź opis w polu **Nowy opis**.</span><span class="sxs-lookup"><span data-stu-id="d4321-135">To create a new reason code in Personnel management, enter a new one in **New reason code**, and then enter a description in **New description**.</span></span>

   <span data-ttu-id="d4321-136">[![Mapuj na kod przyczyny zarządzania pracownikami](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span><span class="sxs-lookup"><span data-stu-id="d4321-136">[![Map to a Personnel management reason code](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span></span>

<span data-ttu-id="d4321-137">Po migrowania kodów przyczyny do funkcji Zarządzania pracownikami opcja używania tych kodów w zarządzaniu świadczeniami jest automatycznie ustawiana na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d4321-137">After reason codes migrate to Personnel management, the option for using them in Benefits management is automatically set to **Yes**.</span></span>

<span data-ttu-id="d4321-138">[![Użyj kodu przyczyny w zarządzaniu świadczeniami](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span><span class="sxs-lookup"><span data-stu-id="d4321-138">[![Use reason code in Benefits management](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]