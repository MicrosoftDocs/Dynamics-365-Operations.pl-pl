---
title: Nie można anulować pracy z powodu stanu
description: Nie można anulować pracy z powodu stanu
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
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924262"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a><span data-ttu-id="7fd52-103">Nie można anulować pracy z powodu stanu</span><span class="sxs-lookup"><span data-stu-id="7fd52-103">Work can't be canceled because of its status</span></span>

<span data-ttu-id="7fd52-104">Kod błędu: WAX2190</span><span class="sxs-lookup"><span data-stu-id="7fd52-104">Error code: WAX2190</span></span>

## <a name="symptoms"></a><span data-ttu-id="7fd52-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="7fd52-105">Symptoms</span></span>

<span data-ttu-id="7fd52-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="7fd52-106">The system shows the following error message:</span></span>

> <span data-ttu-id="7fd52-107">Nie możesz anulować pracy %1, ponieważ jej stanem jest %2.</span><span class="sxs-lookup"><span data-stu-id="7fd52-107">You cannot cancel work %1 because it has a status of %2.</span></span>

## <a name="cause"></a><span data-ttu-id="7fd52-108">Powód</span><span class="sxs-lookup"><span data-stu-id="7fd52-108">Cause</span></span>

<span data-ttu-id="7fd52-109">Nie można anulować pracy w jej bieżącym stanie.</span><span class="sxs-lookup"><span data-stu-id="7fd52-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="7fd52-110">Nagłówek pracy lub wiersze pracy nie mają oczekiwanej wartości **Stan pracy**.</span><span class="sxs-lookup"><span data-stu-id="7fd52-110">The work header or work lines don't have the expected **Work status** value.</span></span> <span data-ttu-id="7fd52-111">Pole **Stan pracy** w nagłówku pracy nie jest ustawione na *Otwarte* ani *W toku*.</span><span class="sxs-lookup"><span data-stu-id="7fd52-111">The **Work status** field on the work header isn't set to *Open* or *In progress*.</span></span>

## <a name="resolution"></a><span data-ttu-id="7fd52-112">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="7fd52-112">Resolution</span></span>

<span data-ttu-id="7fd52-113">Aby anulować pracę, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7fd52-113">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="7fd52-114">Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.</span><span class="sxs-lookup"><span data-stu-id="7fd52-114">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="7fd52-115">W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować.</span><span class="sxs-lookup"><span data-stu-id="7fd52-115">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="7fd52-116">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fd52-116">Select **OK**.</span></span>
1. <span data-ttu-id="7fd52-117">Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.</span><span class="sxs-lookup"><span data-stu-id="7fd52-117">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="7fd52-118">Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="7fd52-118">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
