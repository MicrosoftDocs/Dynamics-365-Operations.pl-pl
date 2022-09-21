---
title: Formant nagłówka pracownika
description: Ten artykuł zawiera informacje dotyczące formantu spersonalizowanego nagłówka w samoobsłudze pracowników etatowych, w centrum osób oraz na stronie Pracownik w Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2867a952df79161aaee657dbc3df1f3298294dd5
ms.sourcegitcommit: 167f73a834629752c6b79c312d744e52df7f0927
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2022
ms.locfileid: "9445952"
---
# <a name="worker-header-control"></a>Formant nagłówka pracownika

Microsoft Dynamics 365 Human Resources oferuje spersonalizowany formant nagłówka w **samoobsłudze pracowników etatowych**, w centrum **Osoby** oraz na uproszczonej stronie **Pracownik**. Nagłówek zawiera kluczowe informacje o pracowniku, a także pojedyncze akcje, takie jak wysyłanie wiadomości e-mail, rozmowy telefoniczne lub wiadomości. Nagłówek można zmodyfikować, usuwając pola lub dodając pola, w tym pola niestandardowe, w celu pokazania dodatkowych informacji. Aby użyć nowej kontrolki nagłówka, przejdź do **Zarządzania funkcją** i włącz funkcję **Formant nagłówka pracownika**.

## <a name="personalization"></a>Personalizacja

Jedną z najważniejszych zalet formantu nagłówka pracownika jest możliwość personalizowania informacji, które są wyświetlane w nagłówku.

W prawym górnym rogu nagłówka znajduje się grupa trzech pól, w których są wyświetlane różne dane, w zależności od stanu pracownika. Ta grupa pól jest określana jako część Polecane nagłówka. Część Polecane nagłówka można spersonalizować, usuwając bieżące lub dodając pola. Pola, które można dodać do części Polecane w formancie nagłówka, różnią się dla funkcji **Samoobsługi pracowników etatowych**,centrum **Osoby** i strony **Pracownik**.

## <a name="employee-self-service"></a>Samoobsługa pracownika etatowego

Nagłówek pracownika na stronie **Samoobsługa pracownika etatowego** zawiera następujące informacje:

- Imię i nazwisko pracownika
- Numer pracownika
- Tytuł stanowiska
- Działy
- Typ pracownika
- Osoba prawna zatrudnienia
- Lata pracy
- Przełożony (menadżer)
- Typ stanowiska

W nagłówku znajduje się także akcja o jednym kliknięciu, która ma na celu edycję informacji osobistych poszczególnych osób. Wybierz pozycję **Edytuj dane osobowe**, aby otworzyć stronę **Informacje osobiste** w **Samoobsłudze pracownika etatowego**.

## <a name="people-hub"></a>Centrum użytkowników

Nagłówek pracownika w centrum **Osoby** (strona **Obszar roboczy osób**) zawiera następujące informacje:

- Imię i nazwisko pracownika
- Numer pracownika
- Tytuł stanowiska
- Działy
- Typ pracownika
- Osoba prawna zatrudnienia
- Lata pracy
- Przełożony (menadżer)
- Typ stanowiska

Nagłówek zawiera również pojedyncze akcje, takie jak wysyłanie wiadomości e-mail, rozmowy telefoniczne lub wiadomości. Jeśli użytkownik przegląda własne informacje na stronie **obszaru roboczego Osoby**, sekcja akcji z jednym kliknięciem zawiera przycisk **Edytuj szczegóły osobiste**. Użytkownik może wybrać ten przycisk, aby otworzyć stronę **Informacje osobiste** w **Samoobsłudze pracownika etatowego**.

## <a name="streamlined-worker-page"></a>Uproszczona strona pracownika

Nagłówek pracownika na uproszczonej stronie **Pracownik** zawiera następujące informacje:

- Imię i nazwisko pracownika
- Numer pracownika
- Tytuł stanowiska
- Działy
- Typ pracownika
- Osoba prawna zatrudnienia

W zależności od stanu pracownika etatowego dane w nagłówku mogą się zmienić. Na przykład, jeśli pracownik etatowy nie pracuje już w firmie, formant nagłówka zawiera logo **Niezatrudniony**, datę zakończenia zatrudnienia i przyczynę zakończenia zatrudnienia.

W poniższej tabeli przedstawiono dane wyświetlane w nagłówku dla różnych stanów pracowników etatowych.

| Stan pracownika etatowego | Wyświetlane dane | Banknot |
|-----------------|--------------------|------|
| Oczekuje | <ul><li>Nazwisko</li><li>Numer pracownika</li><li>Tytuł stanowiska</li><li>Dział</li><li>Typ pracownika</li><li>Firma</li><li>Oczekująca karta identyfikacyjna</li><li>Data początkowa</li><li>Przełożony</li><li>Typ stanowiska</li></ul> | |
| Ostatnie zatrudnienie | <ul><li>Nazwisko</li><li>Numer pracownika</li><li>Tytuł stanowiska</li><li>Dział</li><li>Typ pracownika</li><li>Firma</li><li>Ostatnie zatrudnienie karty identyfikacyjnej</li><li>Lata pracy</li><li>Przełożony</li><li>Typ stanowiska</li></ul> | Domyślnie karta identyfikacyjna **Ostatnie zatrudnienie** jest wyświetlana dla pracowników etatowych, który byli zatrudnieni w ciągi ostatnich siedmiu dni. Aby zmienić to ustawienie, na stronie **Parametry zasobów ludzkich**, w zakładce **Ogólne**, w sekcji **Zakres dat ostatniego zatrudnienia** wpisz przedział czasowy. Na przykład, aby wyświetlić kartę identyfikacyjną **Ostatnio zatrudniony** dla pracowników etatowych, którzy byli zatrudnieni w ciągu ostatnich 14 dni, ustaw w polu **Okres** wartość **14**, a w polu **Jednostka** wartość **Dni**. |
| Aktywny pracownik etatowy | <ul><li>Nazwisko</li><li>Numer pracownika</li><li>Tytuł stanowiska</li><li>Dział</li><li>Typ pracownika</li><li>Firma</li><li>Data początkowa</li><li>Przełożony</li><li>Typ stanowiska</li></ul> | |
| Zamykanie | <ul><li>Nazwisko</li><li>Numer pracownika</li><li>Tytuł stanowiska</li><li>Dział</li><li>Typ pracownika</li><li>Firma</li><li>Karta identyfikacyjna na wypowiedzeniu</li><li>Lata pracy</li><li>Przełożony</li><li>Typ stanowiska</li></ul> | Domyślnie karta identyfikacyjna **Na wypowiedzeniu** jest wyświetlana dla pracowników etatowych, którzy przestaną pracować w ciągu następnych siedmiu dni. Aby zmienić to ustawienie, na stronie **Parametry zasobów ludzkich**, w zakładce **Ogólne**, w sekcji **Zakres dat pracownika na wypowiedzeniu** wpisz przedział czasowy. Na przykład, aby wyświetlić kartę identyfikacyjną **Na wypowiedzeniu** dla pracowników etatowych, którzy opuszczają pracę w ciągu ostatnich 14 dni, ustaw w polu **Okres** wartość **14**, a w polu **Jednostka** wartość **Dni**. |
| Odeszli | <ul><li>Karta identyfikacyjna niezatrudnionego</li><li>Numer pracownika</li><li>Data zakończenia zatrudnienia</li><li>Kod przyczyny</li></ul> | Domyślnie karta identyfikacyjna **Niezatrudniony** jest wyświetlana dla pracowników etatowych, którzy odeszli z pracy z ciągu siedmiu dni. Aby zmienić to ustawienie, na stronie **Parametry zasobów ludzkich**, w zakładce **Ogólne**, w sekcji **Zakres dat pracownika niezatrudnionego** wpisz przedział czasowy. Na przykład, aby wyświetlić kartę identyfikacyjną **Niezatrudniony** dla pracowników etatowych, którzy opuścili pracę w ciągu ostatnich 14 dni, ustaw w polu **Okres** wartość **14**, a w polu **Jednostka** wartość **Dni**. |
