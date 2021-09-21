---
title: Rozłożenie BOM zachowuje się inaczej w przypadku ustalonych i szacowanych zleceń produkcyjnych
description: Rozłożenie listy składowej zachowuje się inaczej w przypadku ustalonych zleceń produkcyjnych i szacowanych zleceń produkcyjnych dla ręcznie utworzonych prac
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 94d4b00ea30396923a61b2748cf1aaeedc0af8af
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477305"
---
# <a name="bom-explosion-behaves-differently-for-firmed-and-estimated-production-orders"></a>Rozłożenie BOM zachowuje się inaczej w przypadku ustalonych i szacowanych zleceń produkcyjnych

## <a name="symptoms"></a>Objawy

Po utrwaleniu zlecenia produkcyjnego towary nie są rozkładane podczas rozkłądania listy składowej (BOM). Jednak podczas ręcznego tworzenia zlecenia produkcyjnego, a następnie szacowania zlecenia produkcyjnego, towary są rozkładane.

### <a name="resolution"></a>Rozwiązanie

Rozłożenie występujące podczas ustalania zlecenia produkcyjnego wskazuje zamówienie planowane, ale zamówienie planowane chyba nie jest obecnie ustalone w tym przypadku. Jeśli jednak zlecenie produkcyjne zostało oszacowane, rozłożenie jest wyzwalane ze zwolnionego zlecenia produkcyjnego, w którym nie istnieje planowane zamówienie
