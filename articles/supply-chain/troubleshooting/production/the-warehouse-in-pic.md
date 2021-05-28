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
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a><span data-ttu-id="2e817-103">Magazyn w arkuszu listy pobrania nie został zaktualizowany w wierszu BOM</span><span class="sxs-lookup"><span data-stu-id="2e817-103">The warehouse in the picking list journal isn't updated on a BOM line</span></span>

<span data-ttu-id="2e817-104">Numer artykułu z bazy wiedzy: 4614848</span><span class="sxs-lookup"><span data-stu-id="2e817-104">KB number: 4614848</span></span>

## <a name="symptoms"></a><span data-ttu-id="2e817-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="2e817-105">Symptoms</span></span>

<span data-ttu-id="2e817-106">Magazyn w arkuszu listy pobrania nie został zaktualizowany w wierszulisty składowej BOM.</span><span class="sxs-lookup"><span data-stu-id="2e817-106">The warehouse in the picking list journal isn't updated on a bill of materials (BOM) line.</span></span>

## <a name="resolution"></a><span data-ttu-id="2e817-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="2e817-107">Resolution</span></span>

<span data-ttu-id="2e817-108">System jest szybując tak jak zaprojektowany.</span><span class="sxs-lookup"><span data-stu-id="2e817-108">The system is behaving as designed.</span></span> <span data-ttu-id="2e817-109">Jeśli zostanie utworzony wiersz arkusza listy pobrania z odwołaniem (za pośrednictwem identyfikatora partii) do wiersza BOM produkcji, magazyn w wierszu BOM produkcji nie zostanie zaktualizowany, jeśli wymiar magazynu w wierszu arkusza listy pobrania produkcji zostanie później zmieniony.</span><span class="sxs-lookup"><span data-stu-id="2e817-109">If a picking list journal line is created that has a reference (via the lot ID) to a production BOM line, the warehouse on the production BOM line won't be updated if the warehouse dimension on the production picking list journal line is changed later.</span></span>
