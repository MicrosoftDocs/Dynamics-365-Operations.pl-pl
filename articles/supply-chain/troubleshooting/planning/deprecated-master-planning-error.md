---
title: Wystąpił błąd podczas uruchamiania wbudowanego aparatu planowania głównego
description: Podczas uruchamiania przestarzałego wbudowanego mechanizmu planowania głównego pojawia się komunikat o błędzie.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294156"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a><span data-ttu-id="c16c9-103">Wystąpił błąd podczas uruchamiania wbudowanego aparatu planowania głównego</span><span class="sxs-lookup"><span data-stu-id="c16c9-103">You receive an error when running the built-in master planning engine</span></span>

<span data-ttu-id="c16c9-104">Kod błędu: ReqCalcScheduleItemTablePlanningOptimizationFitError</span><span class="sxs-lookup"><span data-stu-id="c16c9-104">Error code: ReqCalcScheduleItemTablePlanningOptimizationFitError</span></span>

## <a name="symptoms"></a><span data-ttu-id="c16c9-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="c16c9-105">Symptoms</span></span>

<span data-ttu-id="c16c9-106">Podczas uruchamiania planowania nadrzędnego przy użyciu przestarzałego wbudowanego mechanizmu planowania nadrzędnego pojawia się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="c16c9-106">When you run master planning by using the deprecated built-in master planning engine, you receive the following error message:</span></span>

> <span data-ttu-id="c16c9-107">Ten komunikat o błędzie jest wyświetlany, ponieważ wbudowany główny aparat planowania był używany w scenariuszach obsługiwanych przez optymalizację planowania.</span><span class="sxs-lookup"><span data-stu-id="c16c9-107">You receive this error message because the built-in master planning engine was used for scenarios supported by Planning Optimization.</span></span> <span data-ttu-id="c16c9-108">Należy teraz przeprowadzić migrację do optymalizacji planowania, ponieważ bieżące wbudowane planowanie główne zostanie wycofane.</span><span class="sxs-lookup"><span data-stu-id="c16c9-108">You should migrate to Planning Optimization now, as the current built-in master planning will be deprecated.</span></span> <span data-ttu-id="c16c9-109">Należy zauważyć, że ten przebieg planowania głównego zakończył się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="c16c9-109">Note that this master planning run did complete successfully.</span></span> <span data-ttu-id="c16c9-110">Jeśli migracja jest silnie uzależniona od oczekujących funkcji, można zażądać wyjątku od dalszego korzystania z wbudowanego głównego silnika planowania.</span><span class="sxs-lookup"><span data-stu-id="c16c9-110">In case your migration has strong dependencies on pending features, an exception to continued usage of the built-in master planning engine can be requested.</span></span> <span data-ttu-id="c16c9-111">Wypełnij poniższy kwestionariusz, aby rozpocząć i w razie potrzeby poprosić o wyjątek od migracji do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c16c9-111">Please complete the following questionnaire to get started and, if relevant, request an exception from migration to Planning Optimization.</span></span> [<span data-ttu-id="c16c9-112">Kwestionariusz migracji i wyjątków w optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="c16c9-112">Planning Optimization migration and exception questionnaire</span></span>](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a><span data-ttu-id="c16c9-113">Powód</span><span class="sxs-lookup"><span data-stu-id="c16c9-113">Cause</span></span>

<span data-ttu-id="c16c9-114">Jeśli prowadzisz planowanie i nie używasz funkcji kontroli produkcji, powinieneś rozważyć migrację do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c16c9-114">If you run planning and don't use production control features, you should consider migrating to Planning Optimization.</span></span> <span data-ttu-id="c16c9-115">Wbudowany aparat planowania głównego jest wycofywany.</span><span class="sxs-lookup"><span data-stu-id="c16c9-115">The built-in master planning engine is being deprecated.</span></span> <span data-ttu-id="c16c9-116">Dlatego, jeśli chcesz nadal używać go bez otrzymywania komunikatu o błędzie, musisz ubiegać się o wyjątek od firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c16c9-116">Therefore, if you want to continue to use it without receiving the error message, you must apply for an exception from Microsoft.</span></span>

## <a name="resolution"></a><span data-ttu-id="c16c9-117">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="c16c9-117">Resolution</span></span>

<span data-ttu-id="c16c9-118">Aby uzyskać więcej informacji na temat migracji do optymalizacji planowania lub ubiegania się o wyjątek umożliwiający dalsze korzystanie z przestarzałego wbudowanego mechanizmu planowania, patrz [Migracja do optymalizacji planowania w ramach planowania głównego](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span><span class="sxs-lookup"><span data-stu-id="c16c9-118">For more information about how to migrate to Planning Optimization, or how to apply for an exception so that you can continue to use the deprecated built-in planning engine instead, see [Migration to Planning Optimization for master planning](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span></span>
