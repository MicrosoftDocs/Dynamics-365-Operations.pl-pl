---
title: Błąd podczas zmiany stanu ze Zgłoszone jako gotowe na Zakończone
description: Podczas zmiany stanu zlecenia produkcyjnego ze Zgłoszone jako gotowe na Zakończone może wystapić błąd. Na tej stronie opisano sposób eliminowania tego problemu.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 744637f5cccffe44b85f77c1a9df2034012fac40
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477314"
---
# <a name="error-when-changing-status-of-production-order-from-reported-as-finished-to-end"></a>Błąd podczas zmiany stanu zlecenia produkcyjnego ze Zgłoszone jako gotowe na Zakończone

## <a name="symptoms"></a>Objawy

Gdy stan zlecenia produkcyjnego zostanie zmieniony ze Zgłoszone jako gotowe na Zakończone, zobaczysz jeden z następujących komunikatów o błędzie:

> Aktualizuj konflikt. Koszt standardowy jest niezgodny z wartością zapasów finansowych po aktualizacji.

> Wystąpił błąd krytyczny w funkcji InventCostMovement.checkVariance.

## <a name="cause"></a>Powód

Ten problem występuje, ponieważ dane źródłowe zostały zmienione przez inny proces. Proces podejmie próbę zaktualizowania danych do pięciu razy. Jeśli konflikt wciąż istnieje po pięciu próbach, zostanie wyświetlony jeden z powyższych komunikatów.

## <a name="resolution"></a>Rozwiązanie

Jest to celowe. Aby złagodzić ten problem, wznów zadanie wsadowe. Należy zakończyć pracę.

Jeśli zadanie wsadowe konsekwentnie kończy się niepowodzeniem po jego wznowieniu, sprawdź, czy dokładność zaokrąglania dla domyślnej waluty księgi jest zgodna z zaokrągleniem zastosowanym do wartości w tabeli InventSum. Jeśli precyzja zaokrąglania została zmieniona na niezgodną wartość, prawdopodobnie trzeba ją zmienić z powrotem na zgodną wartość. Wyszukaj **ModifiedDateTime**. W tym przypadku wartość zwykle pokazuje, że dokładność zaokrąglenia była ostatnio zmieniona.
