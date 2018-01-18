---
title: "Wstrzymania zamówień"
description: "W tym temacie opisano, jak wstrzymuje się zamówienia przy użyciu programu Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: c543a1538a83d88eaebce203e14cf8b0e10e2ad3
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---

# <a name="order-holds"></a><span data-ttu-id="c3412-103">Wstrzymania zamówień</span><span class="sxs-lookup"><span data-stu-id="c3412-103">Order holds</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="c3412-104">W tym temacie opisano, jak wstrzymuje się zamówienia przy użyciu programu Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="c3412-104">This topic describes holds on orders using Dynamics 365 for Retail.</span></span>

<span data-ttu-id="c3412-105">Zamówienie może zostać wstrzymane z różnych przyczyn.</span><span class="sxs-lookup"><span data-stu-id="c3412-105">An order can be put on hold for various reasons.</span></span> <span data-ttu-id="c3412-106">Można na przykład wstrzymać zamówienie, dopóki nie zostaną sprawdzone metody płatności lub adres odbiorcy lub dopóki menedżer nie sprawdzi limitu kredytu odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="c3412-106">For example, you might put an order on hold until the customer address or payment method can be verified, or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="c3412-107">Podczas procesu sprzedaży zdarza się, że zamówienie sprzedaży musi być wstrzymane.</span><span class="sxs-lookup"><span data-stu-id="c3412-107">During the sales process, there are times when sales orders must be put on hold.</span></span> <span data-ttu-id="c3412-108">Na przykład zamówienie sprzedaży może być wstrzymane z powodu problemów z płatnością, podejrzenia oszustwa lub oczekiwania na przegląd przez menedżera.</span><span class="sxs-lookup"><span data-stu-id="c3412-108">For example, a sales order might be put on hold because of issues with a customer payment, because of suspected fraud, or because a manager must review the order.</span></span> <span data-ttu-id="c3412-109">Gdy zamówienie sprzedaży jest wstrzymane, kod wstrzymania zamówienia zostaje przypisany do zamówienia sprzedaży, aby wskazać przyczynę wstrzymania.</span><span class="sxs-lookup"><span data-stu-id="c3412-109">When a sales order is put on hold, an order hold code is assigned to the sales order to indicate the reason for the hold.</span></span> <span data-ttu-id="c3412-110">Kody wstrzymania zamówień są konfigurowane w oknie **Sprzedaż i marketing** &gt; **Ustawienia** &gt; **Zamówienia sprzedaży** &gt; **Kody wstrzymania zamówień**.</span><span class="sxs-lookup"><span data-stu-id="c3412-110">Sales order hold codes are configured at **Sales and marketing** &gt; **Setup** &gt; **Sales orders** &gt; **Order holds codes**.</span></span> <span data-ttu-id="c3412-111">Zamówienie sprzedaży może być wstrzymywane ręcznie w chwili utworzenia zamówienia lub później.</span><span class="sxs-lookup"><span data-stu-id="c3412-111">A sales order can be put on hold manually at the time of order creation or later.</span></span> <span data-ttu-id="c3412-112">Oprócz tego zamówienie można wstrzymać automatycznie na podstawie reguł dotyczących oszustw.</span><span class="sxs-lookup"><span data-stu-id="c3412-112">Additionally, an order can be put on hold automatically, based on fraud rules.</span></span> <span data-ttu-id="c3412-113">Gdy zamówienie sprzedaży jest wstrzymane, konieczne może być zaktualizowanie go o dodatkowe informacje.</span><span class="sxs-lookup"><span data-stu-id="c3412-113">While a sales order is on hold, you might have to update it with more information.</span></span> <span data-ttu-id="c3412-114">Można również sprawdzić zamówienie sprzedaży podczas kontynuowania pracy nad nim.</span><span class="sxs-lookup"><span data-stu-id="c3412-114">Alternatively, you might want to check out the sales order as you continue to work on it.</span></span> <span data-ttu-id="c3412-115">Zamówienie sprzedaży można wyewidencjonować, ponownie zaewidencjonować, a nawet zastąpić wyewidencjonowanie go przez innego użytkownika. Służy do tego pulpit wstrzymywania zamówień (**Handel detaliczny** &gt; **Odbiorcy** &gt; **Wstrzymania zamówień**).</span><span class="sxs-lookup"><span data-stu-id="c3412-115">You can check out a sales order, check it back in, and even override the checkout of another user by using the order hold workbench (**Retail** &gt; **Customers** &gt; **Order holds**).</span></span> <span data-ttu-id="c3412-116">Gdy zamówienie jest gotowe do wykonania, należy usunąć wstrzymanie przed zakończeniem procesu zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c3412-116">When an order is ready to be completed, you must remove the hold before you can complete the order process.</span></span>




