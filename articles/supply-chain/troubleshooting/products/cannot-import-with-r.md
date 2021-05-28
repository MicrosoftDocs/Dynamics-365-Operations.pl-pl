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
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026805"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Nie można zaimportować towaru przy użyciu jednostki Zwolnione produkty w wersji 2

Numer artykułu z bazy wiedzy: 4611825

## <a name="symptoms"></a>Objawy

Podczas importowania towaru przy użyciu jednostki *Zwolnione produkty w wersji 2* wyświetlany jest komunikat o błędzie przypominający następujący przykład:

> Nie można utworzyć rekordu w elementach — grupach wymiarów śledzenia (EcoResTrackingDimensionGroupItem). Numer partii towaru: 2040663, Batch. Rekord już istnieje.

## <a name="resolution"></a>Rozdzielczość

Aby zaimportować nowe zwolnione produkty, musisz użyć jednostki *Tworzenie zwolnionego produktu w wersji 2* zamiast jednostki *Zwolnione produkty w wersji 2*.
