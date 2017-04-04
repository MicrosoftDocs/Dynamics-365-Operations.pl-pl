---
title: "Definiowania i utrzymywania klientów kanału, rejestrów i stacje"
description: "Ta strona wiki omawia sposób podłączania urządzeń peryferyjnych do komputera z wystąpieniem aplikacji Retail POS."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: dee5745670ad86000795f2913f99f49c0f123a00
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-maintain-channel-clients-registers-and-hardware-stations"></a>Definiowania i utrzymywania klientów kanału, rejestrów i stacje

Ta strona wiki omawia sposób podłączania urządzeń peryferyjnych do komputera z wystąpieniem aplikacji Retail POS.

**Uwaga:** Aby uzyskać szczegółowe instrukcje instalacji, zobacz artykuły [Konfiguracja i instalacja składnika Retail Hardware Station](retail-hardware-station-configuration-installation.md) i [Samodzielne pobieranie/instalacja składnika Retail Modern POS oraz aktywacja urządzeń typu Modern POS i Cloud POS](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Najważniejsze składniki
Kilka składników jest używanych do definiowania relacji między sklepem, kasami POS (punktów sprzedaży) lub kanałami w sklepie oraz urządzeniami peryferyjnymi wykorzystywanymi przez te kasy lub kanały do przetwarzania transakcji. Ta sekcja zawiera omówienie wszystkich składników i wyjaśnia, jak powinny być używane w danym wdrożeniu sklepu sieci sprzedaży.

### <a name="pos-registers"></a>Rejestry punktu sprzedaży

Nawigacja: Kliknij przycisk **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**rejestruje**. Rejestr punktu sprzedaży jest jednostka, która jest używana do definiowania właściwości konkretnego wystąpienia punktu sprzedaży. Cechy te obejmują profilu sprzętu lub instalacji urządzeń peryferyjnych sieci sprzedaży, które będą używane w rejestrze, magazynie rejestr jest mapowany do i wrażenia wizualne dla użytkownika, który loguje się do którego zarejestrować.

### <a name="devices"></a>Urządzenia

Nawigacja: Kliknij przycisk **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**urządzeń**. Urządzenie to jednostka, która reprezentuje fizyczne wystąpienie urządzenia zmapowanego do kasy POS. Po utworzeniu urządzenie jest mapowane do kasy POS. Jednostka urządzenia śledzi informacje o tym, kiedy kasa punktu sprzedaży jest aktywowana, jaki typ klienta jest używany i jaki pakiet aplikacji został wdrożony na konkretnym urządzeniu. Urządzenia mogą być dwóch typów: **Retail Modern POS** (MPOS) lub **Retail Cloud POS** (Cloud POS).

#### <a name="mpos"></a>MPOS

MPOS to aplikacja kliencka punktu sprzedaży instalowana na komputerze z systemem operacyjnym Windows 8.1 lub nowszym. Jeśli do urządzenia jest mapowana aplikacja typu **Retail Modern POS**, pakiet do pobrania można określić dla konkretnego urządzenia. Pakiet do pobrania można dostosować, aby zawierał różne wersje pakietu instalacyjnego. Możliwość wdrażania różnych pakietów zapewnia elastyczność w przypadkach, gdy różne kasy POS mogą wymagać różnych integracji. Aplikację MPOS wdraża się razem z wbudowanym oprogramowaniem stacji sprzętowej.

#### <a name="cloud-pos"></a>Cloud POS

Chmura POS jest POS opartego na przeglądarce. Ponieważ jest uruchamiana w przeglądarce POS chmura nie wymaga Windows 8.1 lub nowszy system operacyjny na komputer PC. Jeśli aplikacja **Retail Cloud POS** jest zmapowana do określonego urządzenia w systemach zaplecza, urządzenie to można obsługiwać za pośrednictwem przeglądarki, bez konieczności pobierania i instalowania pakietu. Aplikacja Cloud POS wymaga oprogramowania stacji sprzętowej, jeśli ma współpracować ze urządzeniami innymi niż ręczny skaner kodów kreskowych.

### <a name="hardware-profile"></a>Profil sprzętu

Nawigacja: Kliknij przycisk **handlu**&gt;**konfigurację kanału**&gt;**konfiguracji punktu sprzedaży**&gt;**profile POS**&gt;**profile sprzętu**. Profil sprzętu identyfikuje sprzęt, który jest podłączony do kasy POS lub stacji sprzętowej. Profil sprzętu służy również do określenia parametrów procesora płatności, które powinny być używane podczas komunikacji z zestawem SDK obsługi płatności. (Zestaw SDK obsługi płatności jest wdrażany jako część stacji sprzętowej).

### <a name="hardware-station"></a>Stacja sprzętowa

Nawigacja: Kliknij przycisk **sieci sprzedaży i handlu**&gt;**kanałów**&gt;**sklepów detalicznych**&gt;**wszystkich sklepów detalicznych**. Zaznacz sklep i kliknij skróconą kartę **Stacje sprzętowe**. Stacja sprzętowa to wystąpienie logiki biznesowej sterującej działaniem urządzeń peryferyjnych w punkcie sprzedaży. Stacja sprzętowa jest instalowana automatycznie razem z aplikacją MPOS. Alternatywnie stację sprzętową można zainstalować jako autonomiczny składnik, a następnie otwierać z aplikacji MPOS lub Cloud POS za pośrednictwem usługi internetowej. Stacja sprzętowa musi być zdefiniowana na poziomie kanału.

### <a name="hardware-station-profile"></a>Profil stacji sprzętowej

Nawigacja: Kliknij przycisk **Commerce**&gt;**konfigurację kanału**&gt;**konfiguracji punktu sprzedaży**&gt;**profile POS**&gt;**profile sprzętowe stacji**. Sama stacja sprzętowa jest określana na poziomie kanału przy użyciu informacji specyficznych dla wystąpienia, takich jak adres URL stacji, natomiast profil stacji sprzętowej zawiera informacje, które mogą być statyczne lub udostępniane między wieloma stacjami sprzętowymi. Informacje statyczne obejmują port, który ma być używany, dane pakietu stacji sprzętowej oraz profilu sprzętu. Do informacji statycznych należy również opis typu wdrażanej stacji sprzętowej, np. **Finalizacja zakupu ** lub **Zwroty**, w zależności od sprzętu wymaganego dla każdej konkretnej stacji sprzętowej.

## <a name="scenarios"></a>Scenariusze
### <a name="mpos-with-connected-peripheral-devices"></a>Punkt MPOS z podłączonymi urządzeniami peryferyjnymi

[![Tradycyjny, stały punkt sprzedaży](./media/traditional-300x279.png)](./media/traditional.png) Aby połączyć MPOS POS urządzenia peryferyjne w scenariuszu POS stałych, tradycyjne, najpierw przejść do autorejestracji i przypisywanie profilu sprzętu do niego. Można znaleźć Rejestry punktu sprzedaży o **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**rejestruje**. Po przypisaniu profilu sprzętu zsynchronizuj zmiany z bazą danych kanału, używając do tego harmonogramu dystrybucji „Rejestry”. Można znaleźć harmonogramy dystrybucji o **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramu dystrybucji**. Następny skonfiguruj „lokalną” stację sprzętową w kanale. Kliknij **sieci sprzedaży i handlu**&gt;**kanałów**&gt;**sklepów detalicznych**&gt;**wszystkich sklepów detalicznych**i wybierz sklep. Następnie na skróconej karcie **Stacje sprzętowe** kliknij przycisk **Dodaj**, aby dodać stację sprzętową. Wprowadź opis, jako nazwę hosta wpisz **localhost**, a następnie zsynchronizuj zmiany z kanałem przy użyciu harmonogramu dystrybucji „Konfiguracja kanału”. Można znaleźć harmonogramy dystrybucji o **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramu dystrybucji**. Na koniec w aplikacji MPOS za pomocą operacji **Wybierz stację sprzętową** zaznacz stację sprzętową **localhost**. Ustaw dla tej stacji sprzętowej status **Aktywna**. Profil sprzętu używany w tym scenariuszu powinien pochodzić z samej kasy w punkcie sprzedaży. Profil stacji sprzętowej nie jest wymagany w tym scenariuszu. **Uwaga:** Niektóre zmiany w profilu sprzęt, takie jak modyfikacje szuflad kasowych, wymagają, aby po zsynchronizowaniu zmian z kanałem otworzyć nową zmianę. **Uwaga:** Aplikacja Cloud POS musi używać autonomicznej stacji sprzętowej do komunikowania się z urządzeniami peryferyjnymi sieci sprzedaży.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>Urządzenie MPOS lub Cloud POS z autonomiczną stacją sprzętową

\[Identyfikator etykiety = "załącznik\_340041" Wyrównaj = "alignleft" width = "300"\][![urządzenia peryferyjne wspólne dla](./media/shared-300x254.png)](./media/shared.png) urządzenia peryferyjne wspólne dla\[/caption\] w tym scenariuszu stacji autonomicznych sprzętu jest współużytkowane przez klientów MPOS i POS chmury. Ten scenariusz wymaga utworzenia profilu stacji sprzętowej, aby określić pakiet do pobrania, port oraz profil sprzętu, który będzie używany przez stację. Można znaleźć profilu sprzętowego stacji w **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**konfiguracji punktu sprzedaży**&gt;**profile POS**&gt;**profile sprzętowe stacji**. Po utworzeniu profilu sprzętowego stacji, przejdź do określonego kanału sprzedaży (**sieci sprzedaży i handlu**&gt;**kanałów**&gt;**sklepów detalicznych**&gt;**wszystkich sklepów detalicznych**) i Dodaj nową stację sprzętu. Zmapuj tę nową stację sprzętową do utworzonego wcześniej profilu stacji sprzętowej. Następnie podaj opis, który pomoże kasjerowi zidentyfikować stację sprzętową. W **nazwa hosta** wprowadź adres URL komputera hosta w następującym formacie: **https://&lt;MachineName:Port&gt;/HardwareStation**. (Zastąp **&lt;MachineName:Port&gt;** z obecnej nazwy komputera stacja sprzętowa i port, który jest określony w profilu sprzętowym stacji.) Dla stacji autonomicznych sprzętu należy również określić że transferu środków elektronicznych (EFT) identyfikator terminalu. Ta wartość identyfikuje terminal EFT, który jest podłączony do stacji sprzętowej, gdy aplikacja łącznika płatności komunikuje się z dostawcą płatności. Następnie z faktycznego komputera stacji sprzętowej przejdź do kanału i wybierz stację sprzętową. Kliknij przycisk **Pobierz** i zainstaluj stację sprzętową. Następnie w aplikacji MPOS lub Cloud POS wykonaj operację **Wybierz stację sprzętową** i wybierz zainstalowaną wcześniej stację sprzętową. Zaznacz opcję **Paruj**, aby utworzyć bezpieczną relację między kasą POS a stacją sprzętową. Ten krok należy wykonać jeden raz dla każdej kombinacji kasy POS i stacji sprzętowej. Po sparowaniu stacji sprzętowej ta sama operacja służy do uaktywnienia stacji sprzętowej podczas jej używania. W tym scenariuszu dla profilu sprzętu powinny być przypisane do profilu sprzętowego stacji zamiast autorejestracji. Jeśli z jakiegoś powodu stacji sprzętu nie ma profilu sprzętu bezpośrednio przypisane, przypisany do rejestru profil sprzętu jest używany

## <a name="client-maintenance"></a>Zarządzanie klientami
### <a name="registers"></a>Rejestry

Zarządzanie kasami POS odbywa się głównie w samych kasach, a także poprzez profile przypisane do kas. Zarządzanie atrybutami specyficznymi dla poszczególnych kas odbywa się na poziomie kas. Wśród tych atrybutów są: sklep, gdzie jest używana kasa; numer kasy; opis; identyfikator terminala EFT specyficznego dla kasy.

### <a name="pos-profiles"></a>Profile punktów sprzedaży

Można znaleźć profili POS przy **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**konfiguracji punktu sprzedaży**&gt;**profile POS**. Warto zarządzać wieloma aspektami kas poprzez profile, ponieważ profile mogą być współużytkowane przez wiele kas. Profile mogą być mapowane do poszczególnych kas lub do całego sklepu sieci sprzedaży, jeśli dany profil jest ogólnosklepowy. Następujące sekcje opisują profile kas POS i sposób ich użycia.

#### <a name="offline-profile"></a>Profil trybu offline

Profil trybu offline jest ustawiany na poziomie sklepu. Służy do określania ustawień przekazywania transakcji, które są wykonywane w kasie POS, gdy kasa nie ma połączenia z bazą danych kanału.

#### <a name="functionality-profile"></a>Profil funkcji

Profil funkcji jest ustawiany na poziomie sklepu. Służy do określania ustawień na poziomie magazynu o funkcje, które mogą być wykonywane w punkcie sprzedaży. Następujące funkcje są zarządzane za pomocą profilu funkcji. Funkcje są rozmieszczane na skróconych kartach.

-   Skrócona karta **Ogólne**:
    -   Międzynarodowa Organizacja Normalizacyjna (ISO).
    -   Tworzenie odbiorcy w trybie offline.
    -   Profil wysyłania paragonów pocztą elektroniczną.
    -   Centralne uwierzytelnianie logowania personelu.
-   Skrócona karta **Funkcje**:
    -   Zarządzanie logowaniem zwykłym i rozszerzonym.
    -   Aspekty punktu sprzedaży dotyczące finansów i walut, takie jak możliwość wpisywania cen oraz określania, czy dla waluty dodatkowej są wymagane miejsca dziesiętne.
    -   Włączanie rejestracji czasu za pośrednictwem kasy.
    -   Sposób wyświetlania produktów i płatności na kasie POS i paragonach.
    -   Zarządzanie zakończeniem dnia.
    -   Parametry przechowywania transakcji w bazie danych kanału.
    -   Sposób wyszukiwana i tworzenia klientów w punkcie sprzedaży.
    -   Sposób obliczania rabatów.
-   Skrócona karta **Kwota**:
    -   Dozwolone ceny maksymalne i minimalne.
    -   Stosowanie i obliczanie rabatów.
-   Skrócona karta **Kody informacji**:
    -   Wszystkie aspekty jak kody informacji są zarządzane w punkcie sprzedaży. Aby uzyskać szczegółowe informacje, zobacz [kodów informacji](info-codes-retail.md).
-   Skrócona karta **Numeracja paragonów**:
    -   Określ maski numerowania paragonów, które mogą zawierać segmenty na numer sklepu, numer terminala i stałe oraz określać, czy sprzedaż, zwroty, zamówienia sprzedaży i oferty mają być drukowane według osobnych numeracji czy też jednej zbiorczej numeracji.

#### <a name="receipt-profiles"></a>Profile paragonów

Profile paragonów są przypisywane do drukarek w profilach sprzętu. Służą do określania typów paragonów drukowanych na określonej drukarce. Profile zawierają ustawienia formatów paragonów oraz ustawienia określające, czy paragony są drukowane zawsze czy też kasjer jest monitowany o podjęcie decyzji o drukowaniu. Różne drukarki mogą wykorzystywać różne profile paragonów. Na przykład drukarka 1 jest standardową termiczną drukarką paragonów i w związku z tym ma mniejsze formaty paragonów. Jednak drukarka 2 jest pełnowymiarową drukarką paragonów, która służy do drukowania tylko paragonów dla zamówień odbiorców, które wymagają więcej miejsca.

#### <a name="hardware-profiles"></a>Profile sprzętu

Profile sprzętu omówiono jako składnik konfiguracji klienta we wcześniejszej części tego artykułu. Profile sprzętu są przypisywane bezpośrednio do kasy w punkcie sprzedaży lub do profilu stacji sprzętowej. Służą one do określenia typów urządzeń wykorzystywanych przez konkretną kasę POS lub stację sprzętową. Profile sprzętu są również używane do określania ustawień usługi EFT służących do komunikacji z zestawem SDK obsługi płatności.

#### <a name="visual-profiles"></a>Profile graficzne

Profile graficzne przypisuje się na poziomie kasy. Są one używane do określania motywu dla określonej kasy. Profile zawierają ustawienia dotyczące typu używanej aplikacji (MPOS lub Cloud POS), koloru i motywu przewodniego, schemat czcionek, tła okna logowania i tła okien kasy.

### <a name="custom-fields"></a>Pola niestandardowe

Można tworzyć pola niestandardowe, aby dodać pola, które nie są dostarczane gotową do punktu sprzedaży. Aby uzyskać więcej informacji na temat używania pól niestandardowych, zobacz [pracę z pól niestandardowych w blogu](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Tekst w języku

Domyślne ciągi tekstowe interfejsu kasy POS można zastąpić za pomocą wpisów tekstu w innym języku. Aby zastąpić ciąg tekstowy w interfejsie kasy, należy dodać wiersz tekstu w innym języku. Następnie określ identyfikator, domyślny ciąg tekstowy przeznaczony do zastąpienia oraz tekst, który ma być wyświetlany w oknach kasy zamiast domyślnego ciągu.

### <a name="hardware-station-profiles"></a>Profile stacji sprzętowych

Profile stacji sprzętowych omówiono wcześniej w tym artykule. Służą one do przypisywania stacjom sprzętowym informacji niespecyficznych dla wystąpień.

### <a name="channel-reports-configuration"></a>Konfiguracja raportów kanału

W celu skonfigurowania raportów, które mają być dostępne w kanale sprzedaży detalicznej, należy przejść do strony **Konfiguracja raportów kanału detalicznego**. Można tworzyć nowe raporty poprzez dostarczenie definicji XML raportu i przypisanie raportu do określonej grupy uprawnień w punkcie sprzedaży.

### <a name="devices"></a>Urządzenia

Urządzenia zostały omówione wcześniej w tym artykule. Są one używane do zarządzania aktywacjami konkretnych kas POS. Urządzenia służą również do określania aplikacji używanej w konkretnej kasie oraz pakietu instalacyjnego, którego należy użyć w celu zainstalowania klienta MPOS. Oto możliwe stany aktywacji urządzeń:

-   **Oczekujące** — urządzenie jest gotowe do aktywacji.
-   **Aktywowane** — urządzenie zostało uaktywnione.
-   **Zdezaktywowane** — urządzenie zostało zdezaktywowane w systemach zaplecza lub w kasie POS.
-   **Wyłączone** — urządzenie zostało wyłączone.

Dodatkowe informacje związane z aktywacją obejmują dane pracownika, który zmienił stan aktywacji urządzenia, sygnaturę czasową aktywacji oraz oznaczenie, czy konfiguracja urządzenia została zweryfikowana.

### <a name="client-data-synchronization"></a>Synchronizacja danych klienta

Wszystkie zmiany na kliencie punktu sprzedaży, z wyjątkiem zmian stanu aktywacji urządzenia, działają dopiero po zsynchronizowaniu z bazą danych kanału. Aby zsynchronizować zmiany w bazie danych kanałów, przejdź do **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramu dystrybucji**, i uruchomić Harmonogram dystrybucji wymagane. W przypadku zmian na kliencie należy uruchomić harmonogramy dystrybucji „Rejestry” i „Konfiguracja kanału”.


