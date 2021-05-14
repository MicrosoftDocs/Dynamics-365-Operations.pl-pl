---
title: Ostatnim zamkniętym wierszem pracy musi być Odłożenie
description: Ostatnim zamkniętym wierszem pracy musi być Odłożenie
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924382"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a><span data-ttu-id="95fc6-103">Ostatnim zamkniętym wierszem pracy musi być Odłożenie</span><span class="sxs-lookup"><span data-stu-id="95fc6-103">The last closed work line must be a put</span></span>

<span data-ttu-id="95fc6-104">Kod błędu: WAX1285</span><span class="sxs-lookup"><span data-stu-id="95fc6-104">Error code: WAX1285</span></span>

## <a name="symptoms"></a><span data-ttu-id="95fc6-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="95fc6-105">Symptoms</span></span>

<span data-ttu-id="95fc6-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="95fc6-106">The system shows the following error message:</span></span>

> <span data-ttu-id="95fc6-107">Ostatnim zamkniętym wierszem pracy musi być Odłożenie.</span><span class="sxs-lookup"><span data-stu-id="95fc6-107">The last closed work line must be a put.</span></span>

## <a name="cause"></a><span data-ttu-id="95fc6-108">Powód</span><span class="sxs-lookup"><span data-stu-id="95fc6-108">Cause</span></span>

<span data-ttu-id="95fc6-109">Nie można anulować pracy w jej bieżącym stanie.</span><span class="sxs-lookup"><span data-stu-id="95fc6-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="95fc6-110">W ostatnim wierszu pracy pole **Stan pracy** ma wartość *Zamknięte*, ale pole **Typ pracy** nie ma wartości *Odłożenie*.</span><span class="sxs-lookup"><span data-stu-id="95fc6-110">On the last work line, the **Work status** field is set to *Closed*, but the **Work type** field isn't set to *Put*.</span></span>

## <a name="resolution"></a><span data-ttu-id="95fc6-111">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="95fc6-111">Resolution</span></span>

<span data-ttu-id="95fc6-112">Aby anulować pracę, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="95fc6-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="95fc6-113">Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.</span><span class="sxs-lookup"><span data-stu-id="95fc6-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="95fc6-114">W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować.</span><span class="sxs-lookup"><span data-stu-id="95fc6-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="95fc6-115">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="95fc6-115">Select **OK**.</span></span>
1. <span data-ttu-id="95fc6-116">Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.</span><span class="sxs-lookup"><span data-stu-id="95fc6-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="95fc6-117">Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="95fc6-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
