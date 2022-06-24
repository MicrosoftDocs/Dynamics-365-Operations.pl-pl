---
title: Alokacja grupy czynności
description: W tym artykule opisano sposób skonfigurowania kroku alokacji grupy czynności, w tym włączenia dla niego przetwarzania równoległego.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c6b89364afd57b9c4b4413d0319b86e725433594
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906959"
---
# <a name="wave-allocation"></a>Alokacja grupy czynności

[!include [banner](../includes/banner.md)]

Przetwarzanie grupy czynności może być czasochłonne, a większość czasu przetwarzania jest zużywana na etapie alokacji i w kroku tworzenia pracy.

Teraz można uruchomić każdy z tych kroków równolegle, co może poprawić wydajność przetwarzania grupy czynności i umożliwić większą przepustowość grupy czynności w tym samym magazynie. W tym artykule opisano, jak skonfigurować metodę alokacji grupy czynności, która będzie uruchamiana równolegle. Aby uzyskać więcej informacji dotyczących tego, jak skonfigurować tworzenie pracy w celu uruchomienia równoległego, zobacz temat [Planowanie tworzenia pracy podczas grupy czynności](configure-wave-schedule-work-creation.md)c

Wcześniej można było alokować tylko jedną grupy czynności w magazynie na raz. To ograniczenie zostało usunięte i zastąpione przez nowe ograniczenie, które blokuje tylko pozycję i wymiary powyżej lokalizacji w hierarchii rezerwacji. Wymiary powyżej lokalizacji zawsze zawierają wymiary produktu. Jeśli na przykład towar jest skonfigurowany przy użyciu opcji *Kolor*, wówczas warianty *czerwony*, *niebieski* i *żółty* mogą być przetwarzane równolegle.

Oznacza to, że jeśli ten sam towar o takich samych wymiarach powyżej lokalizacji będzie alokowany przez jedną grupy czynności, inne grupy czynności będą musiał czekać na zablokowanie tego samego towaru i wymiarów. Jeśli blokada nie może zostać na czas uzyskana, wystąpi błąd i przetwarzanie grupy czynności nie powiedzie się.

Aby można było korzystać z przetwarzania równoległego, grupy czynności muszą być uruchamiane w trybie wsadowym.

## <a name="performance-improvements"></a>usprawnienia dotyczące wydajności

Korzyści z wydajnością przetwarzania równoległego należą do dwóch kategorii:

- **Poprawiona przepustowość** — przepustowość fal przepływu pracy zwykle poprawia się, nawet jeśli nie skonfigurowano przetwarzania równoległego, zwłaszcza w scenariuszach, w których towary w obrębie tych fal nie zachodzą na siebie.
- **Usprawnianie alokacji jednej grupy czynności** — testowanie danych klientów wykazało blisko 50% poprawy wydajności po przełączeniu do alokacji równoległej. Przetwarzanie równoległe jest wykonywane dla towarów i wymiarów powyżej lokalizacji, więc usprawnienia zależą od tego, ile elementów zawiera ta grupy czynności, dostępna infrastruktura oraz czas trwania alokacji w porównaniu z czasem trwania tworzenia pracy.

## <a name="configure-parallel-allocation"></a>Konfigurowanie alokacji równoległej

### <a name="warehouse-management-parameters"></a>Parametry zarządzania magazynem

Aby użyć równoległego przetwarzania alokacji, wybierz opcje **Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem**, otwórz kartę **Przetwarzanie grupy czynności** i ustaw następujące ustawienia:

- **Grupa przetwarzania wsadowego grupy czynności** — wybierz grupę przetwarzania wsadowego, która ma być pierwszym przetwarzaniem grup czynności. Kolejne przetwarzanie alokacji można wykonać z użyciem różnych grup zadań wsadowych.
- **Przetwarzaj zadania wsadowe** — ustaw wartość *Tak*, aby używać przetwarzania równoległego.
- **Oczekiwanie na blokadę (ms)** - Wprowadź czas w milisekundach, przez który krok alokacji zaczeka na zasób systemowy zablokowany przez inny krok alokacji. Po przekroczeniu tego czasu grupa czynności nie jest przetwarzana i zostanie wyświetlony komunikat o błędzie. Zaleca się, aby na alokację jednej jednostki logicznej można było zakończyć co najmniej kilka sekund.

Aby uzyskać informacje o tych i innych opcjach przetwarzania grupy czynności na stronie **Parametry zarządzania magazynem**, zobacz [Parametry magazynu do przetwarzania grupy czynności](wave-warehouse-parameters.md)c

## <a name="wave-process-methods"></a>Metody przetwarzania grupy czynności

Aby skonfigurować przetwarzanie równoległe:

1. Wybierz kolejno opcje **Zarządzanie magazynem  Ustawienia  Grupy czynności  Metody procesów grupy czynności**.
1. Wybranie metody `allocateWave` w siatce.
1. W okienku akcji wybierz **Konfiguracja zadania**.
1. Zostanie otwarta strona **Konfiguracji zadania metody wpisu grupy czynności**. W tej siatce są wyszczególnione wszystkie magazyny, w których została skonfigurowana metoda `allocateWave`. Przetwarzanie równoległe będzie używane tylko dla magazynów, które są wymienione na liście. W razie potrzeby za pomocą przycisków okienka akcji dodaj lub usuń magazyny z siatki. 
1. Dla każdego magazynu należy wprowadzić następujące ustawienia:
    - **Maksymalna liczba zadań wsadowych** — Umożliwia określenie liczby podań wsadowych, które powinny zostać użyte do alokacji dla wybranego magazynu. Optymalna liczba zadań wsadowych zależy od dostępnej infrastruktury oraz od tego, jakie inne zadania wsadowe są przetwarzane na serwerze. Testy przeprowadzone na czterech podstawowych środowiskach przeznaczonych do przetwarzania grupy czynności pokazywały, że korzystanie z ośmiu zadań przyniosło dobre wyniki.
    - **Grupa przetwarzania wsadowego grupy czynności** — Określone grupy zadań wsadowych mogą być używane w różnych magazynach, aby umożliwić skalowanie w trybie alokacji w poszczególnych magazynach.

## <a name="enable-or-disable-parallelization-across-all-legal-entities"></a>Włączanie lub wyłączanie równoległości we wszystkich firmach

Zaleca się, aby metoda `allocateWave` była uruchamiana równolegle we wszystkich firmach, ponieważ pomaga to zwiększyć wydajność przetwarzania grupy czynności. Począwszy od wersji 10.0.17 Supply Chain Management, funkcja *Równoległości grupy czynności dla metody alokowania grupy czynności* jest domyślnie włączona dla wszystkich nowych i zaktualizowanych instalacji i nie można jej ponownie wyłączyć. Po włączeniu tej funkcji mają miejsce następujące zdarzenia:

- Metoda `allocateWave` została zaktualizowana, tak aby uwzględniała ustawienie konfiguracji zadania, które umożliwia korzystanie ze strony **Metod przetwarzania grupy czynności** w celu zdefiniowania liczby zadań, które będą uruchamiane jednocześnie, co odpowiada liczbie równoległych procesów. W związku z tym czas użyty w kroku alokacji grupy czynności (zwykle 30% do 60% całkowitego czasu przetwarzania) jest reduowany o współczynnik w przybliżeniu odpowiadający liczbie zadań. Można także wybrać partię, która ma być przypisana do przetwarzania tych zadań. Należy pamiętać, że wszystkie firmy zostaną skonfigurowane do przetwarzania wsadowego grupy czynności. W przypadku magazynów, które są już skonfigurowane do przetwarzania wsadowego grup pracy, a dla magazynów, które zostały już skonfigurowane do używania tej metody `allocateWave` równolegle, istniejąca konfiguracja zostanie zachowane.
- Domyślnie wszystkie nowe firmy są skonfigurowane do przetwarzania wsadowego grup czynności. Dla wszystkich nowych magazynów z włączoną opcją **Procesy zarządzania magazynem** metoda `allocateWave` będzie domyślnie uruchamiana równolegle.
- Na stronie **Parametry zarządzania magazynem** ustawienie **Przetwarzanie zapisuje wsadowe** ma wartość *Tak*, a ustawienie **Oczekiwanie na blokadę (ms)** ma wartość domyślną 15 sekund. Oznacza to, że wszystkie zadania wsadowe będą wykonywane w trybie wsadowym. Gdy jest uruchomiona grupa czynności, uzyskuje ona blokadę dla pozycji i wymiarów znajdujących się powyżej lokalizacji podczas wykonywania alokacji. Gdy inne zadanie przetwarzania fali próbuje uzyskać tę samą blokadę dla identycznego rekordu, jest ono blokowane do momentu zakończenia bieżącego procesu. Ustawienia **Oczekiwanie na blokadę (ms)** ustalają maksymalny czas, przez który system będzie oczekiwać na blokadę.

Równoległe przetwarzanie alokacji wymaga, aby przetwarzanie fali działało w trybie wsadowym. Dzięki temu wydajność przetwarzania grupy czynności zostanie wyłączona, jeśli wyłączone jest ustawienie **Proces zapisuje w partii**, zwłaszcza jeśli przetwarzanie grupy czynności korzysta z procesu równoległego zdefiniowanego w konfiguracji zadania dla odpowiednich metod grupy czynności.

W razie potrzeby możesz cofnąć wszystkie ustawienia wprowadzone domyślnie, gdy dla tego wystąpienia jest automatycznie włączona funkcja *Równoległości grupy czynności dla metody alokacji grupy czynności*. W tym celu:

- Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**. Na karcie **Przetwarzanie grupy czynności** zastosuj preferowane wartości dla **Przetwarzanie grup czynności w partii** i **Oczekiwanie na blokadę (ms)**.
- Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**. Wybierz metodę `allocateWave`. W okienku akcji wybierz opcję **Konfiguracja zadania**, aby otworzyć stronę, na której będzie znajduje się lista magazynów, na których ustawiono uruchamianie równoległe metody. Zmodyfikuj lub usuń liczbę zadań wsadowych oraz przypisaną grupę czynności dla każdego z wymienionych magazynów, w razie potrzeby.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="troubleshoot-using-the-infolog"></a>Rozwiązywanie problemów z korzystaniem z infologu

Ponieważ jest używana ta struktury przetwarzania wsadowego, błędy występujące podczas przetwarzania grupy czynności są przechwytywane w ramach dziennika informacyjnego zadań wsadowych. Aby odczytać zadania wsadowe związane z grupy czynności:

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz grupę czynności do inspekcji.
1. W okienku akcji otwórz kartę **Grupa czynności** i z grupy **Grupa czynności** wybierz pozycję **Zadania partii**.

Przetwarzanie grupy czynności jest samou korygujące, więc każdy błąd wykryty podczas przetwarzania powinien być zgłoszony za pomocą infologu.

Typowym błędem związanym z przetwarzaniem równoległym może być próba alokowania tego samego towaru w tym samym czasie przez dwie grupy czynności, a druga nie jest ukończona, przez co druga grupy czynności nie może uzyskać blokady w określonym czasie. W takiej sytuacji dziennik zadań wsadowych będzie zawierał informacje informujące, że nie można uzyskać blokady pozycji. W takim przypadku nieudaną grupy czynności należy przetworzyć ponownie.

Ponieważ przetwarzanie odbywa się równolegle, dane muszą być zachowywane w różnych tabelach, aby można było śledzić stan przetwarzania. Oznacza to, że dzienniki zadań wsadowych mogą zawierać błędy, takie jak błędy zduplikowanych kluczy.

Błędy z zadań wsadowych są również częścią dziennika zadań wsadowych. Najważniejsze informacje są zazwyczaj informacjami na dole.

W niektórych przypadkach, na przykład, jeśli połączenie SQL zostało zakończone, przetwarzanie grupy czynności może się zakończyć w niespójnym stanie, w którym zadanie przetwarzania wsadowego wygląda na uruchomione, ale zostało zatrzymane. Ta grupy czynności nie może obsłużyć tego błędu, więc próba oczyszczania nieudanych grupy czynności jest wykonywana po kolejnym przebiegu grupy czynności. Ewentualnie, jeśli bieżąca grupy czynności jest w stanie niespójnym, należy wykonać następujące kroki:

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz grupy czynności, które chcesz wyczyścić.
1. W okienku akcji otwórz kartę **Grupa czynności** i z grupy **Grupa czynności** wybierz pozycję **Czyszczenie danych grupy czynności**.

### <a name="troubleshoot-using-the-wave-progress-log"></a>Rozwiązywanie problemów z użyciem dziennika postępu grupy czynności

Jeśli opcja **Utwórz dziennik postępu grupy czynności** jest włączona na stronie **Parametry zarządzania magazynem**, wówczas rekord dziennika jest tworzony za każdym razem, gdy alokacja dla towaru zaczyna i kończy się. Ten dziennik należy włączyć tylko wtedy, gdy jest potrzebny, na przykład podczas testowania lub rozwiązywania problemów. Gdy ta opcja jest włączona, dziennik można wyświetlić, wykonać następujące kroki:

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz grupę czynności do inspekcji.
1. W okienku akcji na karcie **Grupa czynności** w grupie **Grupa czynności** wybierz opcję **proces**.
