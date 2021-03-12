---
title: Wymagania wstępne konfiguracji kanałów
description: W tym temacie przedstawiono omówienie wymagań wstępnych dotyczących konfiguracji kanałów w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0705efac4659f96ebca1c67f6f0ab8d23c99d81e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997707"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="d9159-103">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="d9159-103">Channel setup prerequisites</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d9159-104">W tym temacie przedstawiono omówienie wymagań wstępnych dotyczących konfiguracji kanału w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d9159-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d9159-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="d9159-105">Overview</span></span>

<span data-ttu-id="d9159-106">Aby można było utworzyć kanał Dynamics 365 Commerce, należy wykonać kilka wymaganych wstępnie zadań.</span><span class="sxs-lookup"><span data-stu-id="d9159-106">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="d9159-107">Poniższe listy wstępnie wymaganych zadań uporządkowane według typów kanałów.</span><span class="sxs-lookup"><span data-stu-id="d9159-107">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="d9159-108">Nadal trwa tworzenie dokumentacji, a łącza zostaną zaktualizowane po opublikowaniu nowej zawartości.</span><span class="sxs-lookup"><span data-stu-id="d9159-108">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="d9159-109">Inicjalizacja</span><span class="sxs-lookup"><span data-stu-id="d9159-109">Initialization</span></span>

- [<span data-ttu-id="d9159-110">Inicjowanie danych początkowych</span><span class="sxs-lookup"><span data-stu-id="d9159-110">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="d9159-111">Globalne wymagania wstępne dla wszystkich typów kanałów</span><span class="sxs-lookup"><span data-stu-id="d9159-111">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="d9159-112">Definiowanie i konfigurowanie struktury firmy</span><span class="sxs-lookup"><span data-stu-id="d9159-112">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="d9159-113">Konfigurowanie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="d9159-113">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="d9159-114">Ustawianie magazynu</span><span class="sxs-lookup"><span data-stu-id="d9159-114">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="d9159-115">Konfiguracja podatku warunkowego</span><span class="sxs-lookup"><span data-stu-id="d9159-115">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="d9159-116">Konfigurowanie powiadomień pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="d9159-116">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="d9159-117">Konfigurowanie sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="d9159-117">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="d9159-118">Konfigurowanie domyślnego odbiorcy i książki adresowej</span><span class="sxs-lookup"><span data-stu-id="d9159-118">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="d9159-119">Wymagania wstępne kanału Retail</span><span class="sxs-lookup"><span data-stu-id="d9159-119">Retail channel prerequisites</span></span>

- [<span data-ttu-id="d9159-120">Kody informacji i grupy kodów informacji</span><span class="sxs-lookup"><span data-stu-id="d9159-120">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="d9159-121">Konfigurowanie profilu funkcji sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d9159-121">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="d9159-122">Konfigurowanie książki adresowej pracowników</span><span class="sxs-lookup"><span data-stu-id="d9159-122">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="d9159-123">Konfigurowanie układu ekranu</span><span class="sxs-lookup"><span data-stu-id="d9159-123">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="d9159-124">Konfigurowanie stacji sprzętowej</span><span class="sxs-lookup"><span data-stu-id="d9159-124">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="d9159-125">Wymagania wstępne kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="d9159-125">Call Center channel prerequisites</span></span>

- <span data-ttu-id="d9159-126">Parametry biura obsługi</span><span class="sxs-lookup"><span data-stu-id="d9159-126">Call center parameters</span></span>
- [<span data-ttu-id="d9159-127">Zamówienie biura obsługi i metody płatności zwrotnych</span><span class="sxs-lookup"><span data-stu-id="d9159-127">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="d9159-128">Metody dostawy i opłat w biurze obsługi</span><span class="sxs-lookup"><span data-stu-id="d9159-128">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="d9159-129">Wymagania wstępne dotyczące kanału online</span><span class="sxs-lookup"><span data-stu-id="d9159-129">Online channel prerequisites</span></span>

- [<span data-ttu-id="d9159-130">Tworzenie profilu funkcji online</span><span class="sxs-lookup"><span data-stu-id="d9159-130">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="d9159-131">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d9159-131">Additional resources</span></span>

[<span data-ttu-id="d9159-132">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="d9159-132">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="d9159-133">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="d9159-133">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="d9159-134">Konfigurowanie hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="d9159-134">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="d9159-135">Tworzenie firm</span><span class="sxs-lookup"><span data-stu-id="d9159-135">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="d9159-136">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d9159-136">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="d9159-137">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="d9159-137">Set up an online channel</span></span>](channel-setup-online.md)
