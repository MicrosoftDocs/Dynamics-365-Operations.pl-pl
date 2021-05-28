---
title: Nie można zafakturć zamówienia sprzedaży dla odbiorcy
description: Po włączeniu opcji Automatyczne księguj fakturę nie można już zafakturowania oryginalnego zamówienia sprzedaży i zamówienia zakupu z oryginalną dostawą bezpośrednią.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026809"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a><span data-ttu-id="dea2b-103">Nie można zafakturć zamówienia sprzedaży dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="dea2b-103">You can't invoice a customer-facing sales order</span></span>

<span data-ttu-id="dea2b-104">Numer artykułu z bazy wiedzy: 4611793</span><span class="sxs-lookup"><span data-stu-id="dea2b-104">KB number: 4611793</span></span>

## <a name="symptoms"></a><span data-ttu-id="dea2b-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="dea2b-105">Symptoms</span></span>

<span data-ttu-id="dea2b-106">Po włączeniu opcji **Automatyczne księgowanie faktury** na stronie **Międzyfirmowe** dla dostawcy nie można już fakturować oryginalnego zamówienia sprzedaży i oryginalnego zamówienia zakupu z dostawą bezpośrednią.</span><span class="sxs-lookup"><span data-stu-id="dea2b-106">You can no longer invoice the original sales order and the original direct delivery purchase order after you enable the **Post invoice automatically** option on the **Intercompany** page for a vendor.</span></span>

## <a name="resolution"></a><span data-ttu-id="dea2b-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="dea2b-107">Resolution</span></span>

<span data-ttu-id="dea2b-108">Zachowanie synchronizacji dla faktur międzyfirmowych i faktur z zamówieniem dostawy bezpośredniej jest kontrolowane i wymuszane przez parametry opisane w sekcji [Konfigurowanie parametrów w celu zaksięgowania zamówienia międzyfirmowego](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span><span class="sxs-lookup"><span data-stu-id="dea2b-108">The synchronization behavior for intercompany and direct delivery order invoices is controlled and forced by the parameters that are described in [Set up parameters to post an intercompany order](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span></span>

<span data-ttu-id="dea2b-109">Po skonfigurowaniu tych parametrów należy najpierw międzyfirmowe zamówienie sprzedaży fakturę.</span><span class="sxs-lookup"><span data-stu-id="dea2b-109">After you set those parameters, you must invoice the intercompany sales order first.</span></span> <span data-ttu-id="dea2b-110">Oryginalne zamówienia sprzedaży i zakupu zostaną zsynchronizowane.</span><span class="sxs-lookup"><span data-stu-id="dea2b-110">The original sales orders and purchase orders will then be synchronized.</span></span>
