---
title: Konfigurowanie pracownika za pomocą urządzenia przenośnego zadania
description: Ten temat objaśnia, jak przypisać poprawne role do konta użytkownika pracownika, a następnie włączyć pracownikowi możliwość rejestrowania się na produkcji.
author: ShylaThompson
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6e45ea8fdbe30436badd88d4972fda970755275
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835788"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="d4d50-103">Konfigurowanie pracownika za pomocą urządzenia przenośnego zadania</span><span class="sxs-lookup"><span data-stu-id="d4d50-103">Configure a worker using the mobile job device</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4d50-104">Ten temat objaśnia, jak przypisać poprawne role do konta użytkownika pracownika, a następnie włączyć pracownikowi możliwość rejestrowania się na produkcji.</span><span class="sxs-lookup"><span data-stu-id="d4d50-104">This topic explains how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a><span data-ttu-id="d4d50-105">Sprawdzanie, czy pracownik ma przypisaną odpowiednią rolę</span><span class="sxs-lookup"><span data-stu-id="d4d50-105">Verify that a worker is assigned a certain role</span></span>

<span data-ttu-id="d4d50-106">W tym przykładzie należy sprawdzić, czy użytkownik „SHANNON” ma przypisaną rolę operatora maszyny przed skonfigurowaniem konta pracownika.</span><span class="sxs-lookup"><span data-stu-id="d4d50-106">For this example, verify that user "SHANNON" is assigned the machine operator role before you configure the worker account.</span></span>

1. <span data-ttu-id="d4d50-107">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Użytkownicy > Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="d4d50-108">Wyszukaj użytkownika w szybkim filtrze.</span><span class="sxs-lookup"><span data-stu-id="d4d50-108">Search for a user in the quick filter.</span></span> <span data-ttu-id="d4d50-109">W tym przykładzie wpisz `shannon`.</span><span class="sxs-lookup"><span data-stu-id="d4d50-109">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="d4d50-110">Wybierz łącze w kolumnie **Identyfikator użytkownika** wyświetlonego konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d4d50-110">Select the link in the **User ID** column of the user account that appears.</span></span>
4. <span data-ttu-id="d4d50-111">W drzewie **Role użytkownika** wybierz **Role > Operator maszyny**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-111">In the **User's roles** tree, select **Roles > Machine operator**.</span></span>
5. <span data-ttu-id="d4d50-112">Zamknij strony **szczegóły użytkownika** i **użytkownicy**, aby powrócić do strony głównej.</span><span class="sxs-lookup"><span data-stu-id="d4d50-112">Close the **user details** and **users** pages to return to the home page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="d4d50-113">Konfigurowanie konta pracownika</span><span class="sxs-lookup"><span data-stu-id="d4d50-113">Configure worker account</span></span>
1. <span data-ttu-id="d4d50-114">Przejdź do **okienka nawigacji > Moduły > Zasoby ludzkie > Pracownicy > Pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-114">Go to **Navigation pane > Modules > Human resources > Workers > Workers**.</span></span>
2. <span data-ttu-id="d4d50-115">Wyszukaj użytkownika w szybkim filtrze.</span><span class="sxs-lookup"><span data-stu-id="d4d50-115">Search for a user in the quick filter.</span></span> <span data-ttu-id="d4d50-116">W tym przykładzie wpisz `shannon`.</span><span class="sxs-lookup"><span data-stu-id="d4d50-116">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="d4d50-117">Wybierz łącze w kolumnie **Nazwa** wyświetlonego konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d4d50-117">Select the link in the **Name** column of the user account that appears.</span></span>
4. <span data-ttu-id="d4d50-118">Wybierz kartę **Rejestracja czasu**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-118">Select the **Time registration** tab.</span></span>
5. <span data-ttu-id="d4d50-119">Wybierz **Aktywowanie na terminalach rejestracji**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-119">Select **Activate on registration terminals**.</span></span>
6. <span data-ttu-id="d4d50-120">Wpisz lub wybierz wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="d4d50-120">Enter or select values in the following fields:</span></span>  

    - <span data-ttu-id="d4d50-121">**Grupa obliczania**</span><span class="sxs-lookup"><span data-stu-id="d4d50-121">**Calculation group**</span></span>  
    - <span data-ttu-id="d4d50-122">**Domyślna grupa obliczania**</span><span class="sxs-lookup"><span data-stu-id="d4d50-122">**Default calculation group**</span></span>  
    - <span data-ttu-id="d4d50-123">**Grupa zatwierdzania**</span><span class="sxs-lookup"><span data-stu-id="d4d50-123">**Approval group**</span></span>  
    - <span data-ttu-id="d4d50-124">**Profil standardowy**</span><span class="sxs-lookup"><span data-stu-id="d4d50-124">**Standard profile**</span></span>  
    - <span data-ttu-id="d4d50-125">**Grupa profilu**</span><span class="sxs-lookup"><span data-stu-id="d4d50-125">**Profile group**</span></span>  

7. <span data-ttu-id="d4d50-126">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-126">Select **OK**.</span></span>
8. <span data-ttu-id="d4d50-127">Wybierz **Edytuj**, aby wprowadzić numer karty identyfikacyjnej nowego pracownika odpowiedzialnego za rejestrację czasu.</span><span class="sxs-lookup"><span data-stu-id="d4d50-127">Select **Edit** to enter a badge number for the new time registration worker.</span></span> <span data-ttu-id="d4d50-128">Wprowadź wartość w polu **Identyfikator karty identyfikacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-128">Enter a value in the **Badge ID** field.</span></span>
9. <span data-ttu-id="d4d50-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-129">Select **Save**.</span></span>
10. <span data-ttu-id="d4d50-130">Zamknij strony **Szczegóły pracownika** i **Pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-130">Close the **Worker details** and **Workers** pages.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="d4d50-131">Przypisywanie pracownika do grupy urządzeń</span><span class="sxs-lookup"><span data-stu-id="d4d50-131">Assign worker to device group</span></span>
1. <span data-ttu-id="d4d50-132">Wybierz kolejno opcje **Kontrola produkcji > Ustawienia > Wykonywanie produkcji > Konfiguruj kartę zadań dla urządzeń**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-132">Go to **Production control > Setup > Manufacturing execution > Configure job card for devices**.</span></span>
2. <span data-ttu-id="d4d50-133">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-133">Select **Add**.</span></span>
3. <span data-ttu-id="d4d50-134">Na liście zaznacz żądanego pracownika.</span><span class="sxs-lookup"><span data-stu-id="d4d50-134">In the list, select the desired worker.</span></span> <span data-ttu-id="d4d50-135">W tym przykładzie wybierz **SHANNON**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-135">For this example, select **SHANNON**.</span></span>
4. <span data-ttu-id="d4d50-136">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-136">Select **OK**.</span></span>
5. <span data-ttu-id="d4d50-137">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="d4d50-137">Select **Edit**.</span></span>
6. <span data-ttu-id="d4d50-138">W polu **Jednostka produkcyjna** można ustawić domyślny filtr dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="d4d50-138">In the **Production unit** field, you can set the default filter for the worker.</span></span> <span data-ttu-id="d4d50-139">Daje to pewność, że gdy pracownik loguje się do urządzenia, wyświetlane są tylko zadania produkcyjne dla wybranej jednostki produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="d4d50-139">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span> <span data-ttu-id="d4d50-140">Wprowadź odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="d4d50-140">Enter the desired value.</span></span>
7. <span data-ttu-id="d4d50-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d4d50-141">Close the page.</span></span>

