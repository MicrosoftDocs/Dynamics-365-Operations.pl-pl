---
title: Tworzenie profilu funkcji online
description: W tym temacie opisano sposób tworzenia profilu funkcji online w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: be78b92858979b8bb009a4699eff96379ef7cef3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791109"
---
# <a name="create-an-online-functionality-profile"></a><span data-ttu-id="a3342-103">Tworzenie profilu funkcji online</span><span class="sxs-lookup"><span data-stu-id="a3342-103">Create an online functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a3342-104">W tym temacie przedstawiono omówienie konfigurowania profilu funkcji online dla rozwiązania Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3342-104">This topic presents an overview of setting up an online functionality profile for Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a3342-105">Profil funkcji online umożliwia używanie różnych ustawień dla kanałów online.</span><span class="sxs-lookup"><span data-stu-id="a3342-105">The online functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="a3342-106">Każdy kanał online musi określać profil funkcji online.</span><span class="sxs-lookup"><span data-stu-id="a3342-106">Each online channel must specify an online functionality profile.</span></span>

## <a name="create-an-online-functionality-profile"></a><span data-ttu-id="a3342-107">Tworzenie profilu funkcji online</span><span class="sxs-lookup"><span data-stu-id="a3342-107">Create an online functionality profile</span></span>

<span data-ttu-id="a3342-108">Poniższa procedura wyjaśnia, jak utworzyć profil funkcji online z poziomu aplikacji Centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3342-108">The following procedure explains how to create an online functionality profile from within Commerce Headquarters app.</span></span>

1. <span data-ttu-id="a3342-109">W okienku nawigacji przejdź do ustawień **Moduły \> Ustawienia kanału \> Ustawienia sklepu online \> Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="a3342-109">In the navigation pane, go to **Modules \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="a3342-110">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a3342-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a3342-111">W polu **Profil** wprowadź identyfikator profilu.</span><span class="sxs-lookup"><span data-stu-id="a3342-111">In the **Profile** field, enter an ID for the profile.</span></span>
1. <span data-ttu-id="a3342-112">W polu **opis** wprowadź wartość („profil Adventure Works” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="a3342-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="a3342-113">W sekcji **funkcje** zmodyfikuj odpowiednio **koszyk**, **odbiorcy detaliczni** lub ustawienia **realizacji transakcji**.</span><span class="sxs-lookup"><span data-stu-id="a3342-113">In the **Functions** section, modify the **CART**, **RETAIL CUSTOMERS**, or **CHECKOUT** settings, as needed.</span></span>
1. <span data-ttu-id="a3342-114">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a3342-114">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a3342-115">Poniższy obraz przedstawia przykładowy profil funkcji online.</span><span class="sxs-lookup"><span data-stu-id="a3342-115">The following image shows an example online functionality profile.</span></span>
  
![Przekład profilu funkcji online](media/online-functionality-profile.png)

## <a name="functions"></a><span data-ttu-id="a3342-117">Funkcje</span><span class="sxs-lookup"><span data-stu-id="a3342-117">Functions</span></span>

- <span data-ttu-id="a3342-118">**Zagregowane produkty**: po włączeniu tej funkcji zezwala się koszykowi na aktualizację ilości w przypadku, gdy ten sam towar jest dodawany wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="a3342-118">**Aggregate products**: When enabled, this function allows the cart to update quantity when the same item is added multiple times.</span></span>
- <span data-ttu-id="a3342-119">**Zezwalaj na realizację transakcji bez płatności**: Jeśli to pole jest włączone, ta funkcja obsługuje scenariusz, gdy towary dodawane do koszyka mają cenę 0,00 USD.</span><span class="sxs-lookup"><span data-stu-id="a3342-119">**Allow checkout with no payments**: When enabled, this function handles the scenario when items added to cart have a price $0.00.</span></span>
- <span data-ttu-id="a3342-120">**Utwórz odbiorcę w trybie asynchronicznym**: jest to ustawienie starsze w odniesieniu do kanałów handlu elektronicznego innych firm i nie dotyczy witryny Dynamics 365 e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3342-120">**Create customer in async mode**: This is a legacy setting applicable to third-party e-Commerce channels and is not applicable to the Dynamics 365 e-Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3342-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a3342-121">Additional resources</span></span>

[<span data-ttu-id="a3342-122">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="a3342-122">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="a3342-123">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="a3342-123">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="a3342-124">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="a3342-124">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="a3342-125">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a3342-125">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="a3342-126">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="a3342-126">Set up a call center channel</span></span>](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
