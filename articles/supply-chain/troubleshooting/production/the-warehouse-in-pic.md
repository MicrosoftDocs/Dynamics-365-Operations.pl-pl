---
title: Magazyn w arkuszu listy pobrania nie został zaktualizowany w wierszu BOM.
description: Magazyn w arkuszu listy pobrania nie został zaktualizowany w wierszulisty składowej BOM.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5d24c0b8538f3894fd1d2a3edb3a6ed8633c9609
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026804"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a>Magazyn w arkuszu listy pobrania nie został zaktualizowany w wierszu BOM

Numer artykułu z bazy wiedzy: 4614848

## <a name="symptoms"></a>Objawy

Magazyn w arkuszu listy pobrania nie został zaktualizowany w wierszulisty składowej BOM.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany. Jeśli zostanie utworzony wiersz arkusza listy pobrania z odwołaniem (za pośrednictwem identyfikatora partii) do wiersza BOM produkcji, magazyn w wierszu BOM produkcji nie zostanie zaktualizowany, jeśli wymiar magazynu w wierszu arkusza listy pobrania produkcji zostanie później zmieniony.
