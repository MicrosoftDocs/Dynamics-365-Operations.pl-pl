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
ms.openlocfilehash: 270f751e860e56a03e20df720c088f275d0298e7
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477931"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="98acc-103">Wymagania wstępne dotyczące konfiguracji kanału</span><span class="sxs-lookup"><span data-stu-id="98acc-103">Channel setup prerequisites</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="98acc-104">W tym temacie przedstawiono omówienie wymagań wstępnych dotyczących konfiguracji kanałów w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="98acc-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="98acc-105">Aby można było utworzyć kanał Dynamics 365 Commerce, należy wykonać kilka wymaganych wstępnie zadań.</span><span class="sxs-lookup"><span data-stu-id="98acc-105">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="98acc-106">Poniższe listy wstępnie wymaganych zadań uporządkowane według typów kanałów.</span><span class="sxs-lookup"><span data-stu-id="98acc-106">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="98acc-107">Nadal trwa tworzenie dokumentacji, a łącza zostaną zaktualizowane po opublikowaniu nowej zawartości.</span><span class="sxs-lookup"><span data-stu-id="98acc-107">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="98acc-108">Inicjalizacja</span><span class="sxs-lookup"><span data-stu-id="98acc-108">Initialization</span></span>

- [<span data-ttu-id="98acc-109">Inicjowanie danych początkowych</span><span class="sxs-lookup"><span data-stu-id="98acc-109">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="98acc-110">Globalne wymagania wstępne dla wszystkich typów kanałów</span><span class="sxs-lookup"><span data-stu-id="98acc-110">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="98acc-111">Definiowanie i konfigurowanie struktury firmy</span><span class="sxs-lookup"><span data-stu-id="98acc-111">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="98acc-112">Konfigurowanie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="98acc-112">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="98acc-113">Ustawianie magazynu</span><span class="sxs-lookup"><span data-stu-id="98acc-113">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="98acc-114">Konfiguracja podatku warunkowego</span><span class="sxs-lookup"><span data-stu-id="98acc-114">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="98acc-115">Konfigurowanie powiadomień pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="98acc-115">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="98acc-116">Konfigurowanie sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="98acc-116">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="98acc-117">Konfigurowanie domyślnego odbiorcy i książki adresowej</span><span class="sxs-lookup"><span data-stu-id="98acc-117">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="98acc-118">Wymagania wstępne kanału Retail</span><span class="sxs-lookup"><span data-stu-id="98acc-118">Retail channel prerequisites</span></span>

- [<span data-ttu-id="98acc-119">Kody informacji i grupy kodów informacji</span><span class="sxs-lookup"><span data-stu-id="98acc-119">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="98acc-120">Konfigurowanie profilu funkcji sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="98acc-120">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="98acc-121">Konfigurowanie książki adresowej pracowników</span><span class="sxs-lookup"><span data-stu-id="98acc-121">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="98acc-122">Konfigurowanie układu ekranu</span><span class="sxs-lookup"><span data-stu-id="98acc-122">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="98acc-123">Konfigurowanie stacji sprzętowej</span><span class="sxs-lookup"><span data-stu-id="98acc-123">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="98acc-124">Wymagania wstępne kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="98acc-124">Call Center channel prerequisites</span></span>

- <span data-ttu-id="98acc-125">Parametry biura obsługi</span><span class="sxs-lookup"><span data-stu-id="98acc-125">Call center parameters</span></span>
- [<span data-ttu-id="98acc-126">Zamówienie biura obsługi i metody płatności zwrotnych</span><span class="sxs-lookup"><span data-stu-id="98acc-126">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="98acc-127">Metody dostawy i opłat w biurze obsługi</span><span class="sxs-lookup"><span data-stu-id="98acc-127">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="98acc-128">Wymagania wstępne dotyczące kanału online</span><span class="sxs-lookup"><span data-stu-id="98acc-128">Online channel prerequisites</span></span>

- [<span data-ttu-id="98acc-129">Tworzenie profilu funkcji online</span><span class="sxs-lookup"><span data-stu-id="98acc-129">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="98acc-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="98acc-130">Additional resources</span></span>

[<span data-ttu-id="98acc-131">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="98acc-131">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="98acc-132">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="98acc-132">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="98acc-133">Konfigurowanie hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="98acc-133">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="98acc-134">Tworzenie firm</span><span class="sxs-lookup"><span data-stu-id="98acc-134">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="98acc-135">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="98acc-135">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="98acc-136">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="98acc-136">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
