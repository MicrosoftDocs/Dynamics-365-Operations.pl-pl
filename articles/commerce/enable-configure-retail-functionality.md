---
title: Inicjowanie danych początkowych w nowych środowiskach rozwiązania Commerce
description: W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Dynamics 365 Commerce.
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
ms.openlocfilehash: 24d4d49c51738203bb89a9844d57f644b8afd4b7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414851"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a><span data-ttu-id="99f64-103">Inicjowanie danych początkowych w nowych środowiskach rozwiązania Commerce</span><span class="sxs-lookup"><span data-stu-id="99f64-103">Initialize seed data in new Commerce environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="99f64-104">W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="99f64-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Commerce.</span></span>

<span data-ttu-id="99f64-105">Po wdrożeniu rozwiązania Commerce sprzedaży za pomocą Microsoft Dynamics Lifecycle Services (LCS) trzeba zainicjować konfigurację sieci sprzedaży Commerce, aby utworzyć dane konfiguracji podstawowej.</span><span class="sxs-lookup"><span data-stu-id="99f64-105">After the Commerce solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the Commerce configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99f64-106">Przed zainicjowaniem konfiguracji handlowej, upewnij się, że wybrany został język i adres pocztowy dla każdej firmy, w której konfigurujesz sklepy sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="99f64-106">Before you initialize the commerce configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up stores.</span></span> <span data-ttu-id="99f64-107">Ten krok należy wykonać dla każdej firmy używanej dla handlu.</span><span class="sxs-lookup"><span data-stu-id="99f64-107">This step must be completed for each legal entity that you use for commerce.</span></span>

<span data-ttu-id="99f64-108">Aby zainicjować konfigurację, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="99f64-108">To initialize the configuration, follow these steps.</span></span>

1. <span data-ttu-id="99f64-109">Uruchom klienta rozwiązania Commerce.</span><span class="sxs-lookup"><span data-stu-id="99f64-109">Start the Commerce client.</span></span>
2. <span data-ttu-id="99f64-110">Wybierz kolejno opcje **Ustawienia handlu i inne** &gt; **Ustawienia Headquarters** &gt; **Parametry** &gt; **Parametry Commerce**.</span><span class="sxs-lookup"><span data-stu-id="99f64-110">Click **Retail and Commerce** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Commerce parameters**.</span></span>
3. <span data-ttu-id="99f64-111">Kliknij **Inicjuj**.</span><span class="sxs-lookup"><span data-stu-id="99f64-111">Click **Initialize**.</span></span>

<span data-ttu-id="99f64-112">Inicjowanie tworzy następujące dane ogólne konfiguracji domyślnej:</span><span class="sxs-lookup"><span data-stu-id="99f64-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="99f64-113">Zadania i podzadania transferu danych w Commerce</span><span class="sxs-lookup"><span data-stu-id="99f64-113">Commerce scheduler jobs and subjobs</span></span>
- <span data-ttu-id="99f64-114">Schemat kanału handlowego</span><span class="sxs-lookup"><span data-stu-id="99f64-114">Commerce channel schema</span></span>
- <span data-ttu-id="99f64-115">Harmonogramy dystrybucji Commerce</span><span class="sxs-lookup"><span data-stu-id="99f64-115">Commerce distribution schedules</span></span>
- <span data-ttu-id="99f64-116">Domyślne układy ekranu, które obejmują siatki przycisków, obrazy i kompozycje</span><span class="sxs-lookup"><span data-stu-id="99f64-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="99f64-117">Informacje o strefie czasowej</span><span class="sxs-lookup"><span data-stu-id="99f64-117">Time zone information</span></span>
- <span data-ttu-id="99f64-118">Operacje punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="99f64-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="99f64-119">Uprawnienia punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="99f64-119">POS permissions</span></span>
- <span data-ttu-id="99f64-120">Raporty kanału</span><span class="sxs-lookup"><span data-stu-id="99f64-120">Channel reports</span></span>
- <span data-ttu-id="99f64-121">Metadane atrybutu</span><span class="sxs-lookup"><span data-stu-id="99f64-121">Attribute metadata</span></span>
- <span data-ttu-id="99f64-122">Szablony weryfikacji jednostek</span><span class="sxs-lookup"><span data-stu-id="99f64-122">Entity validation templates</span></span>
- <span data-ttu-id="99f64-123">Zadania wsadowego do usuwania historii sesji Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="99f64-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="99f64-124">Oprócz tego logowanie związane z branżą kart płatności (PCI) jest włączone dla bazy danych Commerce.</span><span class="sxs-lookup"><span data-stu-id="99f64-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Commerce database.</span></span>

> [!NOTE]
> <span data-ttu-id="99f64-125">Istnieje możliwość oddzielnego skonfigurowania modułu Harmonogram Commerce.</span><span class="sxs-lookup"><span data-stu-id="99f64-125">There is an option to separately configure the Commerce scheduler.</span></span> <span data-ttu-id="99f64-126">Ta opcja pozwala zresetować konfigurację Harmonogramu Commerce w sieci sprzedaży do ustawień domyślnych.</span><span class="sxs-lookup"><span data-stu-id="99f64-126">This option lets you reset the Commerce scheduler configuration to its default settings.</span></span>

<span data-ttu-id="99f64-127">Po zakończeniu inicjowania należy skonfigurować dodatkowe dane handlowe.</span><span class="sxs-lookup"><span data-stu-id="99f64-127">After initialization is completed, you must configure additional commerce data.</span></span> <span data-ttu-id="99f64-128">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="99f64-128">Here are some examples:</span></span>

- <span data-ttu-id="99f64-129">Parametry handlu</span><span class="sxs-lookup"><span data-stu-id="99f64-129">Commerce parameters</span></span>
- <span data-ttu-id="99f64-130">Parametry handlu harmonogramu</span><span class="sxs-lookup"><span data-stu-id="99f64-130">Commerce scheduler parameters</span></span>
- <span data-ttu-id="99f64-131">Kanały Commerce</span><span class="sxs-lookup"><span data-stu-id="99f64-131">Commerce channels</span></span>
- <span data-ttu-id="99f64-132">Kasy i urządzenia</span><span class="sxs-lookup"><span data-stu-id="99f64-132">Registers and devices</span></span>
- <span data-ttu-id="99f64-133">Asortymenty</span><span class="sxs-lookup"><span data-stu-id="99f64-133">Assortments</span></span>
