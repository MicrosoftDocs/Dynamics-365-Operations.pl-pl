---
title: Ustawienia reguły opróżniania w wierszach BOM nie są zachowane
description: Ustawienia reguły opróżniania w wierszach listy składników BOM nie są zachowane.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026815"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a><span data-ttu-id="191b8-103">Ustawienia reguły opróżniania w wierszach BOM nie są zachowane</span><span class="sxs-lookup"><span data-stu-id="191b8-103">Flushing principle settings on BOM lines aren't respected</span></span>

<span data-ttu-id="191b8-104">Numer artykułu z bazy wiedzy: 4612725</span><span class="sxs-lookup"><span data-stu-id="191b8-104">KB number: 4612725</span></span>

## <a name="symptoms"></a><span data-ttu-id="191b8-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="191b8-105">Symptoms</span></span>

<span data-ttu-id="191b8-106">Ten problem występuje, gdy w polu **Automatyczne zużycie BOM** na karcie **Aktualizacja automatyczna** na stronie **Parametry kontroli produkcji** jest ustawiona wartość *Zasada opróżniania*.</span><span class="sxs-lookup"><span data-stu-id="191b8-106">This issue occurs when the **Automatic BOM consumption** field on the **Automatic update** tab of the **Production control parameters** page is set to *Flushing principle*.</span></span> <span data-ttu-id="191b8-107">To ustawienie wskazuje, że wszystkie wiersze BOM powinny być zużywane automatycznie po otrzymaniu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="191b8-107">This setting indicates that all bill of materials (BOM) lines should automatically be consumed when a purchase order is received.</span></span> <span data-ttu-id="191b8-108">Jeśli pole **Zasada opróżniania** w wierszach BOM zostanie jawnie ustawione na wartość *Ręcznie*, można oczekiwać, że wiersze BOM nie będą zużywane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="191b8-108">If the **Flushing principle** field on BOM lines is explicitly set to *Manual*, you might expect that the BOM lines won't automatically be consumed.</span></span> <span data-ttu-id="191b8-109">Jednak w przypadku tego problemu wiersze BOM, w których w polu **Reguły opróżniania** jest ustawiona wartość *Ręcznie*, są mimo to zużywane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="191b8-109">However, when this issue occurs, BOM lines where the **Flushing principle** field is set to *Manual* are automatically consumed anyway.</span></span>

## <a name="resolution"></a><span data-ttu-id="191b8-110">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="191b8-110">Resolution</span></span>

<span data-ttu-id="191b8-111">Jeśli występuje ten problem, parametry kontroli produkcji mogą być tak ustawione, aby zastąpić ustawienie **Reguły opróżniania** w wierszach BOM.</span><span class="sxs-lookup"><span data-stu-id="191b8-111">If you're experiencing this issue, your production control parameters might be set up to override the **Flushing principle** setting on BOM lines.</span></span> <span data-ttu-id="191b8-112">Na stronie **Parametry kontroli produkcji**, na karcie **Aktualizacja automatyczna** sprawdź wartość pola **Automatyczne zużycie BOM**.</span><span class="sxs-lookup"><span data-stu-id="191b8-112">On the **Production control parameters** page, on the **Automatic update** tab, check the value of the **Automatic BOM consumption** field.</span></span> <span data-ttu-id="191b8-113">Jeśli jest ustawiona wartość *Zawsze*, system zignoruje ustawienie **Reguły opróżniania** we wszystkich wierszach BOM i zawsze opróżnia wiersze.</span><span class="sxs-lookup"><span data-stu-id="191b8-113">If it's set to *Always*, the system will disregard the **Flushing principle** setting on all BOM lines and will always flush the lines.</span></span> <span data-ttu-id="191b8-114">Aby system był przestrzegany ustawienia **reguły opróżniania** w wierszach BOM, zmień wartość pola **Automatyczne zużycie BOM** na *Zasadę opróżniania*.</span><span class="sxs-lookup"><span data-stu-id="191b8-114">To make the system respect the **Flushing principle** setting on BOM lines, change the value of the **Automatic BOM consumption** field to *Flushing principle*.</span></span>
