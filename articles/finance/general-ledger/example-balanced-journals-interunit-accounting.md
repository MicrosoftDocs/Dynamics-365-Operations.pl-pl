---
title: Zbilansowane arkusze dla księgowania międzyjednostkowego
description: W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga.
author: ShylaThompson
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5a926adcc631ec286f37796713466eb0144494c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818399"
---
# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="dd164-103">Zbilansowane arkusze dla księgowania międzyjednostkowego</span><span class="sxs-lookup"><span data-stu-id="dd164-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd164-104">W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga.</span><span class="sxs-lookup"><span data-stu-id="dd164-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="dd164-105">Jeśli zapisy na koncie nie bilansują się na poziomie wartości wymiaru finansowego, zapisy dodatkowe konta są tworzone automatycznie do zrównoważenia arkusza.</span><span class="sxs-lookup"><span data-stu-id="dd164-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="dd164-106">Te zapisy na kontach używają typów księgowania **Międzyjednostkowe — debet** i **Międzyjednostkowe — kredyt** na stronie **kont dla transakcji automatycznych** w celu określenia konta głównego.</span><span class="sxs-lookup"><span data-stu-id="dd164-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="dd164-107">Na przykład: jednostka biznesowa, czyli drugi segment konta księgowego, jest wybrany jako wymiar finansowy bilansowania i trzeba utworzyć następujące wpisy księgowe.</span><span class="sxs-lookup"><span data-stu-id="dd164-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

| &nbsp;               | &nbsp;    |
|----------------------|-----------|
| <span data-ttu-id="dd164-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="dd164-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="dd164-109">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="dd164-109">100.00 DR</span></span> |
| <span data-ttu-id="dd164-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="dd164-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="dd164-111">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="dd164-111">100.00 DR</span></span> |
| <span data-ttu-id="dd164-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="dd164-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="dd164-113">200,00 CR</span><span class="sxs-lookup"><span data-stu-id="dd164-113">200.00 CR</span></span> |

<span data-ttu-id="dd164-114">W tym przypadku określane są następujące salda:</span><span class="sxs-lookup"><span data-stu-id="dd164-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="dd164-115">Dla jednostki biznesowej MSP = 100,00 CR</span><span class="sxs-lookup"><span data-stu-id="dd164-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="dd164-116">Dla jednostki biznesowej NY = 100,00 DR</span><span class="sxs-lookup"><span data-stu-id="dd164-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="dd164-117">Dlatego następujące wpisy księgowe są tworzone automatycznie w celu zbilansowania arkusza na poziomie wartości wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="dd164-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

| &nbsp;                            | &nbsp;    |
|-----------------------------------|-----------|
| <span data-ttu-id="dd164-118">(Międzyjednostkowe — debet) – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="dd164-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="dd164-119">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="dd164-119">100.00 DR</span></span> |
| <span data-ttu-id="dd164-120">(Międzyjednostkowe — kredyt) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="dd164-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="dd164-121">100,00 CR</span><span class="sxs-lookup"><span data-stu-id="dd164-121">100.00 CR</span></span> |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]