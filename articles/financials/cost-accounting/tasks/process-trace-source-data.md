---
title: Przetwarzanie i śledzenie danych źródłowych
description: Całe przetwarzanie danych jest wykonywane przez zadania.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
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
ms.openlocfilehash: e476416420875ba0f2401cf251d34977ae84b8f5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546531"
---
# <a name="process-and-trace-source-data"></a><span data-ttu-id="ba81d-103">Przetwarzanie i śledzenie danych źródłowych</span><span class="sxs-lookup"><span data-stu-id="ba81d-103">Process and trace source data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ba81d-104">Całe przetwarzanie danych jest wykonywane przez zadania.</span><span class="sxs-lookup"><span data-stu-id="ba81d-104">All data processing is run by jobs.</span></span> <span data-ttu-id="ba81d-105">Dla każdego zadania i dostawcy danych jest tworzony arkusz w celu udokumentowania, że proces został wykonany, a wpisy zostały przetworzone w bieżącym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="ba81d-105">For each job and data provider, a journal is created to document that the process has been run, and that the entries were processed in the current job.</span></span> <span data-ttu-id="ba81d-106">Ta procedura umożliwia skonfigurowanie źródła danych, a następnie śledzenie pochodzenia źródła określonego wpisu kosztu.</span><span class="sxs-lookup"><span data-stu-id="ba81d-106">Use this procedure to set up a data source and then  trace the origin of a specific cost entry.</span></span> <span data-ttu-id="ba81d-107">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="ba81d-107">This recording uses the USP2 demo data company USP2.</span></span> <span data-ttu-id="ba81d-108">Przed wykonaniem tego zadania koniecznie odtwórz następujące przewodniki po zadaniach „Tworzenie księgi rachunku kosztów”, „Definiowanie jednostek kontroli kosztów” i „Zarządzanie źródłem danych księgi rachunku kosztów”.</span><span class="sxs-lookup"><span data-stu-id="ba81d-108">Before you complete this task, make sure that you play the following task guides: "Create a cost accounting ledger," "Define cost control units," and "Manage data source for the cost accounting ledger."</span></span>

1. <span data-ttu-id="ba81d-109">Wybierz kolejno opcje Rachunek kosztów > Ustawienia księgi > Księgi rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="ba81d-109">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="ba81d-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ba81d-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ba81d-111">Wybierz utworzoną wcześniej księgę rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="ba81d-111">Select the cost accounting ledger that you created earlier.</span></span>  
3. <span data-ttu-id="ba81d-112">Kliknij opcję Wersje rzeczywiste.</span><span class="sxs-lookup"><span data-stu-id="ba81d-112">Click Actual versions.</span></span>
4. <span data-ttu-id="ba81d-113">W okienku akcji kliknij opcję Przetwarzanie danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="ba81d-113">On the Action Pane, click Source data processing.</span></span>
5. <span data-ttu-id="ba81d-114">Kliknij opcję Arkusze przeniesień zapisów księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="ba81d-114">Click General ledger entry transfer journals.</span></span>
6. <span data-ttu-id="ba81d-115">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ba81d-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="ba81d-116">Kliknij opcję Wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="ba81d-116">Click Journal entries.</span></span>
8. <span data-ttu-id="ba81d-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ba81d-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="ba81d-118">Kliknij opcję Wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="ba81d-118">Click Cost entries.</span></span>
10. <span data-ttu-id="ba81d-119">Kliknij opcję Wpis źródłowy.</span><span class="sxs-lookup"><span data-stu-id="ba81d-119">Click Source entry.</span></span>
11. <span data-ttu-id="ba81d-120">W okienku akcji kliknij opcję Przetwarzanie danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="ba81d-120">On the Action Pane, click Source data processing.</span></span>
12. <span data-ttu-id="ba81d-121">Kliknij opcję Księga główna.</span><span class="sxs-lookup"><span data-stu-id="ba81d-121">Click General ledger.</span></span>
13. <span data-ttu-id="ba81d-122">W polu Okres kalendarza obrachunkowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba81d-122">In the Fiscal calendar period field, enter or select a value.</span></span>
    * <span data-ttu-id="ba81d-123">W tym przykładzie wybierz opcję Obrachunkowy 2017 Okres 9.</span><span class="sxs-lookup"><span data-stu-id="ba81d-123">For this example, select Fiscal 2017 Period 9.</span></span>  
14. <span data-ttu-id="ba81d-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ba81d-124">Click OK.</span></span>

