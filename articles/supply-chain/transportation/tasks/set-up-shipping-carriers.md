---
title: Konfigurowanie firm przewozowych
description: W tej procedurze opisano sposób konfigurowania firmy przewozowej i definiowania szczegółów, takich jak usługi, tryb wysyłki, metoda płatności za transport, ograniczenia transportu i stawka kosztów wysyłki.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
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
ms.openlocfilehash: 6c5ac13d17c97f20ee79e7faf57c570f02158424
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569109"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="2bead-103">Konfigurowanie firm przewozowych</span><span class="sxs-lookup"><span data-stu-id="2bead-103">Set up shipping carriers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2bead-104">W tej procedurze opisano sposób konfigurowania firmy przewozowej i definiowania szczegółów, takich jak usługi, tryb wysyłki, metoda płatności za transport, ograniczenia transportu i stawka kosztów wysyłki.</span><span class="sxs-lookup"><span data-stu-id="2bead-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="2bead-105">Koordynator transportu może następnie przypisać firmę przewozową do ładunku przychodzącego i wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="2bead-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="2bead-106">Tworzenie nowej firmy przewozowej</span><span class="sxs-lookup"><span data-stu-id="2bead-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="2bead-107">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Przewoźnicy > Firmy przewozowe.</span><span class="sxs-lookup"><span data-stu-id="2bead-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="2bead-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2bead-108">Click New.</span></span>
3. <span data-ttu-id="2bead-109">W polu Firma przewozowa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bead-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="2bead-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bead-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2bead-111">W polu Tryb kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="2bead-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bead-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="2bead-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="2bead-114">Wprowadzanie ogólnych informacji o firmie przewozowej</span><span class="sxs-lookup"><span data-stu-id="2bead-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="2bead-115">Przełącz rozwinięcie sekcji Przegląd.</span><span class="sxs-lookup"><span data-stu-id="2bead-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="2bead-116">Zaznacz lub usuń zaznaczenie pola wyboru Aktywuj firmę przewozową.</span><span class="sxs-lookup"><span data-stu-id="2bead-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="2bead-117">W polu Dostawca kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2bead-118">Wybierz konto dostawcy, do którego chcesz przypisać firmę przewozową.</span><span class="sxs-lookup"><span data-stu-id="2bead-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="2bead-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bead-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2bead-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2bead-121">W polu Typ metody płatności za transport wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="2bead-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="2bead-122">Wybierz opcję Ręczne, aby użyć strony Metoda płatności za transport, lub opcję EDI, aby zaktualizować metodę płatności na elektroniczną wymianę danych (EDI).</span><span class="sxs-lookup"><span data-stu-id="2bead-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="2bead-123">Zaznacz lub usuń zaznaczenie pola wyboru Aktywuj oceny przewoźników.</span><span class="sxs-lookup"><span data-stu-id="2bead-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="2bead-124">Tworzenie niezbędnych usług dla firmy przewozowej</span><span class="sxs-lookup"><span data-stu-id="2bead-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="2bead-125">Przełącz rozwinięcie sekcji Usługi.</span><span class="sxs-lookup"><span data-stu-id="2bead-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="2bead-126">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2bead-126">Click New.</span></span>
3. <span data-ttu-id="2bead-127">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2bead-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="2bead-128">W polu Usługa przewozowa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bead-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="2bead-129">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bead-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="2bead-130">W polu Metoda transportu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="2bead-131">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bead-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="2bead-132">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="2bead-133">Konfigurowanie adresu przewoźnika (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="2bead-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="2bead-134">Przełącz rozwinięcie sekcji Adresy.</span><span class="sxs-lookup"><span data-stu-id="2bead-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="2bead-135">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2bead-135">Click New.</span></span>
3. <span data-ttu-id="2bead-136">W polu Nazwa lub opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bead-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="2bead-137">W polu Kraj/region kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2bead-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2bead-139">W polu Kod pocztowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="2bead-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bead-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="2bead-141">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2bead-142">W polu Ulica wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bead-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="2bead-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2bead-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="2bead-144">Konfigurowanie profilu wyznaczania stawek dla przewoźnika</span><span class="sxs-lookup"><span data-stu-id="2bead-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="2bead-145">Przełącz rozwinięcie sekcji Profile oceny.</span><span class="sxs-lookup"><span data-stu-id="2bead-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="2bead-146">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2bead-146">Click New.</span></span>
3. <span data-ttu-id="2bead-147">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2bead-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="2bead-148">W polu Profil oceny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bead-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="2bead-149">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2bead-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="2bead-150">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="2bead-151">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bead-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="2bead-152">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2bead-153">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="2bead-154">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bead-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="2bead-155">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="2bead-156">W polu Aparat wyznaczania stawki kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2bead-157">Wybierz aparat wyznaczania stawki zgodny z umową zawartą z przewoźnikiem.</span><span class="sxs-lookup"><span data-stu-id="2bead-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="2bead-158">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bead-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="2bead-159">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="2bead-160">W polu Główna stawka kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="2bead-161">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2bead-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="2bead-162">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="2bead-163">W polu Aparat czasu tranzytu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2bead-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="2bead-164">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2bead-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="2bead-165">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2bead-165">Click Save.</span></span>

