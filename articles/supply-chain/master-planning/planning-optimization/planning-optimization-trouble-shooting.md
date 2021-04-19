---
title: Rozwiązywanie problemów z optymalizacją planowania
description: W tym temacie opisano sposób rozwiązywania problemów, które mogą wystąpić podczas pracy z optymalizacją planowania.
author: ChristianRytt
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2100235fadabe6af87849aab7d9ec55d85ea66fa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812890"
---
# <a name="troubleshoot-planning-optimization"></a><span data-ttu-id="4a9bb-103">Rozwiązywanie problemów z optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="4a9bb-103">Troubleshoot Planning Optimization</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4a9bb-104">W tym temacie opisano sposób rozwiązywania typowych problemów, które mogą wystąpić podczas pracy z optymalizacją planowania.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-104">This topic describes how to fix common issues that you might encounter while working with Planning Optimization.</span></span>

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a><span data-ttu-id="4a9bb-105">Nie zakończono instalacji dodatku Optymalizacja planowania</span><span class="sxs-lookup"><span data-stu-id="4a9bb-105">Installation of the Planning Optimization add-in doesn't complete</span></span>

<span data-ttu-id="4a9bb-106">Optymalizacja planowania wymaga środowiska wysokiej dostępności z włączonymi usługami Lifecycle Services (LCS) w warstwie 2 lub wyższej (a nie środowiska OneBox) z aplikacją Dynamics 365 Supply Chain Management w wersji 10.0.7 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-106">Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="4a9bb-107">Jeśli spróbujesz zainstalować dodatek w środowisku OneBox, instalacja nie zostanie zakończona.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-107">If you try to install the add-in on a OneBox environment, the installation won't complete.</span></span>

<span data-ttu-id="4a9bb-108">**Poprawka** : anuluj instalację i użyj środowiska wysokiej dostępności w warstwie 2 lub wyższej (a nie środowiska Onebox).</span><span class="sxs-lookup"><span data-stu-id="4a9bb-108">**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).</span></span>

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a><span data-ttu-id="4a9bb-109">Planowanie zadań wsadowych kończy się niepowodzeniem po włączeniu optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="4a9bb-109">Planning of batch jobs fails when Planning Optimization is enabled</span></span>

<span data-ttu-id="4a9bb-110">Po włączeniu optymalizacji planowania wbudowany aparat planowania głównego jest automatycznie wyłączany.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-110">When you enable Planning Optimization, the built-in master planning engine is automatically disabled.</span></span> <span data-ttu-id="4a9bb-111">Zadania wsadowe planowania głównego utworzone dla wbudowanego aparatu planowania Supply Chain Management dostaw zakończą się niepowodzeniem, jeśli będą wyzwalane po włączeniu optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-111">Master planning batch jobs that were created for the built-in Supply Chain Management planning engine will fail if they are triggered while Planning Optimization is enabled.</span></span> <span data-ttu-id="4a9bb-112">Może zostać wyświetlony komunikat o błędzie, taki jak *Ta operacja wyzwoliła planowanie główne, które nie jest obsługiwane po włączeniu optymalizacji planowania*.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-112">You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span></span>

<span data-ttu-id="4a9bb-113">**Poprawka** : anuluj wszystkie zadania wsadowe planowania głównego, które zostały utworzone dla wbudowanego aparatu Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-113">**Fix**: Cancel all master planning batch jobs that were created for the built-in Supply Chain Management planning engine.</span></span>

## <a name="planning-optimization-results-are-different-from-earlier-results"></a><span data-ttu-id="4a9bb-114">Wyniki optymalizacji planowania różnią się od poprzednich wyników</span><span class="sxs-lookup"><span data-stu-id="4a9bb-114">Planning Optimization results are different from earlier results</span></span>

<span data-ttu-id="4a9bb-115">Optymalizacja planowania różni się od wbudowanego projektu planowania głównego w niektórych obszarach.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-115">Planning Optimization differs from the built-in master planning design in some areas.</span></span> <span data-ttu-id="4a9bb-116">Może to być również spowodowane przez oczekujące funkcje.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-116">This can also be caused by pending features.</span></span>

<span data-ttu-id="4a9bb-117">**Poprawka**: uruchom analizę dopasowania optymalizacji planowania i przeanalizuj wyniki, używając odpowiedniej dokumentacji w celu zrozumienia ich wpływu.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-117">**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact.</span></span> <span data-ttu-id="4a9bb-118">Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="4a9bb-118">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="cant-enable-planning-optimization"></a><span data-ttu-id="4a9bb-119">Nie można włączyć optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="4a9bb-119">Can't enable Planning Optimization</span></span>

<span data-ttu-id="4a9bb-120">**Stan połączenia** musi być mieć wartość **Połączono**, aby można było ustawić opcję **Użyj optymalizacji planowania** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-120">The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**.</span></span> <span data-ttu-id="4a9bb-121">Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z optymalizacją planowania](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="4a9bb-121">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="4a9bb-122">**Poprawka**: upewnij się, że dodatek Optymalizacja planowania został pomyślnie zainstalowany.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-122">**Fix**: Make sure that the Planning Optimization add-in was installed successfully.</span></span>

## <a name="error-message-is-shown-during-ctp"></a><span data-ttu-id="4a9bb-123">Komunikat o błędzie jest wyświetlany podczas CTP</span><span class="sxs-lookup"><span data-stu-id="4a9bb-123">Error message is shown during CTP</span></span>

<span data-ttu-id="4a9bb-124">W przypadku próby uruchomienia operacji „możliwe do zrealizowania” (CTP) z zamówienia sprzedaży, gdy jest włączona optymalizacja planowania, zostanie wyświetlony następujący komunikat o błędzie: *Ta operacja wyzwoliła planowanie główne, które nie jest obsługiwane po włączeniu optymalizacji planowania*.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-124">If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span></span>

<span data-ttu-id="4a9bb-125">Jest to związane z oczekującą funkcją, która jest planowana jako część obsługi zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-125">This is related to a pending feature that is planned as part of the support for production orders.</span></span>

<span data-ttu-id="4a9bb-126">**Poprawka:** unikaj obliczeń CTP po włączeniu optymalizacji planowania, dopóki nie będzie dostępna obsługa CTP.</span><span class="sxs-lookup"><span data-stu-id="4a9bb-126">**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4a9bb-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4a9bb-127">Additional resources</span></span>

[<span data-ttu-id="4a9bb-128">Rozpoczęcie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="4a9bb-128">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="4a9bb-129">Analiza dopasowań optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="4a9bb-129">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]