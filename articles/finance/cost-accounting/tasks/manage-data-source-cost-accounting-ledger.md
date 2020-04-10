---
title: Zarządzanie źródłem danych księgi rachunku kosztów
description: Ta procedura służy do zarządzania źródłem danych księgi głównej dla księgi rachunku kosztów.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4cf53e905cf32557f4671477b173b1c5072d186e
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3137828"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="437f8-103">Zarządzanie źródłem danych księgi rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="437f8-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="437f8-104">Ta procedura służy do zarządzania źródłem danych księgi głównej dla księgi rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="437f8-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="437f8-105">Przed wykonaniem tego zadania koniecznie odtwórz przewodniki po zadaniach „Tworzenie księgi rachunku kosztów” i „Definiowanie jednostek kontroli kosztów”.</span><span class="sxs-lookup"><span data-stu-id="437f8-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="437f8-106">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="437f8-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="437f8-107">Wybierz kolejno opcje Rachunek kosztów > Ustawienia księgi > Księgi rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="437f8-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="437f8-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="437f8-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="437f8-109">Kliknij opcję Wersje rzeczywiste.</span><span class="sxs-lookup"><span data-stu-id="437f8-109">Click Actual versions.</span></span>
4. <span data-ttu-id="437f8-110">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="437f8-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="437f8-111">Kliknij opcję Księga główna.</span><span class="sxs-lookup"><span data-stu-id="437f8-111">Click General ledger.</span></span>
6. <span data-ttu-id="437f8-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="437f8-112">Click New.</span></span>
7. <span data-ttu-id="437f8-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="437f8-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="437f8-114">W polu Dostawca danych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="437f8-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="437f8-115">W tym przykładzie wybierz opcję Dynamics 365 Finance — zapisy księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="437f8-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="437f8-116">W polu Wymiar składnika kosztu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="437f8-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="437f8-117">W tym przykładzie wybierz opcję Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="437f8-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="437f8-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="437f8-118">Click Save.</span></span>
11. <span data-ttu-id="437f8-119">Kliknij opcję Konfiguruj dostawcę danych.</span><span class="sxs-lookup"><span data-stu-id="437f8-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="437f8-120">W polu Firma wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="437f8-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="437f8-121">W tym przykładzie wybierz USP2.</span><span class="sxs-lookup"><span data-stu-id="437f8-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="437f8-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="437f8-122">Click New.</span></span>
14. <span data-ttu-id="437f8-123">W polu Warstwa księgowania zaznacz opcję Bieżąca.</span><span class="sxs-lookup"><span data-stu-id="437f8-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="437f8-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="437f8-124">Click OK.</span></span>

