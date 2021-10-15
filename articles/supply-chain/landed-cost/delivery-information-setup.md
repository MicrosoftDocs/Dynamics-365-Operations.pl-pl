---
title: Konfiguracja informacji o dostawie
description: W tym temacie opisano, jak skonfigurować informacje o dostawie dla modułu Koszt dostawy.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMPortTable, ITMLeadTimeTable, ITMLegTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 57f17d481f9660d67b96ac2c8e68558407b1bcf9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577607"
---
# <a name="delivery-information-setup"></a>Konfiguracja informacji o dostawie

[!include [banner](../../includes/banner.md)]

W tym temacie opisano, jak skonfigurować informacje o dostawie dla modułu **Koszt dostawy**.

## <a name="shipping-ports"></a>Porty wysyłki

Porty wysyłki identyfikują miejsce wysyłki towarów. Dla każdej podróży określane są port „do” i „od” na podstawie podróży wybranej dla środka transportu podróży. Porty wysyłkowe służą do budowy etapów podróży, a także działań związanych z podróżami. Są one zazwyczaj definiowane przy użyciu nazwy miasta i kraju lub regionu, w którym znajduje się fizyczny port wysyłki.

Aby pracować z portami wysyłki, przejdź do **Koszty dostawy \> Konfiguracja informacji o dostawie \> Porty wysyłkowe**. Można tam wyświetlać, dodawać i usuwać rekordy portów wysyłki. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Port wysyłki | Wprowadź unikalną nazwę/numer identyfikacyjny portu wysyłki. |
| opis | Wprowadź opis portu wysyłki. |

## <a name="tracking-control-center"></a><a name="tracking-control-center"></a>Centrum kontroli śledzenia

Centrum kontroli śledzenia służy do konfigurowania czasów realizacji, aktualizacji statusu i przepływu informacji związanych z podróżą, gdy kontenery transportowe przemieszczają się z jednego etapu do drugiego. Podczas tworzenia rekordu kontroli śledzenia jest on powiązany z określonym etapem podróży w ramach podróży. Gdy podróży aktualizuje etap, skojarzony rekord jest aktualizowany i wypełniany zgodnie z definicją. Informacje o śledzeniu dla pojedynczych podróży można aktualizować na stronie **Wszystkie podróże**.

Aby otworzyć centrum kontroli śledzenia, przejdź do **Koszt dostawy \> Konfiguracja informacji o dostawie \> Centrum kontroli śledzenia**.

Widok główny śledzenia zawiera jeden z trzech widoków strony, w zależności od wartości wybranej w polu **Utwórz typ** w okienku listy: *Puste*, *Czas realizacji* lub *Aktualizacja stanu*. Każdy typ tworzenia aktualizuje inny zestaw informacji skojarzonych z postępem podróży od punktu pochodzenia do miejsca docelowego.

### <a name="common-rule-settings"></a>Wspólne ustawienia reguł

W poniższej tabeli przedstawiono pola dostępne dla wszystkich trzech typów tworzenia w centrum kontroli śledzenia.

| Pole | opis |
|---|---|
| Tabela źródłowa, pole źródłowe | Pola te identyfikują tabelę źródłową i pole w bazie danych. Reguła załaduje wartość w polu, a następnie użyje jej w sposób zdefiniowany przez inne ustawienia reguły. |
| Tabela docelowa, pole docelowe | Te pola identyfikują tabelę docelową i pole w bazie danych. Reguła załaduje wartość w polu, a następnie użyje jej (lub nadpisze ją) w sposób zdefiniowany przez inne ustawienia reguły. |
| Działanie | To pole określa typ działania, które należy zastosować do kontenera wysyłkowego, do którego pasuje reguła. |
| Kryteria dopasowania | To pole określa sposób, w jaki system identyfikuje dopasowanie reguły. W każdym przypadku system przegląda dane w tabelach źródłowej i docelowej, aby określić, czy i kiedy należy zaktualizować pole w tabeli docelowej.<p>Na przykład tabela źródłowa to *Podróże*, a tabela docelowa to *Nagłówek zakupu* lub *Wiersze zakupu*. Tabela *Podróże* ma wartość **Z portu** *Hongkong*, a tabela *Nagłówka zakupu* ma wartość **Z portu** *Szanghaj*. Zostanie wówczas utworzona reguła mająca *Hongkong* jako wartość „z” portu. W takim przypadku wartości pola **Kryteria uzgadniania** działają w następujący sposób:</p><ul><li>**Oba** — pole docelowe nie zostanie zaktualizowane, ponieważ jeden z dwóch portów nie pasuje.</li><li>**Źródło** — pole docelowe zostanie zaktualizowane, ponieważ port „z” w tabeli źródłowej to *Hongkong*.</li><li>**Cel** — pole docelowe nie zostanie zaktualizowane, ponieważ port „z” w tabeli docelowej to *Szanghaj* (nie *Hongkong*).</li></ul> |
| Kopiuj akcję | Dostępne wartości to: *Kopiuj* i *Domyślne*. Wybierz pozycję *Kopiuj*, aby skopiować wartość z pola źródłowego do pola docelowego. Wybierz opcję *Domyślna*, aby ustawić wartość statyczną dla pola docelowego. |
| Domyślna | Jeśli w polu **Kopiuj akcję** jest ustawiona wartość *Domyślna*, pole **Domyślne** określa domyślną wartość pola docelowego. Jeśli na przykład akcja jest związana z aktualizacją portu, a pole **Kopiuj akcję** ma wartość *Domyślna*, pole **Domyślne** określa port. |
| Etap | To pole określa etap podróży, dla którego ma miejsce określone działanie, np. Załadunek lub odprawa celna. |
| Dostawca usługi | Jeśli do aktualnej aktualizacji statusu / etapu podróży wykorzystywany jest konkretny usługodawca, to pole identyfikuje usługodawcę. Dostawcy usług są zdefiniowani w koncie dostawcy. |

### <a name="lead-time-rules"></a>Zasady dotyczące czasu realizacji

Czas realizacji to szacowany czas potrzebny na podróż, aby ukończyć określony etap podróży w ramach podróży. Czas realizacji każdego etapu podróży jest używany do obliczenia szacowanej daty dostawy w podróży. Data ta jest następnie wprowadzana w polu **Potwierdzona data dostawy** w każdym wierszu zakupu w podróży.

Do zarządzania aktualizacjami dat są reguły czasu realizacji. Działania są generowane automatycznie w przypadku korzystania z szablonu podróży w ramach podróży.

Aby dodać regułę czasu realizacji do centrum kontroli śledzenia, wykonaj następujące kroki.

1. Wykonaj jeden z następujących kroków:

    - Przejdź do ustawień **Koszty z wyładunkiem \> Ustawienia podróży wieloetapowej \> Etapy**. Wybierz nogę, dla której chcesz ustawić czasy realizacji, a następnie w okienku akcji wybierz pozycję **Centrum kontroli śledzenia**. Centrum kontroli śledzenia jest wstępnie załadowane informacjami o wybranym etapie.
    - Przejdź do **Koszt z wyładunkiem \> Konfiguracja informacji o dostawie \> Centrum kontroli śledzenia**. Następnie należy ręcznie wybrać etap w kroku 4 tej procedury.

1. W okienku listy w polu **Utwórz typ** ustaw wartość *Czas realizacji*.
1. W okienku akcji wybierz opcję **Nowy**.
1. Jeśli zaczynasz od centrum kontroli śledzenia w kroku 1, w polu **Etap** ustaw etap, dla którego chcesz utworzyć regułę czasu realizacji. Jeśli rozpoczęto od strony **Etapy**, pole **Etap** jest wstępnie ustawione na nodze wybranej przed otwarciem centrum kontroli śledzenia.

    Na podstawie wartości pola **Etap** kilka pól jest ustawianych automatycznie, jak pokazano poniżej:

    - **Tabela źródłowa:** *Działania kontenera*
    - **Pole źródłowe:** *Data rozpoczęcia*
    - **Tabela docelowa:** *Działania kontenera*
    - **Pole docelowe:** *Szacowana data zakończenia*

1. W polu **Działanie** wybierz działanie, do których ma być zastosowanie bieżąca reguła.
1. W polu **Czas realizacji** wprowadź czas realizacji (w dniach), który ma zostać zastosowany w przypadku wyzwolenia bieżącej reguły.

### <a name="status-update-rules"></a>Zasady aktualizacji statusu

Rekordy, dla których w polu **Typ tworzenia** ustawiono wartość *Aktualizacja stanu*, spowoduje zaktualizowanie stanu wierszy zamówienia zakupu lub stanu na poziomie podróży, kontenera wysyłkowego lub folio. Stany można ustawiać niezależnie. Funkcji tych można użyć w celu poinformowania użytkownika lub działu o etapie podróży (takim jak odebrane dokumenty lub towary w drodze).

Jeśli w polu **Utwórz typ** jest ustawiona wartość *Aktualizacja stanu*, centrum kontroli śledzenia zawiera skróconą kartę **Wiersze**, na której można zdefiniować obszar kosztów oraz zaktualizowany stan podróży. Na przykład w wierszu w polu **Obszar kosztów** ustawiono wartość *Kontener*, a w polu **Stan podróży** są ustawiane *Towary w drodze*. W takim przypadku, gdy zamówienie zakończy określony etap, pole **Stan podróży** kontenera wysyłkowego zostanie zaktualizowane do wartości *Towary w drodze*.

Aktualizacje stanu zapewniają stan podróży w wierszach podróży i wierszach zamówienia zakupu skojarzonych z tą podróży. Gdy podróż przenosi się z portu do magazynu docelowego, pole **Stan podróży** rekordu podróży umożliwia szybkie przeglądanie etapu, na jakim znajdują się towary.

Aby dodać regułę aktualizacji stanu do centrum kontroli śledzenia, wykonaj następujące kroki.

1. Wykonaj jeden z następujących kroków:

    - Przejdź do ustawień **Koszty z wyładunkiem \> Ustawienia podróży wieloetapowej \> Etapy**. Wybierz nogę, dla której chcesz ustawić aktualizację stanu, a następnie w okienku akcji wybierz pozycję **Centrum kontroli śledzenia**. Centrum kontroli śledzenia jest wstępnie załadowane informacjami o wybranym etapie.
    - Przejdź do **Koszt z wyładunkiem \> Konfiguracja informacji o dostawie \> Centrum kontroli śledzenia**. Następnie należy ręcznie wybrać etap w kroku 4 tej procedury.

1. W okienku listy w polu **Utwórz typ** ustaw wartość *Aktualizacja stanu*.
1. W okienku akcji wybierz opcję **Nowy**.
1. Jeśli zaczynasz od centrum kontroli śledzenia w kroku 1, w polu **Etap** ustaw etap, dla którego chcesz utworzyć regułę aktualizacji stanu. Jeśli rozpoczęto od strony **Etapy**, pole **Etap** jest wstępnie ustawione na nodze wybranej przed otwarciem centrum kontroli śledzenia.

    Na podstawie wartości pola **Etap** kilka pól jest ustawianych automatycznie, jak pokazano poniżej:

    - **Tabela źródłowa:** *Działania kontenera*
    - **Pole źródłowe:** *Rzeczywista data zakończenia*
    - **Tabela docelowa:** To pole pozostaje puste.
    - **Pole docelowe:** To pole pozostaje puste.

1. W polu **Działanie** wybierz działanie, do których ma być zastosowanie reguła.
1. Na skróconej karcie **Wiersze** wprowadź aktualizacje stanu dla każdego obszaru kosztów.

### <a name="blank-type-rules"></a>Reguły typu pustego

Rekordy o wartości **Utwórz typ** mają wartość *Puste*, aby zastąpić lub wprowadzić wartość pola na podstawie danych innego pola. Pole z systemu Koszty z wyładunkiem zastąpi dane w innych obszarach rozwiązania Microsoft Dynamics 365 Supply Chain Management, zgodnie z regułami ustawionymi w Centrum kontroli śledzenia.

1. Przejdź do **Koszt z wyładunkiem \> Konfiguracja informacji o dostawie \> Centrum kontroli śledzenia**.
1. W okienku listy w polu **Utwórz typ** ustaw wartość *Puste*.
1. W okienku akcji wybierz opcję **Nowy**.
1. Zdefiniuj wartości źródłowe i docelowe, kryteria dopasowania, czynność kopiowania i inne istotne parametry zgodnie z wymaganiami reguły.

### <a name="required-tracking-control-setup"></a>Wymagana konfiguracja kontroli śledzenia

Dla każdego szablonu podróży należy ustawić dwa rekordy w centrum kontroli śledzenia. Oba rekordy mają wartość **Utwórz typ** o wartości *Puste* i są używane we wszystkich implementacjach kosztów z wyładunkiem. Pomagają one zapewnić, że potwierdzona data zakupu i oczekiwane daty towarów w tranzycie są aktualizowane w przypadku podróży i powiązanych linii zamówienia w oczekiwany sposób.

Pierwszy rekord jest wymagany do zaktualizowania wierszy zakupu. Musi mieć następujące ustawienia:

- **Tabela źródłowa:** *Działania kontenera*
- **Pole źródłowe:** *Szacowana data zakończenia*
- **Tabela docelowa:** *Wiersze zakupu*
- **Pole docelowe:** *Potwierdzone lub data dostawy*

Drugi rekord jest wymagany do aktualizacji towarów w drodze. Musi mieć następujące ustawienia:

- **Tabela źródłowa:** *Działania kontenera*
- **Pole źródłowe:** *Szacowana data zakończenia*
- **Tabela docelowa:** *Zamówienie na towary w drodze*
- **Pole docelowe:** *Oczekiwana data*
