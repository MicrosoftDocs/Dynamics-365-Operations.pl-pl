---
title: Automatyczne tworzenie zleceń serwisowych
description: Zlecenia serwisowe można tworzyć dla jednej lub kilku umów serwisowych.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee68190b117b974ff4131f5d2237d138cac1fda3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "358331"
---
# <a name="create-service-orders-automatically"></a><span data-ttu-id="0a1bd-103">Automatyczne tworzenie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="0a1bd-103">Create service orders automatically</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="0a1bd-104">Zlecenia serwisowe można tworzyć dla jednej lub kilku umów serwisowych.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-104">You can create service orders for one service agreement or for several service agreements.</span></span> <span data-ttu-id="0a1bd-105">Utworzone zlecenia serwisowe można wyświetlić w formularzu **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-105">When they are created, you can view your service orders in the **Service orders** form.</span></span>

<span data-ttu-id="0a1bd-106">Zlecenia serwisowe są tworzone tylko dla ważnego okresu umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-106">Service orders are created only for the valid period of the service agreement.</span></span> <span data-ttu-id="0a1bd-107">Jeśli ramy czasowe określone w formularzu **Utwórz zlecenia serwisowe** wykraczają przed datę rozpoczęcia lub za datę zakończenia umowy serwisowej, zlecenia serwisowe są tworzone tylko dla tej części ram czasowych, która mieści się w granicach czasowych umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-107">If the interval that you specify in the **Create service orders** form is before the starting date or after the ending date of the service agreement, service orders are created only for the part of the interval that is within the service agreement dates.</span></span>

<span data-ttu-id="0a1bd-108">Podczas tworzenia zleceń serwisowych ręcznie lub automatycznie z poziomu wiersza umowy serwisowej zlecenie musi się mieścić w granicach przedziału czasu określonego przez daty początkową i końcową ustawione dla wiersza, chyba że dla wiersza nie określono daty końcowej.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-108">When you create service orders manually or automatically from the service agreement line, the service order must be in the time interval that is defined by the starting and ending dates for the line, unless you do not specify an ending date on the line.</span></span>

## <a name="create-service-orders-automatically-for-a-service-agreement"></a><span data-ttu-id="0a1bd-109">Automatyczne tworzenie zleceń serwisowych dla umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="0a1bd-109">Create service orders automatically for a service agreement</span></span>

1.  <span data-ttu-id="0a1bd-110">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-110">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="0a1bd-111">Wybierz umowę serwisową.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-111">Select a service agreement.</span></span>

3.  <span data-ttu-id="0a1bd-112">Kliknij kartę **Dostarcz**, a następnie kliknij opcję **Planowane zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-112">Click the **Deliver** tab, and then click **Planned service orders**.</span></span>

4.  <span data-ttu-id="0a1bd-113">Określ daty w polach **Od dnia** i **Do dnia**, aby zdefiniować okres serwisu.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-113">Specify dates in the **From date** and **To date** fields to define the service period.</span></span>

5.  <span data-ttu-id="0a1bd-114">Zaznacz pole wyboru **Pokaż dziennik informacyjny**, aby wyświetlić listę utworzonych zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-114">Select the **Show Infolog** check box to display a list of the service orders that are created.</span></span>

6.  <span data-ttu-id="0a1bd-115">Wybierz typy transakcji w grupie pól **Uwzględnij typy transakcji**.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-115">Select transaction types in the **Include transaction types** field group.</span></span> <span data-ttu-id="0a1bd-116">Typy transakcji reprezentują wiersze utworzone w umowie serwisowej, a każdy wybrany typ transakcji powoduje wygenerowanie kilku zleceń serwisowych, w zależności od ram czasowych serwisu określonych w wierszu umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-116">The transaction types represent the lines that are created in the service agreement, and each transaction type that you select generates several service orders, depending on the service interval that is specified on the service agreement line.</span></span>

7.  <span data-ttu-id="0a1bd-117">Aby utworzyć wszelkie brakujące zlecenia serwisowe w ramach ciągłej serii zleceń serwisowych, zaznacz pole wyboru **Ciągłe**.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-117">To create any service orders that are missing from continuous series of service orders, select the **Continuous** check box.</span></span>

8.  <span data-ttu-id="0a1bd-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-118">Click **OK**.</span></span>

## <a name="create-service-orders-automatically-for-several-service-agreements"></a><span data-ttu-id="0a1bd-119">Automatyczne tworzenie zleceń serwisowych dla kilku umów serwisowych</span><span class="sxs-lookup"><span data-stu-id="0a1bd-119">Create service orders automatically for several service agreements</span></span>

1.  <span data-ttu-id="0a1bd-120">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Okresowe** \> **Zlecenia serwisowe** \> **Utwórz zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-120">Click **Service management** \> **Periodic** \> **Service orders** \> **Create service orders**.</span></span>

2.  <span data-ttu-id="0a1bd-121">Kliknij przycisk **Wybierz** i dodaj lub usuń kryteria używane do tworzenia zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-121">Click **Select** to make selections to add or remove criteria to use to create service orders.</span></span>

3.  <span data-ttu-id="0a1bd-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-122">Click **OK**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a1bd-123">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="0a1bd-123">See also</span></span>

[<span data-ttu-id="0a1bd-124">Zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="0a1bd-124">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="0a1bd-125">Automatyczne tworzenie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="0a1bd-125">Automatically creating service orders</span></span>](auto-create-service-orders.md)

  


