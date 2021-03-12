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
ms.openlocfilehash: a53fc77a7d457534428929bd431175be7cf450f7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979654"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="f4d98-103">Tworzenie profilu funkcji handlu detalicznego</span><span class="sxs-lookup"><span data-stu-id="f4d98-103">Create a retail functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f4d98-104">W tym temacie opisano sposób tworzenia profilu funkcji w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4d98-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f4d98-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="f4d98-105">Overview</span></span>

<span data-ttu-id="f4d98-106">Profil funkcji handlu umożliwia używanie różnych ustawień dla kanałów online.</span><span class="sxs-lookup"><span data-stu-id="f4d98-106">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="f4d98-107">Każdy kanał musi określać profil funkcji.</span><span class="sxs-lookup"><span data-stu-id="f4d98-107">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="f4d98-108">Tworzenie profilu funkcji</span><span class="sxs-lookup"><span data-stu-id="f4d98-108">Create a functionality profile</span></span>

<span data-ttu-id="f4d98-109">Aby utworzyć profil funkcji, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="f4d98-109">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="f4d98-110">W okienku nawigacji przejdź do ustawień **Moduły \> Ustawienia kanału \> Profile punktu sprzedaży \> Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="f4d98-110">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="f4d98-111">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f4d98-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f4d98-112">W polu **profil** wprowadź identyfikator profilu („FN006” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="f4d98-112">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="f4d98-113">W polu **opis** wprowadź wartość („profil Adventure Works” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="f4d98-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="f4d98-114">W sekcji **ogólne** wybierz kraj dla ustawień regionalnych **ISO**.</span><span class="sxs-lookup"><span data-stu-id="f4d98-114">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="f4d98-115">W sekcji **ogólne** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="f4d98-115">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="f4d98-116">W sekcji **ogólne** wybierz **identyfikator profilu paragonów** dla paragonów w wiadomościach e-mail.</span><span class="sxs-lookup"><span data-stu-id="f4d98-116">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="f4d98-117">W sekcji **Funkcje** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="f4d98-117">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="f4d98-118">W sekcji **Ilość** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="f4d98-118">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="f4d98-119">W sekcji **Kody informacji** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="f4d98-119">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="f4d98-120">W sekcji **Numeracja paragonów** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="f4d98-120">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="f4d98-121">Poniższy obraz przedstawia przykładowy profil funkcji.</span><span class="sxs-lookup"><span data-stu-id="f4d98-121">The following image shows an example functionality profile.</span></span>
  
![Przekład profilu funkcji](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="f4d98-123">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f4d98-123">Additional resources</span></span>

[<span data-ttu-id="f4d98-124">Kody informacji i grupy kodów informacji</span><span class="sxs-lookup"><span data-stu-id="f4d98-124">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="f4d98-125">Tworzenie nowej książki adresowej</span><span class="sxs-lookup"><span data-stu-id="f4d98-125">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="f4d98-126">Omówienie układu ekranu</span><span class="sxs-lookup"><span data-stu-id="f4d98-126">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="f4d98-127">Konfigurowanie i instalowanie modułu Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="f4d98-127">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 
