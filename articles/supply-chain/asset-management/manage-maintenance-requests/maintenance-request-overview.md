---
title: Żądania konserwacji
description: Ten temat stanowi omówienie zarządzania żądaniami konserwacji w module Zarządzanie składnikami majątku
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 56d4abee451e6e22b9b9cc2fd36a13648202e7df
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847443"
---
# <a name="maintenance-requests"></a><span data-ttu-id="81900-103">Żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="81900-103">Maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="81900-104">Żądania konserwacji to notatki lub deklaracje utworzone w celu powiadamiania menedżera lub planisty, że składnik majątku może wymagać zadania konserwacji lub naprawy, ale bez tworzenia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="81900-104">Maintenance requests are notes or declarations that are created to notify a manager or planner that an asset might require a maintenance or repair job, but without creating a work order.</span></span> <span data-ttu-id="81900-105">Jeśli zawartość żądania konserwacji zostanie zweryfikowana i jej ważność zostanie potwierdzona, można następnie utworzyć zlecenie pracy na podstawie żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-105">If the contents of a maintenance request are considered valid, a work order can then be created based on the maintenance request.</span></span>

<span data-ttu-id="81900-106">Żądania konserwacji mogą być tworzone dla dowolnego składnika majątku w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="81900-106">Maintenance requests can be created for any asset in Asset Management.</span></span> <span data-ttu-id="81900-107">Różne typy żądań konserwacji mogą być tworzone w zależności od tego, jak firma używa żądań konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-107">Various types of maintenance requests can be created, depending on how your company uses maintenance requests.</span></span> <span data-ttu-id="81900-108">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="81900-108">Here are some examples:</span></span>

- <span data-ttu-id="81900-109">Żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="81900-109">Maintenance requests</span></span>
- <span data-ttu-id="81900-110">Notatki</span><span class="sxs-lookup"><span data-stu-id="81900-110">Notes</span></span>
- <span data-ttu-id="81900-111">Korekty lub ulepszenia</span><span class="sxs-lookup"><span data-stu-id="81900-111">Corrections or enhancements</span></span>
- <span data-ttu-id="81900-112">Inwestycje</span><span class="sxs-lookup"><span data-stu-id="81900-112">Investments</span></span>
- <span data-ttu-id="81900-113">Naprawa w magazynie (ten typ jest używany w przypadku odbierania składnika majątku z innej lokalizacji, dzięki czemu można wykonać zadanie konserwacji lub naprawy, a następnie zwrócić składnik majątku po ukończeniu zadania).</span><span class="sxs-lookup"><span data-stu-id="81900-113">Depot repair (This type is used when you receive assets from another location so that you can do a maintenance or repair job, and you then return the asset after the job is completed.)</span></span>

## <a name="view-maintenance-requests"></a><span data-ttu-id="81900-114">Przeglądanie żądań konserwacji</span><span class="sxs-lookup"><span data-stu-id="81900-114">View maintenance requests</span></span>

<span data-ttu-id="81900-115">Aby wyświetlić żądania konserwacji, wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Wszystkie żądania konserwacji**, **Aktywne żądania konserwacji** lub **Żądania konserwacji w moich lokalizacjach czynności konserwacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="81900-115">To view maintenance requests, select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests**, **Active maintenance requests**, or **My functional location maintenance requests**.</span></span> <span data-ttu-id="81900-116">Każda strona listy pokazuje wybrane informacje związane z żądaniem konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-116">Each list page shows some of the information that is related to a maintenance request.</span></span>

![Rysunek 1](media/01-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="81900-118">Strona listy **Moje żądania konserwacji obsługi lokalizacji czynności konserwacyjnych** służy do wyświetlania listy żądań konserwacji, które zawierają lokalizacje czynności konserwacyjnych, które są powiązane z pracownikiem lub składnikami majątku zainstalowanymi w lokalizacjach czynności konserwacyjnych, które są związane z pracownikiem.</span><span class="sxs-lookup"><span data-stu-id="81900-118">Use the **My functional location maintenance requests** list page to view a list of maintenance requests that contain either functional locations that you're related to as a worker or assets that are installed on functional locations that you're related to as a worker.</span></span> <span data-ttu-id="81900-119">(Aby uzyskać informacje na temat konfiguracji lokalizacji czynności konserwacyjnych w odniesieniu do konserwatorów, zobacz temat [Konserwatorzy i grupy pracowników](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="81900-119">(For information about how to set up functional locations on maintenance workers, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).)</span></span>
> 
> <span data-ttu-id="81900-120">Mimo że informacje o koncie odbiorcy są dostępne w zarządzaniu usługami składników majątku (konserwacja zewnętrzna), nie jest możliwe w module Zarządzanie składnikami majątku (konserwacja wewnętrzna).</span><span class="sxs-lookup"><span data-stu-id="81900-120">Although customer account information is available in Asset Service Management (external maintenance), it isn't available in Asset Management (internal maintenance).</span></span>

<span data-ttu-id="81900-121">Aby otworzyć widok szczegółów rekordu, na stronie listy **Wszystkie żądania konserwacji** w widoku siatki wybierz łącze w kolumnie **Żądanie konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="81900-121">To open the details view of a record, on the **All maintenance requests** list page, in the grid view, select a link in the **Maintenance request** column.</span></span>

![Rysunek 2](media/02-manage-maintenance-requests.png)

<span data-ttu-id="81900-123">Przyciski w okienku akcji są zorganizowane na kartach.</span><span class="sxs-lookup"><span data-stu-id="81900-123">The buttons on the Action Pane are organized on tabs.</span></span> <span data-ttu-id="81900-124">Poniższa tabela zawiera krótkie opisy przycisków związanych z zarządzaniem składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="81900-124">The following table briefly describes the buttons that are related to Asset Management.</span></span>

| <span data-ttu-id="81900-125">Nazwa przycisku</span><span class="sxs-lookup"><span data-stu-id="81900-125">Button name</span></span>                      | <span data-ttu-id="81900-126">Opis</span><span class="sxs-lookup"><span data-stu-id="81900-126">Description</span></span> |
|----------------------------------|-------------|
| <span data-ttu-id="81900-127">Edycja</span><span class="sxs-lookup"><span data-stu-id="81900-127">Edit</span></span>                             | <span data-ttu-id="81900-128">Edytuj wybrane żądanie konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-128">Edit the selected maintenance request.</span></span> |
| <span data-ttu-id="81900-129">Nowy element</span><span class="sxs-lookup"><span data-stu-id="81900-129">New</span></span>                              | <span data-ttu-id="81900-130">Utwórz nowe żądanie konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-130">Create a new maintenance request.</span></span> |
| <span data-ttu-id="81900-131">Usuwanie</span><span class="sxs-lookup"><span data-stu-id="81900-131">Delete</span></span>                           | <span data-ttu-id="81900-132">Usuwanie wybranego żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-132">Delete the selected maintenance request.</span></span> |
| <span data-ttu-id="81900-133">Pula zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="81900-133">Work order pool</span></span>                  | <span data-ttu-id="81900-134">Połącz wybrane żądanie konserwacji z pulą zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="81900-134">Connect the selected maintenance request to a work order pool.</span></span> |
| <span data-ttu-id="81900-135">Zlecenie pracy</span><span class="sxs-lookup"><span data-stu-id="81900-135">Work order</span></span>                       | <span data-ttu-id="81900-136">Utwórz zlecenie pracy na podstawie wybranego żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-136">Create a work order, based on the selected maintenance request.</span></span> |
| <span data-ttu-id="81900-137">Usterka składnika majątku</span><span class="sxs-lookup"><span data-stu-id="81900-137">Asset fault</span></span>                      | <span data-ttu-id="81900-138">Kliknij **Usterki składników majątku**, gdzie można utworzyć rejestracje usterek na wybranym żądaniu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-138">Click **Asset faults**, where you can create a fault registration on the selected maintenance request.</span></span> |
| <span data-ttu-id="81900-139">Zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="81900-139">Work orders</span></span>                      | <span data-ttu-id="81900-140">Pokaż listę wszystkich zleceń pracy, które są podłączone do wybranego żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-140">Show a list of all work orders that are connected to the selected maintenance request.</span></span> |
| <span data-ttu-id="81900-141">Aktualizuj stan żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="81900-141">Update maintenance request state</span></span> | <span data-ttu-id="81900-142">Aktualizuj stan żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-142">Update the maintenance request state.</span></span> |
| <span data-ttu-id="81900-143">Dziennik stanu cyklu życia</span><span class="sxs-lookup"><span data-stu-id="81900-143">Lifecycle state log</span></span>              | <span data-ttu-id="81900-144">Wyświetl dziennik pokazujący stany cyklu życia wybranego żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-144">View a log that shows the lifecycle states of the selected maintenance request.</span></span> |
| <span data-ttu-id="81900-145">Szczegóły żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="81900-145">Maintenance request details</span></span>      | <span data-ttu-id="81900-146">Wydrukuj raport pokazujący szczegóły wybranego żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-146">Print a report that shows details of the selected maintenance request.</span></span> |
| <span data-ttu-id="81900-147">Wyślij użyczony składnik majątku</span><span class="sxs-lookup"><span data-stu-id="81900-147">Send loan asset</span></span>                  | <span data-ttu-id="81900-148">Wybierz użyczony składnik majątku, który powinien być tymczasowy zamiennikiem składnika majątku wybranego w wybranym żądaniu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="81900-148">Select a loan asset that should be a temporary replacement for the asset that is selected on the selected maintenance request.</span></span> |
| <span data-ttu-id="81900-149">Zwróć użyczony składnik majątku</span><span class="sxs-lookup"><span data-stu-id="81900-149">Return loan asset</span></span>                | <span data-ttu-id="81900-150">Zarejestruj użyczony składnik majątku jako zwrócony.</span><span class="sxs-lookup"><span data-stu-id="81900-150">Register the loan asset as returned.</span></span> |

