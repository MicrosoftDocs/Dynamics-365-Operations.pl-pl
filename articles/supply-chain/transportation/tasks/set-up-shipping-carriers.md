---
title: Konfigurowanie firm przewozowych
description: W tej procedurze opisano sposób konfigurowania firmy przewozowej i definiowania szczegółów, takich jak usługi, tryb wysyłki, metoda płatności za transport, ograniczenia transportu i stawka kosztów wysyłki.
author: ShylaThompson
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1ec19288f01ceb0bb3021cf549af1c38746785c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233590"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="cb39c-103">Konfigurowanie firm przewozowych</span><span class="sxs-lookup"><span data-stu-id="cb39c-103">Set up shipping carriers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cb39c-104">W tej procedurze opisano sposób konfigurowania firmy przewozowej i definiowania szczegółów, takich jak usługi, tryb wysyłki, metoda płatności za transport, ograniczenia transportu i stawka kosztów wysyłki.</span><span class="sxs-lookup"><span data-stu-id="cb39c-104">This topic shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="cb39c-105">Koordynator transportu może następnie przypisać firmę przewozową do ładunku przychodzącego i wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="cb39c-106">Tworzenie nowej firmy przewozowej</span><span class="sxs-lookup"><span data-stu-id="cb39c-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="cb39c-107">Wybierz kolejno opcje **Okienko Nawigacji > Moduły > Zarządzanie transportem > Ustawienia > Przewoźnicy > Firmy przewozowe**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-107">Go to **Navigation pane > Modules > Transportation management > Setup > Carriers > Shipping carriers**.</span></span>
2. <span data-ttu-id="cb39c-108">Wybierz pozycję **Nowy** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="cb39c-108">Select **New** on the Action Pane.</span></span>
3. <span data-ttu-id="cb39c-109">W polu **Firma przewozowa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cb39c-109">In the **Shipping carrier** field, type a value.</span></span>
4. <span data-ttu-id="cb39c-110">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cb39c-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="cb39c-111">W polu **Tryb** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-111">In the **Mode** field, select an option from the drop-down menu.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="cb39c-112">Wprowadzanie ogólnych informacji o firmie przewozowej</span><span class="sxs-lookup"><span data-stu-id="cb39c-112">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="cb39c-113">Przełącz rozwinięcie sekcji **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-113">Toggle the expansion of the **Overview** section.</span></span>
2. <span data-ttu-id="cb39c-114">Zaznacz lub usuń zaznaczenie pola wyboru **Aktywuj firmę przewozową**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-114">Check or uncheck the **Activate shipping carrier** checkbox.</span></span>
3. <span data-ttu-id="cb39c-115">W polu **Konto dostawcy** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-115">In the **Vendor account** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="cb39c-116">Wybierz konto dostawcy, do którego chcesz przypisać firmę przewozową.</span><span class="sxs-lookup"><span data-stu-id="cb39c-116">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="cb39c-117">W polu **Typ metody płatności** za transport wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="cb39c-117">In the **Transportation tender type** field, select an option.</span></span> <span data-ttu-id="cb39c-118">Wybierz opcję **Ręczne**, aby użyć strony Metoda płatności za transport, lub opcję **EDI**, aby zaktualizować metodę płatności na elektroniczną wymianę danych (EDI).</span><span class="sxs-lookup"><span data-stu-id="cb39c-118">Select **Manual** to use the Transportation Tender page, or select **EDI** to update the tender by using Electronic Data Interchange (EDI).</span></span>  
5. <span data-ttu-id="cb39c-119">Zaznacz lub usuń zaznaczenie pola wyboru **Aktywuj oceny przewoźników**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-119">Check or uncheck the **Activate carrier rating** checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="cb39c-120">Tworzenie niezbędnych usług dla firmy przewozowej</span><span class="sxs-lookup"><span data-stu-id="cb39c-120">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="cb39c-121">Przełącz rozwinięcie sekcji **Usługi**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-121">Toggle the expansion of the **Services** section.</span></span>
2. <span data-ttu-id="cb39c-122">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-122">Select **New**.</span></span>
3. <span data-ttu-id="cb39c-123">W polu **Usługa przewozowa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cb39c-123">In the **Carrier service** field, type a value.</span></span>
4. <span data-ttu-id="cb39c-124">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cb39c-124">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="cb39c-125">W polu **Metoda transportu** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-125">In the **Transportation method** field, select an option from the drop-down menu.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="cb39c-126">Konfigurowanie adresu przewoźnika (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="cb39c-126">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="cb39c-127">Przełącz rozwinięcie sekcji **Adresy**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-127">Toggle the expansion of the **Addresses** section.</span></span>
2. <span data-ttu-id="cb39c-128">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-128">Select **New**.</span></span>
3. <span data-ttu-id="cb39c-129">W polu **Nazwa lub opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cb39c-129">In the **Name or description** field, type a value.</span></span>
4. <span data-ttu-id="cb39c-130">W polu **Kraj/region** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-130">In the **Country/region** field, select an option from the drop-down menu.</span></span>
5. <span data-ttu-id="cb39c-131">W polu **Kod pocztowy** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-131">In the **ZIP/postal code** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="cb39c-132">W polu **Ulica** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cb39c-132">In the **Street** field, type a value.</span></span>
7. <span data-ttu-id="cb39c-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-133">Select **OK**.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="cb39c-134">Konfigurowanie profilu wyznaczania stawek dla przewoźnika</span><span class="sxs-lookup"><span data-stu-id="cb39c-134">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="cb39c-135">Przełącz rozwinięcie sekcji **Profile oceny**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-135">Toggle the expansion of the **Rating profiles** section.</span></span>
2. <span data-ttu-id="cb39c-136">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-136">Select **New**.</span></span>
3. <span data-ttu-id="cb39c-137">W polu **Profil oceny** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cb39c-137">In the **Rating profile** field, type a value.</span></span>
4. <span data-ttu-id="cb39c-138">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cb39c-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="cb39c-139">W polu **Oddział** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-139">In the **Site** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="cb39c-140">W polu **Magazyn** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-140">In the **Warehouse** field, select an option from the drop-down menu.</span></span>
7. <span data-ttu-id="cb39c-141">W polu **Aparat wyznaczania stawki** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-141">In the **Rate engine** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="cb39c-142">Wybierz aparat wyznaczania stawki zgodny z umową zawartą z przewoźnikiem.</span><span class="sxs-lookup"><span data-stu-id="cb39c-142">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
8. <span data-ttu-id="cb39c-143">W polu **Główna stawka** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-143">In the **Rate master** field, select an option from the drop-down menu.</span></span>
9. <span data-ttu-id="cb39c-144">W polu **Aparat czasu tranzytu** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="cb39c-144">In the **Transit time engine** field, select an option from the drop-down menu.</span></span>
10. <span data-ttu-id="cb39c-145">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="cb39c-145">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]