---
title: Tworzenie kanałów biura obsługi i definiowanie atrybutów kanału
description: Ta procedura zawiera instruktaż tworzenia nowego kanału sprzedaży detalicznej i definiowania jego atrybutów.
author: mugunthanm
manager: AnnBe
ms.date: 05/22/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ef094535214ecf4c65f95c36a93455446d7e388
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "346762"
---
# <a name="create-call-center-channels-and-define-channel-attributes"></a><span data-ttu-id="f9537-103">Tworzenie kanałów biura obsługi i definiowanie atrybutów kanału</span><span class="sxs-lookup"><span data-stu-id="f9537-103">Create call center channels and define channel attributes</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="f9537-104">Ta procedura zawiera instruktaż tworzenia nowego kanału sprzedaży detalicznej i definiowania jego atrybutów.</span><span class="sxs-lookup"><span data-stu-id="f9537-104">This procedure walks through creating a new retail channel and defining channel attributes.</span></span> <span data-ttu-id="f9537-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="f9537-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="f9537-106">Ta procedura jest przeznaczona dla pracownika IT w sklepie.</span><span class="sxs-lookup"><span data-stu-id="f9537-106">This procedure is intended for the Retail IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="f9537-107">Tworzenie nowego sklepu</span><span class="sxs-lookup"><span data-stu-id="f9537-107">Create new store</span></span>
1. <span data-ttu-id="f9537-108">Przejdź do wszystkie obszary robocze > Wdrożenie kanału.</span><span class="sxs-lookup"><span data-stu-id="f9537-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="f9537-109">Kliknij opcję Nowy kanał.</span><span class="sxs-lookup"><span data-stu-id="f9537-109">Click New channel.</span></span>
3. <span data-ttu-id="f9537-110">Kliknij opcję Sklep.</span><span class="sxs-lookup"><span data-stu-id="f9537-110">Click Store.</span></span>
4. <span data-ttu-id="f9537-111">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f9537-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="f9537-112">W polu Numer sklepu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f9537-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="f9537-113">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="f9537-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f9537-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="f9537-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="f9537-116">W polu Strefa czasowa sklepu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="f9537-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="f9537-117">W polu Profil kanału kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="f9537-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="f9537-119">W polu Język kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="f9537-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f9537-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="f9537-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="f9537-122">W polu Grupa podatków kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="f9537-123">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f9537-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="f9537-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="f9537-125">W polu Książka adresowa odbiorców kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f9537-126">Zaznacz książkę adresową służącą do łączenia klientów z tym sklepem.</span><span class="sxs-lookup"><span data-stu-id="f9537-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="f9537-127">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f9537-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="f9537-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="f9537-129">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="f9537-129">Click Select.</span></span>
22. <span data-ttu-id="f9537-130">W polu Książka adresowa pracowników kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f9537-131">Zaznacz książkę adresową służącą do łączenia kasjerów z tym kanałem.</span><span class="sxs-lookup"><span data-stu-id="f9537-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="f9537-132">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f9537-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="f9537-133">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="f9537-134">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="f9537-134">Click Select.</span></span>
26. <span data-ttu-id="f9537-135">W polu Domyślny odbiorca kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="f9537-136">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="f9537-137">Rozwiń lub zwiń sekcję Układ ekranu.</span><span class="sxs-lookup"><span data-stu-id="f9537-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="f9537-138">W polu Identyfikator układu ekranu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f9537-139">Wybierz domyślny układ ekranu aplikacji punktu sprzedaży dla danego sklepu.</span><span class="sxs-lookup"><span data-stu-id="f9537-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="f9537-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f9537-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="f9537-141">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="f9537-142">W okienku akcji kliknij pozycję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="f9537-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="f9537-143">Kliknij opcję Atrybuty kanału.</span><span class="sxs-lookup"><span data-stu-id="f9537-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="f9537-144">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f9537-144">Click New.</span></span>
35. <span data-ttu-id="f9537-145">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="f9537-146">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f9537-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="f9537-147">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="f9537-148">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f9537-148">Click Save.</span></span>
39. <span data-ttu-id="f9537-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f9537-149">Close the page.</span></span>
40. <span data-ttu-id="f9537-150">W okienku akcji kliknij pozycję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="f9537-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="f9537-151">Kliknij opcję Metody płatności.</span><span class="sxs-lookup"><span data-stu-id="f9537-151">Click Payment methods.</span></span>
42. <span data-ttu-id="f9537-152">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f9537-152">Click New.</span></span>
43. <span data-ttu-id="f9537-153">W polu Metoda płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="f9537-154">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="f9537-155">Rozwiń lub zwiń sekcję Księgowanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="f9537-156">W polu Numer konta podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="f9537-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="f9537-157">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f9537-157">Click Save.</span></span>
48. <span data-ttu-id="f9537-158">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f9537-158">Close the page.</span></span>
49. <span data-ttu-id="f9537-159">W okienku akcji kliknij pozycję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="f9537-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="f9537-160">Kliknij opcję Deklaracja gotówki.</span><span class="sxs-lookup"><span data-stu-id="f9537-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="f9537-161">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f9537-161">Click New.</span></span>
52. <span data-ttu-id="f9537-162">W polu Kwota w walucie transakcji wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f9537-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="f9537-163">W polu Waluta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="f9537-164">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f9537-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="f9537-165">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="f9537-166">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f9537-166">Click Save.</span></span>
57. <span data-ttu-id="f9537-167">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f9537-167">Close the page.</span></span>
58. <span data-ttu-id="f9537-168">W okienku akcji kliknij pozycję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="f9537-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="f9537-169">Kliknij opcję Przypisanie grupy lokalizatora sklepów.</span><span class="sxs-lookup"><span data-stu-id="f9537-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="f9537-170">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f9537-170">Click New.</span></span>
61. <span data-ttu-id="f9537-171">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f9537-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="f9537-172">W polu Grupa lokalizatora kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f9537-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="f9537-173">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f9537-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="f9537-174">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f9537-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="f9537-175">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f9537-175">Click Save.</span></span>
66. <span data-ttu-id="f9537-176">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f9537-176">Close the page.</span></span>

