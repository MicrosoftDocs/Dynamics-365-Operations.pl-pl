---
title: Ustawianie kodów dyspozycji
description: Ta procedura skupia się na skonfigurowaniu kod dyspozycji, którego można używać na urządzeniu przenośnym do obsługi procesu odbioru w zamówieniu zwrotu.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85402e05d55367da5fe89b242ad8eafc727b441e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "324130"
---
# <a name="set-up-dispositions-codes"></a><span data-ttu-id="6cfa0-103">Ustawianie kodów dyspozycji</span><span class="sxs-lookup"><span data-stu-id="6cfa0-103">Set up dispositions codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6cfa0-104">Ta procedura skupia się na skonfigurowaniu kod dyspozycji, którego można używać na urządzeniu przenośnym do obsługi procesu odbioru w zamówieniu zwrotu.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-104">This procedure focuses on the setup of a disposition code that can be used on a mobile device for the return order receiving process.</span></span> <span data-ttu-id="6cfa0-105">Kody dyspozycji to zbiór reguł, których można używać podczas przyjęcia towarów.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-105">Disposition codes are a collection of rules that can be used when items are received.</span></span> <span data-ttu-id="6cfa0-106">Na przykład gdy użytkownik pracy używa urządzenia przenośnego do przyjęcia towarów, które zostały uszkodzone, musi zeskanować kod dyspozycji tych towarów.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-106">For example, when a work user uses a mobile device to receive items that were damaged, the user must scan a disposition code for damaged items.</span></span> <span data-ttu-id="6cfa0-107">Z zeskanowanego kodu dyspozycji można określić stan zapasów przyjętych towarów, szablon pracy i dyrektywę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-107">The inventory status of the goods received, the work template, and the location directive can be determined from the scanned disposition code.</span></span> <span data-ttu-id="6cfa0-108">Dla procesów przyjęcia w zamówieniu zakupu oraz zgłaszania wyrobów gotowych w zleceniu produkcyjnym używanie kodu dyspozycji jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-108">For the purchase order receiving process and the production order report as finished process, the use of a disposition code is optional.</span></span> <span data-ttu-id="6cfa0-109">W procesie przyjęcia zwrotu w zamówieniu sprzedaży jeśli towary są rejestrowane za pomocą urządzenia przenośnego, użycie kodu dyspozycji jest obowiązkowe.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-109">For the sales order return receiving process, if the items are registered using a mobile device, the use of disposition code is mandatory.</span></span>  <span data-ttu-id="6cfa0-110">Przewodnik utworzono przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-110">This guide was created using the demo data company USMF.</span></span> <span data-ttu-id="6cfa0-111">Ta procedura jest przeznaczona dla kierownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-111">This procedure is intended for the warehouse manager.</span></span> 

1. <span data-ttu-id="6cfa0-112">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Kody dyspozycji.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-112">Go to Warehouse management > Setup > Mobile device > Disposition codes.</span></span>
2. <span data-ttu-id="6cfa0-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-113">Click New.</span></span>
    * <span data-ttu-id="6cfa0-114">Utwórz nowy kod dyspozycji do używania w zwrotach od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-114">Create a new disposition code to use for customer returns.</span></span>  
3. <span data-ttu-id="6cfa0-115">W polu Kod dyspozycji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-115">In the Disposition code field, type a value.</span></span>
4. <span data-ttu-id="6cfa0-116">W polu Stan zapasów wybierz stan zapasów tam, gdzie występuje blokowanie zapasów.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-116">In the Inventory status field, select an inventory status where there is inventory blocking.</span></span>
    * <span data-ttu-id="6cfa0-117">Jeśli używasz firmy USMF, zaznacz opcję „Blokowanie”.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-117">If you're using USMF, select 'Blocking'.</span></span> <span data-ttu-id="6cfa0-118">Do kodu dyspozycji można dodać stan zapasów, aby zastąpić domyślny stan w wierszach zamówienia.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-118">You can add an inventory status to the disposition code to override the default status that’s on the order lines.</span></span>  
5. <span data-ttu-id="6cfa0-119">W polu Szablon pracy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-119">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="6cfa0-120">Opcjonalnie: Wybierz kod szablonu pracy skojarzony z zamówieniem zwrotu.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-120">Optional: Select a work template code that is associated with a return order.</span></span> <span data-ttu-id="6cfa0-121">Jeśli wartość nie zostanie podana, szablon pracy będzie interpretowany przy użyciu standardowych reguł skonfigurowanych w systemie.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-121">If no value is provided, the work template will be resolved using the standard rules configured in your system.</span></span> <span data-ttu-id="6cfa0-122">Wybranie szablonu pracy ograniczy procesy, z którymi można używać tego kodu dyspozycji.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-122">Selecting a work template will limit the processes this disposition code can be used with.</span></span> <span data-ttu-id="6cfa0-123">Na przykład jeśli kod dyspozycji ma szablon pracy ze zleceniem typu Zamówienie zakupu, nie można go używać do rejestrowania towarów zwracanych przez odbiorców.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-123">For example, if a disposition code has a work template with a work order of type purchase order, it can’t be used to register items that are returned by customers.</span></span>  
6. <span data-ttu-id="6cfa0-124">W polu Kod dyspozycji zwrotu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-124">In the Return disposition code field, type a value.</span></span>
    * <span data-ttu-id="6cfa0-125">Kod dyspozycji zwrotu określa pozostałą część procesu zamówienia zwrotu dla zarejestrowanych towarów.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-125">The return disposition code determines the remainder of the return order process for the items registered.</span></span> <span data-ttu-id="6cfa0-126">W tym przykładzie odbiorca powinien otrzymać fakturę korygującą.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-126">In this example, the customer should receive a credit note.</span></span> <span data-ttu-id="6cfa0-127">Dodaj kod dyspozycji zwrotu zawierający akcję Uznanie.</span><span class="sxs-lookup"><span data-stu-id="6cfa0-127">Add a returns disposition code that contains an action Credit.</span></span>  

