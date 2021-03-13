---
title: Automatyczna aktualizacja liczników składników majątku
description: W tym temacie opisano automatyczną aktualizację liczników składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d3e8619439545cf3ea42f84a6dd7ee6ffdf1026e
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021937"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="eaa2c-103">Automatyczna aktualizacja liczników zasobów</span><span class="sxs-lookup"><span data-stu-id="eaa2c-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eaa2c-104">Aby uzyskać informacje dotyczące ręcznej rejestracji liczników składników majątku, zobacz [Ręczna aktualizacja liczników składnika majątku](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="eaa2c-104">For information about manual registration of asset counters, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span> <span data-ttu-id="eaa2c-105">Aby uzyskać informacje na temat sposobu konfigurowania liczników składnika majątku, zobacz [Liczniki](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="eaa2c-105">For information on how to set up asset counters, see [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="eaa2c-106">Wartości licznika mogą być także automatycznie aktualizowane z poziomu rejestracji produkcji na podstawie godzin produkcji lub ilości produkcji (czyli wytwarzanej ilości).</span><span class="sxs-lookup"><span data-stu-id="eaa2c-106">Counter values can also be automatically updated from production registrations, based on the production hours or production quantity (that is, the quantity that is produced).</span></span> <span data-ttu-id="eaa2c-107">Ta aktualizacja jest przeprowadzana na stronie **Aktualizowanie liczników składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-107">This update is done on the **Update asset counters** page.</span></span> <span data-ttu-id="eaa2c-108">Można zaktualizować jeden lub kilka składników majątku, ustawiając jeden parametr **Od dnia**.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-108">You can update one or several assets by setting one parameter, **From date**.</span></span> <span data-ttu-id="eaa2c-109">Ten parametr służy do określania daty rozpoczęcia rejestracji produkcji (godzin produkcji lub ilości produkcji).</span><span class="sxs-lookup"><span data-stu-id="eaa2c-109">This parameter specifies the start date for production registrations (production hours or production quantities).</span></span> <span data-ttu-id="eaa2c-110">Mówiąc inaczej, określa on datę, od której powinny być aktualizowane wartości liczników.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-110">In other words, it specifies the date that counter values should be updated from.</span></span>

<span data-ttu-id="eaa2c-111">Wszystkie składniki majątku, które są związane z zasobem *i* mają liczniki składników majątku skonfigurowane do aktualizacji na podstawie godzin produkcji lub ilości produkcji, zostaną uwzględnione w aktualizacji automatycznej.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-111">All assets that are related to a resource, *and* that have asset counters that are set up to be updated based on the production hours or production quantity, will be included in an automatic update.</span></span> <span data-ttu-id="eaa2c-112">Zostaną utworzone nowe wartości liczników.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-112">New counter values will be created.</span></span>

<span data-ttu-id="eaa2c-113">W przypadku liczników opartych na ilości produkcji licznik uwzględnia ilość dobrych i ilość wadliwych towarów, które są rejestrowane.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-113">For counters that are based on the production quantity, the count includes both the good quantity and the error quantity that are registered.</span></span> <span data-ttu-id="eaa2c-114">Jeśli jednostka używana do rejestrowania ilości produkcji różni się od jednostki używanej w liczniku, ilość jest konwertowana tak, aby odpowiadała jednostce licznika.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-114">If the unit that is used for production quantity registration differs from the unit that is used for the counter, the quantity is converted so that it corresponds to the counter unit.</span></span>

<span data-ttu-id="eaa2c-115">Jak wspomniano powyżej, liczniki automatyczne mogą być aktualizowane na podstawie rejestracji produkcji.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-115">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="eaa2c-116">Dlatego składnik majątku, dla którego mają być automatycznie aktualizowane liczniki, musi być powiązany z zasobem (maszyną).</span><span class="sxs-lookup"><span data-stu-id="eaa2c-116">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="eaa2c-117">Jeśli w zasobie zostały zarejestrowane wyprodukowane ilości lub godziny produkcji, można zaktualizować powiązane liczniki składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-117">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="eaa2c-118">Wybierz pozycję **Zarządzanie składnikami majątku** > **Okresowe** > **Składniki majątku** > **Aktualizuj liczniki składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-118">Select **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="eaa2c-119">W polu **Od dnia** wybierz datę początkową automatycznej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-119">In the **From date** field, select the start date of the automatic update.</span></span>

    >[!NOTE]
    ><span data-ttu-id="eaa2c-120">Datą w tym polu jest datą „pracy w toku” od **Transakcje marszruty** (**Kontrola produkcji** > **Zapytania i raporty** > **Produkcja** > **Transakcje marszruty** > **Data fizycznej transakcji** pole).</span><span class="sxs-lookup"><span data-stu-id="eaa2c-120">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="eaa2c-121">Na skróconej karcie **Rekordy do uwzględnienia** można wybrać określone składniki majątku, typy składników majątku lub zasoby do automatycznej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-121">On the **Records to include** FastTab, you can select specific assets, asset types, or resources for the automatic update.</span></span> <span data-ttu-id="eaa2c-122">Wybierz pozycję **Filtr** i wybierz odpowiednie opcje.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-122">Select **Filter**, and make the relevant selections.</span></span>

4. <span data-ttu-id="eaa2c-123">Na skróconej karcie **uruchom w tle** w razie potrzeby możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-123">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

    <span data-ttu-id="eaa2c-124">Na poniższej ilustracji przedstawiono przykład okna dialogowego **Aktualizowanie liczników składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-124">The illustration below shows an example of the **Update asset counters** dialog.</span></span>

    ![Rysunek 1](media/12-work-orders.png)

5. <span data-ttu-id="eaa2c-126">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-126">Select **OK**.</span></span> 

<span data-ttu-id="eaa2c-127">Po zakończeniu aktualizacji licznika składników majątku można przejrzeć rejestracje liczników powiązane z danym składnikiem majątku na stronie **Liczniki składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-127">After the automatic asset counter update is done, you can view the counter registrations that are related to the asset on the **Asset counters** page.</span></span> <span data-ttu-id="eaa2c-128">Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**, wybierz składnik majątku, a następnie w okienku akcji na karcie **Składnik majątku**, w grupie **Zapobiegawcze** wybierz pozycję **Liczniki**.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-128">Select **Asset management** > **Common** > **Assets** > **All assets**, select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span>

<span data-ttu-id="eaa2c-129">Na stronie **Zagregowana wartość składnika majątku** można uzyskać przegląd najnowszej rejestracji przeprowadzonej dla wszystkich typów licznika we wszystkich składnikach majątku.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-129">On the **Asset aggregated value** page, you can get an overview of the latest registration that have been made on all counter types on all assets.</span></span> <span data-ttu-id="eaa2c-130">Wybierz pozycję **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Zagregowana wartość składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-130">Select **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="eaa2c-131">Ta strona przypomina stronę **Liczniki składników majątku**, ale nie można dodawać ani edytować rejestracji.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-131">This page resembles the **Asset counters** page, but you can't add or edit registrations.</span></span> <span data-ttu-id="eaa2c-132">Służy ona tylko do przeglądu.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-132">It's for overview only.</span></span>

<span data-ttu-id="eaa2c-133">Na poniższej ilustracji przedstawiono przykład strony **Zagregowana wartość składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-133">The illustration below shows an example of the **Asset aggregated value** page.</span></span>

![Rysunek 2](media/13-work-orders.png)

<span data-ttu-id="eaa2c-135">Należy uwzględnić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="eaa2c-135">Note the following points:</span></span>

- <span data-ttu-id="eaa2c-136">W dalszym ciągu możesz tworzyć ręczne rejestracje wartości licznika dla typów licznika, które są automatycznie aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-136">You can still create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="eaa2c-137">Aby uzyskać więcej informacji, zobacz [Ręczna aktualizacja liczników składnika majątku](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="eaa2c-137">For more information, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span>

- <span data-ttu-id="eaa2c-138">Możesz konfigurować liczniki powiązane z innym licznikiem.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-138">You can set up counters that are related to another counter.</span></span> <span data-ttu-id="eaa2c-139">W tym przypadku jeśli licznik jest aktualizowany, powiązane liczniki są automatycznie aktualizowane w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="eaa2c-139">In this case, when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="eaa2c-140">Aby uzyskać więcej informacji na temat sposobu konfigurowania powiązanych liczników, zobacz [Liczniki](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="eaa2c-140">For more information about how to set up related counters, see [Counters](../setup-for-objects/counters.md).</span></span>

