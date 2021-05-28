---
title: Cofanie ustawień arkuszy i wierszy
description: W tym temacie opisano powody, dla których wpis wycofania wprowadzony dla arkusza finansowego mógł nie zostać uwzględniony w ramach zaksięgowanej transakcji.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 74020f6fc9b0fa8e05a1e2a09fd13dcd60490dc0
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028580"
---
# <a name="reverse-settings-on-journals-and-lines"></a><span data-ttu-id="d0800-103">Cofanie ustawień arkuszy i wierszy</span><span class="sxs-lookup"><span data-stu-id="d0800-103">Reverse settings on journals and lines</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0800-104">W tym temacie opisano powody, dla których wpis wycofania wprowadzony dla arkusza finansowego mógł nie zostać uwzględniony w ramach zaksięgowanej transakcji.</span><span class="sxs-lookup"><span data-stu-id="d0800-104">This topic addresses why a reversing entry that was entered on a general journal might not be included on the posted transaction.</span></span>  

## <a name="symptom"></a><span data-ttu-id="d0800-105">Objaw</span><span class="sxs-lookup"><span data-stu-id="d0800-105">Symptom</span></span>

<span data-ttu-id="d0800-106">Arkusz finansowy zawiera wpis wycofania i datę wycofania w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="d0800-106">A general journal includes a reversing entry and reversing date on the journal.</span></span> <span data-ttu-id="d0800-107">Podczas księgowania arkusza żadne załączniki nie są wycofywane.</span><span class="sxs-lookup"><span data-stu-id="d0800-107">When you post the journal, none of the vouchers are reversed.</span></span> <span data-ttu-id="d0800-108">Dlaczego tak się dzieje?</span><span class="sxs-lookup"><span data-stu-id="d0800-108">Why does this happen?</span></span>

## <a name="resolution"></a><span data-ttu-id="d0800-109">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="d0800-109">Resolution</span></span>

<span data-ttu-id="d0800-110">Podczas księgowania arkusza proces wycofywania uwzględnia wyłącznie ustawienia **Wpis wycofania** oraz **Data wycofania** z sekcji **Wiersze** załącznika.</span><span class="sxs-lookup"><span data-stu-id="d0800-110">When the journal is posted, the reversing process looks only at the **Revering entry** and **Reversing date** settings on the **Lines** section of the voucher.</span></span> <span data-ttu-id="d0800-111">Dzięki temu arkusz może obejmować wybrane załączniki oznaczone jako przeznaczone do wycofania, a także takie, które nie mają takiego oznaczenia.</span><span class="sxs-lookup"><span data-stu-id="d0800-111">This approach allows a journal to include some vouchers that are marked for reversing, and others that are not.</span></span>

<span data-ttu-id="d0800-112">Wartości z arkusza są używane jedynie jako wartości domyślne podczas dodawania *nowych* wierszy.</span><span class="sxs-lookup"><span data-stu-id="d0800-112">The values from the journal are only used as defaults when adding *new* lines.</span></span> <span data-ttu-id="d0800-113">Zmiana wartości w arkuszu nie wpływa na istniejące wiersze.</span><span class="sxs-lookup"><span data-stu-id="d0800-113">Changing the values on the journal doesn’t affect existing lines.</span></span> <span data-ttu-id="d0800-114">W tym przykładzie wiersze załącznika zostały wprowadzone wcześniej.</span><span class="sxs-lookup"><span data-stu-id="d0800-114">In this example, the voucher lines were entered first.</span></span> <span data-ttu-id="d0800-115">Jeśli użytkownik wpisze szczegóły wiersza przed oznaczeniem arkusza jako arkusza wycofania, oznaczenia wpisu wycofania i daty wycofania nie będą mieć zastosowana do żadnych istniejących wierszy.</span><span class="sxs-lookup"><span data-stu-id="d0800-115">When you enter the line detail before designating the journal as reversing, the designation as a reversing entry and date won't be applied to any existing lines.</span></span>

<span data-ttu-id="d0800-116">Zmiana wpisu wycofania lub daty wycofania istniejącego wiersza powoduje zastosowanie zmiany do innych wierszy w tym samym załączniku.</span><span class="sxs-lookup"><span data-stu-id="d0800-116">Changing the reversing entry or reversing date on an existing line propagates that change to other lines in the same voucher.</span></span> <span data-ttu-id="d0800-117">Aby zoptymalizować wydajność, siatka nie jest odświeżana po zastosowaniu zmian do innych wierszy.</span><span class="sxs-lookup"><span data-stu-id="d0800-117">To optimize performance, the grid is not refreshed after propagating changes to other Lines.</span></span> <span data-ttu-id="d0800-118">Zaktualizowane wartości można wyświetlić, odświeżając siatkę.</span><span class="sxs-lookup"><span data-stu-id="d0800-118">You can display the updated values by refreshing the grid.</span></span>


