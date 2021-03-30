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
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5f73606708b8c32a7a8ebc364af6ba57c4c343
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205530"
---
# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="0493a-103">Zbilansowane arkusze dla księgowania międzyjednostkowego</span><span class="sxs-lookup"><span data-stu-id="0493a-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0493a-104">W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga.</span><span class="sxs-lookup"><span data-stu-id="0493a-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="0493a-105">Jeśli zapisy na koncie nie bilansują się na poziomie wartości wymiaru finansowego, zapisy dodatkowe konta są tworzone automatycznie do zrównoważenia arkusza.</span><span class="sxs-lookup"><span data-stu-id="0493a-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="0493a-106">Te zapisy na kontach używają typów księgowania **Międzyjednostkowe — debet** i **Międzyjednostkowe — kredyt** na stronie **kont dla transakcji automatycznych** w celu określenia konta głównego.</span><span class="sxs-lookup"><span data-stu-id="0493a-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="0493a-107">Na przykład: jednostka biznesowa, czyli drugi segment konta księgowego, jest wybrany jako wymiar finansowy bilansowania i trzeba utworzyć następujące wpisy księgowe.</span><span class="sxs-lookup"><span data-stu-id="0493a-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="0493a-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="0493a-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="0493a-109">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="0493a-109">100.00 DR</span></span> |
| <span data-ttu-id="0493a-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="0493a-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="0493a-111">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="0493a-111">100.00 DR</span></span> |
| <span data-ttu-id="0493a-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="0493a-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="0493a-113">200,00 CR</span><span class="sxs-lookup"><span data-stu-id="0493a-113">200.00 CR</span></span> |

<span data-ttu-id="0493a-114">W tym przypadku określane są następujące salda:</span><span class="sxs-lookup"><span data-stu-id="0493a-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="0493a-115">Dla jednostki biznesowej MSP = 100,00 CR</span><span class="sxs-lookup"><span data-stu-id="0493a-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="0493a-116">Dla jednostki biznesowej NY = 100,00 DR</span><span class="sxs-lookup"><span data-stu-id="0493a-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="0493a-117">Dlatego następujące wpisy księgowe są tworzone automatycznie w celu zbilansowania arkusza na poziomie wartości wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="0493a-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="0493a-118">(Międzyjednostkowe — debet) – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="0493a-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="0493a-119">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="0493a-119">100.00 DR</span></span> |
| <span data-ttu-id="0493a-120">(Międzyjednostkowe — kredyt) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="0493a-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="0493a-121">100,00 CR</span><span class="sxs-lookup"><span data-stu-id="0493a-121">100.00 CR</span></span> |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]