---
title: Nie można anulować pracy z powodu blokady
description: Nie można anulować pracy z powodu blokady
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924286"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a><span data-ttu-id="b90df-103">Nie można anulować pracy z powodu blokady</span><span class="sxs-lookup"><span data-stu-id="b90df-103">Work can't be canceled because it's blocked</span></span>

<span data-ttu-id="b90df-104">Kod błędu: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="b90df-104">Error code: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="b90df-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="b90df-105">Symptoms</span></span>

<span data-ttu-id="b90df-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="b90df-106">The system shows the following error message:</span></span>

> <span data-ttu-id="b90df-107">Nie można anulować pracy %1, ponieważ jest zablokowana przez typ przyczyny %2.</span><span class="sxs-lookup"><span data-stu-id="b90df-107">Work %1 cannot be cancelled because it is blocked by reason type %2.</span></span> <span data-ttu-id="b90df-108">Praca musi zostać odblokowana, aby mogła zostać anulowana.</span><span class="sxs-lookup"><span data-stu-id="b90df-108">The work must be unblocked before it can be cancelled.</span></span>

## <a name="cause"></a><span data-ttu-id="b90df-109">Powód</span><span class="sxs-lookup"><span data-stu-id="b90df-109">Cause</span></span>

<span data-ttu-id="b90df-110">Praca jest zablokowana i nie można jej anulować.</span><span class="sxs-lookup"><span data-stu-id="b90df-110">The work is blocked and can't be canceled.</span></span>

<span data-ttu-id="b90df-111">Na stronie **Praca**, na karcie **Ogólne** opcja **Zablokowano** ma wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="b90df-111">On the **Work** page, on the **General** tab, the **Blocked** option is set to *Yes*.</span></span> <span data-ttu-id="b90df-112">To ustawienie wskazuje, że praca jest zablokowana.</span><span class="sxs-lookup"><span data-stu-id="b90df-112">This setting indicates that the work is blocked.</span></span> <span data-ttu-id="b90df-113">Na karcie **Przyczyny blokowania** pokazano, dlaczego praca została zablokowana.</span><span class="sxs-lookup"><span data-stu-id="b90df-113">The **Blocking reasons** tab shows why the work was blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="b90df-114">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="b90df-114">Resolution</span></span>

<span data-ttu-id="b90df-115">Aby odblokować pracę, wybierz kartę **Przyczyny blokowania**, a następnie wykonaj jedną z poniższych czynności:</span><span class="sxs-lookup"><span data-stu-id="b90df-115">To unblock the work, select the **Blocking reasons** tab, and then follow one of these steps:</span></span>

- <span data-ttu-id="b90df-116">Jeśli w polu **Przyczyna blokowania pracy** jest ustawiona wartość *Niezdefiniowana przyczyna*: w okienku akcji na karcie **Praca** w grupie **Praca** wybierz pozycję **Odblokuj pracę**.</span><span class="sxs-lookup"><span data-stu-id="b90df-116">If the **Work blocking reason** field is set to *Undefined reason*: On the Action Pane, on the **Work** tab, in the **Work** group, select **Unblock work**.</span></span>
- <span data-ttu-id="b90df-117">Jeśli w polu **Przyczyna blokowania pracy** jest ustawiona wartość *Przetwarzanie grupy czynności*: w okienku akcji, na karcie **Informacje pokrewne** w grupie **Informacje pokrewne** wybierz pozycję **Grupa czynności**.</span><span class="sxs-lookup"><span data-stu-id="b90df-117">If the **Work blocking reason** field is set to *Processing wave*: On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="b90df-118">Następnie na stronie **Grupa czynności**, w okienku akcji otwórz kartę **Grupa czynności** i z grupy **Grupa czynności** wybierz pozycję **Czyszczenie danych grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="b90df-118">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="b90df-119">Obejście</span><span class="sxs-lookup"><span data-stu-id="b90df-119">Workaround</span></span>

<span data-ttu-id="b90df-120">Jeśli poprzednie kroki nie rozwiązały problemu, możesz anulować pracę, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b90df-120">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="b90df-121">Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.</span><span class="sxs-lookup"><span data-stu-id="b90df-121">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="b90df-122">W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować, a obecnie ma wartość pola **Stan pracy** *Otwarta*, *W toku*, *Anulowana*, *Połączona* lub *Zamknięta*.</span><span class="sxs-lookup"><span data-stu-id="b90df-122">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="b90df-123">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b90df-123">Select **OK**.</span></span>
1. <span data-ttu-id="b90df-124">Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.</span><span class="sxs-lookup"><span data-stu-id="b90df-124">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="b90df-125">Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="b90df-125">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
