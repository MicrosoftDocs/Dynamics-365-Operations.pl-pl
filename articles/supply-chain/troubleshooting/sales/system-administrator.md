---
title: Administratorzy systemu nie mogą wyczyścić wstrzymów zamówień, ponieważ nie są autoryzowani
description: Administratorzy systemu nie mogą wyczyścić wstrzymów zamówień, ponieważ nie są autoryzowani.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acabd6409d9b2860535335bc648bcc34304e0cb0
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026830"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a>Administratorzy systemu nie mogą wyczyścić wstrzymów zamówień, ponieważ nie są autoryzowani

Numer artykułu z bazy wiedzy: 4614642

## <a name="symptoms"></a>Objawy

Administratorzy systemu nie mogą wyczyścić wstrzymań zamówień sprzedaży, chyba że mają przypisaną określoną rolę w kodzie przechowywania zamówienia.

## <a name="resolution"></a>Rozdzielczość

Dostęp do niektórych operacji, na przykład rozliczeń wstrzymów zamówień sprzedaży, jest sterowany przez konfigurację zasad biznesowych. Administratorzy systemu zazwyczaj nie mogą wykonywać operacji tego typu. 

Najczęściej dostęp do wykonania określonego zadania podlega zasadom biznesowym i tylko określone osoby w organizacji są zatwierdzone do wykonania tego zadania. Przykładowe są zatwierdzenia wynikające z zatwierdzeń w przepływie pracy i określone zadania wynikające z konfiguracji przepływu pracy.

Chociaż żaden przepływ pracy nie jest skojarzony z wstrzymaniami zamówień, zasada jest podobna. Właściwa rola określa określoną grupę osób w organizacji, które mają prawo do wyczyszczenia wstrzymań zamówień. To prawo nie powinno być konieczne dla wszystkich administratorów, ponieważ takie podejście narusza zdefiniowaną zasady biznesowe.
