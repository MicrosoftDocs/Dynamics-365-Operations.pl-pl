---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (9 kwietnia 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0a4d4de6cf28e24d1265395d6440df85edf71a0d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462288"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-9-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (9 kwietnia 2019)

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integracja lifecycle Services (LCS) z funkcją zgłaszania problemu
W Attract i Onboard problemy zarejestrowane przez użytkowników końcowych za pośrednictwem zgłaszania problemu teraz automatycznie tworzą problemy pomocy technicznej w projekcie LCS odbiorcy. Administratorzy mogą następnie sklasyfikować problemy i przesłać je do firmy Microsoft, w razie potrzeby. Jest to zgodne ze sposobem obsługi problemów użytkownika końcowego w Core HR.

### <a name="relevance-search"></a>Wyszukiwanie wg stopnia zgodności
W pulach umiejętności i kandydatów można teraz przeszukiwać całą bazę kandydatów pod kątem konkretnych kwalifikacji, nazwisk lub wykształcenia. Nie musisz już określać, którą część profilu kandydata chcesz przeszukać. Attract przeszukuje cały profil i podświetla wszystkie znalezione trafienia. Ponadto Attract przeszukuje wszystkie dostępne dokumenty na temat kandydata i inteligentnie ocenia wyniki wyszukiwania. Ponadto można filtrować wyniki według źródła lub czy są one srebrnymi medalistami. Aby uzyskać więcej informacji, zobacz [wyszukiwanie i wyświetlanie profili kandydatów](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-talent-pools#search-and-view-candidate-profiles).

### <a name="prospect-recommendations"></a>Rekomendacja prospektów
Attract pomoże uruchomić poszukiwanie kandydata na stanowisko, gdy tylko aktywujesz tę funkcję, podając inteligentne rekomendacje z bazy danych kandydatów Twojej organizacji. Zalecenia uwzględniają umiejętności i wykształcenie określone podczas wyszukiwania odpowiednich prospektów. Zalecenia te pojawiają się na karcie **prospektów** w obszarze stanowiska, jeśli ta funkcja zostanie włączona podczas procesu zatrudniania na stanowisko. Aby uzyskać więcej informacji, zobacz [Rekomendacje dotyczące prospektów](https://docs.microsoft.com/dynamics365/unified-operations/talent/intelligent-recommendations#prospect-recommendations).

### <a name="interviewer-availability-statuses"></a>Stan dostępności osoby przeprowadzającej rozmowę kwalifikacyjną
Osoby planujące rozmowy kwalifikacyjne będą mogły wkrótce wyświetlać stany **Poza biurem, pracuje w innym miejscu** osób przeprowadzających rozmowy kwalifikacyjne, co jest pomocne w planowaniu terminów rozmów z kandydatami.

### <a name="candidate-interview-experience-save-calendar-invites"></a>Rozmowa kwalifikacyjna z kandydatem: Zapisywanie zaproszeń w kalendarzu
Kandydaci mogą teraz pobrać i zapisać ich zdarzenia rozmowy kwalifikacyjnej w swoich kalendarzach za pomocą pliku .ics dołączonego do wiadomości e-mail z podsumowaniem rozmowy kwalifikacyjnej wysyłanej kandydatowi.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integracja lifecycle Services (LCS) z funkcją zgłaszania problemu
W Attract i Onboard problemy zarejestrowane przez użytkowników końcowych za pośrednictwem zgłaszania problemu teraz automatycznie tworzą problemy pomocy technicznej w projekcie LCS odbiorcy. Administratorzy mogą następnie sklasyfikować problemy i przesłać je do firmy Microsoft, w razie potrzeby. Jest to zgodne ze sposobem obsługi problemów użytkownika końcowego w Core HR.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
Zmiany opisane w tej części dotyczą kompilacji 8.1.2225.

### <a name="percent-of-basis-variable-plans-load-incorrect-amount"></a>Procent podstawowych zmiennych planów wczytuje nieprawidłową kwotę
Wersja z tego tygodnia zawiera poprawkę, która naprawia błąd wczytywania wynagrodzeń o zmiennej wysokości za pomocą procentu planów podstawowych.
 
### <a name="date-picker-on-last-day-worked-doesnt-work-correctly"></a>Wybór daty w ostatnim dniu pracy nie działa poprawnie
Ta zmiana rozwiązuje problem: Kiedy użytkownik edytuje **Datę zakończenia zatrudnienia** i wybiera datę przy użyciu formantu kalendarza, dzień zostanie dodany do zaznaczenia.

###  <a name="limit-personnel-action-types-by-the-action-taken"></a>Limitowanie typów akcji personelu na podstawie wykonywanych akcji
Ta zmiana ogranicza typy akcji, które pojawiają się podczas wykonywania określonej akcji. Na przykład, kiedy jest wymagane nowe stanowisko, tylko akcje nowego stanowiska pojawiają się na liście akcji do wyboru. Wcześniej były wyświetlane nowe akcje i edytowane. 

### <a name="transferring-an-employee-with-compensation-in-a-second-legal-entity"></a>Przenoszenia pracownika z wynagrodzeniem w drugiej firmie
Ta wersja umożliwia zakończenie wynagrodzenia w drugiej firmie, jeśli przeniesienie jest przeniesieniem między firmami.

### <a name="unable-to-select-compensation-for-a-future-employment-during-a-transfer"></a>Podczas przenoszenia nie można wybrać wynagrodzenia dla przyszłego zatrudnienia
Podczas przenoszenia pracownika do nowej firmy można teraz ustawić wynagrodzenie dla nowej firmy.

### <a name="user-isnt-able-to-assign-compensation-during-position-assignment"></a>Użytkownik nie może przypisać wynagrodzenia podczas przypisywania stanowiska.
Dodanie nowego przypisania stanowiska umożliwia teraz skonfigurowanie rekordów związanych ze stałym wynagrodzeniem. 

## <a name="in-preview"></a>Wersja próbna

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Zezwalaj na określanie kodów przyczyn dla typów urlopu
Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.
Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. Może to być spowodowane wymaganiami prawnymi lub polityką firmy. Teraz można określić typy urlopów wymagające podania kodu przyczyny i można wymagać, aby pracownicy podawali powód dla typu urlopu we wniosku.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich
Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny. Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldem. 

## <a name="coming-soon"></a>Wkrótce

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Ulepszona funkcja interfejsu użytkownika do sprawdzania zduplikowanych pracowników
Ta zmiana powoduje, że zduplikowane pozycje są wykrywane po wypełnieniu pól nazwisk, a stan pokazuje liczbę zduplikowanych pozycji. Można wybrać podane łącze, aby otworzyć nową stronę w celu dokonania oceny, czy ma być używane wykryte dopasowanie. Aby uniknąć zakłóceń we wprowadzaniu danych, formularz zduplikowanych pozycji nie jest automatycznie otwierany.

###  <a name="email-support-for-alerts"></a>Pomoc techniczna e-mail dla alertów
Aktualizacja platformy 25 dla Finance and Operations pozwala użytkownikom tworzyć reguły alertów, które automatycznie wysyłają powiadomienia do kontaktów w wyniku wyzwolenia przez zdarzenie. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]