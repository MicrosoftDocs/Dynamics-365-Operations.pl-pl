---
title: Praca pozostaje zablokowana
description: Praca pozostaje zablokowana
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924137"
---
# <a name="work-remains-blocked"></a><span data-ttu-id="564ab-103">Praca pozostaje zablokowana</span><span class="sxs-lookup"><span data-stu-id="564ab-103">Work remains blocked</span></span>

<span data-ttu-id="564ab-104">Kod błędu: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="564ab-104">Error code: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="564ab-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="564ab-105">Symptoms</span></span>

<span data-ttu-id="564ab-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="564ab-106">The system shows the following error message:</span></span>

> <span data-ttu-id="564ab-107">Praca %1 pozostaje zablokowana, ponieważ powiązana grupa czynności %2 ma stan %3.</span><span class="sxs-lookup"><span data-stu-id="564ab-107">Work %1 remains blocked because the related wave %2 has status %3.</span></span>

## <a name="cause"></a><span data-ttu-id="564ab-108">Powód</span><span class="sxs-lookup"><span data-stu-id="564ab-108">Cause</span></span>

<span data-ttu-id="564ab-109">Praca jest obecnie przetwarzana w grupy czynności i nie można jej odblokować, co sygnalizuje jeden z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="564ab-109">The work is currently being processed on a wave and can't be unblocked, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="564ab-110">Na karcie **Przyczyny blokowania** pole **Przyczyna blokady pracy** dla co najmniej jednego wiersza ma wartość *Przetwarzanie grupy czynności*.</span><span class="sxs-lookup"><span data-stu-id="564ab-110">On the **Blocking reasons** tab, the **Work blocking reason** field for one or more lines is set to *Processing wave*.</span></span>
- <span data-ttu-id="564ab-111">Po wybraniu opcji **Grupa czynności** w grupie **Informacje pokrewne** na karcie **Informacje pokrewne** w okienku akcji pole **Stan grupy czynności** ma wartość *Przetwarzanie*.</span><span class="sxs-lookup"><span data-stu-id="564ab-111">When you select **Wave** in the **Related information** group on the **Related information** tab of the Action Pane, the **Wave status** field is set to *Processing*.</span></span>

## <a name="resolution"></a><span data-ttu-id="564ab-112">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="564ab-112">Resolution</span></span>

<span data-ttu-id="564ab-113">W okienku akcji, na karcie **Informacje pokrewne**, w grupie **Informacje pokrewne** wybierz opcję **Grupa czynności**.</span><span class="sxs-lookup"><span data-stu-id="564ab-113">On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="564ab-114">Następnie na stronie **Grupa czynności**, w okienku akcji otwórz kartę **Grupa czynności** i z grupy **Grupa czynności** wybierz pozycję **Czyszczenie danych grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="564ab-114">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="564ab-115">Obejście</span><span class="sxs-lookup"><span data-stu-id="564ab-115">Workaround</span></span>

<span data-ttu-id="564ab-116">Jeśli poprzednie kroki nie rozwiązały problemu, możesz anulować pracę, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="564ab-116">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="564ab-117">Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.</span><span class="sxs-lookup"><span data-stu-id="564ab-117">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="564ab-118">W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować, a obecnie ma wartość pola **Stan pracy** *Otwarta*, *W toku*, *Anulowana*, *Połączona* lub *Zamknięta*.</span><span class="sxs-lookup"><span data-stu-id="564ab-118">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="564ab-119">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="564ab-119">Select **OK**.</span></span>
1. <span data-ttu-id="564ab-120">Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.</span><span class="sxs-lookup"><span data-stu-id="564ab-120">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="564ab-121">Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="564ab-121">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
