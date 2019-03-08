---
title: Wydatki osobiste w raporcie wydatków
description: W tym temacie opisano dwie metody obsługi wydatków osobistych pracownika w Microsoft Dynamics 365 for Finance and Operations.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a6b6c505e7dc5e6544658b00d9f59e6062353608
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "344899"
---
# <a name="personal-expenses-on-an-expense-report"></a><span data-ttu-id="b00b1-103">Wydatki osobiste w raporcie z wydatków</span><span class="sxs-lookup"><span data-stu-id="b00b1-103">Personal expenses on an expense report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b00b1-104">Podczas podróży służbowej pracownik może czasami obciążać firmową kartę kredytową swoimi osobistymi wydatkami.</span><span class="sxs-lookup"><span data-stu-id="b00b1-104">During business travel, workers might sometimes charge personal expenses to their corporate credit cards.</span></span> <span data-ttu-id="b00b1-105">Jeśli nie zdefiniujesz procesu obsługi wydatków osobistych, proces zatwierdzania raportów z wydatków może zostać zakłócony, gdy pracownicy składają szczegółowe raporty z wydatków.</span><span class="sxs-lookup"><span data-stu-id="b00b1-105">If you don't define a process for handling personal expenses, the approval process for expense reports might be disrupted when workers submit their itemized expense reports.</span></span> 

<span data-ttu-id="b00b1-106">W Microsoft Dynamics 365 for Finance and Operations dostępne są dwie metody obsługi wydatków osobistych pracownika:</span><span class="sxs-lookup"><span data-stu-id="b00b1-106">In Microsoft Dynamics 365 for Finance and Operations, there are two methods for handling a worker's personal expenses:</span></span>

- <span data-ttu-id="b00b1-107">**Zapłacone przez pracownika etatowego** — organizacja nie pokrywa wydatków osobistych, które pojawiają się na wyciągu z konta firmowej karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="b00b1-107">**Paid by employee** – Your organization doesn't pay personal expenses that appear on the bill for the corporate credit card.</span></span> <span data-ttu-id="b00b1-108">Zamiast tego jest tworzony raport, który pokazuje wydatki osobiste wraz z wydatkami firmowymi obciążającymi firmową kartę kredytową.</span><span class="sxs-lookup"><span data-stu-id="b00b1-108">Instead, it creates a report that shows personal expenses together with the corporate expenses that were charged to the corporate credit card.</span></span>
- <span data-ttu-id="b00b1-109">**Zapłacone przez firmę** — firma płaci całe saldo wyciągu z rachunku firmowej karty kredytowej, a następnie obciąża konto pracownika kwotą wydatków osobistych.</span><span class="sxs-lookup"><span data-stu-id="b00b1-109">**Paid by company** – Your organization pays the whole bill for the corporate credit card and then debits the worker's account for the personal expenses.</span></span>

<span data-ttu-id="b00b1-110">Metodę używaną przez organizację można zaznaczyć na stronie **Parametry zarządzania wydatkami**.</span><span class="sxs-lookup"><span data-stu-id="b00b1-110">You can select the method that your organization uses on the **Expense management parameters** page.</span></span>
