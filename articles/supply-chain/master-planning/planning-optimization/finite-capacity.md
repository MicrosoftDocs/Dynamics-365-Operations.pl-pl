---
title: Ograniczone planowanie wydajności i planowanie
description: Ograniczone planowanie zdolności produkcyjnych pomaga zrozumieć, jaka ilość pracy może zostać wyprodukowana w danym okresie, gdy są brane pod uwagę ograniczenia dotyczące różnych zasobów.
author: t-benebo
ms.date: 09/19/2022
ms.topic: article
ms.search.form: ReqParameters, ReqPlanSched, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-19
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 3d116b5f7f456630415378e6cc069907e339068b
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689701"
---
# <a name="finite-capacity-planning-and-scheduling"></a>Ograniczone planowanie wydajności i planowanie

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!--KFM: Preview until 10.0.31 GA -->

Ograniczone planowanie zdolności produkcyjnych to podejście, które pomaga zrozumieć, jaka ilość pracy może zostać wyprodukowana w danym okresie, gdy są brane pod uwagę ograniczenia dotyczące różnych zasobów. Planowanie ograniczonych zdolności produkcyjnych ma na celu zapewnienie, że praca będzie kontynuowana w równomiernym i wydajnym stanie w całym zakładzie.

Planowanie i harmonogramowanie ograniczonych zdolności produkcyjnych tworzy bardziej realistyczny harmonogram procesów produkcyjnych, niż stwarza podejście nieskończonego załadunku. Jeśli nie ma wystarczającej pojemności zasobów, data dostawy zostanie wypchnięta, a zadanie zostanie zaplanowane, gdy będzie wystarczająca pojemność.

## <a name="planning-optimization-support-for-finite-capacity-planning"></a>Wsparcie optymalizacji planowania przy planowaniu ograniczonej wydajności

Planowanie i harmonogramowanie ograniczonych zdolności produkcyjnych działa prawie w ten sam sposób, niezależnie od tego, czy korzystasz z optymalizacji planowania, czy z wbudowanego mechanizmu planowania. Jednak Optymalizacja planowania nie używa parametru granicznego **Czas wąskiego gardła**. W przypadku korzystania z Optymalizacji planowania zasoby wąskich gardeł są zawsze planowane przy użyciu tego samego horyzontu czasowego, co zasoby nie będące wąskim gardłem (wskazane przez horyzont czasowy ograniczonej pojemności).

## <a name="set-up-finite-capacity-functionality"></a>Konfigurowanie funkcji ograniczonych zdolności produkcyjnych

Aby korzystać z funkcji ograniczonej zdolności produkcyjnej, należy włączyć globalne planowanie zdolności produkcyjnych i należy włączyć planowanie ograniczonej zdolności produkcyjnej zarówno dla planu głównego, w którym ma być ono używane, jak i dla każdego zasobu, do którego ma zastosowanie. W przypadku planów i zasobów, w których włączono ograniczone zdolności produkcyjne, planowanie planowanych zleceń produkcyjnych będzie uwzględniać zdolności produkcyjne, które zostały już zarezerwowane. Planowane zlecenia produkcyjne są planowane wstecz od daty zapotrzebowania. Jeśli zdolności produkcyjne nie są dostępne w celu spełnienia optymalnego harmonogramu, system spróbuje wcześniej wymagać towarów składowych. Jeśli wydajność może się zmieniać wraz ze zmianą wymagań (na przykład podczas pracy ze zmianami), nie należy używać funkcji wydajności ograniczonej, ponieważ obliczone czasy przetwarzania nie będą poprawne. Planowanie uwzględnia tylko pojemność, która jest już zarezerwowana dla zasobów, dla których jest włączona ograniczona pojemność. Włączając skończoną pojemność dla zasobu, umożliwiasz modyfikowanie horyzontu czasowego skończonej pojemności.

### <a name="activate-master-planning-parameters"></a>Aktywuj parametry planowania głównego

Aby korzystać z funkcji ograniczonych zdolności produkcyjnych, trzeba włączyć planowanie zdolności produkcyjnych na stronie **Parametry planowania głównego**.

1. Wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Parametry planowania głównego**.
1. Na karcie **Zamówienia planowane** w sekcji **Planowanie zdolności produkcyjnych** ustaw wartość **Tak** dla opcji *Produkcja*.

### <a name="activate-a-master-plan"></a>Aktywowanie planu głównego

Musisz włączyć planowanie i harmonogramowanie ograniczonej wydajności dla każdego planu głównego, w którym chcesz z niego korzystać.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. W okienku listy wybierz plan główny, który chcesz skonfigurować, aby używać ograniczonego planowania zdolności produkcyjnych i planowania.
1. Na karcie **Ogólne** w sekcji **Planowane Zamówienia produkcyjne** ustaw wartość **Tak** dla opcji *Ograniczone zdolności produkcyjne*.
1. Powtórz kroki 2 i 3 dla każdego dodatkowego planu głównego, który chcesz skonfigurować.

### <a name="activate-resources"></a>Aktywuj zasoby

Musisz włączyć planowanie i harmonogramowanie ograniczonej wydajności dla każdego zasobu, w którym chcesz z niego korzystać.

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Zasoby \> Zasoby**.
1. W okienku listy wybierz zasób, który chcesz skonfigurować, aby używać ograniczonego planowania zdolności produkcyjnych i planowania.
1. Na skróconej karcie **Operacja**, w sekcji **przycisk Wydajności** ustaw opcję **Ograniczone zdolności produkcyjne** na *Tak*.
1. Powtórz kroki 2 i 3 dla każdego dodatkowego zasobu, który chcesz skonfigurować.

## <a name="examples"></a>Przykłady

W tej sekcji przedstawiono następujące przykłady, które pokazują, jak pracować z planowaniem i harmonogramowaniem zarówno nieskończonych, jak i skończonych zdolności produkcyjnych:

- Przykład 1 – Nieskończone planowanie wydajności
- Przykład 2 – Ograniczone planowanie wydajności z jednym dniem w zakresie planowania
- Przykład 3 – Ograniczone planowanie wydajności z dwoma dniami w zakresie planowania

### <a name="preconditions"></a>Warunki wstępne

Wszystkie trzy przykłady zakładają warunki wstępne opisane w tej sekcji.

Produkt *Produkt1* ma trasę zawierającą następujące operacje.

| Nr operacji | Nazwa operacji | Zasób        | Czas procesu | Ilość z procesu | Następna |
|---------------|----------------|-----------------|----------|--------------|------|
| 10            | Spawanie        | Linia spawania    | 1        | 2            | 20   |
| 20            | Montaż     | Linia montażu | 1        | 4            |      |

Pracownicy w Twojej firmie pracują na jednej zmianie przez osiem godzin (8:00–16:00).

Istnieje zaplanowane zlecenie produkcyjne dla *24 sztuk* *Produktu1*. Ma termin dostawy *Dzisiaj + 3 dni*.

W wyniku planowania system ładuje zasoby w następujący sposób:

- **Linia spawania:** Ten zasób jest ładowany od *Dzisiaj o 8:00* do *Dzisiaj + 1 o 12:00*.
- **Linia montazu:** Ten zasób jest ładowany od *Dzisiaj +1 o 12:00* do *Dzisiaj + 2 o 10:00*.

Na poniższej ilustracji przedstawiono wynikowy wykres Gantta (wybierz go, aby wyświetlić większy widok).

[![Wykres Gantta pokazujący warunki wstępne.](media/finite-examples-conditions-small.png "Wykres Gantta pokazujący warunki wstępne")](media/finite-examples-conditions.png)

### <a name="example-1--infinite-capacity-planning"></a>Przykład 1 – Nieskończone planowanie wydajności

W tym przykładzie przedstawiono wyniki planowania w przypadku korzystania z planowania nieskończonej pojemności zamiast planowania pojemności skończonej.

Plan główny ma następujące odpowiednie ustawienie, które wyłącza planowanie zdolności produkcyjnych w ramach planu:

- **Ograniczone zdolności produkcyjne:** *Nie*

Opcja **Ograniczone zdolności produkcyjne** ma również wartość *Nie* dla obu odpowiednich zasobów, aby wyłączyć dla nich planowanie ograniczonych zdolności produkcyjnych:

- Linia spawania
- Linia montażu

Teraz użytkownik dodaje nowe zamówienie sprzedaży dla *8 sztuk* produktu *Product1* i uruchamia plan. W rezultacie system ładuje linię spawania od *Dzisiaj o 8:00* do *Dzisiaj o 12:00*. Po zakończeniu operacji na linii spawalniczej system załaduje linię montażową od *Dzisiaj o 12:00* do *Dzisiaj o 14:00*.

Na poniższej ilustracji przedstawiono wynikowy wykres Gantta (wybierz go, aby wyświetlić większy widok).

[![Wykres Gantta pokazujący nieskończony przykład planowania zdolności produkcyjnych.](media/finite-examples-example1-small.png "Wykres Gantta pokazujący nieskończony przykład planowania zdolności produkcyjnych")](media/finite-examples-example1.png)

### <a name="example-2--finite-capacity-planning-with-a-time-fence-of-one-day"></a>Przykład 2 – Ograniczone planowanie wydajności z jednym dniem w zakresie planowania

W tym przykładzie przedstawiono wyniki planowania w przypadku korzystania z planowania pojemności skończonej i przedziału czasowego jednego dnia.

Plan główny zawiera następujące odpowiednie ustawienia, które umożliwiają planowanie skończonych zdolności produkcyjnych i ustalają horyzont czasowy dla planu:

- **Ograniczone zdolności produkcyjne:** *Tak*
- **Horyzont czasowy ograniczonych zdolności produkcyjnych:** *1*

Opcja **Ograniczone zdolności produkcyjne** ma również wartość *Tak* dla obu odpowiednich zasobów, aby włączyć dla nich planowanie ograniczonych zdolności produkcyjnych:

- Linia spawania
- Linia montażu

Teraz użytkownik dodaje nowe zamówienie sprzedaży dla *8 sztuk* produktu *Product1* i uruchamia plan. W rezultacie system ładuje linię spawania od *Dzisiaj +1 o 8:00* do *Dzisiaj + 1 o 12:00*. Po zakończeniu operacji na linii spawalniczej system załaduje linię montażową od *Dzisiaj + 1 o 12:00* do *Dzisiaj + 1 o 14:00*. System uwzględnia skończoną pojemność tylko na jeden dzień.

Na poniższej ilustracji przedstawiono wynikowy wykres Gantta (wybierz go, aby wyświetlić większy widok).

[![Wykres Gantta przedstawiający skończone planowanie wydajności z jednodniowym horyzontem czasowym.](media/finite-examples-example2-small.png "Wykres Gantta przedstawiający skończone planowanie wydajności z jednodniowym horyzontem czasowym")](media/finite-examples-example2.png)

### <a name="example-3--finite-capacity-planning-with-a-time-fence-of-two-days"></a>Przykład 3 – Ograniczone planowanie wydajności z dwoma dniami w zakresie planowania

W tym przykładzie przedstawiono wyniki planowania w przypadku korzystania z planowania pojemności skończonej i dwudniowego przedziału czasowego.

Plan główny zawiera następujące odpowiednie ustawienia, które umożliwiają planowanie skończonych zdolności produkcyjnych i ustalają horyzont czasowy dla planu:

- **Ograniczone zdolności produkcyjne:** *Tak*
- **Horyzont czasowy ograniczonych zdolności produkcyjnych:** *2*

Opcja **Ograniczone zdolności produkcyjne** ma również wartość *Tak* dla obu odpowiednich zasobów, aby włączyć dla nich planowanie ograniczonych zdolności produkcyjnych:

- Linia spawania
- Linia montażu

Teraz użytkownik dodaje nowe zamówienie sprzedaży dla *8 sztuk* produktu *Product1* i uruchamia plan. W rezultacie system ładuje linię spawania od *Dzisiaj +1 o 12:00* do *Dzisiaj + 1 o 16:00*. Po zakończeniu operacji na linii spawalniczej system załaduje linię montażową od *Dzisiaj + 2 o 8:00* do *Dzisiaj + 2 o 10:00*. System uwzględnia skończoną pojemność tylko przez dwa dni.

Na poniższej ilustracji przedstawiono wynikowy wykres Gantta (wybierz go, aby wyświetlić większy widok).

[![Wykres Gantta przedstawiający skończone planowanie wydajności z dwudniowym horyzontem czasowym.](media/finite-examples-example3-small.png "Wykres Gantta przedstawiający skończone planowanie wydajności z dwudniowym horyzontem czasowym")](media/finite-examples-example3.png)

> [!IMPORTANT]
> Zawsze należy ustawiać horyzont czasowy o skończonej wydajności, zgodnie z wymaganiami Twojej firmy. Przykłady podane w tym artykule jedynie ilustrują funkcjonalność. W rzeczywistości jednodniowe ramy czasowe są prawdopodobnie zbyt niskie dla większości producentów, którzy stosują planowanie ograniczonej wydajności.
