---
title: Integracja z programem Microsoft Dynamics 365 for Field Service
description: "Ten temat zawiera omówienie integracji z programem Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a57e23691a6b4d48c6b8dd6d1f61fc9730365b39
ms.openlocfilehash: 0c1268d2fddcf7b28ecfc3197f21e9d30a5a5855
ms.contentlocale: pl-pl
ms.lasthandoff: 05/31/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a><span data-ttu-id="2685c-103">Integracja z programem Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="2685c-103">Integration with Microsoft Dynamics 365 for Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2685c-104">Program Microsoft Dynamics 365 for Finance and Operations umożliwia synchronizowanie procesów biznesowych między programami Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="2685c-104">Microsoft Dynamics 365 for Finance and Operations enables synchronization of business processes between Finance and Operations and Microsoft Dynamics 365 for Field Service.</span></span> <span data-ttu-id="2685c-105">Scenariusze integracji konfiguruje się przy użyciu rozszerzalnych szablonów integratora danych oraz usługi Common Data Service (CDS), co umożliwia synchronizowanie procesów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="2685c-105">The integration scenarios are configured by using extensible Data integrator templates and the Common Data Service (CDS) to enable the synchronization of business processes.</span></span>

<span data-ttu-id="2685c-106">[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="2685c-106">[![Synchronization of business processes between Finance and Operations and Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span></span>

<span data-ttu-id="2685c-107">Pierwsza faza integracji między programami Field Service i Finance and Operations skupia się na umożliwieniu fakturowania zleceń pracy i umów z programu Field Service w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2685c-107">The first phase  of the integration between Field Service and Finance and Operations is focused on enabling work orders and agreements in Field Service to be invoiced in Finance and Operations.</span></span> <span data-ttu-id="2685c-108">Obsługiwany przepływ rozpoczyna się w programie Field Service, gdzie informacje ze zleceń pracy są synchronizowane z programem Finance and Operations jako zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2685c-108">The supported flow starts in Field Service, where information from work orders is synchronized to Finance and Operations as sales orders.</span></span> <span data-ttu-id="2685c-109">W programie Finance and Operations zamówienia sprzedaży są fakturowane w celu wygenerowania dokumentów faktur.</span><span class="sxs-lookup"><span data-stu-id="2685c-109">In Finance and Operations, the sales orders are invoiced to generate invoice documents.</span></span> <span data-ttu-id="2685c-110">Ponadto informacje z faktur za umowy w programie Field Service są synchronizowane z programem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2685c-110">In addition, the information from Field Service agreement invoices is synchronized to Finance and Operations.</span></span> <span data-ttu-id="2685c-111">Integrator danych programu Microsoft Dynamics 365 synchronizuje dane przy użyciu konfigurowalnych projektów.</span><span class="sxs-lookup"><span data-stu-id="2685c-111">The Microsoft Dynamics 365 Data integrator synchronizes data by using customizable projects.</span></span> <span data-ttu-id="2685c-112">Można używać standardowych szablonów do tworzenia niestandardowych projektów integracji, gdzie dodatkowe pola standardowe i niestandardowe, a także jednostki, mogą być mapowane w celu skorygowania integracji i spełnienia określonych wymagań.</span><span class="sxs-lookup"><span data-stu-id="2685c-112">Standard templates can be used to create custom integration projects where additional standard and custom fields, and also entities, can be mapped to adjust the integration and meet specific requirements.</span></span>

<span data-ttu-id="2685c-113">Pierwsza faza integracji między programami Field Service i Finance and Operations umożliwia synchronizowanie następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="2685c-113">The first phase of the integration between Field Service and Finance and Operations enables synchronization of the following items:</span></span>

- [<span data-ttu-id="2685c-114">Produkty w programie Finance and Operations z produktami w programie Field Service zawierającymi informacje o typach produktów</span><span class="sxs-lookup"><span data-stu-id="2685c-114">Products in Finance and Operations to products in Field Service that include Product Type information</span></span>](field-service-product.md)
- [<span data-ttu-id="2685c-115">Zlecenia pracy w rozwiązaniu Field Service z zamówieniami sprzedaży w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2685c-115">Work orders in Field Service to sales orders in Finance and Operations</span></span>](field-service-work-order.md)
- [<span data-ttu-id="2685c-116">Faktury w programie Field Service z fakturami niezależnymi w programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2685c-116">Invoices in Field Service to free text invoices in Finance and Operations</span></span>](field-service-invoice.md)

<span data-ttu-id="2685c-117">Aby zobaczyć przykład jak synchronizować zlecenie produkcyjne między Field Service a Finance and Operations, zobacz krótki film w serwisie YouTube [Synchronizowanie zlecenia produkcyjnego między Dynamics 365 for Field Service a Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span><span class="sxs-lookup"><span data-stu-id="2685c-117">To see an example of how you can synchronize a work order between Field Service and Finance and Operations, watch the short YouTube video [Synchronize a work order between Dynamics 365 for Field Service and Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span></span>

[![](https://img.youtube.com/vi/hAB4TDVMjxU/0.jpg)](https://www.youtube.com/watch?v=hAB4TDVMjxU)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="2685c-118">Wymagania systemowe dla rozwiązania Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2685c-118">System requirements for Finance and Operations</span></span>
<span data-ttu-id="2685c-119">Program Field Service można integrować z następującymi wersjami:</span><span class="sxs-lookup"><span data-stu-id="2685c-119">Field Service integration supports the following versions:</span></span>

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a><span data-ttu-id="2685c-120">Dynamics 365 for Finance and Operations w wersji 8.0 (kwiecień 2018) i nowszych</span><span class="sxs-lookup"><span data-stu-id="2685c-120">Dynamics 365 for Finance and Operations version 8.0 (April 2018) or later</span></span>

- <span data-ttu-id="2685c-121">Program Dynamics 365 for Finance and Operations w wersji 8.0 (kwiecień 2018) został wydany w kwietniu 2018 r. i ma numer kompilacji aplikacji 8.0.30.8020 oraz aktualizację Platform Update 15 (7.0.4841.35234).</span><span class="sxs-lookup"><span data-stu-id="2685c-121">Dynamics 365 for Finance and Operations version 8.0 (April 2018) was released in April 2018 and has an application build number 8.0.30.8020 with Platform Update 15 (7.0.4841.35234).</span></span> 

## <a name="system-requirements-for-field-service"></a><span data-ttu-id="2685c-122">Wymagania systemowe programu Field Service</span><span class="sxs-lookup"><span data-stu-id="2685c-122">System requirements for Field Service</span></span>
<span data-ttu-id="2685c-123">Aby korzystać z rozwiązania integracyjnego Field Service, należy zainstalować następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="2685c-123">To use the Field Service integration solution, you must install the following components:</span></span>

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a><span data-ttu-id="2685c-124">Microsoft Dynamics 365 for Field Service 9.0 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="2685c-124">Microsoft Dynamics 365 for Field Service 9.0 or later</span></span>

- <span data-ttu-id="2685c-125">Dynamics 365 for Field Service wersja 1612 (9.0.1.733) (DB 9.0.1.733) online lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="2685c-125">Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) online or a later version.</span></span>
- <span data-ttu-id="2685c-126">Rozwiązanie Prospekt na gotówkę (P2C) dla programu Dynamics 365, wersja 1.15.0.1 lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="2685c-126">Prospect to Cash (P2C) solution for Dynamics 365, version 1.15.0.1 or a later version.</span></span> <span data-ttu-id="2685c-127">To rozwiązanie jest dostępne do pobrania z usługi [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="2685c-127">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
- <span data-ttu-id="2685c-128">Rozwiązanie integracyjne Field Service dla programu Dynamics 365, wersja 1.0.0.0 lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="2685c-128">Field Service integration solution for Dynamics 365, version 1.0.0.0 or a later version.</span></span> <span data-ttu-id="2685c-129">To rozwiązanie jest dostępne do pobrania z usługi [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span><span class="sxs-lookup"><span data-stu-id="2685c-129">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span></span>

