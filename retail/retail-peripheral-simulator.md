---
title: "Symulator urządzeń peryferyjnych sieci sprzedaży"
description: "W tym temacie opisano narzędzie symulatora urządzeń peryferyjnych zawartego w programie Microsoft Dynamics 365 for Operations — Handel detaliczny."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: 11a4633b0a1254f3a8cbdcba8d7aa99bb7c936c1
ms.contentlocale: pl-pl
ms.lasthandoff: 04/26/2017


---

# <a name="retail-peripheral-simulator"></a>Symulator urządzeń peryferyjnych sieci sprzedaży

[!include[banner](includes/banner.md)]


W tym temacie opisano narzędzie symulatora urządzeń peryferyjnych zawartego w programie Microsoft Dynamics 365 for Operations — Handel detaliczny.

<a name="overview"></a>Przegląd
--------

Symulator urządzeń peryferyjnych w programie Microsoft Dynamics 365 for Operations — Handel detaliczny jest narzędziem, które pomaga konfigurować i testować urządzenia peryferyjne używane w środowiskach sieci sprzedaży oraz rozwiązywać problemy z tymi urządzeniami. Symulatora urządzeń peryferyjnych można używać w celu usprawnienia testowania urządzeń peryferyjnych w sklepach detalicznych oraz do izolowania problemów spowodowanych niepoprawną konfiguracją lub nieprawidłowym działaniem sterowników urządzeń. Symulator urządzeń peryferyjnych zawiera aplikację komputerową, która udostępnia wirtualne wersje urządzeń obsługiwanych przez program Microsoft Dynamics 365 for Operations — Handel detaliczny. Sekcja dla każdego urządzenia wirtualnego przedstawia interakcje między urządzeniem a punktem sprzedaży detalicznej (POS). Może także służyć jako źródło danych wejściowych dla różnych scenariuszy punktu sprzedaży. Symulator urządzeń peryferyjnych obsługuje interakcję między punktem sprzedaży a następującymi urządzeniami wirtualnymi:

-   **Drukarka** — symulator urządzeń peryferyjnych może pokazywać paragony skonfigurowane dla drukarki w punkcie sprzedaży.
-   **Wyświetlacz wierszowy** — w wyświetlaczu wierszowym można skonfigurować wyświetlanie operacji wykonywanych na fizycznym wyświetlaczu wierszowym.
-   **Czytnik kart magnetycznych (MSR)** — z symulatora urządzeń peryferyjnych mogą być wysyłane symulowane zdarzenia sczytywania paska magnetycznego do punktu sprzedaży.
-   **Szuflada** — można symulować fizyczną szufladę kasową.
-   **Szuflada 2** — poprzez utworzenie drugiej szuflady kasowej w symulatorze urządzeń peryferyjnych można symulować scenariusze jednej kasy punktu sprzedaży z dwoma aktywnymi zmianami.
-   **Skaner** — wirtualny skaner kodów kreskowych obsługiwany przez symulator urządzeń peryferyjnych może wysyłać zdarzenia zeskanowania kodów kreskowych.
-   **Waga** — wirtualna waga umożliwia symulowanie interakcji ważonych towarów z punktem sprzedaży.
-   **Konsola do wpisywania osobistych numerów identyfikacyjnych (PIN)** — można symulować operacje wykonywane na konsoli PIN. **Uwaga:** W tym celu należy zaimplementować obsługę fizycznej konsoli PIN za pośrednictwem aplikacji łącznika płatności.
-   **Przechwytywanie podpisu** — symulator urządzeń peryferyjnych zawiera wirtualne urządzenie do przechwytywania podpisów, w którym można skonfigurować monitowanie o podpisy wymagane w niektórych operacjach płatności, takich jak wpłaty na konto odbiorcy.

Symulator umożliwia także symulowanie zdarzeń czytnika podłączanego do klawiatury, które pochodzą ze skanera kodów kreskowych i czytnika kart magnetycznych. Symulator wirtualnych urządzeń peryferyjnych w szczególności obsługuje urządzenia zgodne z mechanizmem Object Linking and Embedding for Retail POS (OPOS).

## <a name="key-scenarios"></a>Główne scenariusze
### <a name="troubleshooting"></a>Rozwiązywanie problemów

Symulator urządzeń peryferyjnych może służyć do rozwiązywanie problemów z instalacją urządzeń. Jeśli nie masz symulatora peryferyjnych ani drugiego urządzenia tej samej klasy, może być trudno określić, skąd pochodzą problemy. Jednak mając symulator urządzeń peryferyjnych, można skonfigurować urządzenia wirtualne i uruchomić te same ścieżki kodu i logikę biznesową, które są używane na urządzeniach fizycznych. Z punktu widzenia symulatora urządzeń peryferyjnych zasadnicza różnica między urządzeniami wirtualnymi i fizycznymi dotyczy obiektu usługi (sterownika urządzenia). W urządzeniach fizycznych obiekt usługi jest dostarczany przez producenta urządzenia. Z drugiej strony dla symulatora urządzeń peryferyjnych obiekty usług są dostarczane wewnętrznie przez symulator. Gdy symulator urządzeń peryferyjnych działa prawidłowo, a urządzenie nie działa poprawnie po zmianie jego nazwy w profilu sprzętu na nazwę rzeczywistego urządzenia, można założyć, że istnieje problem z obiektem usługi dostarczonym przez producenta.

### <a name="training"></a>Szkolenie

Za pomocą symulatora urządzeń peryferyjnych można dodać realistyczną warstwę do szkolenia kasjerów, gdy fizyczna instalacja sprzętu nie jest dostępna. Gdy symulator urządzeń peryferyjnych jest ujęty w scenariuszach szkoleń, kasjer może bardziej skutecznie wykonywać czynności w punkcie sprzedaży poprzez dostarczanie danych wejściowych takich jak skany kodów kreskowych produktów i przeciągnięcia pasków magnetycznych kart upominkowych, a następnie obserwowanie, które paragony są drukowane dla konkretnych transakcji.

### <a name="testing"></a>Testowanie

Symulator urządzeń peryferyjnych może służyć do testowania kodów kreskowych produktów, formatów paragonów i tak dalej, bez konieczności instalowania fizycznego sprzętu w środowisku wirtualnym. Ponieważ sprzęt fizyczny nie jest wymagany i nie trzeba instalować oprogramowania klienckiego punktu sprzedaży na stacji sprzętowej ani fizycznym komputerze, można szybciej testować zmiany wprowadzane w systemach zaplecza.

## <a name="set-up-the-peripheral-simulator"></a>Konfigurowanie symulatora urządzeń peryferyjnych
### <a name="set-up-a-hardware-profile"></a>Konfigurowanie profilu sprzętu

1.  Aby skonfigurować symulator urządzeń peryferyjnych, kliknij kolejno opcje **Handel detaliczny i inny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile sprzętu**.
2.  Aby utworzyć nowy profil, kliknij przycisk **Nowy**.
3.  Wprowadź wartości w polach **Numer profilu** i **Opis**.
4.  Skorzystaj z poniższej tabeli, aby skonfigurować urządzenia wirtualne wymagające przetestowania. Poniżej znajdują się wyjaśnienia dotyczące kolumn tabeli:
    -   **Urządzenie** — ta kolumna nadaje nazwę skróconej karcie, którą się później rozwija w celu skonfigurowania urządzenia.
    -   **Typ urządzenia** — ta kolumna nadaje wartość, którą się później wybiera w polu opisanym nazwą urządzenia.
    -   **Nazwa urządzenia** — ta kolumna nadaje dokładną wartość, którą się później wprowadza jako nazwę urządzenia. **Ważne:** Nadane tutaj nazwy urządzeń są wymagane, ponieważ stacja sprzętowa wykorzystuje te konkretne nazwy do adresowania urządzeń. Jeśli nie skorzystasz z tych konkretnych nazw, urządzenie będzie bezużyteczne.

    | Urządzenie            | Typ urządzenia | Nazwa urządzenia              |
    |-------------------|-------------|--------------------------|
    | Drukarka           | OPOS        | MockOPOSPrinter          |
    | Wyświetlacz wierszowy      | OPOS        | MockOPOSLineDisplay      |
    | MSR               | OPOS        | MockOPOSMSR              |
    | Szuflada            | OPOS        | MockOPOSDrawer1          |
    | Drawer2           | OPOS        | MockOPOSDrawers          |
    | Skaner           | OPOS        | MockOPOSScanner          |
    | Skalowanie             | OPOS        | MockOPOSScale            |
    | Konsola PIN           | OPOS        | MockOPOSPinPad           |
    | Przechwytywanie podpisu | OPOS        | MockOPOSSignatureCapture |

**Uwaga:** Nie jest wymagana żadna konkretna konfiguracja profilu sprzętu do symulowania zdarzeń czytników podłączanych do klawiatury ze skanera kodów kreskowych i czytnika kart magnetycznych.

### <a name="assign-the-hardware-profile-to-a-register"></a>Przypisywanie profilu sprzętu do kasy

1.  Po utworzeniu profilu sprzętu wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Rejestry**.
2.  Na liście **Rejestry punktu sprzedaży** kliknij łącze w polu **Numer rejestru** dotyczącym kasy, która ma używać symulatora urządzeń peryferyjnych.
3.  Kliknij przycisk **Edytuj**.
4.  W sekcji **Profile** w polu **Profil sprzętu** wybierz profil sprzętu utworzony dla wirtualnych urządzeń peryferyjnych.
5.  Kliknij przycisk **Zapisz**.

### <a name="synchronize-changes-to-the-channel-database"></a>Synchronizowanie zmian z bazą danych kanału

1.  Wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**.
2.  Wybierz harmonogram dystrybucji **1090**.
3.  Kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.

Po zsynchronizowaniu danych nowy profil sprzętu i modyfikacje kasy są dostępne w bazie danych kanału.

## <a name="install-the-peripheral-simulator"></a>Instalowanie symulatora urządzeń peryferyjnych
1.  Wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile sprzętu**.
2.  Kliknij kolejno opcje **Pobierz** i **PeripheralSimulator**. **Uwaga:** Aby można było pobrać symulator urządzeń peryferyjnych, należy wyłączyć blokowanie wyskakujących okienek.
3.  Po zakończeniu pobierania otwórz folder **Pobrane** i kliknij dwukrotnie plik **VirtualPeripherals.msi**, aby uruchomić instalatora.
4.  Zainstaluj symulator urządzeń peryferyjnych przy użyciu ustawień domyślnych.

Oprócz symulatora urządzeń peryferyjnych należy zainstalować wspólne obiekty formantów od Monroe Consulting Services. W przeciwnym razie symulator urządzeń peryferyjnych nie będzie działał poprawnie. Aby pobrać wspólne obiekty formantów, przejdź do strony <http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Używanie symulatora urządzeń peryferyjnych
Aby uruchomić symulator urządzeń peryferyjnych, kliknij przycisk **Start** na komputerze, wpisz wyrażenie **Symulator urządzeń peryferyjnych sieci sprzedaży** (lub Retail peripheral simulator), a następnie zaznacz aplikację, gdy pojawi się w wynikach wyszukiwania. Po uruchomieniu symulatora urządzeń peryferyjnych kliknij nazwę urządzenia, aby zobaczyć obsługiwane urządzenia. Urządzenia te będą wyświetlane jako karty po lewej stronie okna. Aby wyświetlić określone urządzenie, kliknij jego kartę.

### <a name="line-display-capabilities"></a>Funkcje wyświetlacza wierszowego

Wyświetlacz wierszowy jest pierwszym urządzeniem wymienionym w symulatorze urządzeń peryferyjnych. Po skonfigurowaniu wyświetlacza wierszowego pokazuje on pozycje w wierszach skanowane podczas transakcji w punkcie sprzedaży. Oprócz pozycji w wierszach na ekranie widać sumy należne po wybraniu metody płatności w punkcie sprzedaży. Jest również wyświetlane saldo należności, jeśli wprowadzono metodę płatności, ale transakcja nie została jeszcze w pełni opłacona. Gdy punkt sprzedaży nie jest używany, może się pojawić komunikat informujący, że szuflada kasowa jest zamknięta. Komunikat należy skonfigurować na skróconej karcie **Wyświetlacz wierszowy** w profilu sprzętu.

### <a name="cash-drawer-capabilities"></a>Funkcje szuflady kasowej

Szuflada kasowa jest drugim urządzeniem wymienionym w symulatorze urządzeń peryferyjnych. Gdy profil sprzętu jest skonfigurowany do używania wirtualnych szuflad kasowych, aplikacja punktu sprzedaży otwiera szufladę aktywnej zmiany w odpowiedzi na operacje wykonywane w szufladzie, np. deklaracje środków płatniczych, tak aby kasjer mógł wprowadzić zmiany lub wpłacić gotówkę podczas standardowych transakcji płacenia za towary przy kasie i wychodzenia z nimi ze sklepu. Wirtualne szuflady kasowe mają etykiety **Główna szuflada** i **Szuflada pomocnicza**. Etykiety te reprezentują odpowiednio szuflady Szuflada i Szuflada 2 szuflady w profilu sprzętu. Gdy szuflada jest zamknięta, widać obraz zamkniętej szuflady kasowej, a przycisk na zamkniętej szufladzie kasowej nosi nazwę **Otwórz szufladę**. Jeśli klikniesz ten przycisk, obraz zostanie zastąpiony obrazem otwartej szuflady kasowej, aby wskazać, że szuflada jest teraz otwarta. Przycisk na otwartej szufladzie kasowej ma etykietę **Zamknij szufladę**. Szuflada kasowa może być otwierana przez kilka operacji w punkcie sprzedaży. Większość operacji nie może być kontynuowana, gdy szuflada kasowa jest otwarta. Wyjątkami są niektóre procedury na koniec dnia. Jeśli użytkownik w punkcie sprzedaży otrzyma komunikat o błędzie z informacją, że nie można wykonać operacji, gdy szuflada kasowa jest otwarta, w celu kontynuowania trzeba zamknąć wirtualną lub fizyczną szufladę kasową. Jeśli szuflada kasowa jest oznaczona w profilu sprzętu jako **Udostępniona**, system przed wykonaniem operacji nie sprawdza, czy szuflada jest zamknięta. Operacja jest kontynuowana w zwykły sposób, nawet jeśli szuflada kasowa jest otwarta. To zachowanie obsługuje scenariusze, gdy szuflady kasowe są współużytkowane przez sprzedawców, gdzie jeden sprzedawca używa szuflady kasowej, a drugi wykonuje niepowiązane zadania z tym na swoim własnym urządzeniu POS. Modyfikacje wprowadzone w szufladzie kasowej są widoczne dopiero po zakończeniu bieżącej zmiany i rozpoczęciu nowej.

### <a name="msr-capabilities"></a>Funkcje czytnika kart magnetycznych

Symulator urządzeń peryferyjnych zapewnia rozbudowaną obsługę operacji na wirtualnych czytnikach kartach magnetycznych w trybie OPOS lub czytnika podłączanego do klawiatury. Tryb OPOS wymaga, aby czytnik MSR był skonfigurowany w profilu sprzętu do pracy jako urządzenie OPOS. Tryb czytnika podłączanego do klawiatury tylko wysyła zdarzenia takiego czytnika do systemu Microsoft Windows. Poza różnicami w konfiguracjach tryby OPOS i czytnika podłączanego do klawiatury różnią się w następujący sposób:

-   Aplikacja kliencka punktu sprzedaży obsługuje czytniki MSR punktu sprzedaży w określonych scenariuszach, np. używania danych z pasków magnetycznych do wprowadzania kart lojalnościowych lub upominkowych.
-   W trybie czytnika podłączanego do klawiatury symulator urządzeń peryferyjnych wysyła dane z czytnika do pola aktywnego w momencie wysyłania danych. To zachowanie jest podobne do zachowania występującego podczas wprowadzania danych za pomocą klawiatury. Aby używać czytnika kart magnetycznych jako czytnika podłączanego do klawiatury, użytkownik musi się przełączyć do aplikacji Retail Modern POS (MPOS) i sprawdzić, czy dane zostały odebrane do właściwego pola. W związku z tym można skonfigurować opóźnienie, tak aby użytkownik miał czas na upewnienie się, że dane będą wysyłane do odpowiedniego pola.

#### <a name="testing-gift-and-payment-card-swipes"></a>Testowanie działania przeciągnięć kart upominkowych i płatniczych

Wirtualny czytnik kart magnetycznych dostępny w symulatorze urządzeń peryferyjnych umożliwia również skonfigurowanie określonych danych MSR w celu testowania scenariuszy przeciągnięć kart upominkowych i płatniczych. Aby utworzyć kartę, kliknij przycisk ze znakiem plusa (**+**) i wybierz odpowiedni typ karty. Następnie określ numer karty lub dane śledzenia, które powinny być wysyłane do punktu sprzedaży razem miesiącem i rokiem wygaśnięcia definiowanej karty. Wartość wybrana w polu **Typ karty** jest tylko etykietą, którą można mapować na kartę. Ta etykieta ułatwia identyfikowanie kart, gdy są przeciągane przez symulator urządzeń peryferyjnych. Karty, które zostały skonfigurowane w symulatorze urządzeń peryferyjnych, można wybierać przy użyciu przycisków strzałek w lewo (**&lt;**) i w prawo (**&gt;**) umieszczonych nad obrazem karty. Karty można edytować i usuwać za pomocą przycisków **Edytuj** i **Usuń** umieszczonych obok przycisku ze znakiem plusa (**+**).

### <a name="pin-pad"></a>Konsola PIN

Można skonfigurować symulator konsoli PIN do symulowania konsoli PIN OPOS. Gdy w punkcie sprzedaży jest wykonywane transakcja elektronicznego przelewu środków pieniężnych (EFT) wymagająca wprowadzenia numeru PIN, stacja sprzętu wywołuje urządzenie PIN, aby wysłało monit o wprowadzanie numeru PIN. Aby konsola PIN w symulatorze urządzeń peryferyjnych działała, wymaga obsługi aplikacji łącznika płatności EFT.

### <a name="printer"></a>Drukarka

Wirtualne urządzenie peryferyjne drukarki po prostu pokazuje paragony drukowane z punktu sprzedaży. Jeśli operacji drukowania generuje wiele paragonów, można przewijać te paragony.

#### <a name="configure-receipt-printing"></a>Konfigurowanie drukowania etykiet

1.  Wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile sprzętu**.
2.  Wybierz profil sprzętu utworzony dla wirtualnych urządzeń peryferyjnych.
3.  Na skróconej karcie **Drukarka** kliknij przycisk **Edytuj**.
4.  W polu **Identyfikator profilu paragonów** wybierz profil paragonów.
5.  Kliknij przycisk **Zapisz**.

### <a name="scale"></a>Skalowanie

Gdy do transakcji w punkcie sprzedaży jest dodawany ważony produkt, a jest skonfigurowana waga, aplikacja punktu sprzedaży pobiera masę z wagi. W przypadku zarówno wagi wirtualnej, jak i fizycznej, produkt można dodać do transakcji tylko po uprzednim zdefiniowaniu produktu i wagi. Przed dodaniem ważonego produktu do transakcji przejdź do wagi w symulatorze urządzeń peryferyjnych i użyj przycisków ze znakiem plusa (**+**) i minusa (**–**), aby dostosować masę, jaką ma zgłaszać waga. Można także wprowadzić żądaną masę bezpośrednio w polu **Bieżąca wartość**. Jednostki masy w wadze można dostosować za pomocą przycisków ze znakiem plusa (**+**), **Edytuj** i **Usuń**. W ten sposób jednostki można określić na podstawie ważonych produktów lub ustawień regionalnych, z którymi jest używana waga.

#### <a name="configure-a-scale-product"></a>Konfigurowanie produktu ważonego

1.  Wybierz kolejno opcje **Handel detaliczny i** **inny** &gt; **Produkty i kategorie** &gt; **Zwolnione produkty według kategorii**.
2.  Otwórz rekord produktu.
3.  Wybierz produkt do zważenia.
4.  Na skróconej karcie **Handel detaliczny** przestaw opcję **Produkt ważony** z wartości **Nie** na **Tak**.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synchronizowanie zmian z bazą danych kanału

1.  Wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**.
2.  Wybierz harmonogram dystrybucji **1040**.
3.  Kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.

Gdy dane są zsynchronizowane, podczas dodawania ważonego produktu do transakcji w punkcie sprzedaży aplikacja punktu sprzedaży sprawdza masę w wadze.

### <a name="signature-capture"></a>Przechwytywanie podpisu

Wirtualne urządzenie do przechwytywania podpisów monituje użytkownika o złożenie podpisu na wirtualnej konsoli do składania podpisów, gdy używana metoda płatności wymaga podpisu. Użytkownik może zaakceptować podpis, a wtedy zostanie on wyświetlony w aplikacji punktu sprzedaży. Kasjer może następnie zaakceptować podpis. Podpis zostanie zapisany razem z metodą płatności i wraz z innymi danymi transakcji zsynchronizowany w systemach zaplecza.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Konfigurowanie wymogu podpisu w metodzie płatności

1.  Wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Kanały** &gt; **Sklepy sieci sprzedaży** &gt; **Wszystkie sklepy sieci sprzedaży**.
2.  Wybierz sklep sieci sprzedaży.
3.  Kliknij przycisk **Edytuj**.
4.  Kliknij opcję **Konfiguracja**, a następnie w sekcji **Konfiguracja** kliknij opcję **Metody płatności**.
5.  Kliknij przycisk **Edytuj**.
6.  Wybierz metodę płatności, która wymaga podpisu.
7.  W sekcji **Ogólne** w obszarze **Przechwytywania podpisu** ustaw w opcji **Użycie urządzenia do przechwytywania podpisu** wartość **Tak**.
8.  W polu **Minimalna kwota przechwytywania podpisu** wprowadź minimalną kwotę, która powinna uruchamiać operację przechwytywania podpisu.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synchronizowanie zmian z bazą danych kanału

1.  Wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**.
2.  Wybierz harmonogram dystrybucji **1070**.
3.  Kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.

Gdy dane są zsynchronizowane, metoda płatności wymaga podpisu, a kwota spełnia wymóg progu dla podpisu, aplikacja punktu sprzedaży monituje o złożenie podpisu na wirtualnym urządzeniu do przechwytywania podpisów.

## <a name="additional-configuration"></a>Dodatkowa konfiguracja
Można edytować plik konfiguracji symulatora urządzeń peryferyjnych, aby lepiej pasował do testowanego scenariusza. Plik konfiguracji znajduje się w ścieżce C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Plik konfiguracji definiuje jednostki dostępne do testowania w wadze, rodzaje kart dostępne do testowania i typy kodów kreskowych. Na przykład zmieniając wartości tekstowe w pliku konfiguracji, można dodać nowy typ karty lub jednostkę miary, którą będzie może wybierać w czasie wykonywania. Nowe wartości będą widoczne po ponownym uruchomieniu aplikacji.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Działania wykonywane w symulatorze urządzeń peryferyjnych są rejestrowane w symulatorze. Dziennik znajduje się w ścieżce C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Symulator urządzeń peryferyjnych również raportuje problemy do dziennika zdarzeń systemu Windows, który znajduje się w ścieżce **Dzienniki aplikacji i usług** &gt; **Microsoft** &gt; **DynamicsAX**. Jeśli zmiany wprowadzone w profilu sprzętu lub innych obszarach nie są widoczne podczas korzystania z aplikacji MPOS lub symulatora urządzeń peryferyjnych, sprawdź zadania harmonogramu dystrybucji użyte w celu zsynchronizowania danych z bazą danych kanału. Jeśli zmiany zostały zsynchronizowane, ale nadal nie są widoczne w punkcie sprzedaży, uruchom ponownie aplikację kliencką punktu sprzedaży. Modyfikacje skonfigurowanych szuflad kasowych zaczynają obowiązywać dopiero po utworzeniu nowej zmiany. W związku z tym jeśli wprowadzisz modyfikacje szuflad kasowych, to w celu przetestowania nowej konfiguracji szuflady kasowej koniecznie zamknij istniejącą zmianę. Czasami jeśli po zainstalowaniu wspólnych obiektów formantów od Monroe Consulting Services zostanie zainstalowany sterownik producenta, sterownik może spowodować nieprawidłowe działanie formantów. W takim przypadku należy ponownie zainstalować wspólne obiekty formantów.

<a name="see-also"></a>Informacje dodatkowe
--------

[Przegląd urządzeń peryferyjnych sieci sprzedaży](retail-peripherals-overview.md)




