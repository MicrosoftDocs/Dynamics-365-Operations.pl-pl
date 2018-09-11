--- 
title: Dystrybucja kwestionariuszy z wykorzystaniem harmonogramu
description: "Planowanie kwestionariuszy umożliwia planowanie i dystrybucję kwestionariuszy do wielu respondentów."
author: kherr75
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d371873cbd16f050ca042f5c13d93781fe6fc732
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="distribute-questionnaires-using-scheduling"></a>Dystrybucja kwestionariuszy z wykorzystaniem harmonogramu

[!include [task guide banner](../../includes/task-guide-banner.md)]

Planowanie kwestionariuszy umożliwia planowanie i dystrybucję kwestionariuszy do wielu respondentów. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-questionnaire-schedule"></a>Tworzenie harmonogramu kwestionariusza
1. Wybierz kolejno opcje Kwestionariusz > Rozdzielenie > Harmonogramy kwestionariuszy.
2. Kliknij przycisk Nowy.
3. W polu Planowanie wpisz wartość.
4. Wypełnij pole Opis.
    * Ustaw harmonogram na Anonimowy, jeśli odpowiedzi powinny zostać zarejestrowane bez imion i nazwisk skojarzonych z odpowiedzią.  
    * Najpierw w parametrach kadr należy skonfigurować zezwalanie na anonimowe wyniki.  
5. W polu Typ wybierz typ planowania.  W tym przykładzie użyjemy typu Zadowolenie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Data wprowadź datę.
9. Rozwiń sekcję Wiadomość e-mail samoobsługi pracownika etatowego.
10. W polu Temat wpisz wartość.
    * Przykład: Kwestionariusz dostępny  
11. W polu Tekst wprowadź treść swojej wiadomości e-mail. Uwaga: zmienna może służyć do zastępowania wartości w systemie.
    * Przykład:   Szanowny użytkowniku %P%, Zaloguj się w oknie Samoobsługa pracownika etatowego i wypełnij kwestionariusz zdrowotny pracownika.  Contoso  
12. Kliknij przycisk Zapisz.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>Używanie przycisku Szczegóły ustawień do wyboru kwestionariuszy, na które trzeba odpowiedzieć, i do wysyłania kwerend w celu wyboru respondentów.
1. Kliknij przycisk Szczegóły ustawień.
2. Na liście wybierz zapytanie, które ma posłużyć do znalezienia respondentów kwestionariusza w systemie.
    * Przykład: Pracownicy  
3. Kliknij przycisk Wyświetl lub zmodyfikuj kwerendę, aby wybrać określone osoby lub skorygować kwerendę, by znaleźć osoby pasujące do określonych kryteriów.
    * Pamiętaj, że wszyscy respondenci muszą być również użytkownikami w systemie.  
4. Na liście oznacz wiersz Osoba.
5. W polu Kryteria wprowadź lub wybierz wartość.
    * Wybierz osobę Julia Funderburk  
6. Na liście zaznacz osobę Julia Funderburk.
7. Kliknij przycisk OK.
8. Kliknij kartę Kwestionariusze.
9. W drzewie rozwiń węzeł typu kwestionariusza Ankieta o zadowoleniu.
10. W drzewie zaznacz pozycję „Ocena zdrowia pracowników”.
11. Kliknij przycisk OK.
12. Kliknij opcję Planowana sesja odpowiedzi.
    * Zwróć uwagę, że Planowana sesja odpowiedzi została utworzona dla każdego wybranego użytkownika lub użytkownika dla którego wysłano kwerendę.  
13. Zamknij stronę.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>Uruchamianie harmonogramu kwestionariusza w celu udostępnienia kwestionariusza respondentom do wypełnienia.
1. Kliknij przycisk Funkcje.
2. Kliknij przycisk Rozpocznij.
3. Kliknij przycisk OK.

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>Wysyłanie wiadomości e-mail w celu poinformowania respondentów o dostępnym kwestionariuszu.
1. Kliknij przycisk Funkcje.
2. Kliknij przycisk Wyślij wiadomość e-mail.
3. Kliknij przycisk Anuluj.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>Używanie Planowanej sesji odpowiedzi do sprawdzania, kto musi wypełnić kwestionariusz.
1. Kliknij opcję Planowana sesja odpowiedzi.
    * Usuń wszelkie pozostałe zaplanowane sesje odpowiedzi, aby zakończyć zaplanowaną sesję.  
2. Kliknij przycisk Usuń.
3. Kliknij przycisk Tak.
4. Zamknij stronę.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>Zakończ harmonogram, gdy wszyscy respondenci wypełnią kwestionariusz i/lub wszystkie pozostałe zaplanowane sesje odpowiedzi zostaną usunięte.
1. Kliknij przycisk Funkcje.
2. Kliknij opcję Koniec.
3. Kliknij przycisk OK.


