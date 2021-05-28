---
title: Jeżeli zlecenia produkcyjne są wyzerowane za pomocą zadania wsadowego, nie sąsprawiedliwne zaznaczenie opcji późnego wyboru
description: Jeśli do zresetowania stanu zlecenia produkcyjnego jest używać cyklicznego zadania wsadowego, wybór opóźnionych wyborów nie jest przestrzegany.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e53198f427f4060421a4f0078277682c43db1320
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026807"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>Jeżeli zlecenia produkcyjne są wyzerowane za pomocą zadania wsadowego, nie sąsprawiedliwne zaznaczenie opcji późnego wyboru

Numer artykułu z bazy wiedzy: 4614634

## <a name="symptoms"></a>Objawy

Jeśli do zresetowania stanu zlecenia produkcyjnego jest używać cyklicznego zadania wsadowego, wybór opóźnionych wyborów nie jest przestrzegany.

## <a name="resolution"></a>Rozdzielczość

Bieżący projekt nie obsługuje funkcji późnego wyboru w procesie *Resetowania stanu*.
