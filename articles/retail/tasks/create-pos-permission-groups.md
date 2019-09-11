---
title: Tworzenie grup uprawnień dla punktu sprzedaży
description: W tym temacie wyjaśniono, jak utworzyć grupę uprawnień dla punktu sprzedaży.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e6782c60aa659523775cc6c4eb1694430a4bf4f
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914827"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="620b9-103">Tworzenie grup uprawnień dla punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="620b9-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="620b9-104">W tym temacie wyjaśniono, jak utworzyć grupę uprawnień dla punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="620b9-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="620b9-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="620b9-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="620b9-106">To zadanie jest przeznaczone dla roli Kierownik ds. operacyjnych sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="620b9-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="620b9-107">W okienku nawigacji przejdź do **Moduły > Sprzedaż detaliczna > Pracownicy etatpwi > Grupy uprawnień**.</span><span class="sxs-lookup"><span data-stu-id="620b9-107">In the navigation pane, go to **Modules > Retail > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="620b9-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="620b9-108">Select **New**.</span></span>
3. <span data-ttu-id="620b9-109">W polu **Identyfikator grupy uprawnień dla punktu sprzedaży** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="620b9-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="620b9-110">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="620b9-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="620b9-111">W polu **Wyświetlanie wpisów zegara** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="620b9-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="620b9-112">Teraz można włączyć lub wyłączyć różne uprawnienia w grupie uprawnień dla punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="620b9-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="620b9-113">Dla niektórych uprawnień można ustawić wartość, która będzie używana do oceny, czy użytkownik punktu sprzedaży może wykonać czynność.</span><span class="sxs-lookup"><span data-stu-id="620b9-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="620b9-114">W tym podręczniku po zadaniach włączono kilka uprawnień, które można przyznać kasjerowi.</span><span class="sxs-lookup"><span data-stu-id="620b9-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="620b9-115">W polu **Zezwalaj na tworzenie zamówienia** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="620b9-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="620b9-116">W polu **Zezwalaj na edytowanie zamówienia** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="620b9-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="620b9-117">W polu **Zezwalaj na pobieranie zamówienia** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="620b9-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="620b9-118">W polu **Dopuszczaj zmianę hasła** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="620b9-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="620b9-119">W polu **Zezwalaj na ukrycie raportu podczas zamknięcia kasy** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="620b9-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="620b9-120">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="620b9-120">Select **Save**.</span></span> <span data-ttu-id="620b9-121">Gdy zmiany zostaną zapisane, należy uruchomić harmonogram dystrybucji do pracowników, aby wysłać zmiany do kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="620b9-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span> 
12. <span data-ttu-id="620b9-122">W okienku nawigacji przejdź do **Moduły > Zasoby ludzkie > Zadania > Zadania**.</span><span class="sxs-lookup"><span data-stu-id="620b9-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="620b9-123">Następnie przypiszemy grupę uprawnień dla punktu sprzedaży do zadania.</span><span class="sxs-lookup"><span data-stu-id="620b9-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="620b9-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="620b9-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="620b9-125">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="620b9-125">Select **Edit**.</span></span>
15. <span data-ttu-id="620b9-126">Rozwiń sekcję **Klasyfikacja zadania** .</span><span class="sxs-lookup"><span data-stu-id="620b9-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="620b9-127">W polu Grupa uprawnień dla punktu sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="620b9-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="620b9-128">Wszyscy pracownicy na stanowiskach dla tego zadania będą używali ustawień tej grupy uprawnień dla punktu sprzedaży, chyba że odnośne uprawnienia zostały zastąpione pracownikom na poziomie ich stanowisk.</span><span class="sxs-lookup"><span data-stu-id="620b9-128">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="620b9-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="620b9-129">Select **Save**.</span></span> <span data-ttu-id="620b9-130">Gdy zmiany zostaną zapisane, należy uruchomić harmonogram dystrybucji do pracowników, aby wysłać zmiany do kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="620b9-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  

