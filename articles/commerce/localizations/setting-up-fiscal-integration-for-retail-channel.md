---
title: Konfigurowanie integracji fiskalnej dla kanałów Commerce
description: W tym temacie zawarto wskazówki dotyczące konfigurowania funkcji integracji fiskalnej dla kanałów Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: e4b0b9f7eb4fb0ffab3237459d85ea92c83dd206
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462173"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Konfigurowanie integracji fiskalnej dla kanałów Commerce

[!include [banner](../includes/banner.md)]

W tym temacie zawarto wskazówki dotyczące konfigurowania funkcji integracji fiskalnej dla kanałów Commerce. Aby uzyskać więcej informacji o integracji fiskalnej, zobacz [Omówienie integracji fiskalnej dla kanałów Commerce](fiscal-integration-for-retail-channel.md).

## <a name="set-up-commerce-parameters"></a>Ustawianie parametrów Commerce

1. Na stronie **Wspólne parametry handlu** na karcie **Ogólne** ustaw opcję **Włącz integrację fiskalną** na **Tak**.
1. Na karcie **Sekwencje identyfikatorów** zdefiniuj sekwencję numerów dla następujących odwołań:

    - Identyfikator fiskalnego profilu technicznego
    - Identyfikator grupy łącznika fiskalnego
    - Identyfikator procesu rejestracji

1. Na stronie **Parametry handlu** zdefiniuj sekwencję numerów dla fiskalnego profilu funkcjonalności.

    > [!NOTE]
    > Sekwencje numerów są opcjonalne. Numery dla wszystkich jednostek integracji fiskalnej mogą być generowane z sekwencji numerów albo ręcznie.

## <a name="set-up-a-fiscal-registration-process"></a>Konfigurowanie procesu rejestracji fiskalnej

Proces konfigurowania integracji fiskalnej obejmuje następujące zadania:

- Konfigurowanie łączników fiskalnych dla urządzeń lub usług fiskalnych używanych do celów rejestracji fiskalnej, np. drukarki fiskalne.
- Konfigurowanie dostawców dokumentu, generujących dokumenty fiskalne, którzy będą zarejestrowani w urządzeniach lub usługach fiskalnych przez łączniki fiskalne.
- Konfigurowanie procesu rejestracji fiskalnej, który określa sekwencję kroków fiskalnych oraz łączników fiskalnych i dostawców dokumentów fiskalnych używanych w każdym kroku.
- Przypisywanie procesu rejestracji fiskalnej do profili funkcji POS.
- Przypisywanie profili technicznych łącznika do profili sprzętowych.
- Przypisz profile techniczne złącza do sprzętu lub profili funkcji w punkcie sprzedaży.

### <a name="upload-configurations-of-fiscal-document-providers"></a>Wgraj konfiguracje dostawców dokumentów fiskalnych

Dostawca dokumentów fiskalnych jest odpowiedzialny za generowanie dokumentów fiskalnych, które reprezentują transakcję oraz zdarzenia, które są rejestrowane w POS w formacie, który służy do interakcji z urządzeniem fiskalnym lub usługą fiskalną. Na przykład dostawca dokumentu fiskalnego może wygenerować reprezentację paragonu fiskalnego w formacie XML.

Aby załadować konfiguracje dostawców dokumentów fiskalnych, wykonaj poniższe kroki.

1. W centrali Commerce wybierz stronę **Dostawcy dokumentów fiskalnych** (**Retail i Commerce \> Ustawienia kanału \> Integracja fiskalna \> Dostawcy dokumentów fiskalnych**).
1. Załaduj konfigurację XML dla każdego urządzenia lub usługi, których zamierzasz używać.

> [!TIP]
> Wybierając **Widok**, można wyświetlić wszystkie funkcjonalne profile, które odnoszą się do bieżącego dostawcy dokumentów fiskalnych.

> [!NOTE]
> Mapowanie danych jest uważane za element dostawcy dokumentów fiskalnych. Aby skonfigurować inne mapowania danych dla tego samego łącznika (np. do obsługi szczególnych przepisów stanowych), należy utworzyć innych dostawców dokumentów fiskalnych.

### <a name="upload-configurations-of-fiscal-connectors"></a>Wgraj konfiguracje złączy fiskalnych

Łącznik fiskalny jest odpowiedzialny za komunikację z urządzeniem fiskalnym lub usługą fiskalną. Na przykład łącznik fiskalny może wysłać paragon fiskalny utworzony przez dostawcę dokumentu fiskalnego w formacie XML na drukarce fiskalnej. Aby uzyskać więcej informacji o komponentach integracji fiskalnej, zobacz [Proces rejestracji fiskalnej i przykłady integracji fiskalnej dla urządzeń i usług fiskalnych](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

Aby załadować konfiguracje łączników fiskalnych, wykonaj poniższe kroki.

1. W centrali Commerce wybierz stronę **Łączniki fiskalne** (**Retail i Commerce \> Ustawienia kanału \> Integracja fiskalna \> Łączniki fiskalne**).
1. Wgraj konfigurację XML dla każdego urządzenia lub usługi, którą planujesz wykorzystać do celów integracji fiskalnej.

> [!TIP]
> Wybierając **Widok**, można wyświetlić wszystkie funkcjonalne i techniczne profile, które odnoszą się do bieżącego łącznika fiskalnego.

Przykładowe konfiguracje łączników fiskalnych i dostawców dokumentów fiskalnych, zobacz [Przykłady integracji fiskalnej w zestawie SDK modułu Commerce](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

### <a name="create-connector-functional-profiles"></a>Tworzenie profili funkcjonalnych łączników

Aby utworzyć profile funkcjonalne łączników, wykonaj poniższe kroki.

1. W centrali Commerce wybierz stronę **Profile funkcjonalne łączników** (**Retail i Commerce \> Ustawienia kanału \> Integracja fiskalna \> Profile funkcjonalne łączników**).
1. Dla każdej kombinacji złącza fiskalnego i dostawcy dokumentów fiskalnych, która jest związana z tym złączem fiskalnym, utwórz profil funkcjonalny złącza, wykonując poniższe kroki:

    1. Nazwij łącznik.
    1. Wybierz dostawcę dokumentów.

#### <a name="change-data-mapping-parameters-in-a-connector-functional-profile"></a>Można zmienić parametry mapowania danych w profilu funkcjonalnym łącznika

Można zmienić parametry mapowania danych w profilu funkcjonalnym łącznika. Poniższa tabela zawiera kilka przykładów parametrów mapowania danych w profilu funkcjonalnym łącznika.

| Parametr | Format | Przykład |
|-----------|--------|---------|
| Ustawienia stawek podatku VAT | wartość : VATrate | 1 : 2000, 2 : 1800 |
| Mapowanie kodów VAT | VATcode : wartość | vat20 : 1, vat18 : 2 |
| Mapowanie typów metod płatności | TenderType : wartość | Gotówka : 1, Karta : 2 |

Aby przywrócić domyślne parametry zdefiniowane w konfiguracji dostawcy dokumentów fiskalnych, wybierz **Zaktualizuj** na stronie **Profilów funkcjonalnych łączników**.

> [!NOTE]
> Profile funkcjonalne łącznika są specyficzne dla firmy. Jeśli użytkownik chce używać tej samej kombinacji łącznika fiskalnego i dostawcy dokumentów fiskalnych w różnych firmach, należy utworzyć profil funkcjonalny łącznika dla każdej firmy.

### <a name="create-connector-technical-profiles"></a>Tworzenie profili technicznych łączników

Aby utworzyć profile techniczne łączników, wykonaj poniższe kroki.

1. W centrali Commerce wybierz stronę **Profile techniczne łączników** (**Retail i Commerce \> Ustawienia kanału \> Integracja fiskalna \> Profile techniczne łączników**).
1. Aby utworzyć profil techniczny łącznika dla każdego łącznika fiskalnego, należy wykonać następujące kroki:

    1. Nazwij łącznik.
    1. Wybierz typ łącznika:

        - W przypadku urządzeń lub usług połączonych ze stacją sprzętową lub obecnych w sieci lokalnej wybierz pozycję **Lokalne**.
        - W przypadku usług zewnętrznych wybierz pozycję **Zewnętrzne**.
        - Dla łączników wewnętrznych w środowisku wykonawczym Commerce Runtime (CRT) wybierz opcję **Wewnętrzne**. 

    1. Wybór lokalizacji łącznika:

        - Jeśli łącznik znajduje się w stacji sprzętowej, wybierz pozycję **Stacja sprzętowa**.
        - Jeśli łącznik znajduje się w kasie w programie POS, wybierz opcję **Rejestr**.

Parametry na kartach **Urządzenie** i **Ustawienia** w profilu technicznym łącznika można zmienić. Aby przywrócić domyślne parametry zdefiniowane w konfiguracji łącznika fiskalnego, wybierz **Zaktualizuj**. Kiedy zostanie załadowana nowa wersja konfiguracji XML, otrzymasz komunikat informujący, że bieżący łącznik fiskalny lub dostawca dokumentów fiskalnych są już używane. Ta procedura nie zastępuje zmian wprowadzonych ręcznie wcześniej w profilach funkcjonalnych łączników i profilach technicznych łączników. Aby zastosować domyślny zestaw parametrów z nowej konfiguracji na stronie **Profile funkcjonalne łącznika** lub **Profile techniczne łącznika**, wybierz **Aktualizuj**.

Jeśli musisz skonfigurować specyficzne parametry dla pojedynczego rejestru POS lub sklepu, wykonaj poniższe kroki.

1. Wybierz pozycję w menu **Zastąp**.
1. Na stronie **Zastąp** utwórz nowy rekord.
1. Wybierz sklep lub rejestr POS. Możesz nadpisać parametry wybranego profilu technicznego dla pojedynczej kasy lub wszystkich kas w danym sklepie.
1. Na karcie **Urządzenie** wprowadź parametry wybranej kasy lub sklepu w programie POS.

### <a name="create-fiscal-connector-groups"></a>Tworzenie grup łączników fiskalnych

Grupa łączników fiskalnych łączy profile funkcjonalne łączników fiskalnych, które wykonują te same funkcje i są używane na tym samym etapie procesu rejestracji fiskalnej. Na przykład jeśli kilka modeli drukarki fiskalnej może być używanych w sklepie, łączniki fiskalne dla tych drukarek fiskalnych mogą być połączone w grupie łączników fiskalnych.

Aby utworzyć grupę złączy fiskalnych, wykonaj poniższe kroki.

1. Przejdź na stronę **Grupa łączników fiskalnych** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**).
1. Utwórz nową grupę łączników fiskalnych.
1. Dodaj profile funkcjonalności do grupy łączników. Na karcie **Profile funkcjonalne** wybierz **Dodaj** i wybierz numer profilu. Każdy łącznik fiskalny w grupie łączników może mieć tylko jeden profil funkcjonalności.
1. Aby zawiesić używanie profilu funkcjonalności, ustaw opcję **Wyłącz** na wartość **Tak**. Ta zmiana dotyczy tylko bieżącej grupy łączników. Możesz kontynuować używanie tego samego profilu funkcjonalności w innych grupach łączników.

### <a name="create-a-fiscal-registration-process"></a>Tworzenie procesu rejestracji fiskalnej

Proces rejestracji fiskalnej jest definiowany przez sekwencję etapów rejestracji oraz przez grupę łączników używaną na każdym etapie.

Aby stworzyć proces rejestracji fiskalnej, wykonaj poniższe kroki.

1. W centrali Commerce wybierz stronę **Proces rejestracji fiskalnej** (**Retail i Commerce \> Ustawienia kanału \> Integracja fiskalna \> Proces rejestracji fiskalnej**).
1. Utwórz nowy rekord dla każdego unikalnego procesu rejestracji fiskalnej.
1. Dodaj do procesu kroki rejestracyjne, postępując zgodnie z poniższymi krokami:

    1. Wybierz opcję **Dodaj**.
    1. Wybierz typ łącznika fiskalnego:
    1. W polu **Numer grupy** wybierz odpowiedni grupę łączników fiskalnych.

### <a name="assign-entities-of-the-fiscal-registration-process-to-pos-profiles"></a>Przypisz jednostki procesu rejestracji fiskalnej do profili POS

Aby przypisać podmioty procesu rejestracji fiskalnej do profili POS, wykonaj poniższe kroki.

1. W centrali Commerce przejdź na stronę **Profile funkcjonalności POS** (**Retail i Commerce \> Ustawienia kanału \> Konfiguracja POS \> Profile POS \> Profile funkcjonalności**). 
1. Przyporządkuj proces rejestracji fiskalnej do profilu funkcjonalności POS.
1. Wybierz **Edytuj**, a następnie na karcie **Proces rejestracji fiskalnej** w polu **Numer procesu** wybierz proces.
1. Na karcie **Usługi fiskalne** wybierz profile techniczne łącznika z kasą lokalizacji **łącznika**.
1. Przejdź do strony **Profil sprzętowy POS** (**Retail i Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktu sprzedaży \> Profil sprzętu**).
1. Przyporządkuj profile techniczne łączników do profilu sprzętowego. 
1. Wybierz pozycję **Edytuj**, a następnie na karcie **Fiskalne urządzenia peryferyjne** dodaj wiersz. 
1. Wybierz profil techniczny łącznika w polu **Identyfikator profilu**.
1. Na karcie **Peryferia fiskalne** wybierz profile techniczne łącznika z kasą lokalizacji łącznika **Stacja sprzętowa**.

> [!NOTE]
> Do tego samego profilu sprzętowego można dodać kilka profili technicznych. Jednak profil sprzętowy lub profil funkcjonalności POS powinny mieć tylko jeden punkt styczny z grupą łączników fiskalnych.

Przepływ rejestracji fiskalnej jest definiowany przez proces rejestracji fiskalnej i również przez niektóre parametry komponentów integracji fiskalnej: wykonanie środowiska uruchomieniowego CRT dla dostawcy dokumentów fiskalnych oraz wykonanie Hardware Station dla łącznika fiskalnego.

- Subskrypcja zdarzeń i transakcji w rejestracji fiskalnej jest wstępnie zdefiniowana w dostawcy dokumentów fiskalnych.
- Dostawca dokumentów fiskalnych jest również odpowiedzialny za identyfikację łącznika fiskalnego używanego do rejestracji fiskalnej. Jest on zgodny z profilami funkcjonalnymi łącznika, które są uwzględniane w grupie łączników fiskalnych, określonych dla bieżącego kroku procesu rejestracji fiskalnej z profilem technicznym łącznika, który jest skojarzony z profilem sprzętowym Hardware Station, z którą jest sparowany POS.
- Dostawca dokumentów fiskalnych korzysta z ustawień mapowania danych z konfiguracji dostawcy dokumentów fiskalnych do przekształcania danych transakcji/zdarzeń na podatki i płatności podczas generowania dokumentu fiskalnego.
- Kiedy dostawca dokumentów fiskalnych generuje dokument fiskalny, łącznik fiskalny może albo wysłać go do urządzenia fiskalnego bez zmian, albo przeanalizować go i zamienić na sekwencję poleceń interfejsu API - to zależy od tego, jak obsługiwana jest komunikacja.

### <a name="set-up-registers-with-fiscal-registration-restrictions"></a>Konfigurowanie rejestrów z ograniczeniami rejestracji fiskalnej

Możesz wybrać rejestry, w których rejestracja fiskalna jest zabroniona, na przykład w przypadkach, w których musisz wykonać tylko operacje niefiskalne, takie jak wyszukiwanie katalogu produktów, wyszukiwanie klientów lub tworzenie wersji roboczej transakcji na tych urządzeniach.

Aby skonfigurować rejestry z ograniczeniami rejestracji fiskalnej, wykonaj następujące kroki.

1. W Commerce headquarters wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnej**.
1. Wybierz żądany proces.
1. Wybierz kartę **Rejestry w programie POS z ograniczeniami procesów fiskalnych**.
1. W razie potrzeby dodaj rejestry z ograniczeniami procesu fiskalnego.

### <a name="validate-the-fiscal-registration-process"></a>Weryfikacja procesu rejestracji fiskalnej

Zaleca się, abyś dokonał walidacji procesu rejestracji fiskalnej w następujących przypadkach:

- Dokonałeś już wszystkich ustawień dla nowego procesu rejestracji. Ustawienia te obejmują przypisanie procesów rejestracji do profili funkcjonalności POS i profili sprzętowych.
- Dokonałeś zmian w istniejącym procesie rejestracji fiskalnej i zmiany te mogą spowodować, że w czasie pracy zostanie wybrany inny łącznik fiskalny. (Na przykład, zmieniłeś grupę łączników dla kroku procesu rejestracji fiskalnej, włączyłeś profil funkcjonalny łącznika w grupie łączników lub dodałeś nowy profil funkcjonalny łącznika do grupy łączników).
- Udało się wprowadzenie zmian w przypisaniu profilów technicznych łącznika do profilów sprzętowych.

Aby zatwierdzić proces rejestracji fiskalnej, wykonaj poniższe kroki.

1. W centrali Commerce wybierz stronę **Proces rejestracji fiskalnej** (**Retail i Commerce \> Ustawienia kanału \> Integracja fiskalna \> Proces rejestracji fiskalnej**).
1. Wybierz pozycję **Weryfikuj**, aby sprawdzić poprawność procesu rejestracji fiskalnej.
1. Na stronie **Harmonogram dystrybucji** uruchom zadania **1070** i **1090**, aby przenieść dane do bazy danych kanału.

## <a name="set-up-fiscal-texts-for-discounts"></a>Konfigurowanie tekstów fiskalnych dla rabatów

W niektórych przypadkach specjalny tekst musi zostać wydrukowany na paragonie fiskalnym, w przypadku zastosowania rabatu. Można skonfigurować teksty fiskalne dla rabatów na stronie **Grupa łączników fiskalnych** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**).

- Dla rabatów ręcznych zastosowanych w POS musisz ustawić tekst fiskalny dla kodu informacyjnego lub grupy kodów informacji określonych jako kod informacji **Rabat produktu** w profilu funkcjonalności POS.

    1. Na stronie **Grupa łącznika fiskalnego** wybierz **Tekst paragonu fiskalnego**.
    1. Na karcie **Kody informacji** wybierz **Dodaj** i wybierz kod informacji lub grupę kodów informacji.
    1. W polu **Numer kodu informacji** wybierz wartość.
    1. W polu **Numer kodu podrzędnego** wybierz wartość, jeśli kod podrzędny jest wymagany dla wybranego kodu informacji.
    1. W polu **Tekst paragonu fiskalnego** określ tekst fiskalny, który ma być drukowany na paragonie fiskalnym.
    1. Ustaw opcję **Drukuj tekst użytkownika na paragonie fiskalnym** na **Tak**, aby umożliwić zastąpienie tekstu na paragonie fiskalnym informacjami wprowadzanymi ręcznie przez użytkownika POS. Ta opcja dotyczy tylko kodów informacji, które mają typ danych wejściowych **Tekst**.

    > [!NOTE]
    > Można określić tekst fiskalny dla kilku kodów informacji, aby obsługiwać scenariusze, w których używane są grupy kodów informacji, połączone kody informacji i wywołane kody informacji. W tych scenariuszach paragon fiskalny będzie zawierał tekst fiskalny z wszystkich kodów informacji połączonych z wierszem transakcji, w której zastosowano rabat.

- Dla rabatów specyficznych dla kanału należy zdefiniować tekst fiskalnych dla identyfikatora rabatu.

    1. Na stronie **Grupa łącznika fiskalnego** wybierz **Tekst paragonu fiskalnego**.
    1. Na karcie **Rabaty** wybierz opcję **Dodaj** i wybierz identyfikator rabatu.
    1. W polu **Tekst paragonu fiskalnego** określ tekst fiskalny, który ma być drukowany na paragonie fiskalnym.

    > [!NOTE]
    > Jeśli kilka rabatów jest stosowanych do tego samego wiersza transakcji, paragon fiskalny będzie zawierał teksty fiskalne z wszystkich rabatów, które są połączone z tymi wierszami transakcji.

## <a name="set-error-handling-settings"></a>Określanie ustawienia ustawień obsługi błędów

Opcje obsługi błędów dostępne w integracji fiskalnej ustawia się w procesie rejestracji fiskalnej. Aby uzyskać więcej informacji na temat obsługi błędów w integracji fiskalnej, zobacz [Obsługa błędów](fiscal-integration-for-retail-channel.md#error-handling).

Aby skonfigurować ustawienia obsługi błędów, wykonaj poniższe kroki.

1. Na stronie **Proces rejestracji fiskalnej** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnych**) możesz ustawić następujące parametry dla każdego kroku procesu rejestracji fiskalnej.

    - **Zezwalaj na pomijanie** – ten parametr pozwala korzystać z opcji **Pomiń** w oknie dialogowym obsługi błędów.
    - **Zezwalaj na oznaczanie jako zarejestrowane** — ten parametr umożliwia korzystanie z opcji **Oznacz jako zarejestrowane** w oknie dialogowym obsługi błędów.
    - **Zezwalaj na odłożenie** – ten parametr pozwala korzystać z opcji **Odłóż** w oknie dialogowym obsługi błędów.
    - **Kontynuuj przy błędzie** — Jeśli ten parametr jest włączony, proces rejestracji fiskalnej może być kontynuowany w rejestracji punktu sprzedaży po niepowodzeniu rejestracji transakcji lub zdarzenia. W przeciwnym razie do uruchomienia rejestracji fiskalnej następnej transakcji lub następnego zdarzenia operator musi podjąć ponowną próbę nieudanej rejestracji fiskalnej, pominąć ten krok lub oznaczyć transakcję lub zdarzenie jako zarejestrowane. Aby uzyskać więcej informacji, zobacz [Opcjonalna rejestracja fiskalna](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Po włączeniu parametru **Kontynuuj przy błędzie** parametry **Zezwalaj na pomijanie** i **Zezwalaj na oznaczanie jako zarejestrowane** są automatycznie wyłączone.

1. Opcje **Pomiń** i **Oznacz jako zarejestrowane** w oknie dialogowym obsługi błędów wymagają włączenia **Zezwalaj na pomijanie rejestracji lub oznaczanie jako zarejestrowane**. Aby to zrobić, przejdź na stronę **Grupy uprawnień** (**Retail i Commerce \> Pracownicy \> Grupy uprawnień**) i włącz uprawnienie **Zezwalaj na pomijanie rejestracji lub oznaczanie jako zarejestrowane** na **Tak**.
1. Opcja **Odłóż** w oknie dialogowym obsługi błędów wymaga włączenia uprawnienia **Zezwalaj na odłożenie**. Aby to zrobić, przejdź na stronę **Grupy uprawnień** (**Retail i Commerce \> Pracownicy \> Grupy uprawnień**) i włącz uprawnienie **Zezwalaj odłożenie** na **Tak**.
1. Opcje **Pomiń**, **Odłóż** i **Oznacz jako zarejestrowane** umożliwiają operatorom wprowadzanie dodatkowych informacji, kiedy rejestracja fiskalna nie powiedzie się. Aby udostępnić tę funkcję, należy określić kody informacji **Pomiń**, **Odłóż** i **Oznacz jako zarejestrowane** dla grupy łączników fiskalnych. Informacje wprowadzane przez operatorów są wtedy zapisywane jako transakcja kodu informacji połączona z transakcją fiskalną. Aby dowiedzieć się więcej na temat kodów informacji, zobacz [Kody informacji i grupy kodów informacji](../info-codes-retail.md).

    > [!NOTE]
    > Funkcja wyzwalająca **Produkt** nie jest obsługiwana dla kodów informacji, które są używane do obsługi poleceń **Pomiń** i **Oznacz jako zarejestrowane** w grupach łączników fiskalnych.

    - Na stronie **Grupa łączników fiskalnych** na karcie **Kody informacyjne** wybierz kody informacji lub grupy kodów informacji w polach **Pomiń**, **Odłóż** lub **Oznacz jako zarejestrowane**.

    > [!NOTE]
    > Jeden dokument fiskalny i jeden dokument niefiskalny mogą być generowane w dowolnym kroku procesu rejestracji fiskalnej. Rozszerzenie dostawcy dokumentów fiskalnych identyfikuje każdy rodzaj transakcji lub zdarzenia w odniesieniu do dokumentów fiskalnych lub niefiskalnych. Funkcja obsługi błędów dotyczy tylko dokumentów fiskalnych.
    >
    > - **Dokument fiskalny** — wymagany dokument, który powinien zostać zarejestrowany pomyślnie (na przykład paragon fiskalny).
    > - **Dokument niefiskalny** — dodatkowy dokument dla transakcji lub zdarzenia (na przykład dokument karty upominkowej).

1. Jeśli operator musi mieć możliwość kontynuowania bieżącej operacji (np. tworzenia lub finalizowania transakcji) po wystąpieniu błędu sprawdzania kondycji, należy włączyć uprawnienie **Zezwalaj na pominięcie błędu sprawdzania kondycji** na stronie **grup uprawnień** (**Handel detaliczny i inny \> Pracownicy \> Grupy uprawnień**). Aby uzyskać więcej informacji dotyczących procedury sprawdzania kondycji, zobacz [sprawdzanie kondycji rejestracji fiskalnej](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Konfigurowanie raportów fiskalnych X / końcowych raportów sprzedaży z POS

Aby włączyć raporty fiskalne X / końcowe raporty sprzedaży z POS, należy dodać nowe przyciski do układu POS.

- Na stronie **Siatka przycisków** postępuj zgodnie instrukcjami w [Dodawanie operacji punktu sprzedaży do układów aplikacji POS przy użyciu projektanta siatki przycisków](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters), aby zainstalować projektanta i zaktualizować układ POS.

    1. Wybierz układ do zaktualizowania. 
    1. Dodaj nowy przycisk i ustaw właściwość przycisku **Drukuj częściowy raport obrachunkowy sprzedaży częściowej**.
    1. Dodaj nowy przycisk i ustaw właściwość przycisku **Drukuj obrachunkowy końcowy raport sprzedaży**.
    1. Na stronie **Harmonogram dystrybucji** uruchom zadanie **1090**, aby przenieść zmiany do bazy danych kanału.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej

Aby włączyć ręczne wykonywanie odroczonej rejestracji fiskalnej, należy dodać nowy przycisk do układu punktu sprzedaży.

- Na stronie **Siatka przycisków** postępuj zgodnie instrukcjami w [Dodawanie operacji punktu sprzedaży do układów aplikacji POS przy użyciu projektanta siatki przycisków](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters), aby zainstalować projektanta i zaktualizować układ POS.

    1. Wybierz układ do zaktualizowania.
    1. Dodaj nowy przycisk i ustaw właściwość przycisku **Zakończ proces rejestracji fiskalnej**.
    1. Na stronie **Harmonogram dystrybucji** uruchom zadanie **1090**, aby przenieść zmiany do bazy danych kanału.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
