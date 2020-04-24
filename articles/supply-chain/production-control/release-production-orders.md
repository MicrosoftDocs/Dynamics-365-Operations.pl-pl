---
title: Zwalnianie zleceń produkcyjnych
description: Zwolnione zlecenie produkcyjne to zlecenie zatwierdzone do produkcji. Określenie „zwolnione” opisuje stan w cyklu życia zlecenia produkcyjnego, gdzie jest ono dostępne do wykonania na wydziale produkcji i dla procesów magazynowych.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc6d53fc87bac2e23c0d1e67954be02749042004
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211245"
---
# <a name="release-production-orders"></a><span data-ttu-id="f9361-104">Zwalnianie zleceń produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="f9361-104">Release production orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9361-105">Zwolnione zlecenie produkcyjne to zlecenie zatwierdzone do produkcji.</span><span class="sxs-lookup"><span data-stu-id="f9361-105">A released production order is an order that has been authorized for production.</span></span> <span data-ttu-id="f9361-106">Określenie „zwolnione” opisuje stan w cyklu życia zlecenia produkcyjnego, gdzie jest ono dostępne do wykonania na wydziale produkcji i dla procesów magazynowych.</span><span class="sxs-lookup"><span data-stu-id="f9361-106">The term Released is used to describe a state in the production order life cycle, where the production order is available for execution on the production shop floor and for warehouse processes.</span></span> 

<a name="characteristics-of-the-released-state"></a><span data-ttu-id="f9361-107">Właściwości stanu Zwolnione</span><span class="sxs-lookup"><span data-stu-id="f9361-107">Characteristics of the Released state</span></span>
-------------------------------------

<span data-ttu-id="f9361-108">Stan **Zwolnione** jest stanem jednego cyklu życia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="f9361-108">The **Released** state is one state in the production order life cycle.</span></span> <span data-ttu-id="f9361-109">Zlecenia produkcyjne ze stanem **Zwolnione** są dostępne do wykonania w wydziale produkcji oraz dla procesów magazynowych.</span><span class="sxs-lookup"><span data-stu-id="f9361-109">Production orders that are in the **Released** state are available for execution on the production shop floor and for warehouse processes.</span></span> <span data-ttu-id="f9361-110">Stan **Zwolnione** posiada następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="f9361-110">The **Released** state has the following characteristics:</span></span>

-   <span data-ttu-id="f9361-111">Stan zlecenia produkcyjnego może zostać zmieniony na **Zwolnione** ze zlecenia produkcyjnego lub za pomocą produkcji seryjnej.</span><span class="sxs-lookup"><span data-stu-id="f9361-111">A production order can be changed to the **Released** state either from the production order or by using a batch process.</span></span> <span data-ttu-id="f9361-112">Zlecenie produkcyjne można także aktualizować automatycznie z planowanych zleceń produkcyjnych, które będą ustalane w polu **Horyzont czasowy akceptacji** na stronie **planu głównego**.</span><span class="sxs-lookup"><span data-stu-id="f9361-112">The production order can also be updated automatically from planned production orders that are firmed by using the **Firming time fence** field on the **Master plan** page.</span></span>
-   <span data-ttu-id="f9361-113">Stan **Zwolnione** jest sygnałem dla operatorów do rozpoczęcia wykonywania zadań produkcyjnych w wydziale produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="f9361-113">The **Released** state is the signal for the shop floor operators (operators) to start executing the production jobs on the shop floor.</span></span>
-   <span data-ttu-id="f9361-114">Dokumenty produkcji, takie jak karty marszruty i karty zadań zawierają informacje o zadaniach produkcji i mogą być wystawiane.</span><span class="sxs-lookup"><span data-stu-id="f9361-114">Production papers, such as route cards, route jobs, and jobs cards provide information about production jobs and can be issued.</span></span>
-   <span data-ttu-id="f9361-115">W przypadku materiałów fizycznie zarezerwowanych generowana jest praca w magazynie w celu pobrania materiałów koniecznych do realizacji zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="f9361-115">For materials that are physically reserved, warehouse work is generated to pick materials for the production order.</span></span>

## <a name="releasing-jobs-to-the-shop-floor"></a><span data-ttu-id="f9361-116">Zwalnianie zadań do wydziału produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="f9361-116">Releasing jobs to the shop floor</span></span>
<span data-ttu-id="f9361-117">Po zwolnieniu zlecenia produkcyjnego, zadania produkcji, które są związane z zamówieniem, są widoczne i gotowe do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="f9361-117">After a production order is released, production jobs that are related to the order are visible and ready for registration.</span></span> <span data-ttu-id="f9361-118">Operatorzy wprowadzają rejestracje zadań, takie jak Rozpoczęcie, Zatrzymanie i Zakończenie, na stronie **Terminal kart zadań** lub **Urządzenia karty zadań**.</span><span class="sxs-lookup"><span data-stu-id="f9361-118">The operators can make job registrations, such as Start, Stop, and Completion, on either the **Job card terminal** page or the **Job card device** page.</span></span> <span data-ttu-id="f9361-119">Zarejestrowany czas i ilości są automatycznie przenoszone ze stron rejestracji do arkuszy produkcji w celu śledzenia zużycia czasu i ilości.</span><span class="sxs-lookup"><span data-stu-id="f9361-119">The registered time and quantity are automatically transferred from the registration pages to production journals to keep track of the consumed time and quantity.</span></span>

## <a name="route-cards"></a><span data-ttu-id="f9361-120">Karty marszrut</span><span class="sxs-lookup"><span data-stu-id="f9361-120">Route cards</span></span>
<span data-ttu-id="f9361-121">Karta marszrut zawiera przegląd informacji z konfiguracji marszruty i operacji oraz z metod planowania operacji i zadania.</span><span class="sxs-lookup"><span data-stu-id="f9361-121">A route card provides an overview of information that comes from route and operation setups, and from operation and job scheduling methods.</span></span>

## <a name="route-jobs"></a><span data-ttu-id="f9361-122">Zadania marszruty</span><span class="sxs-lookup"><span data-stu-id="f9361-122">Route jobs</span></span>
<span data-ttu-id="f9361-123">W zadaniu marszruty są wymienione wraz ze szczegółami wszystkie zadania w ramach operacji, a także jest podany czas konfiguracji, procesu, oczekiwania i czas transportu.</span><span class="sxs-lookup"><span data-stu-id="f9361-123">A route job lists each job of an operation in detail, and includes setup, process, queue, and transportation times.</span></span> <span data-ttu-id="f9361-124">Na przykład operacja malowania może się składać z kilku pojedynczych zadań – przygotowania, wykonywania pracy (czyli malowania) i czas oczekiwania (na wyschnięcie pomalowanej powierzchni).</span><span class="sxs-lookup"><span data-stu-id="f9361-124">For example, an operation such as painting might require individual jobs, such as setup time, run time for the painting process, and queue time for drying.</span></span>

## <a name="job-cards"></a><span data-ttu-id="f9361-125">Karty zadania</span><span class="sxs-lookup"><span data-stu-id="f9361-125">Job cards</span></span>
<span data-ttu-id="f9361-126">W karcie zadania są wymienione numery poszczególnych zadań w ramach określonej operacji.</span><span class="sxs-lookup"><span data-stu-id="f9361-126">A job card lists the individual job numbers of a particular operation.</span></span> <span data-ttu-id="f9361-127">Jedno zadanie pojawia się na każdej stronie.</span><span class="sxs-lookup"><span data-stu-id="f9361-127">One job appears on each page.</span></span> <span data-ttu-id="f9361-128">Zadania znajdujące się na karcie zadania, a także szacunkowe czasy tych zadań są podawane na podstawie informacji konfiguracyjnych marszruty i operacji.</span><span class="sxs-lookup"><span data-stu-id="f9361-128">The jobs that are included on a job card, and their estimated times, come from the route and operation setup information.</span></span> <span data-ttu-id="f9361-129">Za pomocą karty zadań można otworzyć stronę **Wiersze arkusza produkcji**, **karta zadań**.</span><span class="sxs-lookup"><span data-stu-id="f9361-129">From a job card, you can open the **Production journal lines**, **job card** page.</span></span> <span data-ttu-id="f9361-130">Osoby, które pracują w gniazdach produkcyjnych, mogą dostarczać informacji zwrotnych dotyczących procesu produkcji.</span><span class="sxs-lookup"><span data-stu-id="f9361-130">People who run operations resources can provide feedback about the production process.</span></span> <span data-ttu-id="f9361-131">W tych polach można wprowadzać dane statystyczne zużycia oraz informacje o niewłaściwych ilościach.</span><span class="sxs-lookup"><span data-stu-id="f9361-131">There are fields where you can enter consumption statistics and information such as the error quantity.</span></span>

## <a name="warehouse-work-for-raw-material-picking"></a><span data-ttu-id="f9361-132">Praca magazynu dla pobrania surowca.</span><span class="sxs-lookup"><span data-stu-id="f9361-132">Warehouse work for raw material picking</span></span>
<span data-ttu-id="f9361-133">Praca pobrania surowca jest generowana podczas zwalniania.</span><span class="sxs-lookup"><span data-stu-id="f9361-133">Work for raw material picking is generated during release.</span></span> <span data-ttu-id="f9361-134">Praca jest generowana tylko dla ilości materiałów fizycznie zarezerwowanej dla zlecenia produkcyjnego przed zwolnieniem zlecenia.</span><span class="sxs-lookup"><span data-stu-id="f9361-134">Work is generated only for the quantity of materials that was physically reserved for the production order before the order was released.</span></span> <span data-ttu-id="f9361-135">Do wygenerowania pracy magazynu dla pobrania surowca konieczna jest następująca konfiguracja:</span><span class="sxs-lookup"><span data-stu-id="f9361-135">The following setup is required to generate warehouse work for raw material picking:</span></span>

-   <span data-ttu-id="f9361-136">Dyrektywa lokalizacji dla pobrania surowca, która określa lokalizację pobrania surowca</span><span class="sxs-lookup"><span data-stu-id="f9361-136">A location directive for raw materials picking that determines which warehouse location to pick the materials in</span></span>
-   <span data-ttu-id="f9361-137">Szablon grupy czynności dla surowców, w którym skonfigurowano zasady wykonania pracy w magazynie</span><span class="sxs-lookup"><span data-stu-id="f9361-137">A wave template for raw materials, where policies for the execution of warehouse work are configured</span></span>
-   <span data-ttu-id="f9361-138">Lokalizacja wejściowa produkcji, która określa umieszczenie materiałów</span><span class="sxs-lookup"><span data-stu-id="f9361-138">A production input location that determines where materials are put</span></span>




