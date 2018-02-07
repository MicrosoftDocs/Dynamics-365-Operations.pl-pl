--- 
title: "Tworzenie grup uprawnień dla punktu sprzedaży"
description: "Ta procedura pokazuje, jak utworzyć grupę uprawnień dla punktu sprzedaży."
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: bcda7c3a5c2cc97fbc6e4945e4d5f0ec42a7a478
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="c7282-103">Tworzenie grup uprawnień dla punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c7282-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="c7282-104">Ta procedura pokazuje, jak utworzyć grupę uprawnień dla punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c7282-104">This procedure will show how to create a POS permission group.</span></span> <span data-ttu-id="c7282-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="c7282-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="c7282-106">To zadanie jest przeznaczone dla roli Kierownik ds. operacyjnych sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c7282-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="c7282-107">Przejdź do okna Grupy uprawnień.</span><span class="sxs-lookup"><span data-stu-id="c7282-107">Go to Permission groups.</span></span>
2. <span data-ttu-id="c7282-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c7282-108">Click New.</span></span>
3. <span data-ttu-id="c7282-109">W polu Identyfikator grupy uprawnień dla punktu sprzedaży wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c7282-109">In the POS permission group ID field, type a value.</span></span>
4. <span data-ttu-id="c7282-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c7282-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c7282-111">W polu Wyświetlanie wpisów zegara wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="c7282-111">Select Yes in the View time clock entries field.</span></span>
    * <span data-ttu-id="c7282-112">Teraz można włączyć lub wyłączyć różne uprawnienia w grupie uprawnień dla punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c7282-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="c7282-113">Dla niektórych uprawnień można ustawić wartość, która będzie używana do oceny, czy użytkownik punktu sprzedaży może wykonać czynność.</span><span class="sxs-lookup"><span data-stu-id="c7282-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span>  <span data-ttu-id="c7282-114">W tym podręczniku po zadaniach włączono kilka uprawnień, które można przyznać kasjerowi.</span><span class="sxs-lookup"><span data-stu-id="c7282-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="c7282-115">W polu Zezwalaj na tworzenie zamówienia wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="c7282-115">Select Yes in the Allow create order field.</span></span>
7. <span data-ttu-id="c7282-116">W polu Zezwalaj na edytowanie zamówienia wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="c7282-116">Select Yes in the Allow edit order field.</span></span>
8. <span data-ttu-id="c7282-117">W polu Zezwalaj na pobieranie zamówienia wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="c7282-117">Select Yes in the Allow retrieve order field.</span></span>
9. <span data-ttu-id="c7282-118">W polu Dopuszczaj zmianę hasła wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="c7282-118">Select Yes in the Allow password change field.</span></span>
10. <span data-ttu-id="c7282-119">W polu Zezwalaj na ukrycie raportu podczas zamknięcia kasy wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="c7282-119">Select Yes in the Allow blind close field.</span></span>
11. <span data-ttu-id="c7282-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c7282-120">Click Save.</span></span>
    * <span data-ttu-id="c7282-121">Gdy zmiany zostaną zapisane, należy uruchomić harmonogram dystrybucji do pracowników, aby wysłać zmiany do kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="c7282-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  
12. <span data-ttu-id="c7282-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c7282-122">Close the page.</span></span>
13. <span data-ttu-id="c7282-123">Przejdź do okna Zadania.</span><span class="sxs-lookup"><span data-stu-id="c7282-123">Go to Jobs.</span></span>
    * <span data-ttu-id="c7282-124">Następnie przypiszemy grupę uprawnień dla punktu sprzedaży do zadania.</span><span class="sxs-lookup"><span data-stu-id="c7282-124">Next we will assign the POS permission group to a Job.</span></span>  
14. <span data-ttu-id="c7282-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c7282-125">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="c7282-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c7282-126">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="c7282-127">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="c7282-127">Click Edit.</span></span>
17. <span data-ttu-id="c7282-128">Rozwiń sekcję Klasyfikacja zadania.</span><span class="sxs-lookup"><span data-stu-id="c7282-128">Expand the Job classification section.</span></span>
18. <span data-ttu-id="c7282-129">W polu Grupa uprawnień dla punktu sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c7282-129">In the POS permission group field, enter or select a value.</span></span>
    * <span data-ttu-id="c7282-130">Wszyscy pracownicy na stanowiskach dla tego zadania będą używali ustawień tej grupy uprawnień dla punktu sprzedaży, chyba że odnośne uprawnienia zostały zastąpione pracownikom na poziomie ich stanowisk.</span><span class="sxs-lookup"><span data-stu-id="c7282-130">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
19. <span data-ttu-id="c7282-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c7282-131">Click Save.</span></span>
    * <span data-ttu-id="c7282-132">Gdy zmiany zostaną zapisane, należy uruchomić harmonogram dystrybucji do pracowników, aby wysłać zmiany do kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="c7282-132">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  


