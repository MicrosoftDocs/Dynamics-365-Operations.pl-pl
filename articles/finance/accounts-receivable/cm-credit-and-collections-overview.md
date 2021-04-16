---
title: Omówienie kredytów i windykacji
description: W tym temacie omówiono funkcje dotyczące kredytów i windykacji.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7929150cd9f6c28620f4c4d4cb7b57b02d27a104
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835419"
---
# <a name="credit-and-collections-overview"></a><span data-ttu-id="9b9ca-103">Omówienie kredytów i windykacji</span><span class="sxs-lookup"><span data-stu-id="9b9ca-103">Credit and collections overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b9ca-104">Można zarządzać limitami kredytowymi odbiorców i wykonywać działania windykacji, gdy staną się niezbędne.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-104">You can manage credit limits for your customers and perform collection activities when they become necessary.</span></span>

## <a name="credit-management"></a><span data-ttu-id="9b9ca-105">Zarządzanie kredytem</span><span class="sxs-lookup"><span data-stu-id="9b9ca-105">Credit management</span></span>

<span data-ttu-id="9b9ca-106">Zarządzanie kredytami odbiorców umożliwia zarządzanie limitami kredytowymi i sterowanie przepływem zamówień sprzedaży za pomocą procesu księgowania na podstawie utworzonych reguł dotyczących kredytu.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-106">Customer credit management lets you manage credit limits and control the flow of sales orders through the posting process, based on credit rules that you create.</span></span>

<span data-ttu-id="9b9ca-107">Proces zarządzania kredytami może obejmować następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="9b9ca-107">The credit management process can include any of the following steps:</span></span>

- <span data-ttu-id="9b9ca-108">Aktualizacja atrybutów kredytu dla odbiorców w celu dostarczenia dodatkowych informacji o zdolnościach kredytowych.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-108">Update credit attributes for customers to provide additional information about their credit worthiness.</span></span>
- <span data-ttu-id="9b9ca-109">Umożliwia tworzenie limitów kredytu dla odbiorców przy użyciu korekt limitu kredytu.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-109">Create credit limits for customers by using credit limit adjustments.</span></span>
- <span data-ttu-id="9b9ca-110">Umożliwia tymaczasowe tworzenie limitów kredytu dla odbiorców przy użyciu korekt limitu kredytu.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-110">Create temporary credit limits for customers by using credit limit adjustments.</span></span> <span data-ttu-id="9b9ca-111">W ten sposób można tymczasowo zwiększyć lub zmniejszyć limity kredytowe klientów na podstawie wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-111">In this way, you can temporarily increase or decrease customer credit limits, based on business requirements.</span></span>
- <span data-ttu-id="9b9ca-112">Umożliwia dodanie informacji, które mogą mieć wpływ na limit kredytu, np. Informacje o ubezpieczeniach i gwarancjach.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-112">Add information that can affect the credit limit, such as information about insurance and guarantees.</span></span>
- <span data-ttu-id="9b9ca-113">Należy utworzyć grupy kredytowe odbiorcy łączące klientów, tak aby mogli oni korzystać z jednego limitu kredytowego.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-113">Create customer credit groups that link customers together so that they share a single credit limit.</span></span>
- <span data-ttu-id="9b9ca-114">Przypisz do odbiorców wyniki ryzyka, a następnie skorzystaj z tych wyników, aby automatycznie wygenerować limity kredytowe dla tych odbiorców za pomocą korekt limitu kredytu.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-114">Assign risk scores to customers, and then use the scores to automatically generate credit limits for those customers through credit limit adjustments.</span></span>
- <span data-ttu-id="9b9ca-115">Utwórz reguły blokowania, które powodują wstrzymanie zamówienia podczas jednego lub większej liczby procesów księgowania, na podstawie czynników takich jak ryzyko, warunki płatności, limity kredytu, kwoty zaległe oraz procent wykorzystania limitu kredytu.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-115">Create blocking rules that put an order on hold during one or more posting processes, based on factors such as risk, payment terms, credit limits, overdue amounts, and the percentage of the credit limit that has been used.</span></span>
- <span data-ttu-id="9b9ca-116">Umożliwia zarządzanie listą wstrzymanych zamówień sprzedaży, przeglądanie przyczyn wstrzymania i łagodzenie problemów.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-116">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate issues.</span></span>
- <span data-ttu-id="9b9ca-117">Zwolnij zamówienia sprzedaży, aby były przetwarzane dalej w procesie księgowania.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-117">Release sales orders so that they continue through the posting process.</span></span>
- <span data-ttu-id="9b9ca-118">Skonfiguruj przepływ pracy, aby zarządzać zatwierdzaniem zmian limitu kredytu i zwalnianiem zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-118">Set up a workflow to manage the approval of credit limit changes and sales order releases.</span></span>

## <a name="collections-management"></a><span data-ttu-id="9b9ca-119">Zarządzanie windykacjami</span><span class="sxs-lookup"><span data-stu-id="9b9ca-119">Collections management</span></span>

<span data-ttu-id="9b9ca-120">Informacje dotyczące windykacji w module Rozrachunki z odbiorcami są zarządzane w jednym centralnym widoku na stronie **Windykacje**.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-120">The **Collections** page provides a centralized view where accounts receivable collections information is managed.</span></span> <span data-ttu-id="9b9ca-121">Kierownicy ds. windykacji i windykacji mogą używać tego centralnego widoku do zarządzania windykacją.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-121">Collections managers can use this centralized view to manage collections.</span></span> <span data-ttu-id="9b9ca-122">Agenci ds. windykacji mogą rozpocząć proces windykacji na podstawie list odbiorców, które są generowane przy użyciu wstępnie zdefiniowanych kryteriów windykacji, lub ze strony **Odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-122">Collections agents can begin the collections process either from customer lists that are generated by using predefined collection criteria or from the **Customers** page.</span></span>

<span data-ttu-id="9b9ca-123">Przed rozpoczęciem konfigurowania lub pracy z windykacjami należy zapoznać się z następującymi pojęciami:</span><span class="sxs-lookup"><span data-stu-id="9b9ca-123">Before you start to set up or work with collections, you should understand the following concepts:</span></span>

- <span data-ttu-id="9b9ca-124">Migawka wiekowania odbiorcy zawiera informacje o wiekowanym saldzie w określonym momencie.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-124">Customer aging snapshots contain aged balance information at a specific point in time.</span></span>
- <span data-ttu-id="9b9ca-125">Pule klientów związanych z windykacjami pomagają w organizacji pracy.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-125">Collections customer pools help you organize your work.</span></span>
- <span data-ttu-id="9b9ca-126">Agenci ds. windykacji mają własne pule klientów.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-126">Collections agents can have their own customer pools.</span></span>
- <span data-ttu-id="9b9ca-127">Strony listy organizują odbiorców związanych z windykacjami, działania i sprawy.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-127">List pages organize collections customers, activities, and cases.</span></span>
- <span data-ttu-id="9b9ca-128">Wszystkie informacje o windykacji dotyczące danego odbiorcy znajdują się na jednej stronie, na której można podejmować wymagane działania.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-128">All collections information for a customer is on one page, and you can take action from that page.</span></span>
- <span data-ttu-id="9b9ca-129">W jednym kroku można wykonać uchylenie, przywrócenie lub wycofanie odsetek.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-129">Interest and fees can be waived, reinstated, or reversed in one step.</span></span>
- <span data-ttu-id="9b9ca-130">W jednym kroku można tworzyć transakcje odpisu.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-130">Write-off transactions can be created in one step.</span></span>
- <span data-ttu-id="9b9ca-131">W jednym kroku można przetwarzać płatności przy niewystarczających funduszach.</span><span class="sxs-lookup"><span data-stu-id="9b9ca-131">Not sufficient funds (NSF) payments can be processed in one step.</span></span>

<span data-ttu-id="9b9ca-132">Aby zapoznać się z opisami tych pojęć, zajrzyj do [Pojęcia kluczowe związane z zarządzaniem windykacją](./cm-collections-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="9b9ca-132">For descriptions of these concepts, see [Collections management key concepts](./cm-collections-concepts.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b9ca-133">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9b9ca-133">Additional resources</span></span>

[<span data-ttu-id="9b9ca-134">Ustawienia parametrów modułu Zarządzanie kredytami odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9b9ca-134">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="9b9ca-135">Ustawienia informacji modułu Zarządzanie kredytami odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9b9ca-135">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="9b9ca-136">Dodaj informacje dotyczące zarządzania kredytem odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9b9ca-136">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="9b9ca-137">Grupy kredytowe odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9b9ca-137">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="9b9ca-138">Korekty limitu kredytu odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9b9ca-138">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="9b9ca-139">Obsługa wstrzymania kredytu zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9b9ca-139">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="9b9ca-140">Zadania okresowe zarządzania kredytami odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9b9ca-140">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]