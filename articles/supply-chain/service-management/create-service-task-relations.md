---
title: Tworzenie relacji zadania serwisowego
description: Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e50b4322c65097ab4f8aba9c36e4d5e6cc4c01b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435346"
---
# <a name="create-service-task-relations"></a><span data-ttu-id="e7fa3-103">Tworzenie relacji zadania serwisowego</span><span class="sxs-lookup"><span data-stu-id="e7fa3-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7fa3-104">Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="e7fa3-105">Te informacje są dostępne dla serwisantów i klientów.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="e7fa3-106">Tworzenie relacji z umową serwisową</span><span class="sxs-lookup"><span data-stu-id="e7fa3-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="e7fa3-107">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-107">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="e7fa3-108">Wybierz istniejącą umowę serwisową lub utwórz nową.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="e7fa3-109">W okienku akcji kliknij przycisk **Zadania serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-109">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="e7fa3-110">W formularzu **Zadania serwisowe** naciśnij kombinację klawiszy CTRL+N, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-110">On the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="e7fa3-111">Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="e7fa3-112">Zamknij formularz, aby zapisać rekord.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-112">Close the form to save the record.</span></span>

<span data-ttu-id="e7fa3-113">Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="e7fa3-114">Pozwala to na określenie zadań serwisowych w dołączonych wierszach umowy.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="e7fa3-115">Relacja zadań serwisowych utworzona dla umowy serwisowej jest dostępna z poziomu wszystkich zleceń serwisowych dołączonych do umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="e7fa3-116">Tworzenie relacji ze zleceniem serwisowym</span><span class="sxs-lookup"><span data-stu-id="e7fa3-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="e7fa3-117">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="e7fa3-118">Wybierz istniejące zlecenie serwisowe lub utwórz nowe.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="e7fa3-119">W okienku akcji kliknij przycisk **Zadania serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-119">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="e7fa3-120">W formularzu **Zadania serwisowe** naciśnij kombinację klawiszy CTRL+N, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-120">From the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="e7fa3-121">Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="e7fa3-122">Zamknij formularz, aby zapisać rekord.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-122">Close the form to save the record.</span></span>

<span data-ttu-id="e7fa3-123">Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="e7fa3-124">Pozwala to na wybranie zadania serwisowego, dla którego utworzono relację podczas tworzenia wierszy zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="e7fa3-125">Relacje zadań serwisowych tworzone dla zlecenia serwisowego są dostępne z poziomu określonego zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e7fa3-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7fa3-126">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e7fa3-126">See also</span></span>

[<span data-ttu-id="e7fa3-127">Omówienie zadań serwisowych</span><span class="sxs-lookup"><span data-stu-id="e7fa3-127">Service tasks overview</span></span>](service-tasks.md)


  


