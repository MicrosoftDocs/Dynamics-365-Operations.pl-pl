---
title: Sprawdzanie jakości towarów
description: W tym temacie opisano sposób przetwarzania zleceń kontroli jakości.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec67e7864db12178c0f3cfe8b93d510a46e8a0d4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956141"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="5dcfd-103">Sprawdzanie jakości towarów</span><span class="sxs-lookup"><span data-stu-id="5dcfd-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5dcfd-104">W tym temacie opisano sposób przetwarzania zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-104">This topic describes how to process quality orders.</span></span> <span data-ttu-id="5dcfd-105">Kontrole jakości są zazwyczaj wykonywane przez pracownika ds. kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-105">Quality inspections are typically done by a quality clerk.</span></span>

<span data-ttu-id="5dcfd-106">Jeśli są zainstalowane standardowe dane demonstracyjne, możesz użyć ich do wykonania procedur standardowych w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-106">If the standard demo data is installed, you can use it to complete the procedures in this topic.</span></span> <span data-ttu-id="5dcfd-107">Aby użyć danych demonstracyjnych, należy wybrać firmę *USMF* przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-107">To use the demo data, select the *USMF* legal entity before you begin.</span></span> <span data-ttu-id="5dcfd-108">Następnie musisz potwierdzić zamówienie zakupu *000016* i zatwierdzić dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-108">You must then confirm purchase order *000016* and post a product receipt.</span></span> <span data-ttu-id="5dcfd-109">Zlecenie kontroli jakości zostanie wygenerowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-109">A quality order is automatically generated.</span></span>

## <a name="step-1-select-a-quality-order"></a><span data-ttu-id="5dcfd-110">Krok 1: Wybieranie zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="5dcfd-110">Step 1: Select a quality order</span></span>

<span data-ttu-id="5dcfd-111">Aby wybrać zlecenie kontroli jakości, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-111">To select a quality order, follow these steps.</span></span>

1. <span data-ttu-id="5dcfd-112">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="5dcfd-113">Przed rozpoczęciem tej procedury wybierz wygenerowane zlecenie kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-113">Select the quality order that was generated before you started this procedure.</span></span>

## <a name="step-2-record-test-results"></a><span data-ttu-id="5dcfd-114">Krok 2: Rejestrowanie wyników testów</span><span class="sxs-lookup"><span data-stu-id="5dcfd-114">Step 2: Record test results</span></span>

<span data-ttu-id="5dcfd-115">Aby zarejestrować wyniki testów, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-115">To record test results, follow these steps.</span></span>

1. <span data-ttu-id="5dcfd-116">Wybierz opcję **Wyniki**.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-116">Select **Results**.</span></span>
1. <span data-ttu-id="5dcfd-117">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-117">Select **Edit**.</span></span>
1. <span data-ttu-id="5dcfd-118">W polu **Liczba wyników** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-118">In the **Result quantity** field, enter a number.</span></span>
1. <span data-ttu-id="5dcfd-119">W polu **Wynik** wybierz pożądany rekord.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-119">In the **Outcome** field, select the desired record.</span></span> <span data-ttu-id="5dcfd-120">W tym przykładzie wynik bazuje na wstępnie zdefiniowanym wyniku.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-120">In this example, the result is based on a predefined outcome.</span></span> <span data-ttu-id="5dcfd-121">Zazwyczaj rejestruje się bardziej szczegółowy wynik testu, na przykład rozmiar lub inny wymiar.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-121">Usually, you will record a more specific test result, such as a size or other dimension.</span></span>
1. <span data-ttu-id="5dcfd-122">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-122">Select **Save**.</span></span>
1. <span data-ttu-id="5dcfd-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-123">Close the page.</span></span>

## <a name="step-3-validate-the-quality-order"></a><span data-ttu-id="5dcfd-124">Krok 3: Sprawdzanie poprawności zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="5dcfd-124">Step 3: Validate the quality order</span></span>

<span data-ttu-id="5dcfd-125">Aby sprawdzić poprawność zlecenia kontroli jakości, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-125">To validate the quality order, follow these steps.</span></span>

1. <span data-ttu-id="5dcfd-126">Wybierz **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-126">Select **Validate**.</span></span>
1. <span data-ttu-id="5dcfd-127">W polu **Poprawność sprawdzona przez** wybierz użytkownika, który wykonuje inspekcję.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-127">In the **Validated by** field, select the user who is doing the inspection.</span></span>
1. <span data-ttu-id="5dcfd-128">Wybierz pozycję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-128">Select **Select**.</span></span>
1. <span data-ttu-id="5dcfd-129">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-129">Select **OK**.</span></span>
1. <span data-ttu-id="5dcfd-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5dcfd-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
