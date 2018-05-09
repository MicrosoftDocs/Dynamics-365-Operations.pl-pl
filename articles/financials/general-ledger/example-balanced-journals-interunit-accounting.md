---
title: "Zbilansowane arkusze dla księgowania międzyjednostkowego"
description: "W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga."
author: twheeloc
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 208b61d9774c2594767cec4733efc552a30da5cc
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="ae119-103">Zbilansowane arkusze dla księgowania międzyjednostkowego</span><span class="sxs-lookup"><span data-stu-id="ae119-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae119-104">W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga.</span><span class="sxs-lookup"><span data-stu-id="ae119-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="ae119-105">Jeśli zapisy na koncie nie bilansują się na poziomie wartości wymiaru finansowego, zapisy dodatkowe konta są tworzone automatycznie do zrównoważenia arkusza.</span><span class="sxs-lookup"><span data-stu-id="ae119-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="ae119-106">Te zapisy na kontach używają typów księgowania **Międzyjednostkowe — debet** i**Międzyjednostkowe — kredyt** na stronie **kont dla transakcji automatycznych** w celu określenia konta głównego.</span><span class="sxs-lookup"><span data-stu-id="ae119-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="ae119-107">Na przykład: jednostka biznesowa, czyli drugi segment konta księgowego, jest wybrany jako wymiar finansowy bilansowania i trzeba utworzyć następujące wpisy księgowe.</span><span class="sxs-lookup"><span data-stu-id="ae119-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="ae119-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="ae119-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="ae119-109">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="ae119-109">100.00 DR</span></span> |
| <span data-ttu-id="ae119-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="ae119-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="ae119-111">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="ae119-111">100.00 DR</span></span> |
| <span data-ttu-id="ae119-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="ae119-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="ae119-113">200,00 CR</span><span class="sxs-lookup"><span data-stu-id="ae119-113">200.00 CR</span></span> |

<span data-ttu-id="ae119-114">W tym przypadku określane są następujące salda:</span><span class="sxs-lookup"><span data-stu-id="ae119-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="ae119-115">Dla jednostki biznesowej MSP = 100,00 CR</span><span class="sxs-lookup"><span data-stu-id="ae119-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="ae119-116">Dla jednostki biznesowej NY = 100,00 DR</span><span class="sxs-lookup"><span data-stu-id="ae119-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="ae119-117">Dlatego następujące wpisy księgowe są tworzone automatycznie w celu zbilansowania arkusza na poziomie wartości wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="ae119-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="ae119-118">(Międzyjednostkowe — debet) – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="ae119-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="ae119-119">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="ae119-119">100.00 DR</span></span> |
| <span data-ttu-id="ae119-120">(Międzyjednostkowe — kredyt) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="ae119-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="ae119-121">100,00 CR</span><span class="sxs-lookup"><span data-stu-id="ae119-121">100.00 CR</span></span> |






