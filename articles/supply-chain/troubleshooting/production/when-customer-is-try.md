---
title: Numer partii jest czyszowany po wybraniu nowego identyfikatora partii
description: Podczas przeglądania wiersza arkusza listy pobrania wartość w polu Numer partii jest czyszowana po wybraniu nowej wartości w polu Identyfikator partii.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026798"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a><span data-ttu-id="54abe-103">Numer partii jest czyszowany po wybraniu nowego identyfikatora partii</span><span class="sxs-lookup"><span data-stu-id="54abe-103">Batch number is cleared when a new lot ID is selected</span></span>

<span data-ttu-id="54abe-104">Numer artykułu z bazy wiedzy: 4613107</span><span class="sxs-lookup"><span data-stu-id="54abe-104">KB number: 4613107</span></span>

## <a name="symptoms"></a><span data-ttu-id="54abe-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="54abe-105">Symptoms</span></span>

<span data-ttu-id="54abe-106">Podczas przeglądania wiersza arkusza listy pobrania wartość w polu **Numer partii** jest czyszowana po wybraniu nowej wartości w polu **Identyfikator partii**.</span><span class="sxs-lookup"><span data-stu-id="54abe-106">When you're reviewing a picking list journal line, the value in the **Batch number** field is cleared if you select a new value in the **Lot ID** field.</span></span>

## <a name="resolution"></a><span data-ttu-id="54abe-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="54abe-107">Resolution</span></span>

<span data-ttu-id="54abe-108">System jest szybując tak jak zaprojektowany.</span><span class="sxs-lookup"><span data-stu-id="54abe-108">The system is behaving as designed.</span></span> <span data-ttu-id="54abe-109">Zmiana identyfikatora partii umożliwia zmianę kontekstu towaru.</span><span class="sxs-lookup"><span data-stu-id="54abe-109">If you change the lot ID, you change the item context.</span></span> <span data-ttu-id="54abe-110">W związku z tym numer partii jest resetowany.</span><span class="sxs-lookup"><span data-stu-id="54abe-110">Therefore, the batch number is reset.</span></span>

<span data-ttu-id="54abe-111">Aby skojarzyć numer partii z identyfikatorem partii, musisz najpierw ustawić identyfikator partii.</span><span class="sxs-lookup"><span data-stu-id="54abe-111">To associate the batch number with a lot ID, you must set the lot ID first.</span></span>
