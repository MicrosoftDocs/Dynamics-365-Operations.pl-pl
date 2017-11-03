---
title: "Zarządzanie magazynem"
description: "Zarządzanie magazynem umożliwia monitorowanie i automatyzację procesów magazynowych."
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ed8baca264e3c277f9c1ff33b20f89f1fd6991c0
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---
# <a name="warehouse-management"></a><span data-ttu-id="9f195-103">Zarządzanie magazynem</span><span class="sxs-lookup"><span data-stu-id="9f195-103">Warehouse management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9f195-104">Moduł Zarządzanie magazynem dla rozwiązania Dynamics 365 for Finance and Operations, Enterprise Edition umożliwia zarządzanie procesami magazynowymi w firmach produkcyjnych, dystrybucyjnych i sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="9f195-104">The Warehouse management module for Dynamics 365 for Finance and Operations, Enterprise edition lets you manage warehouse processes in manufacturing, distribution, and retail companies.</span></span> <span data-ttu-id="9f195-105">Ten moduł oferuje różnorodne funkcje w celu obsługi magazynu na optymalnym poziomie w dowolnej chwili.</span><span class="sxs-lookup"><span data-stu-id="9f195-105">This module has a wide range of features to support the warehouse facility at an optimal level, at any time.</span></span> <span data-ttu-id="9f195-106">Zarządzanie magazynem jest w pełni zintegrowane z innymi procesami biznesowymi w rozwiązaniu Finance and Operations, takimi jak transport, produkcja, kontrola jakości, zakupy, przenoszenie, sprzedaż i zwroty.</span><span class="sxs-lookup"><span data-stu-id="9f195-106">Warehouse management is fully integrated with other business processes in Finance and Operations such as transportation, manufacturing, quality control, purchase, transfer, sales, and returns.</span></span>

## <a name="get-started"></a><span data-ttu-id="9f195-107">Rozpoczynanie pracy</span><span class="sxs-lookup"><span data-stu-id="9f195-107">Get started</span></span>
<span data-ttu-id="9f195-108">Aby rozpocząć pracę z modułem Zarządzanie magazynem należy dokończyć konfigurację ogólnych parametrów magazynu w celu obsługi procesów biznesowych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="9f195-108">To start working with Warehouse management, you need to complete the setup of the general warehouse parameters to support the business processes of you company.</span></span>

- <span data-ttu-id="9f195-109">Przejdź do strony **Parametry zarządzania magazynem** w obszarze **Zarządzanie magazynem** > **Konfiguracja**, aby skonfigurować ogólne parametry magazynu.</span><span class="sxs-lookup"><span data-stu-id="9f195-109">Go to the **Warehouse management parameters** page under **Warehouse management** > **Setup** to set up general warehouse parameters.</span></span>

<span data-ttu-id="9f195-110">Należy skonfigurować składniki dla przychodzących i wychodzących przepływów pracy procesów magazynowych zgodnie z wymaganiami biznesowymi.</span><span class="sxs-lookup"><span data-stu-id="9f195-110">You must configure components for inbound and outbound warehouse process workflows according to business requirements.</span></span> <span data-ttu-id="9f195-111">Najważniejsze składniki, które należy skonfigurować to szablony grupy czynności, szablony pracy, pule pracy i dyrektywy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="9f195-111">The most important components that you must configure are wave templates, work templates, work pools, and location directives.</span></span>

- [<span data-ttu-id="9f195-112">Konfiguracja magazynu</span><span class="sxs-lookup"><span data-stu-id="9f195-112">Warehouse configuration</span></span>](warehouse-configuration.md)
- [<span data-ttu-id="9f195-113">Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji</span><span class="sxs-lookup"><span data-stu-id="9f195-113">Control warehouse work by using work templates and location directives</span></span>](control-warehouse-location-directives.md)
- [<span data-ttu-id="9f195-114">Konfigurowanie urządzeń przenośnych do pracy magazynowej</span><span class="sxs-lookup"><span data-stu-id="9f195-114">Set up mobile devices for warehouse work</span></span>](configure-mobile-devices-warehouse.md)
- [<span data-ttu-id="9f195-115">Konfigurowanie dyrektywy lokalizacji dla odłożenia zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="9f195-115">Set up a location directive for purchase order put-away</span></span>](../transportation/tasks/set-up-location-directive-purchase-order-put-away.md)
- [<span data-ttu-id="9f195-116">Konfigurowanie szablonu pracy dla zamówień zakupu</span><span class="sxs-lookup"><span data-stu-id="9f195-116">Set up a work template for purchase orders</span></span>](./tasks/set-up-work-template-purchase-orders.md)

## <a name="warehouse-management-processes"></a><span data-ttu-id="9f195-117">Procesy zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="9f195-117">Warehouse management processes</span></span>
- <span data-ttu-id="9f195-118">Zintegrowana obsługa dokumentów źródłowych dla zamówień sprzedaży, zwrotów, zamówień przeniesienia, zamówień produkcji i kanban</span><span class="sxs-lookup"><span data-stu-id="9f195-118">Integrated support for source documents for sales orders, returns, transfer orders, production orders, and kanban</span></span>  
- <span data-ttu-id="9f195-119">Elastyczna obsługa procesów roboczych materiałów przychodzących i wychodzących na podstawie kwerend</span><span class="sxs-lookup"><span data-stu-id="9f195-119">Flexible, inbound and outbound material workflow support based on queries</span></span>
- <span data-ttu-id="9f195-120">Pełna integracja z ofertami produkcji i transportu</span><span class="sxs-lookup"><span data-stu-id="9f195-120">Full integration with the Manufacturing and Transportation offerings</span></span>
- <span data-ttu-id="9f195-121">Pełna kontrola limitów składowania w lokalizacji i danych wolumetrycznych lokalizacji</span><span class="sxs-lookup"><span data-stu-id="9f195-121">Full control of location stocking limits and location volumetrics</span></span>
- <span data-ttu-id="9f195-122">Właściwości zapasów kontrolowane przez stan zapasów</span><span class="sxs-lookup"><span data-stu-id="9f195-122">Inventory properties controlled by inventory status</span></span>
- <span data-ttu-id="9f195-123">Pełna obsługa partii i pozycji seryjnych</span><span class="sxs-lookup"><span data-stu-id="9f195-123">Full batch and serial item support</span></span>
- <span data-ttu-id="9f195-124">Różne funkcje odbioru towarów</span><span class="sxs-lookup"><span data-stu-id="9f195-124">Various item receiving capabilities</span></span>
- <span data-ttu-id="9f195-125">Wiele strategii pobierania</span><span class="sxs-lookup"><span data-stu-id="9f195-125">Multiple picking strategies</span></span>
- <span data-ttu-id="9f195-126">Obsługa nowej generacji skanerów kodów kreskowych od razu po rozpoczęciu pracy</span><span class="sxs-lookup"><span data-stu-id="9f195-126">Out-of-the-box support for the next generation of barcode scanners</span></span>
- <span data-ttu-id="9f195-127">Typy palet/kontenerów dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="9f195-127">Pallet/container types for warehouse processes</span></span>
- <span data-ttu-id="9f195-128">Zaawansowane funkcje liczenia</span><span class="sxs-lookup"><span data-stu-id="9f195-128">Advanced counting capabilities</span></span>
- <span data-ttu-id="9f195-129">Drukowanie etykiet i marszruta etykiet z obsługą języka Zebra ZPL</span><span class="sxs-lookup"><span data-stu-id="9f195-129">Label printing and label routing with Zebra ZPL support</span></span>
- <span data-ttu-id="9f195-130">Integracja analizy biznesowej z usługą Power BI</span><span class="sxs-lookup"><span data-stu-id="9f195-130">Business intelligence integration into Power BI</span></span>
- <span data-ttu-id="9f195-131">Ręczne i automatyczne przesuwanie zapasów</span><span class="sxs-lookup"><span data-stu-id="9f195-131">Manual and automatic movement of inventory</span></span>
- <span data-ttu-id="9f195-132">W pełni zintegrowana kontrola jakości (QMS)</span><span class="sxs-lookup"><span data-stu-id="9f195-132">Fully-integrated quality control (QMS)</span></span>
- <span data-ttu-id="9f195-133">Pełne śledzenie obsługi materiałów przez pracowników</span><span class="sxs-lookup"><span data-stu-id="9f195-133">Full traceability of workers' material handling</span></span>
- <span data-ttu-id="9f195-134">Przetwarzanie wychodzących grup czynności</span><span class="sxs-lookup"><span data-stu-id="9f195-134">Outbound wave processing</span></span>
- <span data-ttu-id="9f195-135">Obsługa ręcznego pakowania i automatycznej konteneryzacji</span><span class="sxs-lookup"><span data-stu-id="9f195-135">Manual packing and automatic containerization support</span></span>
- <span data-ttu-id="9f195-136">Wybór grupy</span><span class="sxs-lookup"><span data-stu-id="9f195-136">Cluster picking</span></span>
- <span data-ttu-id="9f195-137">Prosty przeładunek kompletacyjny</span><span class="sxs-lookup"><span data-stu-id="9f195-137">Simple cross docking</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f195-138">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9f195-138">Additional resources</span></span>
### <a name="whats-new-and-in-development"></a><span data-ttu-id="9f195-139">Nowe i opracowywane funkcje</span><span class="sxs-lookup"><span data-stu-id="9f195-139">What's new and in development</span></span>
<span data-ttu-id="9f195-140">Przejdź na stronę [Plan rozwoju usługi Microsoft Dynamics 365](https://roadmap.dynamics.com/), aby zobaczyć, jakie nowe funkcje zostały wydane, a jakie są jeszcze opracowywane.</span><span class="sxs-lookup"><span data-stu-id="9f195-140">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span>

### <a name="blogs"></a><span data-ttu-id="9f195-141">Blogi</span><span class="sxs-lookup"><span data-stu-id="9f195-141">Blogs</span></span>
<span data-ttu-id="9f195-142">Opinie, wiadomości i inne informacje dotyczące modułu Zarządzanie magazynem możesz znaleźć w [blogu usługi Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog).</span><span class="sxs-lookup"><span data-stu-id="9f195-142">You can find opinions, news, and other information about Warehouse management and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog).</span></span>


 


