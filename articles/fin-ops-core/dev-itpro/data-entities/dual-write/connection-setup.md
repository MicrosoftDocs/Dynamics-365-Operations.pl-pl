---
title: Wskazówki dotyczące konfigurowania podwójnego zapisu
description: W tym temacie opisano scenariusze obsługiwane w konfiguracji podwójnego zapisu.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 2d77a1458f3f4c79b231e6a6d7cc320b8ee1fad9
ms.sourcegitcommit: ee643d651d57560bccae2f99238faa39881f5c64
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "4088513"
---
# <a name="guidance-for-how-to-set-up-dual-write"></a><span data-ttu-id="a0b20-103">Wskazówki dotyczące konfigurowania podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="a0b20-103">Guidance for how to set up dual-write</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="a0b20-104">Można skonfigurować połączenie podwójnego zapisywania między środowiskiem Finance and Operations a środowiskiem Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a0b20-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="a0b20-105">Środowisko **Finance and Operations** stanowi podstawową platformę dla aplikacji **Finance and Operations** (na przykład Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management oraz Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="a0b20-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="a0b20-106">**Środowisko Common Data Service** stanowi podstawową platformę aplikacji opartych na **aplikacjach do zakontraktowania odbiorcy** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing i Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="a0b20-106">A **Common Data Service environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="a0b20-107">Human Resources w Finance and Operations obsługuje połączenia dwukrotnego zapisu, ale aplikacja Dynamics 365 Human Resources nie.</span><span class="sxs-lookup"><span data-stu-id="a0b20-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="a0b20-108">Mechanizm konfiguracji zmienia się w zależności od subskrypcji i środowiska.</span><span class="sxs-lookup"><span data-stu-id="a0b20-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="a0b20-109">W przypadku nowych wystąpień aplikacji Finance and Operations konfiguracja podwójnego zapisywania rozpoczyna się w Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="a0b20-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="a0b20-110">Jeśli masz licencję na Power Platform, otrzymasz nowe środowisko Common Data Service, jeśli Twoja dzierżawa nie ma takiego nowego środowiska.</span><span class="sxs-lookup"><span data-stu-id="a0b20-110">If you have a license for Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="a0b20-111">W przypadku istniejących aplikacji Finance and Operations wystąpień Konfiguracja dwukrotnego zapisu rozpoczyna się w środowisku Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a0b20-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="a0b20-112">Przed rozpoczęciem podwójnego zapisywania w jednostce można uruchomić synchronizację początkową umożliwiającą obsługę istniejących danych po obu stronach aplikacji Finance and Operations i aplikacji do zakontraktowania klientów.</span><span class="sxs-lookup"><span data-stu-id="a0b20-112">Before you start dual-write on an entity, you can run an initial sync to handle existing data on both sides of Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="a0b20-113">Synchronizację początkową można pominąć, jeśli nie ma potrzeby synchronizowania danych między tymi środowiskami.</span><span class="sxs-lookup"><span data-stu-id="a0b20-113">You can skip the initial sync if you don't need to synchronize data between the two environments.</span></span>

<span data-ttu-id="a0b20-114">Synchronizacja wstępna umożliwia skopiowanie istniejących danych z jednej aplikacji na inną dwukierunkową.</span><span class="sxs-lookup"><span data-stu-id="a0b20-114">An initial sync lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="a0b20-115">Istnieje kilka różnych scenariuszy konfiguracji, w zależności od tego, które środowiska są już dostępne, oraz jakiego typu dane znajdują się w środowiskach.</span><span class="sxs-lookup"><span data-stu-id="a0b20-115">There are several different setup scenarios depending on which environments you already have and what type of data is in the environments.</span></span>

<span data-ttu-id="a0b20-116">Obsługiwane są następujące scenariusze konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="a0b20-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="a0b20-117">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="a0b20-118">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="a0b20-119">Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="a0b20-120">Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="a0b20-121">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie nowej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="a0b20-122">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="a0b20-123">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="a0b20-124">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i nowym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="a0b20-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="a0b20-125">Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="a0b20-125">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="a0b20-126">Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.</span><span class="sxs-lookup"><span data-stu-id="a0b20-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="a0b20-127">Zainicjowano obsługę administracyjną nowego, pustego wystąpienia aplikacji do zakontraktowania odbiorcy, w której zainstalowano rozwiązanie podstawowe programu CRM.</span><span class="sxs-lookup"><span data-stu-id="a0b20-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="a0b20-128">Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.</span><span class="sxs-lookup"><span data-stu-id="a0b20-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="a0b20-129">W mapowaniach jednostek włączono obsługę synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="a0b20-129">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="a0b20-130">Oba środowiska są następnie gotowe do synchronizacji danych na żywo.</span><span class="sxs-lookup"><span data-stu-id="a0b20-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="a0b20-131">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="a0b20-132">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i istniejącym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="a0b20-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="a0b20-133">Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="a0b20-133">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="a0b20-134">Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.</span><span class="sxs-lookup"><span data-stu-id="a0b20-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="a0b20-135">Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.</span><span class="sxs-lookup"><span data-stu-id="a0b20-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="a0b20-136">W mapowaniach jednostek włączono obsługę synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="a0b20-136">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="a0b20-137">Oba środowiska są następnie gotowe do synchronizacji danych na żywo.</span><span class="sxs-lookup"><span data-stu-id="a0b20-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="a0b20-138">Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a0b20-138">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="a0b20-139">Utwórz nową firmę w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a0b20-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="a0b20-140">Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.</span><span class="sxs-lookup"><span data-stu-id="a0b20-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="a0b20-141">[Uruchom](bootstrap-company-data.md) dane Common Data Service przy użyciu trzech liter kodu firmy Międzynarodowej Organizacji Normalizacyjnej (ISO).</span><span class="sxs-lookup"><span data-stu-id="a0b20-141">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="a0b20-142">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a0b20-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="a0b20-143">Aby zapoznać się z przykładem i alternatywnym podejściem, zajrzyj do [Przykładu](#example).</span><span class="sxs-lookup"><span data-stu-id="a0b20-143">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="a0b20-144">Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="a0b20-145">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a nowym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji wystąpienia aplikacji do zakontraktowania odbiorcy](#new-new), która znajduje się we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="a0b20-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="a0b20-146">Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane z aplikacją do zakontraktowania odbiorcy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a0b20-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="a0b20-147">Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="a0b20-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="a0b20-148">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a0b20-148">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="a0b20-149">Aby zapoznać się z przykładem i alternatywnym podejściem, zajrzyj do [Przykładu](#example).</span><span class="sxs-lookup"><span data-stu-id="a0b20-149">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="a0b20-150">Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="a0b20-151">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a istniejącym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji istniejącego wystąpienia aplikacji do zakontraktowania odbiorcy](#new-existing), która znajduje się we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="a0b20-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="a0b20-152">Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane z aplikacją do zakontraktowania odbiorcy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a0b20-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="a0b20-153">Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="a0b20-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="a0b20-154">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a0b20-154">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="a0b20-155">Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a0b20-155">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="a0b20-156">Utwórz nową firmę w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a0b20-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="a0b20-157">Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.</span><span class="sxs-lookup"><span data-stu-id="a0b20-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="a0b20-158">[Uruchom](bootstrap-company-data.md) dane Common Data Service przy użyciu trzech liter kodu firmy ISO.</span><span class="sxs-lookup"><span data-stu-id="a0b20-158">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="a0b20-159">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a0b20-159">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="a0b20-160">Aby zapoznać się z przykładem i alternatywnym podejściem, zajrzyj do [Przykładu](#example).</span><span class="sxs-lookup"><span data-stu-id="a0b20-160">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="a0b20-161">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie nowej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="a0b20-162">Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finance and Operations a nowym wystąpieniem aplikacji do zakontraktowania odbiorcy występuje w środowisku Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="a0b20-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="a0b20-163">[Skonfiguruj połączenie z aplikacji Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="a0b20-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="a0b20-164">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a0b20-164">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="a0b20-165">Aby zapoznać się z przykładem i alternatywnym podejściem, zajrzyj do [Przykładu](#example).</span><span class="sxs-lookup"><span data-stu-id="a0b20-165">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="a0b20-166">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a0b20-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="a0b20-167">Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finance and Operations a istniejącym wystąpieniem aplikacji do zakontraktowania odbiorcy występuje w środowisku Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="a0b20-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app  occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="a0b20-168">Skonfiguruj połączenie z aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a0b20-168">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="a0b20-169">Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, należy [załadować](bootstrap-company-data.md) dane Common Data Service przy użyciu trój-literowego kodu ISO firmy.</span><span class="sxs-lookup"><span data-stu-id="a0b20-169">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="a0b20-170">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a0b20-170">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="a0b20-171">Aby zapoznać się z przykładem i alternatywnym podejściem, zajrzyj do [Przykładu](#example).</span><span class="sxs-lookup"><span data-stu-id="a0b20-171">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="example"></a><span data-ttu-id="a0b20-172">Przykład</span><span class="sxs-lookup"><span data-stu-id="a0b20-172">Example</span></span>

<span data-ttu-id="a0b20-173">Aby zapoznać się z przykładem, należy zapoznać się z formularzem [Włączanie odbiorcy v3 — Mapa encji kontaktów](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span><span class="sxs-lookup"><span data-stu-id="a0b20-173">For an example, see [Enabling the Customers V3—Contacts entity map](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span></span>

<span data-ttu-id="a0b20-174">W celu rozwiązania alternatywnego opartego na woluminach danych w każdej jednostce, która musi uruchomić synchronizację początkową, należy zapoznać się z [Zagadnienia dotyczące synchronizacji początkowej](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="a0b20-174">For an alternative approach based on data volumes in each entity that need to run initial sync, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>
