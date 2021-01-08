---
title: Automatyczne tworzenie zleceń serwisowych
description: Zlecenia serwisowe można generować na podstawie umowy serwisowej w trakcie okresu ważności umowy serwisowej.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08fb7363ab87fd6a7f3d38406e72b1f542dc2c2a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435402"
---
# <a name="automatically-create-service-orders"></a><span data-ttu-id="c1b8c-103">Automatyczne tworzenie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="c1b8c-103">Automatically create service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="c1b8c-104">Zlecenia serwisowe można generować na podstawie umowy serwisowej w trakcie okresu ważności umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-104">You can generate service orders that are based on a service agreement for the valid period of the service agreement.</span></span>

<span data-ttu-id="c1b8c-105">Wszystkie zlecenia serwisowe generowane na podstawie umowy serwisowej są dołączone do tej umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-105">The service orders that you generate from a service agreement are all attached to the service agreement.</span></span>

<span data-ttu-id="c1b8c-106">Zlecenia serwisowe są generowane automatycznie na podstawie następujących ustawień:</span><span class="sxs-lookup"><span data-stu-id="c1b8c-106">Service orders are generated automatically from the following settings:</span></span>

  - <span data-ttu-id="c1b8c-107">Interwału umowy serwisowej skonfigurowanego w wierszach tej umowy.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-107">The service agreement interval that is set up in the service agreement lines.</span></span> <span data-ttu-id="c1b8c-108">Interwał umowy serwisowej określa częstotliwość, z jaką są tworzone wiersze umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-108">The service agreement interval indicates the frequency that service-order lines are created.</span></span> <span data-ttu-id="c1b8c-109">Aby uzyskać więcej informacji, zobacz [Interwały serwisu](service-intervals.md).</span><span class="sxs-lookup"><span data-stu-id="c1b8c-109">For more information, see [Service intervals](service-intervals.md).</span></span>

  - <span data-ttu-id="c1b8c-110">Okresu serwisu zdefiniowanego w polach **Od dnia** i **Do dnia** w formularzu **Utwórz zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-110">The period that you specify to define the service period in the **From date** and **To date** fields in the **Create service orders** form.</span></span> <span data-ttu-id="c1b8c-111">Aby uzyskać więcej informacji, zobacz [Automatyczne tworzenie zleceń serwisowych](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="c1b8c-111">For more information, see [Create service orders automatically](create-service-orders-automatically.md).</span></span>

  - <span data-ttu-id="c1b8c-112">Opcji **Łączenie zleceń serwisowych** w nagłówku umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-112">The **Combine service orders** option on the service agreement header.</span></span> <span data-ttu-id="c1b8c-113">Ta opcja określa, czy wiersze zlecenia serwisowego wygenerowane na podstawie umowy serwisowej mają łączyć zlecenia serwisowe według kryterium pracownika, zadania serwisowego, przedmiotu serwisu lub umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-113">This option defines whether service order lines generated from a service agreement, combines service orders according to employee, service task, service object, or service agreement.</span></span> <span data-ttu-id="c1b8c-114">Aby uzyskać więcej informacji, zobacz [Łączenie zleceń serwisowych](combine-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="c1b8c-114">For more information, see [Combine service orders](combine-service-orders.md).</span></span>

  - <span data-ttu-id="c1b8c-115">Opcji **Okno czasu** w wierszu umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-115">The **Time window** option on the service agreement line.</span></span> <span data-ttu-id="c1b8c-116">Okno czasowe określa, jak daleko wiersz zlecenia serwisowego może być przesunięty względem jego obliczonej daty.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-116">The time window defines how far a service order line can move with regard to its calculated date.</span></span> <span data-ttu-id="c1b8c-117">Aby uzyskać więcej informacji, zobacz [Okna czasu](time-windows.md).</span><span class="sxs-lookup"><span data-stu-id="c1b8c-117">For more information, see [Time windows](time-windows.md).</span></span>


> [!NOTE]
> <P><span data-ttu-id="c1b8c-118">Jeśli dzień określony dla zlecenia serwisowego nie jest otwarty w kalendarzu wybranym w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG>, pojawi się komunikat informujący o konflikcie kalendarza.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-118">If the day that is specified for a service order is not open in the calendar that you have selected in the <STRONG>Service management parameters</STRONG> form, a message will indicate that there is a calendar conflict.</span></span> <span data-ttu-id="c1b8c-119">Można bez obaw zignorować ten komunikat. Zlecenie serwisowe zostanie utworzone, nawet mimo że dzień jest zamknięty w kalendarzu.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-119">You can safely ignore the message; the service order will be created, even though the day is closed on the calendar.</span></span></P>

## <a name="example-1"></a><span data-ttu-id="c1b8c-120">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="c1b8c-120">Example 1</span></span>

<span data-ttu-id="c1b8c-121">Umowa serwisowa obowiązuje od 1 stycznia 2012 r. do 31 grudnia 2012 r.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-121">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="c1b8c-122">Jeśli okres serwisu określony w formularzu **Utwórz zlecenia serwisowe** sięga od 1 listopada 2012 r. do 1 lutego 2013 r., zlecenia serwisowe będą tworzone od 1 listopada 2012 r. do 31 grudnia 2012 r.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-122">If the service period that you specify in the **Create service orders** form is from November 1, 2012 until February 1, 2013, service orders are created from November 1, 2012 until December 31, 2012.</span></span>

## <a name="example-2"></a><span data-ttu-id="c1b8c-123">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="c1b8c-123">Example 2</span></span>

<span data-ttu-id="c1b8c-124">Umowa serwisowa obowiązuje od 1 stycznia 2012 r. do 31 grudnia 2012 r.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-124">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="c1b8c-125">Do umowy serwisowej są dołączone dwa wiersze umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-125">Two service agreement lines are attached to the service agreement.</span></span> <span data-ttu-id="c1b8c-126">Pierwszy wiersz umowy serwisowej ma datę rozpoczęcia 2 stycznia 2012 r., a datę zakończenia 1 marca 2012 r.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-126">The first service agreement line has a starting date on January 2, 2012 and an ending date on March 1, 2012.</span></span> <span data-ttu-id="c1b8c-127">Drugi wiersz umowy serwisowej ma datę rozpoczęcia 1 kwietnia 2012 r., a datę zakończenia 31 grudnia 2012 r.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-127">The second service agreement line has a starting date on April 1, 2012 and an ending date on December 31, 2012.</span></span> <span data-ttu-id="c1b8c-128">W formularzu **Utwórz zlecenia serwisowe** określasz okres sięgając od 1 października 2012 r. do 31 grudnia 2012 r.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-128">You specify a period in the **Create service orders** form that is from October 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="c1b8c-129">W efekcie zlecenia serwisowe będą generowane tylko dla drugiego wiersza umowy serwisowej, ponieważ daty początkowa i końcowa pierwszego wiersza umowy przypadają przed zdefiniowanym okresem zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="c1b8c-129">Therefore, service orders are generated only for the second agreement line, because the starting date and ending date of the first agreement line are before the period that you specified for the service order.</span></span>

  


