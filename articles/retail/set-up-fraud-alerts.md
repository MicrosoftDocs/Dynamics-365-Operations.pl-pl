---
title: "Ustawianie alertów o oszustwie"
description: "W tym temacie wyjaśniono sposób konfigurowania reguł powiadomień dla działu obsługi klienta o potencjalnie fałszywych informacjach przy przetwarzaniu zamówień. Można zdefiniować określone kody, które będą używane do automatycznego lub ręcznego wstrzymania podejrzanych zamówień."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09d80015298c3d0219b6ffb290dc456990536a62
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-fraud-alerts"></a><span data-ttu-id="83536-104">Ustawianie alertów o oszustwie</span><span class="sxs-lookup"><span data-stu-id="83536-104">Set up fraud alerts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="83536-105">W tym temacie wyjaśniono sposób konfigurowania reguł powiadomień dla działu obsługi klienta o potencjalnie fałszywych informacjach przy przetwarzaniu zamówień.</span><span class="sxs-lookup"><span data-stu-id="83536-105">This topic explains how to set up rules to alert customer service representatives of potentially fraudulent information when orders are processed.</span></span> <span data-ttu-id="83536-106">Można zdefiniować określone kody, które będą używane do automatycznego lub ręcznego wstrzymania podejrzanych zamówień.</span><span class="sxs-lookup"><span data-stu-id="83536-106">You can define specific codes to use to automatically or manually put suspicious orders on hold.</span></span> 

<span data-ttu-id="83536-107">Aby skonfigurować i używać reguł sprawdzania oszustwa, należy włączyć sprawdzanie oszustwa i zdefiniować podstawowe wartości sprawdzania oszustwa w parametrach biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="83536-107">Before you set up and use fraud checking rules, you must enable fraud checking and define the basic fraud checking values in the call center parameters.</span></span> <span data-ttu-id="83536-108">Istnieją dwa typy reguł dotyczących oszustw:</span><span class="sxs-lookup"><span data-stu-id="83536-108">There are two types of fraud rules:</span></span>

-   <span data-ttu-id="83536-109">**Reguły statyczne** używaj konkretnych wartości, np. numeru telefonu, który znajduje się na czarnej liście.</span><span class="sxs-lookup"><span data-stu-id="83536-109">**Static rules** use a specific value, such as a phone number that has been blacklisted.</span></span>
-   <span data-ttu-id="83536-110">**Reguły dynamiczne** mogą składać ze zmiennych i warunków.</span><span class="sxs-lookup"><span data-stu-id="83536-110">**Dynamic rules** can be composed from variables and conditions.</span></span>

<span data-ttu-id="83536-111">Aby utworzyć regułę dynamiczną, należy najpierw utworzyć zmienne i warunki określające, czego dotyczy reguła i kiedy ma być stosowana.</span><span class="sxs-lookup"><span data-stu-id="83536-111">Before you create a dynamic rule, you must create the variables and conditions that define who the rule applies to and when the rule should be applied.</span></span> <span data-ttu-id="83536-112">Na przykład użytkownik chce utworzyć regułę, która wymaga, by każde zamówienie sprzedaży składane przez odbiorcę 1202 o wartości 1000,00 lub większej musi być wstrzymywane do czasu zweryfikowania płatności odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="83536-112">For example, you want to create a rule to require that any sales order that customer 1202 places that is worth 1,000.00 or more be put on hold until the customer payment can be verified.</span></span> <span data-ttu-id="83536-113">W tym przypadku zmiennymi są odbiorca 1202 i 1000,00 jako suma zamówienia.</span><span class="sxs-lookup"><span data-stu-id="83536-113">In this case, the variables are customer 1202 and an order total of 1,000.00.</span></span> <span data-ttu-id="83536-114">Warunek określa, czy jeśli odbiorca 1202 złoży zamówienie i łączna suma zamówienia wynosi 1000,00 lub jest wyższa od tej kwoty, zamówienie sprzedaży musi być wstrzymywane do chwili sprawdzenia płatności odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="83536-114">The condition specifies that if customer 1202 places an order, and the total amount of the order is equal to or more than 1,000.00, the sales order must be put on hold until the customer payment can be verified.</span></span>




