--- 
title: "Konfigurowanie pracownika za pomocą urządzenia przenośnego zadania"
description: "W tej procedurze pokazano, jak przypisać poprawne role do konta użytkownika pracownika, a następnie włączyć pracownikowi możliwość rejestrowania się na produkcji."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5322d77af470c25f0849cbbfbbfbc4a50a7e859b
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="98bdd-103">Konfigurowanie pracownika za pomocą urządzenia przenośnego zadania</span><span class="sxs-lookup"><span data-stu-id="98bdd-103">Configure a worker using the mobile job device</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98bdd-104">W tej procedurze pokazano, jak przypisać poprawne role do konta użytkownika pracownika, a następnie włączyć pracownikowi możliwość rejestrowania się na produkcji.</span><span class="sxs-lookup"><span data-stu-id="98bdd-104">This procedure shows you how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>


## <a name="assign-roles-to-user-account"></a><span data-ttu-id="98bdd-105">Przypisywanie ról do konta użytkownika</span><span class="sxs-lookup"><span data-stu-id="98bdd-105">Assign roles to user account</span></span>
1. <span data-ttu-id="98bdd-106">Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="98bdd-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="98bdd-107">Za pomocą szybkiego filtru wyfiltruj imię i nazwisko pracownika, którego konto użytkownika jest skojarzone z rolą operatora maszyny.</span><span class="sxs-lookup"><span data-stu-id="98bdd-107">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="98bdd-108">W przykładowych danych jest to Shannon.</span><span class="sxs-lookup"><span data-stu-id="98bdd-108">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="98bdd-109">Zaznacz rekord konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="98bdd-109">Highlight the user account record.</span></span>
4. <span data-ttu-id="98bdd-110">Na liście w zaznaczonym wierszu kliknij łącze „Nazwa”, aby wyświetlić szczegółowe informacje o koncie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="98bdd-110">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="98bdd-111">W drzewie zaznacz element „Role\Operator maszyny”.</span><span class="sxs-lookup"><span data-stu-id="98bdd-111">In the tree, select 'Roles\Machine operator'.</span></span>
6. <span data-ttu-id="98bdd-112">Zamknij stronę szczegółów konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="98bdd-112">Close the user account details page.</span></span>
7. <span data-ttu-id="98bdd-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="98bdd-113">Close the page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="98bdd-114">Konfigurowanie konta pracownika</span><span class="sxs-lookup"><span data-stu-id="98bdd-114">Configure worker account.</span></span>
1. <span data-ttu-id="98bdd-115">Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Pracownicy.</span><span class="sxs-lookup"><span data-stu-id="98bdd-115">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="98bdd-116">Za pomocą szybkiego filtru wyfiltruj imię i nazwisko pracownika, którego konto użytkownika jest skojarzone z rolą operatora maszyny.</span><span class="sxs-lookup"><span data-stu-id="98bdd-116">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="98bdd-117">W przykładowych danych jest to Shannon.</span><span class="sxs-lookup"><span data-stu-id="98bdd-117">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="98bdd-118">Zaznacz rekord konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="98bdd-118">Highlight the user account record.</span></span>
4. <span data-ttu-id="98bdd-119">Na liście w zaznaczonym wierszu kliknij łącze „Nazwa”, aby wyświetlić szczegółowe informacje o koncie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="98bdd-119">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="98bdd-120">Kliknij kartę Zatrudnienie.</span><span class="sxs-lookup"><span data-stu-id="98bdd-120">Click the Employment tab.</span></span>
6. <span data-ttu-id="98bdd-121">Rozwiń skróconą kartę rejestracji czasu, a następnie kliknij przycisk Aktywowanie na terminalach rejestracji.</span><span class="sxs-lookup"><span data-stu-id="98bdd-121">Expand the Time registration FastTab and click Activate on registration terminals.</span></span>
7. <span data-ttu-id="98bdd-122">Kliknij opcję Aktywowanie na terminalach rejestracji</span><span class="sxs-lookup"><span data-stu-id="98bdd-122">Click Activate on registration terminals.</span></span>
8. <span data-ttu-id="98bdd-123">W polu Grupa obliczania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="98bdd-123">In the Calculation group field, enter or select a value.</span></span>
9. <span data-ttu-id="98bdd-124">W polu Domyślna grupa obliczania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="98bdd-124">In the Default calculation group field, enter or select a value.</span></span>
10. <span data-ttu-id="98bdd-125">W polu Grupa zatwierdzania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="98bdd-125">In the Approval group field, enter or select a value.</span></span>
11. <span data-ttu-id="98bdd-126">W polu Profil standardowy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="98bdd-126">In the Standard profile field, enter or select a value.</span></span>
12. <span data-ttu-id="98bdd-127">W polu Grupa profilu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="98bdd-127">In the Profile group field, enter or select a value.</span></span>
13. <span data-ttu-id="98bdd-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="98bdd-128">Click OK.</span></span>
14. <span data-ttu-id="98bdd-129">Kliknij przycisk Edytuj, aby wprowadzić numer karty identyfikacyjnej nowego pracownika odpowiedzialnego za rejestrację czasu.</span><span class="sxs-lookup"><span data-stu-id="98bdd-129">Click Edit to enter a badge number for the new time registration worker.</span></span>
15. <span data-ttu-id="98bdd-130">W polu Identyfikator karty identyfikacyjnej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="98bdd-130">In the Badge ID field, type a value.</span></span>
16. <span data-ttu-id="98bdd-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="98bdd-131">Click Save.</span></span>
17. <span data-ttu-id="98bdd-132">Użyj skrótu SaveRecord.</span><span class="sxs-lookup"><span data-stu-id="98bdd-132">Use the SaveRecord shortcut.</span></span>
18. <span data-ttu-id="98bdd-133">Zamknij stronę szczegółów pracownika.</span><span class="sxs-lookup"><span data-stu-id="98bdd-133">Close the worker details page.</span></span>
19. <span data-ttu-id="98bdd-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="98bdd-134">Close the page.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="98bdd-135">Przypisywanie pracownika do grupy urządzeń</span><span class="sxs-lookup"><span data-stu-id="98bdd-135">Assign worker to device group.</span></span>
1. <span data-ttu-id="98bdd-136">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Wykonywanie produkcji > Konfiguruj kartę zadań dla urządzeń.</span><span class="sxs-lookup"><span data-stu-id="98bdd-136">Go to Production control > Setup > Manufacturing execution > Configure job card for devices.</span></span>
2. <span data-ttu-id="98bdd-137">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="98bdd-137">Click Add.</span></span>
3. <span data-ttu-id="98bdd-138">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="98bdd-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="98bdd-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="98bdd-139">Click OK.</span></span>
5. <span data-ttu-id="98bdd-140">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="98bdd-140">Click Edit.</span></span>
6. <span data-ttu-id="98bdd-141">W polu Jednostka produkcyjna można ustawić domyślny filtr dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="98bdd-141">In the Production unit field, you can set the default filter for the worker.</span></span> <span data-ttu-id="98bdd-142">Daje to pewność, że gdy pracownik loguje się do urządzenia, wyświetlane są tylko zadania produkcyjne dla wybranej jednostki produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="98bdd-142">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span>
7. <span data-ttu-id="98bdd-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="98bdd-143">Close the page.</span></span>

