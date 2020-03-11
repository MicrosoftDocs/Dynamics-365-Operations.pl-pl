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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6bee51eb25b04eb65e588dd4cf54a0cef587aa15
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057355"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="d414c-103">Tworzenie profilu funkcji handlu detalicznego</span><span class="sxs-lookup"><span data-stu-id="d414c-103">Create a retail functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d414c-104">W tym temacie opisano sposób tworzenia profilu funkcji w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d414c-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d414c-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="d414c-105">Overview</span></span>

<span data-ttu-id="d414c-106">Profil funkcji handlu umożliwia używanie różnych ustawień dla kanałów online.</span><span class="sxs-lookup"><span data-stu-id="d414c-106">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="d414c-107">Każdy kanał musi określać profil funkcji.</span><span class="sxs-lookup"><span data-stu-id="d414c-107">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="d414c-108">Tworzenie profilu funkcji</span><span class="sxs-lookup"><span data-stu-id="d414c-108">Create a functionality profile</span></span>

<span data-ttu-id="d414c-109">Aby utworzyć profil funkcji, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="d414c-109">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="d414c-110">W okienku nawigacji przejdź do ustawień **Moduły \> Ustawienia kanału \> Profile punktu sprzedaży \> Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="d414c-110">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="d414c-111">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d414c-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d414c-112">W polu **profil** wprowadź identyfikator profilu („FN006” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="d414c-112">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="d414c-113">W polu **opis** wprowadź wartość („profil Adventure Works” w poniższym obrazie poniżej).</span><span class="sxs-lookup"><span data-stu-id="d414c-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="d414c-114">W sekcji **ogólne** wybierz kraj dla ustawień regionalnych **ISO**.</span><span class="sxs-lookup"><span data-stu-id="d414c-114">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="d414c-115">W sekcji **ogólne** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="d414c-115">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="d414c-116">W sekcji **ogólne** wybierz **identyfikator profilu paragonów** dla paragonów w wiadomościach e-mail.</span><span class="sxs-lookup"><span data-stu-id="d414c-116">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="d414c-117">W sekcji **Funkcje** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="d414c-117">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="d414c-118">W sekcji **Ilość** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="d414c-118">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="d414c-119">W sekcji **Kody informacji** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="d414c-119">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="d414c-120">W sekcji **Numeracja paragonów** zmodyfikuj inne ustawienia, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="d414c-120">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="d414c-121">Poniższy obraz przedstawia przykładowy profil funkcji.</span><span class="sxs-lookup"><span data-stu-id="d414c-121">The following image shows an example functionality profile.</span></span>
  
![Przekład profilu funkcji](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="d414c-123">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d414c-123">Additional resources</span></span>

[<span data-ttu-id="d414c-124">Kody informacji i grupy kodów informacji</span><span class="sxs-lookup"><span data-stu-id="d414c-124">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="d414c-125">Tworzenie nowej książki adresowej</span><span class="sxs-lookup"><span data-stu-id="d414c-125">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="d414c-126">Omówienie układu ekranu</span><span class="sxs-lookup"><span data-stu-id="d414c-126">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="d414c-127">Konfigurowanie i instalowanie modułu Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="d414c-127">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 
