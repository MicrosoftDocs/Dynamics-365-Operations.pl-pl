---
title: Profile oceny
description: W tym temacie opisano sposób konfigurowania danych do profili stawek.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f754a8b86b0d369af03812a831d77a8a6fa8154
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233518"
---
# <a name="rating-profiles"></a><span data-ttu-id="4a130-103">Profile oceny</span><span class="sxs-lookup"><span data-stu-id="4a130-103">Rating profiles</span></span>

<span data-ttu-id="4a130-104">Profil stawki przypomina umowę logistyczną (ale nie umowę prawną).</span><span class="sxs-lookup"><span data-stu-id="4a130-104">A rating profile resembles a logistics contract (but not a legal contract).</span></span> <span data-ttu-id="4a130-105">Jest on używany do określenia taryf transportowych dla ładunków.</span><span class="sxs-lookup"><span data-stu-id="4a130-105">It's used to determine transportation tariffs for loads.</span></span> 

<span data-ttu-id="4a130-106">Każdy profil stawek jest unikatowy dla przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="4a130-106">Each rating profile is unique to a shipping carrier.</span></span> <span data-ttu-id="4a130-107">W profilu możesz powiązać przewoźnika z główną stawką.</span><span class="sxs-lookup"><span data-stu-id="4a130-107">In the profile, you associate the shipping carrier with a rate master.</span></span> <span data-ttu-id="4a130-108">Główne stawki określają przypisania stawek podstawowych i stawki podstawowe.</span><span class="sxs-lookup"><span data-stu-id="4a130-108">The rate master defines the rate base assignment and the rate base.</span></span> <span data-ttu-id="4a130-109">Stawka podstawowa określa stawkę przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="4a130-109">The rate base determines the rate of the carrier.</span></span>

<span data-ttu-id="4a130-110">Możesz skonfigurować profil stawek, korzystając z ogólnej strony, która przedstawia przegląd wszystkich istniejących profili stawek.</span><span class="sxs-lookup"><span data-stu-id="4a130-110">You can set up a rating profile by using a generic page that shows an overview of all existing rating profiles.</span></span> <span data-ttu-id="4a130-111">Alternatywnie możesz skonfigurować profil stawek bezpośrednio od przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="4a130-111">Alternatively, you can set up a rating profile directly from the shipping carrier.</span></span> <span data-ttu-id="4a130-112">W obu przypadkach informacje skonfigurowane dla profilu stawek są takie same.</span><span class="sxs-lookup"><span data-stu-id="4a130-112">In both cases, the information that you set up for the rating profile is the same.</span></span>

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a><span data-ttu-id="4a130-113">Tworzenie lub edytowanie profilu oceny na stronie profile stawek</span><span class="sxs-lookup"><span data-stu-id="4a130-113">Create or edit a rating profile on the Rating profiles page</span></span>

<span data-ttu-id="4a130-114">Na stronie **Profile stawek** można przejrzeć wszystkie dostępne profile stawek.</span><span class="sxs-lookup"><span data-stu-id="4a130-114">On the **Rating profiles** page, you can review all available rating profiles.</span></span> <span data-ttu-id="4a130-115">Można również edytować istniejące profile i tworzyć nowe.</span><span class="sxs-lookup"><span data-stu-id="4a130-115">You can also edit existing profiles and create new profiles.</span></span>

1. <span data-ttu-id="4a130-116">Przejdź do **Zarządzanie transportem \> Konfiguracja \> Stawki \> Profil stawek**.</span><span class="sxs-lookup"><span data-stu-id="4a130-116">Go to **Transportation management \> Setup \> Rating \> Rating profile**.</span></span>
1. <span data-ttu-id="4a130-117">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy profil stawek do siatki, lub wybierz **Edytuj**, aby edytować istniejący profil.</span><span class="sxs-lookup"><span data-stu-id="4a130-117">On the Action Pane, select **New** to add a new rating profile to the grid, or select **Edit** to edit an existing profile.</span></span>
1. <span data-ttu-id="4a130-118">W wierszu nowego lub istniejącego profilu stawek należy określić następujące pola:</span><span class="sxs-lookup"><span data-stu-id="4a130-118">In the row for the new or existing rating profile, set the following fields:</span></span>

    - <span data-ttu-id="4a130-119">**Profil stawek** – Wprowadź unikatowy identyfikator (ID) profilu stawek.</span><span class="sxs-lookup"><span data-stu-id="4a130-119">**Rating profile** – Enter a unique identifier (ID) for the rating profile.</span></span>
    - <span data-ttu-id="4a130-120">**Nazwa** — umożliwia wprowadzenie opisowej nazwy profilu stawek.</span><span class="sxs-lookup"><span data-stu-id="4a130-120">**Name** – Enter a descriptive name for the rating profile.</span></span>
    - <span data-ttu-id="4a130-121">**Przewoźnik** — umożliwia wybór firmy przewozowej.</span><span class="sxs-lookup"><span data-stu-id="4a130-121">**Shipping carrier** – Select a shipping carrier.</span></span> <span data-ttu-id="4a130-122">Profil stawek, który konfigurujesz, będzie również widoczny na stronie **Przewoźnicy** dla wybranego przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="4a130-122">The rating profile that you're setting up will also be shown on the **Shipping carriers** page for the selected carrier.</span></span>
    - <span data-ttu-id="4a130-123">**Oddział** i **Magazyn** — umożliwia wybór oddziału i magazynu.</span><span class="sxs-lookup"><span data-stu-id="4a130-123">**Site** and **Warehouse** – Select a site and warehouse.</span></span>
    - <span data-ttu-id="4a130-124">**Aparat wyznaczania stawki** — umożliwia wybór aparatu stawek dla profilu stawek.</span><span class="sxs-lookup"><span data-stu-id="4a130-124">**Rate engine** – Select the rate engine for the rating profile.</span></span>
    - <span data-ttu-id="4a130-125">**Główne stawki** — umożliwia wybór głównych stawek dla profilu stawek.</span><span class="sxs-lookup"><span data-stu-id="4a130-125">**Rate master** – Select the rate master for the rating profile.</span></span> <span data-ttu-id="4a130-126">Głównej stawki możesz użyć do określania typu stawki podstawowej i stawki podstawowej.</span><span class="sxs-lookup"><span data-stu-id="4a130-126">You can use the rate master to define a rate base type and a rate base.</span></span> <span data-ttu-id="4a130-127">Aby uzyskać więcej informacji, zobacz [Ustawianie danych głównych stawki](set-up-rate-masters.md).</span><span class="sxs-lookup"><span data-stu-id="4a130-127">For more information, see [Set up rate masters](set-up-rate-masters.md).</span></span>
    - <span data-ttu-id="4a130-128">**Aparat czasu tranzytu** — umożliwia wybór aparatu czasu tranzytu dla profilu stawek.</span><span class="sxs-lookup"><span data-stu-id="4a130-128">**Transit time engine** – Select the transit time engine for the rating profile.</span></span>
    - <span data-ttu-id="4a130-129">**Indeks paliwowy przewoźnika** – Wybierz indeks paliwa przewoźnika dla profilu stawek.</span><span class="sxs-lookup"><span data-stu-id="4a130-129">**Carrier fuel index** – Select the carrier fuel index for the rating profile.</span></span>
    - <span data-ttu-id="4a130-130">**Data i godzina rozpoczęcia wejścia w życie** oraz **Data i godzina zakończenia obowiązywania** — umożliwia zdefiniowanie okresu, w którym profil stawek powinien być aktywny.</span><span class="sxs-lookup"><span data-stu-id="4a130-130">**Effect start date and time** and **Effective end date and time** – Define the period when the rating profile should be active.</span></span>

1. <span data-ttu-id="4a130-131">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4a130-131">On the Action Pane, select **Save**.</span></span>

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a><span data-ttu-id="4a130-132">Tworzenie profilu stawek bezpośrednio na stronie Przewoźnicy</span><span class="sxs-lookup"><span data-stu-id="4a130-132">Create a rating profile directly on the Shipping carriers page</span></span>

1. <span data-ttu-id="4a130-133">Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Firmy przewozowe**.</span><span class="sxs-lookup"><span data-stu-id="4a130-133">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="4a130-134">Wybierz przewoźnika z listy.</span><span class="sxs-lookup"><span data-stu-id="4a130-134">Select a shipping carrier in the list.</span></span>
1. <span data-ttu-id="4a130-135">Na skróconej karcie **Profile stawek** kliknij opcję **Nowy**, aby utworzyć profil oceny.</span><span class="sxs-lookup"><span data-stu-id="4a130-135">On the **Rating profiles** FastTab, select **New** to create a rating profile.</span></span>
1. <span data-ttu-id="4a130-136">Umożliwia ustawienie pól dla nowego profilu stawek.</span><span class="sxs-lookup"><span data-stu-id="4a130-136">Set the fields for the new rating profile.</span></span> <span data-ttu-id="4a130-137">Te pola odpowiadają polom na stronie **Profile stawek** w sposób opisany w poprzedniej sekcji tego tematu.</span><span class="sxs-lookup"><span data-stu-id="4a130-137">These fields correspond to the fields on the **Rating profiles** page, as described in previous section of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="4a130-138">Profile utworzone na stronie **Przewoźnicy** są również wyświetlane na stronie **Profile ocen**.</span><span class="sxs-lookup"><span data-stu-id="4a130-138">Profiles that are created on the **Shipping carriers** page are also shown on the **Rating profiles** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]