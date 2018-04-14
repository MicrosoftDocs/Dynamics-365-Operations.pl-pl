--- 
title: "Mapowanie wymiaru składnika kosztu"
description: "Kontroler kosztów może za pomocą tej procedury zamapować wymiar składników kosztów na wymiar składników kosztów w firmie MXMF."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 52497aa2c67e852b366a39058d4cbf7597f1bd4a
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="5bfee-103">Mapowanie wymiaru składnika kosztu</span><span class="sxs-lookup"><span data-stu-id="5bfee-103">Map a cost element dimension</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5bfee-104">Kontroler kosztów może za pomocą tej procedury zamapować wymiar składników kosztów na wymiar składników kosztów w firmie MXMF.</span><span class="sxs-lookup"><span data-stu-id="5bfee-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="5bfee-105">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="5bfee-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="5bfee-106">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="5bfee-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="5bfee-107">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5bfee-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5bfee-108">W tym przykładzie wybierz opcję Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="5bfee-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="5bfee-109">Kliknij opcję Mapowania wymiarów.</span><span class="sxs-lookup"><span data-stu-id="5bfee-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="5bfee-110">Kliknij opcję Konfiguruj mapowania z tego wymiaru.</span><span class="sxs-lookup"><span data-stu-id="5bfee-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="5bfee-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5bfee-111">Click New.</span></span>
6. <span data-ttu-id="5bfee-112">W polu Wymiar docelowy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5bfee-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="5bfee-113">W tym przykładzie wybierz opcję MXMF Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="5bfee-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="5bfee-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5bfee-114">Click New.</span></span>
8. <span data-ttu-id="5bfee-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="5bfee-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="5bfee-116">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5bfee-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5bfee-117">W tym przykładzie wybierz element członkowski wymiaru 606400 Wydatki na telefon i faks.</span><span class="sxs-lookup"><span data-stu-id="5bfee-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="5bfee-118">W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5bfee-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5bfee-119">W tym przykładzie wybierz element członkowski wymiaru 6001004 Telefon.</span><span class="sxs-lookup"><span data-stu-id="5bfee-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="5bfee-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5bfee-120">Click Save.</span></span>


