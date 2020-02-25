---
title: Tworzenie profilu funkcji sieci sprzedaży
description: W tym temacie opisano sposób tworzenia profilu funkcji sieci sprzedaży w rozwiązaniu Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 9fb0fd63b11e55f2b153fc9c135f148a6e343057
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002850"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="75b11-103">Tworzenie profilu funkcji sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="75b11-103">Create a retail functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="75b11-104">W tym temacie opisano sposób tworzenia profilu funkcji sieci sprzedaży w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="75b11-104">This topic describes how to create a retail functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="75b11-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="75b11-105">Overview</span></span>

<span data-ttu-id="75b11-106">Profil funkcji sieci sprzedaży umożliwia używanie różnych ustawień dla kanałów online.</span><span class="sxs-lookup"><span data-stu-id="75b11-106">The retail functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="75b11-107">Każdy kanał sieci sprzedaży musi określać profil funkcji sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="75b11-107">Each retail channel must specify a retail functionality profile.</span></span>

## <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="75b11-108">Tworzenie profilu funkcji sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="75b11-108">Create a retail functionality profile</span></span>

<span data-ttu-id="75b11-109">Aby utworzyć profil funkcji sieci sprzedaży, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="75b11-109">To create a retail functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="75b11-110">W okienku nawigacji przejdź do ustawień **Moduły \> Ustawienia kanału \> Profile punktu sprzedaży \> Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="75b11-110">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="75b11-111">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="75b11-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="75b11-112">W polu **profil** wprowadź identyfikator profilu („FN006” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="75b11-112">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="75b11-113">W polu **opis** wprowadź wartość („profil Adventure Works” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="75b11-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="75b11-114">W sekcji **ogólne** wybierz kraj dla ustawień regionalnych **ISO**.</span><span class="sxs-lookup"><span data-stu-id="75b11-114">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="75b11-115">W sekcji **ogólne** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="75b11-115">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="75b11-116">W sekcji **ogólne** wybierz **identyfikator profilu paragonów** dla paragonów w wiadomościach e-mail.</span><span class="sxs-lookup"><span data-stu-id="75b11-116">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="75b11-117">W sekcji **Funkcje** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="75b11-117">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="75b11-118">W sekcji **Ilość** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="75b11-118">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="75b11-119">W sekcji **Kody informacji** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="75b11-119">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="75b11-120">W sekcji **Numeracja paragonów** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="75b11-120">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="75b11-121">Poniższy obraz przedstawia przykładowy profil funkcji sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="75b11-121">The following image shows an example retail functionality profile.</span></span>
  
![Przekład profilu funkcji sieci sprzedaży](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="75b11-123">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="75b11-123">Additional resources</span></span>

[<span data-ttu-id="75b11-124">Kody informacji i grupy kodów informacji</span><span class="sxs-lookup"><span data-stu-id="75b11-124">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="75b11-125">Tworzenie nowej książki adresowej</span><span class="sxs-lookup"><span data-stu-id="75b11-125">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="75b11-126">Omówienie układu ekranu</span><span class="sxs-lookup"><span data-stu-id="75b11-126">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="75b11-127">Konfigurowanie i instalowanie modułu Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="75b11-127">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 
