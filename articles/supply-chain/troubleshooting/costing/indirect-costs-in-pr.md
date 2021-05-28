---
title: Raport Koszty pośrednie w procesie zawiera usunięte zlecenia produkcyjne
description: Raport Koszty pośrednie w procesie zawiera informacje o zleceniach produkcyjnych, które zostały częściowo przetworzone, a później usunięte.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026814"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a><span data-ttu-id="4d902-103">Raport Koszty pośrednie w procesie zawiera usunięte zlecenia produkcyjne</span><span class="sxs-lookup"><span data-stu-id="4d902-103">The Indirect costs in process report includes deleted production orders</span></span>

<span data-ttu-id="4d902-104">Numer artykułu z bazy wiedzy: 4612748</span><span class="sxs-lookup"><span data-stu-id="4d902-104">KB number: 4612748</span></span>

## <a name="symptoms"></a><span data-ttu-id="4d902-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="4d902-105">Symptoms</span></span>

<span data-ttu-id="4d902-106">Raport **Koszty pośrednie w procesie** zawiera informacje o zleceniach produkcyjnych, które zostały częściowo przetworzone, a później usunięte.</span><span class="sxs-lookup"><span data-stu-id="4d902-106">The **Indirect costs in process** report presents information about production orders that were partially processed and later deleted.</span></span>

## <a name="resolution"></a><span data-ttu-id="4d902-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="4d902-107">Resolution</span></span>

<span data-ttu-id="4d902-108">Wycofanie zlecenia produkcyjnego oznacza również wycofanie wszystkich transakcji tego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="4d902-108">When you reverse a production order, you also reverse all the transactions of that production order.</span></span> <span data-ttu-id="4d902-109">Usunięcie zlecenia produkcyjnego spowoduje, że tabele księgi podrzędnej i księga główna utrwalą wszystkie powiązane z nim transakcje.</span><span class="sxs-lookup"><span data-stu-id="4d902-109">When you delete the production order, the subledger tables and general ledger persist all transactions that are related to it.</span></span> <span data-ttu-id="4d902-110">Raporty będą wyświetlać transakcje w tabelach księgi podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="4d902-110">The reports will show the transactions in the subledger tables.</span></span> <span data-ttu-id="4d902-111">Dla określonego zlecenia produkcyjnego wartość netto powinna być 0,00.</span><span class="sxs-lookup"><span data-stu-id="4d902-111">For the specific production order, the net value should be 0.00.</span></span>
