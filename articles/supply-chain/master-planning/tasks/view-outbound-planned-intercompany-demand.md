---
title: Wyświetlanie wychodzących danych o zaplanowanym popycie międzyfirmowym
description: W tej procedurze pokazano sposób wyświetlania wszystkich zamówień planowanych, które zostaną zrealizowane przez dostawcę międzyfirmowego.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bc3addb11d77a5098e80a5826bfea289d232548
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254294"
---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="12918-103">Wyświetlanie wychodzących danych o zaplanowanym popycie międzyfirmowym</span><span class="sxs-lookup"><span data-stu-id="12918-103">View outbound planned intercompany demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="12918-104">W tej procedurze pokazano sposób wyświetlania wszystkich zamówień planowanych, które zostaną zrealizowane przez dostawcę międzyfirmowego.</span><span class="sxs-lookup"><span data-stu-id="12918-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="12918-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="12918-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="12918-106">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="12918-106">Click Master planning.</span></span>
2. <span data-ttu-id="12918-107">W polu Plan wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="12918-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="12918-108">W polu Plan zaznacz plan 10.</span><span class="sxs-lookup"><span data-stu-id="12918-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="12918-109">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="12918-109">Click Run.</span></span>
4. <span data-ttu-id="12918-110">W polu Liczba wątków wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="12918-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="12918-111">Reprezentuje liczbę równoległych wątków, które mają być używane do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="12918-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="12918-112">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="12918-112">Click OK.</span></span>
    * <span data-ttu-id="12918-113">Może to trochę potrwać.</span><span class="sxs-lookup"><span data-stu-id="12918-113">This may take a while.</span></span>  
6. <span data-ttu-id="12918-114">Kliknij opcję Zaplanowany popyt międzyfirmowy.</span><span class="sxs-lookup"><span data-stu-id="12918-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="12918-115">Kliknij opcję Wychodzące dane o zaplanowanym popycie międzyfirmowym.</span><span class="sxs-lookup"><span data-stu-id="12918-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="12918-116">Ta strona zawiera przegląd całego zaplanowanego zapotrzebowanie, które zostanie zaspokojone przez dostawcę w wewnętrznym łańcuchu dostaw.</span><span class="sxs-lookup"><span data-stu-id="12918-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="12918-117">Rozwiń sekcję Szczegóły dotyczące popytu przesyłane od odbiorcy do dostawcy.</span><span class="sxs-lookup"><span data-stu-id="12918-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="12918-118">W tej sekcji można zobaczyć szczegóły dotyczące sposobu zaspokojenia popytu.</span><span class="sxs-lookup"><span data-stu-id="12918-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="12918-119">Zanim zobaczysz tutaj dodatkowe informacje, należy poczekać na wykonanie planowania głównego w firmie dostarczającej.</span><span class="sxs-lookup"><span data-stu-id="12918-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]