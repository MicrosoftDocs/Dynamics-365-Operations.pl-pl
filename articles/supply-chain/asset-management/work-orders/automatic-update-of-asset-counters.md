---
title: Automatyczna aktualizacja liczników składników majątku
description: W tym temacie opisano automatyczną aktualizację liczników składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875847"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="2e707-103">Automatyczna aktualizacja liczników składników majątku</span><span class="sxs-lookup"><span data-stu-id="2e707-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="2e707-104">W poprzedniej sekcji opisano ręczną rejestrację liczników składników majątku.</span><span class="sxs-lookup"><span data-stu-id="2e707-104">In the previous section, manual registration of asset counters is described.</span></span> <span data-ttu-id="2e707-105">Konfiguracja liczników składnika majątku jest opisana w [Liczniki](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="2e707-105">Setup of asset counters is described in [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="2e707-106">Wartości licznika mogą być także automatycznie aktualizowane na podstawie rejestracji produkcji na podstawie godzin produkcji lub ilości produkcji.</span><span class="sxs-lookup"><span data-stu-id="2e707-106">Counter values can also be automatically updated from production registrations, based on production hours or production quantity.</span></span> <span data-ttu-id="2e707-107">Odbywa się to w **Aktualizuj liczniki składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="2e707-107">This is done in **Update asset counters**.</span></span> <span data-ttu-id="2e707-108">Można zaktualizować jeden lub kilka składników majątku, wstawiając jeden parametr **Od dnia**.</span><span class="sxs-lookup"><span data-stu-id="2e707-108">You can update one or several assets by inserting one parameter, **From date**.</span></span> <span data-ttu-id="2e707-109">Ten parametr określa datę początkową rejestracji produkcji (liczba godzin lub ilość wyprodukowana), czyli datę początkową, od której powinny być aktualizowane wartości liczników.</span><span class="sxs-lookup"><span data-stu-id="2e707-109">This parameter specifies the start date for production registrations (hours or quantity produced), meaning the start date from which counter values should be updated.</span></span>

<span data-ttu-id="2e707-110">Wszystkie środki trwałe, które są związane z zasobem *i* mają liczniki składnika majątku, które są skonfigurowane do aktualizacji na podstawie ilości wyprodukowanej lub godzin produkcji, zostaną uwzględnione w aktualizacji automatycznej i zostaną utworzone nowe wartości liczników.</span><span class="sxs-lookup"><span data-stu-id="2e707-110">All assets that are related to a resource *and* have asset counters, which are set up to be updated based on produced quantity or production hours, will be included in an automatic update, and new counter values will be created.</span></span>

<span data-ttu-id="2e707-111">W przypadku liczników na podstawie ilości produkcji, ilość dobrych towarów, a także zarejestrowana ilość wadliwych towarów jest uwzględniana w liczniku.</span><span class="sxs-lookup"><span data-stu-id="2e707-111">Regarding counters based on production quantity, good quantity as well as error quantity registered are included in the count.</span></span> <span data-ttu-id="2e707-112">Jeśli jednostka użyta do zarejestrowania ilości produkcji różni się od jednostki użytej w liczniku, ilość jest konwertowana na odpowiadającą jednostce licznika.</span><span class="sxs-lookup"><span data-stu-id="2e707-112">If the unit used for produced quantity registration is different from the unit used on the counter, quantity is converted to correspond with the counter unit.</span></span>

<span data-ttu-id="2e707-113">Jak wspomniano powyżej, liczniki automatyczne mogą być aktualizowane na podstawie rejestracji produkcji.</span><span class="sxs-lookup"><span data-stu-id="2e707-113">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="2e707-114">Dlatego składnik majątku, dla którego mają być automatycznie aktualizowane liczniki, musi być powiązany z zasobem (maszyną).</span><span class="sxs-lookup"><span data-stu-id="2e707-114">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="2e707-115">Poniższe opisy zawierają przegląd ustawień i przetwarzania zleceń produkcyjnych (w module **Kontrola produkcji**), które są używane jako podstawa automatycznej aktualizacji liczników składnika majątku w module **Zarządzanie składnikami majątku**.</span><span class="sxs-lookup"><span data-stu-id="2e707-115">The following descriptions provide an overview of the setup and processing of production orders (in the **Production control** module), which is used as a basis for automatic update of counters on an asset in the **Asset management** module.</span></span>

<span data-ttu-id="2e707-116">Jeśli w zasobie zostały zarejestrowane wyprodukowane ilości lub godziny produkcji, można zaktualizować powiązane liczniki składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="2e707-116">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="2e707-117">Kliknij **Zarządzanie składnikami majątku** > **Okresowe** > **Składniki majątku** > **Aktualizuj liczniki składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="2e707-117">Click **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="2e707-118">Wybierz datę początkową automatycznej aktualizacji w polu **Od dnia**.</span><span class="sxs-lookup"><span data-stu-id="2e707-118">Select the start date of the automatic update in the **From date** field.</span></span>

>[!NOTE]
><span data-ttu-id="2e707-119">Datą w tym polu jest datą „pracy w toku” od **Transakcje marszruty** (**Kontrola produkcji** > **Zapytania i raporty** > **Produkcja** > **Transakcje marszruty** > **Data fizycznej transakcji** pole).</span><span class="sxs-lookup"><span data-stu-id="2e707-119">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="2e707-120">Jeśli chcesz wybrać określone zasoby, typy składników majątku lub zasoby dla aktualizacji automatycznych, kliknij przycisk **Filtruj** na skróconej karcie **Rekordy do uwzględnienia** i dokonaj odpowiednich wyborów.</span><span class="sxs-lookup"><span data-stu-id="2e707-120">If you want to select specific assets, asset types, or resources for the automatic update, click **Filter** on the **Records to include** FastTab, and make the relevant selections.</span></span>

4. <span data-ttu-id="2e707-121">W razie potrzeby możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe na skróconej karcie **Uruchom w tle**.</span><span class="sxs-lookup"><span data-stu-id="2e707-121">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

![Rysunek 1](media/12-work-orders.png)

5. <span data-ttu-id="2e707-123">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e707-123">Click **OK**.</span></span> <span data-ttu-id="2e707-124">Po wykonaniu aktualizacji licznika składnika majątku można zobaczyć rejestracje liczników powiązanych ze składnikiem majątku w **Liczniki składnika majątku** (**Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku** > wybierz składnik majatku > przycisk **Licznik**).</span><span class="sxs-lookup"><span data-stu-id="2e707-124">When the automatic asset counter update is done, you can see the counter registrations related to the asset in **Asset counters** (**Asset management** > **Common** > **Assets** > **All assets** > select asset > **Counters** button).</span></span>

<span data-ttu-id="2e707-125">W **Sumy licznika składnika majątku** można uzyskać przegląd najnowszej rejestracji wszystkich typów licznika na wszystkich składnikach majątku.</span><span class="sxs-lookup"><span data-stu-id="2e707-125">In **Asset counter totals**, you can get an overview of the latest registration made on all counter types on all assets.</span></span> <span data-ttu-id="2e707-126">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Zagregowana wartość składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="2e707-126">Click **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="2e707-127">Widok jest bardzo podobny do **Liczniki składnika majątku**, ale nie można dodawać ani edytować rejestracji w **Zagregowana wartość składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="2e707-127">The view is very similar to **Asset counters**, but you cannot add or edit registrations in **Asset aggregated value**.</span></span> <span data-ttu-id="2e707-128">Służy tylko do przeglądu.</span><span class="sxs-lookup"><span data-stu-id="2e707-128">It is for overview only.</span></span>

![Rysunek 2](media/13-work-orders.png)


- <span data-ttu-id="2e707-130">Nadal istnieje możliwość tworzenia ręcznych rejestracji wartości licznika dla typów licznika, które są automatycznie aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="2e707-130">It is still possible to create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="2e707-131">Aby uzyskać więcej informacji, zobacz sekcję „Ręczna aktualizacja liczników składnika majątku”</span><span class="sxs-lookup"><span data-stu-id="2e707-131">Refer to the "Manual update of asset counters" section for more information.</span></span>
- <span data-ttu-id="2e707-132">Istnieje możliwość skonfigurowania liczników powiązanych z innym licznikiem, co oznacza, że po zaktualizowaniu licznika powiązane liczniki są automatycznie aktualizowane w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="2e707-132">You can set up counters related to another counter, which means that when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="2e707-133">Należy zapoznać się z tematem [Liczniki](../setup-for-objects/counters.md), aby zobaczyć konfigurację powiązanych liczników.</span><span class="sxs-lookup"><span data-stu-id="2e707-133">Refer to [Counters](../setup-for-objects/counters.md) regarding setup of related counters.</span></span>
