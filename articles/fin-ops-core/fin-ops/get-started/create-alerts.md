---
title: Tworzenie reguł alertów
description: Ten artykuł zawiera informacje dotyczące alertów i informacje dotyczące sposobu tworzenia reguły alertu.
author: RichdiMSFT
ms.date: 10/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: a420c5b2a036ac63a1a179f93462d152c3941fda
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124233"
---
# <a name="create-alert-rules"></a>Tworzenie reguł alertów

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a>Rozpoczęcie pracy

Przed utworzeniem reguły alertu musisz zdecydować, kiedy i w jakich sytuacjach chcesz otrzymywać alerty. Gdy już wiesz, o którym zdarzeniu chcesz otrzymywać powiadomienia, odszukaj stronę, na której pojawiają się dane wywołujące zdarzenie. Zdarzeniem może być nadejście określonego dnia lub wystąpienie konkretnej zmiany. W związku z tym należy odnaleźć stronę, gdzie jest podana data, znajduje się modyfikowane pole lub widać nowo tworzony rekord. Mając te informacje, można utworzyć regułę alertu.

Podczas tworzenia reguły alertu określasz kryteria, które muszą został spełnione, aby został wywołany alert. Kryteria mogą obejmować występowanie zdarzenia oraz spełnienie określonych warunków. Jeżeli dojdzie do zdarzenia, system rozpocznie kontrole zgodnie z określonymi warunkami.

## <a name="ensure-the-alert-batch-jobs-are-running"></a>Upewnij się, że zadania wsadowe alertów są uruchomione

Zadania wsadowe dla alertów dotyczących zmian danych i terminów muszą być uruchomione, aby można było przetworzyć warunki alertów i wysyłać powiadomienia. Aby uruchomić zadania wsadowe, należy przejść do obszaru **administrowanie systemem** > **zadania okresowe** > **Alerty** i dodać nowe zadanie wsadowe dla **alertów na podstawie zmian** i/lub **alertów dotyczących terminów**. Jeśli potrzebne jest bardzo długie i często wykonywane zadanie wsadowe, należy wybrać opcję **cykl** i ustawić **brak daty zakończenia** ze **wzorcem cyklu** w **minutach** i **liczbą** **1**.

## <a name="events"></a>Zdarzenia

Zdarzeniem wyzwalającym regułę alertu może być nadejście określonego dnia lub wystąpienie konkretnej zmiany. Wyzwalacze zdarzeń definiuje się na skróconej karcie **Prześlij mi alert, gdy** w oknie dialogowym **Utwórz regułę alertu**. Dostępność zdarzeń dla konkretnych pól jest uzależniona od wybranego wyzwalacza.

Jeśli na przykład konfigurujesz regułę alertu dla pola **Data rozpoczęcia**, właściwe są zdarzenia zależne od terminów. Z tego względu dla tego pola jest dostępny typ zdarzenia `is due in`. Jednak dla pola takiego jak **Centrum kosztu** zdarzenie zależne od terminu wykonania się nie nadaje. Z tego względu typ zdarzenia `is due in` nie jest dostępny. Zamiast tego jest dostępny typ zdarzenia `has changed`.

## <a name="event-types"></a>Typy zdarzeń

Mogą wystąpić trzy typy zdarzeń:

- **Zdarzenia typu tworzenie i usuwanie** — te zdarzenia wyzwalają alert w momencie utworzenia lub usunięcia rekordu.
- **Zdarzenia typu aktualizacja** — te zdarzenia wyzwalają alert, gdy zmienią się dane w określonym polu.
- **Zdarzenia typu termin** — te zdarzenia wywołują alert, gdy nadejdzie określony dzień.
    
Zachodzące zmiany mogą być inicjowane przez użytkownika. Na przykład użytkownik zmienia datę dostawy dla zamówienia zakupu. Alternatywnie zmiany mogą następować w ramach procesu. Na przykład pole **Stan** na stronie zmienia wartość zgodnie z cyklem życia różnych procesów w systemie.

## <a name="conditions"></a>Warunki

Na skróconej karcie **Prześlij mi alert dla** w oknie dialogowym **Utwórz regułę alertu** można używać warunków do kontrolowania, kiedy otrzymujesz alerty o zdarzeniach.

Na przykład można określić, że system ma wysyłać alert po zmianie stanu zamówienia, ale tylko wtedy, gdy stan jest zgodny z określonym zbiorem warunków. Dokładnie rzecz biorąc chcesz otrzymywać alerty, gdy stan zamówienia zakupu zmieni się na **Otrzymane**. Ta zmiana stanu jest zdarzeniem wyzwalającym alert.

Następnie musisz zdecydować, o których zamówieniach zakupu chcesz otrzymywać alerty. Na przykład można wybrać jedną z następujących opcji. Te opcje określają warunki dla reguły alertu.

- **Aktualnie wybrany rekord** — będziesz otrzymywać alert, gdy stan określonego zamówienia zakupu zmieni się na **Otrzymane**.
- **Wszystkie rekordy** — będziesz otrzymywać alert po zmianie stanu zamówienia zakupu dla towaru w aktywnym widoku strony. Można użyć funkcji zaawansowanego filtrowania, która jest dostępna na stronie, aby utworzyć reguły dla określonego zbioru rekordów. Na przykład można utworzyć alert, który będzie wywoływany dla wszystkich zamówień zakupu od odbiorców w określonej grupie odbiorców.
    
## <a name="expiry-of-rule"></a>Wygaśnięcie reguły

Na skróconej karcie **Przesyłaj mi alerty do** w oknie dialogowym **Utwórz regułę alertu** można określić, jak długo reguła alertu powinna być aktywna.

## <a name="alert-contents"></a>Zawartość alertu

Na skróconej karcie **Prześlij mi alert za pomocą** w oknie dialogowym **Utwórz regułę alertu** można określić tekst tematu i treść wiadomości, które mają być używane w komunikatach alarmowych.

## <a name="user-id"></a>Identyfikator użytkownika

Na skróconej karcie **Prześlij mi alert za pomocą** w oknie dialogowym **Utwórz regułę alertu** można określić, który użytkownik powinien otrzymywać komunikaty alarmowe. Domyślnie jest zaznaczony Twój identyfikator użytkownika. Możliwość zmiany użytkownika otrzymującego alert jest ograniczona tylko do administratorów organizacji.

## <a name="alerts-as-business-events"></a>Alerty jako zdarzenia biznesowe

Możesz wysyłać alerty zewnętrznie za pomocą struktury zdarzeń biznesowych. Podczas tworzenia alertu ustaw **Dla całej organizacji** na **Nie** i ustaw **Wyślij zewnętrznie** na **Tak**. Po wyzwoleniu zdarzenia biznesowego przez alert można wywołać przepływ wbudowany w usłudze Power Automate, korzystając z wyzwalacza **W przypadku wystąpienia zdarzenia biznesowego** w łączniku aplikacji finansowych i operacyjnych, lub jawnie wysłać zdarzenie do punktu końcowego zdarzeń biznesowych za pośrednictwem **katalogu zdarzeń biznesowych**.

## <a name="create-an-alert-rule"></a>Tworzenie reguły alertu

0. Upewnij się, że zadania wsadowe alertów są uruchomione (patrz wyżej).
1. Otwórz stronę zawierającą dane do monitorowania.
2. W okienku akcji na karcie **Opcje** w grupie **Udostępnij** wybierz opcję **Utwórz regułę alertu**.
3. W oknie dialogowym **Utwórz regułę alertu** w polu **Pole** zaznacz pole do monitorowania.
4. W polu **Zdarzenie** wybierz typ zdarzenia.
5. Na skróconej karcie **Prześlij mi alert dla** wybierz żądaną opcję. Aby wysłać alert jako zdarzenie biznesowe, ustaw wartość opcji **Dla całej organizacji** na **Nie**.
6. Jeśli reguła alertu powinna się dezaktywować w określonym dniu, na skróconej karcie **Przesyłaj mi alerty do** zaznacz datę końcową.
7. Na skróconej karcie **Prześlij mi alert za pomocą** w polu **Temat** zaakceptuj domyślny nagłówek tematu wiadomości e-mail lub wprowadź nowy temat. Tekst stanie się nagłówkiem tematu wiadomości e-mail po wyzwoleniu alertu. Aby wysłać Alert jako zdarzenie biznesowe , należy przypisać opcję **Wyślij zewnętrznie** na **tak**.
8. W polu **Wiadomość** wprowadź opcjonalną wiadomość. Wprowadzony tekst staje się wiadomością, jaką otrzymuje użytkownik po wyzwoleniu alertu.
9. Kliknij przycisk **OK**, aby zapisać ustawienia i utworzyć regułę alertu.

## <a name="limitations-and-workarounds"></a>Ograniczenia i rozwiązania

### <a name="workaround-for-creating-alerts-for-the-secondary-data-sources-of-a-form"></a>Rozwiązanie problemu dotyczącego tworzenia alertów dla pomocniczych źródeł danych w formularzu
Nie możesz tworzyć alertów dla niektórych dodatkowych źródeł danych w formularzach. Na przykład podczas tworzenia alertów w formularzu profile księgowania odbiorcy lub dostawcy dostępne są tylko pola w nagłówku (CustLedger lub VendLedger), a nie kont wymiaru. Obejście tego ograniczenia polega na użyciu parametru **SysTableBrowser** w celu otwarcia tej tabeli jako podstawowego źródła danych. 
1. Otwórz tabelę w formularzu **SysTableBrowser**.
    ```
        https://<EnvironmentURL>/?cmp=USMF&mi=SysTableBrowser&TableName=<TableName>
    ```
2. Utwórz alert z formularza SysTableBrowser.

### <a name="change-based-alerts-do-not-work-for-batch-status-changes"></a>Alerty na podstawie zmian nie działają w związku ze zmianami stanu zadania wsadowego
Alerty oparte na zmianach nie działają ze zmianami stanu partii, ponieważ są wyłączone ze względu na wydajność. Zamiast tego należy skonfigurować funkcję **Alertów przetwarzania wsadowego**. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie alertów dla rozszerzonych formularzy przetwarzania wsadowego](../../dev-itpro/sysadmin/alerts.md#set-up-alerts-for-batch-enhanced-forms).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
