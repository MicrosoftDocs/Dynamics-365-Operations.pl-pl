---
title: Generuj raporty Affordable Care Act w zarządzaniu świadczeniami
description: W tym temacie opisano, w jaki sposób zarządzanie świadczeniami pomaga w śledzeniu informacji, które są zgłaszane na formularzu 1095-B i formularzu 1095-C dotyczącym mandatu pracodawcy na podstawie ustawy o przystępnej opiece (ACA).
author: andreabichsel
manager: tfehr
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 2e4b250f4a059719067a9e19bbf3ce4aecc9bb1f
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113896"
---
# <a name="generate-aca-reports-in-benefits-management"></a>Generowanie raportów ACA w zarządzaniu świadczeniami

W jaki sposób zarządzanie świadczeniami pomaga w śledzeniu informacji, które są zgłaszane na formularzu 1095-B i formularzu 1095-C dotyczącym mandatu pracodawcy na podstawie ustawy o przystępnej opiece (ACA). Podobnie jak funkcja raportowania ACA w starym obszarze roboczym **Świadczenia**, ta funkcja dotyczy wyłącznie firm w Stanach Zjednoczonych.

Aby korzystać z tej funkcji, należy najpierw włączyć **Zarządzanie zaawansowanymi świadczeniami**. Aby uzyskać więcej informacji, w tym ważne informacje dotyczące zarządzania świadczeniami, zobacz temat [Włączanie lub wyłączanie funkcji zarządzania świadczeniami](hr-admin-manage-features.md#enable-or-disable-benefits-management).

> [!IMPORTANT]
> Raportowania ACA można używać tylko z obszaru roboczego **Zarządzanie świadczeniami** lub starego obszaru roboczego **Świadczenia**, a nie z obu tych obszarów. Na przykład po przełączeniu do obszaru roboczego Zarządzanie świadczeniami raportowanie ACA jest dostępne tylko z obszaru roboczego **Zarządzanie świadczeniami**, a nie ze starego obszaru roboczego **Świadczenia**.
>
> Jeśli przełączysz się na zarządzanie świadczeniami w środku roku rejestracji, musisz poprawnie skonfigurować dane pracowników za cały rok w Zarządzaniu świadczeniami. Zapewnia to otrzymywanie dokładnych informacji dotyczących raportowania przez cały rok.

## <a name="getting-started"></a>Rozpoczęcie pracy

Aby śledzić informacje dotyczące formularzy 1095, najpierw utwórz jedną lub więcej grup objętych usługą Affordable Care. Grupy te wskazują następujące informacje:

- Oferta świadczenia dostarczonego pracownikowi
- Udział pracownika w najniższej miesięcznej składce, jeśli koszt przekracza federalną granicę ubóstwa
- Program „Bezpieczna Przystań” używany przez pracodawcę, jeśli ma zastosowanie

Grupy objęcia świadczeniami ACA pomagają w zarządzaniu informacjami w przypadku wielu rekordów pracowników, które mają te same warunki. Grupy można łatwo przypisywać do jednego lub większej liczby pracowników.

### <a name="create-or-edit-an-affordable-care-coverage-group"></a>Utwórz lub edytuj grupę ubezpieczenia w przystępnej cenie

1. W obszarze roboczym **Zarządzanie świadczeniami** wybierz **Grupa ubezpieczeniowa Affordable Care**.

    ![Wybieranie grupy Affordable Care](./media/hr-benefits-management-aca-coverage-group.png)

2. Wybierz pozycję **Nowy**, aby utworzyć nową grupę pokrycia Affordable Care lub **Edytuj**, aby zmienić istniejącą grupę.

    ![Wybieranie nowej lub edycji](./media/hr-benefits-management-aca-new.png)

3. Ustaw wartości w następujących polach.

    | Pole | opis |
    |---|---|
    | Imię i nazwisko | Umożliwia wprowadzenie nazwy grupy. |
    | opis | Służy do wprowadzania opisu grupy. |
    | Oferta świadczenia | Ubezpieczenie oferowane pracownikom, ich małżonkom lub partnerom oraz osobom na ich utrzymaniu. |
    | Udział pracownika w koszcie | Kwota, za którą odpowiada pracownik. |
    | Odpowiednia sekcja 4980H w zakresie struktury zabezpieczeń informacji (program Safe Harbor) | Kod bezpiecznej przystani 4980H lub kod zwolnienia w okresie przejściowym. |
    | Miesiąc rozpoczęcia planu | Wybierz miesiąc kalendarzowy, w którym rozpoczyna się rok planu świadczeń. |
    | Grupa ważna od | Data, od kiedy ten rekord jest ważny. |
    | Grupa ważna do | Ostatnia data ważności tego rekordu. Jeśli nie ma daty ważności, wprowadź wartość **Nigdy**. |

    ![Tworzenie grupy zapotrzebowania](./media/hr-benefits-management-aca-new-group.png)

4. Wybierz opcję **Zapisz**.

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a>Przydziel wielu pracowników do grupy objętej usługą Affordable Care

1. W obszarze roboczym **Zarządzanie świadczeniami** wybierz **Grupa ubezpieczeniowa Affordable Care**.
2. Wybierz grupę, do których mają zostać przypisani pracownicy.
3. Wybierz **Przypisanie grupowe**.

    ![Wybierz Przypisanie grupowe](./media/hr-benefits-management-aca-mass-assignment.png)

4. Wybierz pracowników z listy, a następnie **Przypisz**.

    ![Przydzielanie wybranych pracowników do grupy](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a>Utrzymuj wiele wersji opcji pokrycia

Możesz utrzymywać wiele wersji dowolnej grupy pokrycia. Gdy coś się zmieni w Twojej organizacji lub w oferowanych korzyściach, możesz aktualizować informacje o grupie bez konieczności tworzenia nowej grupy i ponownego przypisywania do niej pracowników.

Po utworzeniu grup ubezpieczenia w przystępnej cenie Affordable Care możesz masowo przypisywać do nich pracowników. Możesz również indywidualnie przypisywać pracowników do grup i wskazywać, czy informacje ACA są śledzone i raportowane.

Jeśli nie ma potrzeby śledzenia i zgłaszania informacji ACA pracownika, w opcji **Zgłaszaj objęcie świadczeniem** można ustawić wartość **Nie**. Na przykład mogą to być pracownicy na część czasu, którzy nie wymagają zgłaszania do ACA.

### <a name="override-default-values-for-an-employee"></a>Zastępowanie wartości domyślnych dla pracownika

W przypadku pracowników przypisanych do grupy ACA można zmienić następujące opcje na dowolne miesiące wymagające różnych wartości:

- Oferta świadczenia
- Udział pracownika w koszcie
- Odpowiednia sekcja 4980H w zakresie struktury zabezpieczeń informacji (program Safe Harbor)

> [!NOTE]
> W przypadku zgłoszeń ACA 2020 raporty pracy i kody pocztowe są raportami w formularzu 1095-C. Wartości są wypełniane automatycznie na podstawie bieżących aktywnych lokalizacji. Jeśli w trakcie dowolnej części roku każda z tych lokalizacji różniła się między lokalizacjami, należy zastąpić tę wartość. Pole **Kod pocztowy** (wiersz 17) raportu 1095-C jest wypełniane tylko w przypadku, gdy kod **Oferta świadczenia** zawiera kod od **1L** do **1Q**, w następujący sposób:
>
> - **1L, 1M lub 1N:** kod pocztowy siedziby głównej
> - **1O, 1P, 1Q:** główny kod pocztowy pracy

Aby wprowadzić wyjątki dla dowolnej wartości grupy świadczeń Affordable Care, wykonaj następujące kroki.

1. W obszarze roboczym **Zarządzanie personelem** wybierz opcję **Łącza**, a następnie wybierz **Pracownicy**.
2. Na liście zaznacz pracownika.
3. Na karcie **Zatrudnienie** w sekcji **Więcej informacji** wybierz opcję **Świadczenia ACA**.

    ![Zmienianie opcji dla jednego pracownika](./media/hr-benefits-management-aca-change-single-employee.png)

4. Wybierz opcję **Edycja**.
5. Dla każdego miesiąca wymagającego zmian zaznacz pole wyboru **Zastąp domyślne**, a następnie w razie potrzeby zmień inne wartości.

    ![Zastępowanie wartości domyślnych](./media/hr-benefits-management-aca-override-default.png)

6. Wybierz opcję **Zapisz**.

## <a name="report-health-care-coverage"></a>Zgłoś objęcie świadczeniem zdrowotnym

Musisz śledzić wszystkie ubezpieczenia zdrowotne sponsorowane przez pracodawcę, ubezpieczone przez samych siebie, dla pracowników zatrudnionych w pełnym i niepełnym wymiarze godzin. Uwzględnij każdego pracownika razem z ich na utrzymaniu w raporcie 1095-C dla miesięcy, w których zostały objęte.

Aby wskazać, czy ma zostać zgłoszony plan świadczeń, należy wykonać następujące czynności.

1. W obszarze roboczym **Zarządzanie świadczeniami** wybierz opcję **Plany świadczeń**.
2. Wybierz program świadczeń do zgłoszenia.
3. Wybierz opcję **Edycja**.
4. Ustaw wartość opcji **Zgłoszone do Affordable Care Act** na **Tak**.

    ![Zgłaszanie objęcia świadczeniem zdrowotnym](./media/hr-benefits-management-aca-report-coverage.png)

5. Wybierz opcję **Zapisz**.

Jeśli pracownik wybiera ubezpieczenie zdrowotne dla osoby pozostającej na utrzymaniu, okres ubezpieczenia osoby pozostającej na utrzymaniu jest określany na podstawie daty zapisania lub usunięcia osoby pozostającej na utrzymaniu. Daty ubezpieczenia osób pozostających na utrzymaniu są obliczane automatycznie na podstawie okresu, w którym osoba pozostająca na utrzymaniu kwalifikowała się i była aktywna w ramach planu w ciągu roku rejestracji.

## <a name="generate-1095-b-and-1095-c-forms"></a>Generowanie formularzy 1095-B i 1095-C

Formularze 1095-B i 1095-C ACA można również wygenerować i rozesłać je odnośnym pracownikom. Możesz również wygenerować elektronicznie formularz 1095-C i odpowiednie pliki przekazu 1094-C, aby wysłać je do Internal Revenue Service (IRS).

1. W obszarze roboczym **Zarządzanie świadczeniami** wybierz formularz **ACA 1095-B** lub formularz **ACA 1095-C**.
2. W razie potrzeby zmień parametry i wybierz przycisk **OK**.

    > [!NOTE]
    > W wypadku drukowania formularzy 1095-C dla więcej niż 500 pracowników otrzymasz więcej niż jeden plik PDF. Zaleca się zwiększenie wartości pola **Maksymalny rozmiar pliku w megabajtach** na stronie **Parametry zarządzania dokumentami** do **150**. (Aby szybko otworzyć tę stronę, można użyć pola wyszukiwania na pasku nawigacji.)
    >
    > ![Zmienianie maksymalnego rozmiaru pliku](./media/hr-benefits-management-aca-maximum-file-size.png)

3. Aby sprawdzić stan raportów i wyświetlić je, użyj pola wyszukiwania na pasku nawigacyjnym, aby otworzyć stronę **Zadania raportowania elektronicznego**.

    ![Wyszukiwanie strony zadań raportowania elektronicznego](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. Wybierz raport do wyświetlenia, a następnie wybierz polecenie **Pokaż pliki**.

    ![Wyświetlanie plików](./media/hr-benefits-management-aca-show-files.png)

5. Kliknij przycisk **Otwórz**.

    ![Otwieranie pliku](./media/hr-benefits-management-aca-open-file.png)

6. Na pasku powiadomień w dolnej części okna przeglądarki otwórz plik ZIP, a następnie wybierz raport. Plik PDF można wyświetlić lub wydrukować.

    ![Przykładowy formularz 1095-C](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a>Wyświetlanie informacji o świadczeniach ACA

Na stronie **Świadczenia Worker Affordable Care** dla pracownika są podane następujące informacje:

- Pracownicy przypisani do poszczególnych grup świadczeń
- Pracownicy, którzy nie muszą być uwzględniani w raporcie
- Nieprzypisani pracownicy

Aby wyświetlić informacje, wykonaj następujące kroki.

1. W obszarze roboczym **Zarządzanie świadczeniami** wybierz **Pracownik objęty ubezpieczeniem Affordable Care**.
2. W polu **Nazwa grupy** wprowadź grupę.

    ![Wyświetlanie świadczeń ACA](./media/hr-benefits-management-aca-view-coverage.png)

Jeśli którakolwiek domyślna wartość grupy objętej świadczeniem ACA zostanie zastąpiona, obok niej będzie widoczna gwiazdka. Jeśli wartości dla wszystkich dwunastu miesięcy są takie same i nie zostały zastąpione, wartość zostanie wydrukowana w kolumnie **Wszystkie 12 miesięcy**.

Można wyświetlać pracowników, których oznaczono jako nie podlega zgłoszenia ACA i którzy nie wymagają formularza 1095-C. W polu **Filtruj według** wybierz opcję **Nie do zgłoszenia do ACA**.

Można wyświetlać pracowników, którzy nie są przypisani do grupy lub są przypisani do grupy, których ważność wygasła. W polu **Filtruj według** wybierz grupę **Nieprzypisane lub Wygasłe**.

### <a name="export-to-excel"></a>Eksportuj do programu Excel

Aby wyeksportować dowolną z list do programu Microsoft Excel, wykonaj następujące kroki.

1. Wybierz przycisk **Otwórz w pakiecie Microsoft Office**.
2. Wybierz **Tymczasowa tabela HCM Human Resources do użytku wewnętrznego**.
3. Wybierz opcję **Pobierz**.

### <a name="view-aca-reportable-dependents"></a>Wyświetlanie osób na utrzymaniu podlegających świadczeniom ACA

Jeśli trzeba zgłosić osoby objęte świadczeniem, ponieważ zapewnia się objęcie ubezpieczeniam własnym, można wyświetlać osoby na utrzymaniu objęte planami świadczeń oznaczonymi jako **Objęte zgłoszeniem do ACA**. Na okienku akcji wybierz opcję **Wyświetl świadczenia osób na utrzymaniu**.

![Wyświetlanie zakresu osób na utrzymaniu](./media/hr-benefits-management-aca-view-dependent-coverage.png)

Wyświetlane są informacje o świadczeniach osób na utrzymaniu pracownika.

![Świadczenie dla osoby na utrzymaniu](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> Na stronie są dostępne tylko plany świadczeń oznaczone jako **objęte zgłoszeniem do ACA**.
