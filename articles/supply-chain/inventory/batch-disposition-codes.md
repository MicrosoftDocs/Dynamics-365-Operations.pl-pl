---
title: Używanie kodów dyspozycji partii do oznaczania partii jako dostępnych lub niedostępnych
description: W tym artykule opisano sposób skonfigurowania i używania kodów dyspozycji partii w celu oznaczania partii jako dostępnych lub niedostępnych do użytku w planowaniu głównym, rezerwacji, pobieraniu i/lub wysyłce.
author: t-benebo
ms.date: 09/16/2022
ms.topic: article
ms.search.form: PdsDispositionMaster, InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-16
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: cfb0743a573550de93d75063df517e0c143f2568
ms.sourcegitcommit: 20ce54cb40290dd116ab8b157c0a02d6757c13f5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2022
ms.locfileid: "9542475"
---
# <a name="use-batch-disposition-codes-to-mark-batches-as-available-or-unavailable"></a>Używanie kodów dyspozycji partii do oznaczania partii jako dostępnych lub niedostępnych

W tym artykule opisano sposób skonfigurowania i użycia *kodów dyspozycji partii*. Każdy kod dyspozycji partii ma stan *Dostępny* albo *Niedostępny*. Kody dyspozycji partii przypisuje się do partii zapasów, aby wskazać, czy każda partia jest dostępna na etapie planowania głównego, rezerwacji, pobierania i/lub wysyłki.

Aby użyć kodów dyspozycji partii, należy skonfigurować kody i przypisać je do partii, które mają być zarządzane.

## <a name="set-up-batch-disposition-codes"></a>Ustawianie kodów dyspozycji partii

Należy skonfigurować każdy kod dyspozycji partii, który będzie używany w systemie. Można utworzyć dowolną liczbę kodów. (Na przykład można tworzyć kody w celu określenia różnych przyczyn, dla których partia może być dostępna lub niedostępna). Często jednak dostępne są tylko dwa kody: jeden dla *dostępnych* i jeden dla *niedostępnych*. Można także tworzyć kody niestandardowe umożliwiające używanie partii w niektórych operacjach, a nie w innych.

Wykonaj następujące kroki, aby skonfigurować kody dyspozycji partii.

1. Kliknij kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Partia \> Wzorzec dyspozycji partii**.
1. Strona **Wzorzec dyspozycji partii** zawiera listę bieżących kodów dyspozycji partii i umożliwia tworzenie, usuwanie i edytowanie tych kodów. Wykonaj jeden z następujących kroków:

    - Aby zmodyfikować istniejący kod, zaznacz go w okienku listy.
    - Aby utworzyć nowy kod, wybierz **Nowy** w okienku akcji.

1. Ustaw następujące pola w nagłówku nowego lub wybranego kodu:

    - **Kod dyspozycji partii** — służy do wprowadzania nazwy wyświetlanej dla tego kodu.
    - **Opis** — opisuje, jak należy korzystać z kodu.
    - **Stan dyspozycji partii** — umożliwia wybór stanu partii, do których przypisany jest ten kod:

        - *Niedostępne* — nie można używać partii do planowania głównego, rezerwacji, pobierania ani wysyłki. Po wybraniu tej wartości wszystkie opcje **Blokuj** na skróconej karcie **Ustawienia** są ustawione na *Tak*, a wszystkie opcje tabeli **Do dyspozycji** są ustawione na *Nie*. Można jednak zmienić niektóre z tych ustawień, aby dodać wyjątki.
        - *Dostępne* — można używać partii do planowania głównego, rezerwacji, pobierania i/lub wysyłki. Po wybraniu tej wartości wszystkie opcje **Blokuj** na skróconej karcie **Ustawienia** są ustawione na *Nie*, a wszystkie opcje tabeli **Do dyspozycji** są ustawione na *Tak*. Te ustawienia będą tylko do odczytu, gdy pole **Stan dyspozycji partii** ma wartość *Dostępne*.

1. Ustawienie **Stan dyspozycji partii** na wartość *Niedostępne* umożliwia dostosowanie stanu blokowania każdej operacji (rezerwacji, pobrania i wysyłki) dla każdego typu zamówienia (sprzedaży, przeniesienia i produkcji). W przypadku zleceń produkcyjnych można zablokować lub odblokować arkusz pobrania produkcji. Można także zablokować lub odblokować planowanie główne. Użyj opcji na skróconej karcie **Ustawienia**, aby zablokować lub odblokować każdą z wymaganych operacji. Ustaw wartość *Tak* dla opcji **Do dyspozycji**, aby włączyć planowanie główne, lub ustaw w nim wartość *Nie*, aby zablokować planowanie główne.

## <a name="assign-batch-disposition-codes-to-batches"></a>Przypisywanie kodów dyspozycji partii do partii

Po zdefiniowaniu wymaganych kodów dyspozycji partii należy wykonać poniższe kroki, aby przypisać je do partii.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Partie**.
1. Wybierz jedną lub więcej partii, do których ma zostać przypisany kod dyspozycji partii.
1. W okienku akcji na karcie **Reset** wybierz opcję **Resetuj kod dyspozycji partii**.
1. W oknie dialogowym **Zmiana ograniczeń dotyczących partii zapasów** ustaw pole **Nowy kod dyspozycji partii** na nazwę kodu, który chcesz przypisać.
1. Wybierz przycisk **OK**, aby nowe ustawienie i zapisać zmianę.

    Na stronie **Partie** wartości w kolumnach **Kod dyspozycji partii** i **Stan dyspozycji partii** są aktualizowane w taki sposób, aby odzwierciedlały nowe ustawienia wybranych partii.

## <a name="master-planning-example"></a>Przykład planowania głównego

W tym przykładzie pokazano, jak kody dyspozycji partii mogą wpływać na planowanie główne.

W tym przykładzie kody dyspozycji partii są ustawiane w następujący sposób:

- *P-Dostępne:*

    - **Stan dyspozycji partii:** *Dostępne*
    - **Do dyspozycji:** *Tak*

- *P-Niedostępne:*

    - **Stan dyspozycji partii:** *Niedostępne*
    - **Do dyspozycji:** *Nie*

Produkt (*Produkt-1*) ma dwie partie: *Partię_A* i *Partię-B*. Te partie są ustawiane w następujący sposób:

- *Partia-A:*

    - **Kod dyspozycji partii:** *P-Dostępne*
    - **Ilość dostępnych zapasów:** 1

- *Partia-B:*

    - **Kod dyspozycji partii:** *P-Niedostępne*
    - **Ilość dostępnych zapasów:** 1

Zamówienie sprzedaży (*SO1*) w ilości 2 produktu *Produkt-1*. Data dostawy to trzy dni od dzisiaj.

Uruchamia się planowanie główne i ustawia następujące wartości odpowiednie dla tego przykładu:

- **Planowane zamówienie:** *Zamówienie zakupu*
- **Strategia uzupełniania zapasów:** *Wymaganie*
- **Czas realizacji:** *0*

W wyniku uruchomienia planowania system używa dostępnej partii (*Partia-A*) w celu pokrycia ilości 1 produktu *Produktu-1* dla zamówienia sprzedaży *SO1*. Nie można jednak użyć *Partii-B*, ponieważ ta partia jest oznaczona jako niedostępnej do zaplanowania. Dlatego w celu pokrycia pozostałej ilości system tworzy planowane zamówienie zakupu (*PPO1*) dla nowej partii produktu *Produkt-1*.

Poniższa ilustracja przedstawia oś czasu dla wyniku planowania.

![Przykład, który przedstawia, jak kody dyspozycji partii mogą wpływać na planowanie główne.](media/batch-codes-planning-example.png "Przykład, który przedstawia, jak kody dyspozycji partii mogą wpływać na planowanie główne")
