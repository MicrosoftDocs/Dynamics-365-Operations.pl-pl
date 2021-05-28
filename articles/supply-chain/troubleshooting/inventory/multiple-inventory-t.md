---
title: Wiele transakcji magazynowych dla numerów partii, gdy aktualizacja fizyczna jest wyłączona
description: Po skorygowaniu wiersza zamówienia zakupu dla towarów, dla których w opcji Aktualizacji fizycznej w grupie numerów partii ustawiono wartość Nie, tworzona jest wiele transakcji magazynowych.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026827"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a><span data-ttu-id="c8862-103">Wiele transakcji magazynowych dla numerów partii, gdy aktualizacja fizyczna jest wyłączona</span><span class="sxs-lookup"><span data-stu-id="c8862-103">Multiple inventory transactions for batch numbers when On physical update is disabled</span></span>

<span data-ttu-id="c8862-104">Numer artykułu z bazy wiedzy: 4613390</span><span class="sxs-lookup"><span data-stu-id="c8862-104">KB number: 4613390</span></span>

## <a name="symptoms"></a><span data-ttu-id="c8862-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="c8862-105">Symptoms</span></span>

<span data-ttu-id="c8862-106">Po skorygowaniu wiersza zamówienia zakupu dla towarów, dla których w opcji **Aktualizacji fizycznej** w grupie numerów partii ustawiono wartość *Nie*, tworzona jest wiele transakcji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="c8862-106">Multiple inventory transactions are created after you adjust a purchase order line for items where the **On physical update** option of the batch number group is set to *No*.</span></span>

<span data-ttu-id="c8862-107">W przypadku tworzenia towaru, dla którego dla opcji **Aktualizacji fizycznej** w grupie numerów partii jest ustawiona wartość *Nie*, system automatycznie utworzy nowy numer partii w przypadku zmodyfikowania ilości w wierszu zakupu i zapisania strony zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="c8862-107">When you create an item where the **On physical update** option of the batch number group is set to *No*, the system automatically creates a new batch number if you modify a purchase line quantity and save the purchase order page.</span></span>

## <a name="resolution"></a><span data-ttu-id="c8862-108">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="c8862-108">Resolution</span></span>

<span data-ttu-id="c8862-109">Ustawienie **Przy fizycznej aktualizacji** dla grup numerów partii działa następująco:</span><span class="sxs-lookup"><span data-stu-id="c8862-109">The **On physical update** setting for batch number groups works in the following way:</span></span>

- <span data-ttu-id="c8862-110">Gdy jest ustawiona wartość *Tak*, nowe numery partii są tworzone tylko po fizycznej aktualizacji (na przykład przy wysłaniu lub otrzymaniu towaru).</span><span class="sxs-lookup"><span data-stu-id="c8862-110">When the option is set to *Yes*, new batch numbers are created only after a physical update (for example, when items are shipped or received).</span></span>
- <span data-ttu-id="c8862-111">Gdy jest ustawiona wartość *Nie*, nowy numer partii jest tworzony za każdym razem, gdy stosowana jest aktualizacja (na przykład przy dodaniu nowej ilości do zamówienia zakupu).</span><span class="sxs-lookup"><span data-stu-id="c8862-111">When the option is set to *No*, a new batch number is created every time that an applicable update occurs (for example, when a new quantity is added to a purchase order).</span></span>
