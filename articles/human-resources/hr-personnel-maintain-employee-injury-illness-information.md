---
title: Obsługa informacji dotyczących urazów i chorób pracowników
description: To zadanie opisuje sposób tworzenia sprawy urazu lub choroby.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 36c25626bcc828a2d341d4ce4c9fe8fdcd4e6583
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688553"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Obsługa informacji dotyczących urazów i chorób pracowników


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Zaleca się najpierw wykonać przewodnik po zadaniach „Ustawienia urazów i chorób”, ponieważ część informacji konfiguracyjnych z niego jest używanych w tym miejscu. 



To nagranie zadania opisuje podstawowe kroki tworzenia przypadku urazu lub choroby. Oprócz szczegółów urazu lub choroby jest śledzony stan sprawy. Domyślnie sprawy mają stan **Otwarte**. Możesz zarządzać stanem, korzystając z pozycji menu **Stan sprawy** u góry strony.

1. Wybierz kolejno opcje **Zasoby ludzkie \> Pracownicy \> Uraz i choroba \> Przypadki urazów lub chorób**.
2. Wybierz pozycję **Nowy**.
3. W polu **Opis przypadku** wprowadź wartość (np. **Uraz nadgarstka**).
4. W **polu Pracownik** wprowadź lub wybierz wartość (na przykład **Ana Bowman**).
5. W polu **Data i godzina zdarzenia** wprowadź datę i czas (na przykład 20 stycznia 2016 godz. 10:00).
6. W polu **Typ urazu lub choroby** wpisz lub wybierz wartość (na przykład **Złamanie**).
7. W **polu Część ciała** wprowadź lub wybierz wartość (na przykład **Nadgarstek**).
8. W polu **Typ wyniku** wprowadź lub wybierz wartość (na przykład **Terapia**).
9. W polu **Data i godzina raportowania** wprowadź datę i godzinę.

    Zgłoszona data i godzina musi być późniejsza niż data i godzina zdarzenia.

10. W polu **Osoba, która zgłosiła sprawę** wprowadź lub wybierz wartość (na przykład, **Ana Bowman**).

    Wskazana osoba może być pracownikiem lub innym świadkiem zdarzenia.

11. W sekcji **Zdarzenie**, w polu **Miejsce zdarzenia**, wprowadź wartość (na przykład **Magazyn**).
12. W polu **W miejscu pracy** wybierz opcję **Tak**, jeśli zdarzenie wystąpiło w miejscu pracy.
13. W polu **Data i godzina rozpoczęcia pracy** wprowadź datę i czas, kiedy osoba, których dotyczy ta praca, rozpoczęła pracę przed zdarzeniem.
14. W polu **Zadanie lub zadanie** pracownika wprowadź zadanie lub zadanie, które pracownik wykonuje w czasie zdarzenia (na przykład **Ładowanie pól**). 
15. W polu **Przyczyna zdarzenia** wprowadź przyczynę zdarzenia (na przykład **Poślizgnął się na podłodze**).
16. W polu **Poziom ważności** wprowadź lub wybierz wartość.
17. W polu **Akcja do powzięcia** wprowadź wartość (na przykład **Natychmiast posprzątaj rozlane płyny**).
18. W polu **Oczekiwane dni nieobecności w pracy** wpisz liczbę dni, przez które dana osoba ma być nieobecna w pracy.

    Gdy osoba powróci do pracy, zaktualizuj pole **Dni na zwolnieniu** o rzeczywistą liczbę dni nieobecności danej osoby.

19. W sekcji **Koszty urazu lub choroby** wybierz **Dodaj**.
20. W polu **Data** wprowadź datę.
21. W polu **Typ kosztu** wprowadź lub wybierz wartość (na przykład **Terapia**).

    Możesz również wpisać kwotę i dołączyć do kosztu wszelkie dokumenty potwierdzające (np. faktury lub zaświadczenia lekarskie).

22. Wybierz opcję **Dodaj**.
23. W polu **Data** wprowadź datę.
24. W polu **Typ kosztu** wprowadź lub wybierz wartość (na przykład **Lekarz**).
25. W sekcji **Leczenie urazu lub choroby** wybierz **Dodaj**.
26. W polu **Data leczenia** wprowadź datę i godzinę.
27. W polu **Typ leczenia** wprowadź lub wybierz wartość (na przykład **Szyna unieruchamiająca**).
28. W sekcji **Pobyt w szpitalnym oddziale pomocy doraźnej w nagłych wypadkach** ustaw wartość **Tak**.
29. W polu **Komentarze na temat leczenia** wprowadź lub wybierz wartość (na przykład **Szyna unieruchamiająca przez 2 tygodnie**).
30. W polu **Imię lekarza** wprowadź wartość (na przykład **Dr. Anderson**).
31. W polu **Zakład i lokalizacja leczenia** wprowadź wartość (na przykład **Oddział ratunkowa ul. Elm**).
32. W polu **Szczegóły dotyczące leczenia** wprowadź wartość (na przykład **Prześwietlenie potwierdza złamanie, użycie szyny unieruchamiającej**).
33. Wybierz opcję **Zapisz**.

Stan sprawy można zaktualizować w dowolnym momencie. Jeśli trwa przetwarzanie urazu lub choroby, ustaw stan na **W trakcie**. Po zamknięciu incydentu możesz dodawać lub usuwać tylko koszty, zabiegi lub zgłoszenia, które są związane z incydentem. Aby zmienić inne informacje, musisz ponownie otworzyć sprawę.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
