---
title: Zarządzanie kredytem odbiorcy
description: ''
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
ms.openlocfilehash: 11da8b7fb59bc8f3e2568ada27db753cc815b9c2
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015353"
---
# <a name="customer-credit-management-overview"></a><span data-ttu-id="c95cd-102">Omówienie zarządzania kredytem odbiorcy</span><span class="sxs-lookup"><span data-stu-id="c95cd-102">Customer credit management overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="c95cd-103">Zarządzanie kredytami odbiorców umożliwia zarządzanie limitami kredytowymi i sterowanie przepływem zamówień sprzedaży za pomocą procesu księgowania na podstawie utworzonych reguł dotyczących kredytu.</span><span class="sxs-lookup"><span data-stu-id="c95cd-103">Customer credit management allows you to manage credit limits and control the flow of sales orders through the posting process based on credit rules that you create.</span></span> 

<span data-ttu-id="c95cd-104">Proces zarządzania kredytami może obejmować niektóre albo wszystkie następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="c95cd-104">The process for using credit management can include some or all of the following steps:</span></span>
- <span data-ttu-id="c95cd-105">Aktualizacja atrybutów kredytu odbiorcom w celu dostarczenia dodatkowych informacji o zdolnościach kredytowych</span><span class="sxs-lookup"><span data-stu-id="c95cd-105">Update customers with credit attributes that provide additional information about their credit worthiness</span></span> 
- <span data-ttu-id="c95cd-106">Umożliwia tworzenie limitów kredytu dla odbiorców przy użyciu korekt limitu kredytu</span><span class="sxs-lookup"><span data-stu-id="c95cd-106">Create credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="c95cd-107">Tworzenie tymczasowych limitów kredytu dla odbiorców używających korekt limitu kredytu w przypadku, gdy limit kredytu ma być tymczasowo zwiększany lub zmniejszany na podstawie potrzeb biznesowych</span><span class="sxs-lookup"><span data-stu-id="c95cd-107">Create temporary credit limits for customers using credit limit adjustments when you want to increase or decrease their credit limit temporarily based on business needs</span></span>
- <span data-ttu-id="c95cd-108">Umożliwia dodanie dodatkowych informacji, które mogą mieć wpływ na limit kredytu, np. Informacje o ubezpieczeniach i gwarancjach</span><span class="sxs-lookup"><span data-stu-id="c95cd-108">Add additional information that can affect the credit limit such as insurance and guarantees</span></span>
- <span data-ttu-id="c95cd-109">Należy utworzyć grupy kredytowe odbiorcy łączące klientów, tak aby mogli oni korzystać z jednego limitu kredytowego</span><span class="sxs-lookup"><span data-stu-id="c95cd-109">Create customer credit groups that link customers together so they can share a single credit limit</span></span>
- <span data-ttu-id="c95cd-110">Przypisz do odbiorców wyniki ryzyka, a następnie skorzystaj z tych wyników, aby automatycznie wygenerować limity kredytowe dla tych odbiorców za pomocą korekt limitu kredytu</span><span class="sxs-lookup"><span data-stu-id="c95cd-110">Assign risk scores to customers and then use those scores to automatically generate credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="c95cd-111">Utwórz reguły blokowania, które powodują wstrzymanie zamówienia podczas jednego lub większej liczby procesów księgowania, na podstawie czynników takich jak ryzyko, warunki płatności, limity kredytu, kwoty zaległe oraz procent wykorzystania limitu kredytu</span><span class="sxs-lookup"><span data-stu-id="c95cd-111">Create blocking rules that will place an order on hold during one or more posting processes based on factors such as risk, payment terms, credit limits, overdue amounts, and percentage of credit limit used</span></span>
- <span data-ttu-id="c95cd-112">Umożliwia zarządzanie listą wstrzymanych zamówień sprzedaży, przeglądanie przyczyn wstrzymania i łagodzenie problemów</span><span class="sxs-lookup"><span data-stu-id="c95cd-112">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate the issues</span></span>
- <span data-ttu-id="c95cd-113">Zwolnij zamówienia sprzedaży, aby były przetwarzane dalej w procesie księgowania</span><span class="sxs-lookup"><span data-stu-id="c95cd-113">Release sales orders and allow it to continue through the posting process</span></span>
- <span data-ttu-id="c95cd-114">Skonfiguruj przepływ pracy, aby zarządzać zatwierdzaniem zmian limitu kredytu i zwalnianiem zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c95cd-114">Set up workflow to manage the approval of credit limit changes and sales order releases</span></span>


<a name="additional-resources"></a><span data-ttu-id="c95cd-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c95cd-115">Additional resources</span></span>
--------
[<span data-ttu-id="c95cd-116">Ustawienia parametrów modułu Zarządzanie kredytami odbiorcy</span><span class="sxs-lookup"><span data-stu-id="c95cd-116">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="c95cd-117">Ustawienia informacji modułu Zarządzanie kredytami odbiorcy</span><span class="sxs-lookup"><span data-stu-id="c95cd-117">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="c95cd-118">Dodaj informacje dotyczące zarządzania kredytem odbiorcy</span><span class="sxs-lookup"><span data-stu-id="c95cd-118">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="c95cd-119">Grupy kredytowe odbiorcy</span><span class="sxs-lookup"><span data-stu-id="c95cd-119">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="c95cd-120">Korekty limitu kredytu odbiorcy</span><span class="sxs-lookup"><span data-stu-id="c95cd-120">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="c95cd-121">Obsługa wstrzymania kredytu zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c95cd-121">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="c95cd-122">Zadania okresowe zarządzania kredytami odbiorcy</span><span class="sxs-lookup"><span data-stu-id="c95cd-122">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)


