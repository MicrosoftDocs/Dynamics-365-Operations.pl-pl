---
title: Warunki umowy handlowej nie są stosowane w importowanych wierszach zamówienia
description: Ceny i rabaty umowy handlowej nie są stosowane w wierszach sprzedaży lub zamówienia zakupu, które są importowane za pomocą zarządzania danymi
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: fef38819efaff2f2a927cf09fc7f469490149574
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477336"
---
# <a name="trade-agreement-conditions-arent-applied-to-imported-order-lines"></a>Warunki umowy handlowej nie są stosowane w importowanych wierszach zamówienia

## <a name="symptoms"></a>Objawy

Umowy handlowe, które mają zastosowanie do wierszy sprzedaży lub zamówienia zakupu, nie są stosowane w wierszach importowanych za pomocą funkcji zarządzania danymi. Jednak te same umowy handlowe są stosowane do wierszy sprzedaży lub zamówienia zakupu, które są tworzone ręcznie.

## <a name="cause"></a>Powód

Jeśli wiersze zamówienia zakupu, które są importowane za pomocą zarządzania danymi, zawierają już informacje o cenie, umowa handlowa nie zostanie ponownie oszacowana dla tych wierszy. Na przykład, jeśli **Procent rabatu dla wiersza** lub jakakolwiek cena i wartość rabatu jest ustawiona dla wiersza, umowy handlowe nie będą wyszukiwane dla tego wiersza.

## <a name="workaround"></a>Obejście

Takie zachowanie jest oczekiwane i podobne zarówno do zamówień sprzedaży, jak i zamówień zakupu.

Jako rozwiązanie alternatywne należy zaimportować wiersze zamówienia zakupu bez ustawiania żadnych informacji o cenach. Następnie zostaną zastosowane umowy handlowe, a wiersze zamówienia zakupu zostaną zaktualizowane na podstawie zdefiniowanych umów handlowych.
