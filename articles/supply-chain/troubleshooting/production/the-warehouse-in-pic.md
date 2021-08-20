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
ms.openlocfilehash: 970930bbdd30b57a8374de7810bb3ece8cb19a7010b5ef19d90bfc39d09f172b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740558"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a>Magazyn w arkuszu listy pobrania nie został zaktualizowany w wierszu BOM

Numer artykułu z bazy wiedzy: 4614848

## <a name="symptoms"></a>Objawy

Magazyn w arkuszu listy pobrania nie został zaktualizowany w wierszulisty składowej BOM.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany. Jeśli zostanie utworzony wiersz arkusza listy pobrania z odwołaniem (za pośrednictwem identyfikatora partii) do wiersza BOM produkcji, magazyn w wierszu BOM produkcji nie zostanie zaktualizowany, jeśli wymiar magazynu w wierszu arkusza listy pobrania produkcji zostanie później zmieniony.
