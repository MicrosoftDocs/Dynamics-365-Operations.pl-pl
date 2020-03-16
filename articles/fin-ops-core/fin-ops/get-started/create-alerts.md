---
title: Tworzenie reguł alertów
description: Ten temat zawiera informacje o alertach oraz wyjaśnia, jak utworzyć regułę alertu, dzięki czemu będziesz otrzymywać powiadomienia o zdarzeniach, takich jak nadejście określonego dnia lub wystąpienie konkretnej zmiany.
author: tjvass
manager: AnnBe
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: 85d4774bc710f0c48b384601e5505f11394cf5d5
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "3075931"
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

Jeśli na przykład konfigurujesz regułę alertu dla pola **Data rozpoczęcia**, właściwe są zdarzenia zależne od terminów. Z tego względu dla tego pola jest dostępny typ zdarzenia **należne w**. Jednak dla pola takiego jak **Centrum kosztu** zdarzenie zależne od terminu wykonania się nie nadaje. Z tego względu typ zdarzenia **należne w** nie jest dostępny. Zamiast tego jest dostępny typ zdarzenia **zmodyfikowano**.

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

Alerty mogą być wysyłane zewnętrznie za pomocą struktury zdarzeń biznesowych. Podczas tworzenia alertu ustaw **Dla całej organizacji** na **Nie** i ustaw **Wyślij zewnętrznie** na **Tak**. Po wyzwoleniu zdarzenia biznesowego przez alert, można wywołać przepływ wbudowany w Power Automate, korzystając z polecenia **w przypadku wystąpienia zdarzenia biznesowego** na łączniku Finance and Operations lub jawnie wysłać zdarzenie do punktu końcowego zdarzeń biznesowych za pośrednictwem katalogu **zdarzeń biznesowych**.

## <a name="create-an-alert-rule"></a>Tworzenie reguły alertu

0. Upewnij się, że zadania wsadowe alertów są uruchomione (patrz wyżej).
1. Otwórz stronę zawierającą dane do monitorowania.
2. W okienku akcji na karcie **Opcje** w grupie **Udostępnij** wybierz opcję **Utwórz regułę alertu**.
3. W oknie dialogowym **Utwórz regułę alertu** w polu **Pole** zaznacz pole do monitorowania.
4. W polu **Zdarzenie** wybierz typ zdarzenia.
5. Na skróconej karcie **Prześlij mi alert dla** wybierz żądaną opcję. Aby wysłać alert jako zdarzenie biznesowe, należy się upewnić, że **dla całej organizacji** jest ustawiona wartość **nie**.
6. Jeśli reguła alertu powinna się dezaktywować w określonym dniu, na skróconej karcie **Przesyłaj mi alerty do** zaznacz datę końcową.
7. Na skróconej karcie **Prześlij mi alert za pomocą** w polu **Temat** zaakceptuj domyślny nagłówek tematu wiadomości e-mail lub wprowadź nowy temat. Tekst używany jako nagłówek tematu dla e-maila ten będzie wyświetlany po wyzwoleniu alertu. Aby wysłać Alert jako zdarzenie biznesowe , należy przypisać opcję **Wyślij zewnętrznie** na **tak**.
8. W polu **Wiadomość** wprowadź opcjonalną wiadomość. Wprowadzony tekst jest komunikatem, jaki otrzymuje użytkownik po wyzwoleniu alertu.
9. Kliknij przycisk **OK**, aby zapisać ustawienia i utworzyć regułę alertu.
