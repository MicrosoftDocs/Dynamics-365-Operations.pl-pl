---
title: Konfigurowanie integracji fiskalnej dla kanałów Commerce
description: W tym temacie zawarto wskazówki dotyczące konfigurowania funkcji integracji fiskalnej dla kanałów Commerce.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 889340c13d150ce8e3ad49a08b3d7f0c25a4b77a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017900"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Konfigurowanie integracji fiskalnej dla kanałów Commerce

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Wprowadzenie

W tym temacie zawarto wskazówki dotyczące konfigurowania funkcji integracji fiskalnej dla kanałów Commerce. Aby uzyskać więcej informacji o integracji fiskalnej, zobacz [Omówienie integracji fiskalnej dla kanałów Commerce](fiscal-integration-for-retail-channel.md).

Proces konfigurowania integracji fiskalnej obejmuje następujące zadania:

1. Konfigurowanie łączników fiskalnych dla urządzeń lub usług fiskalnych używanych do celów rejestracji fiskalnej, np. drukarki fiskalne.
2. Konfigurowanie dostawców dokumentu, generujących dokumenty fiskalne, którzy będą zarejestrowani w urządzeniach lub usługach fiskalnych przez łączniki fiskalne.
3. Konfigurowanie procesu rejestracji fiskalnej, który określa sekwencję kroków fiskalnych oraz łączników fiskalnych i dostawców dokumentów fiskalnych używanych w każdym kroku.
4. Przypisywanie procesu rejestracji fiskalnej do profili funkcji POS.
5. Przypisywanie profili technicznych łącznika do profili sprzętowych.

## <a name="set-up-a-fiscal-registration-process"></a>Konfigurowanie procesu rejestracji fiskalnej

Przed użyciem funkcji integracji fiskalnej należy skonfigurować następujące ustawienia.

1. Aktualizuj parametry usługi Commerce.

    1. Na stronie **Wspólne parametry handlu** na karcie **Ogólne** ustaw opcję **Włącz integrację fiskalną** na **Tak**. Na karcie **Sekwencje identyfikatorów** zdefiniuj sekwencję numerów dla następujących odwołań:

        - Identyfikator fiskalnego profilu technicznego
        - Identyfikator grupy łącznika fiskalnego
        - Identyfikator procesu rejestracji

    2. Na stronie **Parametry handlu** zdefiniuj sekwencję numerów dla fiskalnego profilu funkcjonalności.

    > [!NOTE]
    > Sekwencje numerów są opcjonalne. Numery dla wszystkich jednostek integracji fiskalnej mogą być generowane z sekwencji numerów albo ręcznie.

2. Prześlij konfiguracje łączników fiskalnych i dostawców dokumentów fiskalnych.

    Dostawca dokumentów fiskalnych jest odpowiedzialny za generowanie dokumentów fiskalnych, które reprezentują transakcję oraz zdarzenia, które są rejestrowane w POS w formacie, który służy do interakcji z urządzeniem fiskalnym lub usługą fiskalną. Na przykład dostawca dokumentu fiskalnego może wygenerować reprezentację paragonu fiskalnego w formacie XML.

    Łącznik fiskalny jest odpowiedzialny za komunikację z urządzeniem fiskalnym lub usługą fiskalną. Na przykład łącznik fiskalny może wysłać paragon fiskalny utworzony przez dostawcę dokumentu fiskalnego w formacie XML na drukarce fiskalnej. Aby uzyskać więcej informacji o komponentach integracji fiskalnej, zobacz [Proces rejestracji fiskalnej i przykłady integracji fiskalnej dla urządzeń fiskalnych](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

    1. Na stronie **Łączniki fiskalne** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Łączniki fiskalne**) prześlij konfigurację XML dla każdego urządzenia lub usługi, których planujesz używać na potrzeby integracji fiskalnej.

        > [!TIP]
        > Wybierając **Widok**, można wyświetlić wszystkie funkcjonalne i techniczne profile, które odnoszą się do bieżącego łącznika fiskalnego.

    2. Na stronie **Dostawcy dokumentów fiskalnych** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Dostawcy dokumentów fiskalnych**) prześlij konfigurację XML dla każdego urządzenia lub usługi, których planujesz używać.

        > [!TIP]
        > Wybierając **Widok**, można wyświetlić wszystkie funkcjonalne profile, które odnoszą się do bieżącego dostawcy dokumentów fiskalnych.

    Przykładowe konfiguracje łączników fiskalnych i dostawców dokumentów fiskalnych, zobacz [Przykłady integracji fiskalnej w zestawie SDK modułu Retail](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk).

    > [!NOTE]
    > Mapowanie danych jest uważane za element dostawcy dokumentów fiskalnych. Aby skonfigurować inne mapowania danych dla tego samego łącznika (np. do obsługi szczególnych przepisów stanowych), należy utworzyć innych dostawców dokumentów fiskalnych.

3. Tworzenie profili funkcjonalnych i technicznych łącznika.

    1. Na stronie **Profile funkcjonalne łącznika** (**Handel detaliczny i inny \> Konfiguracja kanału \> Integracja fiskalna \> Profile funkcjonalne łącznika**) utwórz profil funkcjonalny łącznika dla każdej kombinacji łącznika fiskalnego i dostawcy dokumentów fiskalnych, która jest związana z tym łącznikiem fiskalnym.

        1. Nazwij łącznik.
        2. Wybierz dostawcę dokumentów.

        Można zmienić parametry mapowania danych w profilu funkcjonalnym łącznika. Aby przywrócić domyślne parametry zdefiniowane w konfiguracji dostawcy dokumentów fiskalnych, wybierz **Zaktualizuj**.

        **Przykłady**

        |   | Format | Przykład |
        |---|--------|---------|
        | **Ustawienia stawek podatku VAT** | wartość : VATrate | 1 : 2000, 2 : 1800 |
        | **Mapowanie kodów VAT** | VATcode : wartość | vat20 : 1, vat18 : 2 |
        | **Mapowanie typów metod płatności** | TenderType : wartość | Gotówka : 1, Karta : 2 |

        > [!NOTE]
        > Profile funkcjonalne łącznika są specyficzne dla firmy. Jeśli użytkownik chce używać tej samej kombinacji łącznika fiskalnego i dostawcy dokumentów fiskalnych w różnych firmach, należy utworzyć profil funkcjonalny łącznika dla każdej firmy.

    2. Na stronie **Profile techniczne łącznia** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile techniczne łącznika**) utwórz profil techniczny łącznika dla każdego łącznika fiskalnego.

        1. Nazwij łącznik.
        2. Wybierz typ łącznika. Dla urządzeń, które są połączone z Hardware Station, zaznacz opcję **Lokalne**.

            > [!NOTE]
            > Obecnie obsługiwane są tylko łączniki lokalne.

        Parametry na kartach **Urządzenie** i **Ustawienia** w profilu technicznym łącznika można zmienić. Aby przywrócić domyślne parametry zdefiniowane w konfiguracji łącznika fiskalnego, wybierz **Zaktualizuj**. Kiedy zostanie załadowana nowa wersja konfiguracji XML, otrzymasz komunikat informujący, że bieżący łącznik fiskalny lub dostawca dokumentów fiskalnych są już używane. Ta procedura nie zastępuje zmian wprowadzonych ręcznie wcześniej w profilach funkcjonalnych łączników i profilach technicznych łączników. Aby zastosować domyślny zestaw parametrów z nowej konfiguracji na stronie **Profile funkcjonalne łącznika** lub **Profile techniczne łącznika**, wybierz **Aktualizuj**.

4. Tworzenie grup łączników fiskalnych.

    Grupa łączników fiskalnych łączy profile funkcjonalne łączników fiskalnych, które wykonują te same funkcje i są używane na tym samym etapie procesu rejestracji fiskalnej. Na przykład jeśli kilka modeli drukarki fiskalnej może być używanych w sklepie, łączniki fiskalne dla tych drukarek fiskalnych mogą być połączone w grupie łączników fiskalnych.

    1. Na stronie **Grupa łączników fiskalnych** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**) utwórz nową grupę łączników fiskalnych.
    2. Dodaj profile funkcjonalności do grupy łączników. Na karcie **Profile funkcjonalne** wybierz **Dodaj** i wybierz numer profilu. Każdy łącznik fiskalny w grupie łączników może mieć tylko jeden profil funkcjonalności.
    3. Aby zawiesić używanie profilu funkcjonalności, ustaw opcję **Wyłącz** na wartość **Tak**. Ta zmiana dotyczy tylko bieżącej grupy łączników. Możesz kontynuować używanie tego samego profilu funkcjonalności w innych grupach łączników.

5. Tworzenie procesu rejestracji fiskalnej.

    Proces rejestracji fiskalnej jest definiowany przez sekwencję etapów rejestracji oraz przez grupę łączników używaną na każdym etapie.

    1. Na stronie **Proces rejestracji fiskalnej** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnych**) utwórz nowy rekord dla każdego unikatowego procesu rejestracji fiskalnej.
    2. Dodaj etapy rejestracji do procesu:

        1. Wybierz opcję **Dodaj**.
        2. Wybierz typ łącznika fiskalnego:
        3. W polu **Numer grupy** wybierz odpowiedni grupę łączników fiskalnych.

6. Przypisz jednostki procesu rejestracji fiskalnej do profili POS.

    1. Na stronie **Profile funkcjonalne POS** (**Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia POS \> Profile POS \> Profile funkcjonalności**) przypisz proces rejestracji fiskalnej do profilu funkcjonalności POS. Wybierz **Edytuj**, a następnie na karcie **Proces rejestracji fiskalnej** w polu **Numer procesu** wybierz proces.
    2. Na stronie **Profil sprzętu POS** (**Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia POS \> Profile POS \> Profile sprzętowe**) przydziel profile techniczne łącznika do profilu sprzętowego. Wybierz **Edytuj** dodaj wiersz do karty **Peryferyjne urządzenia fiskalne**, a następnie w polu **Numer profilu** wybierz profil techniczny łącznika.

    > [!NOTE]
    > Do tego samego profilu sprzętowego można dodać kilka profili technicznych. Jednak profil sprzętowy lub profil funkcjonalności POS powinny mieć tylko jeden punkt styczny z grupą łączników fiskalnych.

    Przepływ rejestracji fiskalnej jest definiowany przez proces rejestracji fiskalnej i również przez niektóre parametry komponentów integracji fiskalnej: wykonanie środowiska uruchomieniowego Commerce dla dostawcy dokumentów fiskalncych oraz wykonanie Hardware Station dla łącznika fiskalnego.

    - Subskrypcja zdarzeń i transakcji w rejestracji fiskalnej jest wstępnie zdefiniowana w dostawcy dokumentów fiskalnych.
    - Dostawca dokumentów fiskalnych jest również odpowiedzialny za identyfikację łącznika fiskalnego używanego do rejestracji fiskalnej. Jest on zgodny z profilami funkcjonalnymi łącznika, które są uwzględniane w grupie łączników fiskalnych, określonych dla bieżącego kroku procesu rejestracji fiskalnej z profilem technicznym łącznika, który jest skojarzony z profilem sprzętowym Hardware Station, z którą jest sparowany POS.
    - Dostawca dokumentów fiskalnych korzysta z ustawień mapowania danych z konfiguracji dostawcy dokumentów fiskalnych do przekształcania danych transakcji/zdarzeń na podatki i płatności podczas generowania dokumentu fiskalnego.
    - Kiedy dostawca dokumentów fiskalnych generuje dokument fiskalny, łącznik fiskalny może albo wysłać go do urządzenia fiskalnego bez zmian, albo przeanalizować go i zamienić na sekwencję poleceń interfejsu API - to zależy od tego, jak obsługiwana jest komunikacja.

7. Na stronie **Proces rejestracji fiskalnej** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnych**) wybierz **Sprawdź**, aby sprawdzić proces rejestracji fiskalnej.

    Zalecamy uruchomienie tego typu weryfikacji w następujących przypadkach:

    - Po zakończeniu wprowadzania wszystkich ustawień dla nowego procesu rejestracji, w tym podczas przypisywania procesu rejestracji do profili funkcjonalności POS i profili sprzętowych.
    - Po wprowadzeniu zmian do istniejącego procesu rejestracji fiskalnej i kiedy te zmiany mogą powodować wybieranie różnych łączników fiskalnych w momencie uruchomienia (np. jeśli zmienisz grupę łączników dla konfiguracji procesu rejestracji fiskalnej, włączysz profil funkcjonalny łącznika w grupie łączników lub dodasz nowy profil funkcjonalny do grupy łączników).
    - Po wprowadzeniu zmian w przypisaniu profilów technicznych łącznika do profilów sprzętowych.

8. Na stronie **Harmonogram dystrybucji** uruchom zadania **1070** i **1090**, aby przenieść dane do bazy danych kanału.

## <a name="set-up-fiscal-texts-for-discounts"></a>Konfigurowanie tekstów fiskalnych dla rabatów

W niektórych przypadkach specjalny tekst musi zostać wydrukowany na paragonie fiskalnym, w przypadku zastosowania rabatu. Można skonfigurować teksty fiskalne dla rabatów na stronie **Grupa łączników fiskalnych** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**).

- Dla rabatów ręcznych zastosowanych w POS musisz ustawić tekst fiskalny dla kodu informacyjnego lub grupy kodów informacji określonych jako kod informacji **Rabat produktu** w profilu funkcjonalności POS.

    1. Na stronie **Grupa łącznika fiskalnego** wybierz **Tekst paragonu fiskalnego**.
    2. Na karcie **Kody informacji** wybierz **Dodaj** i wybierz kod informacji lub grupę kodów informacji.
    3. W polu **Numer kodu informacji** wybierz wartość.
    4. W polu **Numer kodu podrzędnego** wybierz wartość, jeśli kod podrzędny jest wymagany dla wybranego kodu informacji.
    5. W polu **Tekst paragonu fiskalnego** określ tekst fiskalny, który ma być drukowany na paragonie fiskalnym.
    6. Ustaw opcję **Drukuj tekst użytkownika na paragonie fiskalnym** na **Tak**, aby umożliwić zastąpienie tekstu na paragonie fiskalnym informacjami wprowadzanymi ręcznie przez użytkownika POS. Ta opcja dotyczy tylko kodów informacji, które mają typ danych wejściowych **Tekst**.

    > [!NOTE]
    > Można określić tekst fiskalny dla kilku kodów informacji, aby obsługiwać scenariusze, w których używane są grupy kodów informacji, połączone kody informacji i wywołane kody informacji. W tych scenariuszach paragon fiskalny będzie zawierał tekst fiskalny z wszystkich kodów informacji połączonych z wierszem transakcji, w której zastosowano rabat.

- Dla rabatów specyficznych dla kanału należy zdefiniować tekst fiskalnych dla identyfikatora rabatu.

    1. Na stronie **Grupa łącznika fiskalnego** wybierz **Tekst paragonu fiskalnego**.
    2. Na karcie **Rabaty** wybierz opcję **Dodaj** i wybierz identyfikator rabatu.
    3. W polu **Tekst paragonu fiskalnego** określ tekst fiskalny, który ma być drukowany na paragonie fiskalnym.

    > [!NOTE]
    > Jeśli kilka rabatów jest stosowanych do tego samego wiersza transakcji, paragon fiskalny będzie zawierał teksty fiskalne z wszystkich rabatów, które są połączone z tymi wierszami transakcji.

## <a name="set-error-handling-settings"></a>Określanie ustawienia ustawień obsługi błędów

Opcje obsługi błędów dostępne w integracji fiskalnej ustawia się w procesie rejestracji fiskalnej. Aby uzyskać więcej informacji na temat obsługi błędów w integracji fiskalnej, zobacz [Obsługa błędów](fiscal-integration-for-retail-channel.md#error-handling).

1. Na stronie **Proces rejestracji fiskalnej** (**Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnych**) możesz ustawić następujące parametry dla każdego kroku procesu rejestracji fiskalnej.

    - **Zezwalaj na pomijanie** – ten parametr pozwala korzystać z opcji **Pomiń** w oknie dialogowym obsługi błędów.
    - **Zezwalaj na oznaczanie jako zarejestrowane** — ten parametr umożliwia korzystanie z opcji **Oznacz jako zarejestrowane** w oknie dialogowym obsługi błędów.
    - **Kontynuuj przy błędzie** — Jeśli ten parametr jest włączony, proces rejestracji fiskalnej może być kontynuowany w rejestracji punktu sprzedaży po niepowodzeniu rejestracji transakcji lub zdarzenia. W przeciwnym razie do uruchomienia rejestracji fiskalnej następnej transakcji lub następnego zdarzenia operator musi podjąć ponowną próbę nieudanej rejestracji fiskalnej, pominąć ten krok lub oznaczyć transakcję lub zdarzenie jako zarejestrowane. Aby uzyskać więcej informacji, zobacz [Opcjonalna rejestracja fiskalna](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Po włączeniu parametru **Kontynuuj przy błędzie** parametry **Zezwalaj na pomijanie** i **Zezwalaj na oznaczanie jako zarejestrowane** są automatycznie wyłączone.

2. Opcje **Pomiń** i **Oznacz jako zarejestrowane** w oknie dialogowym obsługi błędów wymagają uprawnienia **Zezwalaj na pomijanie rejestracji lub oznaczanie jako zarejestrowane**. Dlatego na stronie **Grupy uprawnień** (**Handel detaliczny i inny \> Pracownicy \> Grupy uprawnień**) trzeba włączyć uprawnienie **Zezwalaj na pomijanie rejestracji lub oznaczanie jako zarejestrowane**.
3. Opcje **Pomiń** i **Oznacz jako zarejestrowane** umożliwiają operatorom wprowadzanie dodatkowych informacji, kiedy rejestracja fiskalna nie powiedzie się. Aby udostępnić tę funkcję, należy określić kody informacji **Pomiń** i **Oznacz jako zarejestrowane** dla grupy łączników fiskalnych. Informacje wprowadzane przez operatorów są wtedy zapisywane jako transakcja kodu informacji połączona z transakcją fiskalną. Aby dowiedzieć się więcej na temat kodów informacji, zobacz [Kody informacji i grupy kodów informacji](../info-codes-retail.md).

    > [!NOTE]
    > Funkcja wyzwalająca **Produkt** nie jest obsługiwana dla kodów informacji, które są używane do obsługi poleceń **Pomiń** i **Oznacz jako zarejestrowane** w grupach łączników fiskalnych.

    - Na stronie **Grupa łączników fiskalnych** na karcie **Kody informacyjne** wybierz kody informacji lub grupy kodów informacji w polach **Pomiń** lub **Oznacz jako zarejestrowane**.

    > [!NOTE]
    > Jeden dokument fiskalny i jeden dokument niefiskalny mogą być generowane w dowolnym kroku procesu rejestracji fiskalnej. Rozszerzenie dostawcy dokumentów fiskalnych identyfikuje każdy rodzaj transakcji lub zdarzenia w odniesieniu do dokumentów fiskalnych lub niefiskalnych. Funkcja obsługi błędów dotyczy tylko dokumentów fiskalnych.
    >
    > - **Dokument fiskalny** — wymagany dokument, który powinien zostać zarejestrowany pomyślnie (na przykład paragon fiskalny).
    > - **Dokument niefiskalny** — dodatkowy dokument dla transakcji lub zdarzenia (na przykład dokument karty upominkowej).

4. Jeśli operator musi mieć możliwość kontynuowania bieżącej operacji (np. tworzenia lub finalizowania transakcji) po wystąpieniu błędu sprawdzania kondycji, należy włączyć uprawnienie **Zezwalaj na pominięcie błędu sprawdzania kondycji** na stronie **grup uprawnień** (**Handel detaliczny i inny \> Pracownicy \> Grupy uprawnień**). Aby uzyskać więcej informacji dotyczących procedury sprawdzania kondycji, zobacz [sprawdzanie kondycji rejestracji fiskalnej](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Konfigurowanie raportów fiskalnych X / końcowych raportów sprzedaży z POS

Aby włączyć raporty fiskalne X / końcowe raporty sprzedaży z POS, należy dodać nowe przyciski do układu POS.

- Na stronie **Siatka przycisków** postępuj zgodnie instrukcjami w [Dodawanie operacji punktu sprzedaży do układów aplikacji POS przy użyciu projektanta siatki przycisków](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters), aby zainstalować projektanta i zaktualizować układ POS.

    1. Wybierz układ do zaktualizowania. 
    2. Dodaj nowy przycisk i ustaw właściwość przycisku **Drukuj częściowy raport obrachunkowy sprzedaży częściowej**.
    3. Dodaj nowy przycisk i ustaw właściwość przycisku **Drukuj obrachunkowy końcowy raport sprzedaży**.
    4. Na stronie **Harmonogram dystrybucji** uruchom zadanie **1090**, aby przenieść zmiany do bazy danych kanału.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej

Aby włączyć ręczne wykonywanie odroczonej rejestracji fiskalnej, należy dodać nowy przycisk do układu punktu sprzedaży.

- Na stronie **Siatka przycisków** postępuj zgodnie instrukcjami w [Dodawanie operacji punktu sprzedaży do układów aplikacji POS przy użyciu projektanta siatki przycisków](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters), aby zainstalować projektanta i zaktualizować układ POS.

    1. Wybierz układ do zaktualizowania.
    2. Dodaj nowy przycisk i ustaw właściwość przycisku **Zakończ proces rejestracji fiskalnej**.
    3. Na stronie **Harmonogram dystrybucji** uruchom zadanie **1090**, aby przenieść zmiany do bazy danych kanału.
