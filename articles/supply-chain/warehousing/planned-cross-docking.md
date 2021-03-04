---
title: Planowany przeładunek kompletacyjny
description: W tym temacie opisano zaawansowane planowane przeładunki kompletacyjne, w którym ilość zapasów wymagana dla zamówienia jest skierowana bezpośrednio z paragonu lub tworzenia do właściwego doku załadunkowego lub obszaru tymczasowego. Wszystkie pozostałe zapasy ze źródła przychodzącego są kierowane do poprawnego miejsca przechowywania za pośrednictwem zwykłego procesu umieszczenia.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: cc217f21a5fa70feb9ef9161f3ef2e2b6a333f35
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435623"
---
# <a name="planned-cross-docking"></a>Planowany przeładunek kompletacyjny

[!include [banner](../includes/banner.md)]

W tym temacie opisano zaawansowany planowany przeładunek kompletacyjny. Zaawansowany planowany przeładunek kompletacyjny to proces magazynowy, w którym ilość zapasów wymagana dla zamówienia jest skierowana bezpośrednio z paragonu lub tworzenia do właściwego doku załadunkowego lub obszaru tymczasowego. Wszystkie pozostałe zapasy ze źródła przychodzącego są kierowane do poprawnego miejsca przechowywania za pośrednictwem zwykłego procesu umieszczenia.

Proces ten pozwala pracownikom pominąć przychodzące umieszczenia i pobrania wychodzące zapasów, które są już oznaczone dla zamówienia wychodzącego. Z tego względu liczba przypadków, gdy zapasy są poruszane, jest zminimalizowana, jeśli to możliwe. Ponadto, ponieważ mniejsza jest interakcja z systemem, wzrasta oszczędność czasu i miejsca w ramach produkcji magazynowej.

Aby można było uruchomić przeładunek kompletacyjny, użytkownik musi skonfigurować nowy szablon przeładunku kompletacyjnego, w którym określono źródło dostaw i inne zestawy wymagań. Po utworzeniu zamówienia wychodzącego wiersz musi być zaznaczony względem zamówienia przychodzącego, które zawiera ten sam towar.

W momencie przyjęcia zamówienia przychodzącego konfiguracja przeładunku kompletacyjnego automatycznie identyfikuje potrzebę przeładunku kompletacyjnego i tworzy pracę dla wymaganej ilości w oparciu o konfigurację dyrektywy lokalizacji.

> [!NOTE]
> Transakcje magazynowe **nie są** rejestrowane, gdy praca przeładunku kompletacyjnego została anulowana, nawet jeśli ustawienie tej funkcji jest włączone w parametrach zarządzania magazynem.

## <a name="turn-on-the-planned-cross-docking-feature"></a>Włącz funkcję planowanego przeładunku kompletacyjnego

Aby można było korzystać z funkcji zaawansowanego planowanego przeładunku kompletacyjnego, funkcja ta musi być włączona w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Planowany zaawansowany przeładunek kompletacyjnego*

## <a name="setup"></a>Konfiguracja

### <a name="regenerate-load-posting-methods"></a>Ponowne generowanie metod księgowania ładunku

Planowany przeładunek kompletacyjny jest implementowany jako metoda księgowania ładunku. Po włączeniu funkcji należy ponownie wygenerować metody.

1. Przejdź do **Zarządzania magazynem \> Konfiguracja \> Metody księgowania ładunku**.
1. W okienku akcji wybierz pozycję **Ponownie utwórz metody**.

    Po zakończeniu ponownego generowania powinna być widoczna metoda, która ma wartość **Nazwa metody** *planCrossDocking*.

1. Zamknij stronę.

### <a name="create-a-cross-docking-template"></a>Tworzenie szablonu przeładunku kompletacyjnego

1. Przejdź kolejno do pozycji **Zarządzanie magazynem \> Konfiguracja \> Praca \> Szablony przeładunku kompletacyjnego**.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć szablon.
1. W nagłówku ustaw następujące wartości:

    - **Sekwencja:** *1*

        To pole określa kolejność, w jakiej są oceniane szablony.

    - **Identyfikator szablonu przeładunku kompletacyjnego** *51*
    - **Opis:** *Magazyn 51*
    - **Zasady zwalniania popytu** *Przed przyjęciem dostawy*
    - **Magazyn:** *51*

1. Konfiguracja na skróconej karcie **Planowanie** decyduje o sposobie działania szablonu. Ustaw następujące wartości:

    - **Wymagania dotyczące popytu:** *Brak*

        To pole definiuje wymagania dotyczące zapasów zapotrzebowania. Jeśli zapotrzebowanie musi być połączone z dostawą przed zwolnieniem, wybierz opcję *Zaznaczenie*. Jeśli zapotrzebowanie musi być zarezerwowane na podstawie zamówienia przed zwolnieniem, wybierz opcję *Rezerwacja zamówienia*.

    - **Lokalizowanie typu:** *Lokalizacje wysyłki*

        To pole określa, czy w ramach pracy przeładunku kompletacyjnego powinny być używane lokalizacje pośredniego/ładunku z wysyłki, czy też mają być używane dyrektywy lokalizacji w celu znalezienia własnych lokalizacji przemieszczania/ładunku.

    - **Szablon pracy:** Pozostaw to pole puste.

        To pole definiuje szablon pracy, który ma być używany podczas tworzenia przeładunku kompletacyjnego.

    - **Sprawdź ponownie na paragonie dostawy:** *Nie*

        Ta opcja umożliwia zdefiniowanie, czy dostawa ma zostać sprawdzona ponownie podczas przyjęcia. Jeśli ta opcja ma wartość *Tak*, sprawdzane są zarówno maksymalne przedziały czasu, jak i zakres daty ważności.

    - **Sprawdzanie poprawności – okno czasowe:** *Tak*

        Ta opcja służy do definiowania, czy w przypadku wybrania źródła dostaw ma być oceniany maksymalny przedział czasu. Jeśli ta opcja ma wartość *Tak*, pola związane z maksymalnym i minimalnym okienkiem czasowym staną się dostępne.

    - **Okienko czasu maksymalnego:** *5*

        To pole określa maksymalny dopuszczalny okres między pojawieniem się dostawy a wysłaniem zapotrzebowania.

    - **Maksymalna jednostka okna czasu:** *Dni*
    - **Okienko czasu minimalnego:** *0*

        To pole określa minimalny dopuszczalny okres między pojawieniem się dostawy a wysłaniem zapotrzebowania.

    - **Minimalna jednostka okna czasu:** *Dni*
    - **Zakres dni daty ważności:** *0*

        *Kryterium pierwsze do wygaśnięcia – pierwsze do wyjścia (FEFO):* to pole określa maksymalną liczbę dni między datą ważności pierwszej partii, która znajduje się obecnie w magazynie a otrzymaną partią.

1. Na skróconej karcie **Źródła dostaw** można określić typy dostaw, które są prawidłowe dla tego szablonu. Wybierz opcję **Nowe**, a następnie określ następujące wartości:

    - **Numer sekwencyjny:** *1*
    - **Źródło dostawy:** *Zamówienie zakupu*

### <a name="create-a-work-class"></a>Tworzenie klasy roboczej

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć klasę roboczą.
1. Ustaw następujące wartości:

    - **Identyfikator klasy roboczej:** *CrossDock*
    - **Opis:** *Przeładunek kompletacyjny*
    - **Typ zlecenia pracy:** *Przeładunek kompletacyjny*

### <a name="create-a-work-template"></a>Tworzenie szablonu pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. W polu **Typ zlecenia pracy** ustaw pozycję *Przeładunek kompletacyjny*.
1. W okienku akcji wybierz opcję **Nowe**, aby dodać nowy wiersz do karty **Przegląd**.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer sekwencyjny:** *1*
    - **Szablon pracy** *51 Cross Dock*
    - **Opis szablonu pracy** *51 Przeładunek kompletacyjny*

1. Wybierz opcję **Zapisz**, aby skrócona karta **Szczegóły szablonu pracy** stała się dostępna.
1. Na skróconej karcie **Szczegółów dot. szablonu pracy** wybierz opcję **Nowy**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Typ pracy:** *Pobranie*
    - **Identyfikator klasy roboczej:** *CrossDock*

1. Wybierz polecenie **Nowy**, aby dodać dodatkowy wiersz i określ następujące wartości:

    - **Typ pracy:** *Odłożenie*
    - **Identyfikator klasy roboczej:** *CrossDock*

1. Wybierz opcję **Zapisz** i upewnij się, że zaznaczono pole wyboru **Prawidłowe** dla szablonu *51 Cross Dock*.

> [!NOTE]
> Identyfikatory klas roboczych dla typów pracy *Pobranie* i *Umieszczenie* muszą być takie same.

### <a name="create-location-directives"></a>Tworzenie dyrektyw lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W lewym okienku w polu **Typ zlecenia produkcyjnego** ustaw wartość na *Przeładunek kompletacyjny*.
1. Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:

    - **Numer sekwencyjny:** *1*
    - **Nazwa:** *51 Cross Dock Put*
    - **Typ pracy:** *Odłożenie*
    - **Oddział:** *5*
    - **Magazyn:** *51*

1. Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.
1. Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Od ilości:** *1*
    - **Do ilości:** *1000000*

1. Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.
1. Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Nazwa:** *Baydoor*
    - **Stałe użycie lokalizacji:** *Stałe i niestałe lokalizacje*

1. Wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę** na pasku **Dyrektywy akcji lokalizacji**.
1. Wybierz opcję **Edytuj kwerendę**, aby otworzyć edytor kwerend.
1. Na karcie **Zakres** upewnij się, że skonfigurowano dwa następujące wiersze:

    - Wiersz 1:

        - **Tabela:** *Lokalizacje*
        - **Tabela pochodna:** *Lokalizacje*
        - **Pole:** *Magazyn*
        - **Kryteria:** *51*

    - Wiersz 2:

        - **Tabela:** *Lokalizacje*
        - **Tabela pochodna:** *Lokalizacje*
        - **Pole:** *Lokalizacja*
        - **Kryteria:** *Baydoor*

1. Kliknij przycisk **OK**, aby zamknąć edytor.

### <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Na liście elementów menu w lewym okienku wybierz pozycję **Umieszczenie zakupu**.
1. Wybierz opcję **Edycja**.
1. Na skróconej karcie **Klasy robocze** wybierz **Nowe**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Identyfikator klasy roboczej:** *CrossDock*
    - **Typ zlecenia pracy:** *Przeładunek kompletacyjny*

1. Wybierz opcję **Zapisz**.

## <a name="scenario"></a>Scenariusz

### <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

Aby utworzyć zamówienie zakupu jako źródło podaży, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:

    - **Konto dostawcy:** *104*
    - **Magazyn:** *51*

1. Wybierz **OK** i zanotuj numer zamówienia.
1. Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia zakupu**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *5*

### <a name="create-a-sales-order"></a>Utwórz zamówienie sprzedaży

Aby utworzyć zamówienie sprzedaży jako źródło popytu, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-002*
    - **Magazyn:** *51*

1. Kliknij przycisk **OK**.
1. Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *3*

### <a name="create-planned-cross-docking"></a>Utwórz planowany przeładunek kompletacyjny

Aby utworzyć planowany przeładunek kompletacyjny na podstawie zamówienia sprzedaży, należy wykonać poniższe kroki.

1. Na stronie **Szczegóły zamówienia sprzedaży** dla utworzonego właśnie zamówienia sprzedaży w okienku akcji na karcie **Magazyn** w grupie **Akcje**, wybierz opcję **Zwolnienie do magazynu**.

    Akcja zwolnienie do magazynu powoduje utworzenie wiersza wysyłki i ładunku dla wiersza zamówienia sprzedaży i próbuje alokować zapasy.
    
    Zostanie wyświetlony komunikat informacyjny. Pojawia się także następujący komunikat ostrzegawczy: „Nie utworzono żadnej pracy dla grupy czynności XXXX. Aby uzyskać szczegółowe informacje, zajrzyj do dziennika historii tworzenia pracy”. Takie zachowanie jest oczekiwane, ponieważ w magazynie nie ma zapasów.

1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Magazyn** wybierz opcję **Szczegóły wysyłki**.

    Zostanie wyświetlona strona **Szczegóły wysyłki**, która została utworzona dla danego wiersza sprzedaży.

1. Na skróconej karcie **Wiersze ładunku**, w **Planowana ilość dla przeładunku kompletacyjnego** powinna być ustawiona wartość *3*. Ponieważ w magazynie nie było dostępnych zapasów, ale podano prawidłowe źródło dostaw w oknie czasu zdefiniowanym w szablonie przeładunku kompletacyjnego, zostanie utworzona ilość przeładunku kompletacyjnego.
1. Na skróconej karcie **Wiersze ładunku** wybierz opcję **Planowany przeładunek kompletacyjny**, aby wyświetlić szczegóły utworzonego przeładunku kompletacyjnego.

## <a name="process-the-cross-docking"></a>Przetwórz przeładunek kompletacyjny

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a>Zlecenie zakupu otrzymane na mobilnej aplikacji magazynowej

System otrzyma ilość 5 od zamówienia zakupu w lokalizacji przyjęcia i utworzy dwie sztuki pracy.

Pierwszy utworzony identyfikator pracy ma wartość **Typ zlecenia pracy** *Przeładunek kompletacyjny* i jest połączony z zamówieniem sprzedaży. Ma ilość 3 i jest kierowana do ostatecznej lokalizacji wysyłki, dzięki czemu można ją wysłać natychmiast.

Drugi utworzony identyfikator pracy ma wartość **Typ zlecenia pracy** *Zlecenie zakupu* i jest połączony z zamówieniem zakupu. Ta wartość ma pozostałą ilość 2, która nie została zadokowana i jest kierowana do umieszczenia w magazynie.

1. Zaloguj się do urządzenia przenośnego jako użytkownik w magazynie *51*.
1. Przejdź do **Przychodzące \> Przyjęcia zakupu**.
1. W polu **PONum** wprowadź numer zamówienia zakupu.
1. W polu **Ilość** wpisz wartość *5*.
1. Kliknij przycisk **OK**.
1. Na następnej stronie w polu **Pozycja** wpisz *A0001*.
1. Kliknij przycisk **OK**.
1. Na następnej stronie potwierdź wartości **PONum**, **Pozycja** oraz **Ilość** klikając **OK**.

    Zostanie wyświetlony komunikat „Praca zakończona”.

1. Wybierz **Anuluj**, aby wyjść.

### <a name="put-away-to-cross-docking-and-bulk"></a>Umieszczenie do przeładunku kompletacyjnego i sprzedaży zbiorczej

Obecnie oba identyfikatory pracy mają taki sam docelowy numer identyfikacyjny. Aby wykonać kolejne kroki, należy uzyskać identyfikator pracy i identyfikator docelowego numeru identyfikacyjnego. Informacje te można uzyskać ze szczegółów pracy dla wiersza zamówienia zakupu oraz dla wiersza zamówienia sprzedaży. Alternatywnie można przejść do **Zarządzanie magazynem \> Praca \> Szczegóły pracy** i odfiltrować wyniki dla wartości **Magazyn** *51*.

1. Na urządzeniu przenośnym przejdź do **Przychodzące \> Umieszczenie zakupu** i wprowadź docelowy numer identyfikacyjny pracy.
1. W polu **Identyfikator** wprowadź docelowy numer identyfikacyjny ze szczegółów dot. pracy.

    Na stronie pobranie przeładunku kompletacyjnego jest wyświetlana lokalizacja pobrania (*RECV*), docelowy numer identyfikacyjny (*numer identyfikacyjny*), pozycja (*A0001*) oraz ilość (*3*).

1. Kliknij przycisk **OK**.
1. W polu **Docelowy num. id.** wprowadź docelowy numer identyfikacyjny dla identyfikatora numeru identyfikacyjnego, który ma zostać umieszczony (przeładunek kompletacyjny) w lokalizacji wysyłki. Możesz wybrać dowolny identyfikator numeru identyfikacyjnego.
1. Kliknij przycisk **OK**.
1. Na następnej stronie, w polu **Identyfikator** wprowadź docelowy numer identyfikacyjny ze szczegółów dot. pracy.
1. Kliknij przycisk **OK**.
1. Potwierdź pracę w celu pobrania pozostałej ilości w wys. 2, a następnie kliknij przycisk **OK**.
1. Na następnej stronie wybierz opcję **Gotowe**, aby zakończyć proces pobierania i rozpocząć proces umieszczenia.

    Aplikacja mobilna zawiera adres i numer identyfikacyjny, w którym ma zostać umieszczony towar.

1. Potwierdź masowe przechowywanie **Umieść**, klikając **OK**.
1. Na następnej stronie potwierdź przeładunek kompletacyjny **Umieść**, klikając **OK**.

    Zostanie wyświetlony komunikat „Praca zakończona”.

1. Wybierz **Anuluj**, aby wyjść.

Na poniższej ilustracji przedstawiono sposób ukończenia pracy przeładunku kompletacyjnego w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.

![Praca przeładunku kompletacyjnego została zakończona](media/PlannedCrossDockingWork.png "Praca przeładunku kompletacyjnego została zakończona")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]