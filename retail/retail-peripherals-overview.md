---
title: "Przegląd urządzeń peryferyjnych sieci sprzedaży"
description: "W tym temacie wyjaśniono pojęcia, które są związane z urządzenia peryferyjnymi sieci sprzedaży. Opisano różne sposoby podłączania urządzeń peryferyjnych do punktu sprzedaży (POS) oraz składniki, które są odpowiedzialne za zarządzanie połączeniem z punktem sprzedaży."
author: rubencdelgado
manager: AnnBe
ms.date: 06/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, UnifiedOperations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611, Retail Version
ms.translationtype: Human Translation
ms.sourcegitcommit: 52a16be4b07eafb493c7fd7ad52a6d9d1bb9ee89
ms.openlocfilehash: 77049ba4c9c39cd44f1919b672deaf700b91357d
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# <a name="retail-peripherals-overview"></a>Przegląd urządzeń peryferyjnych sieci sprzedaży

[!include[banner](includes/banner.md)]


W tym temacie wyjaśniono pojęcia, które są związane z urządzenia peryferyjnymi sieci sprzedaży. Opisano różne sposoby podłączania urządzeń peryferyjnych do punktu sprzedaży (POS) oraz składniki, które są odpowiedzialne za zarządzanie połączeniem z punktem sprzedaży.

## <a name="concepts"></a>Koncepcje

### <a name="pos-registers"></a>Rejestry punktu sprzedaży

Nawigacja: Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Rejestry**. Kasa w punkcie sprzedaży (POS) to jednostka używana do definiowania właściwości konkretnego wystąpienia punktu sprzedaży. Cechy te obejmują profil sprzętu lub konfigurację urządzeń peryferyjnych sieci sprzedaży, które będą używane w kasie, sklep, do którego kasa jest mapowana, oraz wizualne środowisko użytkownika logującego się w tej kasie.

### <a name="devices"></a>Urządzenia

Nawigacja: Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Urządzenia**. Urządzenie to jednostka, która reprezentuje fizyczne wystąpienie urządzenia zmapowanego do kasy POS. Po utworzeniu urządzenie jest mapowane do kasy w punkcie sprzedaży. Jednostka urządzenia śledzi informacje o tym, kiedy kasa punktu sprzedaży jest aktywowana, jaki typ klienta jest używany i jaki pakiet aplikacji został wdrożony na konkretnym urządzeniu. Urządzenia mogą być mapowane do następujących typów aplikacji: Retail Modern POS, Retail Cloud POS, Retail Modern POS dla systemu Windows Phone, Retail Modern POS dla systemu Android i Retail Modern POS dla systemu iOS.

### <a name="retail-modern-pos"></a>Nowoczesny punkt sprzedaży detalicznej

Modern POS to oprogramowanie punktu sprzedaży dla systemu Microsoft Windows. Może być instalowane w systemach operacyjnych Windows 10.

### <a name="cloud-pos"></a>Cloud POS

Cloud POS jest przeglądarkową wersją programu Modern POS, którą można obsługiwać z przeglądarki internetowej.

### <a name="modern-pos-for-ios"></a>Modern POS for iOS

Modern POS for iOS jest wersją programu Modern POS przeznaczoną dla systemu iOS, która może być instalowana na urządzeniach z systemem iOS.

### <a name="modern-pos-for-android"></a>Modern POS for Android

Modern POS for Android jest wersją programu Modern POS przeznaczoną dla systemu Android, która może być instalowana na urządzeniach z systemem Android.

### <a name="pos-peripherals"></a>Urządzenia peryferyjne punktu sprzedaży

Urządzenia peryferyjne punktu sprzedaży to urządzenia, które wspierają funkcje punktu sprzedaży. Te urządzenia peryferyjne są zwykle podzielone na określone klasy. Aby uzyskać więcej informacji na temat tych klas, zobacz sekcję „Klasy urządzeń” w tym temacie.

### <a name="hardware-station"></a>Stacja sprzętowa

Nawigacja: Kliknij kolejno opcje **Handel detaliczny** &gt; **Kanały** &gt; **Sklepy sieci sprzedaży** &gt; **Wszystkie sklepy sieci sprzedaży**. Zaznacz sklep i kliknij skróconą kartę **Stacje sprzętowe**. Ustawienie **Stacja sprzętowa** to ustawienie na poziomie kanału służące do definiowania wystąpień, w których zostanie wdrożona logika urządzeń peryferyjnych sieci sprzedaży. To ustawienie na poziomie kanału jest używane do określenia charakterystyki stacji sprzętowej. Służy również do wyświetlenia listy stacji sprzętowych, które są dostępne dla wystąpienia programu Modern POS w danym sklepie. Stacja sprzętowa jest wbudowana w programie Modern POS dla systemu Windows. Stacje sprzętowe mogą również być instalowane niezależnie jako autonomiczne wystąpienia program Microsoft Internet Information Services (IIS). W takim przypadku są dostępne przez sieć.

### <a name="hardware-profile"></a>Profil sprzętu

Nawigacja: Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile sprzętu**. Profil sprzętu to lista urządzeń skonfigurowanych dla kasy w punkcie sprzedaży lub stacji sprzętowej. Profil sprzętu można mapować bezpośrednio do kasy w punkcie sprzedaży lub do stacji sprzętowej.

## <a name="devices-classes"></a>Klasy urządzeń
Urządzenia peryferyjne sieci sprzedaży są zwykle podzielone na klasy. W tej sekcji opisano i ogólnie omówiono urządzenia obsługiwane przez program Modern POS.

### <a name="printer"></a>Drukarka

Drukarki obejmują tradycyjne drukarki paragonów w punktach sprzedaży oraz drukarki całostronicowe. Drukarki są obsługiwane poprzez mechanizm Object Linking and Embedding dla programu Retail POS (OPOS) i przez interfejsy sterowników systemu Microsoft Windows. Można używać maksymalnie dwóch drukarek w tym samym czasie. Ta funkcja obsługuje scenariusze, gdzie na drukarkach paragonów są drukowane pokwitowania dla klientów płacących za towary przy kasie i wychodzących z nimi ze sklepu, natomiast zamówienia klientów, które zawierają więcej informacji, są drukowane na drukarce całostronicowej. Drukarki paragonów mogą być podłączone bezpośrednio do komputera przez port USB, podłączone do sieci przez port Ethernet lub połączone za pośrednictwem interfejsu Bluetooth.

### <a name="scanner"></a>Skaner

Można używać maksymalnie dwóch skanerów kodów kreskowych w tym samym czasie. Ta funkcja obsługuje scenariusze, gdzie skaner bardziej mobilny jest używany do skanowania dużych i ciężkich przedmiotów, podczas gdy skaner stacjonarny jest stosowany do większości przedmiotów o standardowych wymiarach, co ma przyspieszyć finalizacji zakupu (obsługę przy kasie). Skanery mogą być obsługiwane przez mechanizm OPOS, platformę uniwersalną systemu Windows (UWP) lub interfejsy czytników podłączanych do klawiatury. W celu podłączenia skanera do komputera można użyć interfejsu USB lub Bluetooth.

### <a name="msr"></a>MSR

Przy użyciu sterowników OPOS można skonfigurować jeden czytnik kart magnetycznych (MSR) podłączany przez USB. Jeśli chcesz używać autonomicznego czytnika MSR do płacenia przy użyciu systemu elektronicznego przelewu środków pieniężnych (EFT), czytniki MSR muszą być zarządzane przez aplikację łącznikową płatności. Autonomiczne czytniki MSR mogą służyć do wprowadzania danych lojalnościowych klientów, logowania pracowników i wprowadzania danych kart upominkowych niezależnie od aplikacji łącznikowej płatności.

### <a name="cash-drawer"></a>Szuflada kasowa

W jednym profilu sprzętu mogą być obsługiwane dwie szuflady kasowe. Ta funkcja umożliwia istnienie dwóch aktywnych zmian dla każdej kasy w tym samym czasie. W przypadku zmiany wspólnej lub szuflady kasowej używanej równocześnie przez wiele przenośnych urządzeń punktu sprzedaży dozwolona jest tylko jedna szuflada kasowa w jednym profilu sprzętu. Szuflady kasowe mogą być podłączone bezpośrednio do komputera przez port USB, podłączone do sieci lub podłączone do drukarki paragonów przez interfejs RJ12. W niektórych przypadkach szuflady kasowe można również podłączać za pomocą interfejsu Bluetooth.

### <a name="line-display"></a>Wyświetlacz wierszowy

Wyświetlacze wierszowe służą do wyświetlania produktów, sald transakcji i innych użytecznych informacji klientowi podczas transakcji. Jeden wyświetlacz wierszowy można podłączyć do komputera przez interfejs USB przy użyciu sterowników OPOS.

### <a name="signature-capture"></a>Przechwytywanie podpisu

Urządzenia do przechwytywania podpisu można podłączyć bezpośrednio do komputera przez port USB przy użyciu sterowników OPOS. Gdy zostanie skonfigurowana funkcja przechwytywania podpisu, klient będzie monitowany o zalogowanie się na urządzeniu. Po złożeniu podpisu będzie on wyświetlany kasjerowi do akceptacji.

### <a name="scale"></a>Skalowanie

Wagę można podłączyć do komputera przez interfejs USP przy użyciu sterowników OPOS. Gdy do transakcji zostanie dodany produkt oznaczony jako „Ważony”, aplikacja punktu sprzedaży odczyta masę z wagi, doda produkt do transakcji i użyje ilości otrzymanej z wagi.

### <a name="pin-pad"></a>Konsola PIN

Konsole do wpisywania osobistych numerów identyfikacyjnych (PIN) są obsługiwane za pośrednictwem mechanizmu OPOS, ale muszą być zarządzane za pośrednictwem aplikacji łącznika płatności.

### <a name="secondary-display"></a>Ekran dodatkowy

Po skonfigurowaniu ekranu dodatkowego na ekranie numer 2 w systemie Windows będą pokazywane podstawowe informacje. Zadaniem ekranu dodatkowego jest obsługa rozszerzenia niezależnego dostawcy oprogramowania (ISV), ponieważ w standardzie ekran ten nie jest konfigurowalny i pokazuje ograniczoną treść.

### <a name="payment-device"></a>Urządzenie płatnicze

Obsługa urządzeń płatniczych jest implementowana za pośrednictwem aplikacji łącznika płatności. Urządzenia płatnicze mogą wykonywać jedną lub wiele funkcji realizowanych przez inne klasy urządzeń. Na przykład urządzenie płatnicze może funkcjonować jako czytnik kart magnetycznych (MSR)/innych, wyświetlacz liniowy, urządzenie do przechwytywania podpisu lub konsola PIN. Obsługa urządzeń płatniczych jest implementowana niezależnie od obsługi urządzeń autonomicznych zapewnianej innym urządzeniom uwzględnionym w profilu sprzętu.

## <a name="supported-interfaces"></a>Obsługiwane interfejsy
### <a name="opos"></a>OPOS

Aby zagwarantować możliwość współpracy jak największej gamy urządzeń z programem Microsoft Dynamics 365 for Retail, podstawową platformą obsługi urządzeń peryferyjnych sieci sprzedaży w tym programie jest mechanizm OLE for POS stanowiący branżowy standard. Standard OLE for POS sprzedaży został opracowany przez amerykańską Krajową Federację Sprzedawców Detalicznych (NRF), który ustanawia branżowe protokoły komunikacyjne dla urządzeń peryferyjnych sieci sprzedaży. OPOS jest powszechnie przyjętą implementacją standardu OLE for POS. Został opracowany w połowie lat 1990-ych od tego czasu był kilkukrotnie aktualizowany. Standard OPOS określa architekturę sterownika urządzenia, która umożliwia łatwą integrację urządzeń punktu sprzedaży z systemami punktu sprzedaży opartymi na systemie Windows. Formanty OPOS zarządzają komunikacją między zgodnymi urządzeniami a oprogramowaniem punktu sprzedaży. Formant OPOS składa się z dwóch części:

-   **Obiekt formantu** — Obiekt formantu klasy urządzeń (na przykład wyświetlaczu wierszowym) udostępnia interfejs dla programu komputerowego. Monroe Consulting Services ([www.monroecs.com](http://www.monroecs.com/)) dostarcza zestaw standardowych obiektów formatów OPOS, które są znane jako wspólne obiekty formantów (CCO). Obiekty CCO są używane do testowania składnika punktu sprzedaży w programie Microsoft Dynamics 365 for Retail. W związku z tym testowanie pomaga zagwarantować, że jeśli program Microsoft Dynamics 365 for Retail obsługuje klasę urządzeń za pośrednictwem mechanizmu OPOS, będzie obsługiwanych wiele typów urządzeń, o ile tylko producent dostarczy obiekt usługi zaprojektowany dla tego mechanizmu. Nie trzeba osobno testować każdego typu urządzenia.
-   **Obiekt usługi** — Obiekt usługi zapewnia komunikację między obiektem formantu (CCO) a urządzeniem. Zazwyczaj obiekt usługi dla urządzenia jest dostarczany przez producenta urządzenia. Jednak w niektórych przypadkach może być konieczne pobranie obiektu usługi z witryny internetowej producenta. Na przykład może być dostępny nowszy obiekt usługi. Aby odszukać adres witryny producenta w sieci Web, zajrzyj do dokumentacji sprzętu.

[![Obiekt formantu i obiekt usługi](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png) Obsługa implementacji OPOS standardu OLE for POS pomaga zagwarantować, że jeśli producenci urządzeń i wydawcy oprogramowania punktów sprzedaży poprawnie zaimplementowali standard, systemy punktów sprzedaży i obsługiwane urządzenia mogą współpracować, nawet jeśli nie zostały wcześniej przetestowane razem. **Uwaga:** Obsługa standardu OPOS nie gwarantuje współpracy ze wszystkimi urządzeniami, które mają sterowniki OPOS. Program Microsoft Dynamics 365 for Retail musi najpierw obsługiwać ten lub klasę urządzenia za pośrednictwem mechanizmu OPOS. Ponadto obiekty usług nie zawsze są aktualizowane dla najnowszych wersji obiektów CCO. Należy także pamiętać, że zasadniczo jakość obiektów usługi jest różna.

### <a name="windows"></a>Windows

Drukowanie paragonów w punkcie sprzedaży jest zoptymalizowane dla standardu OPOS. Drukowanie przez mechanizm OPOS często jest znacznie szybsze niż drukowanie za pośrednictwem systemu Windows. Dlatego dobrze jest używać standardu OPOS szczególnie w sklepach detalicznych, gdzie są drukowane paragony 40-kolumnowe, a transakcje muszą być szybko realizowane. Dla większości urządzeń używa się formantów OPOS. Jednak niektóre drukarki paragonów OPOS obsługują również sterowniki systemu Windows. Używanie sterownika systemu Windows zapewnia dostęp do najnowszych czcionek i pozwala ustawić jedną drukarkę sieciową dla wielu kas. Istnieją jednak wady używania sterowników systemu Windows. Oto kilka z nich:

-   Gdy są używane sterowniki dla systemu Windows, obrazy przed wydrukowaniem są renderowane. W związku z tym drukowanie najczęściej jest wolniejsze niż w drukarkach wykorzystujących formanty OPOS.
-   Urządzenia podłączone za pośrednictwem drukarki („łańcuchowo”) mogą nie działać poprawnie w przypadku używania sterowników systemu Windows. Na przykład szuflada kasowa może się nie otwierać lub drukarka pokwitowań może działać w nieoczekiwany sposób.
-   Standard OPOS obsługuje także szerszy zestaw zmiennych specyficznych dla drukarek paragonów w handlu detalicznym, takich jak obcinanie papieru czy drukowanie pokwitowań.

Jeśli formanty OPOS są dostępne dla używanej drukarki systemu Windows, drukarka powinna poprawnie współpracować z programem Microsoft Dynamics 365 for Retail.

### <a name="universal-windows-platform"></a>Platforma uniwersalna systemu Windows

W kontekście urządzeń peryferyjnych sieci sprzedaży platforma UWP odnosi się do obsługi urządzeń typu Plug and Play w systemie Windows. Po podłączeniu urządzenia typu Plug and Play do wersji systemu operacyjnego Windows obsługującej tego typu urządzenie nie trzeba instalować dodatkowego sterownika, aby urządzenie działało zgodnie z przeznaczeniem. Na przykład jeśli system Windows wykryje głośnik Bluetooth, system operacyjny wie, że urządzenie ma typ klasy **Głośnik**. W związku z tym traktuje to urządzenie jako głośnik. Nie jest wymagana żadna dodatkowa konfiguracja. W przypadku sprzętu dla punktu sprzedaży można podłączać wiele urządzeń USB, a system Windows rozpozna je jako urządzenia interfejsu HID. Jednakże może nie być w stanie rozpoznać funkcjonalności urządzenia, ponieważ urządzenie nie podaje swojej klasy/typu. W systemie Windows 10 dodano klasy urządzeń skanerów kodów kreskowych i czytników MSR. W związku z tym jeśli urządzenie deklaruje się wobec systemu 10 Windows jako należące do jednej z tych klas, system Windows będzie nasłuchiwał zdarzeń z tego urządzenia we właściwych momentach. Aplikacja Modern POS obsługuje czytniki MSR i skanery zgodne ze standardem UWP. W związku z tym gdy jest gotowa przyjąć dane wejściowe od jednego z takich urządzeń, a urządzenie należące do jednej z podanych klas jest podłączone, urządzenia można użyć. Na przykład jeśli skaner kodów kreskowych UWP jest podłączony do komputera z systemem Windows 10, a dla programu Modern POS skonfigurowanie logowanie przy użyciu kodów kreskowych, skaner kodów kreskowych stanie się aktywny na ekranie logowania. Nie jest wymagana żadna dodatkowa konfiguracja. Stopniowo do systemu Windows są dodawane kolejne klasy urządzeń punktów sprzedaży zgodne ze standardem UWP. Są wśród nich klasy szuflad kasowych i drukarek paragonów. Obsługa tych nowych klas urządzeń wkrótce zostanie dodana w programie Modern POS.

### <a name="keyboard-wedge"></a>Czytnik podłączany do klawiatury

Urządzenia czytników podłączanych do klawiatury wysyłają dane do komputera tak, jakby były one wpisywane z klawiatury. W związku z tym domyślnie pole aktywne w punkcie sprzedaży otrzymuje dane, które są skanowane lub sczytywane z paska magnetycznego. W niektórych przypadkach może to powodować skanowanie niewłaściwych typów danych do nieodpowiednich pól. Na przykład kod kreskowy może być skanowany do pola, które jest przeznaczone do wprowadzania danych karty kredytowej. W wielu przypadkach w punkcie sprzedaży istnieje logika, która rozpoznaje, czy dane wejściowe pochodzą z kodu kreskowego czy z przeciągnięcia karty. W związku z tym dane są obsługiwane prawidłowo. Jednakże gdy urządzenia są skonfigurowane jako zgodne ze standardem OPOS, a nie jako czytniki podłączane do klawiatury, użytkownik ma większą kontrolę nad sposobem wykorzystania danych z tych urządzeń, ponieważ więcej „wie” o urządzeniu, z którego pochodzą dane. Na przykład dane ze skanera kodów kreskowych są automatycznie rozpoznawane jako kod kreskowy, a odnośny rekord w bazie danych jest znajdowany łatwiej i szybciej niż podczas standardowego wyszukiwania uruchamianego dla czytników podłączanych do klawiatury.

### <a name="native-printer"></a>Macierzysta drukarka

Drukarki macierzyste (tzn. należące do typu o nazwie „Urządzenie” w profilu sprzętu) można skonfigurować w taki sposób, aby monitowały użytkownika o wybór drukarki skonfigurowanej dla komputera. Jeżeli zostanie skonfigurowana drukarka typu **Urządzenie**, to gdy program Modern POS napotka polecenia drukowania, użytkownik będzie monitowany o wybór drukarki z listy. To zachowanie różni się od zachowania sterowników systemu Windows, ponieważ w profilu sprzętu typ drukarki **Windows** nie pokazuje listy drukarek. Zamiast tego w polu **Nazwa urządzenia** trzeba podać nazwaną drukarkę.

### <a name="windows"></a>Windows

Typ urządzenia **Windows** jest używany tylko do drukarek. Podczas konfigurowania drukarki systemu Windows w profilu sprzętu należy podać konkretną nazwę drukarki. Jeśli skonfigurowano drukarkę w systemie Windows, to gdy program Modern POS napotka zdarzenie drukowania, przekaże je do tej drukarki. Użytkownik nie będzie monitowany o wybór drukarki.

### <a name="network"></a>Sieć

Szuflady kasowe adresowalne w sieci, drukarki paragonów i terminale płatnicze mogą być używane w sieci albo bezpośrednio przez stację sprzętową obsługującą funkcję komunikacji międzyprocesowej (IPC) wbudowaną w aplikacji Modern POS for Windows, albo za pośrednictwem stacji sprzętowej z usługami IIS w przypadku innych urządzeń klienckich programu Modern POS.

## <a name="hardware-station-deployment-options"></a>Opcje wdrażania stacji sprzętowej
### <a name="ipc-built-in"></a>IPC (wbudowana)

Stacja sprzętowa z funkcją komunikacji międzyprocesowej (IPC) jest wbudowana w aplikacji Modern POS for Windows. Aby użyć stacji sprzętowej z funkcją IPC, przypisz profil sprzętu do kasy, która będzie używać aplikacji Modern POS for Windows. Następnie utwórz stację sprzętową typu **Dedykowana** dla sklepu, w którym kasa będzie używana. Po uruchomieniu aplikacji Modern POS stacja sprzętowa z funkcją IPC będzie aktywna, a skonfigurowane urządzenia peryferyjne punktu sprzedaży będą gotowe do użycia. Jeśli z jakiegoś powodu tymczasowo nie potrzebujesz lokalnych urządzeń, za pomocą operacji **Zarządzaj stacjami sprzętowymi** wyłącz funkcje stacji sprzętowej. Program Modern POS może również używać stacji sprzętowej z funkcją IPC do bezpośredniego komunikowania się z sieciowymi urządzeniami peryferyjnymi.

### <a name="iis"></a>Usługi IIS

Stacji sprzętowej w wersji z usługami IIS lub autonomicznej można używać na dwa sposoby. Deskryptor „IIS” oznacza, że aplikacja punktu sprzedaży łączy się ze stacją sprzętową za pośrednictwem programu Microsoft Internet Information Services. Aplikacja punktu sprzedaży łączy się ze stacją sprzętową IIS za pośrednictwem usług internetowych uruchomionych na komputerze, do którego są podłączone urządzenia. Jeśli są wykorzystywane usługi IIS, urządzenia peryferyjne sieci sprzedaży podłączone do stacji sprzętowej mogą być używane przez dowolną kasę w punkcie sprzedaży znajdującą się w tej samej sieci, co stacja sprzętowa z usługami IIS. Ponieważ tylko aplikacja Modern POS for Windows zawiera wbudowaną obsługę urządzeń peryferyjnych sieci sprzedaży, wszystkie pozostałe aplikacje Modern POS muszą używać stacji sprzętowej z usługami IIS do komunikowania się z urządzeniami peryferyjnymi punktu sprzedaży skonfigurowanymi w profilu sprzętu. W związku z tym każde wystąpienie stacji sprzętowej IIS wymaga komputera, na którym są uruchomione usługa sieci web i aplikacja komunikujące się z urządzeniami. Stacja sprzętowa z usługami IIS jest konieczna dla wszystkich wystąpień aplikacji Modern POS działających w środowisku innym niż Windows.

#### <a name="dedicated"></a>Wyznaczony

Program Modern POS używa stacji sprzętowej typu **Dedykowana** do wykrywania, czy urządzenia peryferyjne są podłączone bezpośrednio do komputera, na którym jest używana aplikacja. Jednakże typ **Dedykowana** może być również używany przez stacje sprzętowe z usługami IIS. W scenariuszu z tradycyjnym, stacjonarnym punktem sprzedaży, w którym aplikacją punktu sprzedaży jest Cloud POS, typ stacji sprzętowej **Dedykowana** jest używany dla stacji sprzętowych z usługami IIS zainstalowanych na tym samym komputerze, na którym działa oprogramowanie Cloud POS. Z punktu widzenia urządzeń peryferyjnych sieci sprzedaży dedykowana stacja sprzętowa IIS zapewnia lepszą obsługę takich urządzeń w scenariuszach z tradycyjnym, stacjonarnym punktem sprzedaży. Dedykowane stacje sprzętowe obsługują wszystkie urządzenia peryferyjne, które są obsługiwane w profilu sprzętu.

#### <a name="shared"></a>Współdzielony

Wspólne stacje sprzętowe są przeznaczone do wykorzystywania przez wiele urządzeń w punkcie sprzedaży przez cały dzień. Wspólne stacje sprzętowe są zoptymalizowane do obsługi wyłącznie szuflad kasowych, drukarek paragonów i terminali płatniczych. Nie można bezpośrednio podłączać autonomicznych czytników kodów kreskowych, czytników kart magnetycznych, wyświetlaczy wierszowych, wag ani innych urządzeń. W przeciwnym razie wystąpią konflikty, gdy wiele urządzeń punktu sprzedaży będzie próbowało zarezerwować te urządzenia peryferyjne w tym samym czasie. Oto jak są rozwiązywane konflikty dla obsługiwanych urządzeń:

-   **Szuflada kasowa** — Szuflada kasowa jest otwierana za pomocą zdarzenia wysyłanego do urządzenia. Jedyny problem, który może wystąpić przy wywoływaniu szuflady kasowej, dotyczy sytuacji, gdy szuflada jest już otwarta. W przypadku wspólnych stacji sprzętowych należy dla szuflady kasowej w profilu sprzętu ustawić wartość **Udostępniona**. Ustawienie to sprawia, że podczas wysyłania polecenia otwarcia aplikacja punktu sprzedaży nie sprawdza, czy szuflada kasowa jest już otwarta.
-   **Drukarka paragonów** — Jeżeli w tym samym momencie do stacji sprzętowej zostaną wysłane dwa polecenia drukowania paragonów, jedno z poleceń może zostać utracone, w zależności od urządzenia. Niektóre urządzenia mają wewnętrzną pamięć lub funkcję buforowania, który może zapobiec występowaniu tego problemu. Jeśli polecenie drukowania się nie powiedzie, kasjer otrzymuje komunikat o błędzie i może ponowić próbę wykonania polecenia drukowania z aplikacji punktu sprzedaży.
-   **Terminal płatniczy** — Jeśli kasjer próbuje opłacić transakcję w terminalu płatniczym, który jest już używany, komunikat powiadamia go, że terminal jest używany, i prosi kasjera, aby spróbował później. Zwykle kasjerzy widzą, że terminal jest już używany, i czekają na zakończenie drugiej transakcji, zanim ponownie spróbują sfinalizować swoją.

W przyszłości jest planowane dodanie funkcji sprawdzania poprawności w celu wykrywania, czy nieobsługiwane urządzenia zostały skonfigurowane w profilu sprzętu zmapowanym na wspólną stację sprzętową. W razie wykrycia jakiegokolwiek nieobsługiwanego urządzenia użytkownik otrzyma komunikat informujący, że urządzenia nie są obsługiwane dla wspólnych stacji sprzętowych. W przypadku wspólnych stacji sprzętowych opcja **Wybierz przy płatności** ma ustawioną wartość **Tak** na poziomie kasy. Użytkownik punktu sprzedaży jest następnie monitowany o wybór stacji sprzętowej przy wybieraniu opcji płacenia za transakcję w punkcie sprzedaży. Gdy stacja sprzętowa jest wybierana tylko w czasie płacenia, dla scenariuszy mobilnych wybór stacji sprzętowej jest dodawany bezpośrednio do przepływu pracy w punkcie sprzedaży. Dodatkową korzyścią jest to, że w scenariuszach współużytkowania nie jest używany wyświetlacz wierszowy terminala płatniczego. Jeśli terminal płatniczy jest używany jako wyświetlacz wierszowy, może to zablokować korzystanie z terminala przez innych użytkowników aż do zakończenia transakcji. W scenariuszach mobilnych wiersze mogą być dodawane transakcji przez dłuższy czas. W związku z tym opcja **Wybierz przy płatności** jest konieczna w celu zapewnienia optymalnej dostępności urządzenia.

### <a name="network-peripherals"></a>Sieciowe urządzenia peryferyjne

Sieciowe oznaczenie urządzeń w profilu sprzętu umożliwia podłączanie szuflad kasowych, drukarek paragonów i terminali płatniczych przy użyciu połączenia sieciowego.

#### <a name="modern-pos-for-windows"></a>Modern POS for Windows

Adresy IP sieciowych urządzeń peryferyjnych można określić w dwóch miejscach. Jeśli klient programu Modern POS Windows używa jednego zestawu peryferyjnych urządzeń sieciowych, w celu ustawienia adresów IP tych urządzeń należy użyć opcji **Konfiguracja protokołu IP** w okienku akcji w samej kasie. W przypadku urządzeń sieciowych, które będą współużytkowane przez kilka kas w punkcie sprzedaży, profil sprzętu zawierający przypisane urządzenia sieciowe można zmapować bezpośrednio na wspólną stację sprzętową. Aby przypisać adresy IP, wybierz stację sprzętową na stronie **Sklepy sieci sprzedaży**, a następnie w opcji **Konfiguracja protokołu IP** w sekcji **Stacje sprzętowe** wskaż urządzenia sieciowe przypisane do tej stacji sprzętowej. W przypadku stacji sprzętowych zawierających tylko urządzenia sieciowe nie trzeba instalować samej stacji sprzętowej. W takim przypadku stacja sprzętowa jest wymagana tylko w celu koncepcyjnego zgrupowania urządzeń adresowalnych w sieci zgodnie z ich umiejscowieniem w sklepie sieci sprzedaży.

#### <a name="cloud-pos-modern-pos-for-ios-and-modern-pos-for-android"></a>Cloud POS, Modern POS for iOS i Modern POS for Android

Logika sterująca urządzeniami peryferyjnymi połączonymi fizycznie i adresowalnymi w sieci jest zawarta w stacji sprzętowej. W związku z tym dla wszystkich urządzeń klienckich oprogramowania punktu sprzedaży, z wyjątkiem urządzeń z aplikacją Modern POS for Windows, stacja sprzętowa z usługami IIS musi być zainstalowana i aktywna, aby aplikacja punktu sprzedaży mogła się komunikować się z urządzeniami peryferyjnymi, niezależnie od tego, czy te urządzenia peryferyjne są fizycznie podłączone do stacji sprzętowej czy też adresowane przez sieć.

## <a name="setup-and-configuration"></a>Instalacja i konfiguracja
### <a name="hardware-station-installation"></a>Instalacja stacji sprzętowej

Aby uzyskać więcej informacji, zobacz [Konfiguracja i instalacja programu Retail hardware station](retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Instalacja i konfiguracja programu Modern POS for Windows

Aby uzyskać więcej informacji, zobacz [Konfiguracja i instalacja programu Retail Modern POS](retail-modern-pos-device-activation.md).

### <a name="opos-device-setup-and-configuration"></a>Instalacja i konfiguracja urządzenia OPOS

Aby uzyskać więcej informacji na temat składników zgodnych ze standardem OPOS, zobacz sekcję „Obsługiwane interfejsy” w tym dokumencie. Zazwyczaj sterowniki OPOS są dostarczane przez producenta urządzenia. Po zainstalowaniu sterownika urządzenia OPOS jest dodawany klucz do rejestru systemu Windows w jednej z następujących lokalizacji:

-   **System 32-bitowy:** HKEY\_LOCAL\_MACHINESOFTWAREOLEforRetailServiceOPOS
-   **System 64-bitowy:** HKEY\_LOCAL\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS

W rejestrze w kluczu ServiceOPOS skonfigurowane urządzenia są uporządkowane według klasy urządzenia OPOS. System może zapisywać wiele sterowników urządzeń.

## <a name="supported-scenarios-by-hardware-station-type"></a>Obsługiwane scenariusze według typów stacji sprzętowych
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Obsługa klientów — stacja sprzętowa z funkcją IPC kontra stacja sprzętowa z usługami IIS

W poniższej tabeli przedstawiono obsługiwane topologie i scenariusze wdrożenia.

| Klient      | Stacja sprzętowa z funkcją IPC | Stacja sprzętowa z usługami IIS |
|-------------|----------------------|----------------------|
| Aplikacja systemu Windows | Tak                  | Tak                  |
| Cloud POS   | Nr                   | Tak                  |
| Android     | Nr                   | Tak                  |
| iOS         | Nr                   | Tak                  |

### <a name="network-peripherals"></a>Sieciowe urządzenia peryferyjne

Sieciowe urządzenia peryferyjne mogą być obsługiwane bezpośrednio przez stację sprzętową wbudowaną w aplikacji Modern POS for Windows. Na wszystkich innych urządzeniach klienckich należy zainstalować stację sprzętową z usługami IIS.

| Klient      | Stacja sprzętowa z funkcją IPC | Stacja sprzętowa z usługami IIS |
|-------------|----------------------|----------------------|
| Aplikacja systemu Windows | Tak                  | Tak                  |
| Cloud POS   | Nr                   | Tak                  |
| Android     | Nr                   | Tak                  |
| iOS         | Nr                   | Tak                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Obsługiwane typy urządzeń według typów stacji sprzętowych
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS for Windows ze stacją sprzętową z funkcją IPC (wbudowaną)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Obsługiwana klasa urządzeń</th>
<th>Obsługiwane interfejsy</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Drukarka</td>
<td><ul>
<li>OPOS</li>
<li>Sterownik w systemie Windows</li>
<li>Urządzenie</li>
<li>Sieć</li>
</ul></td>
</tr>
<tr class="even">
<td>Drukarka 2</td>
<td><ul>
<li>OPOS</li>
<li>Sterownik w systemie Windows</li>
<li>Urządzenie</li>
<li>Sieć</li>
</ul></td>
</tr>
<tr class="odd">
<td>Wyświetlacz wierszowy</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Dwa wyświetlacze</td>
<td>Sterownik w systemie Windows</td>
</tr>
<tr class="odd">
<td>MSR</td>
<td><ul>
<li>OPOS</li>
<li>UWP (nie trzeba nic konfigurować)</li>
<li>Czytnik podłączany do klawiatury (nie trzeba nic konfigurować)</li>
</ul></td>
</tr>
<tr class="even">
<td>Szuflada</td>
<td><ul>
<li>OPOS</li>
<li>Sieć <strong>Uwaga:</strong> Jeśli w ustawieniach szuflady zostanie włączona opcja <strong>Używaj zmiany udostępnionej</strong>, można skonfigurować tylko jedną szufladę.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Szuflada 2</td>
<td><ul>
<li>OPOS</li>
<li>Sieć <strong>Uwaga:</strong> Jeśli w ustawieniach szuflady zostanie włączona opcja <strong>Używaj zmiany udostępnionej</strong>, można skonfigurować tylko jedną szufladę.</li>
</ul></td>
</tr>
<tr class="even">
<td>Skaner</td>
<td><ul>
<li>OPOS</li>
<li>UWP (nie trzeba nic konfigurować)</li>
<li>Czytnik podłączany do klawiatury (nie trzeba nic konfigurować)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Skaner 2</td>
<td><ul>
<li>OPOS</li>
<li>UWP (nie trzeba nic konfigurować)</li>
<li>Czytnik podłączany do klawiatury (nie trzeba nic konfigurować)</li>
</ul></td>
</tr>
<tr class="even">
<td>Skalowanie</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Konsola PIN</td>
<td>OPOS (obsługa jest realizowana poprzez dostosowanie aplikacji łącznika płatności)</td>
</tr>
<tr class="even">
<td>Przechwytywanie podpisu</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Terminal płatniczy </td>
<td><ul>
<li>Obsługa urządzeń niestandardowych</li>
<li>Sieć (aby uzyskać więcej informacji, zobacz dokumentację aplikacji łącznika płatności)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Wszystkie urządzenia klienckie programu Modern POS mające dedykowaną stację sprzętową z usługami IIS

**Uwaga:** Gdy stacja sprzętowa z usługami IIS jest „dedykowana”, istnieje relacja jeden-do-jednego między aplikacją kliencką punktu sprzedaży a stacją sprzętową.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Obsługiwana klasa urządzeń</th>
<th>Obsługiwane interfejsy</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Drukarka</td>
<td><ul>
<li>OPOS</li>
<li>Sterownik systemu Windows <strong>Uwaga:</strong> W przypadku drukarek systemu Windows w sieci stacja sprzętowa musi mieć uprawnienie dostępu do drukarki.</li>
<li>Sieć</li>
</ul></td>
</tr>
<tr class="even">
<td>Drukarka 2</td>
<td><ul>
<li>OPOS</li>
<li>Sterownik w systemie Windows</li>
<li>Sieć</li>
</ul></td>
</tr>
<tr class="odd">
<td>Wyświetlacz wierszowy</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>MSR</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Szuflada</td>
<td><ul>
<li>OPOS</li>
<li>Sieć <strong>Uwaga:</strong> Jeśli w ustawieniach szuflady zostanie włączona opcja <strong>Używaj zmiany udostępnionej</strong>, można skonfigurować tylko jedną szufladę na każdy profil sprzętu.</li>
</ul></td>
</tr>
<tr class="even">
<td>Szuflada 2</td>
<td><ul>
<li>OPOS</li>
<li>Sieć</li>
</ul></td>
</tr>
<tr class="odd">
<td>Skaner</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Skaner 2</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Skalowanie</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Konsola PIN</td>
<td>OPOS (obsługa jest realizowana poprzez dostosowanie aplikacji łącznika płatności)</td>
</tr>
<tr class="odd">
<td>Podpisy — przechwytywanie</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Terminal płatniczy </td>
<td><ul>
<li>Obsługa urządzeń niestandardowych</li>
<li>Sieć (aby uzyskać więcej informacji, zobacz dokumentację aplikacji łącznika płatności)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Wszystkie urządzenia klienckie programu Modern POS mające wspólną stację sprzętową z usługami IIS

**Uwaga:** Kiedy stacja sprzętowa z usługami IIS jest „udostępniona”, wiele urządzeń może używać tej stacji w tym samym czasie. W tym scenariuszu należy użyć tylko urządzeń wymienionych w tabeli poniżej. Jeśli spróbujesz współużytkować urządzenia, które nie są tutaj wymienione, takiej jak skanery kodów kreskowych i czytniki kart magnetycznych, wystąpią błędy w chwili, gdy wiele urządzeń będzie próbowało zarezerwować to samo urządzenie peryferyjne. W przyszłości taka konfiguracja będzie technicznie niemożliwa do wykonania.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Obsługiwana klasa urządzeń</th>
<th>Obsługiwane interfejsy</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Drukarka</td>
<td><ul>
<li>OPOS</li>
<li>Sterownik systemu Windows <strong>Uwaga:</strong> W przypadku drukarek systemu Windows w sieci stacja sprzętowa musi mieć uprawnienie dostępu do drukarki.</li>
<li>Sieć</li>
</ul></td>
</tr>
<tr class="even">
<td>Drukarka 2</td>
<td><ul>
<li>OPOS</li>
<li>Sterownik w systemie Windows</li>
<li>Sieć</li>
</ul></td>
</tr>
<tr class="odd">
<td>Szuflada</td>
<td><ul>
<li>OPOS</li>
<li>Sieć <strong>Uwaga:</strong> Jeśli w ustawieniach szuflady zostanie włączona opcja <strong>Używaj zmiany udostępnionej</strong>, można skonfigurować tylko jedną szufladę na każdy profil sprzętu.</li>
</ul></td>
</tr>
<tr class="even">
<td>Szuflada 2</td>
<td><ul>
<li>OPOS</li>
<li>Sieć</li>
</ul></td>
</tr>
<tr class="odd">
<td>Terminal płatniczy </td>
<td><ul>
<li>Obsługa urządzeń niestandardowych</li>
<li>Sieć (aby uzyskać więcej informacji, zobacz dokumentację aplikacji łącznika płatności)</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Konfiguracja dla obsługiwanych scenariuszy
Aby uzyskać więcej informacji dotyczących sposobu tworzenia profili sprzętu, zobacz [Definiowania klientów w kanałach, w tym kas i stacji sprzętowych, oraz zarządzanie nimi](define-maintain-channel-clients-registers-hw-stations.md). **Uwaga:** W programie Microsoft Dynamics 365 for Retail w wersji 1611 profil stacji sprzętowej nie jest już używany. Atrybuty uprzednio skonfigurowane w profilu stacji sprzętowej są teraz częścią samej stacji sprzętowej.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS for Windows ze stacją sprzętową z funkcją IPC (wbudowaną)

Ta konfiguracja jest najbardziej typową konfigurację dla kas w tradycyjnych, stacjonarnych punktach sprzedaży. W tym scenariuszu dane profilu sprzętu są mapowane bezpośrednio na samą kasę. W aplikacji kasy należy również ustawić numer terminala EFT. Aby skonfigurować te ustawienia, wykonaj poniższe czynności.

1.  Utwórz profil sprzętu, w którym będą skonfigurowane wszystkie wymagane urządzenia peryferyjne.
2.  Zamapuj profil sprzętu na kasę w punkcie sprzedaży.
3.  Utwórz stację sprzętową typu **Dedykowana** dla sklepu sieci sprzedaży, w którym będzie używana kasa punktu sprzedaży. Opcjonalnie możesz wprowadzić opis. **Uwaga:** Nie trzeba konfigurować żadnych innych właściwości w stacji sprzętowej. Wszystkie pozostałe wymagane informacje, takie jak profil sprzętu, zostaną pobrane bezpośrednio z kasy.
4.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**.
5.  Wybierz harmonogram dystrybucji **1090**, aby zsynchronizować nowy profil sprzętu ze sklepem. Kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.
6.  Wybierz harmonogram dystrybucji **1040**, aby zsynchronizować nową stację sprzętową ze sklepem. Kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.
7.  Zainstaluj i aktywuj aplikację Modern POS for Windows.
8.  Uruchom aplikację Modern POS for Windows i zacznij używać podłączonych urządzeń peryferyjnych.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Wszystkie urządzenia klienckie programu Modern POS mające dedykowaną stację sprzętową z usługami IIS

Tej konfiguracji można używać na wszystkich urządzeniach klienckich programu Modern POS mających stację sprzętową, która jest używana wyłącznie przez jedną kasę w punkcie sprzedaży. Aby skonfigurować te ustawienia, wykonaj poniższe czynności.

1.  Utwórz profil sprzętu, w którym będą skonfigurowane wszystkie wymagane urządzenia peryferyjne.
2.  Utwórz stację sprzętową typu **Dedykowana** dla sklepu sieci sprzedaży, w którym będzie używana kasa punktu sprzedaży.
3.  Na dedykowanej stacji sprzętowej ustaw następujące właściwości:
    -   **Nazwa hosta** — Nazwa komputera hosta, na którym będzie uruchamiana stacja sprzętowa. **Uwaga:** Aplikacja Cloud POS może rozpoznawać właściwość **localhost** w celu ustalania lokalnego komputera, na którym jest uruchomiona. Jednak certyfikat wymagany do sparowania aplikacji Cloud POS ze stacją sprzętową również musi mieć nazwę komputera „Localhost”. Aby uniknąć problemów, zalecamy wyszczególnienie wszystkich potrzebnych wystąpień dedykowanych stacji sprzętowych dla sklepu. Dla każdej stacji sprzętowej nazwą hosta powinna być nazwa konkretnego komputera, na którym zostanie zainstalowana stacja sprzętowa.
    -   **Port** — Port wykorzystywany przez stację sprzętową do komunikacji z urządzeniem klienckim programu Modern POS.
    -   **Profil sprzętu** — Jeśli profil sprzętu nie został określony w samej stacji sprzętowej, będzie używany profil sprzętu przypisany do kasy.
    -   **Numer EFT w punkcie sprzedaży** — Identyfikator terminala EFT, który ma być używany podczas wysyłania autoryzacji płacenia metodą EFT. Ten identyfikator jest dostarczany przez agenta rozliczeniowego kart kredytowych.
    -   **Nazwa pakietu** — Pakiet stacji sprzętowej, który ma być używany podczas instalowania stacji sprzętowej.

4.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**.
5.  Wybierz harmonogram dystrybucji **1090**, aby zsynchronizować nowy profil sprzętu ze sklepem. Kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.
6.  Wybierz harmonogram dystrybucji **1040**, aby zsynchronizować nową stację sprzętową ze sklepem. Kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.
7.  Zainstaluj stację sprzętową. Aby uzyskać więcej informacji dotyczących sposobu instalowania stacji sprzętowej, zobacz [Konfiguracja i instalacja programu Retail hardware station](retail-hardware-station-configuration-installation.md).
8.  Zainstaluj i aktywuj aplikację Modern POS. Aby uzyskać więcej informacji dotyczących sposobu instalowania aplikacji Modern POS, zobacz [Konfiguracja i instalacja programu Retail Modern POS](retail-modern-pos-device-activation.md).
9.  Zaloguj się w aplikacji Modern POS i wybierz opcję **Wykonaj operacje bez użycia szuflady**.
10. Uruchom operację **Zarządzaj stacjami sprzętowymi**.
11. Kliknij przycisk **Zarządzaj**.
12. Na stronie zarządzanie stacją sprzętową ustaw opcję włączenia stacji.
13. Zaznacz stację sprzętową, która ma być używana, a następnie kliknij przycisk **Paruj**.
14. Po sparowaniu stacji sprzętowej kliknij przycisk **Zamknij**.
15. Na stronie wyboru stacji sprzętowej kliknij ostatnio zaznaczoną stację sprzętową, aby ją uaktywnić.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Wszystkie urządzenia klienckie programu Modern POS mające wspólną stację sprzętową z usługami IIS

Tej konfiguracji można używać na wszystkich urządzeniach klienckich programu Modern POS współużytkujących stacje sprzętowe z innymi urządzeniami. Aby skonfigurować te ustawienia, wykonaj poniższe czynności.

1.  Utwórz profil sprzętu, w którym będą skonfigurowane wymagane urządzenia peryferyjne.
2.  Utwórz stację sprzętową typu **Udostępniona** dla sklepu sieci sprzedaży, w którym będzie używana kasa punktu sprzedaży.
3.  Na współużytkowanej stacji sprzętowej ustaw następujące właściwości:
    -   **Nazwa hosta** — Nazwa komputera hosta, na którym będzie uruchamiana stacja sprzętowa.
    -   **Opis** — Tekst, który pomoże identyfikować stację sprzętową, np. jak **Zwroty** lub **Przód sklepu**.
    -   **Port** — Port wykorzystywany przez stację sprzętową do komunikacji z urządzeniem klienckim programu Modern POS.
    -   **Profil sprzętu** — W przypadku wspólnych stacji sprzętowych każda stacja powinna mieć profil sprzętu. Profile sprzętu mogą być współużytkowane przez stacje sprzętowe, ale muszą być mapowane do każdej stacji sprzętowej. Ponadto zalecamy, aby w przypadku, gdy wiele urządzeń korzysta z tej samej wspólnej stacji sprzętowej, stosować zmiany wspólne. Aby skonfigurować udostępnioną zmianę, kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile sprzętu**. Dla każdego współużytkowanego profilu sprzętu zaznacz szufladę kasową i w opcji **Wspólna szuflada dla zmiany** ustaw wartość **Tak**.
    -   **Numer EFT w punkcie sprzedaży** — Identyfikator terminala EFT, który ma być używany podczas wysyłania autoryzacji płacenia metodą EFT. Ten identyfikator jest dostarczany przez agenta rozliczeniowego kart kredytowych.
    -   **Nazwa pakietu** — Pakiet stacji sprzętowej, który ma być używany podczas instalowania stacji sprzętowej.

4.  Powtórz kroki 2 i 3 dla każdej dodatkowej stacji sprzętowej, która jest potrzebna w sklepie.
5.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**.
6.  Wybierz harmonogram dystrybucji **1090**, aby zsynchronizować nowy profil sprzętu ze sklepem. Kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.
7.  Wybierz harmonogram dystrybucji **1040**, aby zsynchronizować nową stację sprzętową ze sklepem. Kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.
8.  Zainstaluj stację sprzętową na każdym komputerze hosta skonfigurowanym w krokach 2 i 3. Aby uzyskać więcej informacji dotyczących sposobu instalowania stacji sprzętowej, zobacz [Konfiguracja i instalacja programu Retail hardware station](retail-hardware-station-configuration-installation.md).
9.  Zainstaluj i aktywuj aplikację Modern POS. Aby uzyskać więcej informacji dotyczących sposobu instalowania aplikacji Modern POS, zobacz [Konfiguracja i instalacja programu Retail Modern POS](retail-modern-pos-device-activation.md).
10. Zaloguj się w aplikacji Modern POS i wybierz opcję **Wykonaj operacje bez użycia szuflady**.
11. Uruchom operację **Zarządzaj stacjami sprzętowymi**.

12. Kliknij przycisk **Zarządzaj**.
13. Na stronie zarządzanie stacją sprzętową ustaw opcję włączenia stacji.
14. Zaznacz stację sprzętową, która ma być używana, a następnie kliknij przycisk **Paruj**.
15. Powtórz krok 14 dla każdej stacji sprzętowej, która będzie używana przez aplikację Modern POS.
16. Po sparowaniu wszystkich wymaganych stacji sprzętowych kliknij przycisk **Zamknij**.
17. Na stronie wyboru stacji sprzętowej kliknij ostatnio zaznaczoną stację sprzętową, aby ją uaktywnić. **Uwaga:** Jeśli urządzenia często używają różnych stacji sprzętowych, zaleca się skonfigurowanie w programie Modern POS monitowania kasjerów o wybór stacji przy rozpoczynaniu procesu płacenia. Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Rejestry**. Zaznacz kasę, a następnie w opcji **Wybierz przy płatności** ustaw wartość **Tak**. Użyj harmonogramu dystrybucji **1090**, aby zsynchronizować zmiany z bazą danych kanału.

## <a name="extensibility"></a>Możliwości rozszerzania
Aby uzyskać informacje na temat scenariuszy rozszerzania stacji sprzętowej, zobacz [Możliwości rozszerzania stacji sprzętowych](dev-itpro/hardware-station-extensibility.md).

## <a name="security"></a>Zabezpieczenia
Zgodnie z obowiązującymi standardami zabezpieczeń w środowisku produkcyjnym należy stosować ustawienia wymienione poniżej. **Uwaga:** Instalator stacji sprzętowej automatycznie wprowadzi te modyfikacje rejestru w ramach procesu instalacji.

-   Należy wyłączyć protokół Secure Sockets Layer (SSL).
-   Należy włączyć i używać tylko protokołu Transport Layer Security (TLS) w wersji 1.2 (lub aktualnie najnowszej wersji). **Uwaga:** Domyślnie protokół SSL i wszystkie wersje protokołu TLS, z wyjątkiem TLS 1.2, są wyłączone. Aby edytować lub włączyć te wartości, wykonaj następujące kroki:
    1.  Naciśnij klawisz z logo systemu Windows i klawisz R, aby otworzyć okno **Uruchamianie**.
    2.  W polu **Otwórz** wpisz **Regedit**, a następnie kliknij przycisk **OK**.
    3.  Jeśli zostanie wyświetlone okno komunikatu **Kontrola konta użytkownika**, kliknij przycisk **Tak**.
    4.  W oknie **Edytor rejestru** przejdź do pozycji **HKEY\_LOCAL\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols**. Następujące klucze zostały wprowadzone automatycznie w celu zapewnienia obsługi wyłącznie protokołu TLS 1.2:
        -   TLS 1.2Server:Enabled=1
        -   TLS 1.2Server:DisabledByDefault=0
        -   TLS 1.2Client:Enabled=1
        -   TLS 1.2Client:DisabledByDefault=0
        -   TLS 1.1Server:Enabled=0
        -   TLS 1.1Client:Enabled=0
        -   TLS 1.0Server:Enabled=0
        -   TLS 1.0Client:Enabled=0
        -   SSL 3.0Server:Enabled=0
        -   SSL 3.0Client:Enabled=0
        -   SSL 2.0Server:Enabled=0
        -   SSL 2.0Client:Enabled=0
-   Nie powinny być otwarte żadne dodatkowe porty sieciowe, chyba że są one wymagane ze znanych, określonych powodów.
-   Funkcja współużytkowania zasobów między źródłami musi być wyłączona i określać dozwolone źródła, które są akceptowane.
-   Do uzyskiwania certyfikatów, które będą używane na komputerach ze stacją sprzętową, powinny być wykorzystywane tylko zaufane urzędy certyfikacji.

**Uwaga:** Bardzo ważne jest, aby się wcześniej zapoznać z wytycznymi dotyczącymi zabezpieczeń usług IIS oraz wymaganiami organizacji Payment Card Industry (PCI).

## <a name="peripheral-simulator"></a>Symulator urządzeń peryferyjnych
Aby uzyskać więcej informacji, zobacz [Symulator urządzeń peryferyjnych sieci sprzedaży](dev-itpro/retail-peripheral-simulator.md).

## <a name="microsofttested-peripheral-devices"></a>Urządzenia peryferyjne przetestowane przez Microsoft
### <a name="ipc-built-in-hardware-station"></a>Stacja sprzętowa z funkcją IPC (wbudowana)

Następujące urządzenia peryferyjne zostały przetestowane przy użyciu stacji sprzętowej z funkcją IPC, która jest wbudowana w programie Modern POS for Windows.

#### <a name="printer"></a>Drukarka

| Producent | Model    | Interfejs | Komentarze                |
|--------------|----------|-----------|-------------------------|
| Epson        | Tm-T88IV | OPOS      |                         |
| Epson        | TM-T88V  | OPOS      |                         |
| Star         | TSP650II | OPOS      |                         |
| Star         | TSP650II | Niestandardowy    | Połączenie przez sieć   |
| Star         | mPOP     | OPOS      | Połączenie przez Bluetooth |
| HP           | F7M67AA  | OPOS      | Zasilanie przez USB             |

#### <a name="bar-code-scanner"></a>Skaner kodów kreskowych

| Producent  | Model         | Interfejs | Komentarze |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Symbol        | LS2208        | OPOS      |          |
| HP Integrated | E1L07AA       | OPOS      |          |
| Datalogic     | Magellan 8400 | OPOS      |          |

#### <a name="pin-pad"></a>Konsola PIN

| Producent | Model  | Interfejs | Komentarze                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Wymaga dostosowania aplikacji łącznika płatności |

#### <a name="payment-terminal"></a>Terminal płatniczy 

| Producent | Model | Interfejs | Komentarze                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Niestandardowy    | Wymaga dostosowania aplikacji łącznika płatności                                |
| VeriFone     | MX925 | Niestandardowy    | Wymaga dostosowania aplikacji łącznika płatności; połączenie przez sieć i USB |
| VeriFone     | MX915 | Niestandardowy    | Wymaga dostosowania aplikacji łącznika płatności; połączenie przez sieć i USB |

#### <a name="cash-drawer"></a>Szuflada kasowa

| Producent | Model     | Interfejs | Komentarze                |
|--------------|-----------|-----------|-------------------------|
| Star         | mPOP      | OPOS      | Połączenie przez Bluetooth |
| APG          | Atwood    | Niestandardowy    | Połączenie przez sieć   |
| Star         | SMD2-1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |

#### <a name="line-display"></a>Wyświetlacz wierszowy

| Producent  | Model   | Interfejs | Komentarze |
|---------------|---------|-----------|----------|
| HP Integrated | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Przechwytywanie podpisu

| Producent | Model  | Interfejs | Komentarze |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Skalowanie

| Producent | Model         | Interfejs | Komentarze |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Producent | Model       | Interfejs | Komentarze |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="dedicated-iis-hardware-station"></a>Dedykowana stacja sprzętowa z usługami IIS

Następujące urządzenia peryferyjne zostały przetestowane przy użyciu dedykowanej (nie wspólnej) stacji sprzętowej z usługami IIS oraz programów Modern POS for Windows i Cloud POS.

#### <a name="printer"></a>Drukarka

| Producent | Model    | Interfejs | Komentarze                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Star         | TSP650II | OPOS      |                           |
| Star         | TSP650II | Niestandardowy    | Połączenie przez sieć     |
| Star         | TSP100   | OPOS      | Wymaga sterowników do modelu TSP650II |
| HP           | F7M67AA  | OPOS      | Zasilanie przez USB               |

#### <a name="bar-code-scanner"></a>Skaner kodów kreskowych

| Producent  | Model   | Interfejs | Komentarze |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | OPOS      |          |
| Symbol        | LS2208  | OPOS      |          |
| HP Integrated | E1L07AA | OPOS      |          |

#### <a name="pin-pad"></a>Konsola PIN

| Producent | Model  | Interfejs | Komentarze                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Wymaga dostosowania aplikacji łącznika płatności |

#### <a name="payment-terminal"></a>Terminal płatniczy 

| Producent | Model | Interfejs | Komentarze                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Niestandardowy    | Wymaga dostosowania aplikacji łącznika płatności                                |
| VeriFone     | MX925 | Niestandardowy    | Wymaga dostosowania aplikacji łącznika płatności; połączenie przez sieć i USB |
| VeriFone     | MX915 | Niestandardowy    | Wymaga dostosowania aplikacji łącznika płatności; połączenie przez sieć i USB |

#### <a name="cash-drawer"></a>Szuflada kasowa

| Producent | Model     | Interfejs | Komentarze              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Niestandardowy    | Połączenie przez sieć |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

#### <a name="line-display"></a>Wyświetlacz wierszowy

| Producent  | Model   | Interfejs | Komentarze |
|---------------|---------|-----------|----------|
| HP Integrated | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Przechwytywanie podpisu

| Producent | Model  | Interfejs | Komentarze |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Skalowanie

| Producent | Model         | Interfejs | Komentarze |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Producent | Model       | Interfejs | Komentarze |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="shared-iis-hardware-station"></a>Wspólna stacja sprzętowa z usługami IIS

Następujące urządzenia peryferyjne zostały przetestowane przy użyciu wspólnej stacji sprzętowej z usługami IIS oraz programów Modern POS for Windows i Cloud POS. **Uwaga:** Obsługiwane są tylko drukarki, terminale płatnicze i szuflady kasowe.

#### <a name="printer"></a>Drukarka

| Producent | Model    | Interfejs | Komentarze                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Star         | TSP650II | OPOS      |                           |
| Star         | TSP650II | Niestandardowy    | Połączenie przez sieć     |
| Star         | TSP100   | OPOS      | Wymaga sterowników do modelu TSP650II |
| HP           | F7M67AA  | OPOS      | Zasilanie przez USB               |

#### <a name="payment-terminal"></a>Terminal płatniczy 

| Producent | Model | Interfejs | Komentarze                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Niestandardowy    | Wymaga dostosowania aplikacji łącznika płatności; połączenie przez sieć i USB |
| VeriFone     | MX915 | Niestandardowy    | Wymaga dostosowania aplikacji łącznika płatności; połączenie przez sieć i USB |

#### <a name="cash-drawer"></a>Szuflada kasowa

| Producent | Model     | Interfejs | Komentarze              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Niestandardowy    | Połączenie przez sieć |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

## <a name="troubleshooting"></a>Rozwiązywanie problemów
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>Aplikacja Modern POS wykrywa stację sprzętową na swojej liście obiektów do wyboru, ale nie może wykonać parowania

**Rozwiązanie:** Sprawdź poniższą listę potencjalnych punktów awarii:

-   Komputer, na którym jest uruchomiony program Modern POS, ufa certyfikatowi używanemu na komputerze, na którym jest uruchomiona stacja sprzętowa.
    -   Aby zweryfikować tę konfigurację, w przeglądarce sieci web przejdź do następującego adresu URL: https://&lt;nazwa komputera&gt;:&lt;numer portu&gt;/HardwareStation/ping.
    -   Ten adres URL używa polecenia ping do sprawdzania, czy jest możliwy dostęp do komputera, a przeglądarka wskazuje, czy certyfikat jest zaufany. Na przykład w programie Internet Explorer na pasku adresu pojawia się ikona kłódki. Po kliknięciu tej ikony program Internet Explorer sprawdza, czy certyfikat jest obecnie zaufany. Można zainstalować certyfikat na lokalnym komputerze, wyświetlając szczegóły pokazanego certyfikatu.
-   Na komputerze, na którym jest uruchomiona stacja sprzętowa, port przeznaczony do używania przez stację sprzętową jest otwarty w zaporze.
-   Na stacji sprzętowej zostały prawidłowo zainstalowane informacje o koncie handlowca za pomocą narzędzia instalowania informacji o handlowcu uruchamianego na koniec procesu instalowania stacji sprzętowej.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>Aplikacja Modern POS nie wykrywa stacji sprzętowej na swojej liście obiektów do wyboru

**Rozwiązanie:** Jeden z następujących czynników może powodować ten problem:

-   Stacja sprzętowa nie została poprawnie skonfigurowana w centrali. Wykonaj kroki opisane wcześniej w tym temacie, aby sprawdzić, czy profil stacji sprzętowej i stacja sprzętowa są poprawnie wprowadzone.
-   Nie wykonano zadań aktualizujących konfigurację kanału. W takim przypadku wykonaj zadanie 1070 dotyczące konfigurowania kanału.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>Aplikacja Modern POS nie uwzględnia nowych ustawień szuflady kasowej

**Rozwiązanie:** Zamknij bieżącą partię. Modyfikacje szuflady kasowej są wprowadzanie w aplikacji Modern POS dopiero po zamknięciu bieżącej partii.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>Aplikacja Modern POS zgłasza problem z urządzeniem peryferyjnym sieci sprzedaży

**Rozwiązanie:** Poniżej przedstawiono niektóre typowe przyczyny tego problemu:

-   Upewnij się, że narzędzia konfiguracji sterowników innych urządzeń są zamknięte. Jeśli te narzędzia są otwarte, mogą uniemożliwiać aplikacji Modern POS lub stacji sprzętowej rezerwowanie urządzenia.
-   Jeśli urządzenie peryferyjne sieci sprzedaży jest współużytkowane przez wiele urządzeń w punkcie sprzedaży, upewnij się, że należy do jednej z poniższych kategorii:
    -   Szuflada kasowa
    -   Drukarka paragonów
    -   Terminal płatniczy 

    Jeśli urządzenie peryferyjne nie należy do żadnej z tych kategorii, stacja sprzętowa nie jest przygotowana do włączenia współużytkowania tego urządzenia przez wiele urządzeń w punkcie sprzedaży.
-   Czasami sterowniki urządzeń mogą powodować, że wspólne obiekty formantów (CCO) przestają działać poprawnie. Jeśli urządzenie zostało niedawno zainstalowane, ale nie działa poprawnie lub zauważasz inne problemy, błędy można często wyeliminować poprzez ponowną instalację obiektów CCO. Aby pobrać obiekty CCO, odwiedź stronę <http://monroecs.com/oposccos_current.htm>.
-   Jeśli często wprowadzasz zmiany w urządzeniach peryferyjnych podczas testowania lub rozwiązywania problemów, lepiej zresetować usługi IIS niż czekać na odświeżanie się pamięci podręcznej. Aby zresetować usługi IIS, wykonaj następujące czynności:
    1.  W menu **Start** wpisz polecenie **CMD**.
    2.  W wynikach wyszukiwania kliknij prawym przyciskiem myszy pozycję **Wiersz polecenia**, a następnie kliknij opcję **Uruchom jako administrator**.
    3.  W oknie **Wiersza polecenia** wpisz wyrażenie **iisreset /Restart** i naciśnij klawisz Enter.
    4.  Po ponownym uruchomieniu usług IIS ponownie uruchom program Modern POS.
-   Jeśli podczas częstego wprowadzania zmian w urządzeniach peryferyjnych również często uruchomiasz i zamykasz aplikację kliencką punktu sprzedaży, proces dllhost z poprzedniej sesji aplikacji punktu sprzedaży POS może zakłócać bieżącą sesję. W takim przypadku urządzenie może stać się użyteczne dopiero po zamknięciu hosta biblioteki dołączanej dynamicznie (DLL) zarządzającego poprzednią sesją. Aby zamknąć hosta biblioteki DLL, wykonaj następujące kroki:
    1.  W menu **Start** wpisz polecenie **Menedżer zadań**.
    2.  W wynikach wyszukiwania kliknij pozycję **Menedżer zadań**.
    3.  W Menedżerze zadań na karcie **Szczegóły** kliknij nagłówek kolumny zatytułowanej **Nazwa**, aby posortować zawartość tabeli alfabetycznie według nazw.
    4.  Przewiń w dół, aż zobaczysz plik dllhost.exe.
    5.  Zaznacz każdego hosta biblioteki DLL, a następnie kliknij przycisk **Zakończ zadanie**.
    6.  Po zamknięciu hostów bibliotek DLL ponownie uruchom program Modern POS.


<a name="see-also"></a>Informacje dodatkowe
--------

[Symulator urządzeń peryferyjnych sieci sprzedaży](dev-itpro/retail-peripheral-simulator.md)




