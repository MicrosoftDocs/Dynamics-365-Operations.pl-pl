---
title: Harmonogram dostaw
description: Ten temat zawiera informacje o stronie Harmonogram dostaw i jej możliwościach.
author: crytt
ms.date: 9/3/2021
ms.topic: article
ms.search.form: ReqSupplyDemandSchedule, ReqSupplyDemandScheduleFilters, ReqSupplyDemandItemDetails, ReqTransFuturesActionsPart, ReqSupplyDemandOverviewLegendPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0760fcd5408d3960dcc55f773b4e09efc3c9f81c
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505596"
---
# <a name="supply-schedule"></a>Harmonogram dostaw

[!include [banner](../includes/banner.md)]

Strona **Harmonogram dostaw** zawiera pełny przegląd podaży i popytu na produkt lub rodzinę produktów. Informacje są filtrowane według lokalizacji, planu głównego i okresów. Za pomocą strony można również tworzyć nowe zamówienia, modyfikować istniejące zamówienia planowane i uruchamiać planowanie główne.

## <a name="open-the-supply-schedule-page"></a>Otwórz stronę Harmonogram dostaw

Stronę **Harmonogram dostaw** można otworzyć na jeden z następujących sposobów:

- Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Harmonogram dostaw**. W oknie dialogowym **Modyfikuj filtr** określ plan i produkt, którego chcesz szukać, wprowadzając wartości filtru w dostarczonych polach. (W pozostałej części tego tematu kolekcja wprowadzanych wartości filtru jest określana jako „filtr” lub „bieżący filtr”.) Po zakończeniu wybierz przycisk **OK**.
- Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**. Wybierz lub otwórz produkt. Następnie w okienku akcji na karcie **Plan** w grupie **Zobacz** wybierz pozycję **Harmonogram dostaw**.
- Przejdź do **Planowanie główne \> Konfiguracja \> Prognozowanie popytu \> Klucze alokacji pozycji**. Wybierz klucz alokacji pozycji, który jest używany jako rodzina produktów. W okienku akcji wybierz opcję **Harmonogram dostaw**.
- Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Zamówienia planowane**. Wybierz lub otwórz zamówienie planowane. Następnie w okienku akcji na karcie **Zobacz** w grupie **Zobacz** wybierz pozycję **Harmonogram dostaw**.

> [!NOTE]
> Po otwarciu strony **Harmonogram dostaw** z produktu, rodziny produktów lub zamówienia planowanego nie trzeba wprowadzać wartości filtru. System użyje domyślnego szablonu okresu.

## <a name="use-the-supply-schedule-page"></a>Użyj strony Harmonogram dostaw

Strona **Harmonogram dostaw** składa się z górnej sekcji, skróconej karty **Zapasy na końcu okresu**, dodatkowej skróconej karty, która staje się widoczna na podstawie wiersza wybranego w górnej sekcji i okienka pola informacji. (Aby otworzyć okienko pola informacji i wyświetlić pole informacji, wybierz opcję **Informacje pokrewne** na prawej krawędzi strony.)

### <a name="upper-section"></a>Górna sekcja

W górnej sekcji strony **Harmonogram dostaw** znajduje się siatka, która pokazuje poniższe dane dotyczące produktu lub rodziny produktów. Te dane są rozbijane na okresy zdefiniowane przez wartość **szablonu okresu** w filtrze.

- **Zapasy na początku okresu** — ten wiersz zawiera oczekiwane saldo magazynowe na początku okresu, jeśli występują wszystkie zamówienia w systemie.
- **Zapasy na końcu okresu** — ten wiersz zawiera oczekiwane saldo magazynowe na końcu okresu, jeśli występują wszystkie zamówienia w systemie.
- **Oznaczone zapasy na koniec okresu** — ten wiersz pokazuje ilość zapasów na koniec okresu, która jest oznaczana na potrzeby przyszłego popytu.
- **Podaż netto w okresie** – Ten wiersz pokazuje różnicę między podażą a popytem w okresie.
- **Minimalny zapas** — w tym węźle jest przedstawiany zapas bezpieczeństwa produktu lub rodziny produktów. Aby rozwinąć lub zwinąć ten węzeł, zaznacz go, a następnie wybierz pozycję **Rozwiń** lub **Zwiń** na pasku narzędzi. Ten węzeł jest widoczny tylko w przypadku, gdy istnieje zapas bezpieczeństwa produktu lub rodziny produktów.
- **Popyt** — ten węzeł pokazuje popyt na produkt lub rodzinę produktów. Popyt jest pogrupowany według typu transakcji. Aby rozwinąć lub zwinąć ten węzeł, zaznacz go, a następnie wybierz pozycję **Rozwiń** lub **Zwiń** na pasku narzędzi. Typy transakcji popytu obejmują sprzedaż, przeniesienia i arkusze magazynowe. Ten węzeł jest wyświetlany tylko wtedy, gdy istnieje zapotrzebowanie na produkt lub rodzinę produktów.
- **Podaż** — Ten węzeł pokazuje podaż produktu lub rodziny produktów. Podaż jest pogrupowana według typu transakcji. Aby rozwinąć lub zwinąć ten węzeł, zaznacz go, a następnie wybierz pozycję **Rozwiń** lub **Zwiń** na pasku narzędzi. Typy transakcji dostaw obejmują produkcję, zakup i transfery. Ten węzeł jest wyświetlany tylko wtedy, gdy istnieje podaż dla produktu lub rodziny produktów.

Wiele dostępnych przycisków paska narzędzi, ekranów FactBox i FastTab zależy od wyborów dokonanych w górnej sekcji. Zazwyczaj typ transakcji wybiera się, wybierając jeden z wierszy w węźle **Podaż** lub **Popyt**. Wybierzesz okres, wybierając określoną kolumnę dla wybranego wiersza.

Pasek narzędzi nad siatką w górnej sekcji strony **Harmonogram dostaw** zawiera następujące przyciski:

- **Rozwiń/zwiń** — rozwiń lub zwiń wybrany węzeł, taki jak węzeł **Popyt**, węzeł **Podaż** i ich podwęzły. (Węzły mają prefiks **\[+\]** lub **\[-\]** wskazujący, czy są obecnie zwinięte czy rozwinięte).
- **Nowy** — Otwórz menu, w którym każde polecenie z kolei otwiera okno dialogowe lub stronę, która umożliwia dodanie określonego typu elementu do zaznaczenia. Dostępne polecenia to **Prognoza dostaw**, **Zamówienie planowane**, **Zaplanowane zadanie Kanban**, **Nowe zlecenie produkcyjne**, **Zamówienie zakupu** i **Zamówienie przeniesienia**.
- **Planowanie główne** – Uruchomienie planowania głównego. Zostanie wyświetlone okno dialogowe, w którym możesz określić plan do uruchomienia. Domyślnie pole **Plan główny** jest zgodne z bieżącym filtrem.
- **Maksymalna liczba gotowych** — Umożliwia otwarcie strony **Maksymalna liczba gotowych** dla produktu zdefiniowanego w bieżącym filtrze
- **Aktualizuj zamówienia planowane** — otwórz stronę **Zamówienia planowane**, na której są widać planowane zamówienia na produkt lub rodzinę produktów zdefiniowaną w bieżącym filtrze.
- **Poziom** — rozsuń planowane zamówienia zgodnie z wyświetlonymi ustawieniami z okna dialogowego
- **Zasady planu materiałów według lokalizacji** — umożliwia otwarcie strony **Zapotrzebowania na towar** dla produktu zdefiniowanego w bieżącym filtrze.
- **Reguła Kanban** — otwórz stronę **reguł Kanban** dla produktu zdefiniowanego w bieżącym filtrze.

### <a name="fasttabs"></a>Skrócone karty

Strona **Harmonogram dostaw** może zawierać następujące skrócone karty:

- **Zapasy na końcu okresu** — na tej skróconej karcie są wyświetlane dane magazynowe na koniec okresu w postaci graficznej.
- **Profil dostaw** — na tej skróconej karcie są wyświetlane dane o dostawie w formacie graficznym. Staje się on widoczny po wybraniu węzła **dostawy** lub wiersza pod nim w górnej sekcji.
- **Podsumowanie** — na tej skróconej karcie są przedstawiane szczegóły podsumowania powiązane z typem transakcji wybranym w górnej sekcji. Na przykład wybranie **sprzedaży** pod węzłem **Popyt** na skróconej karcie umożliwia wybranie pól związanych z zamówieniami sprzedaży, takich jak **Żądane wiersze zamówienia sprzedaży** lub **Łączna kwota**. Jeśli wybierzesz **Zamówienia produkcyjne** w podwęźle **Produkcja** węzła **Podaż**, ta skrócona karta zawiera pola związane ze zleceniami produkcyjnymi, takie jak **Zaplanowane zamówienia produkcyjne** lub **Łącznie zaplanowano**. Wartości pól zależą od okresu wybranego w górnej sekcji. 
- **\[Typ transakcji\] - \[Okres\]** — na tej skróconej karcie są przedstawiane zamówienia dla typu transakcji i okresu wybranego w górnej sekcji. Nazwa skróconej karty odpowiada tym wyborom. Na przykład może mieć on nazwę **Zamówienia sprzedaży — Zaległości** lub **Zlecenia produkcyjne — Tydzień 37**.

### <a name="action-pane"></a>Okienko akcji

W okienku akcji dostępne są następujące przyciski:

- **Modyfikuj filtr** – Otwórz okno dialogowe **Modyfikowanie filtru**, w którym można zaktualizować wartości filtru, a następnie ponownie otworzyć stronę **Harmonogram dostaw**, odzwierciedlając zaktualizowane ustawienia filtru.
- **Pokaż opóźnienia** — wyróżnij odpowiednie wiersze w górnej sekcji, jeśli istnieje opóźniona kolejność tego typu transakcji.

### <a name="factbox-pane"></a>Okienko pola informacji

Aby otworzyć okienko pola informacji i wyświetlić pole informacji, wybierz opcję **Informacje pokrewne** na prawej krawędzi strony. Na stronie **Harmonogram dostaw** są dostępne następujące pola informacji:

- **Szczegóły pozycji** — w tym pole informacji są podane podstawowe informacje o produkcie zdefiniowanym w bieżącym filtrze. To pole jest puste, jeśli w filtrze zdefiniowano rodzinę produktów.
- **Akcje** — To FactBox pokazuje działania dla zleceń typu transakcji wybranego w górnej sekcji.
- **Opóźnienia** — To FactBox pokazuje opóźnienia dla zleceń typu transakcji wybranego w górnej sekcji.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
