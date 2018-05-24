---
title: Tworzenie relacji zadania serwisowego
description: "Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0892161605401420c0817b3b644271357446a99b
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-task-relations"></a><span data-ttu-id="4635d-103">Tworzenie relacji zadania serwisowego</span><span class="sxs-lookup"><span data-stu-id="4635d-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4635d-104">Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia.</span><span class="sxs-lookup"><span data-stu-id="4635d-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="4635d-105">Te informacje są dostępne dla serwisantów i klientów.</span><span class="sxs-lookup"><span data-stu-id="4635d-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="4635d-106">Tworzenie relacji z umową serwisową</span><span class="sxs-lookup"><span data-stu-id="4635d-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="4635d-107">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="4635d-107">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="4635d-108">Wybierz istniejącą umowę serwisową lub utwórz nową.</span><span class="sxs-lookup"><span data-stu-id="4635d-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="4635d-109">W okienku akcji kliknij przycisk **Zadania serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="4635d-109">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="4635d-110">W formularzu **Zadania serwisowe** naciśnij kombinację klawiszy CTRL+N, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="4635d-110">On the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="4635d-111">Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="4635d-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="4635d-112">Zamknij formularz, aby zapisać rekord.</span><span class="sxs-lookup"><span data-stu-id="4635d-112">Close the form to save the record.</span></span>

<span data-ttu-id="4635d-113">Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="4635d-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="4635d-114">Pozwala to na określenie zadań serwisowych w dołączonych wierszach umowy.</span><span class="sxs-lookup"><span data-stu-id="4635d-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="4635d-115">Relacja zadań serwisowych utworzona dla umowy serwisowej jest dostępna z poziomu wszystkich zleceń serwisowych dołączonych do umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="4635d-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="4635d-116">Tworzenie relacji ze zleceniem serwisowym</span><span class="sxs-lookup"><span data-stu-id="4635d-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="4635d-117">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="4635d-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="4635d-118">Wybierz istniejące zlecenie serwisowe lub utwórz nowe.</span><span class="sxs-lookup"><span data-stu-id="4635d-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="4635d-119">W okienku akcji kliknij przycisk **Zadania serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="4635d-119">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="4635d-120">W formularzu **Zadania serwisowe** naciśnij kombinację klawiszy CTRL+N, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="4635d-120">From the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="4635d-121">Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="4635d-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="4635d-122">Zamknij formularz, aby zapisać rekord.</span><span class="sxs-lookup"><span data-stu-id="4635d-122">Close the form to save the record.</span></span>

<span data-ttu-id="4635d-123">Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="4635d-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="4635d-124">Pozwala to na wybranie zadania serwisowego, dla którego utworzono relację podczas tworzenia wierszy zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="4635d-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="4635d-125">Relacje zadań serwisowych tworzone dla zlecenia serwisowego są dostępne z poziomu określonego zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="4635d-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="4635d-126">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4635d-126">See also</span></span>

[<span data-ttu-id="4635d-127">Zadania serwisowe </span><span class="sxs-lookup"><span data-stu-id="4635d-127">Service tasks</span></span>](service-tasks.md)


  



