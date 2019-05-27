---
title: Mapowanie wymiaru składnika kosztu
description: Kontroler kosztów może za pomocą tej procedury zamapować wymiar składników kosztów na wymiar składników kosztów w firmie MXMF.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52b9f6a5b71349d404fe9621b58f58aab843a71f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570700"
---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="0a7a3-103">Mapowanie wymiaru składnika kosztu</span><span class="sxs-lookup"><span data-stu-id="0a7a3-103">Map a cost element dimension</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0a7a3-104">Kontroler kosztów może za pomocą tej procedury zamapować wymiar składników kosztów na wymiar składników kosztów w firmie MXMF.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="0a7a3-105">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="0a7a3-106">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="0a7a3-107">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0a7a3-108">W tym przykładzie wybierz opcję Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="0a7a3-109">Kliknij opcję Mapowania wymiarów.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="0a7a3-110">Kliknij opcję Konfiguruj mapowania z tego wymiaru.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="0a7a3-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-111">Click New.</span></span>
6. <span data-ttu-id="0a7a3-112">W polu Wymiar docelowy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="0a7a3-113">W tym przykładzie wybierz opcję MXMF Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="0a7a3-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-114">Click New.</span></span>
8. <span data-ttu-id="0a7a3-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="0a7a3-116">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="0a7a3-117">W tym przykładzie wybierz element członkowski wymiaru 606400 Wydatki na telefon i faks.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="0a7a3-118">W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="0a7a3-119">W tym przykładzie wybierz element członkowski wymiaru 6001004 Telefon.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="0a7a3-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0a7a3-120">Click Save.</span></span>

