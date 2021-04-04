---
title: Tworzenie profilu funkcji handlu detalicznego
description: W tym temacie opisano sposób tworzenia profilu funkcji w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.openlocfilehash: 14da5fd2b409790de2269036ccb941ffa6d3311c
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478315"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="17845-103">Tworzenie profilu funkcji handlu detalicznego</span><span class="sxs-lookup"><span data-stu-id="17845-103">Create a retail functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="17845-104">W tym temacie opisano sposób tworzenia profilu funkcji w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="17845-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="17845-105">Profil funkcji handlu umożliwia używanie różnych ustawień dla kanałów online.</span><span class="sxs-lookup"><span data-stu-id="17845-105">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="17845-106">Każdy kanał musi określać profil funkcji.</span><span class="sxs-lookup"><span data-stu-id="17845-106">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="17845-107">Tworzenie profilu funkcji</span><span class="sxs-lookup"><span data-stu-id="17845-107">Create a functionality profile</span></span>

<span data-ttu-id="17845-108">Aby utworzyć profil funkcji, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="17845-108">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="17845-109">W okienku nawigacji przejdź do ustawień **Moduły \> Ustawienia kanału \> Profile punktu sprzedaży \> Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="17845-109">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="17845-110">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="17845-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="17845-111">W polu **profil** wprowadź identyfikator profilu („FN006” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="17845-111">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="17845-112">W polu **opis** wprowadź wartość („profil Adventure Works” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="17845-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="17845-113">W sekcji **ogólne** wybierz kraj dla ustawień regionalnych **ISO**.</span><span class="sxs-lookup"><span data-stu-id="17845-113">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="17845-114">W sekcji **ogólne** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="17845-114">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="17845-115">W sekcji **ogólne** wybierz **identyfikator profilu paragonów** dla paragonów w wiadomościach e-mail.</span><span class="sxs-lookup"><span data-stu-id="17845-115">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="17845-116">W sekcji **Funkcje** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="17845-116">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="17845-117">W sekcji **Ilość** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="17845-117">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="17845-118">W sekcji **Kody informacji** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="17845-118">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="17845-119">W sekcji **Numeracja paragonów** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="17845-119">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="17845-120">Poniższy obraz przedstawia przykładowy profil funkcji.</span><span class="sxs-lookup"><span data-stu-id="17845-120">The following image shows an example functionality profile.</span></span>
  
![Przekład profilu funkcji](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="17845-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="17845-122">Additional resources</span></span>

[<span data-ttu-id="17845-123">Kody informacji i grupy kodów informacji</span><span class="sxs-lookup"><span data-stu-id="17845-123">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="17845-124">Tworzenie nowej książki adresowej</span><span class="sxs-lookup"><span data-stu-id="17845-124">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="17845-125">Omówienie układu ekranu</span><span class="sxs-lookup"><span data-stu-id="17845-125">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="17845-126">Konfigurowanie i instalowanie modułu Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="17845-126">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
