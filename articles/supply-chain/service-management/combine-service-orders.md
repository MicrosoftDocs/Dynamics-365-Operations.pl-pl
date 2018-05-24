---
title: "Łączenie zleceń serwisowych"
description: "Zlecenia serwisowe można łączyć."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
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
ms.openlocfilehash: 8bc28d03d36d184e4bf41de2c50dac15e6d7813c
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="combine-service-orders"></a><span data-ttu-id="6a83b-103">Łączenie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="6a83b-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="6a83b-104">Podczas tworzenia wierszy zlecenia serwisowego automatycznie w formularzu **Umowy serwisowe** można wybrać jedną z poniższych opcji, aby określić sposób ich grupowania:</span><span class="sxs-lookup"><span data-stu-id="6a83b-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="6a83b-105">**Według umowy serwisowej**</span><span class="sxs-lookup"><span data-stu-id="6a83b-105">**By service agreement**</span></span>

  - <span data-ttu-id="6a83b-106">**Według zadania serwisowego**</span><span class="sxs-lookup"><span data-stu-id="6a83b-106">**By service task**</span></span>

  - <span data-ttu-id="6a83b-107">**Według pracownika etatowego**</span><span class="sxs-lookup"><span data-stu-id="6a83b-107">**By employee**</span></span>

  - <span data-ttu-id="6a83b-108">**Według przedmiotu serwisu**</span><span class="sxs-lookup"><span data-stu-id="6a83b-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="6a83b-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="6a83b-109">Example</span></span>

<span data-ttu-id="6a83b-110">Tworzysz umowę serwisową o dacie rozpoczęcia 2007-03-31.</span><span class="sxs-lookup"><span data-stu-id="6a83b-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="6a83b-111">W polu **Łączenie zleceń serwisowych** wybierasz opcję **Według przedmiotu serwisu**.</span><span class="sxs-lookup"><span data-stu-id="6a83b-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="6a83b-112">Następnie zostaną utworzone następujące wiersze umowy serwisowej:</span><span class="sxs-lookup"><span data-stu-id="6a83b-112">You then create the following service agreement lines:</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6a83b-113">Numer wiersza umowy</span><span class="sxs-lookup"><span data-stu-id="6a83b-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="6a83b-114">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="6a83b-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="6a83b-115">opis</span><span class="sxs-lookup"><span data-stu-id="6a83b-115">Description</span></span></p></th>
<th><p><span data-ttu-id="6a83b-116">Zakres</span><span class="sxs-lookup"><span data-stu-id="6a83b-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="6a83b-117">Przedmiot serwisu</span><span class="sxs-lookup"><span data-stu-id="6a83b-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="6a83b-118">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="6a83b-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a83b-119">1</span><span class="sxs-lookup"><span data-stu-id="6a83b-119">1</span></span></p></td>
<td><p><span data-ttu-id="6a83b-120"><strong>Godzina</strong></span><span class="sxs-lookup"><span data-stu-id="6a83b-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="6a83b-121">WUS1</span><span class="sxs-lookup"><span data-stu-id="6a83b-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="6a83b-122">Tygodniowa</span><span class="sxs-lookup"><span data-stu-id="6a83b-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="6a83b-123">X-1</span><span class="sxs-lookup"><span data-stu-id="6a83b-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="6a83b-124">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="6a83b-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a83b-125">2</span><span class="sxs-lookup"><span data-stu-id="6a83b-125">2</span></span></p></td>
<td><p><span data-ttu-id="6a83b-126"><strong>Godzina</strong></span><span class="sxs-lookup"><span data-stu-id="6a83b-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="6a83b-127">WUS2</span><span class="sxs-lookup"><span data-stu-id="6a83b-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="6a83b-128">Co dwa tygodnie</span><span class="sxs-lookup"><span data-stu-id="6a83b-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="6a83b-129">X-2</span><span class="sxs-lookup"><span data-stu-id="6a83b-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="6a83b-130">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="6a83b-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a83b-131">3</span><span class="sxs-lookup"><span data-stu-id="6a83b-131">3</span></span></p></td>
<td><p><span data-ttu-id="6a83b-132"><strong>Godzina</strong></span><span class="sxs-lookup"><span data-stu-id="6a83b-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="6a83b-133">WUS3</span><span class="sxs-lookup"><span data-stu-id="6a83b-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="6a83b-134">Tygodniowa</span><span class="sxs-lookup"><span data-stu-id="6a83b-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="6a83b-135">X-2</span><span class="sxs-lookup"><span data-stu-id="6a83b-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="6a83b-136">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="6a83b-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6a83b-137">Okna czasu nie są określane dla żadnego z wierszy umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="6a83b-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="6a83b-138">Dlatego wiersze zlecenia serwisowego nie będą przenoszone z dnia, na który przypadają w wyniku obliczeń.</span><span class="sxs-lookup"><span data-stu-id="6a83b-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="6a83b-139">Następnie w formularzu **Utwórz zlecenia serwisowe** generujesz wiersze zlecenia serwisowego na okres od 2007-04-01 do 2007-04-30.</span><span class="sxs-lookup"><span data-stu-id="6a83b-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="6a83b-140">W sumie utworzono 10 zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="6a83b-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="6a83b-141">Ponieważ wybrano łączone ustawienie **Według przedmiotu serwisu**, wiersze wszystkich utworzonych zleceń serwisowych mają określony tylko jeden przedmiot serwisu.</span><span class="sxs-lookup"><span data-stu-id="6a83b-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="6a83b-142">Wiersze zlecenia serwisowego, które są generowane z umowy serwisowej i mają tę samą datę serwisu oraz przedmiot, są łączone w tym samym zleceniu serwisowym.</span><span class="sxs-lookup"><span data-stu-id="6a83b-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="6a83b-143">W tym przykładzie kalendarz określony w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG> nie zawiera zamkniętych dni.</span><span class="sxs-lookup"><span data-stu-id="6a83b-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="6a83b-144">Dodatkowe grupowanie wierszy zlecenia serwisowego w zlecenia serwisowe zostanie wykonane zgodnie z oknami czasowymi określonymi w wierszach umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="6a83b-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a83b-145">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="6a83b-145">See also</span></span>

[<span data-ttu-id="6a83b-146">Automatyczne tworzenie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="6a83b-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  



