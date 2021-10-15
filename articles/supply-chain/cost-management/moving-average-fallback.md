---
title: Średnia ruchoma sekwencji kosztu rezerwowego
description: Ten temat zawiera informacje dotyczące sekwencji kosztów rezerwowych dla obliczeń średniej ruchomej w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: d91b3b4b8d49e59aa03d62f4dd101b5a1ec18c41
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568214"
---
# <a name="moving-average-fallback-cost-sequence"></a>Średnia ruchoma sekwencji kosztu rezerwowego

[!include [banner](../includes/banner.md)]

Jednym ze sposobów obliczania kosztów zapasów jest użycie _średniej ruchomej_. Z każdym towarem magazynowym można skojarzyć maksymalnie trzy wartości kosztów:

- **Ostatni problem** — ostatni koszt rozchód przypisany przed stanem zapasów był ujemny
- **Aktywny koszt** — ostatni koszt uaktywniony w wersji wyceny
- **Cena towaru** — koszt określony dla zwolnionego produktu

Aby określić, które z tych wartości kosztów powinny być używane w obliczeniach średniej ruchomej, system używa _sekwencji kosztu rezerwowego_ do określenia kolejności preferencji dla wartości. Jeśli preferowana wartość kosztu jest niedostępna, system używa wartości kolejnego uprzywilejowania i tak dalej.

W poprzednich wersjach Microsoft Dynamics 365 Supply Chain Management, system używał stałej sekwencji kosztów rezerwowych (_Ostatni problem — Koszt aktywny – Cena towaru_). W wersji 10.0.11 ta sekwencja nadal jest sekwencją domyślną. Można jednak również włączyć funkcję umożliwiającą wybranie spośród trzech dostępnych sekwencji kosztów rezerwowych. Ta funkcja może być szczególnie przydatna w organizacjach, które regularnie korzystają z ujemnych wartości zapasów.

Aby można było korzystać z selektora kosztu rezerwowego, użytkownik (lub administrator) musi skorzystać z [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) w celu włączenia funkcji, która ma nazwę _Średnia ruchoma sekwencji kosztu rezerwowego_.

Aby wybrać sekwencję kosztów rezerwowych dla obliczeń średniej ruchomej, należy wykonać następujące kroki.

1. Otwórz stronę **Parametry**.
2. Na karcie **Księgowanie zapasów** w sekcji **Średnia ruchoma** określ wartość w polu **Sekwencji kosztu rezerwowego** na jedną z następujących wartości:

    - **Ostatni problem — Koszt aktywny — Cena towaru** — ta sekwencja jest sekwencją domyślną. Jest to ta sama sekwencja, która jest używana, jeśli funkcja _Średnia ruchoma sekwencji kosztu rezerwowego_ nie jest włączona.
    - **Aktywny koszt — Ostatni problem**
    - **Koszt aktywny — cena towaru** — w organizacjach mogą występować problemy z wydajnością, jeśli są one używane w procesach biznesowych, w których zapasy są zwykle ujemne, a jednocześnie objętość transakcji jest wysoka. To ustawienie pomaga złagodzić te problemy z wydajnością.

![Parametry księgowania zapasów.](media/inventory-accounting-parameters.png "Parametry księgowania zapasów")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]