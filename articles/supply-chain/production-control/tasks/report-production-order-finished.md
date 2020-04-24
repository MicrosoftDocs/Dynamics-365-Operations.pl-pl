---
title: Zgłaszanie zlecenia produkcyjnego jako zakończonego
description: W tej procedurze pokazano sposób raportowania zlecenia produkcyjnego jako ukończonego.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: def39fa86103bc69d1c88dde8d0660945c1de82e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210555"
---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="13a38-103">Zgłaszanie zlecenia produkcyjnego jako zakończonego</span><span class="sxs-lookup"><span data-stu-id="13a38-103">Report a production order as finished</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="13a38-104">W tej procedurze pokazano sposób raportowania zlecenia produkcyjnego jako ukończonego.</span><span class="sxs-lookup"><span data-stu-id="13a38-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="13a38-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="13a38-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="13a38-106">Jest to szósta z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="13a38-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="13a38-107">Zgłaszanie zlecenia produkcyjnego jako zakończonego</span><span class="sxs-lookup"><span data-stu-id="13a38-107">Report a production order as finished</span></span>
1. <span data-ttu-id="13a38-108">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="13a38-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="13a38-109">Zaznacz zlecenie produkcyjne, które ma stan Rozpoczęto.</span><span class="sxs-lookup"><span data-stu-id="13a38-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="13a38-110">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="13a38-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="13a38-111">Po zakończeniu kliknij opcję Raport.</span><span class="sxs-lookup"><span data-stu-id="13a38-111">Click Report as finished.</span></span>
    * <span data-ttu-id="13a38-112">Na tej stronie można potwierdzić ilość ukończonego produktu, która ma zostać zgłoszona jako gotowa.</span><span class="sxs-lookup"><span data-stu-id="13a38-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="13a38-113">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="13a38-113">Click the General tab.</span></span>
5. <span data-ttu-id="13a38-114">W polu Ilość dobrych ustaw wartość „18”.</span><span class="sxs-lookup"><span data-stu-id="13a38-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="13a38-115">W polu Ilość wadliwych ustaw wartość „2”.</span><span class="sxs-lookup"><span data-stu-id="13a38-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="13a38-116">W polu Powód błędu wybierz opcję „Materiał”.</span><span class="sxs-lookup"><span data-stu-id="13a38-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="13a38-117">Zaznacz lub wyczyść pole wyboru Zakończ zadanie.</span><span class="sxs-lookup"><span data-stu-id="13a38-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="13a38-118">Zaznacz lub wyczyść pole wyboru Akceptacja błędu.</span><span class="sxs-lookup"><span data-stu-id="13a38-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="13a38-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="13a38-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="13a38-120">Weryfikowanie arkusz zgłoszonych wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="13a38-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="13a38-121">W okienku akcji kliknij pozycję Widok.</span><span class="sxs-lookup"><span data-stu-id="13a38-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="13a38-122">Kliknij opcję Zgłoszone jako gotowe.</span><span class="sxs-lookup"><span data-stu-id="13a38-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="13a38-123">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="13a38-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="13a38-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="13a38-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13a38-125">Arkusz zgłoszonych wyrobów gotowych jest księgowany.</span><span class="sxs-lookup"><span data-stu-id="13a38-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="13a38-126">Jeśli chcesz dokonać korekt w arkuszu, można ręcznie utworzyć nowy arkusz, gdzie można dokonać zmian.</span><span class="sxs-lookup"><span data-stu-id="13a38-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  

