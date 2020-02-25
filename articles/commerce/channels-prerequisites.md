---
title: Wymagania wstępne konfiguracji kanałów
description: W tym temacie przedstawiono omówienie wymagań wstępnych dotyczących konfiguracji kanałów w rozwiązaniu Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: b861d90f1333c8f6e61a83602ed74e30b65f3dc1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002296"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="0b3e6-103">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="0b3e6-103">Channel setup prerequisites</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0b3e6-104">W tym temacie przedstawiono omówienie wymagań wstępnych dotyczących konfiguracji kanału w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0b3e6-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0b3e6-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="0b3e6-105">Overview</span></span>

<span data-ttu-id="0b3e6-106">Aby można było utworzyć kanał Dynamics 365 Commerce, należy wykonać kilka wymaganych wstępnie zadań.</span><span class="sxs-lookup"><span data-stu-id="0b3e6-106">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="0b3e6-107">Poniższe listy wstępnie wymaganych zadań uporządkowane według typów kanałów.</span><span class="sxs-lookup"><span data-stu-id="0b3e6-107">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="0b3e6-108">Nadal trwa tworzenie dokumentacji, a łącza zostaną zaktualizowane po opublikowaniu nowej zawartości.</span><span class="sxs-lookup"><span data-stu-id="0b3e6-108">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="0b3e6-109">Inicjalizacja</span><span class="sxs-lookup"><span data-stu-id="0b3e6-109">Initialization</span></span>

- [<span data-ttu-id="0b3e6-110">Inicjowanie danych początkowych</span><span class="sxs-lookup"><span data-stu-id="0b3e6-110">Initialize seed data</span></span>](../retail/enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="0b3e6-111">Globalne wymagania wstępne dla wszystkich typów kanałów</span><span class="sxs-lookup"><span data-stu-id="0b3e6-111">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="0b3e6-112">Definiowanie i konfigurowanie struktury firmy</span><span class="sxs-lookup"><span data-stu-id="0b3e6-112">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="0b3e6-113">Konfigurowanie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="0b3e6-113">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="0b3e6-114">Ustawianie magazynu</span><span class="sxs-lookup"><span data-stu-id="0b3e6-114">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="0b3e6-115">Konfiguracja podatku warunkowego</span><span class="sxs-lookup"><span data-stu-id="0b3e6-115">Configure sales tax</span></span>](https://docs.microsoft.com/en-us/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="0b3e6-116">Konfigurowanie powiadomień pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="0b3e6-116">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="0b3e6-117">Konfigurowanie sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="0b3e6-117">Set up number sequences</span></span>](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="0b3e6-118">Konfigurowanie domyślnego odbiorcy i książki adresowej</span><span class="sxs-lookup"><span data-stu-id="0b3e6-118">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="0b3e6-119">Wymagania wstępne kanału Retail</span><span class="sxs-lookup"><span data-stu-id="0b3e6-119">Retail channel prerequisites</span></span>

- [<span data-ttu-id="0b3e6-120">Kody informacji i grupy kodów informacji</span><span class="sxs-lookup"><span data-stu-id="0b3e6-120">Info codes and info code groups</span></span>](https://docs.microsoft.com/en-us/dynamics365/retail/info-codes-retail?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="0b3e6-121">Konfigurowanie profilu funkcji sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="0b3e6-121">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="0b3e6-122">Konfigurowanie książki adresowej pracowników</span><span class="sxs-lookup"><span data-stu-id="0b3e6-122">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="0b3e6-123">Konfigurowanie układu ekranu</span><span class="sxs-lookup"><span data-stu-id="0b3e6-123">Set up a screen layout</span></span>](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="0b3e6-124">Konfigurowanie stacji sprzętowej</span><span class="sxs-lookup"><span data-stu-id="0b3e6-124">Set up a hardware station</span></span>](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation?toc=/dynamics365/commerce/toc.json)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="0b3e6-125">Wymagania wstępne kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="0b3e6-125">Call Center channel prerequisites</span></span>

- <span data-ttu-id="0b3e6-126">Parametry biura obsługi</span><span class="sxs-lookup"><span data-stu-id="0b3e6-126">Call center parameters</span></span>
- <span data-ttu-id="0b3e6-127">Metody zwrotu biura obsługi</span><span class="sxs-lookup"><span data-stu-id="0b3e6-127">Call center refund methods</span></span>
- <span data-ttu-id="0b3e6-128">Typy wynajmu</span><span class="sxs-lookup"><span data-stu-id="0b3e6-128">Rental types</span></span>
- <span data-ttu-id="0b3e6-129">Usługi płatności</span><span class="sxs-lookup"><span data-stu-id="0b3e6-129">Payment services</span></span>
- <span data-ttu-id="0b3e6-130">Kody wstrzymania zamówień</span><span class="sxs-lookup"><span data-stu-id="0b3e6-130">Order hold codes</span></span>

## <a name="online-channel-prerequisites"></a><span data-ttu-id="0b3e6-131">Wymagania wstępne kanału online</span><span class="sxs-lookup"><span data-stu-id="0b3e6-131">Online channel prerequisites</span></span>

- [<span data-ttu-id="0b3e6-132">Tworzenie profilu funkcji online</span><span class="sxs-lookup"><span data-stu-id="0b3e6-132">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="0b3e6-133">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0b3e6-133">Additional resources</span></span>

[<span data-ttu-id="0b3e6-134">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="0b3e6-134">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="0b3e6-135">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="0b3e6-135">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="0b3e6-136">Konfigurowanie hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="0b3e6-136">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="0b3e6-137">Tworzenie firm</span><span class="sxs-lookup"><span data-stu-id="0b3e6-137">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="0b3e6-138">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="0b3e6-138">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="0b3e6-139">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="0b3e6-139">Set up an online channel</span></span>](channel-setup-online.md)
