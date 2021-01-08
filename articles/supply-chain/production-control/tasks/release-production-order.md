---
title: Wydawanie zlecenia produkcyjnego
description: W tej procedurze pokazano sposób zwalniania zlecenia produkcyjnego.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: beef850e7e58fb58db545c0be5990b52619070d3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434919"
---
# <a name="release-a-production-order"></a><span data-ttu-id="ee5ec-103">Wydawanie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="ee5ec-103">Release a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ee5ec-104">W tej procedurze pokazano sposób zwalniania zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-104">This procedure shows how to release a production order.</span></span> <span data-ttu-id="ee5ec-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ee5ec-106">Jest to czwarta z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-106">This is the fourth procedure out of seven which explains the production order lifecycle.</span></span>

1. <span data-ttu-id="ee5ec-107">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-107">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="ee5ec-108">W siatce zaznacz zlecenie produkcyjne, które ma stan Zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-108">In the grid, select a production order that has the Scheduled status.</span></span>  
2. <span data-ttu-id="ee5ec-109">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-109">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="ee5ec-110">Kliknij opcję Zwolnienie.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-110">Click Release.</span></span>
    * <span data-ttu-id="ee5ec-111">Na tej stronie można potwierdzić zwolnienie wybranego zakresu zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-111">On this page, you can confirm the release of the selected range of production orders.</span></span> <span data-ttu-id="ee5ec-112">Aby dodać zamówienia, kliknij przycisk Wybierz.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-112">Click Select if you want to add orders.</span></span>  
    * <span data-ttu-id="ee5ec-113">Krok Zwolnienie wskazuje, kiedy zlecenia produkcyjne jest zwalniane do wydziału produkcji, tak aby operatorzy na produkcji mogli informować o postępie zadań produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-113">The Release step indicates when the production order is released to the production shop floor so that the shop floor operators can report progress on the production jobs.</span></span> <span data-ttu-id="ee5ec-114">Mogą być wystawiane dokumenty produkcyjne zawierające istotne informacje o realizacji zadań.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-114">Production papers that contain relevant information about processing the jobs can be issued.</span></span> <span data-ttu-id="ee5ec-115">Praca magazynowa dotycząca pobrania surowca jest generowana dla towarów, które są skonfigurowane dla procesu magazynowego.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-115">The warehouse work for raw material picking is generated for the items that are set up for the warehouse process.</span></span>  
4. <span data-ttu-id="ee5ec-116">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-116">Click the General tab.</span></span>
    * <span data-ttu-id="ee5ec-117">Wybierz raporty o produkcji, które mają być drukowane.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-117">Select which production reports should be printed.</span></span> <span data-ttu-id="ee5ec-118">Raport Karta zadań drukuje stronę dla każdego zadania zaplanowanego i wymaga zaplanowania zlecenia produkcyjnego na poziomie zadania.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-118">The Job card report prints a page for each scheduled job and requires the production order to be scheduled at the job level.</span></span> <span data-ttu-id="ee5ec-119">Raport zawiera informacje o zaplanowanych godzinach rozpoczęcia i zakończenia, ilości do wyprodukowania oraz o zasobach, które będą realizowały zadanie.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-119">The report contains information about the scheduled start and end time, the quantity to produce, and which resource processes the job.</span></span> <span data-ttu-id="ee5ec-120">Raport Zadanie marszruty zbiera te same informacje na tej samej stronie, ale nie drukuje strony dla każdego zadania.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-120">The Route job report collects the same information on the same page, but does not print a page for each job.</span></span> <span data-ttu-id="ee5ec-121">Raport Karta marszruty pokazuje tylko operacje, bez zadań.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-121">The Route card report only shows the operations but not the jobs.</span></span> <span data-ttu-id="ee5ec-122">Dlatego ten raport nie wymaga planowania zadań, ale może być używany podczas planowania zleceń produkcyjnych na poziomie operacji.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-122">Therefore, this report does not require job scheduling, but can be used when production orders are scheduled at the operation level.</span></span>  
5. <span data-ttu-id="ee5ec-123">Zaznacz pole wyboru Drukowanie karty marszruty.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-123">Click the Print route card checkbox.</span></span>
6. <span data-ttu-id="ee5ec-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-124">Click OK.</span></span>
7. <span data-ttu-id="ee5ec-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ee5ec-125">Close the page.</span></span>

