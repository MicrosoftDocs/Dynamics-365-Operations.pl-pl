---
title: Zarządzanie transportem — omówienie
description: W tym temacie omówiono funkcjonalność zarządzania transportem dostępną w programie Microsoft Dynamics 365 for Finance and Operations.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 918167a3ab72b3d3665cf710d8e509417b94a056
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561180"
---
# <a name="transportation-management-overview"></a><span data-ttu-id="54ab6-103">Zarządzanie transportem — omówienie</span><span class="sxs-lookup"><span data-stu-id="54ab6-103">Transportation management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="54ab6-104">W tym temacie omówiono funkcjonalność zarządzania transportem dostępną w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="54ab6-104">This topic gives an overview of the transportation management functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="54ab6-105">Moduł Zarządzanie transportem pozwala korzystać z transportu w firmie oraz identyfikować dostawców i rozwiązania wyboru trasy dla zamówień przychodzących i wychodzących.</span><span class="sxs-lookup"><span data-stu-id="54ab6-105">Transportation management lets you use your company’s transportation, and also lets you identify vendor and routing solutions for inbound and outbound orders.</span></span> <span data-ttu-id="54ab6-106">Można na przykład określić najszybszą trasę lub najtańszą stawkę za wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="54ab6-106">For example, you can identify the fastest route or the least expensive rate for a shipment.</span></span> <span data-ttu-id="54ab6-107">W poniższej tabeli opisano główne scenariusze używania zarządzania transportem w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="54ab6-107">The following table describes the main scenarios for using Transportation management in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54ab6-108">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="54ab6-108">Scenario</span></span></th>
<th><span data-ttu-id="54ab6-109">Jak może pomóc moduł Zarządzanie transportem</span><span class="sxs-lookup"><span data-stu-id="54ab6-109">How Transportation management can help</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="54ab6-110">Korzystanie z zewnętrznych operatorów logistycznych do obsługi transportu.</span><span class="sxs-lookup"><span data-stu-id="54ab6-110">Use external logistics providers for transportation activities.</span></span></td>
<td><span data-ttu-id="54ab6-111">Modułu zarządzania transportem można używać do obsługi transportu przychodzącego i/lub wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="54ab6-111">Use Transportation management for inbound and/or outbound transportation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="54ab6-112">Własna flota firmy jest dostępna do obsługi dostaw/odbiorów, a opłaty za dostawę są przenoszone na odbiorców.</span><span class="sxs-lookup"><span data-stu-id="54ab6-112">The company&#39;s own fleet is available for delivery/pickup, and delivery charges are passed on to customers.</span></span></td>
<td><span data-ttu-id="54ab6-113">W procesach transportu wychodzącego moduł Zarządzanie transportu może służyć do obliczania opłat transportowych i przenoszenia ich na odbiorców.</span><span class="sxs-lookup"><span data-stu-id="54ab6-113">For the outbound processes, you can use Transportation management to determine the transportation charges and pass them on to customers.</span></span> <span data-ttu-id="54ab6-114">Nie jest przy tym konieczny proces uzgadniania faktur z przewoźnikiem.</span><span class="sxs-lookup"><span data-stu-id="54ab6-114">However, the carrier invoice reconciliation process isn&#39;t required.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="54ab6-115">Własna flota firmy jest dostępna do obsługi dostaw/odbiorów, ale opłaty za dostawę nie są przenoszone na odbiorców, ponieważ koszt transportu jest zawarty w cenie produktu.</span><span class="sxs-lookup"><span data-stu-id="54ab6-115">The company&#39;s own fleet is available for delivery/pickup, but delivery charges aren&#39;t passed on to customers, because product prices include transportation.</span></span></td>
<td><span data-ttu-id="54ab6-116">Wiele funkcji zarządzania transportem nie jest potrzebnych.</span><span class="sxs-lookup"><span data-stu-id="54ab6-116">A lot of the Transportation management functionality isn&#39;t required.</span></span> <span data-ttu-id="54ab6-117">Można jednak za pomocą tego modułu obliczać stawki transportowe i odpowiednio korygować ceny sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="54ab6-117">However, you can use Transportation management to determine the transportation rates and adjust the sales price accordingly.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="54ab6-118">Usługi logistyczne są świadczone przez inną firmę w tej samej organizacji.</span><span class="sxs-lookup"><span data-stu-id="54ab6-118">Logistics service is provided by another legal entity in the same company.</span></span></td>
<td><ul>
<li><span data-ttu-id="54ab6-119">Można używać modułu Zarządzanie transportem, traktując tę firmę jak każdego innego przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="54ab6-119">You can use Transportation management by treating the other legal entity like any other shipping carrier.</span></span> <span data-ttu-id="54ab6-120">Nie można zautomatyzować transakcji ekonomicznych między wewnętrznymi firmami.</span><span class="sxs-lookup"><span data-stu-id="54ab6-120">You can&#39;t automate the economic transactions between legal entities.</span></span> <span data-ttu-id="54ab6-121">W związku z tym należy obsługiwać te transakcje ręcznie (na przykład przez tworzenie zamówień zakupu).</span><span class="sxs-lookup"><span data-stu-id="54ab6-121">Therefore, you must handle these transactions manually (for example, by creating a purchase order).</span></span></li>
<li><span data-ttu-id="54ab6-122">W firmie świadczącej usługi logistyczne moduł zarządzania transportem może służyć do obliczania stawek transportowych.</span><span class="sxs-lookup"><span data-stu-id="54ab6-122">In the legal entity that provides the logistics services, Transportation management can be used to determine transportation rates.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-finance-and-operations"></a><span data-ttu-id="54ab6-123">Planowanie transportu w programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="54ab6-123">Planning transportation in Finance and Operations</span></span>
<span data-ttu-id="54ab6-124">W module Zarządzanie transportem planowania transportu może być oparte na zamówieniach lub na wysyłkach tworzonych w oparciu o te zamówienia.</span><span class="sxs-lookup"><span data-stu-id="54ab6-124">In Transportation management, transportation planning can be based either on orders or on the shipments that are created based on those orders.</span></span> <span data-ttu-id="54ab6-125">Wysyłki zawsze się pojawiają w pewnym momencie, ale nie są wymagane do planowania transportu.</span><span class="sxs-lookup"><span data-stu-id="54ab6-125">The shipments always exist at some point in time but aren't required for transportation planning.</span></span> <span data-ttu-id="54ab6-126">Zamówienia przeniesienia są częścią scenariusza transportu wychodzącego i mogą być planowane razem z zamówieniami sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="54ab6-126">Transfer orders are part of the outbound scenario and can be planned together with sales orders.</span></span> 

![Rysunek ładunku](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a><span data-ttu-id="54ab6-128">Transport przychodzący</span><span class="sxs-lookup"><span data-stu-id="54ab6-128">Inbound transportation</span></span>
<span data-ttu-id="54ab6-129">Gdy zamawiasz towary od dostawcy i muszą one zostać dostarczone do Twojego magazynu, można samodzielnie zorganizować transport.</span><span class="sxs-lookup"><span data-stu-id="54ab6-129">When you order items from a vendor, and the items must be delivered to your warehouse, you might want to arrange the transport of the items yourself.</span></span> <span data-ttu-id="54ab6-130">Program Finance and Operations umożliwia zaplanowanie transportu i przyjęcia przychodzącego ładunku.</span><span class="sxs-lookup"><span data-stu-id="54ab6-130">You can use Finance and Operations to plan the transportation and receipt of the inbound load.</span></span> <span data-ttu-id="54ab6-131">Poniższy rysunek przedstawia przepływ procesu biznesowego dla planowania transportu towarów przychodzących.</span><span class="sxs-lookup"><span data-stu-id="54ab6-131">The following illustration shows the business process flow for planning transportation for an inbound load.</span></span> 

![Przebieg procesu biznesowego przychodzącego transportu ładunku](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a><span data-ttu-id="54ab6-133">Transport wychodzący</span><span class="sxs-lookup"><span data-stu-id="54ab6-133">Outbound transportation</span></span>
<span data-ttu-id="54ab6-134">Można planować i przetwarzać ładunki wychodzące w celu wysłania określonych towarów z magazynu firmy do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="54ab6-134">You can plan and process an outbound load to ship specific items from a company’s warehouse to a customer.</span></span> <span data-ttu-id="54ab6-135">Program Finance and Operations umożliwia zaplanowanie transportu i wysyłania ładunków wychodzących.</span><span class="sxs-lookup"><span data-stu-id="54ab6-135">You can use Finance and Operations to plan the transportation and shipping of an outbound load.</span></span> <span data-ttu-id="54ab6-136">Poniższy rysunek przedstawia przepływ procesu biznesowego planowania i przetwarzania obciążenia wychodzącego dla ładunku.</span><span class="sxs-lookup"><span data-stu-id="54ab6-136">The following illustration shows the business process flow for planning and processing outbound loads for shipping.</span></span> 

![Planowanie i przetwarzania ładunków wychodzących](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a><span data-ttu-id="54ab6-138">Kompilowanie ładunku</span><span class="sxs-lookup"><span data-stu-id="54ab6-138">Load building</span></span>
<span data-ttu-id="54ab6-139">Program Finance and Operations zawiera strategię kompilowania ładunku o nazwie Strategia kompilowania ładunku na podstawie objętości.</span><span class="sxs-lookup"><span data-stu-id="54ab6-139">Finance and Operations provides a load building strategy that is named the Volume-based load building strategy.</span></span> <span data-ttu-id="54ab6-140">Pozwala ona stosować maksymalne wartości wysokości i wagi określone w szablonie ładunku albo zastępować te ustawienia wprowadzaniem nowych wartości.</span><span class="sxs-lookup"><span data-stu-id="54ab6-140">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="54ab6-141">Aby użyć tej strategii, zaznacz ją w polu **Strategia kompilowania ładunku** na skróconej karcie **Ustawienia** na karcie **Pulpit kompilowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="54ab6-141">To use this strategy, select it in the **Load building strategy** field on the **Setup** FastTab on the **Load building workbench** page.</span></span> <span data-ttu-id="54ab6-142">Ponadto można dodawać własne strategie kompilowania ładunku przez utworzenie nowej klasy w drzewie obiektów aplikacji (AOT).</span><span class="sxs-lookup"><span data-stu-id="54ab6-142">In addition, you can add your own load-building strategies by creating a new class in the Application Object Tree (AOT).</span></span>



