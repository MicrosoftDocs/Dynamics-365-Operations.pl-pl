---
title: Odwołanie operacji zamówienia w punkcie sprzedaży
description: W tym temacie objaśniono możliwości funkcji dostępnych w przypadku ulepszonych stron wycofywania zamówień w punkcie sprzedaży.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 41944fb7819b5527f6bc023a60acd9450d9e43c2
ms.sourcegitcommit: 25909c6ad3616e4f75a2fe006057dda18d7cc856
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "3974845"
---
# <a name="recall-order-operation-in-pos"></a><span data-ttu-id="15459-103">Odwołanie operacji zamówienia w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="15459-103">Recall order operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="15459-104">Operacja odwoływania zamówienia w punkcie sprzedaży (POS) programu Commerce oferuje zaktualizowane wyszukiwanie i filtrowanie zamówień oraz informacji właściwych dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="15459-104">The Recall order operation in the Commerce point of sale (POS) provides updated order search and filtering features and order-specific information.</span></span> <span data-ttu-id="15459-105">Ta funkcja jest dostępna w Commerce w wersjach 10.0.15 i nowszej.</span><span class="sxs-lookup"><span data-stu-id="15459-105">This feature is available in Commerce versions 10.0.15 and later.</span></span>

<span data-ttu-id="15459-106">Aby włączyć tę funkcję, należy włączyć opcję **Ulepszona operacja odwoływania zamówienia w punkcie sprzedaży** w obszarze roboczym **Zarządzanie funkcjami** w module Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="15459-106">To enable this functionality, turn the **Improved Recall order operation in POS** feature on in **Feature management** workspace in Commerce headquarters.</span></span> <span data-ttu-id="15459-107">Po włączeniu tej funkcji należy rozważyć aktualizację [układów ekranu](pos-screen-layouts.md) w punkcie sprzedaży, aby korzystać z niektórych zmienionych możliwości.</span><span class="sxs-lookup"><span data-stu-id="15459-107">After you enable the feature, consider updating your [screen layouts](pos-screen-layouts.md) in POS to take advantage of some of the changed  capabilities.</span></span>

<span data-ttu-id="15459-108">Konfiguracja przycisku operacji **Odwołanie zamówienia** pozwala organizacjom na wdrożenie operacji na wstępnie zdefiniowanym ekranie.</span><span class="sxs-lookup"><span data-stu-id="15459-108">The configuration of the **Recall order** operation button allows organizations to deploy the operation with a pre-defined display.</span></span>

![Konfiguracja siatki przycisków](media/recallorderbuttongrid.png)

<span data-ttu-id="15459-110">Opcje wyświetlania opisano poniżej.</span><span class="sxs-lookup"><span data-stu-id="15459-110">The display options are as follows.</span></span>
- <span data-ttu-id="15459-111">**Brak** — ta opcja powoduje wdrożenie operacji bez określonego ekranu.</span><span class="sxs-lookup"><span data-stu-id="15459-111">**None** – This option deploys the operation with no specific display.</span></span> <span data-ttu-id="15459-112">Gdy użytkownik otworzy operację z tą konfiguracją, zostanie wyświetlony monit o wyszukanie i znalezienie zamówień lub wybrania wstępnie zdefiniowanego filtru zamówień.</span><span class="sxs-lookup"><span data-stu-id="15459-112">When a user opens the operation with this configuration, they will be prompted to search and find orders or choose from a pre-defined order filter.</span></span>
- <span data-ttu-id="15459-113">**Zamówienia do realizacji** — gdy użytkownik uruchomi operację, zostanie ona automatycznie uruchomiona w celu przeszukania i wyświetlenia listy zamówień, które mają być zrealizowane przez sklep.</span><span class="sxs-lookup"><span data-stu-id="15459-113">**Orders to fulfill** – When a user launches the operation, a query will run automatically to search and display a list of orders that are to be fulfilled by the store.</span></span> <span data-ttu-id="15459-114">Zamówienia te są konfigurowane do odbioru w sklepie lub wysyłki do sklepu, a wiersze tych zamówień nie zostały jeszcze pobrane ani zapakowane.</span><span class="sxs-lookup"><span data-stu-id="15459-114">These orders are configured for in-store pickup or store shipment and the lines of these orders have not yet been picked or packed.</span></span>
- <span data-ttu-id="15459-115">**Zamówienia do odbioru** — gdy użytkownik uruchomi operację, automatycznie zostanie wykonane zapytanie w celu przeszukania i wyświetlenia listy zamówień, które są skonfigurowane do odbioru w bieżącym sklepie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="15459-115">**Orders to pick up** – When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for in-store pickup at the user's current store.</span></span>
- <span data-ttu-id="15459-116">**Zamówienia do wysyłki** — gdy użytkownik uruchomi operację, automatycznie zostanie wykonane zapytanie w celu przeszukania i wyświetlenia listy zamówień, które są skonfigurowane do wysyłki z bieżącego sklepu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="15459-116">**Orders to ship** - When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for shipment from the user's current store.</span></span>

<span data-ttu-id="15459-117">W przypadku uruchamiania operacji **Odwołanie zamówienia** z punktu sprzedaży, jeśli opcję wyświetlania skonfigurowano na **Brak**, użytkownik będzie mógł wyszukiwać i pobierać zamówienia w jeden z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="15459-117">When launching the **Recall order** operation from POS, if the display is configured to **None**, a user will be able to search and retrieve orders in one of the following ways.</span></span>
- <span data-ttu-id="15459-118">Skanowanie kodów kreskowych zamówień.</span><span class="sxs-lookup"><span data-stu-id="15459-118">Scan order barcodes.</span></span> <span data-ttu-id="15459-119">Spowoduje to wyszukanie pól numeru zamówienia, odwołanie do kanału i identyfikatora odbioru pod kątem dopasowań.</span><span class="sxs-lookup"><span data-stu-id="15459-119">This will search order number, channel reference, and receipt ID fields for matches.</span></span>
- <span data-ttu-id="15459-120">Wybierz ikonę **Wyszukaj zamówienia** lub **Wyszukaj i filtruj** na AppBar, aby zastosować mechanizm filtrowania do lokalizowania zamówień spełniających kryteria filtru.</span><span class="sxs-lookup"><span data-stu-id="15459-120">Select **Search orders** or **Search and filter** icon on the AppBar to use the filtering mechanism to locate orders that meet the filter criteria.</span></span>
- <span data-ttu-id="15459-121">Umożliwia wybranie wstępnie zdefiniowanego filtru z menu rozwijanego **Pokaż zamówienia** (zamówienia do zrealizowania, zamówienia do odbioru lub zamówienia do wysłania).</span><span class="sxs-lookup"><span data-stu-id="15459-121">Choose from a pre-defined filter from the **Show Orders** drop-down menu (orders to fulfill, orders to pick up, or orders to ship).</span></span>

![RecallOrderMainMenu](media/recallordermain.png)

<span data-ttu-id="15459-123">Po zastosowaniu kryteriów wyszukiwania w aplikacji zostanie wyświetlona lista pasujących zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="15459-123">After search criteria are applied, the application will display a list of matching sales orders.</span></span>

![RecallOrderDetail](media/orderrecalldetail.png)

<span data-ttu-id="15459-125">Użytkownik może wybrać zamówienie z listy, aby wyświetlić dodatkowe szczegóły.</span><span class="sxs-lookup"><span data-stu-id="15459-125">A user can select an order on the list to view additional details.</span></span> <span data-ttu-id="15459-126">Panel informacji po prawej stronie ekranu zawiera informacje dotyczące wybranego zamówienia, w tym szczegóły wiersza zamówienia, szczegóły dotyczące dostawy i szczegóły dotyczące realizacji.</span><span class="sxs-lookup"><span data-stu-id="15459-126">The information panel on the right side of the screen displays specifics on the selected order, including order line details, delivery details, and fulfillment details.</span></span>

<span data-ttu-id="15459-127">W AppBar użytkownik może wybrać operację.</span><span class="sxs-lookup"><span data-stu-id="15459-127">From the AppBar, a user can select an operation.</span></span> <span data-ttu-id="15459-128">Niektóre operacje mogą nie być włączane w zależności od stanu zamówienia.</span><span class="sxs-lookup"><span data-stu-id="15459-128">Depending on the status of the order, certain operations may not be enabled.</span></span>

- <span data-ttu-id="15459-129">**Zwrot** — powoduje wykonanie zwrotu dla co najmniej jednej faktury powiązanej z wybranym zamówieniem odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="15459-129">**Return** – Executes a return for one or more invoices related to the selected customer order.</span></span>

- <span data-ttu-id="15459-130">**Anuluj** — powoduje wygenerowanie pełnego anulowania wybranego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="15459-130">**Cancel** – Issue a full cancellation of the selected sales order.</span></span>

- <span data-ttu-id="15459-131">**Zrealizuj** — przenosi użytkownika na stronę realizacji zamówienia, która zostanie wstępnie przefiltrowana pod kątem wybranego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="15459-131">**Fulfill** – Transfers the user to the order fulfillment page, which will be pre-filtered for the selected order.</span></span> <span data-ttu-id="15459-132">Zostaną wyświetlone tylko wiersze zamówienia otwarte do realizacji przez sklep użytkownika dla wybranego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="15459-132">Only order lines that are open for fulfillment by the user's store for the selected order will be displayed.</span></span>

- <span data-ttu-id="15459-133">**Edycja** — pozwala użytkownikom na wprowadzanie zmian w wybranym zamówieniu odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="15459-133">**Edit** – Allows users to make changes to the selected customer order.</span></span>

- <span data-ttu-id="15459-134">**Odbiór** — powoduje uruchomienie przepływu odbioru umożliwiającego użytkownikowi wybranie produktów, które mają zostać pobrane, i utworzenie transakcji pobrania sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="15459-134">**Pick up** – Launches the pickup flow, which allows the user to choose the products to be picked up and creates the pickup sales transaction.</span></span>
