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
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2439d1912b3ca013f4a524f3354923d2a3f76ca
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221288"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="f332e-103">Tworzenie grup uprawnień dla punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="f332e-103">Create POS permission groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f332e-104">W tym temacie wyjaśniono, jak utworzyć grupę uprawnień dla punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f332e-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="f332e-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="f332e-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="f332e-106">To zadanie jest przeznaczone dla roli Kierownik ds. operacyjnych handlu.</span><span class="sxs-lookup"><span data-stu-id="f332e-106">This task is intended for the Commerce operations manager role.</span></span>

1. <span data-ttu-id="f332e-107">W okienku nawigacji przejdź do **Moduły > Retail i Commerce > Pracownicy etatpwi > Grupy uprawnień**.</span><span class="sxs-lookup"><span data-stu-id="f332e-107">In the navigation pane, go to **Modules > Retail and Commerce > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="f332e-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f332e-108">Select **New**.</span></span>
3. <span data-ttu-id="f332e-109">W polu **Identyfikator grupy uprawnień dla punktu sprzedaży** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f332e-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="f332e-110">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f332e-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="f332e-111">W polu **Wyświetlanie wpisów zegara** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f332e-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="f332e-112">Teraz można włączyć lub wyłączyć różne uprawnienia w grupie uprawnień dla punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f332e-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="f332e-113">Dla niektórych uprawnień można ustawić wartość, która będzie używana do oceny, czy użytkownik punktu sprzedaży może wykonać czynność.</span><span class="sxs-lookup"><span data-stu-id="f332e-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="f332e-114">W tym podręczniku po zadaniach włączono kilka uprawnień, które można przyznać kasjerowi.</span><span class="sxs-lookup"><span data-stu-id="f332e-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="f332e-115">W polu **Zezwalaj na tworzenie zamówienia** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f332e-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="f332e-116">W polu **Zezwalaj na edytowanie zamówienia** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f332e-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="f332e-117">W polu **Zezwalaj na pobieranie zamówienia** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f332e-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="f332e-118">W polu **Dopuszczaj zmianę hasła** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f332e-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="f332e-119">W polu **Zezwalaj na ukrycie raportu podczas zamknięcia kasy** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f332e-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="f332e-120">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f332e-120">Select **Save**.</span></span> <span data-ttu-id="f332e-121">Gdy zmiany zostaną zapisane, należy uruchomić harmonogram dystrybucji do pracowników, aby wysłać zmiany do kanałów handlu.</span><span class="sxs-lookup"><span data-stu-id="f332e-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to commerce channels.</span></span> 
12. <span data-ttu-id="f332e-122">W okienku nawigacji przejdź do **Moduły > Zasoby ludzkie > Zadania > Zadania**.</span><span class="sxs-lookup"><span data-stu-id="f332e-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="f332e-123">Następnie przypiszemy grupę uprawnień dla punktu sprzedaży do zadania.</span><span class="sxs-lookup"><span data-stu-id="f332e-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="f332e-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f332e-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="f332e-125">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="f332e-125">Select **Edit**.</span></span>
15. <span data-ttu-id="f332e-126">Rozwiń sekcję **Klasyfikacja zadania** .</span><span class="sxs-lookup"><span data-stu-id="f332e-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="f332e-127">W polu Grupa uprawnień dla punktu sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f332e-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="f332e-128">Wszyscy pracownicy na Stanowiskach dla tego zadania będą używali ustawień tej grupy uprawnień punktu sprzedaży, chyba że odnośne uprawnienia zostały zastąpione pracownikom na poziomie ich Stanowisk.</span><span class="sxs-lookup"><span data-stu-id="f332e-128">All Workers in Positions for this Job will use this POS permission group's settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="f332e-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f332e-129">Select **Save**.</span></span> <span data-ttu-id="f332e-130">Gdy zmiany zostaną zapisane, należy uruchomić harmonogram dystrybucji do pracowników, aby wysłać zmiany do kanałów.</span><span class="sxs-lookup"><span data-stu-id="f332e-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to channels.</span></span>  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]