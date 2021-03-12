---
title: Rozwiązywanie problemów z operacjami magazynowymi
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z operacjami magazynowymi.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3a22229106753d265a90f0ef05f5ac82dc745bbd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967162"
---
# <a name="troubleshoot-inventory-operations"></a>Rozwiązywanie problemów z operacjami magazynowymi

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z operacjami magazynowymi.

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Nie można znaleźć okna dialogowego „Przepływ pracy” dla arkuszy magazynowych.

### <a name="issue-description"></a>Opis problemu

Nie można znaleźć okna dialogowego **Przepływ pracy** na stronie arkusza lub powiązane operacje przepływu pracy są niedostępne.

Ten problem może mieć trzy przyczyny, co opisano w poniższych podsekcjach.

### <a name="issue-resolution-1"></a>Rozwiązanie problemu 1

Jeśli problem dotyczy wszystkich użytkowników, może on wystąpić, ponieważ przepływ pracy zatwierdzania nie został przypisany do nazwy arkusza. Aby naprawić problem, należy wykonać następujące czynności.

1. Przejdź do obszaru **Zarządzanie zapasami &gt; Ustawienia &gt; Nazwy arkuszy &gt; Zapasy**.
1. W okienku listy wybierz nazwę arkusza, aby otworzyć jego ustawienia.
1. Na skróconej karcie **Ogólne** ustaw opcję **Przepływ pracy zatwierdzania** na *Tak*. Wybierz **Tak**, jeśli zostanie wyświetlony monit o potwierdzenie zmiany.
1. W polu **Przepływ pracy** wybierz przepływ pracy do użycia dla wybranej nazwy arkusza.

### <a name="issue-resolution-2"></a>Rozwiązanie problemu 2

Jeśli w przepływie pracy jest używany dostosowany kod, problemy mogą wystąpić po uaktualnieniu systemu. Na przykład w przepływie pracy arkusza przycisk **Prześlij** może być wyszarzony, więc nie można go wybrać w celu zatwierdzenia przesłania.

Jeśli przycisk **Prześlij** jest wyszarzony, być może przepływ pracy został dostosowany, co oznacza, że metoda przepływu pracy `canSubmitToWorkflow()` w `FormDataUtil` została rozszerzona. Aby rozwiązać ten problem, zmień sposób rozszerzania metody `canSubmitToWorkflow()` w celu używania struktury w poniższym przykładzie.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a>Rozwiązanie problemu 3

Jeśli problem dotyczy tylko kilku określonych użytkowników, użytkownicy ci mogą nie mieć uprawnień zabezpieczeń wymaganych do uruchamiania operacji przepływu pracy w arkuszach magazynowych. Sprawdź, czy każdy z tych użytkowników ma uprawnienie zabezpieczeń *Obsługa przepływu pracy arkusza magazynowego*. Domyślnie to uprawnienie jest przypisywane do obowiązków o takiej samej nazwie i jest stosowane do ról *Pracownik magazynu* i *Menedżer magazynu*.

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a>Mój arkusz magazynowy ma nadal stan zablokowania przez system, a zadanie wsadowe przepływu pracy nie działa.

### <a name="issue-description"></a>Opis problemu

Jeden z arkuszy magazynowych jest zablokowany przez operację i nie jest zwalniany. Jeśli na przykład podczas księgowania wystąpi nieznany błąd (czyli operacja blokowania systemu), arkusz może pozostać w stanie zablokowania systemu. W takim przypadku program obsługi elementów roboczych przepływu pracy wystąpi błąd podczas blokowania weryfikacji.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Zaloguj się do wystąpienia programu SQL Server dla aplikacji Supply Chain Management i sprawdź, czy ustawienie **InventJournalTable.SystemBlocked** ma wartość *1*. Jeśli tak, upewnij się, że arkusz nie powinien być w stanie zablokowania, a następnie zresetuj pozycję **InventJournalTable.SystemBlocked** na *0*.

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a>Nigdy nie ukończono mojego przepływu pracy arkusza magazynowego i nie można go edytować ani zaksięgować.

### <a name="issue-description"></a>Opis problemu

Po przesłaniu przepływu pracy zatwierdzania arkusza proces przetwarzania przepływu pracy przestaje odpowiadać i nie można edytować ani przetwarzać arkuszy.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Istnieje kilka przyczyn, dla których przetwarzanie przepływu może nie zostać ukończone. Sprawdź następujące problemy:

- Przejdź do obszaru **Zarządzanie zapasami &gt; Ustawienia &gt; Przepływy pracy zarządzania zapasami** i przejrzyj konfigurację danego przepływu pracy. Aby uzyskać więcej informacji, zobacz temat [Przepływy pracy zatwierdzania arkusza magazynowego](inventory-journal-workflow.md).
- Przepływ pracy może napotkać wyjątek lub błąd. Przejrzyj historię elementów roboczych, których dotyczy ten przepływ pracy, aby sprawdzić, czy zawiera on błąd aplikacji, który kończy przepływ pracy.
- Arkusz magazynowy można aktualizować lub edytować tylko wtedy, gdy jest zatwierdzony. Jeśli odwołanie jest aktywne, można spróbować odwołać arkusz. Wykonanie zadania wsadowego przepływu pracy może być zawieszone z wielu przyczyn. Niektóre z tych przyczyn mogą być spowodowane przez problem ze strukturą przepływu pracy.

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a>Warunki przepływu pracy arkusza magazynowego mają zastosowanie tylko na poziomie arkusza, a nie na poziomie wiersza

### <a name="issue-description"></a>Opis problemu

Ten problem może wystąpić na przykład w przypadku próby skonfigurowania warunku przepływu pracy arkusza magazynowego dla kwoty kosztu. Warunek jest ustawiany w taki sposób, aby krok 1 był uruchamiany tylko wtedy, gdy kwota kosztu jest mniejsza niż 100. Następnie inny warunek jest ustawiany w taki sposób, aby krok 2 był uruchamiany tylko wtedy, gdy kwota kosztu jest większa lub równa 100. Potem podczas uruchamiania przepływu pracy historia przepływu pracy pokazuje tylko jeden wiersz, a pierwszy warunek jest zawsze obliczany jako *prawdziwy*, niezależnie od przesłanej wartości.

### <a name="issue-workaround"></a>Obejście problemu

W aktualnym wydaniu warunki przepływu pracy arkusza magazynowego mają zastosowanie tylko na poziomie arkusza, a nie na poziomie wiersza. Jest to celowe. Zaleca się, aby kryteria warunku ustawić tylko dla atrybutów na poziomie arkusza.

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a>Okienko filtru na stronie dostępnych zapasów nie filtruje wyników w oczekiwany sposób.

### <a name="issue-description"></a>Opis problemu

Filtry w okienku filtrów na stronie **dostępnych zapasów** nie filtruje wyników w oczekiwany sposób.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jest to celowe.

Strona  **dostępnych zapasów** jest składana z tabeli szczegółowych dostępnych zapasów, która zawiera wszystkie dostępne wymiary. Jednak lista na tej stronie jest podsumowaniem. Dlatego można łączyć wiersze z tabeli źródłowej, sumując wartości zgodnie z podanymi wymiarami.

Filtry zdefiniowane w okienku filtrów mają zastosowanie do tabeli źródłowej, a nie do listy agregowanej. Takie zachowanie może czasami mieć nieoczekiwane wyniki, tak jak pokazano w [tych przykładach](inventory-on-hand-list.md#examples).

Jednak  [filtry dostarczone w siatce](inventory-on-hand-list.md#grid-filters) *są* stosowane do zagregowanej listy. Filtry te obejmują zarówno QuickFilter na górze siatki, jak i filtr dla każdego nagłówka kolumny.

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>Jednostki i ilość jednostek nie działają poprawnie w arkuszu magazynowym.

### <a name="issue-description"></a>Opis problemu

Podczas pracy z jednostkami i ilościami w arkuszu magazynowymi może wystąpić jeden lub oba następujące problemy:

- Nie ma żadnych jednostek ani ilości jednostek w arkuszu magazynowym, gdy dla zwolnionego produktu jest ustawiona jednostka konwersji i nie można zmienić tej jednostki w arkuszu magazynowym.
- W arkuszu magazynowym są widoczne pola **Ilość** i **Jednostka**, ale pole **Ilość jednostki** jest niewidoczne. Po zmianie jednostki, wprowadzeniu ilości i zaksięgowaniu arkusza w arkuszu będzie nadal wyświetlana oryginalna jednostka miary dla tej ilości.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Aby naprawić ten problem, należy wykonać następujące czynności.

1. Upewnij się, że w obszarze roboczym **Zarządzanie funkcjami** jest włączona funkcja *Używanie jednostki miary i ilości jednostek w arkuszach magazynowych*. Ta funkcja dodaje pola **Jednostka** i **Ilość jednostek** do arkusza.
1. Po włączeniu tej funkcji użyj pól **Ilość**, **Ilość jednostki** i **Jednostka** w następujący sposób:

    - **Ilość** — określ ilość, używając domyślnej jednostki zdefiniowanej dla zwolnionego produktu. W tym miejscu jednak nie jest wyświetlana jednostka domyślna. Jeśli zostanie ustawiona konwersja między jednostką domyślną a jednostką wybraną w polu **Jednostka**, pole **Ilość** jest automatycznie aktualizowane na podstawie opcji wybranych w polach **Ilość jednostki** i **Jednostka**.
    - **Ilość jednostki** — określ ilość, używając jednostki wybranej w polu **Jednostka**.
    - **Jednostka** — wybierz jednostkę, która zostanie zastosowania do wartości w polu **Ilość jednostki**.

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Wyświetlany jest następujący komunikat o błędzie: „Maksymalna liczba miejsc dziesiętnych dla jednostki magazynowej wynosi 0”.

### <a name="issue-description"></a>Opis problemu

Podczas próby zaksięgowania transakcji magazynowej lub rezerwacji zapasów zostanie wyświetlony następujący komunikat o błędzie: „Maksymalna liczba miejsc dziesiętnych dla jednostki magazynowej wynosi 0”.

Ten problem występuje, gdy ilość transakcji magazynowej jest określona jako wartość dziesiętna poniżej poziomu dokładności, który obsługuje to pole. Na przykład dla transakcji magazynowej określono ilość *0,5*, ale są obsługiwane tylko liczby całkowite. Dlatego powinna to być wartość *1*, a nie *0,5*.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

1. Uruchom następujący skrypt w wystąpieniu programu SQL Server, aby zaokrąglić ilości w transakcjach magazynowych. Ten skrypt spowoduje poprawienie wartości w tabeli **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Uruchom sprawdzanie spójności dostępnych zapasów, dla których włączono opcję **poprawiania błędu**. Ten test spowoduje poprawienie wartości w tabeli **inventSum**.

> [!IMPORTANT]
> Zdecydowanie zalecamy uważne edytowanie skryptu zgodnie z wymaganiami środowiska, testowanie go w środowisku testowym, a następnie sprawdzanie wynikowych danych przed uruchomieniem skryptu w środowisku produkcyjnym.
