---
title: Klucze redukcji prognozy
description: Ten temat zawiera przykłady pokazujące konfigurowanie klucza redukcji. Zawiera informacje o różnych ustawieniach kluczy redukcji i wynikach ich zastosowania. Za pomocą klucza redukcji można określić sposób zmniejszania prognozowanych zapotrzebowań.
author: roxanadiaconu
manager: tfehr
ms.date: 04/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 25cdde073878ed090a4d981eff75a337a79b37af
ms.sourcegitcommit: 724f5b400a4e7c385da9d8b22db416ebc3623b93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/03/2020
ms.locfileid: "3225112"
---
# <a name="forecast-reduction-keys"></a>Klucze redukcji prognozy

[!include [banner](../includes/banner.md)]

W tym temacie omówiono różne metody, które służą do zmniejszania prognozowanych zapotrzebowań. Zawiera przykłady wyników każdej z tych metod. Ponadto wyjaśniono, jak tworzyć, konfigurować i używać kluczy redukcji prognoz. Niektóre metody używają kluczy redukcji prognoz do zmniejszania prognozowanych zapotrzebowań.

## <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Metody używane w celu zmniejszenia prognozowanych zapotrzebowań

Po dołączeniu prognozy do planu głównego można wybrać sposób redukowania prognozowanych zapotrzebowań, gdy rzeczywisty popyt jest uwzględniony. Należy zauważyć, że planowanie główne wyklucza prognozowane zapotrzebowania z przeszłości, co obejmuje wszystkie zapotrzebowania podlegające prognozie przed datą dzisiejszą.

Aby uwzględnić prognozę w planie głównym i wybrać metodę, która jest używana do zmniejszenia prognozowanych zapotrzebowań, przejdź do **Planowanie główne \> ustawienia \> Plany \> plany główne**. W polu **Model prognozy** wybierz model prognozy. W polu **Metoda używana w celu zmniejszenia prognozowanych zapotrzebowań** wybierz metodę. Dostępne są następujące opcje:

- Brak
- Procent — klucz redukcji
- Transakcje — klucz redukcji
- Transakcje — okres dynamiczny

Poniższe sekcje zawierają więcej informacji o każdej funkcji.

### <a name="none"></a>Brak

Jeśli wybrana zostanie wartość **Brak**: Prognozowane zapotrzebowanie nie będzie redukowane podczas planowania głównego. W takim przypadku planowanie główne tworzy zamówienia planowane w celu dostarczania prognozy popytu (prognozowane zapotrzebowania). Planowane zamówienia zachowują sugerowaną ilość bez względu na inne typy popytu. Na przykład, jeśli zostaną złożone zamówienia sprzedaży, planowanie główne tworzy dodatkowe zamówienia planowane w celu dostarczenia zamówienia sprzedaży. Ilość prognozowanego zapotrzebowania nie jest zmniejszona.

### <a name="percent--reduction-key"></a>Procent — klucz redukcji

Jeśli wybierzesz **Procent — klucz redukcji**, zmniejsza wymagania dotyczące prognozy popytu według wartości procentowych i okresów czasu, które są definiowane według klucza redukcji. W takim przypadku planowanie główne tworzy zamówienia planowane, gdzie ilość jest obliczana jako klucz redukcji × Prognozowana ilość w każdym okresie. Jeśli istnieją inne typy zapotrzebowania, planowanie główne tworzy również zamówienia planowane w celu zaspokojenia tego popytu.

#### <a name="example-percent--reduction-key"></a>Przykład: Procent — klucz redukcji

W tym przykładzie pokazano, jak klucz redukcji zmniejsza wymagania dotyczące prognozy popytu według wartości procentowych i okresów, które są definiowane według klucza redukcji.

Na przykład wprowadzono następującą prognozę sprzedaży w planie głównym.

| Miesiąc    | Prognoza popytu |
|----------|-----------------|
| Styczeń  | 1 000           |
| luty | 1 000           |
| marzec    | 1 000           |
| kwiecień    | 1 000           |

Na stronie **Klucz redukcji** ustaw następujące wiersze.

| Zmiana | Jednostka  | Procent |
|--------|-------|---------|
| 1      | Miesiąc | 100     |
| 2      | Miesiąc | 75      |
| 3      | Miesiąc | 50      |
| 4      | Miesiąc | 25      |

Przypisz klucz redukcji do grupy zapotrzebowania dla towaru. Następnie na stronie **plany główne** w polu **Metoda używana w celu zmniejszenia prognozowanych zapotrzebowań** wybierz **procent — klucz redukcji**.

W tym przypadku uruchomienie planowania w dniu 1 stycznia spowoduje, że wymagania prognozy popytu zostaną zużyte według wartości procentowych ustawionych na stronie **Klucze redukcji**. Następujące ilości wymagania są przenoszone do planu głównego.

| Miesiąc                | Planowana ilość zamówienia | Obliczenie    |
|----------------------|------------------------|----------------|
| Styczeń              | 0                      | = 0% × 1,000   |
| luty             | 250                    | = 25% × 1,000  |
| marzec                | 500                    | = 50% × 1,000  |
| kwiecień                | 750                    | = 75% × 1,000  |
| Od maja do grudnia | 1 000                  | = 100% × 1,000 |

### <a name="transactions--reduction-key"></a>Transakcje — klucz redukcji

Jeśli wybierzesz **Transakcje — klucz redukcji** zmniejsza wymagania dotyczące prognozy popytu według transakcji zachodzących w okresach czasu, które są definiowane według klucza redukcji.

#### <a name="example-transactions--reduction-key"></a>Przykład: Transakcje— klucz redukcji

W tym przykładzie pokazano, jak rzeczywiste zamówienia występujące w okresach zdefiniowanych przez klucz redukują wymagania prognozy popytu.

W tym przykładzie wybierasz **Transakcje — klucz redukcji** w **Metoda używana w celu zmniejszenia prognozowanych zapotrzebowań** na stronie **Plany główne**.

1 stycznia istnieją następujące zamówienia sprzedaży.

| Miesiąc    | Zamówiona liczba sztuk |
|----------|--------------------------|
| Styczeń  | 956                      |
| Luty | 1,176                    |
| Marzec    | 451                      |
| Kwiecień    | 119                      |

Przy tej samej prognozie popytu dla 1000 sztuk na miesiąc do planu głównego przesyłane są następujące ilości wymagania.

| Miesiąc                | Wymagana liczba sztuk |
|----------------------|---------------------------|
| Styczeń              | 44                        |
| luty             | 0                         |
| marzec                | 549                       |
| kwiecień                | 881                       |
| Od maja do grudnia | 1 000                     |

### <a name="transactions--dynamic-period"></a>Transakcje — okres dynamiczny

W przypadku wybrania **transakcje — okres dynamiczny**, prognozowane zapotrzebowania są redukowane zgodnie z rzeczywistymi transakcjami zamówień w okresie dynamicznym. Okres dynamiczny obejmuje aktualne daty prognozy i kończy się na początku kolejnej prognozy. W takim przypadku planowanie główne tworzy zamówienia planowane w celu dostarczania prognozy popytu (prognozowane zapotrzebowania). Jednak po zrealizowaniu rzeczywistych transakcji zamówień prognozowane wymagania są redukowane. Rzeczywiste transakcje zużywają część prognozowanego zapotrzebowania.

Ta opcja jest używana, występują następujące zachowania:

- Klucze redukcji nie są wymagane/używane. 
- Jeśli prognoza zostanie zmniejszona do zera, wymagania prognozy dla bieżącej prognozy przybierają wartość 0 (zero).
- Jeśli nie ma żadnej przyszłej prognozy, wymagania prognozy z ostatnio wprowadzonej prognozy są redukowane.
- Horyzonty czasowe są uwzględniane w obliczeniach redukcji prognozy.
- Dni pasywne są uwzględniane w obliczeniach redukcji prognozy.
- Jeśli transakcje rzeczywistego zamówienia przekraczają prognozowane zapotrzebowanie, pozostałe transakcje nie są przekazywane do następnego okresu prognozy.

#### <a name="example-1-transactions--dynamic-period"></a>Przykład 1: Transakcje — okres dynamiczny

Tutaj jest prosty przykład pokazujący sposób działania metody **transakcje — okres dynamiczny**.

Na przykład wprowadzono następującą prognozę sprzedaży w planie głównym.

| Data       | Prognoza popytu |
|------------|-----------------|
| 1 stycznia  | 1 000           |
| 1 lutego | 1 000             |

Można również utworzyć następujące zamówienia sprzedaży.

| Data        | Ilość dla zamówienia sprzedaży |
|-------------|----------------------|
| 15 stycznia  | 200                  |
| 15 lutego | 400                  |

W takim wypadku są tworzone następujące zamówienia planowane.

| Data prognozy popytu | Ilość | Wyjaśnienie                           |
|--------------------- |----------|---------------------------------------|
| 1 stycznia            | 800      | Prognozowane zapotrzebowanie (= 1000 – 200) |
| 15 stycznia           | 200      | Zapotrzebowanie w zamówieniach sprzedaży             |
| 1 lutego           | 600      | Prognozowane zapotrzebowanie (= 1000 – 400) |
| 15 lutego          | 400      | Zapotrzebowanie w zamówieniach sprzedaży             |

#### <a name="example-2-transactions--dynamic-period"></a>Przykład 2: Transakcje — okres dynamiczny

W większości przypadków systemy są skonfigurowane tak, aby transakcje zmniejszały prognozy popytu w określonych okresach prognozy: tygodnie, miesiąca itd. Te okresy są definiowane w kluczu redukcji. Jednak czas między dwoma wierszami popytu mogą również *implikować* okresu.

W tym przykładzie tworzymy prognozę popytu dla następujących dat i ilości.

| Data       | Prognoza popytu |
|------------|-----------------|
| 1 stycznia  | 1 000           |
| 5 stycznia  | 500             |
| 12 stycznia | 1 000           |

Należy zauważyć, że w tej prognozie, nie ma okresu pomiędzy datami prognoz. Między pierwszą a drugą datą jest czterodniowy odstęp, a między drugą a trzecią datą jest odstęp 7 dni. Te różne zakresy są okresami dynamicznymi.

Można również utworzyć następujące wiersze zamówienia sprzedaży.

| Data                             | Ilość dla zamówienia sprzedaży |
|----------------------------------|----------------------|
| 15 grudnia w poprzednim roku | 500                  |
| 3 stycznia                        | 100                  |
| 10 stycznia                       | 200                  |

W takim przypadku prognoza jest zmniejszana w następujący sposób:

- Ponieważ pierwsze zamówienie sprzedaży nie mieści się w żadnym okresie, więc nie ograniczy żadnej prognozy.
- Ponieważ drugie zamówienie sprzedaży mieści się w dniach 1-5 stycznia, więc ograniczy prognozę dla 1 stycznia o 100.
- Ponieważ trzecie zamówienie sprzedaży mieści się w dniach 5-12 stycznia, więc ograniczy prognozę dla 5 stycznia o 200.

W takim wypadku są tworzone następujące zamówienia planowane.

| Data prognozy popytu             | Ilość | Wyjaśnienie                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| 15 grudnia w poprzednim roku | 500      | Zapotrzebowanie w zamówieniach sprzedaży                                            |
| 1 stycznia                        | 900      | Prognozowane zapotrzebowanie na okres od 1 stycznia do 5 stycznia (= 1000 – 100) |
| 3 stycznia                        | 100      | Zapotrzebowanie w zamówieniach sprzedaży                                            |
| 5 stycznia                        | 300      | Prognozowane zapotrzebowanie na okres od 5 stycznia do 10 stycznia (= 500 – 200)  |
| 12 stycznia                       | 1 000    | Prognozowane zapotrzebowanie na okres od 12 stycznia końca                      |

## <a name="create-and-set-up-a-forecast-reduction-key"></a>Tworzenie i konfigurowanie klucza redukcji prognoz

Klucz redukcji prognozy jest używany w metodach **transakcje — klucz redukcji** i **procent — klucz redukcji** redukcji prognozowanego zapotrzebowania. Wykonaj następujące kroki, aby utworzyć i skonfigurować klucz redukcji.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Klucze redukcji**.
2. Wybierz **nowy** lub naciśnij **Ctrl + N**, aby utworzyć klucz redukcji.
3. W polu **klucza redukcji** wprowadź unikatowy identyfikator klucza redukcji prognoz. Następnie w polu **Nazwa** nadaj nazwę. 
4. Definiowanie okresów i procenta klucza redukcji w każdym okresie:

    - Pole **Data wejścia w życie** wskazuje datę rozpoczęcia tworzenia okresów. Jeśli opcja **Użyj daty obowiązywania** jest ustawiona jako **Tak**, okresy zaczynają się zgodnie z datą wejścia w życie. Jeśli ta opcja jest ustawiona jako **Nie**, okresy zaczynają się w dniu uruchomienia planowania głównego.
    - Definiowanie okresów, w których powinna mieć miejsce redukcja prognozy.
    - W danym okresie należy określić wartości procentowe, o które powinno być zmniejszane prognozowane zapotrzebowanie. Można wprowadzić wartość dodatnią, aby zmniejszyć wymagania, lub wartość ujemną, aby zwiększyć zapotrzebowanie.

## <a name="use-a-reduction-key"></a>Użyj Klucza redukcji

Klucz redukcji prognoz musi być przypisany do grupy zapotrzebowania towaru. Wykonaj następujące kroki, aby przypisać klucz redukcji do grupy zapotrzebowania dla towaru.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Grupy zapotrzebowania**.
2. Na skróconej karcie **Inne** w polu **Klucz redukcji** wybierz klucz redukcji, który zostanie przypisany do grupy zapotrzebowania. Klucz redukcji następnie stosuje się do wszystkich elementów, które należą do grupy zapotrzebowania.
3. Aby użyć klucza redukcji do obliczania redukcji prognozy w planowaniu głównym, to ustawienie należy zdefiniować w oknie ustawień planu głównego lub planu wg prognozy. Przejdź do jednej z następujących lokalizacji:

    - Planowanie główne \> Konfiguracja \> Plany \> Plany wg prognoz
    - Planowanie główne \> Ustawienia \> Plany \> Plany główne

4. Na stronie **planów wg prognozy** lub **planów głównych** na skróconej karcie **ogólne** w polu **metoda używana do zmniejszenia prognozowanych zapotrzebowań** wybierz opcję **procent — klucz redukcji**lub **transakcje — klucz redukcji**.

## <a name="reduce-a-forecast-by-transactions"></a>Redukcja prognoz według transakcji

Po wybraniu metody **Transakcje — klucz redukcji** lub **Transakcje — okres dynamiczny** do redukcji prognozowanego zapotrzebowania można wybrać, które transakcje będą uwzględniane w redukowaniu prognozy. Na stronie **Zwolnione produkty** na skróconej karcie **Inne** w polu **Zmniejsz prognozę o** wybierz **Wszystkie transakcje**, jeśli wszystkie transakcje mają redukować prognozę, lub **Zamówienia**, jeśli tylko zamówienia sprzedaży mają redukować prognozę.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie planów głównych](master-plans.md)
