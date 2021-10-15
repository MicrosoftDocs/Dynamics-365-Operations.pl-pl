---
title: Automatyczne zwalnianie wysyłki do przeładunku kompletacyjnego
description: W tym temacie opisano strategię przeładunku kompletacyjnego, która umożliwia automatyczne zwalnianie zamówienia zapotrzebowania do magazynu, gdy zlecenie produkcyjne dostarczające ilość z zapotrzebowania jest zgłaszane jako gotowe, dzięki czemu ilość jest przenoszona bezpośrednio z lokalizacji wyjściowej produkcji do lokalizacji załadunkowej.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 1315bda1fd284eb326d4f08bf36bfea59074fde3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577943"
---
# <a name="auto-release-shipment-for-cross-docking"></a>Automatyczne zwalnianie wysyłki do przeładunku kompletacyjnego

[!include [banner](../includes/banner.md)]

W tym temacie opisano strategię przeładunku kompletacyjnego, która umożliwia automatyczne zwalnianie zamówienia zapotrzebowania do magazynu, gdy zlecenie produkcyjne dostarczające ilość zapotrzebowania jest zgłaszane jako gotowe. W ten sposób ilość wymagana do realizacji zamówienia zapotrzebowania jest przenoszona bezpośrednio z lokalizacji wyjściowej produkcji do lokalizacji załadunkowej.

Przeładunek kompletacyjny to przepływ obsługi magazynu, w którym ilość wymagana do zrealizowania zamówienia wychodzącego jest kierowana do doku załadunkowego zamówienia lub obszaru tymczasowego z lokalizacji, w której zostało odebrane zamówienie przychodzące. (Zamówienie przychodzące może być zamówieniem zakupu, zleceniem przeniesienia lub zleceniem produkcyjnym). Zaawansowana funkcja przeładunku kompletacyjnego obsługuje wszystkie zamówienia podaży i zapotrzebowania oraz wymaga, aby popyt wychodzący został zwolniony przed zidentyfikowaniem możliwości przeładunku kompletacyjnego, a funkcja automatycznego zwalniania wysyłki ma następujące cechy:

- Obsługuje tylko zlecenia produkcyjne jako podaż oraz tylko zamówienia sprzedaży i zamówienia przeniesienia jako popyt.
- Operację przeładunku kompletacyjnego można rozpocząć nawet wtedy, gdy zamówienie zapotrzebowania nie zostało zwolnione do magazynu przed zarejestrowaniem przyjęcia dostawy (czyli przed zgłoszeniem produkcji jako zakończonej)

Ta funkcjonalność przeładunku kompletacyjnego ma dwie zalety:

- Operacje magazynowe mogą pominąć krok odkładania ilości gotowych towarów w zwykłym miejscu magazynu, jeśli ilości te zostaną pobrane ponownie w celu zrealizowania zamówienia wychodzącego. W zamian ilości można przenieść jeden raz, z lokalizacji wyjściowej do lokalizacji pakowania/wysyłki. Dzięki temu funkcja pomaga zminimalizować liczbę operacji obsługi zapasów, a w konsekwencji pomaga zmaksymalizować oszczędność czasu i miejsca w wydziale produkcyjnym magazynu.
- Operacje magazynowe mogą spowodować odroczenie zwolnienia zamówień sprzedaży i zamówień przeniesienia do magazynu, dopóki produkcja wyrobów gotowych dla skojarzonego zlecenia produkcyjnego nie zostanie zgłoszona jako gotowa. Ta korzyść może być szczególnie przydatna w środowiskach produkcji na zamówienie, gdzie czasy realizacji produkcji są przeważnie dłuższe niż czasy realizacji w środowiskach tworzenia zapasów.

## <a name="prerequisites"></a>Wymagania wstępne

| Wymaganie wstępne | Opis |
|---|---|
| Element | Dla danego towaru musi być możliwa obsługa zarządzania magazynem.<p>**Uwaga:** w procesach przeładunku kompletacyjnego nie można uwzględniać towarów z włączoną opcją ilości efektywnej.</p> |
| Magazyn | Musi być możliwe zarządzanie danym magazynem. |
| Szablony przeładunku kompletacyjnego | Dla danego magazynu należy skonfigurować co najmniej jeden szablon przeładunku kompletacyjnego, w którym jest używana zasada zwolnienia popytu **Przy przyjęciu dostawy**. |
| Klasa robocza | Należy utworzyć identyfikator klasy pracy przeładunku kompletacyjnego dla typu zlecenia pracy **Przeładunek kompletacyjny**. |
| Szablony pracy | Szablony pracy z typem zlecenia pracy **Przeładunek kompletacyjny** są wymagane do utworzenia operacji pobrania i odłożenia pracy na potrzeby przeładunku kompletacyjnego. |
| Dyrektywy lokalizacji | Dyrektywy lokalizacji typu zlecenia pracy **Przeładunek kompletacyjny** są wymagane do przeprowadzania odkładania pracy w lokalizacjach, w których ilości zamówień sprzedaży zostaną zapakowane i wysłane. |
| Oznaczenie między zamówieniem zapotrzebowania i zleceniem produkcyjnym | System magazynu może wyzwolić automatyczne zwalnianie wysyłki zamówienia wychodzącego i utworzyć pracę przeładunku kompletacyjnego z lokalizacji wyjściowej w ramach akcji zgłaszania towarów gotowych tylko wtedy, gdy zamówienia sprzedaży i zamówienia przeniesienia zostały zarezerwowane i oznaczone względem zlecenia produkcyjnego. |

## <a name="example-cross-docking-flow"></a>Przykładowy przepływ przeładunku kompletacyjnego

Typowy przepływ przeładunku kompletacyjnego składa się z następujących głównych kroków:

1. Osoba przyjmująca zamówienie sprzedaży tworzy zamówienie sprzedaży dla produktu wytwarzanego na zamówienie. Zazwyczaj żądana ilość nie jest od razu dostępna i najpierw trzeba ją wyprodukować.
2. Osoba przyjmująca zamówienie sprzedaży tworzy zlecenie produkcyjne bezpośrednio z wiersza zamówienia sprzedaży. W ten sposób osoba ta rezerwuje i oznacza ilość w zamówieniu sprzedaży względem ilości w zleceniu produkcyjnym. 

    Alternatywnie planista produkcji określa, że podczas ustalania zamówień planowanych należy zaktualizować oznaczenie.

3. Zlecenie produkcyjne przechodzi przez następujące kroki:

    1. Planista produkcji szacuje i zwalnia zlecenie produkcyjne. (Szacowanie obejmuje rezerwację surowca, a zwolnienie oznacza zwolnienie do magazynu).
    2. Pracownik magazynu rozpoczyna i kończy pobieranie surowca z lokalizacji magazynu do lokalizacji wejściowej produkcji, zgodnie z pracą pobrania produkcji.
    3. Operator w wydziale produkcyjnym rozpoczyna zlecenie produkcyjne.
    4. Podczas ostatniej operacji operator maszyny używa urządzenia przenośnego w celu zgłoszenia zlecenia produkcyjnego jako gotowego.

4. System używa konfiguracji w celu zidentyfikowania zdarzenia przeładunku kompletacyjnego dla dwóch powiązanych zamówień, a następnie wykonuje następujące zadania:

    1. Automatyczne zwolnienie skojarzonego zamówienia sprzedaży do magazynu w celu utworzenia wysyłki.
    2. Automatycznie utworzenie pracy przeładunku kompletacyjnego, która zawiera instrukcje dotyczące pobierania wyrobów gotowych z lokalizacji wyjściowej i przenoszenia ich do lokalizacji wychodzącej, którą dyrektywy lokalizacji przeładunku kompletacyjnego przypisały do zamówienia sprzedaży.
    3. Monitowanie operatora maszyny o zakończenie pracy przeładunku kompletacyjnego bezpośrednio po zgłoszeniu zlecenia produkcyjnego jako gotowego.

5. Po zakończeniu pracy przeładunku kompletacyjnego i załadowaniu ilości do pojazdu, planista w magazynie wychodzącym potwierdza wysyłkę sprzedaży.

## <a name="example-scenario"></a>Przykładowy scenariusz

W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być używana **USMFowa** firma danych demonstracyjnych.

### <a name="set-up-cross-docking-that-uses-the-auto-release-shipment-feature"></a>Konfigurowanie przeładunku kompletacyjnego korzystającego z funkcji automatycznego zwalniania wysyłki

#### <a name="cross-docking-template"></a>Szablon przeładunku kompletacyjnego

1. Przejdź kolejno do pozycji **Zarządzanie magazynem** \> **Ustawienia** \> **Praca** \> **Szablony pracy**.
2. Wybierz pozycję **Nowy**.
3. W polu **Numer sekwencyjny** wprowadź wartość **1**.
4. W polu **Identyfikator szablonu przeładunku kompletacyjnego** wprowadź nazwę, np. **XDock\_ilość zgłoszona jako gotowa**.
5. W polu **Zasady zwolnienia popytu** wybierz pozycję **Przy przyjęciu dostawy**.
6. W polu **Magazyn** wprowadź numer magazynu, w którym chcesz skonfigurować proces przeładunku kompletacyjnego. W tym przykładzie wybierz wartość **51**.

    > [!NOTE]
    > Po wybraniu pozycji **Przy przyjęciu dostawy** jako zasad zwolnienia popytu dla szablonu wszystkie inne pola na stronie staną się niedostępne. Podobnie nie można definiować żadnych źródeł dostawy. To zachowanie występuje, ponieważ przeładunek kompletacyjny, który korzysta z funkcji automatycznego zwalniania wysyłki, obsługuje tylko zlecenia produkcyjne jako źródła dostaw i wymaga, aby istniało oznaczenie między zamówieniami sprzedaży i zleceniami produkcyjnymi. W przypadku wybrania pozycji **Przed przyjęciem dostawy** jako zasad zwolnienia popytu pola na kartach **Planowanie** i **Źródła dostaw** są dostępne i można je edytować.

#### <a name="work-classes"></a>Klasy robocze

1. Przejdź kolejno do pozycji **Zarządzanie magazynem** \> **Ustawienia** \> **Praca** \> **Klasy robocze**.
2. Wybierz pozycję **Nowy**.
3. W polu **Identyfikator klasy pracy** wprowadź nazwę, np. **CrossDock**.
4. W polu **Typ zlecenia pracy** wybierz pozycję **Przeładunek kompletacyjny**.

Aby ograniczyć typy lokalizacji, w których mogą być umieszczane towary gotowe do przeładunku kompletacyjnego, można określić co najmniej jeden prawidłowy typ lokalizacji.

#### <a name="work-templates"></a>Szablony pracy

1. Przejdź do pozycji **Zarządzanie magazynem** \> **Ustawienia** \> **Praca** \> **Szablony pracy**.
2. W polu **Typ zlecenia pracy** wybierz pozycję **Przeładunek kompletacyjny**.
3. Wybierz pozycję **Nowy**.
4. W polu **Numer sekwencyjny** wprowadź wartość **1**.
5. W polu **Szablon pracy** wprowadź nazwę, np. **CrossDock\_51**.
6. Wybierz opcję **Zapisz**.
7. W sekcji **Szczegóły szablonu pracy** wybierz pozycję **Nowe**.
8. W przypadku nowego wiersza w polu **Typ pracy** wybierz pozycję **Pobieranie**. W polu **Identyfikator klasy pracy** wybierz pozycję **Przeładunek kompletacyjny**.
9. Wybierz pozycję **Nowy**.
10. W przypadku nowego wiersza w polu **Typ pracy** wybierz pozycję **Odkładanie**. W polu **Identyfikator klasy pracy** wybierz pozycję **Przeładunek kompletacyjny**.

#### <a name="location-directives"></a>Dyrektywy lokalizacji

Standardowy proces odkładania dla gotowych towarów wymaga dyrektywy lokalizacji **Odłożenie**, aby przeprowadzić proces przenoszenia pobranych ilości produkcji do zwykłego miejsca w magazynie. Podobnie musisz skonfigurować dyrektywę lokalizacji **Odłożenie** przeładunku kompletacyjnego, aby określić, że podczas pracy ilość ukończona ma zostać umieszczona w wyznaczonej lokalizacji wychodzącej, która obsługuje wysyłkę skojarzonego zamówienia sprzedaży.

W przypadku przeładunku kompletacyjnego w odniesieniu do zwykłego odłożenia wyrobów gotowych nie trzeba tworzyć dyrektywy lokalizacji dla akcji pracy pobrania, ponieważ określono lokalizację wyjściową. Ponadto oczekuje się, że ta lokalizacja wyjściowa zostanie skonfigurowana jako domyślna lokalizacja wyjściowa w jednym z rekordów powiązanych z zasobami (takim jak zasób, relacja grupy zasobów lub grupa zasobów) lub jako domyślna lokalizacja wyprodukowanych wyrobów gotowych dla magazynu.

1. Przejdź kolejno do pozycji **Zarządzanie magazynem** \> **Ustawienia** \> **Dyrektywy lokalizacji**.
2. W polu **Typ zlecenia pracy** wybierz pozycję **Przeładunek kompletacyjny**.
3. Wybierz pozycję **Nowy**.
4. W polu **Numer sekwencyjny** wprowadź wartość **1**.
5. W polu **Nazwa** wprowadź nazwę, na przykład **Baydoor**.
6. W polu **Typ pracy** zaznacz opcję **Odłożenie**.
7. W polu **Oddział** wybierz wartość **5**.
8. W polu **Magazyn** wybierz wartość **51**.
9. W skróconej karcie **Wiersze** wybierz pozycję **Nowy**.
10. W polu **Do ilości** wprowadź maksymalną ilość z zakresu, na przykład **1000000**.
11. Wybierz opcję **Zapisz**.
12. Na skróconej karcie **Akcje dyrektyw lokalizacji** wybierz pozycję **Nowa**.
13. W polu **Nazwa** wprowadź nazwę, na przykład **Baydoor**.
14. Wybierz opcję **Zapisz**.
15. Można również użyć standardowej funkcji zapytań, aby ograniczyć lokalizacje odkładania do jednej lub wielu konkretnych lokalizacji. Wybierz pozycję **Edytuj zapytanie**, a następnie wybierz wartość **51** jako kryterium dla pola **Magazyn** w tabeli **Lokalizacje**.

### <a name="cross-dock-finished-goods-to-the-outbound-location"></a>Towary gotowe do przeładunku kompletacyjnego w lokalizacji wychodzącej

Aby przeprowadzić przeładunek kompletacyjny ilości towarów gotowych do lokalizacji wychodzącej skojarzonej z zamówieniem sprzedaży, wykonaj następujące kroki.

1. Przejdź kolejno do pozycji **Sprzedaż i marketing** \> **Zamówienia sprzedaży** \> **Wszystkie zamówienia sprzedaży**.
2. Wybierz pozycję **Nowy**.
3. W przypadku nagłówka zamówienia sprzedaży wybierz konto klienta **US-001** oraz magazyn skonfigurowany do przeładunku kompletacyjnego, w którym jest używana funkcja automatycznego zwalniania wysyłki.
4. Dodaj wiersz dla gotowego produktu i wprowadź **10** jako ilość.
5. W sekcji **Wiersze zamówienia sprzedaży** wybierz pozycję **Produkt i dostawa** \> **Zlecenie produkcyjne**.
6. W oknie dialogowym **Tworzenie zlecenia produkcyjnego** przejrzyj wartości domyślne, a następnie wybierz pozycję **Utwórz**. Nowe zlecenie produkcyjne zostanie utworzone i połączone z zamówieniem sprzedaży (czyli zarezerwowane i oznaczone).
7. Opcjonalnie: zmień wartość w polu **Ilość**, tak aby była większa niż wartość wymagana do zrealizowania zamówienia sprzedaży. Jeśli ilość produkcji zostanie zgłoszona jako gotowa, system utworzy pracę przeładunku kompletacyjnego dla oznaczonej ilości i pracy odłożenia dla pozostałej ilości, zgodnie z normalną procedurą obsługi odłożenia wyrobów gotowych.

    Jak wspomniano wcześniej, musi istnieć oznaczenie między zamówieniem sprzedaży i zleceniem produkcyjnym. W przeciwnym razie przeładunek kompletacyjny nie będzie działać. Oznaczenie można utworzyć na wiele sposobów:

    - System może automatycznie utworzyć to oznaczenie w następujących sytuacjach:

        - Zlecenie produkcyjne jest tworzone bezpośrednio z wiersza zamówienia sprzedaży (zobacz krok 6).
        - Planowane zlecenia produkcyjne są akceptowane, a pole **Aktualizacja oznaczenia** jest ustawiane na wartość **Standardowa**.

    - Użytkownik może ręcznie utworzyć oznaczenie, otwierając stronę **Oznaczenie** z wiersza zamówienia zapotrzebowania.

    > [!NOTE]
    > Oznaczenia nie można ręcznie utworzyć dla towarów skonfigurowanych tak, aby używały średniej standardowej i ważonej jako modeli zapasów.

8. Na stronie **Zlecenie produkcyjne**, w okienku akcji, na karcie **Zlecenie produkcyjne**, w grupie **Proces** wybierz pozycję **Szacowanie**, a następnie kliknij przycisk **OK**. Zlecenie zostanie oszacowane, a ilość surowca — zarezerwowana na potrzeby produkcji.
9. W okienku akcji, na karcie **Zlecenie produkcyjne**, w grupie **Proces** wybierz pozycję **Zwolnienie**, a następnie kliknij przycisk **OK**. Dla surowców zostanie utworzona praca pobrania z magazynu.
10. Otwórz i przejrzyj pracę. W okienku akcji, na karcie **Magazyn**, w grupie **Ogólne** wybierz pozycję **Szczegóły pracy**. Zanotuj identyfikator pracy.
11. Zaloguj się do aplikacji Warehouse Management, aby uruchomić pracę w magazynie 51.
12. Przejdź do pozycji **Produkcja** \> **Pobranie produkcji**.
13. Wprowadź identyfikator pracy w celu rozpoczęcia i ukończenia pobierania surowca. 

    Po zgłoszeniu pracy jako zakończonej ilość surowca jest dostępna w lokalizacji wejściowej produkcji (**005** w danych demonstracyjnych USMF), a wykonywanie zlecenia produkcyjnego może się rozpocząć.

14. Na stronie **Zlecenie produkcyjne**, w okienku akcji, na karcie **Zlecenie produkcyjne**, w grupie **Proces** wybierz pozycję **Uruchom**, a następnie wybierz przycisk **OK**.
15. W aplikacji przejdź do pozycji **Produkcja** \> **Ilość zgłoszona jako gotowa i odłożenie**.
16. W polu **Identyfikator produktu** wprowadź numer zlecenia produkcyjnego i inne wymagane szczegóły, a następnie wybierz przycisk **OK**.

Zwróć uwagę na następujące zachodzące zdarzenia:

- Zwolnienie do magazynu jest wyzwalane dla połączonego zamówienia sprzedaży.
- Praca obejmująca wysyłkę i przeładunek kompletacyjny jest tworzona na podstawie zwolnienia. Ta praca instruuje operatora magazynu, że powinien pobrać ilości wymagane do zrealizowania wiersza zamówienia sprzedaży i umieścić je w lokalizacji wychodzącej określonej w dyrektywie lokalizacji przeładunku kompletacyjnego.
- Jeśli ilość w zleceniu produkcyjnym jest większa niż ilość wymagana przez zamówienie sprzedaży, jest tworzona zwykła praca odłożenia. Ta praca instruuje operatora magazynu, że powinien pobrać ilość wyrobów gotowych pozostałą po przeładunku kompletacyjnym i przenieść ją do zwykłego magazynu zgodnie z dyrektywą lokalizacji.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]