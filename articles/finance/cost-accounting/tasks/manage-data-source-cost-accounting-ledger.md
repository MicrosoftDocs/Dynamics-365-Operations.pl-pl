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
ms.search.form: CAMAXGeneralLedgerEntryProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7246d42b42404f0f1215bbf14b8ad168fe12691c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990724"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="45b81-103">Zarządzanie źródłem danych księgi rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="45b81-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="45b81-104">Ta procedura służy do zarządzania źródłem danych księgi głównej dla księgi rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="45b81-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="45b81-105">Przed wykonaniem tego zadania koniecznie odtwórz przewodniki po zadaniach „Tworzenie księgi rachunku kosztów” i „Definiowanie jednostek kontroli kosztów”.</span><span class="sxs-lookup"><span data-stu-id="45b81-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="45b81-106">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="45b81-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="45b81-107">Wybierz kolejno opcje Rachunek kosztów > Ustawienia księgi > Księgi rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="45b81-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="45b81-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="45b81-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="45b81-109">Kliknij opcję Wersje rzeczywiste.</span><span class="sxs-lookup"><span data-stu-id="45b81-109">Click Actual versions.</span></span>
4. <span data-ttu-id="45b81-110">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="45b81-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="45b81-111">Kliknij opcję Księga główna.</span><span class="sxs-lookup"><span data-stu-id="45b81-111">Click General ledger.</span></span>
6. <span data-ttu-id="45b81-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="45b81-112">Click New.</span></span>
7. <span data-ttu-id="45b81-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="45b81-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="45b81-114">W polu Dostawca danych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="45b81-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="45b81-115">W tym przykładzie wybierz opcję Dynamics 365 Finance — zapisy księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="45b81-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="45b81-116">W polu Wymiar składnika kosztu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="45b81-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="45b81-117">W tym przykładzie wybierz opcję Składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="45b81-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="45b81-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="45b81-118">Click Save.</span></span>
11. <span data-ttu-id="45b81-119">Kliknij opcję Konfiguruj dostawcę danych.</span><span class="sxs-lookup"><span data-stu-id="45b81-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="45b81-120">W polu Firma wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="45b81-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="45b81-121">W tym przykładzie wybierz USP2.</span><span class="sxs-lookup"><span data-stu-id="45b81-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="45b81-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="45b81-122">Click New.</span></span>
14. <span data-ttu-id="45b81-123">W polu Warstwa księgowania zaznacz opcję Bieżąca.</span><span class="sxs-lookup"><span data-stu-id="45b81-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="45b81-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="45b81-124">Click OK.</span></span>

