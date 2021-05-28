---
title: Błąd podczas księgowania raportu jako gotowego arkusza
description: Podczas zaksięgowania arkusza Zgłoszenia gotowych wyświetlany jest komunikat o błędzie informujący, że zamówione ilości nie mogą zostać zmniejszone.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 55db7d0033dd66c1b973abf96671a20ab05d61d8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026802"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a><span data-ttu-id="98c97-103">Błąd podczas księgowania raportu jako gotowego arkusza</span><span class="sxs-lookup"><span data-stu-id="98c97-103">Error when the Report as finished journal is posted</span></span>

<span data-ttu-id="98c97-104">Numer artykułu z bazy wiedzy: 4612891</span><span class="sxs-lookup"><span data-stu-id="98c97-104">KB number: 4612891</span></span>

## <a name="symptoms"></a><span data-ttu-id="98c97-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="98c97-105">Symptoms</span></span>

<span data-ttu-id="98c97-106">Podczas zaksięgowania arkusza **zgłoszenia gotowych** wystąpi błąd i zostanie wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="98c97-106">When you post the **Report as finished** journal, an error occurs, and you receive the following error message:</span></span>

> <span data-ttu-id="98c97-107">Ilość zamówiona nie może być zmniejszona. Niewystarczający poziom zapasów ze stanem Zamówione.</span><span class="sxs-lookup"><span data-stu-id="98c97-107">Quantity ordered cannot be reduced because there are not enough open inventory transactions with the ordered status.</span></span> <span data-ttu-id="98c97-108">Pozycje to Zakupione, Odebrane lub Zarejestrowane.</span><span class="sxs-lookup"><span data-stu-id="98c97-108">The items are Purchased, Received or Registered.</span></span>

<span data-ttu-id="98c97-109">Ten błąd występuje tylko wtedy, gdy pole **Ilość towarów błędnych** jest ustawione w pierwszym wierszu arkusza **Zgłoszenie jako gotowe**, a pole **Ilość dobrych** jest ustawione w ostatnim wierszu.</span><span class="sxs-lookup"><span data-stu-id="98c97-109">This error occurs only when the **Error quantity** field is set on the first line of the **Report as finished** journal, and the **Good quantity** field is set on the last line.</span></span> <span data-ttu-id="98c97-110">Jeśli pole **Ilość błędów** jest ustawione w ostatnim wierszu, nie występuje błąd.</span><span class="sxs-lookup"><span data-stu-id="98c97-110">If the **Error quantity** field is set on the last line, no error occurs.</span></span>

## <a name="resolution"></a><span data-ttu-id="98c97-111">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="98c97-111">Resolution</span></span>

<span data-ttu-id="98c97-112">Aby uniknąć tego błędu, otwórz stronę **Parametry kontroli produkcji**, a następnie na karcie **Ogólne** dla opcji **Zwiększ ilość pozostała z błędami** ustaw wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="98c97-112">To prevent this error, open the **Production control parameters** page, and then, on the **General** tab, set the **Increase remain qty with error qty** option to *Yes*.</span></span>
