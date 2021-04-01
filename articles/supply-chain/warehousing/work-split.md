---
title: Podział pracy
description: Ten temat zawiera informacje dotyczące funkcji podziału pracy. Ta funkcja umożliwia dzielenie dużych zleceń roboczych na kilka mniejszych zleceń produkcyjnych, które można następnie przypisać do wielu pracowników magazynu. Dzięki temu ta sama praca może być pobierana jednocześnie przez kilku pracowników magazynu.
author: mirzaab
manager: tfehr
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6dbf0f6dd0c691db74eaad2174d8f9849b4cb26a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245089"
---
# <a name="work-split"></a>Podział pracy

Funkcja podziału pracy umożliwia dzielenie identyfikatorów dużych zleceń roboczych (czyli zleceń pracy, które mają kilka wierszy) na kilka mniejszych identyfikatorów zleceń produkcyjnych, które można następnie przypisać do wielu pracowników magazynu. Dzięki temu numer utworzenia tej samej pracy może być pobierany jednocześnie przez kilku pracowników magazynu.

> [!IMPORTANT]
> Można dzielić tylko zlecenia pracy, które mają stan *Otwarte* lub *W toku*.

## <a name="turn-on-the-work-split-functionality"></a>Włącz funkcję podziału pracy

Aby można było korzystać z funkcji podziału pracy, należy włączyć tę funkcję i jej funkcję wstępnie wymaganą w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć je, jeśli istnieje taka potrzeba.

Najpierw włącz wstępnie wymaganą funkcję *Blokowania pracy w całej organizacji*, jeśli nie została jeszcze włączona. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Blokowanie pracy w całej organizacji*

> [!NOTE]
> Po uaktywnieniu tej funkcji uaktualnienie danych jest automatycznie stosowane po włączeniu funkcji we wszystkich osobach prawnych.

Następnie włącz funkcję *Podziału pracy*, która jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Podział pracy*

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a>Ulepszenia szczegółów pracy i wszystkich stron pracy

Funkcja *Podziału pracy* powoduje dodanie poniższych dwóch przycisków do karty **Praca** w okienku akcji na stronach **Szczegóły pracy** i **Cała praca**:

- **Podział pracy** — dzielenie bieżącej pracy o podanym identyfikatorze na wiele mniejszych prac, które mogą być wykonywane przez różnych pracowników.
- **Anuluj sesję podziału pracy** — umożliwia anulowanie sesji podziału pracy i udostępnienie pracy do przetwarzania.

![Przyciski sesji podziału pracy i anulowania podziału pracy](media/Work_split_buttons.png "Przyciski sesji podziału pracy i anulowania podziału pracy")

> [!IMPORTANT]
> Przycisk **Podziału pracy** nie jest dostępny, jeśli spełniony jest dowolny z następujących warunków:
>
> - Stan pracy to coś innego niż *Otwarte* lub *W toku*.
> - Identyfikator kontenera jest skojarzony z identyfikatorem pracy. (Kontener nie może być podzielony systematycznie, ponieważ wymaga fizycznego działania.)
> - Praca jest skojarzona z klastrem.
> - Typ zlecenia produkcyjnego ma wartość inną niż jeden z następujących typów:
>
>    - Zamówienia sprzedaży
>    - Pobranie surowca
>    - Wydanie przeniesienia
>
> - Obecnie praca jest dzielona przez innego użytkownika. W przypadku próby otwarcia strony podziału dla pracy, która jest już podzielona przez innego użytkownika, pojawia się następujący komunikat o błędzie: „Praca o identyfikatorze \#\#\#\# jest obecnie dzielona. Spróbuj ponownie za kilka minut. Jeśli ten komunikat będzie nadal wyświetlany, skontaktuj się z kierownikiem”.

Nowa przyczyna blokowania pracy — *Podział pracy* wskazuje, kiedy identyfikator pracy jest w trakcie dzielenia. Jest ona wyświetlana zarówno na stronie **Podziału pracy**, jak i w aplikacji magazynu, jeśli użytkownik podejmie próbę uruchomienia pracy. Jeśli są używane przyczyny blokowania, nazwa pola **Zablokowanej grupy czynności** w identyfikatorze pracy zostaje zmieniona na **Zablokowane**.

## <a name="initiate-a-work-split"></a>Inicjowanie podziału pracy

Ta funkcja dodaje nową stronę **Podziału pracy**, która umożliwia użytkownikom podzielenie wierszy pracy od identyfikatora pracy. Po pierwszym otwarciu strony wyświetlane są wiersze o stanie pracy *Otwarte* i dostępne do podziału. W okienku akcji wybierz opcję **Podziel pracę**, aby przetworzyć wybraną pracę.

Aby podzielić pracę, wykonaj następujące kroki.

1. Otwórz jedną z następujących stron pracy:

    - **Szczegóły pracy** (**Zarządzanie magazynem \> Praca \> Szczegóły pracy**)
    - **Cała praca** (**Zarządzanie magazynem \> Praca \> Cała praca**)

1. W siatce wybierz identyfikator pracy, który ma zostać podzielony. Dla pola **Typ zlecenia produkcyjnego** należy określić jedną z następujących wartości:

    - Zamówienia sprzedaży
    - Pobranie surowca
    - Wydanie przeniesienia

1. W okienku akcji, na karcie **Praca**, w grupie **Praca** wybierz pozycję **Podział pracy**.

    Zostanie wyświetlona strona **Podział pracy** zawierająca wiersze pracy, które są otwarte i dostępne do podziału. Domyślnie wyświetlane są tylko dostępne wiersze pracy. Aby wyświetlić wszystkie wiersze dla identyfikatora pracy (na przykład wiersze z typem pracy *Odłóż*), zaznacz pole wyboru **Pokaż wszystkie wiersze** nad siatką.

    Pokazany jest następujący komunikat: „Użytkownicy nie mogą przetwarzać wierszy pracy, dopóki nie skończysz dzielenia i zamknięcia tej strony”.

    W polu **Przyczyna blokady pracy** dla bieżącej pracy zostanie ustawiona wartość *Podział pracy*, a praca zostanie zablokowana.

    ![Przyczyna blokowania](media/Blocking_reason.png "Przyczyna blokowania")

1. Wybierz wiersze, które mają zostać usunięte z bieżącego identyfikatora pracy i dodane do nowego identyfikatora pracy. Występują wówczas następujące zdarzenia:

    - Po podzieleniu pracy wybrane wiersze lub wiersze z oryginalnego identyfikatora pracy zostaną anulowane, a następnie skopiowane do nowego identyfikatora pracy.
    - Zachowana zostanie struktura szablonu pracy oraz lokalizacja funkcji odłożenia (a także przyszłych par pobranie/odłożenie). Wartości następujących pól identyfikatora pracy są kopiowane z oryginalnej pracy do nowej pracy:

        - Identyfikator ładunku
        - Identyfikator wysyłki
        - Typ zlecenia
        - Numer zamówienia
        - Oddział
        - Magazyn
        - Priorytet pracy
        - Identyfikator puli pracy
        - Identyfikator grupy czynności
        - Identyfikator tworzenia pracy

    - Następujące pola nie są kopiowane do nowego identyfikatora pracy:

        - **Identyfikator pracy** — nowy identyfikator pracy jest generowany na podstawie odpowiedniej sekwencji numerów.
        - **Stan pracy** — to pole jest ustawione jako *Otwarte*.
        - **Zablokowane przez** — to pole jest początkowo ustawione jako puste.
        - **Docelowy identyfikator numeru identyfikacyjnego** — to pole jest puste.
        - **Data i godzina utworzenia** — to pole ma ustawioną bieżącą datę i godzinę.
        - **Zablokowana grupa czynności/zamrożona** — to pole jest przeliczane dla oryginalnego identyfikatora pracy i nowego identyfikatora pracy.

1. W okienku akcji wybierz **Podział pracy**.

Podczas dzielenia pracy jest pokazywany następujący komunikat: „Operacja przetwarzania — podział pracy”. Gdy ten komunikat jest widoczny, można anulować operację, klikając przycisk **Anuluj** w oknie komunikatu.

Jeśli pole wyboru **Pokaż wszystkie wiersze** jest wyczyszczone, wiersz, który został podzielony i anulowany, nie będzie już wyświetlany w siatce. Jeśli to pole wyboru jest zaznaczone, należy sprawdzić, czy wartość w polu **Stan pracy** dla danego wiersza została zmieniona na *Anulowane*.

Pokazane jest następujące powiadomienie wskazujące, że utworzono identyfikator nowego zadania: „Praca \#\#\#\# została utworzona przez podzielenie od pracy oryginalnej \#\#\#\#”.

Inne wiersze pracy z oryginalnego identyfikatora pracy (np. wierszy *odłożenia*) będą korygowane zgodnie z potrzebami, aby odzwierciedlić wiersze pracy, które zostały anulowane. Jeśli na przykład pierwotny identyfikator pracy ma wiersz *odłożenia* dla ilości 15, a wiersze *pobrania* o całkowitej ilości 10 zostały anulowane, nowa ilość w *odłożenia* oryginalnym identyfikatorze pracy będzie teraz równa 5.

Nowa praca nie zostanie natychmiast przypisana do żadnego użytkownika. Można jednak przypisać ją do użytkownika teraz, zgodnie z potrzebą, za pomocą standardowych funkcji strony **Szczegóły pracy**.

> [!IMPORTANT]
> Można podzielić tylko te identyfikatory pracy, które zawierają co najmniej dwa dostępne wiersze pracy. Jeśli wybrano tylko jeden wiersz pracy **Podział pracy**, zostanie wyświetlony następujący komunikat o błędzie: „Co najmniej jeden wiersz pracy musi pozostać w pracy początkowej”. W takim przypadku podział nie zostanie wykonany.

## <a name="finish-a-work-split"></a>Kończenie podziału pracy

Aby zakończyć pracę z podziałem, należy usunąć przyczynę blokady *Podziału pracy*. Istnieją dwa sposoby na zakończenie tego kroku:

- Użytkownik, który dzieli pracę, zamyka stronę **Podziału pracy**, wybierając przycisk **Zamknij** (**X**) w prawym górnym rogu. Gdy strona zostanie zamknięta, przyczyna blokady *Podziału pracy* zostanie usunięta. Stan *Zablokowane* tej pracy zostanie ponownie obliczony, jeśli nie pozostały żadne przyczyny blokowania tej pracy, praca zostanie odblokowana.
- Każdy użytkownik otworzy identyfikator pracy i wybierze przycisk **Anuluj sesję podziału pracy** w okienku akcji. Przyczyna blokowania *Podziału pracy* zostanie usunięta, a stan *Zablokowane* dla tej pracy zostanie ponownie obliczony, tak jak w przypadku zamknięcia strony **Podziału pracy**.

Po usunięciu przyczyny zablokowania *Podziału pracy* można uruchomić pracę na urządzeniu przenośnym, pod warunkiem, że w identyfikatorze pracy stan **Zablokowane** jest ustawiony wartość *Nie*.

## <a name="user-blocking-on-the-warehouse-app"></a>Blokowanie użytkowników w aplikacji magazynowej

W przypadku użycia aplikacji magazynowej do uruchomienia pobierania pracy według identyfikatora pracy, pojawi się następujący komunikat o błędzie: „Praca o identyfikatorze \#\#\#\# jest obecnie dzielona”. Jeśli zostanie wyświetlony ten komunikat, wybierz przycisk **Anuluj**. Następnie można kontynuować przetwarzanie innej pracy.

## <a name="other-blocked-operations"></a>Inne zablokowane operacje

Wszystkie operacje, które modyfikują wiersze pracy, transakcje dotyczące magazynu pracy lub łącza uzupełniania związane z pracą, która jest podzielona, będą kończyć się niepowodzeniem i wyświetlany będzie następujący komunikat o błędzie: „Praca z identyfikatorem \#\#\#\# jest obecnie dzielona”.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]