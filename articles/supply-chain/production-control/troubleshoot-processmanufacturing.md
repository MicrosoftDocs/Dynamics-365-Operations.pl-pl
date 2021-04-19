---
title: Rozwiązywanie problemów dotyczących wytwarzania procesowego
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z wytwarzaniem procesowym.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 938820b6cd2bb470b440fea7b70124efc0faf7f8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824997"
---
# <a name="troubleshoot-process-manufacturing"></a><span data-ttu-id="bc62d-103">Rozwiązywanie problemów dotyczących wytwarzania procesowego</span><span class="sxs-lookup"><span data-stu-id="bc62d-103">Troubleshoot process manufacturing</span></span>

<span data-ttu-id="bc62d-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z wytwarzaniem procesowym.</span><span class="sxs-lookup"><span data-stu-id="bc62d-104">This topic describes how to fix issues that you might encounter while you work with process manufacturing.</span></span>

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a><span data-ttu-id="bc62d-105">Kiedy używam urządzenia karty pracy do zgłaszania ilości częściowej dla ostatniego zlecenia w zleceniu produkcyjnym, wszystkie poprzednie zadania w tym zamówieniu, które mają stan W toku, są automatycznie kończone.</span><span class="sxs-lookup"><span data-stu-id="bc62d-105">When I use the job card device to report a partial quantity on the last job in a production order, all the previous jobs on that order that have a status of In progress are automatically ended.</span></span>

<span data-ttu-id="bc62d-106">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="bc62d-106">This behavior is by design.</span></span> <span data-ttu-id="bc62d-107">Na stronie **Ustawienia domyślne zlecenia produkcyjnego** na karcie **Zgłoszenie wyrobów gotowych** istnieje opcja o nazwie **Znacznik końcowy trasy**.</span><span class="sxs-lookup"><span data-stu-id="bc62d-107">On the **Production order defaults** page, on the **Report as finished** tab, there is an option that is named **End-mark route**.</span></span> <span data-ttu-id="bc62d-108">Jeśli w tym temacie jest ustawiona wartość *Tak*, arkusz karty trasy jest księgowany, gdy pracownik korzysta z terminalu karty zadań lub urządzenia karty zadań w celu zgłoszenia ostatniej operacji.</span><span class="sxs-lookup"><span data-stu-id="bc62d-108">If this topic is set to *Yes*, a route card journal is posted when a worker uses the job card device or job card terminal to report the last operation.</span></span> <span data-ttu-id="bc62d-109">Ten arkusz oznacza wszystkie operacje jako zakończone i kończy wszystkie zadania produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="bc62d-109">This journal marks all the operations as completed and ends all the production jobs.</span></span> <span data-ttu-id="bc62d-110">Jeśli dla opcji **Znacznik końcowy trasy** jest ustawiona wartość *Tak*, system nie będzie traktować stanu zadania wybranego przez pracownika podczas raportowania ostatniej operacji.</span><span class="sxs-lookup"><span data-stu-id="bc62d-110">When the **End-mark route** option is set to *Yes*, the system doesn't consider the job status that the worker selected when they reported the last operation.</span></span> <span data-ttu-id="bc62d-111">System nie bierze również pod uwagę, czy pracownik zgłasza ilość pełną czy częściową.</span><span class="sxs-lookup"><span data-stu-id="bc62d-111">The system also doesn't consider whether the worker is reporting a full or partial quantity.</span></span>

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a><span data-ttu-id="bc62d-112">Podczas próby zamknięcia zapasów otrzymuję następujący komunikat ostrzegawczy: „Nie zarejestrowano wykonania obliczenia wyceny wstecznej z datą %1 pasującą do końca okresu”.</span><span class="sxs-lookup"><span data-stu-id="bc62d-112">When I attempt a stock closing, I receive the following warning message: "No execution of Backflush costing calculation with a date %1 matching period end has been registered."</span></span>

<span data-ttu-id="bc62d-113">W zwolnieniach przed wydaniem 10.0.13, jeśli nie jest używany przepływ kosztów produkcji oszczędnej, podczas zamykania magazynu jest wyświetlany następujący błędny komunikat ostrzegawczy:</span><span class="sxs-lookup"><span data-stu-id="bc62d-113">In releases before release 10.0.13, if you aren't using the lean production costing flow, you receive the following erroneous warning message during inventory closing:</span></span>

> <span data-ttu-id="bc62d-114">Zamierzasz wykonać zamknięcie zapasów z datą %1.</span><span class="sxs-lookup"><span data-stu-id="bc62d-114">You are about to execute an Inventory close with a date %1.</span></span> <span data-ttu-id="bc62d-115">Nie zarejestrowano wykonania obliczania wyceny wstecznej z datą %1 pasującą do zakończenia okresu.</span><span class="sxs-lookup"><span data-stu-id="bc62d-115">No execution of Backflush costing calculation with a date %1 matching period end has been registered.</span></span> <span data-ttu-id="bc62d-116">Należy pamiętać o wykonaniu obliczania wyceny wstecznej z datą %1 pasującą do zakończenia okresu.</span><span class="sxs-lookup"><span data-stu-id="bc62d-116">Please remember to execute a Backflush costing calculation with a date of %1 matching period end.</span></span> <span data-ttu-id="bc62d-117">Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji.</span><span class="sxs-lookup"><span data-stu-id="bc62d-117">The valuation of inventories, cost of goods sold and variances might not be correct in Subledger or General ledger until this has been executed.</span></span>

<span data-ttu-id="bc62d-118">Ten błąd został rozwiązany w wersji wydania 10.0.13 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="bc62d-118">This issue has been fixed in release 10.0.13 and later.</span></span> <span data-ttu-id="bc62d-119">Aby uzyskać więcej informacji, zobacz [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span><span class="sxs-lookup"><span data-stu-id="bc62d-119">For more information, see [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]