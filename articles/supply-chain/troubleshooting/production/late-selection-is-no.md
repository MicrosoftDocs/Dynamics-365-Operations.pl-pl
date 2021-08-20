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
ms.openlocfilehash: 8800ec411ddd7ae73c5ac159592620a07b50c1e87938f823274ec24062c9a71a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741963"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>Jeżeli zlecenia produkcyjne są wyzerowane za pomocą zadania wsadowego, nie sąsprawiedliwne zaznaczenie opcji późnego wyboru

Numer artykułu z bazy wiedzy: 4614634

## <a name="symptoms"></a>Objawy

Jeśli do zresetowania stanu zlecenia produkcyjnego jest używać cyklicznego zadania wsadowego, wybór opóźnionych wyborów nie jest przestrzegany.

## <a name="resolution"></a>Rozdzielczość

Bieżący projekt nie obsługuje funkcji późnego wyboru w procesie *Resetowania stanu*.
