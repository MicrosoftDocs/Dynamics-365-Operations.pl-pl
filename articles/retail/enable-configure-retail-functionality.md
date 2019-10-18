---
title: Inicjowanie danych początkowych w nowych środowiskach rozwiązania Retail
description: W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 49b21d81437ebd7cc55076444ee71ae1143bfac0
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025523"
---
# <a name="initialize-seed-data-in-new-retail-environments"></a><span data-ttu-id="d9f06-103">Inicjowanie danych początkowych w nowych środowiskach rozwiązania Retail</span><span class="sxs-lookup"><span data-stu-id="d9f06-103">Initialize seed data in new Retail environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d9f06-104">W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="d9f06-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Retail.</span></span>

<span data-ttu-id="d9f06-105">Po wdrożeniu rozwiązania Sieć sprzedaży za pomocą Microsoft Dynamics Lifecycle Services (LCS) trzeba zainicjować konfigurację sieci sprzedaży, aby utworzyć dane konfiguracji podstawowej.</span><span class="sxs-lookup"><span data-stu-id="d9f06-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9f06-106">Przed zainicjowaniem konfiguracji sieci sprzedaży, upewnij się, że wybrany został język i adres pocztowy dla każdej firmy, w której konfigurujesz sklepy sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d9f06-106">Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="d9f06-107">Ten krok należy wykonać dla każdej firmy używanej dla sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d9f06-107">This step must be completed for each legal entity that you use for retail.</span></span>

<span data-ttu-id="d9f06-108">Aby zainicjować konfigurację sieci sprzedaży, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d9f06-108">To initialize the retail configuration, follow these steps.</span></span>

1. <span data-ttu-id="d9f06-109">Uruchom klienta rozwiązania Retail.</span><span class="sxs-lookup"><span data-stu-id="d9f06-109">Start the Retail client.</span></span>
2. <span data-ttu-id="d9f06-110">Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia centrali** &gt; **Parametry** &gt; **Parametry sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="d9f06-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3. <span data-ttu-id="d9f06-111">Kliknij **Inicjuj**.</span><span class="sxs-lookup"><span data-stu-id="d9f06-111">Click **Initialize**.</span></span>

<span data-ttu-id="d9f06-112">Inicjowanie tworzy następujące dane ogólne konfiguracji domyślnej:</span><span class="sxs-lookup"><span data-stu-id="d9f06-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="d9f06-113">Zadania i podzadania transferu danych w sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d9f06-113">Retail scheduler jobs and subjobs</span></span>
- <span data-ttu-id="d9f06-114">Schemat kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d9f06-114">Retail channel schema</span></span>
- <span data-ttu-id="d9f06-115">Harmonogramy dystrybucji w sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d9f06-115">Retail distribution schedules</span></span>
- <span data-ttu-id="d9f06-116">Domyślne układy ekranu, które obejmują siatki przycisków, obrazy i kompozycje</span><span class="sxs-lookup"><span data-stu-id="d9f06-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="d9f06-117">Informacje o strefie czasowej</span><span class="sxs-lookup"><span data-stu-id="d9f06-117">Time zone information</span></span>
- <span data-ttu-id="d9f06-118">Operacje punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d9f06-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="d9f06-119">Uprawnienia punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d9f06-119">POS permissions</span></span>
- <span data-ttu-id="d9f06-120">Raporty kanału</span><span class="sxs-lookup"><span data-stu-id="d9f06-120">Channel reports</span></span>
- <span data-ttu-id="d9f06-121">Metadane atrybutu</span><span class="sxs-lookup"><span data-stu-id="d9f06-121">Attribute metadata</span></span>
- <span data-ttu-id="d9f06-122">Szablony weryfikacji jednostek</span><span class="sxs-lookup"><span data-stu-id="d9f06-122">Entity validation templates</span></span>
- <span data-ttu-id="d9f06-123">Zadania wsadowego do usuwania historii sesji Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="d9f06-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="d9f06-124">Oprócz tego logowanie związane z branżą kart płatności (PCI) jest włączone dla bazy danych Retail.</span><span class="sxs-lookup"><span data-stu-id="d9f06-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Retail database.</span></span>

> [!NOTE]
> <span data-ttu-id="d9f06-125">Istnieje możliwość oddzielnego skonfigurowania modułu Transfer danych.</span><span class="sxs-lookup"><span data-stu-id="d9f06-125">There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="d9f06-126">Ta opcja pozwala zresetować konfigurację transfer danych w sieci sprzedaży do ustawień domyślnych.</span><span class="sxs-lookup"><span data-stu-id="d9f06-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span>

<span data-ttu-id="d9f06-127">Po zakończeniu inicjowania należy skonfigurować dodatkowe dane sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d9f06-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="d9f06-128">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="d9f06-128">Here are some examples:</span></span>

- <span data-ttu-id="d9f06-129">Parametry sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d9f06-129">Retail parameters</span></span>
- <span data-ttu-id="d9f06-130">Parametry transferu danych w sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d9f06-130">Retail scheduler parameters</span></span>
- <span data-ttu-id="d9f06-131">Kanały sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="d9f06-131">Retail channels</span></span>
- <span data-ttu-id="d9f06-132">Kasy i urządzenia</span><span class="sxs-lookup"><span data-stu-id="d9f06-132">Registers and devices</span></span>
- <span data-ttu-id="d9f06-133">Asortymenty</span><span class="sxs-lookup"><span data-stu-id="d9f06-133">Assortments</span></span>
