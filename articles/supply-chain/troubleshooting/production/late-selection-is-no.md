---
title: Jeżeli zlecenia produkcyjne są wyzerowane za pomocą zadania wsadowego, nie sąsprawiedliwne zaznaczenie opcji późnego wyboru
description: Jeśli do zresetowania stanu zlecenia produkcyjnego jest używać cyklicznego zadania wsadowego, wybór opóźnionych wyborów nie jest przestrzegany.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e53198f427f4060421a4f0078277682c43db1320
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026807"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a><span data-ttu-id="6200d-103">Jeżeli zlecenia produkcyjne są wyzerowane za pomocą zadania wsadowego, nie sąsprawiedliwne zaznaczenie opcji późnego wyboru</span><span class="sxs-lookup"><span data-stu-id="6200d-103">Late selection isn't respected when production orders are reset via a batch job</span></span>

<span data-ttu-id="6200d-104">Numer artykułu z bazy wiedzy: 4614634</span><span class="sxs-lookup"><span data-stu-id="6200d-104">KB number: 4614634</span></span>

## <a name="symptoms"></a><span data-ttu-id="6200d-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="6200d-105">Symptoms</span></span>

<span data-ttu-id="6200d-106">Jeśli do zresetowania stanu zlecenia produkcyjnego jest używać cyklicznego zadania wsadowego, wybór opóźnionych wyborów nie jest przestrzegany.</span><span class="sxs-lookup"><span data-stu-id="6200d-106">When you use a recurring batch job to reset the status of a production order, late selections aren't respected.</span></span>

## <a name="resolution"></a><span data-ttu-id="6200d-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="6200d-107">Resolution</span></span>

<span data-ttu-id="6200d-108">Bieżący projekt nie obsługuje funkcji późnego wyboru w procesie *Resetowania stanu*.</span><span class="sxs-lookup"><span data-stu-id="6200d-108">The current design doesn't support the use of late selections for the *Reset status* process.</span></span>
