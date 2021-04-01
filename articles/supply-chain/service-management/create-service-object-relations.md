---
title: Tworzenie relacji przedmiotów serwisu
description: W tym temacie opisano sposób tworzenia relacji przedmiotów serwisu dla umowy serwisowej i zlecenia serwisowego.
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
ms.openlocfilehash: 44ca8920619ff4b0ae45293c997a8c385cfbd091
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234904"
---
# <a name="create-service-object-relations"></a><span data-ttu-id="f919b-103">Tworzenie relacji przedmiotów serwisu</span><span class="sxs-lookup"><span data-stu-id="f919b-103">Create service object relations</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f919b-104">W tym temacie opisano sposób tworzenia relacji przedmiotów serwisu dla umowy serwisowej i zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="f919b-104">This topic describes how to create service object relations for a service agreement and a service order.</span></span> <span data-ttu-id="f919b-105">Podczas tworzenia relacji przedmiotów serwisu przedmiot serwisu jest łączony z umową serwisową lub zleceniem serwisowym.</span><span class="sxs-lookup"><span data-stu-id="f919b-105">When you a create service object relation, you associate the service object to a service agreement or service order.</span></span> <span data-ttu-id="f919b-106">Gdy klient zażąda usługi dotyczącej pozycji, która jest przedmiotem serwisu, możesz wybrać przedmiot serwisu z listy relacji przedmiotów serwisu.</span><span class="sxs-lookup"><span data-stu-id="f919b-106">When a customer requests service for an item that is a service object, you can select the service object from the list of service object relations.</span></span>

## <a name="create-a-service-object-relation-for-a-service-agreement"></a><span data-ttu-id="f919b-107">Tworzenie relacji przedmiotów serwisu dla umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="f919b-107">Create a service object relation for a service agreement</span></span>

<span data-ttu-id="f919b-108">Aby utworzyć relację przedmiotów serwisu dla umowy serwisowej, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="f919b-108">Use the following steps to create a service object relation for a service agreement:</span></span>

1.  <span data-ttu-id="f919b-109">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="f919b-109">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="f919b-110">Z listy **Umowy serwisowe** wybierz istniejącą umowę serwisową lub kliknij opcję **Nowy**, aby utworzyć nową umowę serwisową.</span><span class="sxs-lookup"><span data-stu-id="f919b-110">In the **Service agreements** list, select an existing service agreement, or click **New** to create a new service agreement.</span></span>

3.  <span data-ttu-id="f919b-111">W formularzu **Umowy serwisowe** w **okienku akcji** na karcie **Umowa serwisowa** w grupie **Relacje** kliknij opcję **Przedmioty serwisu**.</span><span class="sxs-lookup"><span data-stu-id="f919b-111">In the **Service agreements** form, on the **Action Pane**, on the **Service agreement** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="f919b-112">W formularzu **Przedmioty serwisu** kliknij opcję **Nowy**, a następnie wybierz przedmiot serwisu dla tej umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="f919b-112">In the **Service objects** form, click **New**, and then select a service object for this service agreement.</span></span>

5.  <span data-ttu-id="f919b-113">Aby przypisać szablon listy składowej (BOM) do umowy serwisowej, kliknij opcję **Funkcje** i wybierz opcję **Dołącz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="f919b-113">To assign a template bill of materials (BOM) to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="f919b-114">W formularzu **Wybierz szablon BOM** w polu **Szablon BOM** wybierz szablon.</span><span class="sxs-lookup"><span data-stu-id="f919b-114">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 

## <a name="create-a-service-object-relation-for-a-service-order"></a><span data-ttu-id="f919b-115">Tworzenie relacji przedmiotów serwisu dla zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="f919b-115">Create a service object relation for a service order</span></span>

<span data-ttu-id="f919b-116">Aby utworzyć relację przedmiotów serwisu dla zlecenia serwisowego, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="f919b-116">Use the following steps to create a service object relation for a service order:</span></span>

1.  <span data-ttu-id="f919b-117">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="f919b-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="f919b-118">Z listy **Zlecenia serwisowe** wybierz istniejące zlecenie serwisowe lub utwórz nowe.</span><span class="sxs-lookup"><span data-stu-id="f919b-118">In the **Service orders** list, select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="f919b-119">W formularzu **Zlecenia serwisowe** w **okienku akcji** na karcie **Zlecenie serwisowe** w grupie **Relacje** kliknij opcję **Przedmioty serwisu**.</span><span class="sxs-lookup"><span data-stu-id="f919b-119">In the **Service orders** form, on the **Action Pane**, on the **Service order** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="f919b-120">W formularzu **Przedmioty serwisu** kliknij opcję **Nowy**, a następnie wybierz przedmiot serwisu dla tego zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="f919b-120">In the **Service objects** form, click **New**, and then select a service object for this service order.</span></span>

5.  <span data-ttu-id="f919b-121">Aby przypisać szablon BOM do umowy serwisowej, kliknij opcję **Funkcje** i wybierz opcję **Dołącz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="f919b-121">To assign a template BOM to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="f919b-122">W formularzu **Wybierz szablon BOM** w polu **Szablon BOM** wybierz szablon.</span><span class="sxs-lookup"><span data-stu-id="f919b-122">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 


## <a name="see-also"></a><span data-ttu-id="f919b-123">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f919b-123">See also</span></span>

[<span data-ttu-id="f919b-124">Omówienie przedmiotów serwisu</span><span class="sxs-lookup"><span data-stu-id="f919b-124">Service objects overview</span></span>](service-objects.md)

[<span data-ttu-id="f919b-125">Relacje przedmiotów serwisu</span><span class="sxs-lookup"><span data-stu-id="f919b-125">Service object relations</span></span>](service-object-relations.md)

[<span data-ttu-id="f919b-126">Szablony BOM</span><span class="sxs-lookup"><span data-stu-id="f919b-126">Template BOMs</span></span>](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]