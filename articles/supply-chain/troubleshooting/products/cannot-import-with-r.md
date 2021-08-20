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
ms.openlocfilehash: efd773313f89784d8fca6b37d867e204cb2d06ab29694a19cbec7eed107a8019
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764699"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Nie można zaimportować towaru przy użyciu jednostki Zwolnione produkty w wersji 2

Numer artykułu z bazy wiedzy: 4611825

## <a name="symptoms"></a>Objawy

Podczas importowania towaru przy użyciu jednostki *Zwolnione produkty w wersji 2* wyświetlany jest komunikat o błędzie przypominający następujący przykład:

> Nie można utworzyć rekordu w elementach — grupach wymiarów śledzenia (EcoResTrackingDimensionGroupItem). Numer partii towaru: 2040663, Batch. Rekord już istnieje.

## <a name="resolution"></a>Rozdzielczość

Aby zaimportować nowe zwolnione produkty, musisz użyć jednostki *Tworzenie zwolnionego produktu w wersji 2* zamiast jednostki *Zwolnione produkty w wersji 2*.
