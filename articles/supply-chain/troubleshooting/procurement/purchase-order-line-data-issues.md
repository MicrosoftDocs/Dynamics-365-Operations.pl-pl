---
title: Rozbieżności danych wiersza zamówienia zakupu
description: Istnieje rozbieżność danych lub rozbieżność danych w wierszach zamówienia zakupu.
author: SmithaNataraj
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: PurchLineManualCorrection, PurchTable, PurchLine, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ee2cb9a07c8a00a92c71e3e99d8ec20aa27fb20e
ms.sourcegitcommit: b9799a58d6ec221df86788bc37c4fbd28b435e89
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2022
ms.locfileid: "8100806"
---
# <a name="purchase-order-line-data-discrepancies"></a>Rozbieżności danych wiersza zamówienia zakupu

## <a name="symptoms"></a>Objawy

Podczas sprawdzania wierszy zamówienia zakupu można zauważyć co najmniej jeden z następujących problemów:

- Istnieje rozbieżność danych lub rozbieżność w resztach wiersza zamówienia zakupu (dostawa lub faktura).
- Istnieje uszkodzenie wiersza zamówienia zakupu lub stanu nagłówka.
- Nie można zafakturć zamówienia zakupu, ponieważ na przykład otrzymujesz co najmniej jeden z następujących komunikatów o błędach:

    - „Zatrzymane (błąd): Transakcja została już zaksięgowana”.
    - „Nie można zafakturować ilości, ponieważ liczba transakcji magazynowych o stanie Odebrane jest niewystarczająca”.
    - „Niewystarczająca liczba transakcji magazynowych ze stanem Zakupione” dla ilości %0 pozycji %1”.

- Nie można sfinalizować lub zamknąć zamówienia zakupu z powodu na przykład jednego z następujących problemów:

    - Przycisk **Zakończ** jest niedostępny.
    - Nie można anulować zamówioną ilość wiersza zamówienia zakupu dla zamówienia zakupu w stanie potwierdzoną i otrzymaną.

## <a name="cause"></a>Powód

Te problemy są zazwyczaj spowodowane uszkodzeniem danych lub rozbieżnością ilości pozostałych do jednego lub większej liczby wierszy zamówienia zakupu.

## <a name="resolution"></a>Rozwiązanie

Zazwyczaj te problemy można rozwiązać, aktualizując stan zakupu, pozostałą część dostawy i/lub pozostałą część faktury dla odpowiednich wierszy zamówienia zakupu, zgodnie z następującą procedurą.

1. Przejdź ręcznie do zadania **Zaopatrzenie i sourcing \> Zadania okresowe \> Czyszczenie \> Ręczne korygowanie wierszy zamówienia zakupu**.
1. W polu **Zamówienie zakupu** znajdź i wybierz zamówienie zakupu, które daje problemy.
1. W sekcji **Wiersze zamówienia zakupu** wybierz wiersz, w którym znaleziono rozbieżność.
1. W sekcji **Transakcje magazynowe** sprawdź wyświetlane dane. Jeśli występuje niespójność między wierszem zamówienia zakupu a jego transakcjami magazynowymi, należy wybrać jedno z następujących poleceń w okienku akcji, w zależności od miejsca, w którym są widać niespójności:

    - **Oblicz ponownie \> Oblicz ponownie ilość pozostałych do dostarczenia** — automatycznie aktualizuj wiersz zamówienia zakupu i stany nagłówka. Ta funkcja działa tylko dla wierszy zamówienia zakupu magazynowego (to jest wierszy, w których pozycja jest pozycję magazynową). Aktualnie nie są obsługiwane towary nie magazynowe i towary w wadze catch.
    - **Oblicz ponownie \> Przelicz pozostałą część faktury** — automatycznie aktualizuj wiersz zamówienia zakupu i stany nagłówka. Ta funkcja działa tylko dla wierszy zamówienia zakupu magazynowego (to jest wierszy, w których pozycja jest pozycję magazynową). Aktualnie nie są obsługiwane towary nie magazynowe i towary w wadze catch.
    - **Oblicz ponownie \> oblicz ponownie stan** — oblicz ponownie stan wybranego wiersza. Obliczenia są oparte na istniejącej logice. W związku z tym stan nagłówka zamówienia zakupu zostanie zaktualizowany zgodnie z potrzebą na podstawie nowego stanu wiersza zamówienia zakupu.

1. Jeśli nadal będzie widać niespójności w ilości pozostałych do użycia, można je edytować bezpośrednio w następujących polach:

    - Pozostałe do dostarczenia
    - Przypomnienie o dostarczeniu zapasów
    - Pozostałe do zafakturowania
    - Przypomnienie o fakturze magazynowej
