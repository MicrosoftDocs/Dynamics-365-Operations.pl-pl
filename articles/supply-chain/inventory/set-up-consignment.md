---
title: Konfigurowanie konsygnacji
description: W tym temacie wyjaśniono sposób konfigurowania operacji konsygnacji przychodzącej dla zapasów.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 24500ff46cc77ca8fa59c0c16427d9f05f33a87e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550026"
---
# <a name="set-up-consignment"></a><span data-ttu-id="abc8b-103">Konfigurowanie konsygnacji</span><span class="sxs-lookup"><span data-stu-id="abc8b-103">Set up consignment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="abc8b-104">W tym temacie wyjaśniono sposób konfigurowania operacji konsygnacji przychodzącej dla zapasów.</span><span class="sxs-lookup"><span data-stu-id="abc8b-104">This topic explains how to configure inbound consignment inventory operations.</span></span>

<span data-ttu-id="abc8b-105">Zapasy konsygnacyjne to zapasy, których właścicielem jest dostawca, ale są one przechowywane Twojej siedzibie.</span><span class="sxs-lookup"><span data-stu-id="abc8b-105">Consignment inventory is inventory that’s owned by a vendor, but stored at your site.</span></span> <span data-ttu-id="abc8b-106">Gdy masz wszystko przygotowane do zużycia lub wykorzystania zapasów, przejmujesz ich własność.</span><span class="sxs-lookup"><span data-stu-id="abc8b-106">When you’re ready to consume or use the inventory, you take over the ownership of the inventory.</span></span> <span data-ttu-id="abc8b-107">W tym temacie opisano konfigurację niezbędną do włączenia procesów konsygnacji.</span><span class="sxs-lookup"><span data-stu-id="abc8b-107">This topic describes the setup needed to enable consignment processes.</span></span> <span data-ttu-id="abc8b-108">Aby uzyskać więcej informacji o procesach konsygnacji, zobacz [Konsygnacja](consignment.md).</span><span class="sxs-lookup"><span data-stu-id="abc8b-108">For more information about consignment processes, see [Consignment](consignment.md).</span></span>

## <a name="inventory-owners"></a><span data-ttu-id="abc8b-109">Właściciele zapasów</span><span class="sxs-lookup"><span data-stu-id="abc8b-109">Inventory owners</span></span>
<span data-ttu-id="abc8b-110">Aby zarejestrować fizyczne przychodzące zapasy konsygnacyjne, należy zdefiniować właściciela będącego dostawcą.</span><span class="sxs-lookup"><span data-stu-id="abc8b-110">In order to record physical inbound consignment inventory, you need to define a vendor owner.</span></span> <span data-ttu-id="abc8b-111">Służy do tego strona **Właściciel zapasów**.</span><span class="sxs-lookup"><span data-stu-id="abc8b-111">This is done on the **Inventory owner** page.</span></span> <span data-ttu-id="abc8b-112">Wybranie opcji **Konto dostawcy** spowoduje wygenerowanie wartości domyślnych dla pól **Nazwa** i **Właściciel**.</span><span class="sxs-lookup"><span data-stu-id="abc8b-112">When you select a **Vendor account** this generates default values for the **Name** and **Owner** fields.</span></span> <span data-ttu-id="abc8b-113">Wartość w polu **Właściciel** będzie widoczna dla dostawcy, więc warto ją zmienić, jeśli nazwy kont dostawców przechowywane w firmowych systemach są trudne do rozpoznania przez osoby zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="abc8b-113">The value in the **Owner** field will be visible to the vendor, so you might want to change it if your vendor account names aren’t easy for external people to recognize.</span></span> <span data-ttu-id="abc8b-114">Istnieje możliwość edytowania pola **Właściciel**, ale tylko do momentu zapisania rekordu **Właściciel zapasów**.</span><span class="sxs-lookup"><span data-stu-id="abc8b-114">It’s possible to edit the **Owner** field, but only up to the point when you save the **Inventory owner** record.</span></span> <span data-ttu-id="abc8b-115">W polu **Nazwa** jest wprowadzana nazwa strony, z którą jest skojarzone konto dostawcy, i nie można jej zmienić.</span><span class="sxs-lookup"><span data-stu-id="abc8b-115">The **Name** field is populated with the name of the party that the vendor account is associated with, and this cannot be changed.</span></span>

<span data-ttu-id="abc8b-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span><span class="sxs-lookup"><span data-stu-id="abc8b-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span></span>

## <a name="tracking-dimension-group"></a><span data-ttu-id="abc8b-117">Grupa wymiarów śledzenia</span><span class="sxs-lookup"><span data-stu-id="abc8b-117">Tracking dimension group</span></span>
<span data-ttu-id="abc8b-118">Towary, które mają być używane w procesach konsygnacji, muszą być powiązane z **grupą wymiarów śledzenia**, która w wymiarze **Właściciel** ma ustawioną wartość **Aktywny**.</span><span class="sxs-lookup"><span data-stu-id="abc8b-118">Items that are going to be used in consignment processes must be associated with a **Tracking dimension group** where the **Owner** dimension is set to **Active**.</span></span> <span data-ttu-id="abc8b-119">Wymiar Właściciel zawsze ma zaznaczone opcje **Magazyn fizyczny** i **Magazyn finansowy**.</span><span class="sxs-lookup"><span data-stu-id="abc8b-119">The Owner dimension always has the **Physical inventory** and **Financial inventory** options selected.</span></span> <span data-ttu-id="abc8b-120">Opcja **Plan zapotrzebowania wg wymiaru** nigdy nie jest zaznaczona.</span><span class="sxs-lookup"><span data-stu-id="abc8b-120">The **Coverage plan by dimension** is never selected.</span></span>

<span data-ttu-id="abc8b-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span><span class="sxs-lookup"><span data-stu-id="abc8b-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span></span>

## <a name="inventory-ownership-change-journal"></a><span data-ttu-id="abc8b-122">Arkusz zmian własności zapasów</span><span class="sxs-lookup"><span data-stu-id="abc8b-122">Inventory ownership change journal</span></span>
<span data-ttu-id="abc8b-123">Arkusz **Zmiana własności zapasów** służy do rejestrowania przeniesienia własności zapasów konsygnacyjnych z dostawcy na firmę, która je zużyje.</span><span class="sxs-lookup"><span data-stu-id="abc8b-123">The **Inventory ownership change** journal is used to record the transfer of ownership of consignment inventory from the vendor to the legal entity that’s consuming it.</span></span> <span data-ttu-id="abc8b-124">Podobnie jak każdy arkusz magazynowy, musi być identyfikowany za pomocą nazwy arkusza magazynowego.</span><span class="sxs-lookup"><span data-stu-id="abc8b-124">Like any inventory journal, it must be identified with an Inventory journal name.</span></span> <span data-ttu-id="abc8b-125">Nazwy te są tworzone na stronie **Nazwy arkuszy magazynowych**, a w ustawieniu **Typ arkusza** trzeba zaznaczyć wartość **Zmiana własności**.</span><span class="sxs-lookup"><span data-stu-id="abc8b-125">These names are created on the **Inventory journal names** page, and the **Journal type** must be set to **Ownership change**.</span></span>

<span data-ttu-id="abc8b-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span><span class="sxs-lookup"><span data-stu-id="abc8b-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span></span>

## <a name="vendor-collaboration-in-consignment-processes"></a><span data-ttu-id="abc8b-127">Współpraca z dostawcami w procesach konsygnacji</span><span class="sxs-lookup"><span data-stu-id="abc8b-127">Vendor collaboration in consignment processes</span></span>
<span data-ttu-id="abc8b-128">Jeśli dostawcy używają interfejsu współpracy z dostawcami, mogą w nim monitorować zużywanie zapasów w oddziale Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="abc8b-128">If your vendors are using the vendor collaboration interface, they can use this to monitor the consumption of inventory at your site.</span></span> <span data-ttu-id="abc8b-129">Aby uzyskać więcej informacji o konfigurowaniu dostawców do używania portalu współpracy z dostawcami, zobacz [Konfiguracja zabezpieczeń dla użytkowników portalu współpracy z dostawcami](../procurement/configure-security-vendor-portal-users.md).</span><span class="sxs-lookup"><span data-stu-id="abc8b-129">For more information about setting up vendors to use vendor collaboration, see [Configuration of security for vendor collaboration users](../procurement/configure-security-vendor-portal-users.md).</span></span>
