---
title: Omówienie kanałów
description: W tym temacie omówiono kanały w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 099ccd9f769ea5c431c1a82532d8654cbbd082b1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414901"
---
# <a name="channels-overview"></a><span data-ttu-id="437b9-103">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="437b9-103">Channels overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="437b9-104">W tym temacie omówiono kanały w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="437b9-104">This topic presents an overview of channels in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="437b9-105">Znajdują się tu informacje o zadaniach, które należy wykonać przed i po skonfigurowaniu każdego kanału.</span><span class="sxs-lookup"><span data-stu-id="437b9-105">It includes information about the tasks that you must complete both before and after you set up each channel.</span></span>

## <a name="types-of-channels"></a><span data-ttu-id="437b9-106">Typy kanałów</span><span class="sxs-lookup"><span data-stu-id="437b9-106">Types of Channels</span></span>

<span data-ttu-id="437b9-107">Dynamics 365 Commerce obsługuje trzy różne typy kanałów: sieć sprzedaży, biuro obsługi i kanały online.</span><span class="sxs-lookup"><span data-stu-id="437b9-107">Dynamics 365 Commerce supports three different channel types: retail, call center, and online channels.</span></span>

### <a name="retail-channels"></a><span data-ttu-id="437b9-108">Kanały sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="437b9-108">Retail channels</span></span>

<span data-ttu-id="437b9-109">Kanały sieć sprzedaży reprezentują standardowe sklepy.</span><span class="sxs-lookup"><span data-stu-id="437b9-109">Retail channels represent standard brick-and-mortar stores.</span></span> <span data-ttu-id="437b9-110">Każdy sklep ma własne kasy punktów sprzedaży (POS), konta przychodów i wydatków oraz personel.</span><span class="sxs-lookup"><span data-stu-id="437b9-110">Each store can have its own point of sale (POS) registers, income and expense accounts, and staff.</span></span> 

### <a name="call-center-channels"></a><span data-ttu-id="437b9-111">Kanały biura obsługi</span><span class="sxs-lookup"><span data-stu-id="437b9-111">Call center channels</span></span>

<span data-ttu-id="437b9-112">Kanały biura obsługi reprezentują kolejność biur obsługi i zarządzanie odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="437b9-112">Call center channels represent call center order and customer management.</span></span>

### <a name="online-channels"></a><span data-ttu-id="437b9-113">Kanały online</span><span class="sxs-lookup"><span data-stu-id="437b9-113">Online channels</span></span>

<span data-ttu-id="437b9-114">Kanały online reprezentują sklepy e-commerce w trybie online.</span><span class="sxs-lookup"><span data-stu-id="437b9-114">Online channels represent online e-Commerce storefronts.</span></span> <span data-ttu-id="437b9-115">Po utworzeniu kanału online witryna musi zostać utworzona przy użyciu narzędzia Kreatora witryn Microsoft Dynamics 365 Commerce lub innego rozwiązania e-commerce jednostki zewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="437b9-115">Once an online channel is created, a site must be created using the Microsoft Dynamics 365 Commerce Site Builder tool or other third-party e-Commerce solution.</span></span>

## <a name="channel-setup-basics"></a><span data-ttu-id="437b9-116">Podstawy ustawień kanału</span><span class="sxs-lookup"><span data-stu-id="437b9-116">Channel setup basics</span></span>

<span data-ttu-id="437b9-117">Konfiguracja kanału jest wykonywana w narzędziu Commerce.</span><span class="sxs-lookup"><span data-stu-id="437b9-117">Channel set up is performed in the Commerce tool.</span></span> <span data-ttu-id="437b9-118">Każdy kanał może mieć własne metody płatności, grupy cenowe, hierarchie produktów, asortymenty i zestawy produktów.</span><span class="sxs-lookup"><span data-stu-id="437b9-118">Each channel can have its own payment methods, price groups, product hierarchies, assortments, and set of products.</span></span> <span data-ttu-id="437b9-119">Po utworzeniu kanału, można przypisać produkty, które mają trafić do sklepu i je sprzedawać.</span><span class="sxs-lookup"><span data-stu-id="437b9-119">After you create a channel, you assign the products that you want it to carry and sell.</span></span> <span data-ttu-id="437b9-120">Każdy typ kanału ma unikatowy zbiór funkcji, które mogą wymagać skonfigurowania.</span><span class="sxs-lookup"><span data-stu-id="437b9-120">Each channel type has a unique set of features that may need to be configured.</span></span> <span data-ttu-id="437b9-121">Na przykład kanał sprzedaży detalicznej potrzebuje przypisanych pracowników, kas i odbiorców.</span><span class="sxs-lookup"><span data-stu-id="437b9-121">For example, a retail channel needs assigned employees, registers, and customers.</span></span> <span data-ttu-id="437b9-122">Po utworzeniu nowego kanału należy go przypisać do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="437b9-122">Once a new channel is created, it needs to be assigned to an organization hierarchy.</span></span>

## <a name="channel-setup-prerequisites"></a><span data-ttu-id="437b9-123">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="437b9-123">Channel setup prerequisites</span></span>

<span data-ttu-id="437b9-124">Aby można było skonfigurować kanał, należy wykonać pewne wymagane zadania wstępne na podstawie typu kanału.</span><span class="sxs-lookup"><span data-stu-id="437b9-124">Before you can set up a channel, you must complete some prerequisite tasks based on the channel type.</span></span> <span data-ttu-id="437b9-125">Aby uzyskać więcej informacji, zajrzyj do [Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="437b9-125">For more information, see [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="set-up-a-channel"></a><span data-ttu-id="437b9-126">Konfigurowanie kanału</span><span class="sxs-lookup"><span data-stu-id="437b9-126">Set up a channel</span></span>

<span data-ttu-id="437b9-127">Po wykonaniu wymaganych zadań wstepnych, aby uzyskać więcej instrukcji konfiguracyjnych, należy skorzystać z następujących łączy:</span><span class="sxs-lookup"><span data-stu-id="437b9-127">After you complete the prerequisite tasks, for further setup instructions, use the following links.</span></span>

- [<span data-ttu-id="437b9-128">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="437b9-128">Set up a retail channel</span></span>](channel-setup-retail.md)
- [<span data-ttu-id="437b9-129">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="437b9-129">Set up a call center channel</span></span>](channel-setup-callcenter.md)
- [<span data-ttu-id="437b9-130">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="437b9-130">Set up an online channel</span></span>](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a><span data-ttu-id="437b9-131">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="437b9-131">Additional resources</span></span>

[<span data-ttu-id="437b9-132">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="437b9-132">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="437b9-133">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="437b9-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="437b9-134">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="437b9-134">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="437b9-135">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="437b9-135">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="437b9-136">Konfigurowanie hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="437b9-136">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)
