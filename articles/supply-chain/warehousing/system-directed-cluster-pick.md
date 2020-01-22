---
title: Pobieranie dla grupy sterowane przez system
description: Ten temat zawiera omówienie pobierania dla grupy sterowanego przez system w aplikacji Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: c3b23a5d3b77bae89e4845bdff4ab20f95c46497
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917863"
---
# <a name="system-directed-cluster-picking"></a>Pobieranie dla grupy sterowane przez system

[!include [banner](../includes/banner.md)]

Pobieranie dla grupy jest procesem pobierania elementów, który umożliwia wybieranie elementów dla wielu zamówień w tym samym czasie przez pobieranie ich do wybranej grupy. Następnie musisz odwiedzić lokalizację pobrania tylko jeden raz. Zazwyczaj ta funkcja jest używana do pobierania małych zamówień lub ilości, które są mniejsze niż wielkości dla przypadku.

Po skonfigurowaniu pobierania dla grupy sterowanego przez system można wybrać nagłówki robocze pobierania dla grupy na grupie wygenerowanej przez system. System pobiera zamówienia dla grupy do liczby stanowisk określonej w profilu grupy. W związku z tym można wybrać wiele zamówień w tym samym czasie bez konieczności ręcznego tworzenia grupy.

Pobieranie dla grupy sterowane przez system oferuje alternatywę dla ręcznego budowania grupy, gdzie profil grupy jest używany do tworzenia grupy. Przed użyciem grupy należy w jej profilu skonfigurować kilka wierszy związanych z konfiguracją:

- **Liczba stanowisk** odpowiada liczbie zleceń, które zostaną umieszczone w grupie. W związku z tym odpowiada liczbie pojemników.
- Wartość **Podziel grupę** określa, kiedy należy podzielić grupę.
- Wartość **Generuj identyfikator grupy** kontroluje, czy identyfikator grupy zostanie wygenerowany przez system lub wprowadzony przez użytkownika.
- **Typ weryfikacji sortowania** określa, czy wymagana jest weryfikacja pozycji.

Nowy element menu urządzenia przenośnego służy do pobierania dla grupy sterowanego przez system. Identyfikator profilu grupy należy określić dla opcji **Sterowane przez**. Ponadto kolejność zapytań sterowanych przez system może grupować zamówienia na podstawie kryteriów specyficznych dla firmy. W związku z tym można dodatkowo zoptymalizować przypisania zleceń pracy, określając dostosowane kryteria sortowania na potrzeby porządkowania zamówień sterowanego przez system.

Po zakończeniu pobierania dla grupy sterowanego przez systemu pracownicy magazynu uzyskują dostęp do grupy, w którym zamówienia pobrania zostały wstępnie przypisane do stanowisk grupy. W związku z tym pracownicy mogą zacząć wybierać element dla wielu zleceń pracy, odwiedzając lokalizację pobrania tylko jeden raz. Proces pobierania dla grupy sterowany przez system jest taki sam jak proces pobierania dla grupy sterowany przez użytkownika.

## <a name="set-up-system-directed-cluster-picking"></a>Konfigurowanie pobierania dla grupy sterowanego przez system

### <a name="create-cluster-profiles"></a>Tworzenie profilów grup

Profile grup kontrolują sposób, w jaki system tworzy każdą grupę. Jeśli wymagane są różne grupy, dla każdego elementu menu urządzenia przenośnego należy utworzyć inny profil grupy.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Profile grup**.
2. Wybierz pozycję **Nowy**.
3. W polu **Identyfikator profilu grupy** wprowadź **Pozycja 2**.
4. W polu **Nazwa** wprowadź **Pozycja 2**.
5. Na skróconej karcie **Ogólne** ustaw następujące pola:

    - **Generuj identyfikator grupy:** ustaw tę opcję na **Tak**. Ta opcja określa, czy identyfikator grupy jest automatycznie tworzony przez system, czy też użytkownik utworzy go na początku pobierania.
    - **Aktywuj stanowiska:** ustaw tę opcję na **Tak**. Ta opcja określa, czy nazwy stanowisk są generowane automatycznie na podstawie konfiguracji nazw stanowisk. Jeśli ta opcja zostanie ustawiona na **Nie**, będzie używany numer identyfikacyjny dla stanowiska.
    - **Liczba stanowisk:** wprowadź **2**. To pole określa maksymalną liczbę stanowisk, które może zawierać grupa (czyli maksymalną liczbę opakowań, pojemników itd.).
    - **Nazwa stanowiska:** wybierz pozycję **Numeryczna**, tak aby stanowiska były nazywane przy użyciu liczb ciągłych. Jeśli wybierzesz pozycję **Alfabetyczna**, stanowiska będą nazywane w kolejności alfabetycznej.
    - **Podziel grupę w:** wybierz pozycję **Odłożenie**. To pole określa, kiedy grupa jest dzielona.
    - **Typ weryfikacji sortowania:** wybierz pozycję **Skan pozycji**. To pole określa, czy jest weryfikowany krok odłożenia do pozycji.

6. Na skróconej karcie **Sortowanie grupy** można zdefiniować kryteria sortowania, tworząc nowy wiersz i ustawiając następujące pola:

    - **Numer sekwencyjny** : to pole określa sekwencję, według której system sortuje. Wartość jest wprowadzana automatycznie, ale w razie potrzeby można ją zmienić.
    - **Nazwa pola:** wybierz wartość **WMSLocationId**. To pole określa pole używane przez wiersz dla kryteriów sortowania.
    - **Sortowanie:** wybierz pozycję **Rosnąco**. To pole określa, czy sortowanie odbywa się w porządku rosnącym czy malejącym.

### <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego

Aby utworzyć nowy element menu urządzenia przenośnego dla pobierania dla grupy sterowanego przez system i połączyć identyfikator profilu grupy z elementem menu urządzenia przenośnego, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa elementu menu** wprowadź **Grupa SD**.
4. W polu **Tytuł** wprowadź **Grupa SD**.
5. W polu **Tryb** wybierz opcję **Praca**.
6. W opcji **Użyj istniejącej pracy** zaznacz wartość **Tak**.
7. Na skróconej karcie **Ogólne** ustaw następujące pola:

    - **Sterowane przez**: wybierz opcję **Sterowane przez system**.
    - **Generuj numer identyfikacyjny:** ustaw tę opcję na **Tak**.
    - **Identyfikator profilu grupy:** wybierz opcję **Pozycja 2**.

8. Na skróconej karcie **Klasy robocze** skonfiguruj prawidłową klasę roboczą dla tego elementu menu urządzenia przenośnego, ustawiając następujące pola:

    - **Identyfikator klasy roboczej:** upewnij się, że wprowadzono wartość **Sprzedaż**.
    - **Typ zlecenia pracy:** upewnij się, że wprowadzono wartość **Zamówienia sprzedaży**.

9. Wykonaj następujące kroki, aby określić nowe zapytanie dotyczące sekwencji pracy sterowanej przez system:

    1. Wybierz pozycję **Nowy**.
    2. W polu **Numer sekwencyjny** wprowadź wartość **1**.
    3. W polu **Opis** wybierz pozycję **Priorytet pracy — identyfikator pracy**.

10. W menu wybierz pozycję **Edytuj zapytanie**.
11. Ustaw następujące pola na karcie **Sortowanie**:

    - **Tabela:** wybierz pozycję **Praca**.
    - **Tabela pochodna:** wybierz pozycję **Praca**.
    - **Pole:** wybierz pozycję **Priorytet pracy**.
    - **Kierunek wyszukiwania:** wybierz pozycję **Rosnąco**.
    - **Tabela:** wybierz pozycję **Praca**.
    - **Tabela pochodna:** wybierz pozycję **Praca**.
    - **Pole:** wybierz pozycję **Identyfikator pracy**.
    - **Kierunek wyszukiwania:** wybierz pozycję **Rosnąco**.

System będzie teraz sortować identyfikatory pracy w grupie, najpierw według priorytetu pracy, a następnie według identyfikatora pracy.

### <a name="set-up-a-mobile-device-menu"></a>Konfigurowanie menu urządzenia przenośnego

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
2. Dodaj element menu, który został właśnie utworzony, do żądanego menu.

## <a name="example"></a>Przykład

### <a name="create-picking-work"></a>Tworzenie pracy pobrania

Aby można było skonfigurować pobieranie dla grupy sterowane przez system, należy utworzyć kilka kwalifikujących się prac wychodzących. Utworzony wcześniej profil grupy określa dwie pozycje grupy. W związku z tym musisz utworzyć co najmniej dwa identyfikatory pracy.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
2. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.
3. W polu **Konto klienta** wybierz dowolnego klienta.
4. Na skróconej karcie **Ogólne** w polu **Magazyn** wybierz magazyn **62**.
5. Kliknij przycisk **OK**.
6. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz pozycję **Dodaj wiersz**.
7. W polu **Numer pozycji** wybierz wartość **A0001**.
8. W polu **Ilość** wpisz wartość **1**.
9. Wybierz pozycję **Dodaj wiersz**, aby dodać drugi wiersz.
10. W polu **Numer pozycji** wybierz wartość **A0002**.
11. W polu **Ilość** wpisz wartość **3**.
12. Powtórz kroki od 2 do 6.
13. W polu **Numer pozycji** wybierz wartość **A0001**.
14. W polu **Ilość** wpisz wartość **4**.
15. Wybierz pozycję **Dodaj wiersz**, aby dodać drugi wiersz.
16. W polu **Numer pozycji** wybierz wartość **A0002**.
17. W polu **Ilość** wpisz wartość **2**.

Zarezerwuj zapasy i zwolnij je do magazynu. Tworzone są dwa różne identyfikatory pracy. Każdy identyfikator pracy ma dwa wiersze pobrania.

### <a name="run-the-mobile-device-flow"></a>Uruchamianie przepływu na urządzeniu przenośnym

1. Na urządzeniu przenośnym wybierz menu, które zawiera nowy element menu urządzenia przenośnego.
2. Wybierz element menu **Grupa SD** i zainicjuj pobieranie. Zostanie utworzona grupa i dwa identyfikatory pracy, które utworzono wcześniej, są do niej dołączane. Jeśli utworzono więcej niż dwa identyfikatory pracy, tylko dwa pierwsze są dodawane do grupy. Zauważ, że identyfikatory pracy są dodawane do grupy w kolejności rosnącej, jak określono w konfiguracji zapytania.

    > [!NOTE]
    > Nowa grupa jest tworzona automatycznie tylko wtedy, gdy wcześniej utworzono wystarczająco dużo dodatkowych identyfikatorów pracy. W przeciwnym razie wyświetlany jest następujący komunikat: „Dla grupy nie można znaleźć wystarczającej ilości pracy”.

    Po wybraniu menu zostanie wyświetlony pierwszy ekran wyboru. System agreguje wszystkie pasujące wiersze pobrania z dwóch identyfikatorów pracy i kieruje Cię do odwiedzenia lokalizacji pobrania jeden raz, dzięki czemu można zrealizować oba zamówienia za pomocą jednego pobrania. Ten proces odbywa się w taki sam sposób jak proces pobierania dla grupy sterowany przez użytkownika.

3. Potwierdź pierwszy wybór. Następnie musisz wprowadzić nazwę pozycji, aby potwierdzić, że elementy zostały umieszczone w prawidłowej pozycji.
4. Powtórz ten proces, aż wszystkie elementy zostaną pobrane i umieszczone w prawidłowej pozycji.
5. Ostatnim krokiem na urządzeniu przenośnym jest umieszczenie grupy w ostatecznej lokalizacji. Po potwierdzeniu tej operacji odłożenia grupa jest zamykana i dzielona na podstawie wartości ustawionej w polu **Podziel grupę w** w profilu grupy. Identyfikatory pracy są również zamknięte.
6. Na urządzeniu przenośnym jest wyświetlany komunikat „Grupa kompletna”.
