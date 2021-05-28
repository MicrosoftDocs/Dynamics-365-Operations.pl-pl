---
title: Fizycznie odebrane zamówienia zakupu nie są widoczne w raporcie zamknięcia magazynu
description: Fizycznie otrzymane zamówienia zakupu nie pojawiają się w raporcie zamknięcia zapasów Sprawdź otwarte ilości.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026813"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a><span data-ttu-id="f6a31-103">Fizycznie odebrane zamówienia zakupu nie są widoczne w raporcie zamknięcia magazynu</span><span class="sxs-lookup"><span data-stu-id="f6a31-103">Physically received purchase orders don't appear on the inventory closing report</span></span>

<span data-ttu-id="f6a31-104">Numer artykułu z bazy wiedzy: 4612595</span><span class="sxs-lookup"><span data-stu-id="f6a31-104">KB number: 4612595</span></span>

## <a name="symptoms"></a><span data-ttu-id="f6a31-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="f6a31-105">Symptoms</span></span>

<span data-ttu-id="f6a31-106">Fizycznie otrzymane zamówienia zakupu nie pojawiają się w raporcie zamknięcia zapasów **Sprawdź otwarte ilości**.</span><span class="sxs-lookup"><span data-stu-id="f6a31-106">Physically received purchase orders don't appear on the **Check open quantities** inventory closing report.</span></span>

## <a name="resolution"></a><span data-ttu-id="f6a31-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="f6a31-107">Resolution</span></span>

<span data-ttu-id="f6a31-108">Raport **Sprawdź otwarte ilości** zawiera transakcje rozliczeń, których nie można rozliczyć względem finansowo zaktualizowanych przychodów magazynowych dla wybranej daty zamknięcia.</span><span class="sxs-lookup"><span data-stu-id="f6a31-108">The **Check open quantities** report shows issue transactions that can't be settled against financially updated inventory receipts as of the selected closing date.</span></span> <span data-ttu-id="f6a31-109">Można wybrać opcję uwzględniania w raporcie fizycznego przychodu.</span><span class="sxs-lookup"><span data-stu-id="f6a31-109">You can choose to include physical receipts on the report.</span></span> <span data-ttu-id="f6a31-110">W takim przypadku fizyczne przychody zostaną wyświetlone, jeśli będą pokrywały transakcje rozliczeniowe, których nie można rozliczyć.</span><span class="sxs-lookup"><span data-stu-id="f6a31-110">In that case, physical receipts will be shown if they can cover the issue transactions that can't be settled.</span></span> <span data-ttu-id="f6a31-111">Aby uzyskać więcej informacji, zobacz [Przygotowanie do przeprowadzenia zamknięcia magazynu](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span><span class="sxs-lookup"><span data-stu-id="f6a31-111">For more information, see [Preparing to run inventory close](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span></span>
