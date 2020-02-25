---
title: Zarejestrowanie pracownika w systemie stałych wynagrodzeń
description: Menedżer ds. wynagrodzenia i świadczeń może przypisywać pracowników do planów stałych wynagrodzeń w celu zarządzania ich wynagrodzeniami podstawowymi.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 843db6bc133382a701d4b25b164794e57df152c7
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010278"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="87c46-103">Zarejestrowanie pracownika w systemie stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="87c46-103">Enroll an employee in a fixed compensation plan</span></span>

<span data-ttu-id="87c46-104">Menedżer ds. wynagrodzenia i świadczeń może przypisywać pracowników do planów stałych wynagrodzeń w celu zarządzania ich wynagrodzeniami podstawowymi.</span><span class="sxs-lookup"><span data-stu-id="87c46-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="87c46-105">Ta procedura zakłada, że plan stałych wynagrodzeń został utworzony i jest aktywny oraz skonfigurowano w nim reguły uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="87c46-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="87c46-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="87c46-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="87c46-107">Aby rozpocząć procedurę, wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Pracownicy > Wynagrodzenie > Plan stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="87c46-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="87c46-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="87c46-108">Click New.</span></span>
2. <span data-ttu-id="87c46-109">W polu Akcja wybierz akcję związaną ze stałym wynagrodzeniem typu Zatrudnienie/ponowne zatrudnienie, aby opisać zmianę wynagrodzenia pracownika.</span><span class="sxs-lookup"><span data-stu-id="87c46-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="87c46-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="87c46-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="87c46-111">W polu Stanowisko kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="87c46-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="87c46-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="87c46-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="87c46-113">Poziom wyświetlany z poziomu wynagrodzeń dla zadania na tym stanowisku.</span><span class="sxs-lookup"><span data-stu-id="87c46-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="87c46-114">Aby wynagrodzenie można było przypisać do pracownika, poziom musi zostać ustawiony w zadaniu.</span><span class="sxs-lookup"><span data-stu-id="87c46-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="87c46-115">W polu Plan wybierz plan stałych wynagrodzeń dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="87c46-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="87c46-116">Wyszukiwanie planu zostanie wyfiltrowane w celu wyświetlenia tylko planów, do których pracownik jest uprawniony zgodnie z regułami uprawnień.</span><span class="sxs-lookup"><span data-stu-id="87c46-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="87c46-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="87c46-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="87c46-118">Wartości pól Data obowiązywania i Data wygaśnięcia dla wynagrodzenia domyślnie pochodzą z daty rozpoczęcia i zakończenia przypisania stanowiska pracownika.</span><span class="sxs-lookup"><span data-stu-id="87c46-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="87c46-119">W razie potrzeby można zmienić te daty.</span><span class="sxs-lookup"><span data-stu-id="87c46-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="87c46-120">Jeśli plan stałych wynagrodzeń jest planem typu Krok, zaznacz krok zawierający stawkę płacy odpowiednią dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="87c46-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="87c46-121">Jeśli plan stałych wynagrodzeń jest planem typu Pasmo lub Kategoria, wprowadź stawkę płacy pracownika.</span><span class="sxs-lookup"><span data-stu-id="87c46-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="87c46-122">Stawka płacy będzie weryfikowana względem ustawień tolerancji dla planu oraz minimalnego i maksymalnego punktu odniesienia w poziomie wynagrodzeń dla zadania.</span><span class="sxs-lookup"><span data-stu-id="87c46-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="87c46-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87c46-123">Click OK.</span></span>

