---
title: Okna czasu
description: Okna czasu umożliwiają optymalizowanie planowania wierszy zleceń serwisowych.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d79e3d3756b8dc402d6f293437209b2e108be38e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435383"
---
# <a name="time-windows"></a><span data-ttu-id="d8ea5-103">Okna czasu</span><span class="sxs-lookup"><span data-stu-id="d8ea5-103">Time windows</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8ea5-104">Okna czasu umożliwiają optymalizowanie planowania wierszy zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-104">You can use time windows to optimize the scheduling of service order lines.</span></span> <span data-ttu-id="d8ea5-105">Istnieje możliwość takiego skonfigurowania systemu, aby automatycznie tworzył zlecenia serwisowe.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-105">You can set up the system so that it automatically creates service orders.</span></span> <span data-ttu-id="d8ea5-106">Na podstawie kryteriów określonych przez okno czasu można połączyć jak największą liczbę wierszy zleceń serwisowych z jak najmniejszą liczbą zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-106">Based on the criteria specified by a time window, you can connect as many service order lines as possible to as few service orders as possible.</span></span>

<span data-ttu-id="d8ea5-107">Okna czasu określają, jak daleko może zostać przesunięty wiersz zlecenia serwisowego względem obliczonej daty.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-107">Time windows specify how far a service order line can move from its calculated date.</span></span> <span data-ttu-id="d8ea5-108">Obliczona data określa, kiedy według harmonogramu ma zostać wykonany wiersz zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-108">The calculated date is the date when the service order line was scheduled to occur.</span></span> <span data-ttu-id="d8ea5-109">Data bazuje na ustawieniu interwału i okresie serwisu podanym na stronie **Tworzenie zleceń serwisowych**.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-109">The date is based on its interval setting and the service period that you defined in the **Create service orders** page.</span></span> <span data-ttu-id="d8ea5-110">Okno czasu definiuje się za pomocą wartości z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-110">You define a time window by using the values in the following table.</span></span>

| <span data-ttu-id="d8ea5-111">Metoda</span><span class="sxs-lookup"><span data-stu-id="d8ea5-111">Method</span></span> | <span data-ttu-id="d8ea5-112">opis</span><span class="sxs-lookup"><span data-stu-id="d8ea5-112">Description</span></span>                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d8ea5-113">Tydzień</span><span class="sxs-lookup"><span data-stu-id="d8ea5-113">Week</span></span>   | <span data-ttu-id="d8ea5-114">Dowolny otwarty dzień w tym samym tygodniu, w którym wypada początkowa obliczona data, do którego można przenieść wiersz zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-114">The date that the service order line can be moved to any open day in the same week as the initial calculated date.</span></span>                                                                                                                                                                                    |
| <span data-ttu-id="d8ea5-115">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="d8ea5-115">Month</span></span>  | <span data-ttu-id="d8ea5-116">Dowolny otwarty dzień w tym samym miesiącu, w którym wypada początkowa obliczona data, do którego można przenieść wiersz zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-116">The date that the service order line can be moved to any open day in the same month as the initial calculated date.</span></span> <span data-ttu-id="d8ea5-117">Na przykład obliczoną datą wiersza zlecenia serwisowego jest 15 lutego 2017 r.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-117">For example, the calculated date for a service order line is February 15, 2017.</span></span> <span data-ttu-id="d8ea5-118">Wiersz zlecenia serwisowego można zaplanować na dowolny dzień roboczy między 1 lutego a 28 lutego 2017 r.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-118">The service order line can be scheduled for any weekday between February 1 and February 28, 2017.</span></span> |
| <span data-ttu-id="d8ea5-119">Ręczny</span><span class="sxs-lookup"><span data-stu-id="d8ea5-119">Manual</span></span> | <span data-ttu-id="d8ea5-120">Należy określić maksymalną liczbę dni przed początkową obliczoną datą i po niej, o jaką może zostać przesunięty wiersz zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-120">You define the maximum number of days before or after the initial calculated date that the service order line can be moved.</span></span>                                                                                                                                                                           |

<span data-ttu-id="d8ea5-121">Jeśli nie określisz okna czasu dla wiersza umowy serwisowej, wiersz zlecenia serwisowego wygenerowany na podstawie tej umowy serwisowej musi zostać wykonany dokładnie w dniu, na który został pierwotnie zaplanowany.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-121">If you do not specify a time window for a service agreement line, the service order line that is derived from the service agreement must be on the exact date for which it was originally scheduled.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8ea5-122">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="d8ea5-122">Related topics</span></span>

[<span data-ttu-id="d8ea5-123">Tworzenie okien czasowych</span><span class="sxs-lookup"><span data-stu-id="d8ea5-123">Create time windows</span></span>](create-time-windows.md)

