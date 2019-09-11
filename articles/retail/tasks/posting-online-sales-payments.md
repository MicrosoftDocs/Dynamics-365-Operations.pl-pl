---
title: Księgowanie sprzedaży i płatności online
description: Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d42b585a61214628980cd45a859215443ed55b5
ms.sourcegitcommit: c461758290d7ddc19f0b60701368937c35ef78b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864160"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="7922d-103">Księgowanie sprzedaży i płatności online</span><span class="sxs-lookup"><span data-stu-id="7922d-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="7922d-104">Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym.</span><span class="sxs-lookup"><span data-stu-id="7922d-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="7922d-105">Księgowanie sprzedaży i płatności online jest procesem dwuetapowym.</span><span class="sxs-lookup"><span data-stu-id="7922d-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="7922d-106">Ściąganie danych transakcji sieci sprzedaży w trybie online w HQ.</span><span class="sxs-lookup"><span data-stu-id="7922d-106">Pulling the online retail transaction data in HQ.</span></span>
- <span data-ttu-id="7922d-107">Synchronizowanie zamówień w celu utworzenia zamówień sprzedaży w HQ.</span><span class="sxs-lookup"><span data-stu-id="7922d-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="7922d-108">Dane transakcji detalicznych w trybie online można ściągnąć, ręcznie uruchamiając zadanie P lub tworząc cykliczne zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="7922d-108">Pulling the online retail transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="7922d-109">Ręczne uruchamianie zadania P</span><span class="sxs-lookup"><span data-stu-id="7922d-109">Manually running the P-job</span></span>

1. <span data-ttu-id="7922d-110">Wybierz kolejno opcje Wszystkie obszary robocze > Składniki IT w handlu detalicznym.</span><span class="sxs-lookup"><span data-stu-id="7922d-110">Go to All workspaces > Retail IT.</span></span>
2. <span data-ttu-id="7922d-111">Kliknij Harmonogram dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="7922d-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="7922d-112">Wybierz P-0001.</span><span class="sxs-lookup"><span data-stu-id="7922d-112">Select P-0001.</span></span>
4. <span data-ttu-id="7922d-113">W razie potrzeby skoryguj grupy baz danych kanału.</span><span class="sxs-lookup"><span data-stu-id="7922d-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="7922d-114">Kliknij przycisk Uruchom teraz.</span><span class="sxs-lookup"><span data-stu-id="7922d-114">Click Run now.</span></span>
6. <span data-ttu-id="7922d-115">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="7922d-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="7922d-116">Planowanie cyklicznego zadania P</span><span class="sxs-lookup"><span data-stu-id="7922d-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="7922d-117">Wybierz kolejno opcje Wszystkie obszary robocze > Składniki IT w handlu detalicznym.</span><span class="sxs-lookup"><span data-stu-id="7922d-117">Go to All workspaces > Retail IT.</span></span>
2. <span data-ttu-id="7922d-118">Kliknij Harmonogram dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="7922d-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="7922d-119">Wybierz P-0001.</span><span class="sxs-lookup"><span data-stu-id="7922d-119">Select P-0001.</span></span>
4. <span data-ttu-id="7922d-120">Kliknij Utwórz zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="7922d-120">Click Create batch job.</span></span>
5. <span data-ttu-id="7922d-121">Kliknij Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="7922d-121">Click Run in the background.</span></span>
5. <span data-ttu-id="7922d-122">Włącz Przetwarzanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="7922d-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="7922d-123">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="7922d-123">Click Recurrence..</span></span>
7. <span data-ttu-id="7922d-124">Wybierz opcję Brak daty zakończenia.</span><span class="sxs-lookup"><span data-stu-id="7922d-124">Select the No end date option.</span></span>
8. <span data-ttu-id="7922d-125">W polu Liczba wprowadź interwał między uruchomieniami w minutach.</span><span class="sxs-lookup"><span data-stu-id="7922d-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="7922d-126">Zwykle jest to 5-10.</span><span class="sxs-lookup"><span data-stu-id="7922d-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="7922d-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7922d-127">Click OK.</span></span>
10. <span data-ttu-id="7922d-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7922d-128">Click OK.</span></span>

<span data-ttu-id="7922d-129">Zamówienia można synchronizować ręcznie, uruchamiając zadanie „Synchronizuj zamówienia” lub tworząc cykliczne zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="7922d-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="7922d-130">Ręcznie uruchomiona synchronizacja zamówień</span><span class="sxs-lookup"><span data-stu-id="7922d-130">Manually running order synchronization</span></span> 

<span data-ttu-id="7922d-131">Wykonaj poniższe kroki, aby ręcznie uruchomić zadanie „Synchronizuj zamówienia” raz.</span><span class="sxs-lookup"><span data-stu-id="7922d-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="7922d-132">Wybierz kolejno opcje Wszystkie obszary robocze > Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="7922d-132">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="7922d-133">Kliknij opcję Synchronizuj zamówienia.</span><span class="sxs-lookup"><span data-stu-id="7922d-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="7922d-134">W polu Hierarchia organizacyjna wybierz opcję „Sklepy sieci sprzedaży według regionów”.</span><span class="sxs-lookup"><span data-stu-id="7922d-134">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="7922d-135">Wybierz określony sklep internetowy albo węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="7922d-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="7922d-136">Kliknij strzałkę, aby dodać zaznaczone obiekty.</span><span class="sxs-lookup"><span data-stu-id="7922d-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="7922d-137">Kliknij kartę Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="7922d-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="7922d-138">Wyłącz Przetwarzanie wsadowe</span><span class="sxs-lookup"><span data-stu-id="7922d-138">Disable Batch processing</span></span>
6. <span data-ttu-id="7922d-139">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="7922d-139">Click Recurrence.</span></span>
7. <span data-ttu-id="7922d-140">Wybierz opcję koniec po</span><span class="sxs-lookup"><span data-stu-id="7922d-140">Select End After option</span></span>
8. <span data-ttu-id="7922d-141">W polu Koniec po wpisz 1.</span><span class="sxs-lookup"><span data-stu-id="7922d-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="7922d-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7922d-142">Click OK.</span></span>
10. <span data-ttu-id="7922d-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7922d-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="7922d-144">Planowanie synchronizacji zamówień cyklicznych</span><span class="sxs-lookup"><span data-stu-id="7922d-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="7922d-145">Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym.</span><span class="sxs-lookup"><span data-stu-id="7922d-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="7922d-146">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="7922d-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="7922d-147">Wybierz kolejno opcje Wszystkie obszary robocze > Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="7922d-147">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="7922d-148">Kliknij opcję Synchronizuj zamówienia.</span><span class="sxs-lookup"><span data-stu-id="7922d-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="7922d-149">W polu Hierarchia organizacyjna wybierz opcję „Sklepy sieci sprzedaży według regionów”.</span><span class="sxs-lookup"><span data-stu-id="7922d-149">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="7922d-150">Wybierz określony sklep internetowy albo węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="7922d-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="7922d-151">Kliknij strzałkę, aby dodać zaznaczone obiekty.</span><span class="sxs-lookup"><span data-stu-id="7922d-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="7922d-152">Kliknij kartę Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="7922d-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="7922d-153">Włącz Przetwarzanie wsadowe</span><span class="sxs-lookup"><span data-stu-id="7922d-153">Enable Batch processing</span></span>
6. <span data-ttu-id="7922d-154">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="7922d-154">Click Recurrence.</span></span>
7. <span data-ttu-id="7922d-155">Wybierz opcję Brak daty zakończenia.</span><span class="sxs-lookup"><span data-stu-id="7922d-155">Select the No end date option.</span></span>
8. <span data-ttu-id="7922d-156">W polu Liczba wprowadź interwał między uruchomieniami w minutach.</span><span class="sxs-lookup"><span data-stu-id="7922d-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="7922d-157">Zwykle jest to 2-20.</span><span class="sxs-lookup"><span data-stu-id="7922d-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="7922d-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7922d-158">Click OK.</span></span>
10. <span data-ttu-id="7922d-159">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7922d-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="7922d-160">Jednostki danych uczestniczące w procesie</span><span class="sxs-lookup"><span data-stu-id="7922d-160">Data entities involved in the process</span></span>

- <span data-ttu-id="7922d-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="7922d-161">RetailTransactionTable</span></span>
- <span data-ttu-id="7922d-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="7922d-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="7922d-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="7922d-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="7922d-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="7922d-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="7922d-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="7922d-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="7922d-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="7922d-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="7922d-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="7922d-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="7922d-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="7922d-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="7922d-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="7922d-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="7922d-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="7922d-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="7922d-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="7922d-171">RetailTransactionAttributeTrans</span></span>
