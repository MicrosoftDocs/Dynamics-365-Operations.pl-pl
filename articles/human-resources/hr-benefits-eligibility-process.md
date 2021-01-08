---
title: Przetwarzanie uprawnień do świadczeń
description: Ta procedura pokazuje działanie procesu kwalifikowania do świadczeń.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: d23dcf4a16979b14ddf58b54e812f21e6698dfc7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419987"
---
# <a name="benefit-eligibility-process"></a><span data-ttu-id="f25d9-103">Przetwarzanie uprawnień do świadczeń</span><span class="sxs-lookup"><span data-stu-id="f25d9-103">Benefit eligibility process</span></span>

<span data-ttu-id="f25d9-104">Ta procedura pokazuje działanie procesu kwalifikowania do świadczeń.</span><span class="sxs-lookup"><span data-stu-id="f25d9-104">This procedure shows how the benefit eligibility process works.</span></span> <span data-ttu-id="f25d9-105">Po zakończeniu procesu można wyświetlić wyniki.</span><span class="sxs-lookup"><span data-stu-id="f25d9-105">When the process is complete you can view the results.</span></span> <span data-ttu-id="f25d9-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="f25d9-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="f25d9-107">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Świadczenia.</span><span class="sxs-lookup"><span data-stu-id="f25d9-107">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="f25d9-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f25d9-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f25d9-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f25d9-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f25d9-110">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="f25d9-110">Click Edit.</span></span>
5. <span data-ttu-id="f25d9-111">W polu Uprawnienie zaznacz opcję „Oparte na regułach”.</span><span class="sxs-lookup"><span data-stu-id="f25d9-111">In the Eligibility field, select 'Rule based'.</span></span>
6. <span data-ttu-id="f25d9-112">W polu Typ reguły zaznacz regułę świadczeń, którą chcesz zastosować do świadczenia.</span><span class="sxs-lookup"><span data-stu-id="f25d9-112">In the Rule type field, select the benefit policy rule you would like applied to the benefit.</span></span>
7. <span data-ttu-id="f25d9-113">W okienku akcji kliknij pozycję Świadczenie.</span><span class="sxs-lookup"><span data-stu-id="f25d9-113">On the Action Pane, click Benefit.</span></span>
8. <span data-ttu-id="f25d9-114">Kliknij przycisk Utwórz zdarzenie dotyczące uprawnień, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f25d9-114">Click Create eligibility event to open the drop dialog.</span></span>
9. <span data-ttu-id="f25d9-115">W polu Zdarzenie wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f25d9-115">In the Event field, type a value.</span></span>
10. <span data-ttu-id="f25d9-116">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f25d9-116">In the Description field, type a value.</span></span>
11. <span data-ttu-id="f25d9-117">W polu Typ zdarzenia wybierz opcję „Otwarcie rejestracji”.</span><span class="sxs-lookup"><span data-stu-id="f25d9-117">In the Event type field, select 'Open enrollment'.</span></span>
12. <span data-ttu-id="f25d9-118">W polu Data początkowa okresu obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="f25d9-118">In the Coverage start date field, enter a date and time.</span></span>
13. <span data-ttu-id="f25d9-119">W polu Data początkowa okresu rejestracji wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="f25d9-119">In the Enrollment period start date field, enter a date and time.</span></span>
14. <span data-ttu-id="f25d9-120">W polu Dni okresu rejestracji wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f25d9-120">In the Days to enroll field, enter a number.</span></span>
15. <span data-ttu-id="f25d9-121">Kliknij przycisk Utwórz zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="f25d9-121">Click Create event.</span></span>
16. <span data-ttu-id="f25d9-122">Na skróconej karcie pracownicy kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f25d9-122">Click Add in the Workers FastTab.</span></span>
17. <span data-ttu-id="f25d9-123">W polu Wyświetlanie według typów zaznacz opcję „Pracownicy”.</span><span class="sxs-lookup"><span data-stu-id="f25d9-123">In the Show by type field, select 'Employees'.</span></span>
18. <span data-ttu-id="f25d9-124">W polu Wyświetlanie według firm wybierz opcję „Bieżąca firma”.</span><span class="sxs-lookup"><span data-stu-id="f25d9-124">In the Show by legal entity field, select 'Current legal entity'.</span></span>
19. <span data-ttu-id="f25d9-125">Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.</span><span class="sxs-lookup"><span data-stu-id="f25d9-125">In the list, mark or unmark all rows.</span></span>
20. <span data-ttu-id="f25d9-126">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f25d9-126">Click OK.</span></span>
21. <span data-ttu-id="f25d9-127">Kliknij przycisk Przetwarzaj.</span><span class="sxs-lookup"><span data-stu-id="f25d9-127">Click Process.</span></span>
22. <span data-ttu-id="f25d9-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f25d9-128">Click OK.</span></span>
23. <span data-ttu-id="f25d9-129">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="f25d9-129">Refresh the page.</span></span>
24. <span data-ttu-id="f25d9-130">Kliknij przycisk Pokaż wyniki.</span><span class="sxs-lookup"><span data-stu-id="f25d9-130">Click Show results.</span></span>
25. <span data-ttu-id="f25d9-131">Otwórz filtr kolumn Stan.</span><span class="sxs-lookup"><span data-stu-id="f25d9-131">Open Status column filter.</span></span>
26. <span data-ttu-id="f25d9-132">Sortuj od A do Z</span><span class="sxs-lookup"><span data-stu-id="f25d9-132">Sort A to Z</span></span>

