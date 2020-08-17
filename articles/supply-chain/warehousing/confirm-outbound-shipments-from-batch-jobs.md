---
title: Potwierdź wychodzące wysyłki z zadań wsadowych
description: W tym temacie opisano sposób konfigurowania zadania wsadowego, które automatycznie potwierdza wysyłki wychodzących zamówień przeniesienia dla ładunków gotowych do wysyłki.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 41dbfb90b7b19c964e725ee0a4c769402414fb17
ms.sourcegitcommit: 27233e0fda61dac541c5210ca8d94ab4ba74966f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2020
ms.locfileid: "3652259"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a><span data-ttu-id="9b03b-103">Potwierdź wychodzące wysyłki z zadań wsadowych</span><span class="sxs-lookup"><span data-stu-id="9b03b-103">Confirm outbound shipments from batch jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b03b-104">W tym temacie opisano sposób konfigurowania zadania wsadowego, które automatycznie potwierdza wysyłki wychodzących zamówień przeniesienia dla ładunków gotowych do wysyłki.</span><span class="sxs-lookup"><span data-stu-id="9b03b-104">This topic describes how to set up a batch job that automatically confirms outbound transfer-order shipments for ready-to-ship loads.</span></span> <span data-ttu-id="9b03b-105">Opisane tu zadanie wsadowe dotyczy tylko wysyłek zamówień przeniesienia, a nie zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9b03b-105">The batch job described here only applies to transfer order shipments, not to sales orders.</span></span>

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a><span data-ttu-id="9b03b-106">Włącz funkcję Potwierdź wychodzące wysyłki z zadań wsadowych</span><span class="sxs-lookup"><span data-stu-id="9b03b-106">Enable the Confirm outbound shipments from batch jobs feature</span></span>

<span data-ttu-id="9b03b-107">Aby móc używać tej funkcji, musi zosyać włączona w systemie.</span><span class="sxs-lookup"><span data-stu-id="9b03b-107">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="9b03b-108">Administratorzy mogą skorzystać ze strony [Zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="9b03b-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="9b03b-109">Funkcja jest wyświetlana jako:</span><span class="sxs-lookup"><span data-stu-id="9b03b-109">The feature is listed as:</span></span>

- <span data-ttu-id="9b03b-110">**Moduł** - *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="9b03b-110">**Module** - *Warehouse management*</span></span>
- <span data-ttu-id="9b03b-111">**Nazwa funkcji** - *Potwierdź wychodzące wysyłki z zadań wsadowych*</span><span class="sxs-lookup"><span data-stu-id="9b03b-111">**Feature name** - *Confirm outbound shipments from batch jobs*</span></span>

## <a name="process-outbound-shipments"></a><span data-ttu-id="9b03b-112">Przetwarzanie wysyłek wychodzących</span><span class="sxs-lookup"><span data-stu-id="9b03b-112">Process outbound shipments</span></span>

<span data-ttu-id="9b03b-113">Aby skonfigurować zaplanowane zadanie wsadowe w celu uruchomienia potwierdzenia wysyłki wychodzącej dla ładunków gotowych do wysyłki:</span><span class="sxs-lookup"><span data-stu-id="9b03b-113">To set up a scheduled batch job to run the outbound shipment confirmation for loads that are ready to ship:</span></span>

1. <span data-ttu-id="9b03b-114">Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Przetwarzanie przesyłek wychodzących**.</span><span class="sxs-lookup"><span data-stu-id="9b03b-114">Go to **Warehouse management \> Periodic tasks \> Process outbound shipments**.</span></span>
1. <span data-ttu-id="9b03b-115">Zostanie otwarte okno dialogowe **Potwierdzanie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="9b03b-115">The **Confirm shipment** dialog box opens.</span></span> <span data-ttu-id="9b03b-116">W **Rekordy do uwzględnienia** na skróconej karcie, wybierz opcję **Filtr**.</span><span class="sxs-lookup"><span data-stu-id="9b03b-116">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="9b03b-117">Otworzy się okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="9b03b-117">The query editor dialog box opens.</span></span> <span data-ttu-id="9b03b-118">Na karcie **Zakres** dodaj wiersz z następującymi wartościami:</span><span class="sxs-lookup"><span data-stu-id="9b03b-118">On the **Range** tab, add a row with the following values:</span></span>
    - <span data-ttu-id="9b03b-119">**Tabela** - *Ładunki*</span><span class="sxs-lookup"><span data-stu-id="9b03b-119">**Table** - *Loads*</span></span>
    - <span data-ttu-id="9b03b-120">**Tabela pochodna** - *Ładunki*</span><span class="sxs-lookup"><span data-stu-id="9b03b-120">**Derived table** - *Loads*</span></span>
    - <span data-ttu-id="9b03b-121">**Pole** - *Stan ładunku*</span><span class="sxs-lookup"><span data-stu-id="9b03b-121">**Field** - *Load status*</span></span>
    - <span data-ttu-id="9b03b-122">**Kryterium** - *Załadowano*</span><span class="sxs-lookup"><span data-stu-id="9b03b-122">**Criteria** - *Loaded*</span></span>
1. <span data-ttu-id="9b03b-123">Wybierz przycisk **OK**, aby powrócić do okna dialogowego **Potwierdzanie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="9b03b-123">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="9b03b-124">Na skróconej karcie **Uruchom w tle** należy skonfigurować **Przetwarzanie wsadowe** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9b03b-124">On the **Run in the background** FastTab, set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="9b03b-125">Na skróconej karcie **Uruchom w tle** wybierz **Cykl**.</span><span class="sxs-lookup"><span data-stu-id="9b03b-125">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="9b03b-126">Zostanie otwarte okno dialogowe **Definiuj cykl**.</span><span class="sxs-lookup"><span data-stu-id="9b03b-126">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="9b03b-127">Umożliwia ustawienie harmonogramu uruchamiania w zależności od potrzeb firmy.</span><span class="sxs-lookup"><span data-stu-id="9b03b-127">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="9b03b-128">Wybierz przycisk **OK**, aby powrócić do okna dialogowego **Potwierdzanie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="9b03b-128">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="9b03b-129">Aby dodać zadanie wsadowe do kolejki przetwarzania wsadowego, należy wybrać opcję **OK** w oknie dialogowym **Potwierdzanie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="9b03b-129">Select **OK** on the **Confirm shipment** dialog box to add the batch job to the batch queue.</span></span>

<span data-ttu-id="9b03b-130">Aby uzyskać więcej informacji, zobacz [Omówienie przetwarzania wsadowego](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9b03b-130">For more information, see [Batch processing overview](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span></span>
