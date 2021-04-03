---
title: Zapytania o koszty z wyładunkiem
description: W tym temacie opisano sposób wyszukiwania i używania różnych typów zapytań dostępnych w module Koszty z wyładunkiem.
author: sherry-zheng
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMLine, ITMItemTracking, ITMContainerActivityTracking, ITMContainerTracking
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 10f5948b4e3df089aef982269143254d9ac1e8a9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500363"
---
# <a name="landed-cost-inquiries"></a>Zapytania o koszty z wyładunkiem

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="voyage-line-inquiries"></a>Zapytania o wiersz podróży

W zapytaniach dotyczących **Wierszy podróży** są wszystkie wiersze podróży w zakresie, w których są one związane z zapasami. To zapytanie może służyć jako filtr ułatwiający wyszukiwanie towaru, zamówienia zakupu lub innych przydatnych informacji. Można go również używać do identyfikowania oczekiwanej daty dostawy towaru, który może być w jednej lub większej liczby podróży. W ten sposób pomaga w zarządzaniu oczekiwanym przyjęciem na magazyn.

Aby otworzyć to zapytanie, przejdź do **Koszt z wyładunkiem \> Zapytania \> Wiersze podróży**.

### <a name="overview-tab"></a>Karta Przegląd

Karta **Przegląd** na stronie zapytania **Wiersze podróży** zawiera siatkę, która zawiera podstawowe informacje o poszczególnych wierszach podróży. W poniższej tabeli opisano kolumny w siatce.

| Kolumnowy | opis |
|---|---|
| **Numer pozycji** | Pozycja dla linii podróży. |
| **Odwołanie** | Typ zamówienia (zamówienie zakupu lub zamówienie przeniesienia). |
| **Identyfikator** | Numer zamówienia zakupu lub numer zamówienia przeniesienia. |
| **Folio** | Folio powiązane z wierszem podróży. |
| **Kontener wysyłkowy** | Kontener transportowy powiązany z wierszem podróży. |
| **Podróż** | Podróż powiązana z wierszem podróży. |
| **Ilość** | Ilość towaru w wierszu podróży. |
| (Inne wymiary) | Kolumny dla dodatkowych wymiarów można wyświetlać w wymaganych wymiarach. Wymiary te obejmują numer partii, stan zapasów i magazyn. W okienku akcji wybierz **Zapasy \> Wyświetl wymiary**, aby otworzyć okno dialogowe, w którym można wybrać wymiary, które mają zostać dołączyć. |

### <a name="general-tab"></a>Karta Ogólne

Wybierz kartę **Ogólne**, aby wyświetlić więcej informacji o wierszu aktualnie wybranym na karcie **Przegląd**.

### <a name="dimensions-tab"></a>Karta Wymiary

Wybierz kartę **Wymiary**, aby wyświetlić wartości wszystkich dostępnych wymiarów dla wiersza aktualnie wybranego na karcie **Przegląd**, niezależnie od wymiarów wybranych do wyświetlenia na tej karcie.

## <a name="cost-estimate-inquiries"></a>Zapytania dotyczące szacowania kosztów

Po każdym wygenerowaniu oszacowania kosztów szacowanie jest dodawane do strony zapytania **Szacowanie kosztów**. Aby uzyskać pełne informacje dotyczące sposobu generowania, wyświetlania i pracy z oszacowaniami kosztów (w tym szacunkami na stronie zapytania), zobacz temat [Szacowanie i zarządzanie kosztami z wyładunkiem](estimate-manage-landed-costs.md).

## <a name="item-tracking"></a>Śledzenie pozycji

Strona **Śledzenia pozycji** umożliwia wyświetlenie otwartych wierszy zamówień zakupu oraz ich bieżących stanów. Aby mogły pojawiać się w tym miejscu, wiersze nie muszą być skojarzone z podróżą. Jeśli jednak towar jest skojarzony z podróżą, wiersz rekordu śledzenia towaru zawiera identyfikator podróży.

Aby otworzyć tę stronę, przejdź do śledzenia **Koszt z wyładunkiem \> Zapytania \> Śledzenie \> Śledzenie pozycji**.

Ponieważ system prawdopodobnie zawiera bardzo wiele wierszy zamówienia zakupu, strona **Śledzenie pozycji** początkowo nie zawiera rekordów. Rozpocznij, używając pól filtru w górnej części strony, aby zdefiniować zestaw szukanych wierszy zamówienia zakupu. Następnie w okienku akcji wybierz opcję **Aktualizuj**, aby wygenerować listę. W dowolnym polu filtru można użyć gwiazdki (\*) jako znaku wieloznacznego. Na przykład aby znaleźć wszystkie wiersze zamówienia zakupu dla towarów, których nazwa zawiera słowo „DVD”, ustaw w polu **Typ** wartość **Nazwa produktu** i wprowadź *\*DVD\** w polu **Wartości pola**.

> [!NOTE]
> Obecnie zamówienia niezrealizowane obejmują tylko zamówienia sprzedaży. Oferty sprzedaży nie są pokazywane ani uznawane za niezrealizowane.

W poniższej tabeli opisano kolumny w siatce na stronie **Śledzenie pozycji**.

| Kolumnowy | opis |
|---|---|
| **Port docelowy** | Ostateczne miejsce docelowe. |
| **Potwierdzone** | Potwierdzona data wiersza zamówienia zakupu. |
| **Data dostawy** | Data dostawy wiersza zamówienia zakupu. |
| **Podróż** | Jeśli wiersz jest związany z podróżą, identyfikator podróży. |
| **Kontener wysyłkowy** | Identyfikator kontenera, jeśli wiersz jest dołączony do kontenera wysyłkowego. |
| **Port wysyłki** | Bieżący port na podstawie pierwszego etapu w formularzu śledzenia, w którym nie ustawiono rzeczywistej daty dla kontenera wysyłkowego skojarzonego z wierszem zamówienia zakupu. |
| **Działanie** | Bieżące działanie na podstawie pierwszego etapu w formularzu śledzenia, w którym nie ustawiono rzeczywistej daty dla kontenera wysyłkowego skojarzonego z wierszem zamówienia zakupu. |
| **Szacowana data końcowa** | Data oczekiwanej podróży w magazynie docelowym. |
| **Imię i nazwisko** | Nazwa dostawcy. |
| **Stan podróży** | Status wysyłki dołączony do wiersza zamówienia zakupu. |
| **Numer pozycji** | Kod towaru dla wiersza zamówienia zakupu. |
| **Zewnętrzne** | Imię dostawcy towaru. |
| **Nazwa produktu** | Nazwa towaru w wierszu zamówienia zakupu. |
| **Ilość** | Ilość w wierszu zamówienia zakupu dla wiersza zamówienia zakupu. |
| **Jednostka** | Jednostka miary dotycząca danego wiersza zamówienia zakupu. |
| **Odwołanie** | Typ zamówienia (zamówienie zakupu lub zamówienie przeniesienia) |
| **Numer odwołania** | Numer zamówienia zakupu lub numer zamówienia przeniesienia. |
| **Zamówienie niezrealizowane** | Symbol oznacza, że istnieją niezrealizowane zamówienia sprzedaży towaru. |
| (Inne wymiary) | Kolumny dla dodatkowych wymiarów można wyświetlać w wymaganych wymiarach. Wymiary te obejmują numer partii, stan zapasów i magazyn. W okienku akcji wybierz **Wyświetl wymiary**, aby otworzyć okno dialogowe, w którym można wybrać wymiary, które mają zostać dołączyć. |

### <a name="related-information-about-backorders"></a>Informacje pokrewne o zamówieniach niezrealizowanych

Aby wyświetlić więcej informacji o zamówieniach niezrealizowanych, wybierz kartę **Informacje pokrewne** po prawej stronie strony, a następnie wybierz pozycję **Zamówienia niezrealizowane**. Aby wyświetlić jeszcze więcej informacji o określonym niezrealizowanych zamówieniach, wybierz wiersz dla niego, a następnie wybierz łącze **Więcej**.

## <a name="individual-shipping-container-tracking"></a>Śledzenie indywidualnego kontenera wysyłkowego

**Zapytanie dotyczące śledzenia poszczególnych kontenerów wysyłkowych** zawiera filtr, który umożliwia znalezienie kontenera wysyłkowego, a następnie określenie wszystkich wierszy podróży w tym kontenerze.

Aby otworzyć to zapytanie, przejdź do śledzenia **Koszt z wyładunkiem \> Zapytania \> Śledzenie \> Śledzenie poszczególnych kontenerów wysyłkowych**.

## <a name="multiple-shipping-container-tracking"></a>Śledzenie wielu kontenerów wysyłkowych

**Zapytanie dotyczące śledzenia wielu kontenerów wysyłkowych** udostępnia filtr, który pozwala znaleźć zbiór kontenerów transportowych, a następnie zidentyfikować wszystkie linie rejsowe w tych kontenerach.

Aby otworzyć to zapytanie, przejdź do śledzenia **Koszt z wyładunkiem \> Zapytania \> Śledzenie \> Śledzenie wielu kontenerów wysyłkowych**.
