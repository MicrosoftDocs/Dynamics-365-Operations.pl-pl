---
title: Raport magazynu wartości zapasów
description: W tym temacie wyjaśniono, jak uruchomić raport magazynowy wartości zapasówi udostępnić go cyfrowo jako stronę interaktywną w Microsoft Dynamics 365 Supply Chain Management lub w postaci wyeksportowanego dokumentu w dowolnym z kilku formatów.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0f54c02fc828d60f4ddb28be932bbf8eb137ee92
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008187"
---
# <a name="inventory-value-storage-report"></a>Raport magazynu wartości zapasów

W tym temacie wyjaśniono, jak uruchomić raport **Magazynu wartości zapasów** i udostępnić go cyfrowo jako stronę interaktywną w Microsoft Dynamics 365 Supply Chain Management lub w postaci wyeksportowanego dokumentu w dowolnym z kilku formatów.

Podczas wyświetlania raportu w przeglądarce kolumny i salda zagregowane są dynamicznie dostosowywane w zależności od skonfigurowanego układu. Można posortować wyniki, przefiltrować je, przejść do kolejnych danych i wykonać inne zadania.

Wyniki raportu są przechowywane w jednostce danych **Wartości zapasów**. Można więc filtrować i eksportować wyniki do formatu, takiego jak wartości rozdzielane przecinkami (CSV) lub Microsoft Excel.

Raport **Magazyn wartości zapasów** jest przydatny, gdy dane wyjściowe zawierają wiele wierszy. Na przykład pozycje 50 000 i 300 sklepów zostały utworzone jako magazyny. W takim przypadku, jeśli salda końcowe zapasów są żądane według towarów, oddziału i magazynu, produkcja będzie zawierała wiele wierszy.

> [!NOTE]
> Raport nie będzie zawierać sum częściowych, które są zdefiniowane w układzie raportu. Nie uwzględnia również sald księgi głównej, nawet jeśli są zdefiniowane w układzie raportu. Uzgodnienia księgi głównej należy wykonać przy użyciu bilansów próbnych.

## <a name="turn-on-the-inventory-value-storage-feature"></a>Włącz raport magazynu wartości zapasów

Aby można było wygenerować raport **magazynu wartości zapasów**, należy włączyć tę funkcję w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł** - zarządzanie kosztami
- **Nazwa funkcji** – Włącz raport magazynu wartości zapasów

## <a name="generate-an-inventory-value-storage-report"></a>Tworzenie raportu magazynu wartości zapasów

Wykonaj poniższe kroki, aby wygenerować i zapisać raport **magazynu wartości zapasów**:

1. Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Magazyn raportów wartości zapasów**.
1. Wybierz pozycję **Nowy**.
1. W wyświetlonym oknie dialogowym **Wartość zapasów** należy określić następujące wartości, aby określić, które rekordy będą uwzględniane w raporcie:

    - Na skróconej karcie **Parametry** należy wprowadzić unikatową nazwę raportu, a następnie za pomocą pól w sekcji **Zakres dat** określić, które rekordy mają być uwzględniane w raporcie. Aby zdefiniować interwał dat, można wybrać wstępnie zdefiniowany zakres (w odniesieniu do daty generowania raportu) w polu **Kod zakresu dat** lub wybrać określone daty w polach **Od dnia** i **Do dnia**.
    - Na skróconej karcie **Rekordy do uwzględnienia** należy skonfigurować filtry i ograniczenia w celu zdefiniowania danych uwzględnionych w raporcie.
    - Na skróconej karcie **Uruchom w tle** określ sposób, kiedy i jak często generowany jest raport.

    > [!NOTE]
    > Ten raport jest zawsze wykonywany w ramach zadania wsadowego.

1. Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okienko dialogowe.

Po zakończeniu zadania wsadowego raport będzie wyświetlany na stronie **Magazyn raportów wartości zapasów**. W celu wyświetlenia zaktualizowanego raportu może być konieczne odświeżenie strony.

## <a name="explore-an-inventory-value-storage-report"></a>Poznawanie raportu magazynu wartości zapasów

Po wygenerowaniu raportu można go przeglądać i eksplorować w dowolnym momencie wykonując następujące kroki:

1. Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Magazyn raportów wartości zapasów**.
1. Na liście wybierz raport.
1. Wybierz opcję **Wyświetl szczegóły**, aby wyświetlić zawartość raportu.
1. Przeglądaj raport, wykonując następujące kroki:

    - Podobnie jak w przypadku większości standardowych formularzy w Supply Chain Management możesz wybrać niemal dowolny nagłówek kolumny, aby posortować lub przefiltrować siatkę według wartości w tej kolumnie.
    - Pole **Filtr** umożliwia filtrowanie raportu według dowolnej wartości w dowolnej z kilku dostępnych kolumn.
    - Aby zapisać i załadować Ulubione kombinacje opcji sortowania i filtrowania, należy skorzystać z menu Widok (powyżej pola **Filtr**).

## <a name="export-an-inventory-value-storage-report"></a>Eksportowanie raportu magazynu wartości zapasów

Każdy generowany raport jest przechowywany w jednostce danych **Wartości zapasów**. Za pomocą standardowych funkcji Supply Chain Management można eksportować dane z tej jednostki do dowolnego obsługiwanego formatu danych, w tym także do pliku CSV lub programu Excel.

W poniższym przykładzie przedstawiono sposób eksportowania raportu dotyczącego **raportu wartości zapasów**.

1. Wybierz kolejno opcje **Administrowanie systemem \> Obszary robocze \> Zarządzanie danymi**.
1. W sekcji **Import/eksport** wybierz kafelek **Eksportuj**. 
1. Na wyświetlonej stronie **Eksportuj**, zostanie skonfigurowane zadanie eksportowania. Najpierw wprowadź nazwę grupy dla zadania.
1. W sekcji **Wybrane jednostki** wybierz pozycję **Dodaj jednostkę**.
1. W wyświetlonym oknie dialogowym można ustawić następujące pola:

    - **Nazwa jednostki** — umożliwia wybór **Wartości zapasów**.
    - **Docelowy format danych** — umożliwia wybór formatu, do którego mają zostać wyeksportowane dane.

1. Wybierz przycisk **Dodaj**, aby dodać nowy wiersz, a następnie kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.
1. Zazwyczaj w danym momencie można eksportować jeden raport. Aby wyeksportować jeden raport, należy skonfigurować filtr dla wiersza dodanego właśnie do okna dialogowego **Zapytanie**. W ten sposób można określić, który Raport z jednostki **Wartość zapasów** będzie uwzględniony w eksporcie. Wykonaj następujące kroki, aby skonfigurować następujące opcje filtrowania i wyeksportować pojedynczy raport:

    1. Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz.
    2. W polu **Tabela** ustaw wartość **Wartość zapasów**.
    3. W polu **Tabela pochodna** ustaw wartość **Wartość zapasów**.
    4. Ustaw pole **Pole**, według którego ma być wykonywane filtrowanie. Zazwyczaj używane jest pole **Nazwa wykonania** i/lub pole **Czas wykonania**.
    5. W polu **Kryterium** należy określić wartość, która ma być wyszukiwana w wybranym polu. (Jeśli w poprzednim kroku zaznaczono pole **Nazwa wykonania**, ta wartość będzie nazwą raportu. Jeśli zaznaczono pole **Czas wykonania**, będzie to godzina wygenerowania raportu.)
    6. Dodaj wiersze na karcie **Zakres** w razie potrzeby, dopóki szukany raport nie zostanie jednoznacznie zidentyfikowany.

1. Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okienko dialogowe.
1. Wybierz **Zapisz**, by zapisać ustawienia eksportu.
1. Otwórz kartę **Opcje eksportu** i wybierz pozycję **Eksportuj teraz**, aby wygenerować plik eksportu.
1. Zostanie otwarta strona **podsumowanie wykonania**, na której możesz zobaczyć stan zadania eksportowania oraz listę wyeksportowanych jednostek. W obszarze **Stan przetwarzania jednostki** wybierz jednostkę **Wartość zapasów** z listy, a następnie wybierz opcję **Pobierz plik**, aby pobrać dane wyeksportowane z tej jednostki.

Aby uzyskać więcej informacji o używaniu funkcji zarządzania danymi do eksportowania danych, patrze [omówienie importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
