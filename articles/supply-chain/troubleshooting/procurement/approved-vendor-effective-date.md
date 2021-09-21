---
title: Nie można zmienić daty obowiązywania dla zatwierdzonego dostawcy
description: Lista zatwierdzonych dostawców według jednostki produktu nie zezwala na zmianę daty obowiązywania
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
ms.openlocfilehash: cb6dbd134d63daa163261cabdbd7eceb978877ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477264"
---
# <a name="cant-change-the-effective-date-for-an-approved-vendor"></a>Nie można zmienić daty obowiązywania dla zatwierdzonego dostawcy


## <a name="symptoms"></a>Objawy

Produkt ma zatwierdzonego dostawcę, który ma na przykład datę wejścia w życie 11 stycznia 2018 r. (*11/01/2018*) i datę ważności *Nigdy*. Próba zmiany daty rozpoczęcia na 10 stycznia 2018 (*10/01/2018*) lub 12 stycznia 2018 (*12/01/2018*) powoduje wyświetlenie następującego błędu:

> Nie można utworzyć rekordu na liście zatwierdzonych dostawców (PdsApproveVendorList). Wartość „Data ważności” musi być większa lub równa wartości „Data wejścia w życie”.

## <a name="resolution"></a>Rozwiązanie

Można wydłużyć okres, dla którego dostawca został zatwierdzony. Obowiązują następujące zasady:

- Aby zmienić datę wejścia w życie, tak aby była wcześniejsza niż jakikolwiek z istniejących rekordów (okresów) dla dostawcy towaru, data wygaśnięcia nowego okresu musi być wcześniejsza niż wszystkie daty wygaśnięcia w istniejących rekordach.
- Aby zmienić datę wygaśnięcia, tak aby była późniejsza niż jakikolwiek z istniejących okresów, data wejścia w życie musi być późniejsza niż ostatnia data wygaśnięcia dowolnego istniejącego rekordu.
- Aby skrócić cały okres, do którego dostawca jest zatwierdzony, należy usunąć lub zmodyfikować istniejące rekordy. Alternatywnie można skorzystać z przełącznika **obcinania** podczas importu. Ten przełącznik powoduje usunięcie wszystkich istniejących rekordów z tabeli dla zatwierdzonych dostawców według towarów.

W przykładzie scenariusza opisanego w opisie zagadnienia, gdy rekord ma datę wejścia w życie *11/01/2018* oraz datę ważności *Nigdy*, można zaimportować nowy rekord z datą wejścia w życie *10/01/2018* oraz datę ważności *Nigdy*. Nie można jednak skrócić okresu, tak aby Data wejścia w życie była aktualizowana do *12/01/2018* za pomocą funkcji zarządzania danymi. Tę zmianę należy wprowadzić w interfejsie użytkownika.
