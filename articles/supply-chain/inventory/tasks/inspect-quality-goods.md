---
title: Sprawdzanie jakości towarów
description: W tym temacie wyjaśniono sposób przetwarzania zlecenia kontroli jakości.
author: perlynne
ms.date: 08/01/2019
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
ms.openlocfilehash: 47e7156e5c57d5f983564cc966b4108f1180ff8d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825922"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="ff5fc-103">Sprawdzanie jakości towarów</span><span class="sxs-lookup"><span data-stu-id="ff5fc-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ff5fc-104">W tym temacie wyjaśniono sposób przetwarzania zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-104">This topic explains how to process a quality order.</span></span> <span data-ttu-id="ff5fc-105">Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="ff5fc-106">Przed rozpoczęciem tej przykładowej procedury należy potwierdzić zamówienia zakupu „000016” i zaksięgować dokument przyjęcia produktu.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-106">Before you start this example procedure, you need to confirm purchase order "000016" and post a product receipt.</span></span> <span data-ttu-id="ff5fc-107">Spowoduje to automatyczne utworzenie zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-107">This will automatically create a quality order.</span></span> <span data-ttu-id="ff5fc-108">Kontrole jakości są zazwyczaj wykonywane przez pracownika ds. kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="ff5fc-109">Wybieranie zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="ff5fc-109">Select a quality order</span></span>
1. <span data-ttu-id="ff5fc-110">W okienku nawigacji otwórz **Moduły > Zarządzanie zapasami > Zadania okresowe > Zarządzanie jakością > Zlecenia kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-110">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="ff5fc-111">Przed rozpoczęciem tej procedury wybierz utworzone zlecenie kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-111">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="ff5fc-112">Rejestrowanie wyników testów</span><span class="sxs-lookup"><span data-stu-id="ff5fc-112">Record test results</span></span>
1. <span data-ttu-id="ff5fc-113">Wybierz opcję **Wyniki**.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-113">Select **Results**.</span></span>
2. <span data-ttu-id="ff5fc-114">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-114">Select **Edit**.</span></span>
3. <span data-ttu-id="ff5fc-115">W polu **Liczba wyników** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-115">In the **Result quantity** field, enter a number.</span></span>
4. <span data-ttu-id="ff5fc-116">W polu **Wynik** wybierz odpowiedni rekord z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-116">In the **Outcome** field, select the desired record in the drop-down menu.</span></span>  
- <span data-ttu-id="ff5fc-117">W tym przykładzie wynik bazuje na wstępnie zdefiniowanym wyniku.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-117">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="ff5fc-118">Zwyczajowo rejestruje się bardziej szczegółowy wynik inspekcji, na przykład rozmiaru lub innego wymiaru.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-118">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
5. <span data-ttu-id="ff5fc-119">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-119">Select **Save**.</span></span>
6. <span data-ttu-id="ff5fc-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-120">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="ff5fc-121">Sprawdź poprawność zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="ff5fc-121">Validate the quality order</span></span>
1. <span data-ttu-id="ff5fc-122">Wybierz **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-122">Select **Validate**.</span></span>
2. <span data-ttu-id="ff5fc-123">W polu **Poprawność sprawdzona przez** wybierz użytkownika wykonującego inspekcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-123">In the **Validated by** field, select the user performing the inspection from the drop-down menu.</span></span>  
3. <span data-ttu-id="ff5fc-124">Kliknij opcję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-124">Click **Select**.</span></span>
4. <span data-ttu-id="ff5fc-125">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-125">Select **OK**.</span></span>
5. <span data-ttu-id="ff5fc-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff5fc-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]