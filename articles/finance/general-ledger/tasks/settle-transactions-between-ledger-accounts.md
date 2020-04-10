---
title: Rozliczanie transakcji między kontami księgowymi
description: W tej procedurze pokazano, jak rozliczać transakcje między kontami księgowymi oraz anulować rozliczenie księgi.
author: aprilolson
manager: AnnBe
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb53e9fee35712343f034389f00f3d4539cc652d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144681"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="e92ef-103">Rozliczanie transakcji między kontami księgowymi</span><span class="sxs-lookup"><span data-stu-id="e92ef-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e92ef-104">W tej procedurze pokazano, jak rozliczać transakcje między kontami księgowymi oraz anulować rozliczenie księgi.</span><span class="sxs-lookup"><span data-stu-id="e92ef-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="e92ef-105">Procedura wykorzystuje dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e92ef-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="e92ef-106">Rozliczanie transakcji między kontami księgowymi</span><span class="sxs-lookup"><span data-stu-id="e92ef-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="e92ef-107">Wybierz kolejno opcje Księga główna > Zadania okresowe > Rozliczenia księgi.</span><span class="sxs-lookup"><span data-stu-id="e92ef-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="e92ef-108">Na liście znajdź transakcję, którą chcesz rozliczyć.</span><span class="sxs-lookup"><span data-stu-id="e92ef-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e92ef-109">Saldo kwot musi być równe zero.</span><span class="sxs-lookup"><span data-stu-id="e92ef-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="e92ef-110">Kliknij przycisk Uwzględnij.</span><span class="sxs-lookup"><span data-stu-id="e92ef-110">Click Include.</span></span>
4. <span data-ttu-id="e92ef-111">Kliknij przycisk Akceptuj.</span><span class="sxs-lookup"><span data-stu-id="e92ef-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="e92ef-112">Anulowanie rozliczenia księgi</span><span class="sxs-lookup"><span data-stu-id="e92ef-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="e92ef-113">Wybierz kolejno opcje > Księga główna > Zapytania i raporty > Bilans próbny.</span><span class="sxs-lookup"><span data-stu-id="e92ef-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="e92ef-114">Kliknij przycisk Parametry, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="e92ef-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="e92ef-115">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="e92ef-115">Click Update.</span></span>
4. <span data-ttu-id="e92ef-116">Na liście znajdź konto zawierające rozliczoną transakcję.</span><span class="sxs-lookup"><span data-stu-id="e92ef-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="e92ef-117">Kliknij opcję Wszystkie transakcje.</span><span class="sxs-lookup"><span data-stu-id="e92ef-117">Click All transactions.</span></span>
6. <span data-ttu-id="e92ef-118">Użyj filtru, aby łatwo odnaleźć transakcję na liście.</span><span class="sxs-lookup"><span data-stu-id="e92ef-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="e92ef-119">Kliknij opcję Rozliczenia księgi.</span><span class="sxs-lookup"><span data-stu-id="e92ef-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="e92ef-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e92ef-120">In the list, mark the selected row.</span></span>

