---
title: Wyświetlany jest monit o zapisanie ustawień zapotrzebowania elementu, mimo że nie wprowadzono żadnych zmian
description: Wyświetlany jest monit o zapisanie ustawień zapotrzebowania elementu, mimo że nie wprowadzono żadnych zmian.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049484"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a><span data-ttu-id="3644c-103">Wyświetlany jest monit o zapisanie ustawień zapotrzebowania elementu, mimo że nie wprowadzono żadnych zmian</span><span class="sxs-lookup"><span data-stu-id="3644c-103">You're prompted to save item coverage settings even though you made no changes</span></span>

<span data-ttu-id="3644c-104">Numer artykułu z bazy wiedzy: 4615588</span><span class="sxs-lookup"><span data-stu-id="3644c-104">KB number: 4615588</span></span>

## <a name="symptoms"></a><span data-ttu-id="3644c-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="3644c-105">Symptoms</span></span>

<span data-ttu-id="3644c-106">W niektórych scenariuszach po zaimportowaniu towarów za pomocą strony *Zapotrzebowanie na towar V2* po otwarciu strony **Zapotrzebowania na towar** może zostać wyświetlony następujący komunikat:</span><span class="sxs-lookup"><span data-stu-id="3644c-106">In some scenarios, you might receive the following message when you open the **Item coverage** page after you import items through the *Item coverage V2* entity:</span></span>

> <span data-ttu-id="3644c-107">Czy przed zamknięciem chcesz zapisać zmiany?</span><span class="sxs-lookup"><span data-stu-id="3644c-107">Do you want to save your changes before closing?</span></span>

<span data-ttu-id="3644c-108">Ten komunikat zostanie wyświetlony nawet wtedy, gdy nie poczynisz żadnych zmian.</span><span class="sxs-lookup"><span data-stu-id="3644c-108">You receive this message even though you haven't made any changes.</span></span>

## <a name="resolution"></a><span data-ttu-id="3644c-109">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="3644c-109">Resolution</span></span>

<span data-ttu-id="3644c-110">Strona **Zapotrzebowanie na towar** zawiera złożoną logikę wartości domyślnych, która może spowodować, że komunikat będzie wyświetlany po bezpośrednich zmianach wprowadzonych w bazie danych, na przykład za pośrednictwem importu encji.</span><span class="sxs-lookup"><span data-stu-id="3644c-110">The **Item coverage** page includes complex defaulting logic that might cause the message to be shown after direct changes have recently been made in the database, such as through entity import.</span></span> <span data-ttu-id="3644c-111">Na przykład w polu encji `AREGENERALSETTINGSOVERRIDDEN` ustawiono wartość *Nie*, ale importowany jest plik, który zawiera nowe lub zmodyfikowane wartości dla pól, takich jak `PRODUCTCOVERAGEGROUPID` i/lub `VENDORACCOUNTNUMBER`.</span><span class="sxs-lookup"><span data-stu-id="3644c-111">For example, the `AREGENERALSETTINGSOVERRIDDEN` entity field is set to *No*, but you import a file that provides new or modified values for fields such as `PRODUCTCOVERAGEGROUPID` and/or `VENDORACCOUNTNUMBER`.</span></span> <span data-ttu-id="3644c-112">W takim przypadku, ponieważ pole `AREGENERALSETTINGSOVERRIDDEN` ma wartość *Nie*, wartości zostaną automatycznie wyczyszone z pól, gdy strona **Zapotrzebowania na towar** zostanie otwarta po raz pierwszy po imporcie.</span><span class="sxs-lookup"><span data-stu-id="3644c-112">In this case, because the `AREGENERALSETTINGSOVERRIDDEN` field is set to *No*, the values are automatically cleared from the fields when you open the **Item coverage** page for the first time after the import.</span></span> <span data-ttu-id="3644c-113">Zmiany zapisane w odpowiedzi na monit zostaną zapisane w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="3644c-113">If you save the changes as the message box prompts, they are stored in the database.</span></span> <span data-ttu-id="3644c-114">W przeciwnym razie przy kolejnym otwarciu strony zostanie wyświetlony ten sam komunikat.</span><span class="sxs-lookup"><span data-stu-id="3644c-114">Otherwise, you will receive the same message the next time that you open the page.</span></span>

<span data-ttu-id="3644c-115">Aby zapobiec takiemu zachowaniu, ale również uwzględnić wartości dla pól, takich jak `PRODUCTCOVERAGEGROUPID` przez import jednostek, należy ustawić w `AREGENERALSETTINGSOVERRIDDEN` wartość *Tak* podczas importowania.</span><span class="sxs-lookup"><span data-stu-id="3644c-115">To prevent this behavior but also include values for fields such as `PRODUCTCOVERAGEGROUPID` through entity import, set `AREGENERALSETTINGSOVERRIDDEN` to *Yes* when you import.</span></span>
