---
title: Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze
description: Ta procedura pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 964302cb7e7835b6e619602ac7165c9e7adbcefb
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916767"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="d7292-103">Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze</span><span class="sxs-lookup"><span data-stu-id="d7292-103">Set up short picking item reallocation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d7292-104">Ta procedura pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani.</span><span class="sxs-lookup"><span data-stu-id="d7292-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> <span data-ttu-id="d7292-105">Istnieje możliwość używania procesu automatycznej zmiany alokacji, który wykorzystuje dyrektywy lokalizacji do pobierania towarów, jeśli są one dostępne w innej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="d7292-105">It’s possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they’re available at another location.</span></span> <span data-ttu-id="d7292-106">Alternatywnie w przypadku używania ręcznej zmiany alokacji na urządzeniu przenośnym jest wyświetlana lista lokalizacji z dostępnymi ilościami, dzięki czemu pracownik magazynu może wybrać lokalizację do pobrania zapasów.</span><span class="sxs-lookup"><span data-stu-id="d7292-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="d7292-107">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d7292-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="d7292-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="d7292-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="d7292-109">Ustaw wyjątki pracy</span><span class="sxs-lookup"><span data-stu-id="d7292-109">Set up work exceptions</span></span>
1. <span data-ttu-id="d7292-110">W **okienku nawigacji** przejdź do **Zarządzanie magazynem > Ustawienia > Praca > Wyjątki dotyczące pracy**.</span><span class="sxs-lookup"><span data-stu-id="d7292-110">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="d7292-111">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d7292-111">Click **New**.</span></span> <span data-ttu-id="d7292-112">Istnieje możliwość zdefiniowania kilku wyjątków dotyczących pracy z różnymi zasadami zmiany alokacji towarów, aby umożliwić pracownikowi magazynu wybór towaru na podstawie potrzeb przesyłki, którą akurat przetwarza.</span><span class="sxs-lookup"><span data-stu-id="d7292-112">It’s possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="d7292-113">W polu **Kod wyjątku pracy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d7292-113">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="d7292-114">Zatytułuj wyjątek dotyczący pracy w taki sposób, aby wskazywał, do czego wyjątek jest używany.</span><span class="sxs-lookup"><span data-stu-id="d7292-114">Give the work exception a title to indicate what it’s used for.</span></span> <span data-ttu-id="d7292-115">Na przykład: Ręczne pobieranie w niedomiarze.</span><span class="sxs-lookup"><span data-stu-id="d7292-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="d7292-116">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d7292-116">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="d7292-117">W polu typ **Wyjątku** zaznacz wartość „Pobranie w niedomiarze”.</span><span class="sxs-lookup"><span data-stu-id="d7292-117">In the **Exception** type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="d7292-118">Zaznacz pole wyboru **Korekta zapasów**.</span><span class="sxs-lookup"><span data-stu-id="d7292-118">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="d7292-119">Ta opcja oznacza, że zapasy będą automatycznie korygowane na 0 w lokalizacji pobierania w niedomiarze.</span><span class="sxs-lookup"><span data-stu-id="d7292-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="d7292-120">W polu **Kod domyślnego typu korekty** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d7292-120">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="d7292-121">Na przykład w firmie USMF można wybrać pozycję „Usuń Res Adj Out”.</span><span class="sxs-lookup"><span data-stu-id="d7292-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="d7292-122">W polu **Zmiana alokacji pozycji** wybierz opcję „Ręcznie”.</span><span class="sxs-lookup"><span data-stu-id="d7292-122">In the **Item reallocation** field, select 'Manual'.</span></span> <span data-ttu-id="d7292-123">Jeśli wybierzesz opcję Ręcznie lub Automatyczne i ręczne, pracownikowi magazynu trzeba włączyć funkcję stosowania ręcznej zmiany alokacji.</span><span class="sxs-lookup"><span data-stu-id="d7292-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="d7292-124">Konfigurowanie pracownika do używania ręcznej zmiany alokacji</span><span class="sxs-lookup"><span data-stu-id="d7292-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="d7292-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d7292-125">Close the page.</span></span>
2. <span data-ttu-id="d7292-126">W **okienku nawigacji** przejdź do **Zarządzanie magazynem > Ustawienia > Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="d7292-126">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="d7292-127">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="d7292-127">Click **Edit**.</span></span>
4. <span data-ttu-id="d7292-128">Na liście zaznacz pracownika 24.</span><span class="sxs-lookup"><span data-stu-id="d7292-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="d7292-129">Rozwiń skróconą kartę **Praca**.</span><span class="sxs-lookup"><span data-stu-id="d7292-129">Expand the **Work** fastTab.</span></span>
6. <span data-ttu-id="d7292-130">W polu **Zezwalaj na ręczną zmianę alokacji pozycji** wybierz opcję „Tak”.</span><span class="sxs-lookup"><span data-stu-id="d7292-130">Select 'Yes' in the **Allow manual item reallocation** field.</span></span>

