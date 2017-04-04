---
title: "Przegląd urządzeń peryferyjnych sieci sprzedaży"
description: "W tym temacie wyjaśniono pojęcia, które są związane z urządzenia peryferyjne sieci sprzedaży. Opisuje różne sposoby, że urządzenia peryferyjne może być podłączony do punktu sprzedaży (POS) i składników, które są odpowiedzialne za zarządzanie połączeniami z punktu sprzedaży."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 268444
ms.assetid: 2ea93e43-8019-49a0-a7f8-325565ebc52d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 79a43c35691f16d773b88faad63c4ab79cb93f1f
ms.openlocfilehash: c6fb3922ba2c4b15f1043d0bcbac40ff2da9a469
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripherals-overview"></a>Przegląd urządzeń peryferyjnych sieci sprzedaży

W tym temacie wyjaśniono pojęcia, które są związane z urządzenia peryferyjne sieci sprzedaży. Opisuje różne sposoby, że urządzenia peryferyjne może być podłączony do punktu sprzedaży (POS) i składników, które są odpowiedzialne za zarządzanie połączeniami z punktu sprzedaży.

<a name="concepts"></a>Koncepcje
--------

### <a name="pos-registers"></a>Rejestry punktu sprzedaży

Nawigacja: Kliknij przycisk **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**rejestruje**. Punkt sprzedaży (POS) rejestru jest podmiot, który jest używany do definiowania właściwości konkretnego wystąpienia punktu sprzedaży. Cechy te obejmują profilu sprzętu lub instalacji urządzeń peryferyjnych sieci sprzedaży, które będą używane w rejestrze, magazynie rejestr jest mapowany do i wrażenia wizualne dla użytkownika, który loguje się do tego rejestru.

### <a name="devices"></a>Urządzenia

Nawigacja: Kliknij przycisk **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**urządzeń**. Urządzenie to jednostka, która reprezentuje fizyczne wystąpienie urządzenia zmapowanego do kasy POS. Po utworzeniu urządzenie jest mapowany do POS rejestru. Jednostka urządzenia śledzi informacje o tym, kiedy kasa punktu sprzedaży jest aktywowana, jaki typ klienta jest używany i jaki pakiet aplikacji został wdrożony na konkretnym urządzeniu. Urządzenia mogą być mapowane do następujących typów aplikacji: nowoczesny punkt sprzedaży, program Retail POS chmury, Retail POS nowoczesnych – Windows Phone, program Retail POS nowoczesnych – Android i Retail POS nowoczesnych – iOS.

### <a name="retail-modern-pos"></a>Nowoczesny punkt sprzedaży detalicznej

Nowoczesne POS to program Retail POS systemu Microsoft Windows. Mogą być wdrażane w systemach operacyjnych Windows 10 (OSs).

### <a name="cloud-pos"></a>Cloud POS

Chmura POS jest wersja przeglądarki programu Retail POS nowoczesnych, który jest możliwy w przeglądarce sieci web.

### <a name="modern-pos-for-ios"></a>Nowoczesne POS dla iOS

Nowoczesne POS dla iOS jest wersją systemem iOS program nowoczesnych POS, które mogą być wdrażane na urządzeniach.

### <a name="modern-pos-for-android"></a>Nowoczesne POS dla Androida

Nowoczesne POS dla Androida jest wersją Android na program nowoczesnych POS, które mogą być wdrażane na urządzeniach z Androidem.

### <a name="pos-peripherals"></a>Urządzenia peryferyjne punktu sprzedaży

Urządzenia peryferyjne POS są urządzenia, które wyraźnie są obsługiwane dla funkcji punktu sprzedaży. Te urządzenia peryferyjne są zwykle podzielone na określonych klas. Aby uzyskać więcej informacji na temat tych klas zobacz sekcję "Klas urządzeń" w tym temacie.

### <a name="hardware-station"></a>Stacja sprzętowa

Nawigacja: Kliknij przycisk **sieci sprzedaży i handlu**&gt;**kanałów**&gt;**sklepów detalicznych**&gt;**wszystkich sklepów detalicznych**. Zaznacz sklep i kliknij skróconą kartę **Stacje sprzętowe**. **Sprzętu stacji** ustawienie to ustawienie poziomie kanału, która jest używana do definiowania wystąpień, gdzie zostanie wdrożony logiki obwodowych sieci sprzedaży. To ustawienie na poziomie kanału jest używany do określenia charakterystyki stacji sprzętu. Służy również do listy sprzętu stacje, które są dostępne dla wystąpienia nowoczesny punkt sprzedaży w danym sklepie. Stacja sprzętowa jest wbudowana w program nowoczesnych POS dla systemu Windows. Stacja sprzętowa również mogą być wdrażane niezależnie jako autonomiczny program Microsoft Internet Information Services (IIS). W takim przypadku mogą być dostępne za pośrednictwem sieci.

### <a name="hardware-profile"></a>Profil sprzętu

Nawigacja: Kliknij przycisk **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**konfiguracji punktu sprzedaży**&gt;**profile POS**&gt;**profile sprzętu**. Profil sprzętu znajduje się lista urządzeń, które są skonfigurowane dla rejestru punktu sprzedaży lub stację sprzętową. Profil sprzętu mogą być mapowane bezpośrednio do rejestru punktu sprzedaży lub stację sprzętową.

## <a name="devices-classes"></a>Klasy urządzeń
Urządzenia peryferyjne POS zazwyczaj są podzielone na klasy. W tej sekcji opisano i przedstawiono omówienie urządzenia, które obsługuje nowoczesnych POS.

### <a name="printer"></a>Drukarka

Drukarki obejmują tradycyjne POS przyjęcia oraz całej strony drukarki. Drukarki są obsługiwane poprzez łączenie i osadzanie obiektów interfejsów sterownik Retail POS (OPOS) i Microsoft Windows. Maksymalnie dwie drukarki można w tym samym czasie. Ta funkcja obsługuje scenariuszy, gdzie prowadzącym klienta paragony są drukowane na drukarkach przyjęcia, natomiast zamówień klienta, które prowadzą więcej informacji, są drukowane na drukarce całej strony. Drukarki paragonów mogą być podłączony bezpośrednio do portu USB komputera, podłączony do sieci za pośrednictwem sieci Ethernet lub podłączone za pośrednictwem połączenia Bluetooth.

### <a name="scanner"></a>Skaner

Do dwóch kodów kreskowych skanerów można w tym samym czasie. Ta funkcja obsługuje scenariuszy, gdzie jest wymagana w celu skanowania duże i ciężkie przedmioty, skanera, który jest bardziej mobilni stałych skaner osadzony jest stosowana dla większości elementów o standardowych wymiarach, aby przyspieszyć czas realizacji transakcji. Skanery mogą być obsługiwane przez OPOS, platformy (Uniwersalnej systemu Windows) lub interfejsów klina klawiatury. USB lub Bluetooth może służyć do Podłącz skaner do komputera.

### <a name="msr"></a>MSR

Jeden czytnik kart magnetycznych USB (MSR) można skonfigurować przy użyciu sterowników OPOS. Jeśli chcesz użyć autonomicznych MSR dla środków elektronicznych transakcji płatniczych transferu (EFT), MSR muszą być zarządzane przez łącznik płatności. MSRs autonomiczny może służyć do zapisu lojalność klienta, logowanie pracownika i pozycję karty upominkowej, niezależnie od łącznika płatności.

### <a name="cash-drawer"></a>Szuflada kasowa

Dwie szuflady do kas mogą być obsługiwane na profilu sprzętu. Umożliwia to dwie zmiany aktywnego dla jednej kasy za dostępne w tym samym czasie. W przypadku zmian udostępnionych lub szuflady kasowej, który jest używany przez wiele urządzeń przenośnych POS w tym samym czasie dozwolony jest tylko jeden szuflady kasowej profilu sprzętu. Szuflady do kas mogą być podłączony bezpośrednio do portu USB komputera, podłączony do sieci lub podłączony do drukarki przyjęcia za pośrednictwem interfejsu RJ12. W niektórych przypadkach szuflady do kas mogą być połączone za pomocą technologii Bluetooth.

### <a name="line-display"></a>Wyświetlacz wierszowy

Wyświetla wiersz służą do wyświetlania produktów, salda transakcji i innych użytecznych informacji do klienta podczas transakcji. Wyświetlanie jednego wiersza można podłączyć do komputera za pomocą kabla USB przy użyciu sterowników OPOS.

### <a name="signature-capture"></a>Przechwytywanie podpisu

Urządzenia do przechwytywania podpisu można podłączyć bezpośrednio do portu USB komputera przy użyciu sterowników OPOS. Po skonfigurowaniu przechwytywania podpisu, klient jest monit o zalogowanie się na urządzeniu. Po podpis jest dostarczany, wykazano, że kasjer do akceptacji.

### <a name="scale"></a>Skalowanie

Skale można podłączyć do komputera za pomocą USP przy użyciu sterowników OPOS. Produkt, który jest oznaczony jako "Weighed" produkt zostanie dodany do transakcji, punktu sprzedaży odczytuje wagi z wagi, doda produktu do transakcji i używa ilości dostarczonego w skali.

### <a name="pin-pad"></a>Konsola PIN

Identyfikator osobisty numerycznej (PIN) są obsługiwane za pośrednictwem OPOS, ale musi być zarządzany za pośrednictwem łącznika płatności.

### <a name="secondary-display"></a>Wyświetlacz pomocniczy

Po skonfigurowaniu wyświetlaczu pomocniczym, Wyświetl numer 2 systemu Windows służy do pokazywania podstawowe informacje. Celem wyświetlacz pomocniczy jest do obsługi niezależnego oprogramowania (ISV) dostawcy rozszerzenie, ponieważ po rozpakowaniu wyświetlacz pomocniczy nie jest konfigurowalny i pokazuje zawartość ograniczona.

### <a name="payment-device"></a>Urządzenie płatnicze

Obsługa urządzeń płatności jest implementowana za pośrednictwem łącznika płatności. Urządzenia płatności można wykonać jedno lub wiele funkcji, które zapewniają innych klas urządzeń. Na przykład urządzenie płatności może funkcjonować jako MSR/czytnik kart, wyświetlaczy linearnych, urządzenia do przechwytywania podpisu lub Konsola PIN. Obsługa urządzeń płatności jest zaimplementowana niezależnie od pomocy technicznej autonomicznego urządzenia, dostarczanego dla innych urządzeń, które są zawarte w profilu sprzętowym.

## <a name="supported-interfaces"></a>Obsługiwane interfejsy
### <a name="opos"></a>OPOS

W celu zagwarantowania, że największą gamę urządzeń może służyć z Microsoft Dynamics 365 dla operacji - handel detaliczny, OLE dla standard branżowy POS jest podstawowy detalicznych platformy urządzenie peryferyjne, który jest obsługiwany w programie Microsoft Dynamics 365 dla operacji - sieci sprzedaży. OLE dla standardowych POS został wyprodukowany przez krajowe sieci sprzedaży federacyjnej (NRF), który ustanawia protokoły komunikacyjne standardowych urządzeń peryferyjnych sieci sprzedaży. OPOS jest powszechnie przyjętego wdrażanie OLE dla standardowych punktu sprzedaży. To został opracowany w połowie lat 1990 i został zaktualizowany kilka razy od tego czasu. OPOS zapewnia architektura sterownika urządzenia, który umożliwia łatwą integrację sprzętu punktu sprzedaży z systemami POS opartych na systemie Windows. OPOS formantów uchwyt komunikacji między zgodny sprzęt i oprogramowanie POS. Formant OPOS składa się z dwóch części:

-   **Obiekt formantu** – kontroli obiektu dla klasy urządzenia (na przykład wyświetla linia) udostępnia interfejs umożliwiający oprogramowaniem. Monroe Consulting Services ([www.monroecs.com](http://www.monroecs.com/)) zawiera zestaw standardowych OPOS sterowanie obiektami, które są znane jako obiekty wspólnej kontroli (CCOs). CCOs są używane do testowania składnika POS Microsoft Dynamics 365 dla operacji - sieci sprzedaży. W związku z tym Testowanie pomaga zagwarantować, że, jeśli Microsoft Dynamics 365 dla operacji - obsługuje sieci sprzedaży, który może być obsługiwany klasy urządzenia za pośrednictwem OPOS, wiele typów urządzeń, pod warunkiem, że producent dostarczył obiektu usługi, który jest przeznaczony dla OPOS. Nie trzeba jawnie badania każdego typu urządzenia.
-   **Obiekt Usługa** — obiekt usługi zapewnia komunikację między obiekt formantu (CCO) a urządzeniem. Zazwyczaj obiekt usługi dla urządzenia jest dostarczany przez producenta urządzenia. Jednak w niektórych przypadkach trzeba będzie pobrać obiektu usługi z witryny producenta w sieci Web. Na przykład może być dostępny nowszą obiektu usługi. Aby odszukać adres witryny producenta w sieci Web, zajrzyj do dokumentacji sprzętu.

[![Kontroli obiektu i obiektu usługi](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png) Obsługa do wykonania OPOS OLE POS pomaga zagwarantować, że jeśli producenci urządzeń i wydawców POS poprawnie implementuje standard, systemy POS i obsługiwane urządzenia mogą pracować razem, nawet jeśli nie zostały one wcześniej przetestowane razem. **Uwaga:** Obsługa OPOS nie gwarantuje wsparcie dla wszystkich urządzeń, które mają sterowniki OPOS. Microsoft Dynamics 365 dla operacji - sieci sprzedaży po raz pierwszy musi obsługiwać tego typu urządzenia lub klasy, poprzez OPOS. Ponadto obiekty usługi nie zawsze być dostęp do najnowszych wersji CCOs. Należy także pamiętać, że, ogólnie, jakość obiektów usługi jest różna.

### <a name="windows"></a>Windows

Drukowanie paragonów w punkcie sprzedaży jest zoptymalizowany dla OPOS. OPOS wydaje się być znacznie szybsza niż opcja drukowania za pośrednictwem systemu Windows. Dlatego dobrze jest użyć OPOS, szczególnie w sektorze handlu detalicznego gdzie paragony 40 kolumn są drukowane i czasy transakcji muszą być szybko. Dla większości urządzeń można użyć formantów OPOS. Niektóre drukarki OPOS przyjęcia obsługuje również sterowników systemu Windows. Przy użyciu sterownika systemu Windows, są dostępne najnowsze czcionek i jednej drukarki sieciowej dla wielu kas. Istnieją jednak wady używania sterowników systemu Windows. Oto kilka przykładów następujące wady:

-   Gdy używane są sterowniki dla systemu Windows, obrazy są renderowane przed drukowaniem. W związku z tym drukowanie wydaje się być wolniejsze, niż w przypadku drukarek, które wykorzystują formanty OPOS.
-   Urządzenia podłączone do drukarki ("łańcuchu") mogą nie działać poprawnie kiedy są używane sterowniki dla systemu Windows. Na przykład szuflady kasowej może się nie otworzyć lub drukarki dostawy nie może być wyraz zgodnie z oczekiwaniami.
-   OPOS obsługuje także szerszy zestaw zmiennych, które są specyficzne dla drukarki przyjęcia sprzedaży detalicznej, takie jak cięcia papieru lub drukowania dokumentów dostawy.

Jeśli formanty OPOS są dostępne dla drukarki systemu Windows, której używasz, drukarka powinna nadal działa poprawnie z Microsoft Dynamics 365 dla operacji - sieci sprzedaży.

### <a name="universal-windows-platform"></a>Platformę uniwersalną systemu Windows

UWP, w przypadku sprzedaży detalicznej, urządzenia peryferyjne, jest powiązany do obsługi systemu Windows dla urządzeń typu Plug and Play. Po podłączeniu urządzenia typu Plug and Play do wersji systemu operacyjnego Windows, który obsługuje tego typu urządzenia, sterownik nie jest wymagane urządzenie, które ma być używane zgodnie z przeznaczeniem. Na przykład, jeśli system Windows wykryje urządzenie Bluetooth głośnika, system operacyjny wie, że urządzenie ma **głośników** typ klasy. W związku z tym i traktuje jako głośnik tego urządzenia. Nie dodatkowe ustawienia jest wymagane. W przypadku urządzeń POS można podłączyć wiele urządzeń USB, a system Windows będzie rozpoznawał je jako urządzenia interfejsu HID (HIDs). Jednakże to może nie móc określają możliwości, które zapewnia urządzenia, ponieważ urządzenie nie określono klasy lub typu urządzenia. W systemie Windows 10 zostały dodane klas urządzeń dla skanerów kodu kreskowego i MSRs. W związku z tym jeśli urządzenie deklaruje, że do 10 systemu Windows jako urządzenie w jednej z tych klas, system Windows będzie nasłuchiwać zdarzenia z urządzenia we właściwym czasie. Nowoczesne POS obsługuje UWP MSRs i skanery. W związku z tym gdy jest gotowy do danych wejściowych z jednego z tych urządzeń, a urządzenie należy do jednej z tych klas jest podłączone, urządzenie może służyć. Na przykład jeśli UWP skaner kodów kreskowych jest podłączony do komputera systemu Windows 10 i Logowanie kodu kreskowego jest skonfigurowany dla nowoczesnych POS, skaner kodów kreskowych staną się aktywne na ekranie logowania. Nie dodatkowe ustawienia jest wymagane. Dodatkowe klasy punkt usług UWP urządzeń są dodawane do systemu Windows. Klasy te zawierają klasy szuflady do kas i drukarki paragonów. Obsługa tych nowych klas urządzeń w nowoczesnych POS jest oczekujące.

### <a name="keyboard-wedge"></a>Klin klawiatury

Urządzenia klina klawiatury wysyłać dane do komputera, tak jakby te dane zostały wpisane z klawiatury. W związku z tym Domyślnie pole, które jest aktywne w punkcie sprzedaży otrzyma dane, które jest skanowany lub czytniku. W niektórych przypadkach może to spowodować niewłaściwego typu danych, które mają być skanowane w niewłaociwym polu. Na przykład kod kreskowy może być skanowany w polu, które jest przeznaczony do wprowadzania danych karty kredytowej. W wielu przypadkach jest logika w punkcie sprzedaży, która określa, czy dane, które jest skanowany lub czytniku jest kod kreskowy lub wsuń kartę do czytnika. W związku z tym dane jest obsługiwana prawidłowo. Jednakże gdy urządzenia są ustawione jako OPOS zamiast klawiatury klina urządzeń, istnieje większą kontrolę nad jak dane z tych urządzeń może być spożywany, ponieważ więcej jest "znany" o urządzeniu, że dane pochodzą od. Na przykład danych przy użyciu skanera kodu kreskowego jest automatycznie rozpoznawana jako kod kreskowy i skojarzonego z nim rekordu w bazie danych znajduje się łatwiej i szybciej niż Jeśli rodzajowy ciąg wyszukiwania były używane, podobnie jak w przypadku urządzeń klina klawiatury.

### <a name="native-printer"></a>Macierzysty drukarki

Macierzysty (lub o nazwie "Urządzenie" jako typ w profilu sprzętowym) drukarki można skonfigurować na monitowanie użytkownika o wybranie drukarki, który jest skonfigurowany dla komputera. Gdy drukarka z **urządzenia** typ jest skonfigurowany, jeśli nowoczesnych POS napotka polecenia print, użytkownik jest monitowany o wybranie drukarki z listy. To zachowanie różni się od zachowania sterowników dla systemu Windows, ponieważ **Windows** typ drukarki profil sprzętu nie pokazuje listę drukarek. Zamiast tego wymaga podania o nazwie drukarki w **nazwa urządzenia** pole.

### <a name="windows"></a>Windows

**Windows** typ urządzenia jest używany tylko dla drukarek. Po skonfigurowaniu drukarki w systemie Windows w profilu sprzętu, należy podać nazwę drukarki. Nowoczesne POS napotka zdarzenia drukowania, jeśli skonfigurowano drukarki w systemie Windows, zdarzenie zostanie przekazany do określonej drukarki systemu Windows. Użytkownik nie będzie monitowany wybierz drukarkę.

### <a name="network"></a>Sieć

Szuflady do kas mogą być adresowane sieci, drukarki paragonów i terminale płatności może służyć sieci, bezpośrednio przez stację sprzętu komunikacji międzyprocesowej (IPC), która jest wbudowana w nowoczesne POS aplikacji dla systemu Windows lub przez stację sprzętu usług IIS dla innych klientów nowoczesnych POS.

## <a name="hardware-station-deployment-options"></a>Opcje wdrażania stacji sprzętu
### <a name="ipc-built-in"></a>IPC (wbudowany)

Stacja sprzętowa komunikacji międzyprocesowej (IPC) jest wbudowana w nowoczesne POS aplikacji dla systemu Windows. Aby użyć stacji sprzętu IPC, przypisywanie profilu sprzętu do rejestru, który będzie używać nowoczesnych POS aplikacji dla systemu Windows. Następnie utwórz stacja sprzętu **dedykowane** typu dla sklepu, w którym rejestr będzie używany. Po uruchomieniu nowoczesnych POS stacja sprzętowa IPC jest aktywny, i urządzenia peryferyjne punktu sprzedaży, które zostały skonfigurowane będzie gotowe do użycia. Jeśli możesz tymczasowo nie wymagają lokalnych sprzętu z jakiegoś powodu, użyj **Zarządzanie stacjami sprzętu** operacji, aby wyłączyć możliwości sprzętowych stacji. Nowoczesne POS służy także stacja sprzętowa IPC do bezpośredniego komunikowania się z urządzeniami sieciowymi.

### <a name="iis"></a>Usługi IIS

Można użyć usług IIS lub autonomiczną wersję programu stacji sprzętu na dwa sposoby. Deskryptor "IIS" oznacza, że aplikacja POS łączy do stacji sprzętu za pomocą programu Microsoft Internet Information Services. Aplikacja punktu sprzedaży łączy się stacji sprzętu IIS za pośrednictwem usług sieci web, które są uruchamiane na komputerze gdzie są podłączone urządzenia. Jeśli używany jest program IIS, urządzenia peryferyjne sprzedaży detalicznej, które są podłączone do stacji sprzętu mogą być używane przez dowolnego rejestru punktu sprzedaży, który jest w tej samej sieci jako stacja sprzętu usług IIS. Ponieważ tylko nowoczesnych POS dla systemu Windows zawiera wbudowaną obsługę urządzeń peryferyjnych detalicznych, wszystkie inne aplikacje nowoczesnych POS należy użyć stacji sprzętu usług IIS do komunikowania się z urządzeniami peryferyjnymi POS, które są skonfigurowane w profilu sprzętowym. W związku z tym każde wystąpienie stacja sprzętowa IIS wymaga komputera, który uruchamia usługę sieci web i aplikacji, która komunikuje się z urządzeniami. Stacja sprzętowa usług IIS jest wymagany dla wszystkich aplikacji non - Windows Modern POS.

#### <a name="dedicated"></a>Wyznaczony

Modern POS używa stacji sprzętu **dedykowane** typu do wykrywania urządzenia peryferyjne są podłączone bezpośrednio do komputera, gdzie aplikacja jest używany. Jednakże **dedykowane** typu można również dla stacji sprzętu usług IIS. W przypadku stałych, tradycyjne Retail POS używa POS chmury jako aplikacji Retail POS **dedykowane** typ stacji sprzętu jest używany dla stacji sprzętu internetowych usług informacyjnych, które są wdrożone na tym samym komputerze, uruchomionym POS chmury. Z punktu widzenia urządzenia peryferyjne sprzedaży detalicznej dedykowany stacja sprzętowa IIS lepiej detalicznych Obsługa urządzeń peryferyjnych dla stałych, tradycyjne scenariuszy POS. Dedykowane stacje obsługują wszystkie urządzenia peryferyjne, które są obsługiwane w profilu sprzętowym.

#### <a name="shared"></a>Współdzielony

Udostępniony sprzęt, który stacje mają być używane przez wiele urządzeń POS za pomocą ciągu dnia. Wspólne stacje są zoptymalizowane do obsługi tylko szuflady do kas, drukarki paragonów i terminale sprzętu. Nie można bezpośrednio połączyć czytniki kodów kreskowych autonomicznych, MSRs, wyświetla wiersz, wagi lub innych urządzeń. W przeciwnym razie konfliktów ma miejsce, gdy wiele urządzeń POS spróbować przejąć te urządzenia peryferyjne w tym samym czasie. Oto, jak konflikty są zarządzane dla obsługiwanych urządzeń:

-   **Szuflada kasowa** – szuflady kasowej otwierają się zdarzenie, które jest wysyłane do urządzenia. Tylko problem, który może wystąpić, gdy szuflada kasowa jest nazywany występuje, jeśli jest już otwarta szuflada kasowa. W przypadku sprzętu udostępnionego stacje szuflady kasowej powinien być ustawiony na **Shared** w profilu sprzętowym. Ustawienie to zapobiega sprawdzanie, czy szuflada kasowa jest już otwarty podczas wysyłania polecenia Otwórz punktu sprzedaży.
-   **Drukarki paragonów** – Jeżeli otrzymania dwóch poleceń drukowania są wysyłane do stacji sprzętu, w tym samym czasie, jedno z poleceń mogą być utracone, w zależności od urządzenia. Niektóre urządzenia mają wewnętrzną pamięć lub buforowania, który może zapobiec występowaniu tego problemu. Jeśli polecenia print zakończy się niepowodzeniem, kasjer otrzymuje komunikat o błędzie i można ponowić próbę wykonania polecenia drukowania z punktu sprzedaży.
-   **Płatności końcowych** -Jeśli kasjer próbuje przetargu transakcji na terminalu płatności, która jest już używana, komunikat powiadamia kasjer, że terminal jest używany i prosi kasjer powinni spróbować później. Zwykle kasjerzy można zobaczyć, że terminal jest już używana i będzie czekać do momentu zakończenia innych transakcji przed próbują ponownie przetargu.

Sprawdzanie poprawności jest planowane w przyszłości, aby wykryć, czy nieobsługiwane urządzenia są ustawione dla profilu sprzętu, który jest mapowany do stacji udostępnionego sprzętu. Jeśli wszystkie nieobsługiwane urządzenia zostaną wykryte, użytkownik otrzyma komunikat informujący, że urządzenia nie są obsługiwane dla stacji udostępnionego sprzętu. W przypadku sprzętu udostępnionego stacje **wybierz po przetargu** opcja jest ustawiona na **tak** na poziomie rejestru. Użytkownik POS następnie jest monitowany o wybranie stacji sprzętu po wybraniu oferty dla transakcji w punkcie sprzedaży. Po wybraniu stacji sprzętu tylko w czasie o zaproszeniu do składania ofert, wybór stacji sprzętu jest dodawany bezpośrednio do punktu sprzedaży przepływu pracy dla scenariuszy mobilnych. Jako dodatkowe korzyści wyświetlacza wierszowego na płatności terminali nie jest używany dla współużytkowanych. Jeśli terminali płatności jest używany jako wyświetlacz wierszowy, innych użytkowników może być zablokowane przy użyciu tego terminalu, aż do zakończenia transakcji. W scenariuszach mobilnych do transakcji w dłuższym okresie mogą być dodane wiersze. W związku z tym **wybierz po przetargu** opcja jest wymagana w celu zapewnienia optymalnego urządzenia dostępności.

### <a name="network-peripherals"></a>Urządzenia peryferyjne

Oznaczenie sieci dla urządzenia w profilu sprzętu umożliwia szuflady do kas, drukarki paragonów i terminale połączenie za pośrednictwem połączenia sieciowego.

#### <a name="modern-pos-for-windows"></a>Nowoczesne POS dla systemu Windows

Można określić adresy IP dla urządzenia peryferyjne w dwóch miejscach. Jeśli klient nowoczesne okna POS używa jednego zestawu urządzenia peryferyjne, należy ustawić adresy IP dla tych urządzeń za pomocą **konfiguracji IP** opcji w okienku akcji dla autorejestracji. W przypadku urządzenia sieciowe, które będą udostępniane między Rejestry punktu sprzedaży, profil sprzętu, który ma przypisane do niego urządzenia sieciowe mogą być mapowane bezpośrednio do stacji udostępnionego sprzętu. Przypisywanie adresów IP, wybierz stację tego sprzętu na **sklepów detalicznych** strona, a następnie użyj **konfiguracji IP** opcji w **stacje** sekcji, aby określić urządzenia sieciowe, które są przypisane do tego dworca sprzętu. W przypadku stacji sprzętu, które mają tylko urządzenia sieciowe nie musisz wdrożyć sama stacja sprzętu. W takim przypadku stacja sprzętowa jest wymagany tylko w celu koncepcyjnie grupy sieci adresowanych urządzeń według ich lokalizacji w sklepu sieci sprzedaży.

#### <a name="cloud-pos-modern-pos-for-ios-and-modern-pos-for-android"></a>Chmury POS, nowoczesnych POS dla iOS i nowoczesnych POS dla Androida

Logikę, która napędza fizycznie podłączone i adresach sieciowych urządzeń peryferyjnych znajduje się w stacji sprzętu. W związku z tym dla wszystkich klientów POS z wyjątkiem nowoczesnych POS for Windows, stację sprzętu IIS musi być rozwinięty i aktywna, aby włączyć POS do komunikowania się z urządzeniami peryferyjnymi, niezależnie od tego, czy te urządzenia peryferyjne są fizycznie podłączony do stacji sprzętu lub kierowane przez sieć.

## <a name="setup-and-configuration"></a>Instalacja i Konfiguracja
### <a name="hardware-station-installation"></a>Instalacja sprzętu stacji

Aby uzyskać informacje, zobacz [sprzedaży detalicznej konfiguracja stacji sprzętu i instalacji](retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Nowoczesne POS for Windows Instalacja i Konfiguracja

Aby uzyskać informacje, zobacz [Retail POS nowoczesnych konfiguracji i instalacji](retail-modern-pos-device-activation.md).

### <a name="opos-device-setup-and-configuration"></a>Instalator urządzenia OPOS i Konfiguracja

Aby uzyskać więcej informacji na temat składników OPOS zobacz sekcję "Obsługiwane interfejsy" tego dokumentu. Zazwyczaj sterowniki OPOS są dostarczane przez producenta urządzenia. Po zainstalowaniu sterownika urządzenia zostanie OPOS dodaje klucz do rejestru systemu Windows w jednej z następujących lokalizacji:

-   **32-bitowy system:** HKEY\_lokalnego\_MACHINESOFTWAREOLEforRetailServiceOPOS
-   **64-bitowy system:** HKEY\_lokalnego\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS

W tej lokalizacji rejestru ServiceOPOS skonfigurowane urządzenia są zorganizowane według klasy urządzenia OPOS. Wiele sterowników urządzeń są zapisywane.

## <a name="supported-scenarios-by-hardware-station-type"></a>Obsługiwane scenariusze przez typ stacji sprzętu
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Obsługa klienta — stacja sprzętowa IPC kontra stacja sprzętowa usług IIS

W poniższej tabeli przedstawiono topologii i scenariuszy wdrażania, które są obsługiwane.

| Klient      | Stacja sprzętowa IPC | Stacja sprzętowa usług IIS |
|-------------|----------------------|----------------------|
| Aplikacja systemu Windows | Tak                  | Tak                  |
| Cloud POS   | Nr                   | Tak                  |
| Android     | Nr                   | Tak                  |
| iOS         | Nr                   | Tak                  |

### <a name="network-peripherals"></a>Urządzenia peryferyjne

Urządzenia peryferyjne są obsługiwane bezpośrednio przez stację sprzętu, która jest wbudowana w nowoczesne POS aplikacji dla systemu Windows. Dla innych klientów należy wdrożyć w stację sprzętu usług IIS.

| Klient      | Stacja sprzętowa IPC | Stacja sprzętowa usług IIS |
|-------------|----------------------|----------------------|
| Aplikacja systemu Windows | Tak                  | Tak                  |
| Cloud POS   | Nr                   | Tak                  |
| Android     | Nr                   | Tak                  |
| iOS         | Nr                   | Tak                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Obsługiwane typy urządzenia według typów sprzętu stacji
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Nowoczesne POS dla systemu Windows ze stacją sprzętu IPC (wbudowany)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Klasa obsługiwanego urządzenia</th>
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
<li>UWP (bez konfiguracji jest wymagany).</li>
<li>Klin klawiatury (Instalator nie jest wymagane).</li>
</ul></td>
</tr>
<tr class="even">
<td>Szuflada</td>
<td><ul>
<li>OPOS</li>
<li>Sieci <strong>Uwaga:</strong> można ustawić tylko jedną szufladę wyżej, jeśli <strong>wykorzystania udostępnionych shift</strong> jest skonfigurowana na szuflady.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Szuflada 2</td>
<td><ul>
<li>OPOS</li>
<li>Sieci <strong>Uwaga:</strong> można ustawić tylko jedną szufladę wyżej, jeśli <strong>wykorzystania udostępnionych shift</strong> jest skonfigurowana na szuflady.</li>
</ul></td>
</tr>
<tr class="even">
<td>Skaner</td>
<td><ul>
<li>OPOS</li>
<li>UWP (bez konfiguracji jest wymagany).</li>
<li>Klin klawiatury (Instalator nie jest wymagane).</li>
</ul></td>
</tr>
<tr class="odd">
<td>Skaner 2</td>
<td><ul>
<li>OPOS</li>
<li>UWP (bez konfiguracji jest wymagany).</li>
<li>Klin klawiatury (Instalator nie jest wymagane).</li>
</ul></td>
</tr>
<tr class="even">
<td>Skalowanie</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Konsola PIN</td>
<td>OPOS (obsługa jest zapewniana poprzez dostosowywanie łącznika płatności).</td>
</tr>
<tr class="even">
<td>Przechwytywanie podpisu</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Terminal płatniczy </td>
<td><ul>
<li>Obsługa urządzeń niestandardowych</li>
<li>Sieci (Aby uzyskać więcej informacji, zobacz dokumentację łącznika płatności).</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Wszyscy klienci nowoczesnych POS, które mają dedykowane stacji sprzętu usług IIS

**Uwaga:** gdy stacja sprzętowa usług IIS jest "dedykowany", jest relacja jeden do jednego między klientem POS i stacji sprzętu.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Klasa obsługiwanego urządzenia</th>
<th>Obsługiwane interfejsy</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Drukarka</td>
<td><ul>
<li>OPOS</li>
<li>Sterownik systemu Windows <strong>Uwaga:</strong> For Windows drukarki w sieci, użytkownik stacji sprzęt musi mieć uprawnienia dostępu do drukarki.</li>
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
<li>Sieci <strong>Uwaga:</strong> tylko jedną szufladę na profil sprzętu można skonfigurować if <strong>wykorzystania udostępnionych shift</strong> jest skonfigurowana na szuflady.</li>
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
<td>OPOS (obsługa jest zapewniana poprzez dostosowywanie łącznika płatności).</td>
</tr>
<tr class="odd">
<td>SIG. przechwytywanie</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Terminal płatniczy </td>
<td><ul>
<li>Obsługa urządzeń niestandardowych</li>
<li>Sieci (Aby uzyskać więcej informacji, zobacz dokumentację łącznika płatności).</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Wszyscy klienci nowoczesnych POS, które mają stację sprzętową udostępnionych usług IIS

**Uwaga:** kiedy stacja sprzętowa usług IIS jest "udostępniony", wiele urządzeń można użyć stacji sprzętu w tym samym czasie. W tym scenariuszu należy używać tylko urządzenia, które są wymienione w poniższej tabeli. Jeśli spróbujesz udostępnić urządzeń, które nie są wymienione w tym miejscu, takich jak czytniki kodów kreskowych i MSRs, wystąpią błędy podczas wielu urządzeń spróbować przejąć samego urządzenie peryferyjne. W przyszłości taka konfiguracja zostanie wyraźnie zabronione.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Klasa obsługiwanego urządzenia</th>
<th>Obsługiwane interfejsy</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Drukarka</td>
<td><ul>
<li>OPOS</li>
<li>Sterownik systemu Windows <strong>Uwaga:</strong> For Windows drukarki w sieci, użytkownik stacji sprzęt musi mieć uprawnienia dostępu do drukarki.</li>
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
<li>Sieci <strong>Uwaga:</strong> tylko jedną szufladę na profil sprzętu można skonfigurować if <strong>wykorzystania udostępnionych shift</strong> jest skonfigurowana na szuflady.</li>
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
<li>Sieci (Aby uzyskać więcej informacji, zobacz dokumentację łącznika płatności).</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Konfiguracja dla obsługiwanych scenariuszach
Aby uzyskać więcej informacji dotyczących sposobu tworzenia profilów sprzętowych, zobacz [Definiuj i obsługa klientów kanału, w tym rejestrów i stacje](define-maintain-channel-clients-registers-hw-stations.md). **Uwaga:** For Microsoft Dynamics 365 dla wersji operacji 1611, profil sprzętowy stacji nie jest już używana. Atrybuty, które uprzednio określonymi przez użytkownika w profilu sprzętu stacji są teraz częścią sama stacja sprzętu.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Nowoczesne POS dla systemu Windows ze stacją sprzętu IPC (wbudowany)

Ta konfiguracja jest najbardziej typową konfigurację dla tradycyjnych, stałe rejestry punktu sprzedaży. W tym scenariuszu informacje o profilu sprzętu jest mapowany bezpośrednio do autorejestracji. Należy również określić numer terminalu EFT na autorejestracji. Aby ustawić tę konfigurację, wykonaj następujące kroki.

1.  Utwórz profil sprzętowy, w którym wszystkie wymagane urządzenia peryferyjne są skonfigurowane.
2.  Mapować profil sprzętu punktu sprzedaży.
3.  Tworzenie stacji sprzętu z **dedykowane** typu do sprzedaży detalicznej, w którym będzie używany do rejestru punktu sprzedaży. Opis jest opcjonalny. **Uwaga:** nie trzeba ustawiać inne właściwości stacji sprzętu. Wszystkich innych wymaganych informacji, takich jak profil sprzętu będą pochodzić z autorejestracji.
4.  Kliknij **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramu dystrybucji**.
5.  Wybierz **1090** harmonogramu dystrybucji do synchronizacji nowego profilu sprzętu do magazynu. Kliknij **Uruchom teraz** do synchronizacji zmian w punkcie sprzedaży.
6.  Wybierz **1040** harmonogramu dystrybucji do synchronizowania stacji nowego sprzętu do magazynu. Kliknij **Uruchom teraz** do synchronizacji zmian w punkcie sprzedaży.
7.  Zainstaluj i Aktywuj nowoczesnych POS dla systemu Windows.
8.  Uruchom nowoczesnych POS dla Windows i zacząć używać przyłączonych urządzeń peryferyjnych.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Wszyscy klienci nowoczesnych POS, które mają dedykowane stacji sprzętu usług IIS

Taka konfiguracja może służyć dla wszystkich klientów nowoczesnych POS, które mają stacji sprzętu, które jest używane wyłącznie przez jednego punktu sprzedaży zarejestrować. Aby ustawić tę konfigurację, wykonaj następujące kroki.

1.  Utwórz profil sprzętowy, w którym wszystkie wymagane urządzenia peryferyjne są skonfigurowane.
2.  Tworzenie stacji sprzętu z **dedykowane** typu do sprzedaży detalicznej, w którym będzie używany do rejestru punktu sprzedaży.
3.  Na stacji wydzielonych sprzętowych należy ustawić następujące właściwości:
    -   **Nazwa hosta** — nazwa komputera hosta, gdzie będzie uruchamiana na stacji sprzętu. **Uwaga:** chmur Retail POS można rozwiązać **localhost** do określenia komputera lokalnego, gdzie działa POS chmury. Jednak certyfikat, który jest wymagane w celu parowanie POS chmura stacji sprzętu musi mieć "Localhost" jako nazwy komputera. Aby uniknąć problemów, zaleca się, że listy wystąpienie każdej stacji wydzielonych sprzętowych dla sklepu, zgodnie z wymaganiami. Dla każdej stacji sprzętu nazwę hosta powinna być nazwą określonego komputera gdzie będą wdrażane stacji sprzętu.
    -   **Port** — port wykorzystywany dla stacji sprzętu do komunikacji z klientem nowoczesnych POS.
    -   **Profil sprzętu** -Jeśli profil sprzętu nie jest pod warunkiem na sama stacja sprzęt będzie używany profil sprzętu, który jest przypisany do rejestru.
    -   **Numer EFT punktu sprzedaży** — identyfikator terminalu EFT do użycia podczas EFT zezwoleń są wysyłane. Ten identyfikator jest dostarczana przez agenta rozliczeniowego kart kredytowych.
    -   **Nazwa pakietu** — pakiet stacji sprzętu używanego do stacji sprzętu jest rozmieszczana.

4.  Kliknij **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramu dystrybucji**.
5.  Wybierz **1090** harmonogramu dystrybucji do synchronizacji nowego profilu sprzętu do magazynu. Kliknij **Uruchom teraz** do synchronizacji zmian w punkcie sprzedaży.
6.  Wybierz **1040** harmonogramu dystrybucji do synchronizowania stacji nowego sprzętu do magazynu. Kliknij **Uruchom teraz** do synchronizacji zmian w punkcie sprzedaży.
7.  Zainstaluj sprzęt stacji. Aby uzyskać więcej informacji dotyczących sposobu instalowania stacji sprzętu, zobacz [sprzedaży detalicznej konfiguracja stacji sprzętu i instalacji](retail-hardware-station-configuration-installation.md).
8.  Zainstaluj i Aktywuj nowoczesnych POS. Aby uzyskać więcej informacji dotyczących sposobu instalowania nowoczesnych POS, zobacz [Retail POS nowoczesnych konfiguracji i instalacji](retail-modern-pos-device-activation.md).
9.  Zaloguj się w nowoczesnych POS i wybierz **wykonywanie operacji bez użycia szuflady**.
10. Uruchom **Zarządzanie stacjami sprzętu** operacji.
11. Kliknij **zarządzanie**.
12. Na stronie Zarządzanie sprzętem stacji ustawić opcję, aby włączyć stację sprzętu.
13. Wybierz stację sprzętu, a następnie kliknij przycisk **para**.
14. Po sparowaniu stacji sprzętu, kliknij przycisk **Zamknij**.
15. Na stronie Wybór stacji sprzętu kliknij stację ostatnio zaznaczonego sprzętu Aby je uaktywnić.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Wszyscy klienci nowoczesnych POS, które mają stację sprzętową udostępnionych usług IIS

Konfiguracja ta może służyć do wszystkich klientów nowoczesnych POS, które współużytkują stacje z innymi urządzeniami. Aby ustawić tę konfigurację, wykonaj następujące kroki.

1.  Tworzenie profilu sprzętu, gdzie wymagane urządzenia peryferyjne są skonfigurowane.
2.  Tworzenie stacji sprzętu z **Shared** typu do sprzedaży detalicznej, w którym będzie używany do rejestru punktu sprzedaży.
3.  Na stacji sprzętu udostępnionego należy ustawić następujące właściwości:
    -   **Nazwa hosta** — nazwa komputera hosta, gdzie będzie uruchamiana na stacji sprzętu.
    -   **Opis** — tekst, który pomoże zidentyfikować stację, sprzętu, takich jak **zwraca** lub **przednich magazynu**.
    -   **Port** — port wykorzystywany dla stacji sprzętu do komunikacji z klientem nowoczesnych POS.
    -   **Profil sprzętu** — dla stacji sprzętu udostępnionego każdej stacji sprzęt powinien mieć profil sprzętu. Profile sprzętu mogą być współużytkowane przez stacje, ale musi być mapowany do każdej stacji sprzętu. Ponadto zaleca się zastosowanie zmiany udostępnione podczas wielu urządzeń użyć tej samej stacji sprzętu udostępnionego. Aby skonfigurować udostępnione klawisz shift, kliknij przycisk **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**konfiguracji punktu sprzedaży**&gt;**profile POS**&gt;**profile sprzętu**. Dla każdego profilu sprzętu udostępnionego zaznacz szuflady kasowej i ustaw **Shared shift szuflady** opcji w celu **tak**.
    -   **Numer EFT punktu sprzedaży** — identyfikator terminalu EFT do użycia podczas EFT zezwoleń są wysyłane. Ten identyfikator jest dostarczana przez agenta rozliczeniowego kart kredytowych.
    -   **Nazwa pakietu** — pakiet stacji sprzętu używanego do stacji sprzętu jest rozmieszczana.

4.  Powtórz kroki 2 i 3 dla każdej stacji dodatkowego sprzętu, który jest wymagany w magazynie.
5.  Kliknij **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramu dystrybucji**.
6.  Wybierz **1090** harmonogramu dystrybucji do synchronizacji nowego profilu sprzętu do magazynu. Kliknij **Uruchom teraz** do synchronizacji zmian w punkcie sprzedaży.
7.  Wybierz **1040** harmonogramu dystrybucji do synchronizowania stacji nowego sprzętu do magazynu. Kliknij **Uruchom teraz** do synchronizacji zmian w punkcie sprzedaży.
8.  Stacja sprzętu należy zainstalować na każdym komputerze hosta, który został ustawiony w krokach 2 i 3. Aby uzyskać więcej informacji dotyczących sposobu instalowania stacji sprzętu, zobacz [sprzedaży detalicznej konfiguracja stacji sprzętu i instalacji](retail-hardware-station-configuration-installation.md).
9.  Zainstaluj i Aktywuj nowoczesnych POS. Aby uzyskać więcej informacji dotyczących sposobu instalowania nowoczesnych POS, zobacz [Retail POS nowoczesnych konfiguracji i instalacji](retail-modern-pos-device-activation.md).
10. Zaloguj się w nowoczesnych POS i wybierz **wykonywanie operacji bez użycia szuflady**.
11. Uruchom **Zarządzanie stacjami sprzętu** operacji.

12. Kliknij **zarządzanie**.
13. Na stronie Zarządzanie sprzętem stacji ustawić opcję, aby włączyć stację sprzętu.
14. Wybierz stację sprzętu, a następnie kliknij przycisk **para**.
15. Powtórz krok 14 dla każdej stacji sprzętu, którego użyje nowoczesnych POS.
16. Po sparowaniu wszystkie stacje wymagany sprzęt, kliknij przycisk **Zamknij**.
17. Na stronie Wybór stacji sprzętu kliknij stację ostatnio zaznaczonego sprzętu Aby je uaktywnić. **Uwaga:** Jeśli urządzenia często używają różnych stacje, zaleca się skonfigurowanie nowoczesnych POS kasjerów, aby wybrać stację sprzętu, kiedy zaczynają procedury przetargowej. Kliknij **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**rejestruje**. Umożliwia wybranie rejestru, a następnie ustaw **wybierz po przetargu** opcji w celu **tak**. Użyj **1090** harmonogramu dystrybucji, aby zsynchronizować zmiany do bazy danych kanału.

## <a name="extensibility"></a>Możliwości rozszerzania
Aby uzyskać informacji na temat scenariuszy rozszerzania dla stacji sprzętu, zobacz [rozszerzania sprzętu stacji](dev-itpro/hardware-station-extensibility.md).

## <a name="security"></a>Zabezpieczenia
Zgodnie z obowiązującymi normami bezpieczeństwa, następujące ustawienia powinny być używane w środowisku produkcyjnym: **Uwaga:** Instalatora stacji sprzętu będzie automatycznie wprowadzić te zmiany rejestru jako część instalacji za pośrednictwem samoobsługowych.

-   Należy wyłączyć protokół Secure Sockets Layer (SSL).
-   Tylko zabezpieczeń TLS (Transport Layer) w wersji 1.2 (lub bieżącej wersji najwyższym) powinny być włączone i używane. **Uwaga:** domyślnie, SSL i TLS z wyjątkiem TLS 1.2 wszystkich wersji są wyłączone. Aby edytować lub włączyć te wartości, wykonaj następujące kroki:
    1.  Naciśnij klawisz Windows logo klawisz R, aby otworzyć **uruchomić** okna.
    2.  W **Otwórz** wpisz **Regedit**, a następnie kliknij przycisk **OK**.
    3.  Jeśli **Kontrola konta użytkownika** zostanie wyświetlone okno komunikatu, kliknij przycisk **tak**.
    4.  W **Edytora rejestru** okna, przejdź do **HKEY\_lokalnego\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols**. Następujące klucze zostały automatycznie wprowadzone do umożliwienia TLS 1.2 tylko:
        -   TLS 1.2Server: włączone = 1
        -   TLS 1.2Server:DisabledByDefault = 0
        -   TLS 1.2Client: włączone = 1
        -   TLS 1.2Client:DisabledByDefault = 0
        -   TLS 1.1Server: włączone = 0
        -   TLS 1.1Client: włączone = 0
        -   TLS 1.0Server: włączone = 0
        -   TLS 1.0Client: włączone = 0
        -   SSL 3.0Server: włączone = 0
        -   SSL 3.0Client: włączone = 0
        -   SSL 2.0Server: włączone = 0
        -   SSL 2.0Client: włączone = 0
-   Nie dodatkowych sieci powinny być otwarte, chyba że są one wymagane ze względów znane, określonego.
-   Udostępnianie zasobów Cross pochodzenia musi być wyłączony i należy określić dozwolonych pochodzenia, które są akceptowane.
-   Tylko zaufanych urzędów certyfikacji powinny służyć do uzyskiwania certyfikatów, które będą używane na komputerach stacji sprzętu.

**Uwaga:** jest bardzo ważne, przejrzyj wskazówki dotyczące zabezpieczeń dla usług IIS i wymagania płatności Card Industry (PCI).

## <a name="peripheral-simulator"></a>Symulator urządzeń peryferyjnych
Aby uzyskać informacje, zobacz [symulator obwodowych Retail](retail-peripheral-simulator.md).

## <a name="microsofttested-peripheral-devices"></a>Urządzenia peryferyjne Microsofttested
### <a name="ipc-built-in-hardware-station"></a>Stacja sprzętowa IPC (wbudowany)

Następujące urządzenia peryferyjne zostały przetestowane przy użyciu stacji sprzętu IPC, która jest wbudowana w nowoczesne POS dla systemu Windows.

#### <a name="printer"></a>Drukarka

| Producent | Model    | Interfejs | Komentarze                |
|--------------|----------|-----------|-------------------------|
| EPSON        | TM-T88IV | OPOS      |                         |
| EPSON        | TM-T88V  | OPOS      |                         |
| Gwiazda         | TSP650II | OPOS      |                         |
| Gwiazda         | TSP650II | Niestandardowy    | Połączenie przez sieć   |
| Gwiazda         | mPOP     | OPOS      | Połączone za pomocą technologii Bluetooth |
| HP           | F7M67AA  | OPOS      | Zasilany USB             |

#### <a name="bar-code-scanner"></a>Skaner kodów kreskowych

| Producent  | Model         | Interfejs | Komentarze |
|---------------|---------------|-----------|----------|
| Firma Motorola      | DS9208        | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Symbol        | LS2208        | OPOS      |          |
| HP zintegrowane | E1L07AA       | OPOS      |          |
| Datalogic     | Magellan 8400 | OPOS      |          |

#### <a name="pin-pad"></a>Konsola PIN

| Producent | Model  | Interfejs | Komentarze                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Wymaga dostosowania łącznika płatności |

#### <a name="payment-terminal"></a>Terminal płatniczy 

| Producent | Model | Interfejs | Komentarze                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Niestandardowy    | Wymaga dostosowania łącznika płatności                                |
| VeriFone     | MX925 | Niestandardowy    | Wymaga dostosowania łącznika płatności; podłączone do portu USB i sieci |
| VeriFone     | MX915 | Niestandardowy    | Wymaga dostosowania łącznika płatności; podłączone do portu USB i sieci |

#### <a name="cash-drawer"></a>Szuflada kasowa

| Producent | Model     | Interfejs | Komentarze                |
|--------------|-----------|-----------|-------------------------|
| Gwiazda         | mPOP      | OPOS      | Połączone za pomocą technologii Bluetooth |
| APG          | Atwood    | Niestandardowy    | Połączenie przez sieć   |
| Gwiazda         | SMD2-1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |

#### <a name="line-display"></a>Wyświetlacz wierszowy

| Producent  | Model   | Interfejs | Komentarze |
|---------------|---------|-----------|----------|
| HP zintegrowane | G6U79AA | OPOS      |          |
| EPSON         | M58DC   | OPOS      |          |

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

### <a name="dedicated-iis-hardware-station"></a>Dedykowany stacja sprzętowa usług IIS

Następujące urządzenia peryferyjne zostały przetestowane przy użyciu stacji dedykowanego sprzętu IIS (nie współdzielonym) wraz z nowoczesnymi punktu sprzedaży dla systemu Windows i POS chmury.

#### <a name="printer"></a>Drukarka

| Producent | Model    | Interfejs | Komentarze                  |
|--------------|----------|-----------|---------------------------|
| EPSON        | TM-T88IV | OPOS      |                           |
| EPSON        | TM-T88V  | OPOS      |                           |
| Gwiazda         | TSP650II | OPOS      |                           |
| Gwiazda         | TSP650II | Niestandardowy    | Połączenie przez sieć     |
| Gwiazda         | TSP100   | OPOS      | Wymaga sterowników TSP650II |
| HP           | F7M67AA  | OPOS      | Zasilany USB               |

#### <a name="bar-code-scanner"></a>Skaner kodów kreskowych

| Producent  | Model   | Interfejs | Komentarze |
|---------------|---------|-----------|----------|
| Firma Motorola      | DS9208  | OPOS      |          |
| Symbol        | LS2208  | OPOS      |          |
| HP zintegrowane | E1L07AA | OPOS      |          |

#### <a name="pin-pad"></a>Konsola PIN

| Producent | Model  | Interfejs | Komentarze                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Wymaga dostosowania łącznika płatności |

#### <a name="payment-terminal"></a>Terminal płatniczy 

| Producent | Model | Interfejs | Komentarze                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Niestandardowy    | Wymaga dostosowania łącznika płatności                                |
| VeriFone     | MX925 | Niestandardowy    | Wymaga dostosowania łącznika płatności; podłączone do portu USB i sieci |
| VeriFone     | MX915 | Niestandardowy    | Wymaga dostosowania łącznika płatności; podłączone do portu USB i sieci |

#### <a name="cash-drawer"></a>Szuflada kasowa

| Producent | Model     | Interfejs | Komentarze              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Niestandardowy    | Połączenie przez sieć |
| Gwiazda         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

#### <a name="line-display"></a>Wyświetlacz wierszowy

| Producent  | Model   | Interfejs | Komentarze |
|---------------|---------|-----------|----------|
| HP zintegrowane | G6U79AA | OPOS      |          |
| EPSON         | M58DC   | OPOS      |          |

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

### <a name="shared-iis-hardware-station"></a>Stacja sprzętowa udostępnionego usług IIS

Następujące urządzenia peryferyjne zostały przetestowane przy użyciu udostępnionych stacji sprzętu IIS wraz z nowoczesnymi punktu sprzedaży dla systemu Windows i POS chmury. **Uwaga:** obsługiwane są tylko drukarki, terminal płatności i szuflady kasowej.

#### <a name="printer"></a>Drukarka

| Producent | Model    | Interfejs | Komentarze                  |
|--------------|----------|-----------|---------------------------|
| EPSON        | TM-T88IV | OPOS      |                           |
| EPSON        | TM-T88V  | OPOS      |                           |
| Gwiazda         | TSP650II | OPOS      |                           |
| Gwiazda         | TSP650II | Niestandardowy    | Połączenie przez sieć     |
| Gwiazda         | TSP100   | OPOS      | Wymaga sterowników TSP650II |
| HP           | F7M67AA  | OPOS      | Zasilany USB               |

#### <a name="payment-terminal"></a>Terminal płatniczy 

| Producent | Model | Interfejs | Komentarze                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Niestandardowy    | Wymaga dostosowania łącznika płatności; podłączone do portu USB i sieci |
| VeriFone     | MX915 | Niestandardowy    | Wymaga dostosowania łącznika płatności; podłączone do portu USB i sieci |

#### <a name="cash-drawer"></a>Szuflada kasowa

| Producent | Model     | Interfejs | Komentarze              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Niestandardowy    | Połączenie przez sieć |
| Gwiazda         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

## <a name="troubleshooting"></a>Rozwiązywanie problemów
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>Nowoczesne POS może wykryć stacji sprzętu na liście wyboru, ale nie może ukończyć parowania

**Rozwiązanie:** Sprawdź poniższą listę potencjalnych punktów awarii:

-   Komputera, na którym jest uruchomiony nowoczesnych POS ufa certyfikat, który jest używany na komputerze, na którym jest uruchamiana na stacji sprzętu.
    -   Aby zweryfikować tego Instalatora w przeglądarce sieci web przejdź do następującego adresu URL: https://&lt;nazwa komputera&gt;:&lt;numer portu&gt;/HardwareStation/ping.
    -   Ten adres URL używa ping, aby sprawdzić, czy komputer jest możliwy i przeglądarki wskazuje, czy certyfikat jest zaufany. (Na przykład, w programie Internet Explorer, ikona kłódki pojawi się na pasku adresu. Po kliknięciu tej ikony programu Internet Explorer sprawdza, czy certyfikat jest obecnie zaufany. Można zainstalować certyfikat na komputerze lokalnym, wyświetlając szczegóły certyfikatu, który jest wyświetlany.)
-   Na komputerze, na którym jest uruchamiana na stacji sprzętu portu, który będzie używany przez stację sprzętu jest otwarte w zaporze.
-   Stacja sprzętowa została zainstalowana prawidłowo informacje o koncie handlowca za pomocą narzędzia handlowca informacje instalacji działającą na końcu Instalator stacji sprzętu.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>Nowoczesne POS nie może wykryć stacji sprzętu na liście wyboru

**Rozwiązanie:** jedną z następujących czynników może powodować ten problem:

-   Stacja sprzęt nie został poprawnie skonfigurowany w centrali. Wykonaj kroki wcześniej w tym temacie, aby sprawdzić, czy profil sprzętowy stacji i stacji sprzętu są poprawnie wprowadzone.
-   Zadania jeszcze nie została uruchomiona zaktualizować konfigurację kanału. W takim przypadku uruchomić zadanie 1070 przy konfigurowaniu kanału.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>Nowe ustawienia szuflady środków pieniężnych nie znajdują odzwierciedlenia w nowoczesnych POS

**Rozwiązanie:** zamknięcia bieżącej partii. Zmiany do szuflady kasowej nie są aktualizowane do nowoczesnych POS, aż do zamknięcia bieżącej partii.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>Nowoczesne POS jest zgłoszenie problemu z retail urządzenia peryferyjne

**Rozwiązanie:** poniżej przedstawiono niektóre typowe przyczyny tego problemu:

-   Upewnij się, że inne narzędzia konfiguracji sterownika urządzenia są zamknięte. Jeśli narzędzia te są otwarte, one może uniemożliwić nowoczesnych POS lub stacja sprzętowa twierdząc urządzenia.
-   Urządzenie peryferyjne detalicznych jest współużytkowany z wieloma urządzeniami punktu sprzedaży, upewnij się, że należy do jednej z poniższych kategorii:
    -   Szuflada kasowa
    -   Drukarki paragonów
    -   Terminal płatniczy 

    Jeśli urządzenie peryferyjne nie należą do jednej z tych kategorii, stacja sprzętu nie jest przeznaczony do Włącz urządzenie peryferyjne dzielony pomiędzy wieloma urządzeniami punktu sprzedaży.
-   Sterowniki urządzeń można czasami powodować wspólnych obiektów kontroli (CCOs) przestał działać poprawnie. Jeśli urządzenie zostało już zainstalowane, ale nie działa poprawnie lub zauważysz innych problemów, można często rozwiązać problem, instalując ponownie CCOs. Aby pobrać CCOs, odwiedź stronę <http://monroecs.com/oposccos_current.htm>.
-   Częste zmiany peryferyjnych wprowadzone podczas testowania lub rozwiązywania problemów, należy zresetować usługi IIS zamiast czekać na proces odświeżania pamięci podręcznej. Aby zresetować usługi IIS, wykonaj następujące kroki:
    1.  Od **Start** menu, typ **CMD**.
    2.  W wynikach wyszukiwania kliknij prawym przyciskiem myszy **wiersza polecenia**, a następnie kliknij przycisk **Uruchom jako administrator**.
    3.  W **wiersza polecenia** wpisz **iisreset/restart** i naciśnij klawisz Enter.
    4.  Po ponownym uruchomieniu usług IIS, należy ponownie uruchomić nowoczesnych POS.
-   Podczas dokonywania częstych zmian do urządzeń peryferyjnych, również często uruchomienie i Zamknij klienta programu Retail POS, proces dllhost od poprzedniej sesji POS mogą zakłócać bieżącej sesji. W takim przypadku nie może być można używać urządzenia, aż do zamknięcia hosta biblioteki dołączanej (dynamicznie DLL), który zarządza poprzedniej sesji. Aby zamknąć hosta biblioteki DLL, wykonaj następujące kroki:
    1.  Od **Start** menu, typ **Menedżera zadań**.
    2.  W wynikach wyszukiwania, kliknij przycisk **Menedżera zadań**.
    3.  W Menedżerze zadań na **szczegóły**, należy kliknąć nagłówek kolumny, która jest oznaczona etykietą **nazwa** do sortowania tabeli alfabetycznie według nazw.
    4.  Przewiń w dół do momentu znalezienia dllhost.exe.
    5.  Zaznacz każdy host biblioteki DLL, a następnie kliknij **Zakończ zadanie**.
    6.  Po zamknięciu hostów bibliotek DLL, należy ponownie uruchomić nowoczesnych POS.


<a name="see-also"></a>Informacje dodatkowe
--------

[Symulator obwodowych sieci sprzedaży](retail-peripheral-simulator.md)


