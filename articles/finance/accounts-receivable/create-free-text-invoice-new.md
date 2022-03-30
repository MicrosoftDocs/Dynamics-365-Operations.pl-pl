---
title: Tworzenie faktury niezależnej
description: W tym temacie opisano sposób tworzenia faktur niezależnych.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 6e9578d9b2d61f241ab5e92fc9740b88b80969f6
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/07/2022
ms.locfileid: "8392892"
---
# <a name="create-a-free-text-invoice"></a>Tworzenie faktury niezależnej

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia faktur niezależnych. Ta procedura wykorzystuje firmę demonstracyjną **USMF**.

## <a name="create-a-free-text-invoice"></a>Tworzenie faktury niezależnej

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami (lub Księga sprzedaży) \> Faktury \> Wszystkie faktury niezależne**.
2. Wybierz pozycję **Nowy**.
3. W polu **Konto odbiorcy** wybierz wartość.

    * Domyślnie kontem faktury będzie konto wybrane jako konto odbiorcy.
    * Jeśli faktura nie jest zaksięgowana, stan księgowania zaczyna się od stanu **W trakcie przetwarzania**.
    * Identyfikator faktury zostanie przypisany podczas księgowania faktury.
    * Jeśli używasz upoważnień bankowych SEPA (Jednolitego Obszaru Płatniczego w Euro), zgoda na polecenie zapłaty będzie automatycznie wprowadzana po wybraniu konta odbiorcy.

4. W polu **Opis** wprowadź lub wybierz wartość.
5. W polu **Konto główne** określ numer konta, które nie ma wymiarów. Wymiary zostaną wprowadzone w dalszej części tego tematu.

    Można również wpisać jeden lub więcej znaków konta głównego, a następnie za pomocą funkcji wyszukiwania znaleźć konto.

6. Kliknij skróconą kartę **Szczegóły wiersza**, aby dodać wymiary do konta głównego.
7. Kliknij kartę **Wiersz wymiarów finansowych**.

    * Wymiary dotyczą tylko wybranego wiersza.
    * Grupa podatków jest wypełniania domyślnie na podstawie odbiorcy. Jeśli odbiorca nie ma zdefiniowanej grupy podatków, jest używana grupa podatków z konta głównego.
    * Grupa podatków dla pozycji jest wypełniana na podstawie konta głównego. Jeśli konto główne nie ma zdefiniowanej grupy podatków dla pozycji, jest używana grupa podatków dla pozycji określona w parametrach podatków w Księdze głównej.

8. Opcjonalnie: wprowadź liczbę w polu **Ilość**.
9. Opcjonalnie: w polu **Cena jednostkowa** wpisz liczbę.

    Kwota jest obliczana jako ilość pomnożona przez cenę jednostkową. Można jednak zastąpić wynik tego obliczenia poprzez samodzielne wprowadzenie kwoty.

10. Kliknij opcję **Podatek**, aby wyświetlić podatek obliczony dla faktury.

    Można wyświetlić kwoty podatków na tej stronie albo zastąpić kwoty na karcie **Korekta**.

11. Kliknij przycisk **OK**.
12. Kliknij opcję **Opłaty**, aby dodać opłatę do faktury.
13. W polu **Kod opłat** wpisz wartość.
14. W polu **Wartość opłat** wprowadź liczbę.
15. Zamknij stronę.
16. Kliknij opcję **Sumy**, aby wyświetlić szczegóły i sumy faktury zbiorczej.
17. Kliknij przycisk **Zamknij**.
18. Wybierz opcję **Księguj**, aby zaksięgować fakturę. Nadal będziesz mieć możliwość anulowania operacji przed rzeczywistym zaksięgowaniem.

    * Możesz zmienić harmonogram drukowania faktur. Zaznacz opcję **Bieżąca**, aby drukować każdą fakturę po jej aktualizacji. Zaznacz opcję **Po**, aby drukować po zaktualizowaniu wszystkich faktur.
    * Aby zmienić sposób weryfikowania limitu kredytowego odbiorcy przed zaksięgowaniem faktury, zmień wartość w pola **Typ limitu kredytu**.
    * Na karcie **Aktualizacje** na stronie **Parametry rozrachunków z odbiorcami** (**Rozrachunki z odbiorcami > Ustawienia > Parametry rozrachunków z odbiorcami**) możesz zatrzymać księgowanie faktury niezależnej po wystąpieniu błędu. Wybierz opcję **Tak**, aby **zatrzymać księgowanie** faktur wolnych dla pierwszego parametru błędu, aby zatrzymać księgowanie faktur wolnych w przypadku wystąpienia błędu. W przypadku zaksięgowania w partii błąd spowoduje zatrzymanie procesu księgowania, a stan partii będzie ustawiony na **Błąd**. Jeśli ta opcja nie zostanie wybrana, proces księgowania pominie fakturę z błędem księgowania i będzie kontynuował księgowanie dodatkowych faktur. Jeśli księgowanie w partii, błąd księgowania nie zapobiegnie zaksięgowaniu innych faktur. Stan partii będzie **zakończony**. Szczegółowy raport procesu księgowania będzie dostępny do przeglądu w historii zadań wsadowych.
    * Aby wydrukować fakturę, zaznacz w tej opcji wartość **Tak**.
    * Aby zaksięgować fakturę, zaznacz w tej opcji wartość **Tak**. Fakturę można wydrukować bez księgowania.

19. Kliknij przycisk **OK**.

## <a name="copy-lines"></a>Kopiuj wiersze
Aby skopiować wiersze faktury niezależnej, zaznacz jeden lub więcej wierszy, a następnie kliknij przycisk **Kopiuj zaznaczone wiersze**. Można określić liczbę kopii, jaka ma zostać wykonana, oraz skopiować notatki i załączniki. Można skopiować dystrybucje lub pozwolić na ich ponowne tworzenie podczas księgowania.

Po skopiowaniu wierszy można edytować informacje zgodnie z potrzebami.

## <a name="create-a-free-text-invoice-from-a-template"></a>Tworzenie faktury niezależnej z szablonu
Fakturę niezależną można utworzyć na podstawie szablonu. Gdy na karcie **Faktura** wybierzesz opcję **Nowe z szablonu**, można wybrać nazwę szablonu i konto odbiorcy dla nowej faktury niezależnej. Wartości domyślne, takie jak warunki płatności i metoda płatności, mogą być automatycznie wprowadzane na podstawie danych odbiorcy lub też można użyć wartości zapisanych w szablonie.

Zostanie utworzona nowa faktura niezależna i można w niej edytować wartości zgodnie z potrzebami.

## <a name="resetting-the-workflow-status-for-free-text-invoices-from-unrecoverable-to-draft"></a>Resetowanie stanu przepływu pracy dla faktur niezależnych z Nieodwracalne na Wersja robocza
Wystąpienie przepływu pracy, które zostało zatrzymane z powodu nieodwracalnego błędu będzie miało stan przepływu pracy **Nieodwracalne**. Gdy stan przepływu pracy faktury niezależnej od odbiorcy to **Nieodwracalne**, można go zmienić na **Wersja robocza**, wybierając opcję **Odwołaj** z akcji przepływu pracy. Następnie można edytować fakturę wolną od faktur dla odbiorcy. Ta funkcja jest dostępna, jeśli jest włączony parametr **Resetowanie statusu przepływu pracy dla faktur niezależnych z Nie do odzyskania na Wersja robocza** na stronie **Zarządzanie funkcjami**.

Za pomocą strony **Historia przepływu pracy** można zmienić stan przepływu pracy na **Wersja robocza**. Można otworzyć tę stronę z menu **Faktura niezależna** lub z menu nawigacji **Wspólne > Zapytania > Przepływ pracy**. Aby zresetować stan przepływu pracy na **Wersja robocza**, wybierz opcję **Odwołaj**. Możesz również zresetować stan przepływu pracy do **wersji roboczej**, wybierając akcję **Odwołaj** na stronie **Faktura niezależna** lub na stronie **Wszystkie faktury niezależne**. Po zmianie stanu przepływu pracy na **Wersja robocza**, fakturę będzie można edytować na stronie **Faktura niezależna**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
