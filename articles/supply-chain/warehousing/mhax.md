---
title: Interfejs urządzeń do obsługi materiałów (MHAX)
description: W tym artykule opisano, jak skonfigurować interfejs sprzętu do obsługi materiałów (MHAX), aby można było połączyć się z zewnętrznymi fizycznymi systemami obsługi materiałów (MH).
author: Mirzaab
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMHEParameters, WMHESubscription, WMHEQueueManagerWorkspace, WMHEInboundQueue, WMHEOutboundQueue
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: dc46c9fea94c3d86f9511c2bea4ea64455c936f9
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068368"
---
# <a name="material-handling-equipment-interface-mhax"></a>Interfejs urządzeń do obsługi materiałów (MHAX)

[!include [banner](../../includes/banner.md)]

Interfejs *urządzeń do obsługi materiałów* (MHAX) umożliwia połączenie zewnętrznych systemów obsługi fizycznego materiału (MH) z magazynem zarządzanym przez procesy zarządzania magazynem (WMS) w Microsoft Dynamics 365 Supply Chain Management. Interfejs między systemami WMS i MH składa się z dwóch kolejek: jednej dla zdarzeń wychodzących (WMS do MH) i jednej dla zdarzeń przychodzących (MH do WMS). System WMS generuje zdarzenia wychodzące na podstawie linii roboczych, które są tworzone podczas różnych procesów tworzenia i wykonywania pracy. Następnie system MH regularnie odpytuje system WMS o nowe zdarzenia i przetwarza odpowiedzi. Po zakończeniu obsługi zdarzeń zgodnie z instrukcją pracy system MH wysyła zdarzenia przychodzące, takie jak kompletacja linii roboczych i krótka kompletacja.

Na poniższej ilustracji przedstawiono różne elementy i kolejność, w jakiej występują procesy podczas korzystania z integracji MHAX.

![Składniki i interakcje MHAX.](media/mhax-components.png "Składniki i interakcje MHAX")

Oto wyjaśnienie interakcji widocznych na poprzedniej ilustracji:

1. Podczas tworzenia pracy lub wykonywania pracy zdarzenia wychodzące są tworzone w kolejce wychodzącej.
2. Sprzęt MH łączy się z serwisem sprzętu MH, odpytuje o wszelkie nowe zdarzenia, które są dla niego istotne, i przetwarza te zdarzenia.
3. Gdy sprzęt MH jest gotowy do zgłoszenia zwrotnego, ponownie łączy się z usługą i przesyła zdarzenia przychodzące. Te zdarzenia są natychmiast przetwarzane przez procesor kolejek.
4. Na podstawie danych o zdarzeniach przychodzących procesor kolejek może uruchamiać istniejącą pracę, modyfikować ją lub tworzyć nową pracę.

## <a name="turn-on-the-mhax-feature"></a>Włączanie funkcji MHAX

Aby można było używać funkcji MHAX, należy włączyć zarówno funkcję, jak i klucz konfiguracji.

1. Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.
2. W obszarze roboczym **[Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** włącz funkcję o nazwie *Interfejs urządzeń do obsługi materiałów*.
3. Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
4. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.
5. Rozwiń **Handel \> Zarządzanie magazynem i transportem**, a następnie zaznacz pole wyboru **Interfejs urządzeń do obsługi materiałów**.
6. Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

## <a name="set-mhax-parameters"></a>Ustawianie parametrów MHAX

Aby skonfigurować tę funkcję, trzeba ustawić kilka ogólnych parametrów na stronie **Parametry interfejsu urządzeń do obsługi materiałów**.

1. Przejdź do **Interfejs urządzeń do obsługi materiałów \> Konfiguracja \> Parametry interfejsu urządzeń do obsługi materiałów**.
2. Na karcie **Ogólne** ustaw następujące pola:

    - **Identyfikator użytkownika** – wybierz pracownika. Ten proces roboczy będzie używany do uruchamiania wszystkich operacji roboczych (wybierania i wysyłania), które są przetwarzane przez kolejkę przychodzącą.
    - **Włącz identyfikator wiadomości przychodzącej** — jeśli dla tej opcji jest ustawiona wartość *Tak*, jeśli odebrano zduplikowany identyfikator wiadomości przychodzącej, wiadomość zostanie odrzucona, a komunikat o błędzie będzie oznaczał, że wiadomość już istnieje. Gdy ta opcja ma wartość *Nie*, są dozwolone zduplikowane identyfikatory wiadomości przychodzących.

3. Na karcie **Sekwencje numerów** wybierz sekwencje numerów na całym systemie, które powinny być używane do generowania unikatowych identyfikatorów dla elementów kolejki przychodzącej, elementów kolejki wychodzącej i par wiersza pracy.

## <a name="outbound-events"></a>Zdarzenia wychodzące

W określonych momentach tworzenia lub wykonywania pracy system określa, czy musi generować zdarzenia wychodzące w celu przesłania do systemu MH. Jeśli subskrypcja jest skonfigurowana dla określonego punktu podczas przetwarzania magazynu, system wygeneruje zdarzenie zgodnie z konfiguracją subskrypcji.

### <a name="structure-of-outbound-events"></a>Struktura zdarzeń wychodzących

Każde zdarzenie wychodzące jest jednoznacznie identyfikowane przez identyfikator kolejki wychodzącej. Typ transakcji wychodzącej określa typ zdarzenia. W zdarzeniu jest również rejestrowany magazyn i identyfikator subskrypcji, która wygenerowała zdarzenie.

Do przenoszenia danych do systemu MH zdarzenie wychodzące zawiera 10 pól danych (od **data01** do **data10**). Pola te mają mapowanie jeden do jednego (1:1) do istniejących pól bazy danych. W szczególności są wyodrębnione z pól w wierszu pracy i tabelach nagłówka pracy. Pola można wybierać swobodnie. Są ustawiane podczas tworzenia subskrypcji.

Oprócz pól danych 10, które mają mapowanie 1:1 na istniejące pola bazy danych, zdarzenie może zawierać dodatkowe pole danych zwane *ładunkiem*. Zawartość tego pola jest generowana przez niestandardowy kod X++, który jest znany jako *generator ładunku*. Każdy generator ładunków, który powinien zostać użyty, jest ustawiony w subskrypcji.

Aby system MH odbierał każdy identyfikator kolejki wychodzącej tylko raz, w polu statusu określa się, czy zdarzenie jest gotowe do wysłania do systemu zewnętrznego, czy też zostało już wysłane.

### <a name="outbound-queue-subscriptions"></a>Subskrypcje kolejek wychodzących

Przed wygenerowaniem zdarzeń należy skonfigurować subskrypcję, aby poinformować funkcję MHAX o tym, czy i w jaki sposób mają być generowane zdarzenia. Wygenerowane zdarzenia są oznakowane przez identyfikator subskrypcji. Z tego względu wiele systemów MH może łączyć się z tym samym systemem WMS, ale zachować osobne zdarzenia. Podczas wyszukiwania nowych zdarzeń usługa MHAX jest jedną z dostępnych opcji pobierania zdarzeń.

Aby utworzyć subskrypcję, przejdź do **Interfejs urządzeń do obsługi materiałów \> Konfiguracja \> Subskrypcje**. Dla każdej subskrypcji są dostępne następujące parametry:

- **Identyfikator subskrypcji** — unikatowa nazwa identyfikująca subskrypcję.
- **Opis** – Dowolny opis subskrypcji.
- **Magazyn** — określone magazyny, według których powinny być filtrowane zdarzenia.
- **Typ transakcji wychodzącej** — typ zdarzeń, które powinna zawierać subskrypcja.
- **Generator ładunku** — opcjonalne rozszerzenie kodu, które może wprowadzać dodatkowe informacje w polu **Ładunek** dla zdarzenia wychodzącego.

Kwerendę można skojarzyć z każdą subskrypcją. To zapytanie filtruje wiersze pracy i nagłówki, aby dodatkowo ograniczyć pracę, która będzie używać subskrypcji do generowania zdarzeń. Aby dodać kwerendę do subskrypcji, zaznacz pole wyboru **Uruchom kwerendę** dla odpowiedniej subskrypcji na stronie **Subskrypcje**, a następnie wybierz w okienku akcji opcję **Edytuj kwerendę**. Zostanie wyświetlony standardowy edytor kwerend Supply Chain Management.

Ponadto subskrypcja zawiera *mapę subskrypcji*, która mapuje pola z nagłówka pracy lub wiersza pracy do niektórych lub wszystkich 10 wolnych pól danych zdarzenia wychodzącego (zgodnie z potrzebą). Aby zwrócić informacje do usługi MHAX, zazwyczaj jest używany identyfikator rekordu wiersza pracy lub *identyfikator pary wiersza pracy*. (Identyfikator pary linii roboczych to nowa właściwość, która umożliwia systemowi użycie pojedynczego polecenia powrotu do przetwarzania wierszy pobierania i umieszczania). Pozostałe pola zależą od przypadku użycia. Podano kilka przykładów dalej w tym artykule.

Aby skonfigurować mapę subskrypcji, wybierz odpowiednią subskrypcję na stronie **Subskrypcje**, a następnie wybierz pozycję **Mapa subskrypcji** w okienku akcji. W wyświetlonym oknie dialogowym **Mapa subskrypcji** można przypisać tabelę i pole do każdego wymaganego pola danych.

### <a name="outbound-event-types"></a>Typy zdarzeń wychodzących

W tej sekcji opisano różne dostępne typy zdarzeń. (Typy zdarzeń są nazywane także *typami transakcji*.) Wyjaśniono w nim także, kiedy w systemie WMS są tworzone poszczególne typy zdarzeń.

#### <a name="work-creation-events"></a>Zdarzenia tworzenia pracy

Zdarzenia tworzenia pracy są tworzone po wygenerowaniu pracy przez aplikację. To działanie dotyczy większości typów procesów tworzenia pracy, z których większość dotyczy tworzenia pracy pobierania i uzupełniania zapasów. Ogólnie, jeśli praca została utworzona w stanie *Otwarte*, co wskazuje, że praca jest gotowa do uruchomienia przez pracownika, zostanie wygenerowane zdarzenie tworzenia pracy. Ponadto zdarzenia tworzenia pracy będą generowane dla podstawowej pracy dotyczącej ruchu (a nie przemieszczania według pracy szablonu), nawet jeśli ta praca nie została utworzona jako otwarta praca.

Wyjątkiem tego zachowania jest praca inwentaryzacji cyklicznej, która nie jest obecnie obsługiwana. Inwentaryzacje w systemie MH są poza zakresem MHAX i należy zaimportować wyniki inwentaryzacji do arkusza zliczania zapasów.

Po utworzeniu pracy usługa MHAX przetwarza wygenerowane wiersze pracy i przypisuje identyfikator pary wierszy pracy do wszystkich generowanych wierszy pracy dla każdego nagłówka pracy. Celem jest zgrupowanie wszystkich linii roboczych pobrania z kolejnymi pozycjami pod jednym identyfikatorem pary linii roboczych. (Grupy odpowiadają parom pobrania / odłóż w szablonach pracy). W ten sposób pojedynczy identyfikator może być używany do raportowania zakończenia pracy dla wszystkich powiązanych linii pobrania i umieszczenia. Proces grupowania rozpoczyna się od pierwszego wiersza, a następnie jest kontynuowany z tym samym identyfikatorem, aż napotka kolejną parę wierszy roboczych typu odłożyć/pobrać. Działający identyfikator jest przypisywany do linii put tej pary. Nowy identyfikator, który zostanie użyty jako wiersz pobrania dla pary od nowa. Ten proces trwa do momentu przetworzenia wszystkich wierszy należących do nagłówka pracy.

Jako specjalna funkcja zdarzeń tworzenia pracy, jeśli w nagłówku pracy jako opcja **Zablokowano grupy czynności** jest ustawiona wartość *Tak*, generowane zdarzenia będą mieć stan *Zablokowane* zamiast zwykłego stanu *Gotowe*, który jest używany do wysyłania ich do systemu MH. Flaga **Zablokowana grupy czynności** w nagłówku pracy wskazuje, że nagłówek pracy nie jest jeszcze gotowy do uruchomienia przez pracowników, być może z powodu niezakończonej pracy uzupełniania zapasów. Po wyczyszczeniu flagi **Zablokowana grupy czynności** zdarzenia, które zostały już wygenerowane, są odblokowane i są dostępne do pobrania z kolejki przez system MH.

#### <a name="work-initiation-events"></a>Wydarzenia inicjujące pracę

Zdarzenia inicjacji pracy są wyzwalane, gdy stan pracy zmienia się z *Otwarte* na *W trakcie* podczas aktualizacji pracy.

#### <a name="work-completion-events"></a>Zdarzenia ukończenia pracy

Zdarzenia zakończenia pracy są wyzwalane, gdy stan pracy zmienia się z *W trakcie* na *Zamknięte* podczas aktualizacji pracy.

#### <a name="work-cancellation-events"></a>Zdarzenia anulowania pracy

Zdarzenia anulowania pracy są wyzwalane, gdy stan pracy zmienia się z jakiegokolwiek statusu poza *Anulowano* na *Anulowano* podczas aktualizacji pracy. Ponadto wszystkie inne zdarzenia związane z nagłówkiem pracy są usuwane z kolejki dla wszystkich subskrypcji. W ten sposób zewnętrzne systemy nie mogą przetwarzać zdarzeń, które nie są wymagane.

#### <a name="pickput-completion-events"></a>Wydarzenia związane z zakończeniem pobierania / odłożenia

Zdarzenia zakończenia pobierania/odłożenia są wyzwalane, gdy stan wiersza pobierania/odłożenia zmienia się z *W trakcie* na *Zamknięte* podczas aktualizacji wiersza pracy.

### <a name="monitor-the-outbound-queue"></a>Monitorowanie kolejki wychodzącej

Aby przejrzeć kolejkę wychodzącą, przejdź do **Interfejs urządzeń do obsługi materiałów \> Wspólne \> Kolejka wychodząca**. Na stronie **Kolejki wychodzącej** jest wymieniony każdy element kolejki wychodzącej oraz jego stan. Wybierz element kolejki, aby wyświetlić jego szczegóły. Te szczegóły obejmują typ transakcji towaru, używaną subskrypcję oraz wartości dla poszczególnych pól danych (od **data01** do **data10**) i ładunku.

### <a name="clean-up-the-outbound-queue"></a>Oczyszczanie kolejki wychodzącej

Ostatecznie kolejka wychodząca stanie się pełna wysłanych już elementów kolejki. Aby usunąć te elementy, przejdź do **Interfejs urządzeń do obsługi materiałów \> Zadania okresowe \> Oczyszczanie \> Oczyszczanie kolejki wychodzącej**.

## <a name="inbound-events"></a>Zdarzenia przychodzące

W tej sekcji opisano różne typy zdarzeń przychodzących, które system MH może raportować z powrotem do systemu WMS. Wyjaśnia również, że dane muszą być dostarczane przez system MH i co każde zdarzenie przychodzące robi w systemie WMS.

### <a name="structure-of-inbound-events"></a>Struktura zdarzeń przychodzących

Przy przesłaniu zdarzenia przychodzącego system zewnętrzny musi podać typ transakcji przychodzącej do 10 parametrów (od **data01** do **data10**). Opcjonalna walidacja może zapewnić, że usługa MHAX nie otrzymała tego samego zdarzenia przychodzącego więcej niż jeden raz. Aby można było włączyć tę weryfikację, każde zdarzenie przychodzące musi mieć unikatowy identyfikator komunikatu. Jeśli zostanie odebrany zduplikowany identyfikator wiadomości, a w opcji **Włącz identyfikator wiadomości przychodzącej** jest ustawiona wartość *Tak* na stronie **Parametry interfejsu obsługi materiału**, wiadomość zostanie odrzucona. Komunikat o błędzie będzie oznaczał, że komunikat już istnieje.

Oprócz pól danych przychodzących system przypisuje do zdarzenia unikatowy identyfikator kolejki przychodzącej.

### <a name="inbound-event-types"></a>Typy zdarzeń przychodzących

W tej sekcji opisano typy zdarzeń przychodzących (typy transakcji), które są obsługiwane, oraz dane, które muszą zostać dostarczone, aby zdarzenia zostały przetworzone.

#### <a name="work-confirm-events"></a>Zdarzenia potwierdzenia pracy

Zdarzenia potwierdzenia pracy wymagają, aby pola danych przychodzących zawierały następujące informacje:

- **data01** — identyfikator pary wiersza pracy.
- **data02** — identyfikator rekordu wiersza pracy (wartość `RecId`).

    > [!NOTE]
    > *Musi* być obecne pole **data01** *lub* **data02**.

- **data03** — identyfikator numeru identyfikacyjnego, z których ma na być pobranie.
- **data04** — docelowy numer identyfikacyjny nagłówka pracy.

Jeśli zostanie podany identyfikator pary wierszy pracy, wszystkie wiersze pobrania, odłożenia lub pracy niestandardowej, oznaczone przez identyfikator pary wierszy pracy i o stanie *Otwarte* lub *W przetwarzaniu*, są uruchamiane sekwencyjnie. Jeśli podano identyfikator rekordu wiersza pracy (wartość `RecId`), wiersz pracy musi być wierszem pobrania, odłożenia lub niestandardowego wiersza pracy o stanie *Otwarta* lub *W przetwarzaniu*.

Pobrania wierszy z lokalizacji kontrolowanych przez numer identyfikacyjny wymaga, aby **dane03** określały numer identyfikacyjny, z którego należy pobrać, niezależnie od tego, czy wiersze są oznaczone identyfikatorem rekordu wiersza pracy, czy identyfikatorem pary wierszy pracy. Pole **data04** musi określać docelowy numer identyfikacyjny nagłówka pracy dla pobrania.

Wiersze odłożenia nie akceptują dalszych informacji. Są one uruchamiane tylko na podstawie lokalizacji bieżącego wiersza pracy i docelowego numer identyfikacyjnego pracy. Jeśli odłożenie musi zostać wykonane w innej lokalizacji, zmień lokalizację wiersza pracy zgodnie z opisem w sekcji [Zastępowanie zdarzeń](#override-events) w dalszej części tego artykułu.

Niestandardowe wiersze pracy nie wymagają ani nie obsługują żadnych dodatkowych informacji w zdarzeniu przychodzącym.

#### <a name="short-pick-events"></a>Zdarzenia pobrania krótkiego

Zdarzenia pobrania krótkiego wymagają, aby pola danych przychodzących zawierały następujące informacje:

- **data02** — identyfikator rekordu pracy (wartość `RecId`).
- **data03** — identyfikator numeru identyfikacyjnego, z których ma na być pobranie.
- **data04** – Ilość do pobrania.
- **data05** — kod wyjątku pobrania krótkiego.
- **data06** — docelowy numer identyfikacyjny nagłówka pracy.

> [!NOTE]
> Pole **data01** nie jest używane w zdarzeniach krótkiego pobrania.

To zdarzenie przypomina zdarzenie potwierdzenia pracy, ale dotyczy tylko wierszy pobrania.

#### <a name="override-events"></a><a id="override-events"></a>Zastąp zdarzenia

Zastąpienie zdarzeń wymaga, aby pola danych przychodzących zawierały następujące informacje:

- **data01** — identyfikator rekordu pracy (wartość `RecId`).
- **data02** — identyfikator nowej lokalizacji.

Wiersz pracy musi mieć stan *Otwarty* lub *W przetwarzaniu* i musi istnieć nowa lokalizacja.

#### <a name="license-plate-receipt-events"></a>Zdarzenia przyjęcia dla numerów identyfikacyjnych

Zdarzenia przyjęcia dla numerów identyfikacyjnych wymagają, aby pola danych przychodzących zawierały następujące informacje:

- **data01** — identyfikator numeru identyfikacyjnego przejściowego, z których ma na być odbiór.

System wykonuje operację odbierania dla numeru identyfikacyjnego na podstawie wartości pola **data01** przekazanej jako numer identyfikacyjny.

### <a name="monitor-the-inbound-queue"></a>Monitorowanie kolejki przychodzącej

Aby przejrzeć kolejkę przychodzącą, przejdź do **Interfejs urządzeń do obsługi materiałów \> Wspólne \> Kolejka przychodząca**. Na stronie **Kolejki przychodzącej** jest wymieniony każdy element kolejki przychodzącej oraz jego stan. Wybierz element kolejki, aby wyświetlić jego szczegóły. Te szczegóły obejmują typ transakcji pozycji, identyfikator komunikatu i wartości dla każdego pola danych (od **data01** do **data10**).

Jeśli podczas przetwarzania zdarzeń przychodzących wystąpił błąd lub inny typ elementu dziennika, można sprawdzić dziennik, wybierając opcję **Dziennik błędów** w okienku akcji.

### <a name="inbound-event-processing"></a>Przetwarzanie zdarzenia przychodzącego

Zdarzenia przychodzące są najpierw zapisywane w bazie danych, a następnie są natychmiast (synchronicznie) uruchamiane. Jeśli podczas przetwarzania wystąpi błąd, zdarzenie jest nadal zapisywane do kolejki, ale stan ma wartość *Błąd*. Usługa MHAX zwraca komunikat o błędzie do systemu MH i przechowuje dziennik błędów w rekordzie zdarzeń przychodzących w celu późniejszego zbadania.

Zdarzenia o stanie *Błąd* można później przetworzyć ponownie, jeśli warunek błędu jest stały. Aby je ponownie przetworzyć, wykonaj jedną z następujących czynności:

- Przejdź do **Interfejs urządzeń do obsługi materiałów \> Wspólne \> Kolejka przychodząca**. Wybierz odpowiednią kolejkę przychodzących, a następnie wybierz opcję **Przetwórz ponownie** w okienku akcji.
- Przejdź do **Interfejs urządzeń do obsługi materiałów \> Wspólne \> Przetwórz ponownie kolejkę przychodzącą z błędami**. Zostanie wyświetlone standardowe okno dialogowe zadania wsadowego. Można tam skonfigurować filtr rekordów oraz zaplanować lub uruchomić zadanie wsadowe w celu ponownego przetworzenia kolejki.

Wszystkie operacje pracy (pobrania i odłogowania) są wykonywane przy użyciu pracownika wybranego w polu **Identyfikator użytkownika** na stronie **Parametry interfejsu sprzętu do obsługi materiałów**.

### <a name="clean-up-the-inbound-queue"></a>Oczyszczanie kolejki przychodzącej

Ostatecznie kolejka przychodząca stanie się pełna przetworzonych już elementów kolejki. Aby usunąć te elementy, przejdź do **Interfejs urządzeń do obsługi materiałów \> Zadania okresowe \> Oczyszczanie \> Oczyszczanie kolejki przychodzącej**.

## <a name="get-a-quick-overview-by-using-the-queue-manager"></a>Uzyskiwanie szybkiego przeglądu przy użyciu menedżera kolejek

Aby uzyskać szybki przegląd wszystkich działań związanych z kolejkami przychodzącymi i wychodzącymi, przejdź do obszaru **Interfejs urządzeń do obsługi materiałów \> Obszary robocze \> Menedżer kolejek**. Strona **Menedżer kolejek** zawiera zestaw kart i kafelków, których można używać do monitorowania i eksplorowania kolejek. Zawiera również przydatne łącza do większości innych stron wymienionych w tym artykule.

## <a name="connect-to-the-mhax-service"></a>Połącz się z usługą MHAX

Kod MHAX został zaimplementowany jako usługa niestandardowa. Z tego powodu jest on dostępny za pośrednictwem wywołań SOAP i REST. Oto adresy punktów końcowych SOAP i REST:

- **SOAP:** `https://base_environment_URL/soap/services/WMHEServices`
- **REST:** `https://base_environment_URL/api/services/WMHEServices/WMHEService`

## <a name="retrieve-messages-from-the-outbound-queue"></a>Pobieranie wiadomości z kolejki wychodzącej

Aby pobrać wiadomości z kolejki wychodzącej, należy użyć jednej z następujących metod:

- Użyj `readOutboundSubscriptionQueue`, aby pobrać zdarzenia na podstawie identyfikatora subskrypcji.
- Użyj `readOutboundWarehouseQueue` do pobierania zdarzeń na podstawie typu zdarzenia i identyfikatora magazynu w wielu subskrypcjach.
