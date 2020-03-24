---
title: Zarządzanie kredytem odbiorcy
description: Zarządzanie kredytami odbiorców umożliwia zarządzanie limitami kredytowymi i sterowanie przepływem zamówień sprzedaży za pomocą procesu księgowania na podstawie utworzonych reguł dotyczących kredytu.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1e7d3325587d7cfc876e8f8c7b9207d44046ccd4
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124284"
---
# <a name="customer-credit-management-overview"></a><span data-ttu-id="e6487-103">Omówienie zarządzania kredytem odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e6487-103">Customer credit management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6487-104">Zarządzanie kredytami odbiorców umożliwia zarządzanie limitami kredytowymi i sterowanie przepływem zamówień sprzedaży za pomocą procesu księgowania na podstawie utworzonych reguł dotyczących kredytu.</span><span class="sxs-lookup"><span data-stu-id="e6487-104">Customer credit management allows you to manage credit limits and control the flow of sales orders through the posting process based on credit rules that you create.</span></span> 

<span data-ttu-id="e6487-105">Proces zarządzania kredytami może obejmować niektóre albo wszystkie następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="e6487-105">The process for using credit management can include some or all of the following steps:</span></span>
- <span data-ttu-id="e6487-106">Aktualizacja atrybutów kredytu odbiorcom w celu dostarczenia dodatkowych informacji o zdolnościach kredytowych</span><span class="sxs-lookup"><span data-stu-id="e6487-106">Update customers with credit attributes that provide additional information about their credit worthiness</span></span> 
- <span data-ttu-id="e6487-107">Umożliwia tworzenie limitów kredytu dla odbiorców przy użyciu korekt limitu kredytu</span><span class="sxs-lookup"><span data-stu-id="e6487-107">Create credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="e6487-108">Tworzenie tymczasowych limitów kredytu dla odbiorców używających korekt limitu kredytu w przypadku, gdy limit kredytu ma być tymczasowo zwiększany lub zmniejszany na podstawie potrzeb biznesowych</span><span class="sxs-lookup"><span data-stu-id="e6487-108">Create temporary credit limits for customers using credit limit adjustments when you want to increase or decrease their credit limit temporarily based on business needs</span></span>
- <span data-ttu-id="e6487-109">Umożliwia dodanie dodatkowych informacji, które mogą mieć wpływ na limit kredytu, np. Informacje o ubezpieczeniach i gwarancjach</span><span class="sxs-lookup"><span data-stu-id="e6487-109">Add additional information that can affect the credit limit such as insurance and guarantees</span></span>
- <span data-ttu-id="e6487-110">Należy utworzyć grupy kredytowe odbiorcy łączące klientów, tak aby mogli oni korzystać z jednego limitu kredytowego</span><span class="sxs-lookup"><span data-stu-id="e6487-110">Create customer credit groups that link customers together so they can share a single credit limit</span></span>
- <span data-ttu-id="e6487-111">Przypisz do odbiorców wyniki ryzyka, a następnie skorzystaj z tych wyników, aby automatycznie wygenerować limity kredytowe dla tych odbiorców za pomocą korekt limitu kredytu</span><span class="sxs-lookup"><span data-stu-id="e6487-111">Assign risk scores to customers and then use those scores to automatically generate credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="e6487-112">Utwórz reguły blokowania, które powodują wstrzymanie zamówienia podczas jednego lub większej liczby procesów księgowania, na podstawie czynników takich jak ryzyko, warunki płatności, limity kredytu, kwoty zaległe oraz procent wykorzystania limitu kredytu</span><span class="sxs-lookup"><span data-stu-id="e6487-112">Create blocking rules that will place an order on hold during one or more posting processes based on factors such as risk, payment terms, credit limits, overdue amounts, and percentage of credit limit used</span></span>
- <span data-ttu-id="e6487-113">Umożliwia zarządzanie listą wstrzymanych zamówień sprzedaży, przeglądanie przyczyn wstrzymania i łagodzenie problemów</span><span class="sxs-lookup"><span data-stu-id="e6487-113">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate the issues</span></span>
- <span data-ttu-id="e6487-114">Zwolnij zamówienia sprzedaży, aby były przetwarzane dalej w procesie księgowania</span><span class="sxs-lookup"><span data-stu-id="e6487-114">Release sales orders and allow it to continue through the posting process</span></span>
- <span data-ttu-id="e6487-115">Skonfiguruj przepływ pracy, aby zarządzać zatwierdzaniem zmian limitu kredytu i zwalnianiem zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e6487-115">Set up workflow to manage the approval of credit limit changes and sales order releases</span></span>


<a name="additional-resources"></a><span data-ttu-id="e6487-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e6487-116">Additional resources</span></span>
--------
[<span data-ttu-id="e6487-117">Ustawienia parametrów modułu Zarządzanie kredytami odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e6487-117">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="e6487-118">Ustawienia informacji modułu Zarządzanie kredytami odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e6487-118">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="e6487-119">Dodaj informacje dotyczące zarządzania kredytem odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e6487-119">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="e6487-120">Grupy kredytowe odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e6487-120">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="e6487-121">Korekty limitu kredytu odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e6487-121">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="e6487-122">Obsługa wstrzymania kredytu zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e6487-122">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="e6487-123">Zadania okresowe zarządzania kredytami odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e6487-123">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)


