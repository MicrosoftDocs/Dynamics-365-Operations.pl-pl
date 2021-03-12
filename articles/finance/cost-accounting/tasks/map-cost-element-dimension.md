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
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5570d7cf2a8139d7959cb708d306e8b91065ed1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990674"
---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="09f34-103">Mapowanie wymiaru składnika kosztu</span><span class="sxs-lookup"><span data-stu-id="09f34-103">Map a cost element dimension</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="09f34-104">Kontroler kosztów może za pomocą tej procedury zamapować wymiar składników kosztów na wymiar składników kosztów w firmie MXMF.</span><span class="sxs-lookup"><span data-stu-id="09f34-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="09f34-105">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="09f34-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="09f34-106">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="09f34-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="09f34-107">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="09f34-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="09f34-108">W tym przykładzie wybierz opcję Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="09f34-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="09f34-109">Kliknij opcję Mapowania wymiarów.</span><span class="sxs-lookup"><span data-stu-id="09f34-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="09f34-110">Kliknij opcję Konfiguruj mapowania z tego wymiaru.</span><span class="sxs-lookup"><span data-stu-id="09f34-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="09f34-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="09f34-111">Click New.</span></span>
6. <span data-ttu-id="09f34-112">W polu Wymiar docelowy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="09f34-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="09f34-113">W tym przykładzie wybierz opcję MXMF Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="09f34-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="09f34-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="09f34-114">Click New.</span></span>
8. <span data-ttu-id="09f34-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="09f34-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="09f34-116">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="09f34-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="09f34-117">W tym przykładzie wybierz element członkowski wymiaru 606400 Wydatki na telefon i faks.</span><span class="sxs-lookup"><span data-stu-id="09f34-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="09f34-118">W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="09f34-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="09f34-119">W tym przykładzie wybierz element członkowski wymiaru 6001004 Telefon.</span><span class="sxs-lookup"><span data-stu-id="09f34-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="09f34-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="09f34-120">Click Save.</span></span>

