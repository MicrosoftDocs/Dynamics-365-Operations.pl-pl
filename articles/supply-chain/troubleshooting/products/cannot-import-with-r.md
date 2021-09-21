---
title: Nie można zaimportować towaru przy użyciu jednostki Zwolnione produkty w wersji 2
description: Nie można zaimportować towaru przy użyciu jednostki Zwolnione produkty w wersji 2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: bf6eb0eb755de3f2842c235946bfd7ccad04ccf7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474731"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Nie można zaimportować towaru przy użyciu jednostki Zwolnione produkty w wersji 2

Numer artykułu z bazy wiedzy: 4611825

## <a name="symptoms"></a>Objawy

Podczas importowania towaru przy użyciu jednostki *Zwolnione produkty w wersji 2* wyświetlany jest komunikat o błędzie przypominający następujący przykład:

> Nie można utworzyć rekordu w elementach — grupach wymiarów śledzenia (EcoResTrackingDimensionGroupItem). Numer partii towaru: 2040663, Batch. Rekord już istnieje.

## <a name="resolution"></a>Rozdzielczość

Aby zaimportować nowe zwolnione produkty, musisz użyć jednostki *Tworzenie zwolnionego produktu w wersji 2* zamiast jednostki *Zwolnione produkty w wersji 2*.
