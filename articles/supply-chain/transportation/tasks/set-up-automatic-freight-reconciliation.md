---
title: Konfigurowanie automatycznego uzgadniania frachtu
description: Ta procedura pokazuje, jak skonfigurować dane dla automatycznego uzgadniania frachtu.
author: ShylaThompson
manager: AnnBe
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7551805b7b942b042a0f0f8d2ce408d0bac19d06
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146280"
---
# <a name="set-up-automatic-freight-reconciliation"></a><span data-ttu-id="0c77b-103">Konfigurowanie automatycznego uzgadniania frachtu</span><span class="sxs-lookup"><span data-stu-id="0c77b-103">Set up automatic freight reconciliation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0c77b-104">Ta procedura pokazuje, jak skonfigurować dane dla automatycznego uzgadniania frachtu.</span><span class="sxs-lookup"><span data-stu-id="0c77b-104">This procedure shows how to set up data for automatic freight reconciliation.</span></span> <span data-ttu-id="0c77b-105">Zwykle wykonuje to kierownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="0c77b-105">This is typically done by a warehouse manager.</span></span> <span data-ttu-id="0c77b-106">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="0c77b-106">You can use this procedure in demo data company USMF.</span></span>


## <a name="set-up-the-freight-bill-type"></a><span data-ttu-id="0c77b-107">Konfigurowanie typu opłaty frachtowej</span><span class="sxs-lookup"><span data-stu-id="0c77b-107">Set up the freight bill type</span></span>
1. <span data-ttu-id="0c77b-108">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Uzgodnienie frachtu > Typ opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="0c77b-108">Go to Transportation management > Setup > Freight reconciliation > Freight bill type.</span></span>
    * <span data-ttu-id="0c77b-109">Typ dokumentu opłaty frachtowej określa, jak powinny być uzgadniane dokumenty opłat frachtowych i faktury przewoźników.</span><span class="sxs-lookup"><span data-stu-id="0c77b-109">The freight bill type defines how freight bills and carrier invoices  should be matched.</span></span>  
2. <span data-ttu-id="0c77b-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0c77b-110">Click New.</span></span>
3. <span data-ttu-id="0c77b-111">W polu Typ opłaty frachtowej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c77b-111">In the Freight bill type field, type a value.</span></span>
4. <span data-ttu-id="0c77b-112">W polu Zestaw aparatu wpisz „Microsoft.Dynamics.Ax.Tms.dll”.</span><span class="sxs-lookup"><span data-stu-id="0c77b-112">In the Engine assembly field, type 'Microsoft.Dynamics.Ax.Tms.dll'.</span></span>
    * <span data-ttu-id="0c77b-113">Jest to biblioteka standardowych kodów aparatu uzgadniania w zarządzaniu transportem.</span><span class="sxs-lookup"><span data-stu-id="0c77b-113">This is the standard Transportation management matching engine code library.</span></span>  
5. <span data-ttu-id="0c77b-114">W polu Klasa aparatu wpisz „Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer”.</span><span class="sxs-lookup"><span data-stu-id="0c77b-114">In the Engine class field, type 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.</span></span>
    * <span data-ttu-id="0c77b-115">Jest to standardowa klasa aparatu uzgadniania w zarządzaniu transportem.</span><span class="sxs-lookup"><span data-stu-id="0c77b-115">This is the standard Transportation management matching engine class.</span></span>  
6. <span data-ttu-id="0c77b-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0c77b-116">Click New.</span></span>
7. <span data-ttu-id="0c77b-117">W polu Opis wybierz wartość, która powinna być zgodna na dokumencie opłaty frachtowej i fakturze przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="0c77b-117">In the Description field, choose the value that should match on the freight bill and the carrier invoice.</span></span>  
8. <span data-ttu-id="0c77b-118">W polu Wymagane dopasowanie wybierz opcję „Tak”.</span><span class="sxs-lookup"><span data-stu-id="0c77b-118">In the Match required field, select 'Yes'.</span></span>
    * <span data-ttu-id="0c77b-119">Jeśli w tym polu ustawisz wartość Tak, oznacza to, że wartość wybrana w polu Opis musi być zgodna z wartościami na dokumencie opłaty frachtowej i na fakturze przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="0c77b-119">If you set this field to Yes this means that the value selected in the Description field needs to match on both the freight bill and the carrier invoice.</span></span> <span data-ttu-id="0c77b-120">Jeśli zostanie ustawiona wartość Nie, pole może być puste w jednym z tych dokumentów.</span><span class="sxs-lookup"><span data-stu-id="0c77b-120">If you set it to No, the field can be blank on one of these.</span></span>  
9. <span data-ttu-id="0c77b-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0c77b-121">Click Save.</span></span>

## <a name="set-up-the-freight-bill-type-assignment"></a><span data-ttu-id="0c77b-122">Konfigurowanie przypisania typu opłaty frachtowej</span><span class="sxs-lookup"><span data-stu-id="0c77b-122">Set up the freight bill type assignment</span></span>
1. <span data-ttu-id="0c77b-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0c77b-123">Close the page.</span></span>
2. <span data-ttu-id="0c77b-124">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Uzgodnienie frachtu > Przypisania typu opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="0c77b-124">Go to Transportation management > Setup > Freight reconciliation > Freight bill type assignments.</span></span>
    * <span data-ttu-id="0c77b-125">Przypisanie typu dokumentu opłaty frachtowej służy do określania, który typ dokumentu opłaty frachtowej jest używany dla określonego przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="0c77b-125">The freight bill type assignment is used to specify which freight bill type is used for a particular carrier.</span></span>   
3. <span data-ttu-id="0c77b-126">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0c77b-126">Click New.</span></span>
4. <span data-ttu-id="0c77b-127">Wprowadź lub wybierz wartość w polu Tryb.</span><span class="sxs-lookup"><span data-stu-id="0c77b-127">In the Mode field, enter or select a value.</span></span>
5. <span data-ttu-id="0c77b-128">Wprowadź lub wybierz wartość w polu Firma przewozowa.</span><span class="sxs-lookup"><span data-stu-id="0c77b-128">In the Shipping carrier field, enter or select a value.</span></span>
6. <span data-ttu-id="0c77b-129">W polu Typ opłaty frachtowej wybierz typ dokumentu opłaty frachtowej, który został wcześniej utworzony.</span><span class="sxs-lookup"><span data-stu-id="0c77b-129">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
7. <span data-ttu-id="0c77b-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0c77b-130">Close the page.</span></span>

## <a name="set-up-the-audit-master"></a><span data-ttu-id="0c77b-131">Konfigurowanie głównej inspekcji</span><span class="sxs-lookup"><span data-stu-id="0c77b-131">Set up the audit master</span></span>
1. <span data-ttu-id="0c77b-132">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Uzgodnienie frachtu > Główna inspekcja.</span><span class="sxs-lookup"><span data-stu-id="0c77b-132">Go to Transportation management > Setup > Freight reconciliation > Audit master.</span></span>
    * <span data-ttu-id="0c77b-133">Główna inspekcja definiuje granice tolerancji dla automatycznego uzgadniania frachtu.</span><span class="sxs-lookup"><span data-stu-id="0c77b-133">The audit master defines the tolerance limits for automatic freight reconciliation.</span></span> <span data-ttu-id="0c77b-134">Określa, o ile kwoty pieniężne na dokumencie opłaty frachtowej i fakturze przewoźnika mogą się różnić, aby jeszcze następowało uzgodnienie.</span><span class="sxs-lookup"><span data-stu-id="0c77b-134">It specifies by how much the monetary amounts on the freight bill and the carrier invoice can differ and still allow reconciliation to occur.</span></span> <span data-ttu-id="0c77b-135">Definiuje również sposób obsługi niezgodności.</span><span class="sxs-lookup"><span data-stu-id="0c77b-135">It also defines how to handle discrepancies.</span></span>  
2. <span data-ttu-id="0c77b-136">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0c77b-136">Click New.</span></span>
3. <span data-ttu-id="0c77b-137">W polu Identyfikator głównej inspekcji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c77b-137">In the Audit master ID field, type a value.</span></span>
4. <span data-ttu-id="0c77b-138">W polu Firma przewozowa zaznacz tę samą firmę przewozową, jak poprzednio.</span><span class="sxs-lookup"><span data-stu-id="0c77b-138">In the Shipping carrier  field, select the same shipping carrier as you did earlier.</span></span>
5. <span data-ttu-id="0c77b-139">W polu Typ opłaty frachtowej wybierz typ dokumentu opłaty frachtowej, który został wcześniej utworzony.</span><span class="sxs-lookup"><span data-stu-id="0c77b-139">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
6. <span data-ttu-id="0c77b-140">Rozwiń sekcję Tolerancja.</span><span class="sxs-lookup"><span data-stu-id="0c77b-140">Expand the Tolerance section.</span></span>
7. <span data-ttu-id="0c77b-141">W polu Minimalny poziom tolerancji wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="0c77b-141">In the Minimum tolerance level field, enter a number.</span></span>
8. <span data-ttu-id="0c77b-142">W polu Maksymalny poziom tolerancji wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="0c77b-142">In the Maximum tolerance level field, enter a number.</span></span>
9. <span data-ttu-id="0c77b-143">Rozwiń sekcję Wynik.</span><span class="sxs-lookup"><span data-stu-id="0c77b-143">Expand the Result section.</span></span>
10. <span data-ttu-id="0c77b-144">W polu Kod przyczyny nadpłaty wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c77b-144">In the Overpayment reason code field, enter or select a value.</span></span>
    * <span data-ttu-id="0c77b-145">Jeśli kwoty pieniężne różnią się na dokumencie opłaty frachtowej i fakturze przewoźnika, kody przyczyn nadpłaty i niedopłaty określają konta, na których należy zarejestrować różnicę, o ile tylko różnica mieści się w granicach tolerancji.</span><span class="sxs-lookup"><span data-stu-id="0c77b-145">If the monetary amounts differ on the freight bill and the carrier invoice, the overpayment and underpayment reason codes specify the accounts that the difference should be registered on, as long as the difference is within the tolerance levels.</span></span>  
11. <span data-ttu-id="0c77b-146">W polu Kod przyczyny niedopłaty wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c77b-146">In the Underpayment reason code field, enter or select a value.</span></span>
12. <span data-ttu-id="0c77b-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0c77b-147">Close the page.</span></span>

