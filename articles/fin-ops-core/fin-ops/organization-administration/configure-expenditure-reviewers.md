---
title: Konfigurowanie osób sprawdzających wydatki
description: W tym temacie opisano, jak używać kontrolerów wydatków do dynamicznego wybierania użytkownika, do którego przypisane jest zadanie przepływu pracy, zatwierdzenie lub decyzja ręczna.
author: rachel-profitt
ms.date: 06/25/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2021-06-24
ms.openlocfilehash: ad980889247e0239ad743078cb013c1c5839f676
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070153"
---
# <a name="configure-expenditure-reviewers"></a>Konfigurowanie osób sprawdzających wydatki
[!include[banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Można skonfigurować dynamiczne osoby sprawdzające wydatki, aby kierować wydatki do przeglądu na podstawie użytkownika przypisanego do roli projektu lub wymiaru finansowego, w którym naliczany jest wydatek. Proces przepływu pracy korzysta z określonej roli projektu lub właściciela wymiaru finansowego przy ustalaniu celu marszruty rozchodu.

Można zdefiniować jedną lub więcej konfiguracji rewidenta rozchodów, a następnie wybrać konfigurację podczas tworzenia przepływu pracy. Można konfigurować wartości rewidenta rozchodów dla każdej firmy w organizacji. Zdefiniowane konfiguracje rewidenta rozchodów są przypisywane. Osób sprawdzających wydatki można przypisywać do zadań przepływu pracy, zatwierdzeń i decyzji ręcznych.

> [!NOTE]
> Chociaż weryfikatorzy wydatków nie są obowiązkowi, mogą pomóc uprościć konfigurację przepływu pracy. Na przykład nie trzeba tworzyć jednej warunkowej decyzji, aby sprawdzić każdy wymiar miejsca powstawania kosztów, a następnie utworzyć kolejny element, aby przypisać zatwierdzenie lub zadanie do określonego użytkownika lub grup użytkowników. Zamiast tego można skonfigurować właściciela wymiaru centrum kosztów i użyć kontrolera wydatków, aby dynamicznie wybrać odpowiedniego użytkownika. W ten sposób, gdy prawa własności lub przypisanie centrów kosztów się zmieni, wystarczy zaktualizować pole **Właściciel** dla wymiaru finansowego.

## <a name="types-of-expenditure-reviewers"></a>Typy rewidentów rozchodów

Nie wszystkie przepływy pracy obsługują koncepcję recenzentów wydatków. Domyślnie można skonfigurować osób sprawdzających wydatki dla zapo zapotrzebowania na zakup, zamówienia zakupu, faktury dostawcy i raporty z wydatków. Każdy z tych typów przepływu pracy wymaga skonfigurowania kontrolerów wydatków na osobnej stronie, która jest specyficzna dla funkcji i modułu. W przypadku każdego obsługiwanego dokumentu weryfikatorów wydatków można używać z przepływami pracy na poziomie nagłówka lub z przepływami pracy na poziomie wiersza.

Poniższa tabela pokazuje, gdzie można skonfigurować kontrolera wydatków dla każdego obsługiwanego dokumentu.

| Wydruk pokwitowania | Ścieżka nawigacji |
|----------|-----------------|
| Raporty z wydatków | Zarządzanie wydatkami \> Ustawienia \> Zasady \> Rewidenci rozchodów |
| Zamówienia zakupu | Zaopatrzenie i sourcing \> Ustawienia \> Zasady \> Rewidenci wydatków zamówień zakupu |
| Zapotrzebowania na zakup | Zaopatrzenie i sourcing \> Ustawienia \> Zasady \> Rewidenci wydatków zapotrzebowania na zakup |
| Faktury dostawcy | Rozrachunki z dostawcami \> Ustawienia zasad \> Rewidenci wydatków na faktury dostawcy |

## <a name="expenditure-reviewer-assignments"></a>Zadania rewidentów wydatków

Dla każdego recenzenta wydatków dostępne są dwa typy przydziału: *dystrybucje projektu* i *dystrybucje organizacji*. W przypadku dystrybucji projektu można wybierać między uprawnieniami projektu a wymiarami finansowymi. W przypadku dystrybucji organizacji można wybrać wymiary finansowe.

Do urzędów projektu należy menedżer projektu, kontroler projektu i kierownik ds. sprzedaży projektu. Aby zdefiniować te urzędy bezpośrednio w projekcie, należy wybrać pracownika w odpowiednich polach.

Wymiary finansowe są kontrolowane przez struktury kont w poszczególnych firmach. Dla każdej firmy można wybrać wymiary finansowe, które będą używane dla osoby sprawdzanej rozchody. Wymiary mogą pochodzić z projektu (w tym przypadku należy wybrać wymiary na karcie **Dystrybucje projektu**) lub z dokumentu (w tym przypadku należy wybrać wymiary na karcie **Dystrybucje organizacji**). W polu **Właściciel** na stronie **Wartości wymiarów finansowych** możesz wybrać pracownika dla każdego wymiaru finansowego.

## <a name="example-1-expenditure-reviewers-based-on-organization-distributions"></a>Przykład 1: Weryfikatorzy wydatków na podstawie podziałów organizacji

Pracujesz dla Contoso Appliances, a Twoja organizacja ma sześć działów i 10 centrów kosztów. Po przesłaniu nowego zapotrzebowania na zakup zatwierdzenie musi pochodzić najpierw od kierownika działu, a następnie od kierownika centrum kosztów.

W tym przykładzie należy skonfigurować dwóch osób *sprawdzających wydatki związane z zapotrzebowaniami zakupu*:

- Dla pierwszej osoby sprawdzającej nadasz nazwę działowi, a następnie wybierz wymiar finansowy **Dział** na karcie **Dystrybucje organizacji**. 
- Dla drugiej osoby sprawdzającej nadasz Centrum kosztu, a następnie wybierz wymiar finansowy **Centrum kosztu** na karcie **Dystrybucje organizacji**.

Podczas konfigurowania przepływu pracy tworzysz dwa kroki zatwierdzania. Pierwsza z nich jest dla działu, a druga dla Centrum kosztów.. Dla każdego elementu zatwierdzania należy zaznaczyć pole **Uczestnik** w polu **Typ przypisania** na karcie **Oparte na rolach**, wybrać **uczestników rozchodów** w polu **Typ uczestnika**, a następnie wybrać odpowiedniego uczestnika w polu **Uczestnik**.

Po utworzeniu zapotrzebowania na zakup wymiary finansowe działu i centrum kosztów są przypisywane do wierszy zapotrzebowania na zakup. Po przesłaniu przepływu pracy system najpierw ocenia dział zapotrzebowania na zakup i przypisuje element zatwierdzenia użytkownikowi powiązanemu z pracownikiem wybranym dla działu. Po zakończeniu pierwszego etapu zatwierdzania system ocenia drugi etap zatwierdzania i przypisuje drugi element zatwierdzania użytkownikowi powiązanemu z pracownikiem wybranym dla miejsca powstawania kosztów.

## <a name="example-2-expenditure-reviewers-based-on-project-distributions"></a>Przykład 2: Weryfikatorzy wydatków na podstawie dystrybucji projektów

Pracujesz dla oddziału usług Contoso Appliances. Organizacja wymaga, aby kierownik projektu dla każdego zamówienia zakupu zatwierdził wydatek. Ponadto kierownik ds. centrów kosztów projektu musi je zatwierdzić. Zatwierdzenia można dokonać w tym samym czasie. W każdym razie obaj użytkownicy muszą zatwierdzić zamówienie zakupu przed kontynuowaniem przepływu pracy.

W tym przykładzie można utworzyć jedną *osobę sprawdzającą wydatki związane z zamówieniami zakupu* o nazwie **PM i centrum kosztów**. Zaznacz pole wyboru **Menedżer projektur** i ustaw opcję **Wymiar miejsca powstawania kosztów** na **Tak** na karcie **Dystrybucje projektu** strony **Przeglądarka wydatków na zamówienie zakupu**. W ramach konfiguracji musisz mieć pewność, że pole **Menedżer projektu** jest ustawione dla wszystkich projektów i czy właściciel jest określony dla wszystkich centrów kosztów na stronie **Wartości wymiaru finansowego**.

Podczas konfigurowania przepływu pracy potrzebujesz jednego elementu zatwierdzenia. Wybierz **uczestnika** w polu **Typ przypisania**. Następnie na karcie **Oparte na rolach** wybierz **uczestników rozchodów** w polu **Typ uczestnika**, a następnie wybierz menedżera projektu i Centrum kosztów w polu **Uczestnik**. Aby mieć pewność, że przepływ pracy nie może być kontynuowany, dopóki kierownik projektu i właściciel centrum kosztów nie zatwierdzą przepływu pracy, ustaw w polu **Zasady uzupełniania** wartość **Wszystkie osoby zatwierdzające**.

Podczas tworzenia zamówienia zakupu należy określić pole **Projekt**. Jeśli nie potrzebujesz projektu dla wszystkich zamówień zakupu, dodaj warunkową decyzję do przepływu pracy, aby sprawdzić projekt przed uruchomieniem kroku zatwierdzania. Następnie system ocenia projekt określony dla zamówienia zakupu i przypisuje element zatwierdzania do użytkownika, który jest powiązany z pracownikiem, w polu **Menedżer projektu**. Ponadto system tworzy zadanie i przypisuje je do użytkownika, który jest powiązany z pracownikiem wybierany w polu **Właściciel** dla centrum kosztów z projektu. Należy zauważyć, że w tym przykładzie używane jest miejsce powstawania kosztów projektu, a nie miejsce powstawania kosztów zamówienia zakupu.

## <a name="set-up-expenditure-reviewers"></a>Konfigurowanie rewidentów rozchodów

Ten przykład pokazuje, jak skonfigurować recenzenta wydatków zapotrzebowania na zakup. Aby skonfigurować inne typy recenzentów wydatków, zastąp ścieżkę nawigacji w kroku 1 odpowiednią ścieżką z tabeli w sekcji [Rodzaje recenzentów wydatków](configure-expenditure-reviewers.md#types-of-expenditure-reviewers) we wcześniejszej części tego tematu.

1. Przejdź do **Zaopatrzenie i sourcing \> Ustawienia \> Zasady \> Rewidenci wydatków zapotrzebowania na zakup**.
2. Na stronie **Osób sprawdzających wydatki związane z zapotrzebowaniami** na zakup wybierz pozycję **Nowy**.
3. W polu **Nazwa** wprowadź nazwę konfiguracji osoby sprawdzacej wydatki, np. **centrum kosztów**.
4. Na skróconej karcie **Osoby sprawdzające wydatki** według firmy wybierz firmę, która ma zostać skonfigurowana.
5. Aby uzyskać dystrybucję projektu, zaznacz pole wyboru wszystkich organów projektu i wybierz opcję **Tak** dla każdego wymiaru finansowego, który chcesz włączyć. 
6. W przypadku dystrybucji organizacji na karcie **Dystrybucje organizacji** wybierz opcję **Tak** dla każdego wymiaru finansowego, który chcesz włączyć.
7. Powtórz kroki od 4 do 6 dla każdej dodatkowej firmy.

## <a name="assign-owners-to-financial-dimensions"></a>Przypisywanie właścicieli do wymiarów finansowych

Aby przypisać właściciela do wymiaru finansowego, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Księga główna \> Plan kont \>> Wymiary \> Wymiary finansowe**.
2. Z listy wybierz wymiar finansowy, do których chcesz przypisać właścicieli.
3. Wybierz **wartości wymiarów**.
4. Wybierz **pozycję Edytuj**, aby dokonać zmian w wartościach wymiaru.
5. Z listy wybierz wartość wymiaru, do której chcesz przypisać właściciela.
6. W polu **Właściciel** wybierz pracownika, do którego ma zostać przypisana wartość wymiaru.

## <a name="configure-project-distributions"></a>Konfigurowanie dystrybucji projektów

Aby przypisać uprawnienia projektowe do projektu, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie \> Projekty \> Wszystkie projekty**.
2. Wybierz projekt, do który mają być przypisane urzędy.
3. Wybierz **pozycję Edytuj**, aby dokonać zmian w projekcie.
4. Na skróconej karcie **Ogólne**, w sekcji **Osoba odpowiedzialna** wybierz pracownika w polach **Menedżer sprzedaży**, **Menedżer projektu** i **Kontroler projektu** zgodnie z potrzebą.
5. Na skróconej karcie **Wymiary finansowe** wybierz wymagane wymiary finansowe dla projektu.

## <a name="assign-expenditure-reviewers-to-a-workflow-task"></a>Przypisywanie rewidentów rozchodów do zadania w ramach przepływu pracy

W tym przykładzie pokazano, jak skonfigurować przepływ pracy zapotrzebowania zakupu, aby był on używany przez użytkownika sprawdzacego wydatki związane z zapotrzebowaniami zakupu. Aby skonfigurować inne typy przepływów pracy, strona przepływu pracy, która musi zostać otwarta w kroku 1, może znajdować się w module **Zarządzanie wydatkami** lub **Rozrachunki z dostawcami** zamiast modułu **Zaopatrzenie i sourcing**.

Aby przypisać osoby sprawdzające wydatki zapotrzebowania na zakup do zadania przepływu pracy, wykonaj następujące kroki.

1. Przejdź do **Zaopatrzenie i sourcing \> ustawień \> Przepływy pracy modułu Zaopatrzenie i sourcing**.
2. Naciśnij dwukrotnie (lub kliknij dwukrotnie) istniejący przepływ pracy lub utwórz nowy przepływ pracy.
3. W edytorze przepływu pracy w okienku **Przepływ pracy** wybierz zadanie, do których ma zostać przypisana konfiguracja osoby sprawdzacej wydatki. W **okienku akcji**, w grupie **Pokaż**, a następnie wybierz **Właściwości**.
4. W lewym okienku strony **Właściwości** wybierz pozycję **Przypisanie**.
5. Na karcie **Typ przypisania** wybierz pozycję **uczestnik**.
6. Na karcie **Oparte na rolach** w polu **Typ uczestnika** wybierz pozycję **Uczestnicy rozchodów**. W polu **Uczestnik** wybierz konfigurację rewidenta rozchodów, która będzie użyta w zadaniu w ramach przepływu pracy.
