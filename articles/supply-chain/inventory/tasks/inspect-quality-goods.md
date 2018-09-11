--- 
title: "Sprawdzanie jakości towarów"
description: "W tej procedurze pokazano sposób realizacji zlecenia kontroli jakości."
author: perlynne
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: c2313ba26eac8abf6e603f0230f06103802536c4
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="13dec-103">Sprawdzanie jakości towarów</span><span class="sxs-lookup"><span data-stu-id="13dec-103">Inspect the quality of goods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="13dec-104">W tej procedurze pokazano sposób realizacji zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="13dec-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="13dec-105">Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="13dec-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="13dec-106">Przed rozpoczęciem tej przykładowej procedury należy potwierdzić zamówienia zakupu „000016” i zaksięgować dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="13dec-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="13dec-107">Spowoduje to automatyczne utworzenie zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="13dec-107">This will automatically create a quality order.</span></span> <span data-ttu-id="13dec-108">Kontrole jakości są zazwyczaj wykonywane przez pracownika ds. kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="13dec-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="13dec-109">Wybieranie zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="13dec-109">Select a quality order</span></span>
1. <span data-ttu-id="13dec-110">Wybierz kolejno opcje Zarządzanie zapasami > Zadania okresowe > Zarządzanie jakością > Zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="13dec-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="13dec-111">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="13dec-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="13dec-112">Przed rozpoczęciem tej procedury wybierz utworzone zlecenie kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="13dec-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="13dec-113">Rejestrowanie wyników testów</span><span class="sxs-lookup"><span data-stu-id="13dec-113">Record test results</span></span>
1. <span data-ttu-id="13dec-114">Kliknij przycisk Wyniki.</span><span class="sxs-lookup"><span data-stu-id="13dec-114">Click Results.</span></span>
2. <span data-ttu-id="13dec-115">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="13dec-115">Click Edit.</span></span>
3. <span data-ttu-id="13dec-116">W polu Liczba wyników wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="13dec-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="13dec-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="13dec-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="13dec-118">W polu Wynik kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="13dec-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="13dec-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="13dec-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="13dec-120">W tym przykładzie wynik bazuje na wstępnie zdefiniowanym wyniku.</span><span class="sxs-lookup"><span data-stu-id="13dec-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="13dec-121">Zwyczajowo rejestruje się bardziej szczegółowy wynik inspekcji, na przykład rozmiaru lub innego wymiaru.</span><span class="sxs-lookup"><span data-stu-id="13dec-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="13dec-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="13dec-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="13dec-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="13dec-123">Click Save.</span></span>
9. <span data-ttu-id="13dec-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="13dec-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="13dec-125">Sprawdź poprawność zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="13dec-125">Validate the quality order</span></span>
1. <span data-ttu-id="13dec-126">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="13dec-126">Click Validate.</span></span>
2. <span data-ttu-id="13dec-127">W polu Poprawność sprawdzona przez kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="13dec-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="13dec-128">Wybierz użytkownika wykonującego inspekcję.</span><span class="sxs-lookup"><span data-stu-id="13dec-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="13dec-129">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="13dec-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="13dec-130">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="13dec-130">Click Select.</span></span>
5. <span data-ttu-id="13dec-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="13dec-131">Click OK.</span></span>
6. <span data-ttu-id="13dec-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="13dec-132">Close the page.</span></span>


