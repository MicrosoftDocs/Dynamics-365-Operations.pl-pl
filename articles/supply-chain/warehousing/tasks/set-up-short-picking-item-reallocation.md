--- 
title: Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze
description: "Ta procedura pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani."
author: ShylaThompson
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 99a4afb58f0c4beef818fd7c0a6a1837e00638d8
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="b31ef-103">Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze</span><span class="sxs-lookup"><span data-stu-id="b31ef-103">Set up short picking item reallocation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b31ef-104">Ta procedura pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani.</span><span class="sxs-lookup"><span data-stu-id="b31ef-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> <span data-ttu-id="b31ef-105">Istnieje możliwość używania procesu automatycznej zmiany alokacji, który wykorzystuje dyrektywy lokalizacji do pobierania towarów, jeśli są one dostępne w innej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="b31ef-105">It’s possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they’re available at another location.</span></span> <span data-ttu-id="b31ef-106">Alternatywnie w przypadku używania ręcznej zmiany alokacji na urządzeniu przenośnym jest wyświetlana lista lokalizacji z dostępnymi ilościami, dzięki czemu pracownik magazynu może wybrać lokalizację do pobrania zapasów.</span><span class="sxs-lookup"><span data-stu-id="b31ef-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="b31ef-107">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b31ef-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="b31ef-108">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="b31ef-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="b31ef-109">Ustaw wyjątki pracy</span><span class="sxs-lookup"><span data-stu-id="b31ef-109">Set up work exceptions</span></span>
1. <span data-ttu-id="b31ef-110">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Wyjątki dotyczące pracy.</span><span class="sxs-lookup"><span data-stu-id="b31ef-110">Go to Warehouse management > Setup > Work > Work exceptions.</span></span>
2. <span data-ttu-id="b31ef-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b31ef-111">Click New.</span></span>
    * <span data-ttu-id="b31ef-112">Istnieje możliwość zdefiniowania kilku wyjątków dotyczących pracy z różnymi zasadami zmiany alokacji towarów, aby umożliwić pracownikowi magazynu wybór towaru na podstawie potrzeb przesyłki, którą akurat przetwarza.</span><span class="sxs-lookup"><span data-stu-id="b31ef-112">It’s possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="b31ef-113">W polu Kod wyjątku pracy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b31ef-113">In the Work exception code field, type a value.</span></span>
    * <span data-ttu-id="b31ef-114">Zatytułuj wyjątek dotyczący pracy w taki sposób, aby wskazywał, do czego wyjątek jest używany.</span><span class="sxs-lookup"><span data-stu-id="b31ef-114">Give the work exception a title to indicate what it’s used for.</span></span> <span data-ttu-id="b31ef-115">Na przykład: Ręczne pobieranie w niedomiarze.</span><span class="sxs-lookup"><span data-stu-id="b31ef-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="b31ef-116">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="b31ef-116">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b31ef-117">W polu Typ wyjątku zaznacz wartość „Pobranie w niedomiarze”.</span><span class="sxs-lookup"><span data-stu-id="b31ef-117">In the Exception type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="b31ef-118">Zaznacz pole wyboru Korekta zapasów.</span><span class="sxs-lookup"><span data-stu-id="b31ef-118">Select the Adjust inventory check box.</span></span>
    * <span data-ttu-id="b31ef-119">Ta opcja oznacza, że zapasy będą automatycznie korygowane na 0 w lokalizacji pobierania w niedomiarze.</span><span class="sxs-lookup"><span data-stu-id="b31ef-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="b31ef-120">W polu Kod domyślnego typu korekty wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b31ef-120">In the Default adjustment type code field, enter or select a value.</span></span>
    * <span data-ttu-id="b31ef-121">Na przykład w firmie USMF można wybrać pozycję „Usuń Res Adj Out”.</span><span class="sxs-lookup"><span data-stu-id="b31ef-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="b31ef-122">W polu Zmiana alokacji pozycji wybierz opcję „Ręcznie”.</span><span class="sxs-lookup"><span data-stu-id="b31ef-122">In the Item reallocation field, select 'Manual'.</span></span>
    * <span data-ttu-id="b31ef-123">Jeśli wybierzesz opcję Ręcznie lub Automatyczne i ręczne, pracownikowi magazynu trzeba włączyć funkcję stosowania ręcznej zmiany alokacji.</span><span class="sxs-lookup"><span data-stu-id="b31ef-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="b31ef-124">Konfigurowanie pracownika do używania ręcznej zmiany alokacji</span><span class="sxs-lookup"><span data-stu-id="b31ef-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="b31ef-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b31ef-125">Close the page.</span></span>
2. <span data-ttu-id="b31ef-126">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Pracownik.</span><span class="sxs-lookup"><span data-stu-id="b31ef-126">Go to Warehouse management > Setup > Worker.</span></span>
3. <span data-ttu-id="b31ef-127">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="b31ef-127">Click Edit.</span></span>
4. <span data-ttu-id="b31ef-128">Na liście zaznacz pracownika 24.</span><span class="sxs-lookup"><span data-stu-id="b31ef-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="b31ef-129">Rozwiń sekcję Praca.</span><span class="sxs-lookup"><span data-stu-id="b31ef-129">Expand the Work section.</span></span>
6. <span data-ttu-id="b31ef-130">W polu Zezwalaj na ręczną zmianę alokacji pozycji wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b31ef-130">Select Yes in the Allow manual item reallocation field.</span></span>


