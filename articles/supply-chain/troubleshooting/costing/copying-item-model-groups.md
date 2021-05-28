---
title: Brak ustawień pól podczas kopiowania grup modeli pozycji do innej firmy
description: Brakuje ustawień pola, gdy grupy modeli pozycji są kopiowane do innej firmy.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f6fdfef0bc377418ed8a9c8830e74526a0b95eb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026808"
---
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a><span data-ttu-id="4bec9-103">Brak ustawień pól podczas kopiowania grup modeli pozycji do innej firmy</span><span class="sxs-lookup"><span data-stu-id="4bec9-103">Missing field settings when item model groups are copied to another legal entity</span></span>

<span data-ttu-id="4bec9-104">Numer artykułu z bazy wiedzy: 4612800</span><span class="sxs-lookup"><span data-stu-id="4bec9-104">KB number: 4612800</span></span>

## <a name="symptoms"></a><span data-ttu-id="4bec9-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="4bec9-105">Symptoms</span></span>

<span data-ttu-id="4bec9-106">Podczas kopiowania grup modeli towarów do innej firmy (firmy) przy użyciu jednostki *Zasady zapasów grupy modeli pozycji* brakuje niektórych ustawień pól (na przykład modelu zapasów i opisu) w nowej grupie modeli w docelowej firmie.</span><span class="sxs-lookup"><span data-stu-id="4bec9-106">When you copy item model groups to another legal entity (company) by using the *Item model group inventory policies* entity, some field settings (for example, the inventory model and description) are missing in the new model group in the destination legal entity.</span></span>

## <a name="resolution"></a><span data-ttu-id="4bec9-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="4bec9-107">Resolution</span></span>

<span data-ttu-id="4bec9-108">Aby utworzyć pełną kopię grupy modeli towarów do innej firmy, należy również wybrać zarówno zasady zapasów grupy modeli towarów (\`\`InventInventoryPolicyEntity`), jak i zasady założenia przepływu kosztów (`InventCostFlowAssumptionPolicyEntity\`), które są powiązane z towarem grupa modeli.</span><span class="sxs-lookup"><span data-stu-id="4bec9-108">To create a complete copy of an item model group to another legal entity, you must also select both the item model group inventory policies (`InventInventoryPolicyEntity`) and the cost flow assumption policies (`InventCostFlowAssumptionPolicyEntity`) that are associated with the item model group.</span></span>
