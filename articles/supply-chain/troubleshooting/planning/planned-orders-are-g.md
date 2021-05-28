---
title: Planowanie główne generuje planowane zamówienia na produkty fantomu
description: Planowane zamówienia są generowane na produkty pozorne po uruchomieniu planowania głównego.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026820"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a><span data-ttu-id="d1fcc-103">Planowanie główne generuje planowane zamówienia na produkty fantomu</span><span class="sxs-lookup"><span data-stu-id="d1fcc-103">Master planning generates planned orders for phantom products</span></span>

<span data-ttu-id="d1fcc-104">Numer artykułu z bazy wiedzy: 4614729</span><span class="sxs-lookup"><span data-stu-id="d1fcc-104">KB number: 4614729</span></span>

## <a name="symptoms"></a><span data-ttu-id="d1fcc-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="d1fcc-105">Symptoms</span></span>

<span data-ttu-id="d1fcc-106">Planowane zamówienia są generowane na produkty pozorne po uruchomieniu planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="d1fcc-106">Planned orders are generated for phantom products after master planning is run.</span></span>

## <a name="resolution"></a><span data-ttu-id="d1fcc-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="d1fcc-107">Resolution</span></span>

<span data-ttu-id="d1fcc-108">Ustawienie opcji **Fantom** dla zwolnionych produktów określa domyślny typ wiersza w BOM.</span><span class="sxs-lookup"><span data-stu-id="d1fcc-108">The setting of the **Phantom** option for released products determines the default line type on the bill of material (BOM).</span></span> <span data-ttu-id="d1fcc-109">Jeśli w ustawieniach opcji **Fantom** jest ustawiona wartość *Tak*, system nadal będzie tworzyć planowane zamówienia dla towaru, ale opcja **Zapotrzebowanie pochodne bezpośrednie** dla każdego planowanego zamówienia będzie mieć wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="d1fcc-109">When the **Phantom** option is set to *Yes*, the system will still create planned orders for the item, but the **Directly derived requirement** option for each planned order will be set to *Yes*.</span></span> <span data-ttu-id="d1fcc-110">W związku planowane zlecenie produkcyjne nie można jej samodzielnie określić.</span><span class="sxs-lookup"><span data-stu-id="d1fcc-110">Therefore, the planned production order can't be firmed on its own.</span></span> <span data-ttu-id="d1fcc-111">Będzie ona natomiast zawsze uwzględniana automatycznie podczas procesów języdzyka produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d1fcc-111">Instead, it will always be automatically included when the parent production order is firmed.</span></span> <span data-ttu-id="d1fcc-112">Ponadto wiersze BOM planowanego zamówienia fantomu zostaną uwzględnione w BOM nadrzędnego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d1fcc-112">Additionally, the BOM lines of the planned phantom order will be included in the BOM of the parent production order.</span></span>
