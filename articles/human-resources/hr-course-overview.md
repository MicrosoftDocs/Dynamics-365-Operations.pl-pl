---
title: Omówienie kursów
description: Ten artykuł wyjaśnia, jak administratorzy rozwiązania Human Resources i menedżerowie mogą korzystać z funkcji kursów do obsługi informacji o kursach są udostępnione pracownikom.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a1fd00fb9feea9ab426f67095770389696452215
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2022
ms.locfileid: "9716341"
---
# <a name="courses-overview"></a>Omówienie kursów

Microsoft Dynamics 365 Human Resources dostarcza rozwiązanie dla potrzeb w zakresie kształcenia w organizacji. To rozwiązanie oferuje dwie ścieżki kursu szkoleniowego: *wirtualną* i *instruktorską*.

*Uczenie wirtualne* to możliwości kształcenia rozszerzone za pośrednictwem zasobów online. Podczas *szkolenia prowadzonego przez instruktora* instruktor ułatwia sesje szkoleniowe dla grupy pracowników lub uczniów.

W module Szkolenia pracownicy modułu Human Resources, administratorzy, menedżerowie szkoleń i kierownicy mogą tworzyć ścieżki kształcenia i przypisywać je do pracowników.

> [!NOTE]
> Aby korzystać z kursów wirtualnych, należy ją włączyć w Zarządzanie funkcjami funkcję **Ulepszenia kursu**.

## <a name="set-up-virtual-courses"></a>Ustawianie kursów wirtualnych

Aby skonfigurować kursy wirtualne, należy ją włączyć w Zarządzanie funkcjami funkcję **Ulepszenia kursu**. Przejdź do opcji **Kursy \> Nowy** i ustaw opcję **Wirtualne** na **Tak**. Po włączeniu tej funkcji wymagane jest łącze do kursu. Pole **Stan kursu** potrącenia będzie ustawione na **Otwarte**. Opcja **Zezwalaj na samodzielną rejestrację pracownika etatowego** jest ustawiona na **Tak**, ale można ustawić wartość na **Nie**.

Po włączeniu funkcji **Ulepszeń kursowych** w zarządzaniu funkcjami zachodzą następujące zmiany:

- Dla przypisania kursu musi być określona data realizacji.
- Łącze kursu jest wymagane.
- **Samoobsługa pracownika etatowego** spowoduje pokazanie przeglądu pracowników etatowych w **Kursach**. Użytkownik może wyświetlić kursy, które są przeterminowane, wkrótce będą i przypisane.
- Pracownicy mogą ukończyć kursy wirtualne i samodzielnie je atestować.

## <a name="set-up-instructor-led-courses"></a>Ustaw kursy prowadzone przez instruktorów

Kursy prowadzone przez instruktorów nie muszą być skonfigurowane przed ich rozpoczęciem.

Następujące informacje to opcjonalne informacje, które można określić dla kursów. Jeśli te informacje zostaną wprowadzone dla kursów, należy je skonfigurować przed ich utworzeniem:

- Typ kursu
- Grupy klas
- Grupy kursów
- Lokalizacje kursu
- Klasy
- Instruktorzy
- Typy kursów

*Typy kursów* służą do klasyfikowania kursów według ich struktury lub zawartości. Typy kursów można tworzyć na stronie  **Typy kursów**.

Minimalną i maksymalną liczbę uczestników, jaką można zarejestrować na kurs, określa się na skróconej karcie  **Ogólne** na stronie  **Kursy**.

### <a name="course-setup-type"></a>Rodzaj ustawień kursu 

*Typy ustawień* określają struktury kursu. Istnieją trzy typy ustawień kursów.

| Typ konfiguracji | Opis |
|------|--------|
| Standardowo | Kursy tego typu ustawień nie mają dziennego terminarzu. Jest to domyślny typ ustawień przy tworzeniu nowego kursu. |
| Terminarz | Wybierz ten typ ustawienia, aby zaplanować szczegóły każdego dnia kursu, który odbywa się przez kilka dni. |
| Terminarz + sesja | <p>Wybierz ten ustawienia typ dla bardziej złożonych kursów. Na przykład można podzielić terminarz kursu na *ścieżki* i *sesje*.</p><ul><li>*Ścieżki* to określone dziedziny dla kursu.</li><li>*Sesje* — rozdzielają ścieżki i pomagają w określeniu procesów i technik, które są związane z każdą ścieżką.</li></ul> |

### <a name="course-tasks"></a>Zadania kursu

Dla każdego kursu wykonaj następujące zadania:

- Rejestracja uczestników.
- Określenie ostatecznego terminu rejestracji.
- Określić minimalną i maksymalną liczbę uczestników.
- Przypisz lokalizację i klasę dla kursu.
- Hotele rekomendowane uczestnikom kursu.
- Utworzenie opisu kursu, który później może zostać opublikowany w module  **Samoobsługa pracownika etatowego**.

> [!NOTE]
> Kurs można usunąć tylko wtedy, gdy nikt się na niego nie zarejestrował.

### <a name="course-statuses"></a>Stany kursu

W poniższej tabeli wymieniono stany poszczególnych operacji.

| Stan | Akcje |
|------|--------|
| Utworzony | <ul><li>Wprowadzanie i modyfikowanie informacji o kursie.</li><li>Zmienianie stanu kursu na  **Otwarty**, dzięki czemu pracownicy mogą rejestrować się na kursie.</li></ul> | 
| Otwórz | <ul><li>Rejestrowanie uczestników kursu.</li><li>Usuwanie uczestników z kursu.</li><li>Zatwierdzanie uczestników kursu.</li><li>Zmiana stanu kursu na  **Zamknięty** lub  **Anulowany** dla uczestników, których stanem jest **Potwierdzony**.</li></ul>|
| Zamknięty | Kurs można otworzyć ponownie. |
| Anulowany | Kurs można otworzyć ponownie. |

### <a name="course-participants"></a>Uczestnicy kursu

*Uczestnikami kursu* są pracownicy, którzy biorą udział w kursie lub wydarzeniu. Można zarejestrować uczestników tylko na kursach otwartych.

### <a name="workflow"></a>Przepływ pracy

Rejestracje pracowników, którzy zapisali się na kurs poprzez stronę  **Samoobsługa pracownika etatowego**, mogą zostać przekierowane przez przepływ pracy celem zatwierdzenia. Możesz przypisać przepływ pracy do kursu na skróconej karcie  **Ogólne** na stronie  **Kursy**.
