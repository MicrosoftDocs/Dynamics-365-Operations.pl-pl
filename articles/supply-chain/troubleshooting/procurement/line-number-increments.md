---
title: Zaimportowane zamówienia zakupu wskazują niepoprawne numery wiersza
description: Gdy zamówienia zakupu są importowane za pomocą zarządzania danymi, numery wierszy zamówienia nie są zgodne z przyrostem zdefiniowanym w parametrach systemu.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e1cf5cf1d04824213f495ac3ebf556796c96611a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477263"
---
# <a name="imported-purchase-orders-show-incorrect-line-numbers"></a>Zaimportowane zamówienia zakupu wskazują niepoprawne numery wiersza

## <a name="symptoms"></a>Objawy

Domyślnie automatycznie generowane numery wierszy zamówień zakupu, które są importowane za pomocą jednostki danych *Wiersze zamówienia zakupu V2*, nie używaj przyrostu numeru wiersza systemowego określonego w parametrach systemowych. Jeśli ręcznie utworzysz zamówienie zakupu i dodasz wiersze za pośrednictwem interfejsu użytkownika (UI), numery wierszy zostaną poprawnie zwiększone. Jeśli jednak używasz struktury zarządzania danymi (DMF), nie są one poprawnie zwiększane.

Ten problem występuje, ponieważ podczas importowania wierszy przez DMF, jeśli numery wierszy nie są jeszcze przypisane w importowanej encji, system używa metody DMF do ich przypisywania. Ta metoda zawsze zwiększa liczbę wierszy o jeden.

## <a name="workaround"></a>Obejście

Upewnij się, że żądane numery wierszy są już podane w polach numeru wiersza jednostki danych podczas importowania wierszy zamówienia zakupu. W takim przypadku DMF nie zastąpi numerów wierszy.
