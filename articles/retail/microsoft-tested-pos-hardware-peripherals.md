---
title: "Urządzenia peryferyjne punktu sprzedaży"
description: "Aplikacje Retail Modern Point of Sale (POS) i Cloud POS mogą wykorzystywać różnorodne urządzenia peryferyjne dla punktów sprzedaży. Obsługa wielu interfejsów i opcji wdrażania pozwala realizować różne scenariusze biznesowe wymagane przez sprzedawców detalicznych."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 215234
ms.assetid: 1893d4b3-e1b7-4b66-be58-0102addd5b36
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4fbfb176f2504be8aaf67992d094da1daeefeb76
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="pos-hardware-peripherals"></a><span data-ttu-id="fd624-103">Urządzenia peryferyjne punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="fd624-103">POS hardware peripherals</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="fd624-104">Aplikacje Retail Modern Point of Sale (POS) i Cloud POS mogą wykorzystywać różnorodne urządzenia peryferyjne dla punktów sprzedaży. Obsługa wielu interfejsów i opcji wdrażania pozwala realizować różne scenariusze biznesowe wymagane przez sprzedawców detalicznych.</span><span class="sxs-lookup"><span data-stu-id="fd624-104">Retail Modern point of sale (POS) and Cloud POS can utilize a wide range of POS hardware peripherals, with multiple interfaces and deployment options to achieve a retailer’s various business scenarios.</span></span> 

<span data-ttu-id="fd624-105">Aby zapewnić obsługę jak najszerszej gamy i modeli urządzeń różnych producentów, moduł punktu sprzedaży wykorzystuje standardowe interfejsy, takie jak OLE dla programu Retail POS (OPOS), sterowniki urządzeń systemu Windows oraz interfejsy programowania aplikacji (API) dla punktów usług systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="fd624-105">To support the widest selection of devices across manufactures and models, POS utilizes standard interfaces such as OLE for Retail POS (OPOS), Windows device drivers, and Windows point of service application program interfaces (APIs).</span></span> <span data-ttu-id="fd624-106">Ogólnie rzecz biorąc moduł punktu sprzedaży będzie działał na tych urządzeniach pod warunkiem zapewnienia odpowiedniego sterownika.</span><span class="sxs-lookup"><span data-stu-id="fd624-106">Generally, POS will work on these devices provided that the appropriate driver is supplied.</span></span> <span data-ttu-id="fd624-107">Jednak ponieważ implementacja tych standardów może być nieco inna u każdego producenta sprzętu i twórcy oprogramowania, często występują różnice w obsługiwanych funkcjach lub zachowaniach.</span><span class="sxs-lookup"><span data-stu-id="fd624-107">However, because each manufacturer and software developer’s implementation of these standards can vary, there are often differences in supported capabilities or behaviors.</span></span>

<span data-ttu-id="fd624-108">Poniższa lista zawiera modele urządzeń w każdej klasie, które zostały wewnętrznie sprawdzone przez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd624-108">The following list includes device models, in each class, that have been tested internally by Microsoft.</span></span>

<span data-ttu-id="fd624-109">**Urządzenia OPOS**</span><span class="sxs-lookup"><span data-stu-id="fd624-109">**OPOS devices**</span></span>

-   <span data-ttu-id="fd624-110">Czytnik kodów kreskowych — Motorola DS9208</span><span class="sxs-lookup"><span data-stu-id="fd624-110">Barcode – Motorola DS9208</span></span>
-   <span data-ttu-id="fd624-111">Czytnik kart magnetycznych — HP IDRA-334133, SD Magtek - 21073062</span><span class="sxs-lookup"><span data-stu-id="fd624-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span></span>
-   <span data-ttu-id="fd624-112">Wyświetlacz wierszowy — Epson M58DC</span><span class="sxs-lookup"><span data-stu-id="fd624-112">LineDisplay – Epson M58DC</span></span>
-   <span data-ttu-id="fd624-113">Konsola PIN — Verifone 1000SE</span><span class="sxs-lookup"><span data-stu-id="fd624-113">Pinpad – Verifone 1000SE</span></span>
-   <span data-ttu-id="fd624-114">Konsola do podpisu elektronicznego — Scriptel ST1550</span><span class="sxs-lookup"><span data-stu-id="fd624-114">Signature pad – Scriptel ST1550</span></span>
-   <span data-ttu-id="fd624-115">Drukarka — EPSON TM-T88IV, TMT88V</span><span class="sxs-lookup"><span data-stu-id="fd624-115">Printer – EPSON TM-T88IV, TMT88V</span></span>
-   <span data-ttu-id="fd624-116">Szuflada kasowa — Star SMD2-1317BK44</span><span class="sxs-lookup"><span data-stu-id="fd624-116">Cash drawer – Star SMD2-1317BK44</span></span>
-   <span data-ttu-id="fd624-117">Waga — Datalogic Magellan 8400</span><span class="sxs-lookup"><span data-stu-id="fd624-117">Scale – Datalogic Magellan 8400</span></span>

<span data-ttu-id="fd624-118">**Czytnik kart magnetycznych podłączany do klawiatury**</span><span class="sxs-lookup"><span data-stu-id="fd624-118">**Keyboard wedge MSR**</span></span>

-   <span data-ttu-id="fd624-119">Magtek USB</span><span class="sxs-lookup"><span data-stu-id="fd624-119">Magtek USB</span></span>

<span data-ttu-id="fd624-120">**Terminal płatniczy**</span><span class="sxs-lookup"><span data-stu-id="fd624-120">**Payment terminal**</span></span>

-   <span data-ttu-id="fd624-121">Equinox L3500</span><span class="sxs-lookup"><span data-stu-id="fd624-121">Equinox L3500</span></span>
-   <span data-ttu-id="fd624-122">Verifone MX925</span><span class="sxs-lookup"><span data-stu-id="fd624-122">Verifone MX925</span></span>

<span data-ttu-id="fd624-123">**Urządzenia sieciowe**</span><span class="sxs-lookup"><span data-stu-id="fd624-123">**Network devices**</span></span>

-   <span data-ttu-id="fd624-124">Drukarka — Star TSP650II</span><span class="sxs-lookup"><span data-stu-id="fd624-124">Printer – Star TSP650II</span></span>
-   <span data-ttu-id="fd624-125">Szuflada kasowa — APG Atwood</span><span class="sxs-lookup"><span data-stu-id="fd624-125">Cash drawer – APG Atwood</span></span>
-   <span data-ttu-id="fd624-126">Terminal płatniczy — MX915, MX925</span><span class="sxs-lookup"><span data-stu-id="fd624-126">Payment terminal – MX915, MX925</span></span>

<span data-ttu-id="fd624-127">**Bezpośrednio do MPOS, tylko IPC**</span><span class="sxs-lookup"><span data-stu-id="fd624-127">**MPOS direct IPC only**</span></span>

-   <span data-ttu-id="fd624-128">Czytnik kodów kreskowych — Honeywell 1900, HP LS2208</span><span class="sxs-lookup"><span data-stu-id="fd624-128">Barcode – Honeywell 1900, HP LS2208</span></span>
-   <span data-ttu-id="fd624-129">Czytnik kart magnetycznych — SD Magtek - 21073075</span><span class="sxs-lookup"><span data-stu-id="fd624-129">MSR – Magtek PN - 21073075</span></span>





