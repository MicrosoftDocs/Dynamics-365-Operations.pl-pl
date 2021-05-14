---
title: Włączanie zarządzania kontrolą jakości i niezgodnością
description: Ten temat zawiera omówienie procesu konfigurowania funkcji zarządzania kontrolą jakości i niezgodnościami w systemie Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d5da648e31d07d054246f5d308a6c6cdeb506c
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956261"
---
# <a name="enable-quality-and-nonconformance-management"></a><span data-ttu-id="c506c-103">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="c506c-103">Enable quality and nonconformance management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c506c-104">Ten temat zawiera omówienie procesu konfigurowania funkcji zarządzania kontrolą jakości i niezgodnościami w systemie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c506c-104">This topic provides an overview of the process for setting up and configuring quality and nonconformance management features in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a><span data-ttu-id="c506c-105">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="c506c-105">Enable quality and nonconformance management</span></span>

<span data-ttu-id="c506c-106">Aby włączyć zarządzanie kontrolą jakości w systemie, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c506c-106">Follow these steps to enable quality management on your system.</span></span>

1. <span data-ttu-id="c506c-107">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Parametry modułu Zarządzanie zapasami i magazynem**.</span><span class="sxs-lookup"><span data-stu-id="c506c-107">Go to **Inventory management \> Setup \> Inventory and warehouse management parameters**.</span></span>
1. <span data-ttu-id="c506c-108">Na karcie **Zarządzanie kontrolą jakości** ustaw opcję **Użyj zarządzania kontrolą jakości** na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="c506c-108">On the **Quality management** tab, set the **Use quality management** option to *Yes*.</span></span>
1. <span data-ttu-id="c506c-109">W polu **Stawka godzinowa** wpisz stawkę godzinową pracy w walucie lokalnej.</span><span class="sxs-lookup"><span data-stu-id="c506c-109">In the **Hourly rate** field, enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="c506c-110">Stawka godzinowa używana jest do obliczania kosztów operacji związanych z niezgodnością.</span><span class="sxs-lookup"><span data-stu-id="c506c-110">The hourly rate is used to calculate costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="c506c-111">Stawka godzinowa i obliczone koszty dostarczają informacji pomocniczych o niezgodności.</span><span class="sxs-lookup"><span data-stu-id="c506c-111">The hourly rate and calculated costs provide reference information for a nonconformance.</span></span> <span data-ttu-id="c506c-112">Nie mają one styczności z innymi funkcjami.</span><span class="sxs-lookup"><span data-stu-id="c506c-112">They don't interact with other functionality.</span></span>
1. <span data-ttu-id="c506c-113">Wybierz opcję **Konfigurowanie raportu**.</span><span class="sxs-lookup"><span data-stu-id="c506c-113">Select **Report setup**.</span></span>
1. <span data-ttu-id="c506c-114">Dodaj nowe wiersze dla różnych typów raportów i wybierz typ dokumentu, który ma być używany z poszczególnymi raportami.</span><span class="sxs-lookup"><span data-stu-id="c506c-114">Add new lines for the various report types, and select the type of document to use for each report.</span></span>
1. <span data-ttu-id="c506c-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c506c-115">Close the page.</span></span>
1. <span data-ttu-id="c506c-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c506c-116">Close the page.</span></span>

## <a name="quality-management-configuration-process"></a><span data-ttu-id="c506c-117">Proces konfigurowania zarządzania kontrolą jakości</span><span class="sxs-lookup"><span data-stu-id="c506c-117">Quality management configuration process</span></span>

<span data-ttu-id="c506c-118">Aby można było rozpocząć korzystanie z funkcji zarządzania kontrolą jakości i generować zlecenia kontroli jakości, należy skonfigurować system i wymagania wstępne.</span><span class="sxs-lookup"><span data-stu-id="c506c-118">Before you can start to use the quality management features and generate quality orders, you must configure the system and prerequisites.</span></span> <span data-ttu-id="c506c-119">Poniżej znajduje się lista kroków wymaganych do skonfigurowania zarządzania kontrolą jakości.</span><span class="sxs-lookup"><span data-stu-id="c506c-119">Here is a list of the steps that are required to configure quality management.</span></span>

1. <span data-ttu-id="c506c-120">[Włącz zarządzania kontrolą jakości i niezgodnością](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="c506c-120">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="c506c-121">Opcjonalnie: [Skonfiguruj przyrządy testowe](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-121">Optional: [Configure test instruments](quality-test-instruments.md).</span></span>
1. <span data-ttu-id="c506c-122">[Skonfiguruj testy](quality-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-122">[Configure tests](quality-tests.md).</span></span>
1. <span data-ttu-id="c506c-123">[Skonfiguruj zmienne i wyniki testów](quality-test-variables.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-123">[Configure test variables and outcomes](quality-test-variables.md).</span></span>
1. <span data-ttu-id="c506c-124">[Skonfiguruj grupy testowe](quality-test-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-124">[Configure test groups](quality-test-groups.md).</span></span>
1. <span data-ttu-id="c506c-125">Opcjonalnie: [Skonfiguruj grupy jakości i łącza do produktów](quality-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-125">Optional: [Configure quality groups, and link to products](quality-groups.md).</span></span>
1. <span data-ttu-id="c506c-126">Opcjonalnie: [Skonfiguruj skojarzenia jakości](quality-associations.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-126">Optional: [Configure quality associations](quality-associations.md).</span></span>

<span data-ttu-id="c506c-127">Po zakończeniu konfiguracji można rozpocząć tworzenie i przetwarzanie zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="c506c-127">After the configuration is completed, you can start to create and process quality orders.</span></span> <span data-ttu-id="c506c-128">Aby uzyskać więcej informacji na temat tworzenia zleceń kontroli jakości i korzystania z nich, zobacz [Zlecenia kontroli jakości](quality-orders.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-128">For more information about how to create and work with quality orders, see [Quality orders](quality-orders.md).</span></span>

## <a name="nonconformance-management-configuration-process"></a><span data-ttu-id="c506c-129">Proces konfigurowania zarządzania niezgodnościami</span><span class="sxs-lookup"><span data-stu-id="c506c-129">Nonconformance management configuration process</span></span>

<span data-ttu-id="c506c-130">Aby można było rozpocząć korzystanie z funkcji zarządzania niezgodnościami i generować niezgodności, należy skonfigurować system i wymagania wstępne.</span><span class="sxs-lookup"><span data-stu-id="c506c-130">Before you can start to use the nonconformance management features and generate nonconformances, you must configure the system and prerequisites.</span></span> <span data-ttu-id="c506c-131">Poniżej znajduje się lista kroków wymaganych do skonfigurowania zarządzania niezgodnościami.</span><span class="sxs-lookup"><span data-stu-id="c506c-131">Here is a list of the steps that are required to configure nonconformance management.</span></span>

1. <span data-ttu-id="c506c-132">[Włącz zarządzania kontrolą jakości i niezgodnością](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="c506c-132">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="c506c-133">[Skonfiguruj pracowników odpowiedzialnych za zatwierdzanie niezgodności](quality-responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-133">[Configure workers who are responsible for approving nonconformances](quality-responsible-workers.md).</span></span>
1. <span data-ttu-id="c506c-134">[Skonfiguruj typy problemów](quality-problem-types.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-134">[Configure problem types](quality-problem-types.md).</span></span>
1. <span data-ttu-id="c506c-135">[Skonfiguruj strefy kwarantanny](quality-quarantine-zones.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-135">[Configure quarantine zones](quality-quarantine-zones.md).</span></span>
1. <span data-ttu-id="c506c-136">[Skonfiguruj typów diagnostyczne](quality-diagnostic-types.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-136">[Configure diagnostic types](quality-diagnostic-types.md).</span></span>
1. <span data-ttu-id="c506c-137">[Skonfiguruj operacje](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-137">[Configure operations](quality-operations.md).</span></span>
1. <span data-ttu-id="c506c-138">Opcjonalnie: [Skonfiguruj opłaty związane z kontrolą jakości](quality-charges.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-138">Optional: [Configure quality charges](quality-charges.md).</span></span>

<span data-ttu-id="c506c-139">Po zakończeniu konfiguracji można rozpocząć tworzenie i przetwarzanie niezgodności.</span><span class="sxs-lookup"><span data-stu-id="c506c-139">After the configuration is completed, you can start to create and process nonconformances.</span></span> <span data-ttu-id="c506c-140">Aby uzyskać więcej informacji na temat tworzenia niezgodności i korzystania z nich [Tworzenie i przetwarzanie niezgodności](tasks/create-process-non-conformance.md).</span><span class="sxs-lookup"><span data-stu-id="c506c-140">For more information about how to create and work with nonconformances, see [Create and process nonconformances](tasks/create-process-non-conformance.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c506c-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c506c-141">Additional resources</span></span>

- [<span data-ttu-id="c506c-142">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="c506c-142">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="c506c-143">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="c506c-143">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="c506c-144">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="c506c-144">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
