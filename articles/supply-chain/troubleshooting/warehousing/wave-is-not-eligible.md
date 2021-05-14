---
title: Grupa czynności nie kwalifikuje się do oczyszczania
description: Grupa czynności nie kwalifikuje się do oczyszczania
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924334"
---
# <a name="wave-isnt-eligible-for-cleanup"></a><span data-ttu-id="13e99-103">Grupa czynności nie kwalifikuje się do oczyszczania</span><span class="sxs-lookup"><span data-stu-id="13e99-103">Wave isn't eligible for cleanup</span></span>

<span data-ttu-id="13e99-104">Kod błędu: WaveNotEligibleForCleanup</span><span class="sxs-lookup"><span data-stu-id="13e99-104">Error code: WaveNotEligibleForCleanup</span></span>

## <a name="symptoms"></a><span data-ttu-id="13e99-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="13e99-105">Symptoms</span></span>

<span data-ttu-id="13e99-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="13e99-106">The system shows the following error message:</span></span>

> <span data-ttu-id="13e99-107">Grupa czynności %1 nie kwalifikuje się do oczyszczania.</span><span class="sxs-lookup"><span data-stu-id="13e99-107">Wave %1 is not eligible for cleanup.</span></span>

<span data-ttu-id="13e99-108">Nie można wyczyścić danych grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="13e99-108">The wave data can't be cleaned up.</span></span>  

## <a name="cause"></a><span data-ttu-id="13e99-109">Powód</span><span class="sxs-lookup"><span data-stu-id="13e99-109">Cause</span></span>

<span data-ttu-id="13e99-110">Grupa czynności jest obecnie przetwarzana, co sygnalizuje jeden z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="13e99-110">The wave is currently being processed, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="13e99-111">Pole **Stan grupy czynności** ma wartość *Wykonywanie*.</span><span class="sxs-lookup"><span data-stu-id="13e99-111">The **Wave status** field is set to *Executing*.</span></span>
- <span data-ttu-id="13e99-112">Po wybraniu opcji **Zadanie wsadowe** w grupie **Grupa czynności** na karcie **Grupa czynności** okienka akcji wartość pola **Stan** nie jest zmieniana na *Zakończone*, *Błąd* lub *Anulowane*.</span><span class="sxs-lookup"><span data-stu-id="13e99-112">When you select **Batch job** in the **Wave** group on the **Wave** tab of the Action Pane, the **Status** field isn't set to *Ended*, *Error*, or *Canceled*.</span></span> <span data-ttu-id="13e99-113">W związku z tym zadanie wsadowe nadal działa.</span><span class="sxs-lookup"><span data-stu-id="13e99-113">Therefore, a batch job is currently running.</span></span>

## <a name="resolution"></a><span data-ttu-id="13e99-114">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="13e99-114">Resolution</span></span>

<span data-ttu-id="13e99-115">W okienku akcji, na karcie **Grupa czynności** w grupie **Grupa czynności** wybierz opcję **Zadanie wsadowe**, a następnie wykonaj jedną z poniższych czynności:</span><span class="sxs-lookup"><span data-stu-id="13e99-115">On the Action Pane, on the **Wave** tab, in the **Wave** group, select **Batch job**, and then follow one of these steps:</span></span>

- <span data-ttu-id="13e99-116">Jeśli pole **Stan** ma wartość *Wykonywanie*: w okienku akcji, na karcie **Zadanie wsadowe** w grupie **Zadanie wsadowe** wybierz pozycję **Wyświetl zadania**.</span><span class="sxs-lookup"><span data-stu-id="13e99-116">If the **Status** field is set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Batch job** group, select **View tasks**.</span></span> <span data-ttu-id="13e99-117">Można monitorować postęp, odświeżając stronę **Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="13e99-117">You can follow the progress by refreshing the **Batch tasks** page.</span></span>
- <span data-ttu-id="13e99-118">Jeśli pole **Stan** nie ma wartości *Wykonywanie*: w okienku akcji, na karcie **Zadanie wsadowe** w grupie **Funkcje** wybierz pozycję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="13e99-118">If the **Status** field isn't set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Functions** group, select **Change status**.</span></span> <span data-ttu-id="13e99-119">W polu **Wybierz nowy stan** wybierz opcję *Oczekiwanie*.</span><span class="sxs-lookup"><span data-stu-id="13e99-119">In the **Select new status** field, select *Waiting*.</span></span> <span data-ttu-id="13e99-120">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="13e99-120">Then select **OK**.</span></span>
