---
title: Tworzenie profilu funkcji handlu detalicznego
description: W tym temacie opisano sposób tworzenia profilu funkcji w rozwiązaniu Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: b8d481597485775796290f61de19ef7682cb9f43
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792005"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="8db03-103">Tworzenie profilu funkcji handlu detalicznego</span><span class="sxs-lookup"><span data-stu-id="8db03-103">Create a retail functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8db03-104">W tym temacie opisano sposób tworzenia profilu funkcji w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8db03-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8db03-105">Profil funkcji handlu umożliwia używanie różnych ustawień dla kanałów online.</span><span class="sxs-lookup"><span data-stu-id="8db03-105">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="8db03-106">Każdy kanał musi określać profil funkcji.</span><span class="sxs-lookup"><span data-stu-id="8db03-106">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="8db03-107">Tworzenie profilu funkcji</span><span class="sxs-lookup"><span data-stu-id="8db03-107">Create a functionality profile</span></span>

<span data-ttu-id="8db03-108">Aby utworzyć profil funkcji, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="8db03-108">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="8db03-109">W okienku nawigacji przejdź do ustawień **Moduły \> Ustawienia kanału \> Profile punktu sprzedaży \> Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="8db03-109">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="8db03-110">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="8db03-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8db03-111">W polu **profil** wprowadź identyfikator profilu („FN006” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="8db03-111">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="8db03-112">W polu **opis** wprowadź wartość („profil Adventure Works” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="8db03-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="8db03-113">W sekcji **ogólne** wybierz kraj dla ustawień regionalnych **ISO**.</span><span class="sxs-lookup"><span data-stu-id="8db03-113">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="8db03-114">W sekcji **ogólne** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="8db03-114">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="8db03-115">W sekcji **ogólne** wybierz **identyfikator profilu paragonów** dla paragonów w wiadomościach e-mail.</span><span class="sxs-lookup"><span data-stu-id="8db03-115">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="8db03-116">W sekcji **Funkcje** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="8db03-116">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="8db03-117">W sekcji **Ilość** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="8db03-117">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="8db03-118">W sekcji **Kody informacji** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="8db03-118">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="8db03-119">W sekcji **Numeracja paragonów** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="8db03-119">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="8db03-120">Poniższy obraz przedstawia przykładowy profil funkcji.</span><span class="sxs-lookup"><span data-stu-id="8db03-120">The following image shows an example functionality profile.</span></span>
  
![Przekład profilu funkcji](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="8db03-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8db03-122">Additional resources</span></span>

[<span data-ttu-id="8db03-123">Kody informacji i grupy kodów informacji</span><span class="sxs-lookup"><span data-stu-id="8db03-123">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="8db03-124">Tworzenie nowej książki adresowej</span><span class="sxs-lookup"><span data-stu-id="8db03-124">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="8db03-125">Omówienie układu ekranu</span><span class="sxs-lookup"><span data-stu-id="8db03-125">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="8db03-126">Konfigurowanie i instalowanie modułu Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="8db03-126">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
