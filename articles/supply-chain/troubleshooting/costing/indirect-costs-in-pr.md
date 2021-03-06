---
title: Raport Koszty pośrednie w procesie zawiera usunięte zlecenia produkcyjne
description: Raport Koszty pośrednie w procesie zawiera informacje o zleceniach produkcyjnych, które zostały częściowo przetworzone, a później usunięte.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026814"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a>Raport Koszty pośrednie w procesie zawiera usunięte zlecenia produkcyjne

Numer artykułu z bazy wiedzy: 4612748

## <a name="symptoms"></a>Objawy

Raport **Koszty pośrednie w procesie** zawiera informacje o zleceniach produkcyjnych, które zostały częściowo przetworzone, a później usunięte.

## <a name="resolution"></a>Rozdzielczość

Wycofanie zlecenia produkcyjnego oznacza również wycofanie wszystkich transakcji tego zlecenia produkcyjnego. Usunięcie zlecenia produkcyjnego spowoduje, że tabele księgi podrzędnej i księga główna utrwalą wszystkie powiązane z nim transakcje. Raporty będą wyświetlać transakcje w tabelach księgi podrzędnej. Dla określonego zlecenia produkcyjnego wartość netto powinna być 0,00.
