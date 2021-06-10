---
title: Wyświetlany jest monit o zapisanie ustawień zapotrzebowania elementu, mimo że nie wprowadzono żadnych zmian
description: Wyświetlany jest monit o zapisanie ustawień zapotrzebowania elementu, mimo że nie wprowadzono żadnych zmian.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049484"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a>Wyświetlany jest monit o zapisanie ustawień zapotrzebowania elementu, mimo że nie wprowadzono żadnych zmian

Numer artykułu z bazy wiedzy: 4615588

## <a name="symptoms"></a>Objawy

W niektórych scenariuszach po zaimportowaniu towarów za pomocą strony *Zapotrzebowanie na towar V2* po otwarciu strony **Zapotrzebowania na towar** może zostać wyświetlony następujący komunikat:

> Czy przed zamknięciem chcesz zapisać zmiany?

Ten komunikat zostanie wyświetlony nawet wtedy, gdy nie poczynisz żadnych zmian.

## <a name="resolution"></a>Rozwiązanie

Strona **Zapotrzebowanie na towar** zawiera złożoną logikę wartości domyślnych, która może spowodować, że komunikat będzie wyświetlany po bezpośrednich zmianach wprowadzonych w bazie danych, na przykład za pośrednictwem importu encji. Na przykład w polu encji `AREGENERALSETTINGSOVERRIDDEN` ustawiono wartość *Nie*, ale importowany jest plik, który zawiera nowe lub zmodyfikowane wartości dla pól, takich jak `PRODUCTCOVERAGEGROUPID` i/lub `VENDORACCOUNTNUMBER`. W takim przypadku, ponieważ pole `AREGENERALSETTINGSOVERRIDDEN` ma wartość *Nie*, wartości zostaną automatycznie wyczyszone z pól, gdy strona **Zapotrzebowania na towar** zostanie otwarta po raz pierwszy po imporcie. Zmiany zapisane w odpowiedzi na monit zostaną zapisane w bazie danych. W przeciwnym razie przy kolejnym otwarciu strony zostanie wyświetlony ten sam komunikat.

Aby zapobiec takiemu zachowaniu, ale również uwzględnić wartości dla pól, takich jak `PRODUCTCOVERAGEGROUPID` przez import jednostek, należy ustawić w `AREGENERALSETTINGSOVERRIDDEN` wartość *Tak* podczas importowania.
