---
title: Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze
description: Ten temat pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e14a4fc72d256bea31296bff80d5b5818b95ea9d
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527426"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="1f95c-103">Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze</span><span class="sxs-lookup"><span data-stu-id="1f95c-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1f95c-104">Ta procedura pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani.</span><span class="sxs-lookup"><span data-stu-id="1f95c-104">This procedure shows how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> 

<span data-ttu-id="1f95c-105">Proces zmiany alokacji jest kontrolowany przez **Wyjątek pracy** i używany przez **Pracownika** magazynu.</span><span class="sxs-lookup"><span data-stu-id="1f95c-105">The reallocation process is controlled by a **Work exception** and used by the warehouse **worker.**</span></span>

<span data-ttu-id="1f95c-106">Możliwe jest użycie zarówno automatycznego, ręcznego, jak i obu procesów zmiany alokacji:</span><span class="sxs-lookup"><span data-stu-id="1f95c-106">It is possible to use Automatic, Manual, or both reallocation processes:</span></span>

- <span data-ttu-id="1f95c-107">Automatyczna zmiana alokacji – dyrektywy lokalizacji służą do określenia, czy towary są dostępne w innej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1f95c-107">Automatic reallocation - Location directives are used to determine if the goods are available at another location.</span></span> <span data-ttu-id="1f95c-108">Jeśli to możliwe, praca zostanie zaktualizowana, a użytkownik magazynu zostanie skierowany do lokalizacji alternatywnej.</span><span class="sxs-lookup"><span data-stu-id="1f95c-108">If possible, the work will be updated and the warehouse user will be directed to the alternative location.</span></span>
- <span data-ttu-id="1f95c-109">Ręczna zmiana pozycji – umożliwia użytkownikowi systemu magazynowego wybranie jednej lub wielu lokalizacji z niezarezerwowanymi ilościami towarów.</span><span class="sxs-lookup"><span data-stu-id="1f95c-109">Manual reallocation - Allows the warehouse user to select from one or more locations with unreserved quantities of goods.</span></span> 
- <span data-ttu-id="1f95c-110">Automatycznie i ręcznie – Jeśli system nie jest w stanie wykonać automatycznej zmiany alokacji, a są dostępne lokalizacje z niezarezerwowanymi ilościami, użytkownik będzie monitowany o wybranie lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1f95c-110">Automatic and manual - If the system is unable to perform an automatic reallocation, and locations are available with unreserved quantities, the user will be prompted to select a location.</span></span>

## <a name="set-up-work-exceptions"></a><span data-ttu-id="1f95c-111">Ustaw wyjątki pracy</span><span class="sxs-lookup"><span data-stu-id="1f95c-111">Set up work exceptions</span></span>
<span data-ttu-id="1f95c-112">Istnieje możliwość zdefiniowania kilku wyjątków dotyczących pracy z różnymi zasadami zmiany alokacji towarów, aby umożliwić pracownikowi magazynu wybór towaru na podstawie potrzeb przesyłki, którą akurat przetwarza.</span><span class="sxs-lookup"><span data-stu-id="1f95c-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>

<span data-ttu-id="1f95c-113">Do stworzenia tej procedury wykorzystano dane z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="1f95c-113">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="1f95c-114">W **okienku nawigacji** przejdź do **Zarządzanie magazynem > Ustawienia > Praca > Wyjątki dotyczące pracy**.</span><span class="sxs-lookup"><span data-stu-id="1f95c-114">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="1f95c-115">Kliknij przycisk **Nowy**</span><span class="sxs-lookup"><span data-stu-id="1f95c-115">Click **New**</span></span> 
3. <span data-ttu-id="1f95c-116">W polu **Kod wyjątku pracy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1f95c-116">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="1f95c-117">Będzie to tytuł tego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="1f95c-117">This will be the title of this exception .</span></span> <span data-ttu-id="1f95c-118">Na przykład: Ręczne pobieranie w niedomiarze.</span><span class="sxs-lookup"><span data-stu-id="1f95c-118">For example, Short picking manual.</span></span>
4. <span data-ttu-id="1f95c-119">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1f95c-119">In the **Description** field, type a value.</span></span> <span data-ttu-id="1f95c-120">Będzie to krótki opis wykorzystania tego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="1f95c-120">This will be a short description of the usage of this exception.</span></span> <span data-ttu-id="1f95c-121">Na przykład, Pobranie w niedomiarze – pozycja niedostępna.</span><span class="sxs-lookup"><span data-stu-id="1f95c-121">For example, Short picking - item not available.</span></span>
5. <span data-ttu-id="1f95c-122">W polu **Typ wyjątku** zaznacz wartość „**Pobranie w niedomiarze**”.</span><span class="sxs-lookup"><span data-stu-id="1f95c-122">In the **Exception** type field, select **Short pick**.</span></span>
6. <span data-ttu-id="1f95c-123">Zaznacz pole wyboru **Korekta zapasów**.</span><span class="sxs-lookup"><span data-stu-id="1f95c-123">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="1f95c-124">Jeśli została wybrana, ta opcja oznacza, że zapasy będą automatycznie korygowane na 0 w lokalizacji pobierania w niedomiarze.</span><span class="sxs-lookup"><span data-stu-id="1f95c-124">If selected, inventory will automatically be adjusted to 0 at the short picked location.</span></span>
7. <span data-ttu-id="1f95c-125">W polu **Kod domyślnego typu korekty** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1f95c-125">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="1f95c-126">Na przykład w USMF można wybrać opcję **Usuń Res Adj Out**. Każdy kod typu korekty zawiera cztery cechy: nazwa, opis, nazwa arkusza magazynowego i **Usuń rezerwacje**.</span><span class="sxs-lookup"><span data-stu-id="1f95c-126">For example, in USMF you can select **Remove Res Adj Out**. Each Adjustment type code contains four characteristics: name, description, inventory journal name, and **Remove reservations**.</span></span> <span data-ttu-id="1f95c-127">Jeśli opcja **Usuń rezerwacje** jest włączona, rezerwacje wiersza zamówienia z pobrania w niedomiarze zostanie usunięte.</span><span class="sxs-lookup"><span data-stu-id="1f95c-127">If **Remove reservations** is enabled, the short-picked order line's reservations will be removed.</span></span>  
8. <span data-ttu-id="1f95c-128">W polu **Zmiana pozycji przedmiotów** wybierz wartość, np. „Ręcznie”.</span><span class="sxs-lookup"><span data-stu-id="1f95c-128">In the **Item reallocation** field, select a value, such as Manual.</span></span> <span data-ttu-id="1f95c-129">Jeśli wybierzesz opcję Ręcznie lub Automatyczne i ręczne, pracownikowi magazynu trzeba włączyć funkcję stosowania ręcznej zmiany alokacji.</span><span class="sxs-lookup"><span data-stu-id="1f95c-129">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="1f95c-130">Konfigurowanie pracownika do używania ręcznej zmiany alokacji</span><span class="sxs-lookup"><span data-stu-id="1f95c-130">Set up a worker to use manual item reallocation</span></span>

<span data-ttu-id="1f95c-131">Do stworzenia tej procedury wykorzystano dane z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="1f95c-131">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="1f95c-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1f95c-132">Close the page.</span></span>
2. <span data-ttu-id="1f95c-133">W **okienku nawigacji** przejdź do **Zarządzanie magazynem > Ustawienia > Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="1f95c-133">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="1f95c-134">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="1f95c-134">Click **Edit**.</span></span>
4. <span data-ttu-id="1f95c-135">Na liście zaznacz pracownika.</span><span class="sxs-lookup"><span data-stu-id="1f95c-135">In the list, select worker.</span></span> <span data-ttu-id="1f95c-136">Na przykład Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="1f95c-136">For example, Julia Funderburk.</span></span>
5. <span data-ttu-id="1f95c-137">Rozwiń skróconą kartę **Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="1f95c-137">Expand the **Users** FastTab.</span></span>
6. <span data-ttu-id="1f95c-138">Na liście wybierz **Identyfikator użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="1f95c-138">In the list, select a **User ID**.</span></span> <span data-ttu-id="1f95c-139">Na przykład 24.</span><span class="sxs-lookup"><span data-stu-id="1f95c-139">For example, 24.</span></span>
7. <span data-ttu-id="1f95c-140">Rozwiń skróconą kartę **Praca**.</span><span class="sxs-lookup"><span data-stu-id="1f95c-140">Expand the **Work** FastTab.</span></span>
8. <span data-ttu-id="1f95c-141">W polu **Zezwalaj na ręczną zmianę alokacji pozycji** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="1f95c-141">Select **Yes** in the **Allow manual item reallocation** field.</span></span>
