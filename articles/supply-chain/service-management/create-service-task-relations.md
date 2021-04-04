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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea5952376fe30f489d385c8f8295fbf86f2af085
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470744"
---
# <a name="create-service-task-relations"></a><span data-ttu-id="12fa7-103">Tworzenie relacji zadania serwisowego</span><span class="sxs-lookup"><span data-stu-id="12fa7-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12fa7-104">Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia.</span><span class="sxs-lookup"><span data-stu-id="12fa7-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="12fa7-105">Te informacje są dostępne dla serwisantów i klientów.</span><span class="sxs-lookup"><span data-stu-id="12fa7-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="12fa7-106">Tworzenie relacji z umową serwisową</span><span class="sxs-lookup"><span data-stu-id="12fa7-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="12fa7-107">Przejdź do **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="12fa7-107">Go to **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="12fa7-108">Wybierz istniejącą umowę serwisową lub utwórz nową.</span><span class="sxs-lookup"><span data-stu-id="12fa7-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="12fa7-109">W okienku akcji wybierz przycisk **Zadania serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="12fa7-109">On the Action Pane, select the **Service tasks** button.</span></span>

4.  <span data-ttu-id="12fa7-110">W formularzu **Zadania serwisowe** wybierz **Nowy**, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="12fa7-110">On the **Service tasks** form, select **New** to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="12fa7-111">Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="12fa7-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="12fa7-112">Zamknij formularz, aby zapisać rekord.</span><span class="sxs-lookup"><span data-stu-id="12fa7-112">Close the form to save the record.</span></span>

<span data-ttu-id="12fa7-113">Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="12fa7-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="12fa7-114">Pozwala to na określenie zadań serwisowych w dołączonych wierszach umowy.</span><span class="sxs-lookup"><span data-stu-id="12fa7-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="12fa7-115">Relacja zadań serwisowych utworzona dla umowy serwisowej jest dostępna z poziomu wszystkich zleceń serwisowych dołączonych do umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="12fa7-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="12fa7-116">Tworzenie relacji ze zleceniem serwisowym</span><span class="sxs-lookup"><span data-stu-id="12fa7-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="12fa7-117">Przejdź do **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="12fa7-117">Go to **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="12fa7-118">Wybierz istniejące zlecenie serwisowe lub utwórz nowe.</span><span class="sxs-lookup"><span data-stu-id="12fa7-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="12fa7-119">W okienku akcji wybierz przycisk **Zadania serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="12fa7-119">On the Action Pane, select the **Service tasks** button.</span></span>

4.  <span data-ttu-id="12fa7-120">W formularzu **Zadania serwisowe** wybierz **Nowy**, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="12fa7-120">From the **Service tasks** form, select **New** to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="12fa7-121">Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="12fa7-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="12fa7-122">Zamknij formularz, aby zapisać rekord.</span><span class="sxs-lookup"><span data-stu-id="12fa7-122">Close the form to save the record.</span></span>

<span data-ttu-id="12fa7-123">Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="12fa7-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="12fa7-124">Pozwala to na wybranie zadania serwisowego, dla którego utworzono relację podczas tworzenia wierszy zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="12fa7-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="12fa7-125">Relacje zadań serwisowych tworzone dla zlecenia serwisowego są dostępne z poziomu określonego zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="12fa7-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="12fa7-126">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="12fa7-126">See also</span></span>

[<span data-ttu-id="12fa7-127">Omówienie zadań serwisowych</span><span class="sxs-lookup"><span data-stu-id="12fa7-127">Service tasks overview</span></span>](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]