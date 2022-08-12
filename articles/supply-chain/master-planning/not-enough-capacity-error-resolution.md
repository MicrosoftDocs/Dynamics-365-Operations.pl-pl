---
title: Napraw błąd silnika planowania „Nie można znaleźć wystarczającej pojemności” i skończoną pojemność
description: Ten artykuł zawiera informacje o przyczynach i rozwiązaniach problemu polegającego na tym, że nie można zaplanować zlecenia produkcyjnego %1. Nie znaleziono wystarczających zdolności produkcyjnych”.
author: t-benebo
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4f54c06a07b3cdd0b8fe2cc52614189ff31ba7f
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135608"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>Usuwanie błędu aparatu planowania „Nie znaleziono wystarczających zdolności produkcyjnych”

[!include [banner](../includes/banner.md)]

Po uruchomieniu planowania może pojawić się następujący komunikat o błędzie:

> Nie można zaplanować zlecenia produkcyjnego %1. Brak wystarczających zdolności produkcyjnych.

Istnieje kilka przyczyn awarii aparatu planowania i wystawienia tego komunikatu o błędzie. Ten artykuł zawiera wskazówki, które pomogą w znalezieniu przyczyny głównej błędu, a następnie zmniejszeniu związanego z nim ryzyka.

## <a name="review-the-applicable-resources"></a>Przeglądanie odpowiednich zasobów

Ten błąd może wystąpić, jeśli odpowiednie zasoby nie spełniają wymagań dotyczących operacji w siedzibie dla zlecenia produkcyjnego.

Aby przejrzeć dostępne zasoby, wykonaj poniższe kroki.

1. Przejdź do opcji **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne** i otwórz lub wybierz zlecenie produkcyjne, którego nie można zaplanować.
1. W okienku akcji na karcie **Zlecenie produkcyjne** w grupie **Szczegóły produkcji** wybierz opcję **Marszruta**.
1. Na stronie **Marszruta produkcji** wybierz operację, a następnie w okienku akcji wybierz opcję **Pasujące zasoby**.
1. W oknie dialogowym **Pasujące zasoby** ustaw pole **Użyj wymagań dla** na *Planowanie operacji* lub *Planowanie zadań*, w zależności od typu stosowanego planowania.
1. Upewnij się, że w siedzibie dla zlecenia produkcyjnego istnieją pasujące zasoby.

## <a name="review-the-calendars-that-are-associated-with-resources"></a>Przeglądanie kalendarzy skojarzonych z zasobami

Błąd może wystąpić, jeśli żaden kalendarz nie jest skojarzony z zasobem lub grupą zasobów lub jeśli skojarzony kalendarz nie jest poprawnie skonfigurowany (na przykład nie ma godzin pracy lub wydajność jako wartość procentowa wynosi 0 \[zero\]).

Aby sprawdzić, czy kalendarz jest skojarzony z zasobem lub grupą zasobów, wykonaj następujące kroki.

1. Przejdź do opcji **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne** i otwórz lub wybierz zlecenie produkcyjne, którego nie można zaplanować.
1. W okienku akcji na karcie **Zlecenie produkcyjne** w grupie **Szczegóły produkcji** wybierz opcję **Marszruta**.
1. Na stronie **Marszruta produkcji** wybierz operację, a następnie w okienku akcji wybierz opcję **Pasujące zasoby**.
1. W oknie dialogowym **Pasujące zasoby** wybierz zasób, a następnie wybierz pozycję **Wyświetl zasób**. Ewentualnie wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w polu **Grupa zasobów**, a następnie wybierz polecenie **Wyświetl szczegóły**.
1. Na stronie **Zasoby** lub **Grupy zasobów** na skróconej karcie **Kalendarze** upewnij się, że kalendarz jest skojarzony z zasobem lub grupą zasobów.

> [!NOTE]
> Jeśli ten błąd wystąpi podczas planowania operacji, należy się upewnić, że kalendarz jest skojarzony ze wszystkimi pasującymi grupami zasobów.

Aby przejrzeć ustawienia kalendarza, wykonaj następujące kroki.

1. Przejdź do pozycji **Administrowanie organizacją \> Konfiguracja \> Kalendarze \> Kalendarze** i wybierz kalendarz skojarzony z zasobem lub grupą zasobów.
1. W okienku akcji wybierz opcję **Czasy pracy**.
1. Na stronie **Czasy pracy** upewnij się, że strona nie jest pusta. Ponadto dla określonych dni upewnij się, że pole **Kontrola** nie ma wartości *Zamknięto*, istnieją czasy pracy, a pole **Wydajność jest wartością procentową** nie jest ustawione na *0* (zero).

Jeśli kalendarz jest skojarzony z kalendarzem bazowym, należy również sprawdzić konfigurację kalendarza bazowego.

> [!NOTE]
> W planowaniu operacji kalendarz grupy zasobów służy do ustalania godzin i dat rozpoczęcia i zakończenia każdej operacji. Ogranicza on również czas, który system może zaplanować dla jednej określonej operacji na jeden dzień w jednej konkretnej grupie zasobów. Jeśli na przykład czas pracy grupy zasobów jednego określonego dnia to godziny od 8:00 do 16:00, obciążenie pracą jednej operacji dla grupy zasobów nie może przekroczyć obciążenia mieszczącego się w przedziale ośmiu godzin, niezależnie od dostępnych zdolności produkcyjnych danej grupy zasobów w danym dniu. Jednak dostępne zdolności produkcyjne mogą dodatkowo ograniczyć obciążenie pracą.

## <a name="review-the-scheduling-parameters"></a>Przeglądanie parametrów planowania

Aby zapewnić dobrą wydajność, aparat planowania wyszukuje zasób tylko przez określony czas i dla określonej liczby konfliktów planowania.

Aby przejrzeć parametry planowania, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Administrowanie organizacją \> Konfiguracja \> Parametry planowania**.
1. Wykonaj jeden z następujących kroków:

    - Jeśli opcję **Limit czasu planowania włączony** ustawiono na *Nie*, przejdź do kroku 3.
    - Jeśli opcję **Limit czasu planowania włączony** ustawiono na *Tak*, zwiększ wartość pola **Maksymalny czas planowania na sekwencję**, aby zyskać więcej czasu na ukończenie przetwarzania.

1. Wykonaj jeden z następujących kroków:

    - Jeśli opcję **Limit czasu optymalizacji włączony** ustawiono na *Nie*, przejdź do kroku 4.
    - Jeśli opcję **Limit czasu optymalizacji włączony** ustawiono na *Tak*, zwiększ wartość pola **Limit czasu prób optymalizacji**, aby zyskać więcej czasu na ukończenie przetwarzania.

1. Jeśli zmieniono dowolne ustawienia na stronie, ponownie zaplanuj zamówienie, aby spróbować jeszcze raz.

## <a name="review-capacity"></a>Przeglądanie zdolności produkcyjnych

Błąd może wystąpić podczas wykonywania ograniczonego planowania, ale brak wolnych zdolności produkcyjnych.

Aby wykonywać nieskończone planowanie zdolności produkcyjnych, wykonaj następujące kroki.

1. Przejdź do opcji **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne** i wybierz lub otwórz wybierz zlecenie produkcyjne, którego nie można zaplanować.
1. W okienku akcji, na karcie **Harmonogram** w grupie **Zlecenie produkcyjne** wybierz pozycję **Zaplanuj operacje** lub **Zaplanuj zadania**.
1. W oknie dialogowym **Planowanie operacji** lub **Planowanie zadań** ustaw opcję **Ograniczone zdolności produkcyjne** na *Nie*.
1. Kliknij przycisk **OK**, aby zaplanować zamówienie.

Aby przejrzeć dostępne zdolności produkcyjne zasobu, wykonaj następujące kroki.

1. Przejdź do pozycji **Administracja organizacją \> Zasoby \> Zasoby** i wybierz zasób dostępny dla zamówienia, który nie może zostać zaplanowany.
1. W okienku akcji, na karcie **Zasób**, w grupie **Widok** wybierz **Obciążenie zdolności produkcyjnych** lub **Obciążenie zdolności produkcyjnych, graficznie** i upewnij się, że są dostępne zdolności produkcyjne.

Aby przejrzeć dostępne zdolności produkcyjne grupy zasobów, wykonaj następujące kroki.

1. Przejdź do pozycji **Administracja organizacją \> Zasoby \> Grupy zasobów** i wybierz grupę zasobów dostępną dla zamówienia, które nie może zostać zaplanowane.
1. W okienku akcji, na karcie **Grupa zasobów**, w grupie **Widok** wybierz **Obciążenie zdolności produkcyjnych** lub **Obciążenie zdolności produkcyjnych, graficznie** i upewnij się, że są dostępne zdolności produkcyjne.

## <a name="master-planning-books-a-resource-when-the-resource-calendar-is-closed"></a>Planowanie główne księguje zasób podczas zamknięcia kalendarza zasobów

Podczas planowania operacji planowanie główne będzie planować zdolności produkcyjne zgodnie z kalendarzem głównej grupy zasobów. Księguje operację pomocniczą w tym samym czasie co operację główną i nie uwzględnia kalendarzy ani zdolności produkcyjnych operacji pomocniczej. Może to spowodować zaplanowanie zlecenia produkcyjnego w zamkniętym kalendarzu lub w czasie, gdy operacja pomocnicza nie jest dostępna (zamknięte w kalendarzu, brak zdolności produkcyjnych).

Podczas planowania zadań podczas planowania zamówienia planowanie główne uwzględnia zdolności produkcyjne i kalendarz operacji głównej i pomocniczej. Aby można było zaplanować zamówienie, kalendarze zasobów obu operacji muszą być otwarte i mieć dostępne zdolności produkcyjne.

## <a name="maximum-job-lead-time-is-too-short"></a>Maksymalny czas realizacji zadania jest zbyt krótki

Silnik planowania nie będzie mógł zaplanować zamówienia, jeśli **Maksymalny czas realizacji zadania** ustawiony dla twojej witryny jest mniejszy niż czas realizacji określony dla elementu w domyślnych ustawieniach zamówienia lub ustawieniach zasięgu.

Aby wyświetlić lub edytować ustawienie **Maksymalny czas realizacji zadania** dla swojej witryny, przejdź do **Kontrola produkcji \> Ustawienia \> Parametry kontroli produkcji** i otwórz zakładkę **Ogólne**.

Aby wyświetlić lub edytować domyślne ustawienia zamówienia dla przedmiotu, wykonaj poniższe kroki:

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Na liście znajdź i zaznacz odpowiedni produkt.
1. Na pasku akcji otwórz zakładkę **Zarządzanie zapasami** i wybierz **Domyślne ustawienia zamówień**.
1. Rozwiń kartę **Zapasy** i przejrzyj lub edytuj ustawienie **Czas realizacji zapasów**.

Aby wyświetlić lub edytować ustawienia objęcia dla przedmiotu, wykonaj poniższe kroki:

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Na liście znajdź i zaznacz odpowiedni produkt.
1. W okienku akcji otwórz kartę **Plan** i wybierz pozycję **Objęcie przedmiotu**.
1. Otwórz zakładkę **Czas realizacji** i przejrzyj lub edytuj wartość **Czas produkcji**, jeśli to konieczne.

## <a name="excessive-quantity-of-required-resources"></a>Nadmierna ilość wymaganych zasobów

Podczas planowania silnik próbuje dopasować wymaganą ilość zasobów ustaloną dla operacji na trasie do odpowiednich zasobów zgodnie z wymaganiami dotyczącymi zasobów operacji. Ustawienie zbyt dużej ilości zasobów może spowodować, że trasa będzie niewykonalna, co spowoduje błąd planowania.

Użyj poniższej procedury, aby sprawdzić zarówno określoną ilość, jak i odpowiednie zasoby dla wybranego produktu, trasy i operacji trasy:

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Na siatce znajdź i zaznacz odpowiedni produkt.
1. W okienku akcji otwórz kartę **Konstruuj** i wybierz opcję **Trasa**.
1. Na siatce znajdź i zaznacz odpowiednią trasę.
1. Otwórz kartę **Przegląd** u dołu strony.
1. Wybierz operację z listy wybranych operacji na trasie.
1. Wybierz **Odpowiednie zasoby**, aby otworzyć okno dialogowe, w którym można wyświetlić zasoby właściwe dla wybranej operacji trasy.
1. Otwórz zakładkę **Obciążenie zasobów**. W polu **ilość** znajduje się ilość zasobów wymaganych dla wybranej operacji na trasie. W razie potrzeby przeglądaj je i/lub edytuj.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
