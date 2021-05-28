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
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a>Brak ustawień pól podczas kopiowania grup modeli pozycji do innej firmy

Numer artykułu z bazy wiedzy: 4612800

## <a name="symptoms"></a>Objawy

Podczas kopiowania grup modeli towarów do innej firmy (firmy) przy użyciu jednostki *Zasady zapasów grupy modeli pozycji* brakuje niektórych ustawień pól (na przykład modelu zapasów i opisu) w nowej grupie modeli w docelowej firmie.

## <a name="resolution"></a>Rozdzielczość

Aby utworzyć pełną kopię grupy modeli towarów do innej firmy, należy również wybrać zarówno zasady zapasów grupy modeli towarów (``InventInventoryPolicyEntity`), jak i zasady założenia przepływu kosztów (`InventCostFlowAssumptionPolicyEntity`), które są powiązane z towarem grupa modeli.
