---
title: "Inicjowanie danych początkowych w nowym środowisku sieci sprzedaży"
description: "W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ac4f651cd7e5df912ea2535eafd5e54c11377253
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a><span data-ttu-id="45a23-103">Inicjowanie danych początkowych w nowym środowisku sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="45a23-103">Initialize seed data in a new Retail environment</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="45a23-104">W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="45a23-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="45a23-105">Po wdrożeniu rozwiązania Sieć sprzedaży za pomocą Microsoft Dynamics Lifecycle Services (LCS) trzeba zainicjować konfigurację sieci sprzedaży, aby utworzyć dane konfiguracji podstawowej.</span><span class="sxs-lookup"><span data-stu-id="45a23-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span> <span data-ttu-id="45a23-106">**Ważne:** przed zainicjowaniem konfiguracji sieci sprzedaży, upewnij się, że wybrany został język i adres pocztowy dla każdej firmy, w której konfigurujesz sklepy sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="45a23-106">**Important:** Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="45a23-107">Ten krok należy wykonać dla każdej firmy używanej dla sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="45a23-107">This step must be completed for each legal entity that you use for retail.</span></span> <span data-ttu-id="45a23-108">Aby zainicjować konfigurację sieci sprzedaży, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="45a23-108">To initialize the retail configuration, follow these steps.</span></span>

1.  <span data-ttu-id="45a23-109">Uruchom klienta programu Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="45a23-109">Start the Dynamics 365 for Retail client.</span></span>
2.  <span data-ttu-id="45a23-110">Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia centrali** &gt; **Parametry** &gt; **Parametry sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="45a23-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3.  <span data-ttu-id="45a23-111">Kliknij **Inicjuj**.</span><span class="sxs-lookup"><span data-stu-id="45a23-111">Click **Initialize**.</span></span>

<span data-ttu-id="45a23-112">Inicjowanie tworzy następujące dane ogólne konfiguracji domyślnej:</span><span class="sxs-lookup"><span data-stu-id="45a23-112">Initialization creates the following default configuration data:</span></span>

-   <span data-ttu-id="45a23-113">Zadania i podzadania transferu danych w sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="45a23-113">Retail scheduler jobs and subjobs</span></span>
-   <span data-ttu-id="45a23-114">Schemat kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="45a23-114">Retail channel schema</span></span>
-   <span data-ttu-id="45a23-115">Harmonogramy dystrybucji w sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="45a23-115">Retail distribution schedules</span></span>
-   <span data-ttu-id="45a23-116">Domyślne układy ekranu, które obejmują siatki przycisków, obrazy i kompozycje</span><span class="sxs-lookup"><span data-stu-id="45a23-116">Default screen layouts, which include button grids, images, and themes</span></span>
-   <span data-ttu-id="45a23-117">Informacje o strefie czasowej</span><span class="sxs-lookup"><span data-stu-id="45a23-117">Time zone information</span></span>
-   <span data-ttu-id="45a23-118">Operacje punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="45a23-118">Point-of-sale (POS) operations</span></span>
-   <span data-ttu-id="45a23-119">Uprawnienia punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="45a23-119">POS permissions</span></span>
-   <span data-ttu-id="45a23-120">Raporty kanału</span><span class="sxs-lookup"><span data-stu-id="45a23-120">Channel reports</span></span>
-   <span data-ttu-id="45a23-121">Metadane atrybutu</span><span class="sxs-lookup"><span data-stu-id="45a23-121">Attribute metadata</span></span>
-   <span data-ttu-id="45a23-122">Szablony weryfikacji jednostek</span><span class="sxs-lookup"><span data-stu-id="45a23-122">Entity validation templates</span></span>
-   <span data-ttu-id="45a23-123">Zadanie wsadowe do usuwania historii sesji Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="45a23-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="45a23-124">Oprócz tego protokołowanie związane ze standardem organizacji Payment Card Industry (PCI) jest włączone dla bazy danych programu Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="45a23-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span> <span data-ttu-id="45a23-125">**Uwaga:** istnieje możliwość oddzielnego skonfigurowania modułu Transfer danych.</span><span class="sxs-lookup"><span data-stu-id="45a23-125">**Note:** There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="45a23-126">Ta opcja pozwala zresetować konfigurację transfer danych w sieci sprzedaży do ustawień domyślnych.</span><span class="sxs-lookup"><span data-stu-id="45a23-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span> <span data-ttu-id="45a23-127">Po zakończeniu inicjowania należy skonfigurować dodatkowe dane sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="45a23-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="45a23-128">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="45a23-128">Here are some examples:</span></span>

-   <span data-ttu-id="45a23-129">Parametry sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="45a23-129">Retail parameters</span></span>
-   <span data-ttu-id="45a23-130">Parametry transferu danych w sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="45a23-130">Retail scheduler parameters</span></span>
-   <span data-ttu-id="45a23-131">Kanały sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="45a23-131">Retail channels</span></span>
-   <span data-ttu-id="45a23-132">Kasy i urządzenia</span><span class="sxs-lookup"><span data-stu-id="45a23-132">Registers and devices</span></span>
-   <span data-ttu-id="45a23-133">Asortymenty</span><span class="sxs-lookup"><span data-stu-id="45a23-133">Assortments</span></span>





