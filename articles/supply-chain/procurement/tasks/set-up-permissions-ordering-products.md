---
title: Tworzenie uprawnień do zamawiania produktów w imieniu innej osoby
description: W tej procedurze pokazano, jak przyznać pracownikom uprawnienia do przygotowywania zapotrzebowań na zakup w imieniu innych pracowników.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eea1577972879cc24a2295a0c5a8d7d3de5f4520
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837981"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a><span data-ttu-id="e6443-103">Tworzenie uprawnień do zamawiania produktów w imieniu innej osoby</span><span class="sxs-lookup"><span data-stu-id="e6443-103">Set up permissions for ordering products on behalf of someone else</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e6443-104">W tej procedurze pokazano, jak przyznać pracownikom uprawnienia do przygotowywania zapotrzebowań na zakup w imieniu innych pracowników.</span><span class="sxs-lookup"><span data-stu-id="e6443-104">This procedure shows how to grant workers permission to prepare purchase requisitions on behalf of other workers.</span></span> <span data-ttu-id="e6443-105">Innymi słowy „wystawca” zapotrzebowania na zakup może utworzyć zapotrzebowanie dla innej osoby, zwanej „zleceniodawcą”.</span><span class="sxs-lookup"><span data-stu-id="e6443-105">In other words, a purchase requisition “preparer” can create a requisition for another “requester.”</span></span> <span data-ttu-id="e6443-106">W procedurze również pokazano, jak przyznać pracownikowi uprawnienie do zamawiania towarów i usług w innych firmach i jednostkach operacyjnych.</span><span class="sxs-lookup"><span data-stu-id="e6443-106">The procedure also shows how to grant a worker permission to order items and services in different legal entities or operating units.</span></span> <span data-ttu-id="e6443-107">Zazwyczaj te zadania wykonuje kierownik ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="e6443-107">Typically, these tasks are performed by a purchasing manager.</span></span> <span data-ttu-id="e6443-108">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="e6443-108">You can use this procedure either on data for the USMF demo company or on your own data.</span></span>


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a><span data-ttu-id="e6443-109">Przyznawanie uprawnienia do wprowadzania zapotrzebowań na zakup w imieniu innego pracownika</span><span class="sxs-lookup"><span data-stu-id="e6443-109">Grant permission to enter purchase requisitions on behalf of another worker</span></span>
1. <span data-ttu-id="e6443-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zasady > Uprawnienia zapotrzebowania na zakup.</span><span class="sxs-lookup"><span data-stu-id="e6443-110">Go to Procurement and sourcing > Setup > Policies > Purchase requisition permissions.</span></span>
    * <span data-ttu-id="e6443-111">Upewnij się, że w polu Bieżący widok zaznaczono wartość Wg wystawcy.</span><span class="sxs-lookup"><span data-stu-id="e6443-111">Make sure that the Current view field is set to By preparer.</span></span>  <span data-ttu-id="e6443-112">Na liście w lewym okienku są wyświetlane osoby, którym można przyznać uprawnienie do przygotowywania zapotrzebowań w imieniu innych osób.</span><span class="sxs-lookup"><span data-stu-id="e6443-112">The list in the left pane shows the people who can be granted permission to prepare requisitions on behalf of other people.</span></span>  
2. <span data-ttu-id="e6443-113">Wybierz osobę, której chcesz przyznać uprawnienia (wystawcę).</span><span class="sxs-lookup"><span data-stu-id="e6443-113">Select the person to grant permission to (the preparer).</span></span>
3. <span data-ttu-id="e6443-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="e6443-114">Click Add.</span></span>
4. <span data-ttu-id="e6443-115">Znajdź i zaznacz osobę, którą chcesz dodać jako zleceniodawcę.</span><span class="sxs-lookup"><span data-stu-id="e6443-115">Find and select the person to add as a requester.</span></span>
    * <span data-ttu-id="e6443-116">Zleceniodawca jest osobą, w imieniu której wystawca może tworzyć zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="e6443-116">The requester is the person that the preparer can create requisitions on behalf of.</span></span>  
    * <span data-ttu-id="e6443-117">W polu Autoryzacja zaznacz opcję Określony, jeśli wystawca powinien mieć możliwość tworzenia zapotrzebowań na zakup w imieniu wybranego pracownika.</span><span class="sxs-lookup"><span data-stu-id="e6443-117">In the Authorization field, select Specific if the preparer should be able to create purchase requisitions on behalf of the selected worker.</span></span> <span data-ttu-id="e6443-118">Wybierz opcję Raportowanie, jeżeli wystawca powinien mieć również możliwość tworzenia zapotrzebowań na zakup w imieniu wszystkich pracowników podlegających wybranemu pracownikowi.</span><span class="sxs-lookup"><span data-stu-id="e6443-118">Select Reporting if the preparer should also be able to create purchase requisitions on behalf of all workers who report to that worker.</span></span>  
5. <span data-ttu-id="e6443-119">W polu Data wprowadzenia wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="e6443-119">In the Effective field, enter a date.</span></span>
6. <span data-ttu-id="e6443-120">W polu Data wygaśnięcia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="e6443-120">In the Expiration field, enter a date.</span></span>

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a><span data-ttu-id="e6443-121">Wyświetlanie wystawców mających uprawnienie do tworzenia zapotrzebowań na zakup dla wybranego pracownika</span><span class="sxs-lookup"><span data-stu-id="e6443-121">View preparers who have permission to create purchase requisitions for a selected worker</span></span>
1. <span data-ttu-id="e6443-122">W polu Bieżący widok wybierz wartość „Wg zleceniodawcy”.</span><span class="sxs-lookup"><span data-stu-id="e6443-122">In the Current view field, select 'By requester'.</span></span>
    * <span data-ttu-id="e6443-123">Ten widok zawiera listę wystawców, którym przyznano uprawnienie do tworzenia zapotrzebowań na zakup w imieniu wybranego pracownika.</span><span class="sxs-lookup"><span data-stu-id="e6443-123">This view shows a list of preparers who have been granted permission to create purchase requisitions on behalf of a selected worker.</span></span>  
2. <span data-ttu-id="e6443-124">Za pomocą szybkiego filtru znajdź pracownika, który właśnie został dodany jako zleceniodawca.</span><span class="sxs-lookup"><span data-stu-id="e6443-124">Use the Quick Filter to find the worker that you just added as the requester.</span></span>
3. <span data-ttu-id="e6443-125">Zaznacz zleceniodawcę.</span><span class="sxs-lookup"><span data-stu-id="e6443-125">Select the requester.</span></span>
    * <span data-ttu-id="e6443-126">Na liście wystawców znajdują się osoby uprawnione do zamawiania towarów w imieniu zleceniodawcy wybranego w lewym okienku.</span><span class="sxs-lookup"><span data-stu-id="e6443-126">The Preparer list shows the people who have permission to order items on behalf of the requester who is selected in the left pane.</span></span>   <span data-ttu-id="e6443-127">W tym miejscu można dodawać kolejnych wystawców.</span><span class="sxs-lookup"><span data-stu-id="e6443-127">You can add additional preparers here.</span></span>   <span data-ttu-id="e6443-128">Ten widok umożliwia również przyznanie uprawnień zleceniodawcy pozwalających tworzyć zapotrzebowania w firmach i jednostkach operacyjnych, które nie są podstawowymi firmami ani jednostkami operacyjnymi danej osoby.</span><span class="sxs-lookup"><span data-stu-id="e6443-128">This view also lets you grant the requester permission to create requisitions in legal entities and operating units that aren't that person's primary legal entity or operating unit.</span></span>  

