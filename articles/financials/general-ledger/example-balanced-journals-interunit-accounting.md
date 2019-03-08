---
title: Zbilansowane arkusze dla księgowania międzyjednostkowego
description: W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b596a2332a9ada01df7b4e718a79eb624ee52fc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "326775"
---
# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="405b5-103">Zbilansowane arkusze dla księgowania międzyjednostkowego</span><span class="sxs-lookup"><span data-stu-id="405b5-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="405b5-104">W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga.</span><span class="sxs-lookup"><span data-stu-id="405b5-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="405b5-105">Jeśli zapisy na koncie nie bilansują się na poziomie wartości wymiaru finansowego, zapisy dodatkowe konta są tworzone automatycznie do zrównoważenia arkusza.</span><span class="sxs-lookup"><span data-stu-id="405b5-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="405b5-106">Te zapisy na kontach używają typów księgowania **Międzyjednostkowe — debet** i**Międzyjednostkowe — kredyt** na stronie **kont dla transakcji automatycznych** w celu określenia konta głównego.</span><span class="sxs-lookup"><span data-stu-id="405b5-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="405b5-107">Na przykład: jednostka biznesowa, czyli drugi segment konta księgowego, jest wybrany jako wymiar finansowy bilansowania i trzeba utworzyć następujące wpisy księgowe.</span><span class="sxs-lookup"><span data-stu-id="405b5-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="405b5-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="405b5-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="405b5-109">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="405b5-109">100.00 DR</span></span> |
| <span data-ttu-id="405b5-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="405b5-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="405b5-111">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="405b5-111">100.00 DR</span></span> |
| <span data-ttu-id="405b5-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="405b5-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="405b5-113">200,00 CR</span><span class="sxs-lookup"><span data-stu-id="405b5-113">200.00 CR</span></span> |

<span data-ttu-id="405b5-114">W tym przypadku określane są następujące salda:</span><span class="sxs-lookup"><span data-stu-id="405b5-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="405b5-115">Dla jednostki biznesowej MSP = 100,00 CR</span><span class="sxs-lookup"><span data-stu-id="405b5-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="405b5-116">Dla jednostki biznesowej NY = 100,00 DR</span><span class="sxs-lookup"><span data-stu-id="405b5-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="405b5-117">Dlatego następujące wpisy księgowe są tworzone automatycznie w celu zbilansowania arkusza na poziomie wartości wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="405b5-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="405b5-118">(Międzyjednostkowe — debet) – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="405b5-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="405b5-119">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="405b5-119">100.00 DR</span></span> |
| <span data-ttu-id="405b5-120">(Międzyjednostkowe — kredyt) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="405b5-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="405b5-121">100,00 CR</span><span class="sxs-lookup"><span data-stu-id="405b5-121">100.00 CR</span></span> |





