---
title: Podłączanie urządzeń peryferyjnych do komputera z aplikacją POS
description: Ten temat omawia sposób podłączania urządzeń peryferyjnych do komputera z wystąpieniem aplikacji Retail POS.
author: BrianShook
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice
audience: Application User
ms.reviewer: josaw
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 66912443c25adfae6fa11e6a25c4a97f63a438ba
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779525"
---
# <a name="connect-peripherals-to-the-point-of-sale-pos"></a>Podłączanie urządzeń peryferyjnych do komputera z aplikacją POS

[!include [banner](includes/banner.md)]

Ten temat omawia sposób podłączania urządzeń peryferyjnych do komputera z wystąpieniem aplikacji Retail POS.

> [!NOTE]
> Aby uzyskać szczegółowe instrukcje dotyczące instalacji, należy zapoznać się z tematem [konfigurowanie i instalowanie modułu Retail Hardware Station](retail-hardware-station-configuration-installation.md) i [Konfigurowanie, instalowanie i aktywacja Modern POS (MPOS)](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Najważniejsze składniki

Kilka składników jest używanych do definiowania relacji między sklepem, kasami POS (punktów sprzedaży) lub kanałami w sklepie oraz urządzeniami peryferyjnymi wykorzystywanymi przez te kasy lub kanały do przetwarzania transakcji. Ta sekcja zawiera omówienie wszystkich składników i wyjaśnia, jak powinny być używane w danym wdrożeniu sklepu.

### <a name="pos-registers"></a>Rejestry punktu sprzedaży

Nawigacja: Kliknij kolejno opcje **Retail i Commerce** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Rejestry**.

Kasa w punkcie sprzedaży (POS) to jednostka używana do definiowania właściwości konkretnego wystąpienia punktu sprzedaży. Cechy te obejmują profil sprzętu lub konfigurację urządzeń peryferyjnych, które będą używane w kasie, sklep, do którego kasa jest mapowana, oraz wizualne środowisko użytkownika logującego się w tej kasie.

### <a name="devices"></a>Urządzenia

Nawigacja: Kliknij kolejno opcje **Retail i Commerce** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Urządzenia**.

Urządzenie to jednostka, która reprezentuje fizyczne wystąpienie urządzenia zmapowanego do kasy POS. Po utworzeniu urządzenie jest mapowane do kasy POS. Jednostka urządzenia śledzi informacje o tym, kiedy kasa punktu sprzedaży jest aktywowana, jaki typ klienta jest używany i jaki pakiet aplikacji został wdrożony na konkretnym urządzeniu. Urządzenia mogą być dwóch typów: **Retail modern POS** (MPOS) lub **Retail Cloud POS** (Cloud POS).

#### <a name="mpos"></a>MPOS

MPOS to aplikacja kliencka punktu sprzedaży instalowana na komputerze z systemem operacyjnym Windows 8.1 lub nowszym. Jeśli do urządzenia jest mapowana aplikacja typu **Retail modern POS**, pakiet do pobrania można określić dla konkretnego urządzenia. Pakiet do pobrania można dostosować, aby zawierał różne wersje pakietu instalacyjnego. Możliwość wdrażania różnych pakietów zapewnia elastyczność w przypadkach, gdy różne kasy POS mogą wymagać różnych integracji. Aplikację MPOS wdraża się razem z wbudowanym oprogramowaniem stacji sprzętowej.

#### <a name="cloud-pos"></a>Cloud POS

Cloud POS jest modułem punktu sprzedaży opartym na przeglądarce internetowej. Ponieważ aplikacja jest uruchamiana w przeglądarce, nie wymaga komputera z systemem operacyjnym Windows 8.1 lub nowszym. Jeśli aplikacja **Retail Cloud POS** jest zmapowana do określonego urządzenia w Headquarters, urządzenie to można obsługiwać za pośrednictwem przeglądarki, bez konieczności pobierania i instalowania pakietu. Aplikacja Cloud POS wymaga oprogramowania stacji sprzętowej, jeśli ma współpracować ze urządzeniami innymi niż ręczny skaner kodów kreskowych.

### <a name="hardware-profile"></a>Profil sprzętu

Nawigacja: Kliknij kolejno opcje **Handel detaliczny i inny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile sprzętu**.

Profil sprzętu identyfikuje sprzęt, który jest podłączony do kasy POS lub stacji sprzętowej. Profil sprzętu służy również do określenia parametrów procesora płatności, które powinny być używane podczas komunikacji z zestawem SDK obsługi płatności. (Zestaw SDK obsługi płatności jest wdrażany jako część stacji sprzętowej).

### <a name="hardware-station"></a>Hardware Station

Nawigacja: Kliknij kolejno opcje **Retail i Commerce** &gt; **Kanały** &gt; **Sklepy** &gt; **Wszystkie sklepy**. Zaznacz sklep i kliknij skróconą kartę **Stacje sprzętowe**.

Stacja sprzętowa to wystąpienie logiki biznesowej sterującej działaniem urządzeń peryferyjnych w punkcie sprzedaży. Stacja sprzętowa jest instalowana automatycznie razem z aplikacją MPOS. Alternatywnie stację sprzętową można zainstalować jako autonomiczny składnik, a następnie otwierać z aplikacji MPOS lub Cloud POS za pośrednictwem usługi internetowej. Stacja sprzętowa musi być zdefiniowana na poziomie kanału.

### <a name="hardware-station-profile"></a>Profil stacji sprzętowej

Nawigacja: Kliknij kolejno opcje **Handel detaliczny i inny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile stacji sprzętowych**.

Sama stacja sprzętowa jest określana na poziomie kanału przy użyciu informacji specyficznych dla wystąpienia, takich jak adres URL stacji, natomiast profil stacji sprzętowej zawiera informacje, które mogą być statyczne lub udostępniane między wieloma stacjami sprzętowymi. Informacje statyczne obejmują port, który ma być używany, dane pakietu stacji sprzętowej oraz profilu sprzętu. Do informacji statycznych należy również opis typu wdrażanej stacji sprzętowej, np. **Finalizacja zakupu** lub **Zwroty**, w zależności od sprzętu wymaganego dla każdej konkretnej stacji sprzętowej.

## <a name="scenarios"></a>Scenariusze

### <a name="mpos-with-connected-peripheral-devices"></a>Punkt MPOS z podłączonymi urządzeniami peryferyjnymi

[![Tradycyjny, stacjonarny punkt sprzedaży.](./media/traditional-300x279.png)](./media/traditional.png)

Aby podłączyć punkt MPOS do urządzeń peryferyjnych punktu sprzedaży w tradycyjnym scenariuszu stacjonarnego punktu sprzedaży, najpierw przejdź do samej kasy POS i przypisz jej profil sprzętu. Kasy POS są wyszczególnione w oknie **Retail i Commerce** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Rejestry**. 

Po przypisaniu profilu sprzętu zsynchronizuj zmiany z bazą danych kanału, używając do tego harmonogramu dystrybucji **Rejestry**. Harmonogramy dystrybucji są wyszczególnione w oknie **Retail and Commerce** &gt; **Składniki IT w Retail i Commerce** &gt; **Harmonogram dystrybucji**. 

Następny skonfiguruj „lokalną” stację sprzętową w kanale. Kliknij kolejno opcje **Retail i Commerce** &gt; **Kanały** &gt; **Sklepy** &gt; **Wszystkie sklepy** i wybierz sklep. 

Następnie na skróconej karcie **Stacje sprzętowe** kliknij przycisk **Dodaj**, aby dodać stację sprzętową. Wprowadź opis, jako nazwę hosta wpisz **localhost**, a następnie zsynchronizuj zmiany z kanałem przy użyciu harmonogramu dystrybucji **Konfiguracja kanału**. Harmonogramy dystrybucji są wyszczególnione w oknie **Retail and Commerce** &gt; **Składniki IT w Retail i Commerce** &gt; **Harmonogram dystrybucji**. 

Na koniec w aplikacji MPOS za pomocą operacji **Wybierz stację sprzętową** zaznacz stację sprzętową **localhost**. Ustaw dla tej stacji sprzętowej status **Aktywna**. Profil sprzętu używany w tym scenariuszu powinien pochodzić z samej kasy w punkcie sprzedaży. Profil stacji sprzętowej nie jest wymagany w tym scenariuszu.

> [!NOTE]
> Niektóre zmiany w profilu sprzęt, takie jak modyfikacje szuflad kasowych, wymagają, aby po zsynchronizowaniu zmian z kanałem otworzyć nową zmianę.
>
> Aplikacja Cloud POS musi używać autonomicznej stacji sprzętowej do komunikowania się z urządzeniami peryferyjnymi.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>Urządzenie MPOS lub Cloud POS z autonomiczną stacją sprzętową

[![Współużytkowane urządzenia peryferyjne.](./media/shared-300x254.png)](./media/shared.png)

W tym scenariuszu autonomiczna stacja sprzętowa jest współużytkowana przez klientów MPOS i Cloud POS. Ten scenariusz wymaga utworzenia profilu stacji sprzętowej, aby określić pakiet do pobrania, port oraz profil sprzętu, który będzie używany przez stację. Profil stacji sprzętowej można znaleźć w oknie **Retail and Commerce** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile stacji sprzętowych**. 

Po utworzeniu profilu stacji sprzętowej przejdź do konkretnego kanału sprzedaży (**Retail i Commerce** &gt; **Kanały** &gt; **Sklepy** &gt; **Wszystkie sklepy**) i dodaj nową stację sprzętową. Zmapuj tę nową stację sprzętową do utworzonego wcześniej profilu stacji sprzętowej. 

Następnie podaj opis, który pomoże kasjerowi zidentyfikować stację sprzętową. W polu **Nazwa hosta** wprowadź adres URL komputera hosta w następującym formacie: `https://<MachineName:Port>/HardwareStation` (wyrażenie **&lt;NazwaKomputera:Port&gt;** zastąp faktyczną nazwą komputera stacji sprzętowej oraz numerem portu określonym w profilu stacji sprzętowej). W przypadku autonomicznej stacji sprzętowej należy również określić identyfikator terminala systemu elektronicznego przelewu środków pieniężnych (EFT). Ta wartość identyfikuje terminal EFT, który jest podłączony do stacji sprzętowej, gdy aplikacja łącznika płatności komunikuje się z dostawcą płatności. 

Następnie z faktycznego komputera stacji sprzętowej przejdź do kanału i wybierz stację sprzętową. Kliknij przycisk **Pobierz** i zainstaluj stację sprzętową. 

Następnie w aplikacji MPOS lub Cloud POS wykonaj operację **Wybierz stację sprzętową** i wybierz zainstalowaną wcześniej stację sprzętową. Zaznacz opcję **Paruj**, aby utworzyć bezpieczną relację między kasą POS a stacją sprzętową. Ten krok należy wykonać jeden raz dla każdej kombinacji kasy POS i stacji sprzętowej. 

Po sparowaniu stacji sprzętowej ta sama operacja służy do uaktywnienia stacji sprzętowej podczas jej używania. W tym scenariuszu profil sprzętu powinien być przypisany do profilu stacji sprzętowej, a nie do samej kasy. Jeśli z jakiegoś powodu stacja sprzętowa nie ma bezpośrednio przypisanego profilu sprzętu, jest używany profil sprzętu przypisany do kasy.

## <a name="client-maintenance"></a>Zarządzanie klientami

### <a name="registers"></a>Rejestry

Zarządzanie kasami POS odbywa się głównie w samych kasach, a także poprzez profile przypisane do kas. Zarządzanie atrybutami specyficznymi dla poszczególnych kas odbywa się na poziomie kas. Wśród tych atrybutów są: sklep, gdzie jest używana kasa; numer kasy; opis; identyfikator terminala EFT specyficznego dla kasy.

### <a name="pos-profiles"></a>Profile punktów sprzedaży

Profile kas POS są wyszczególnione w oknie **Retail and Commerce** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży**. Warto zarządzać wieloma aspektami kas poprzez profile, ponieważ profile mogą być współużytkowane przez wiele kas. Profile mogą być mapowane do poszczególnych kas lub do całego sklepu, jeśli dany profil jest ogólnosklepowy. Następujące sekcje opisują profile kas POS i sposób ich użycia.

#### <a name="offline-profile"></a>Profil trybu offline

Profil trybu offline jest ustawiany na poziomie sklepu. Służy do określania ustawień przekazywania transakcji, które są wykonywane w kasie POS, gdy kasa nie ma połączenia z bazą danych kanału.

#### <a name="functionality-profile"></a>Profil funkcji

Profil funkcji jest ustawiany na poziomie sklepu. Służy do określania ogólnosklepowych ustawień funkcji, które można wykonywać w punkcie sprzedaży. Za pomocą profilu funkcji odbywa się zarządzanie funkcjami wymienionymi poniżej. Funkcje są rozmieszczane na skróconych kartach.

- Skrócona karta **Ogólne**:

    - Międzynarodowa Organizacja Normalizacyjna (ISO).
    - Tworzenie odbiorcy w trybie offline.
    - Profil wysyłania paragonów pocztą elektroniczną.
    - Centralne uwierzytelnianie logowania personelu.

- Skrócona karta **Funkcje**:

    - Zarządzanie logowaniem zwykłym i rozszerzonym.
    - Aspekty punktu sprzedaży dotyczące finansów i walut, takie jak możliwość wpisywania cen oraz określania, czy dla waluty dodatkowej są wymagane miejsca dziesiętne.
    - Włączanie rejestracji czasu za pośrednictwem kasy.
    - Sposób wyświetlania produktów i płatności na kasie POS i paragonach.
    - Zarządzanie zakończeniem dnia.
    - Parametry przechowywania transakcji w bazie danych kanału.
    - Sposób wyszukiwana i tworzenia klientów w punkcie sprzedaży.
    - Sposób obliczania rabatów.

- Skrócona karta **Kwota**:

    - Dozwolone ceny maksymalne i minimalne.
    - Stosowanie i obliczanie rabatów.

- Skrócona karta **Kody informacji**:

    - Zarządzanie wszystkimi aspektami kodów informacji odbywa się na kasie w punkcie sprzedaży. Aby dowiedzieć się więcej, zobacz [Kody informacji i grupy kodów informacji](info-codes-retail.md).

- Skrócona karta **Numeracja paragonów**:

    - Określ maski numerowania paragonów, które mogą zawierać segmenty na numer sklepu, numer terminala i stałe oraz określać, czy sprzedaż, zwroty, zamówienia sprzedaży i oferty mają być drukowane według osobnych numeracji czy też jednej zbiorczej numeracji.

#### <a name="receipt-profiles"></a>Profile paragonów

Profile paragonów są przypisywane do drukarek w profilach sprzętu. Służą do określania typów paragonów drukowanych na określonej drukarce. Profile zawierają ustawienia formatów paragonów oraz ustawienia określające, czy paragony są drukowane zawsze czy też kasjer jest monitowany o podjęcie decyzji o drukowaniu. Różne drukarki mogą wykorzystywać różne profile paragonów. Na przykład drukarka 1 jest standardową termiczną drukarką paragonów i w związku z tym ma mniejsze formaty paragonów. Jednak drukarka 2 jest pełnowymiarową drukarką paragonów, która służy do drukowania tylko paragonów dla zamówień odbiorców, które wymagają więcej miejsca.

#### <a name="hardware-profiles"></a>Profile sprzętu

Profile sprzętu omówiono jako składnik konfiguracji klienta we wcześniejszej części tego artykułu. Profile sprzętu są przypisywane bezpośrednio do kasy w punkcie sprzedaży lub do profilu stacji sprzętowej. Służą one do określenia typów urządzeń wykorzystywanych przez konkretną kasę POS lub stację sprzętową. Profile sprzętu są również używane do określania ustawień usługi EFT służących do komunikacji z zestawem SDK obsługi płatności.

#### <a name="visual-profiles"></a>Profile graficzne

Profile graficzne przypisuje się na poziomie kasy. Są one używane do określania motywu dla określonej kasy. Profile zawierają ustawienia dotyczące typu używanej aplikacji (MPOS lub Cloud POS), koloru i motywu przewodniego, schemat czcionek, tła okna logowania i tła okien kasy.

### <a name="custom-fields"></a>Pola niestandardowe

Można tworzyć pola niestandardowe, tzn. takie, których nie ma w gotowych aplikacjach punktu sprzedaży. Aby uzyskać więcej informacji na temat używania pól niestandardowych, zobacz wpis na blogu [Praca z niestandardowymi polami](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Tekst w języku

Domyślne ciągi tekstowe interfejsu kasy POS można zastąpić za pomocą wpisów tekstu w innym języku. Aby zastąpić ciąg tekstowy w interfejsie kasy, należy dodać wiersz tekstu w innym języku. Następnie określ identyfikator, domyślny ciąg tekstowy przeznaczony do zastąpienia oraz tekst, który ma być wyświetlany w oknach kasy zamiast domyślnego ciągu.

### <a name="hardware-station-profiles"></a>Profile stacji sprzętowych

Profile stacji sprzętowych omówiono wcześniej w tym artykule. Służą one do przypisywania stacjom sprzętowym informacji niespecyficznych dla wystąpień.

### <a name="channel-reports-configuration"></a>Konfiguracja raportów kanału

W celu skonfigurowania raportów, które mają być dostępne w kanale, należy przejść do strony **Konfiguracja raportów kanału**. Można tworzyć nowe raporty poprzez dostarczenie definicji XML raportu i przypisanie raportu do określonej grupy uprawnień w punkcie sprzedaży.

### <a name="devices"></a>Urządzenia

Urządzenia zostały omówione wcześniej w tym artykule. Są one używane do zarządzania aktywacjami konkretnych kas POS. Urządzenia służą również do określania aplikacji używanej w konkretnej kasie oraz pakietu instalacyjnego, którego należy użyć w celu zainstalowania klienta MPOS. Oto możliwe stany aktywacji urządzeń:

- **Oczekujące** — urządzenie jest gotowe do aktywacji.
- **Aktywowane** — urządzenie zostało uaktywnione.
- **Zdezaktywowane** — urządzenie zostało zdezaktywowane w Headquarters lub w kasie POS.
- **Wyłączone** — urządzenie zostało wyłączone.

Dodatkowe informacje związane z aktywacją obejmują dane pracownika, który zmienił stan aktywacji urządzenia, sygnaturę czasową aktywacji oraz oznaczenie, czy konfiguracja urządzenia została zweryfikowana.

### <a name="client-data-synchronization"></a>Synchronizacja danych klienta

Wszystkie zmiany na kliencie punktu sprzedaży, z wyjątkiem zmian stanu aktywacji urządzenia, działają dopiero po zsynchronizowaniu z bazą danych kanału. Aby zsynchronizować zmiany z bazą danych kanału, wybierz kolejno opcje **Retail i Commerce** &gt; **Składniki IT w handlu detalicznym i innym** &gt; **Harmonogram dystrybucji** i uruchom wymagany harmonogram dystrybucji. W przypadku zmian na kliencie należy uruchomić harmonogramy dystrybucji **Rejestry** i **Konfiguracja kanału**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]