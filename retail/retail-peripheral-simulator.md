---
title: "Symulator obwodowych sieci sprzedaży"
description: "W tym temacie opisano narzędzie symulator obwodowych, dołączony do usługi Microsoft Dynamics 365 dla operacji - sieci sprzedaży."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 42dc414ff2bb6359b47d89c3bd3c510e4258f816
ms.openlocfilehash: b2229466040351d8c2b9494b30b4c928651820b8
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripheral-simulator"></a>Symulator obwodowych sieci sprzedaży

W tym temacie opisano narzędzie symulator obwodowych, dołączony do usługi Microsoft Dynamics 365 dla operacji - sieci sprzedaży.

<a name="overview"></a>Przegląd
--------

Usługi Microsoft Dynamics 365 dla operacji - symulator obwodowych detalicznych jest narzędziem, które pomaga skonfigurować, testowanie i rozwiązywanie problemów z urządzeniami, które są używane w środowiskach sieci sprzedaży. Można użyć obwodowych symulatora, usprawnić testowania urządzeń peryferyjnych detalicznych i izolowanie problemów, które są spowodowane przez niepoprawne ustawienia lub nieprawidłowe działanie sterowników urządzeń. Urządzenia peryferyjne symulator zawiera pulpitu programu, który oferuje wirtualne wersje urządzeń tego 365 Dynamics dla operacji - obsługuje sieci sprzedaży. Sekcja dla każdego urządzenia wirtualnego przedstawiono interakcji między urządzeniem a punktem sprzedaży detalicznej sprzedaży (POS). Można także użyć do zapewnienia wkładu, który jest prawidłowy dla różnych scenariuszy POS. Symulator peryferyjne obsługuje interakcji między punktu sprzedaży oraz następujące urządzenia wirtualnego:

-   **Drukarka** – symulator urządzenia peryferyjne można pokazać przyjęć, które są skonfigurowane dla drukarki POS.
-   **Liniowy wyświetlacz** — można skonfigurować wyświetlanie wirtualnego wiersza do pokazania działania na wyświetlaczu fizycznej linii.
-   **Czytnik kart magnetycznych (MSR)** — zdarzenia symulowanego magnetycznych można wysyłać do punktu sprzedaży z symulatora obwodowych.
-   **Szuflada na** — można symulować szuflady kasowej fizycznego.
-   **Szuflada na 2** -przez utworzenie drugiej szuflady kasowej w symulatorze obwodowych, można symulować scenariuszy, które wymagają jednego rejestru punktu sprzedaży, która ma dwie zmiany aktywnego.
-   **Skaner** — skaner wirtualnego kodu kreskowego, który obsługuje urządzenia peryferyjne symulator może wystawiać zdarzenia skanowania kodów kreskowych.
-   **Skala** — Skala wirtualnego umożliwia symulowanie interakcji z elementów zważoną z punktu sprzedaży.
-   **Identyfikator osobisty numerycznej (PIN)** — można symulować operacje Konsola PIN. **Uwaga:** musi implementować obsługę fizyczne Konsola PIN za pośrednictwem łącznika płatności.
-   **Przechwytywanie podpisu** – obwodowych symulator zawiera urządzenia do przechwytywania podpisu wirtualnych, które można skonfigurować na monitowanie o podpisów, które są wymagane dla niektórych ofert, takich jak wpłat na konto odbiorcy.

Umożliwia także obwodowych symulatora do symulacji klawiatury klina zdarzeń, które pochodzą z skaner kodów kreskowych i MSR. Symulator wirtualnego peryferyjnych w szczególności obsługuje łączenie i osadzanie obiektów dla urządzeń Retail POS (OPOS).

## <a name="key-scenarios"></a>Podstawowe scenariusze
### <a name="troubleshooting"></a>Rozwiązywanie problemów

Urządzenia peryferyjne symulator służy do Rozwiązywanie problemów z instalacją urządzeń. Jeśli nie masz symulator peryferyjnych lub drugie urządzenie tej samej klasy, może być trudno określić, skąd pochodzą problemów. Jednak gdy symulator obwodowych, można skonfigurować urządzenia wirtualnego i uruchomić samej ścieżki kodu i logiki biznesowej, które są używane do urządzeń fizycznych. Z punktu widzenia peryferyjnych symulatora zasadnicza różnica między urządzenia wirtualne i fizyczne urządzenia jest obiekt usługi lub sterownika urządzenia. Dla urządzeń fizycznych obiekt usługi jest dostarczany przez producenta urządzenia. Z drugiej strony dla urządzenia peryferyjne symulator obiektów usługi są dostarczane jako część urządzenia peryferyjne symulatora. Symulator obwodowych działa prawidłowo, jeśli urządzenie nie działa poprawnie po zmianie nazwy urządzenia w profilu sprzętu do nazwy rzeczywiste urządzenie, można założyć, że istnieje problem z obiektem usługi, dostarczonego przez producenta.

### <a name="training"></a>Szkolenie

Urządzenia peryferyjne symulator służy do dodawania realistyczne warstwy do kasjera, szkolenia, kiedy instalacja sprzętu fizycznego nie jest dostępny. Po symulator peryferyjnych jest zawarty w scenariuszach szkolenia, kasjer może bardziej skutecznie współdziałać z punktu sprzedaży udostępniając dane wejściowe, takie jak produktu skanowanie kodu i prezent paska kiepskie piwo karty i obserwując przyjęcia są drukowane dla konkretnej transakcji.

### <a name="testing"></a>Testowanie

Symulator obwodowych służy do testowania kodów kreskowych produktu, formaty paragonów i tak dalej, bez konieczności wdrażania sprzętu fizycznego w środowisku wirtualnym. Ponieważ sprzęt fizyczny nie jest wymagany, a nie trzeba wdrażać klienta punktu sprzedaży na stacji sprzętu lub komputera fizycznego, szybciej można przetestować zmiany wprowadzone w back office.

## <a name="set-up-the-peripheral-simulator"></a>Konfigurowanie urządzenia peryferyjne symulatora
### <a name="set-up-a-hardware-profile"></a>Konfigurowanie profilów sprzętu

1.  Aby skonfigurować urządzenia peryferyjne symulatora, przejdź do **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**konfiguracji punktu sprzedaży**&gt;**profile POS**&gt;**profile sprzętu**.
2.  Aby utworzyć nowy profil, kliknij przycisk **nowy**.
3.  Wpisz wartości w **profil numer** i **opis** pól.
4.  Skorzystaj z poniższej tabeli, aby skonfigurować urządzenia wirtualne, które muszą być badane. Poniżej znajdują się wyjaśnienia dotyczące kolumny w tabeli:
    -   **Urządzenie** — w tej kolumnie nadaje nazwę skróconą kartę, która rozwiń skonfigurować urządzenie.
    -   **Typ urządzenia** — w tej kolumnie daje wartość wybrana w polu, które jest opatrywany etykietą zawierającą nazwę urządzenia.
    -   **Nazwa urządzenia** — w tej kolumnie podaje dokładną wartość, która zostanie wprowadzona nazwa urządzenia. **Ważne:** nazwy urządzeń, które są podane w tym polu jest wymagane, ponieważ stacja sprzętowa wykorzystuje te konkretne nazwy do rozwiązania urządzeń. Jeśli nie korzystasz z tych określonych nazw, nie będzie można używać urządzenia.

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

**Uwaga:** określonych ustawień w profilu sprzętowym jest wymagane symulowanie zdarzeń klina klawiatury z skaner kodów kreskowych i MSR.

### <a name="assign-the-hardware-profile-to-a-register"></a>Przypisywanie profilu sprzętu do rejestru

1.  Po utworzeniu profilu sprzętu, przejdź do **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**rejestruje**.
2.  W **Rejestry punktu sprzedaży** listy, kliknij łącze w **numer rejestru** dla rejestru, który należy używać urządzenia peryferyjne symulator pole.
3.  Kliknij przycisk **Edytuj**.
4.  W **profile** sekcji w **profilu sprzętu** wybierz profil sprzętu, który został utworzony dla wirtualnego urządzenia peryferyjne.
5.  Click **Save**.

### <a name="synchronize-changes-to-the-channel-database"></a>Synchronizowanie zmian wprowadzonych do bazy danych kanałów

1.  Przejdź do **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramu dystrybucji**.
2.  Wybierz **1090** harmonogramu dystrybucji.
3.  Kliknij **Uruchom teraz** do synchronizowania zmian do punktu sprzedaży.

Po dane są synchronizowane, nowy profil sprzętu i zmiany w rejestrze są dostępne w bazie danych kanału.

## <a name="install-the-peripheral-simulator"></a>Instalowanie urządzenia peryferyjne symulatora
1.  Przejdź do **detalicznych i commerce**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**profile POS**&gt;**profile sprzętu**.
2.  Kliknij **Pobierz**, a następnie kliknij przycisk **PeripheralSimulator**. **Uwaga:** należy wyłączyć blokowanie wyskakujących okienek, przed pobraniem obwodowych symulatora.
3.  Po zakończeniu pobierania Otwórz **programów** folder, a następnie kliknij dwukrotnie **VirtualPeripherals.msi** Aby uruchomić Instalatora.
4.  Symulator peryferyjne należy zainstalować przy użyciu ustawień domyślnych.

Oprócz symulator obwodowych należy zainstalować obiekty wspólnej kontroli z Monroe Consulting Services. W przeciwnym razie symulator peryferyjne nie będzie działać poprawnie. Aby pobrać obiektów wspólnej kontroli, przejdź do <http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Za pomocą symulatora urządzenia peryferyjne
Aby uruchomić symulator obwodowych, kliknij **Start** na komputerze, należy wpisać **symulator obwodowych Retail**, a następnie wybierz aplikację, gdy pojawi się w wynikach wyszukiwania. Po uruchomieniu symulatora obwodowych, kliknij nazwę urządzenia obsługiwanego urządzenia. Te urządzenia będą wyświetlane jako karty po lewej stronie okna. Aby wyświetlić określonego urządzenia, kliknij kartę dla tego urządzenia.

### <a name="line-display-capabilities"></a>Możliwości wyświetlania linii

Wyświetlanie linii jest pierwszego urządzenia wymienionego w peryferyjnych symulatora. Wyświetlanie linii jest skonfigurowany, to pokazuje pozycje, jak są skanowane w transakcji w punkcie sprzedaży. Oprócz pozycji, której wyświetlane są sumy należną po wybraniu oferty w punkcie sprzedaży. Pokazuje również saldo należności Jeśli oferta zostanie wprowadzona, ale równowagi jest nadal płatności dla transakcji. Gdy punktu sprzedaży nie jest używany, komunikat może wykazać wskazują, że kasowego jest zamknięty. Wiadomość należy skonfigurować na **liniowy wyświetlacz** skróconą kartę w profilu sprzętowym.

### <a name="cash-drawer-capabilities"></a>Możliwości szuflady środków pieniężnych

Szuflada kasowa jest drugim urządzeniem, wymieniony w peryferyjnych symulatora. Gdy profil sprzętu jest skonfigurowany do używania szuflady do kas wirtualnych, punktu sprzedaży Otwiera szufladę kasy active klawisza Shift w odpowiedzi na operacje szuflady, takie jak deklaracje środków płatniczych i tak, że kasjer może wprowadzić zmiany lub depozytu gotówkowego podczas standardowych prowadzącym transakcji. Szuflady do kas wirtualne mają etykiety **szuflady głównego** i **pomocniczy szuflady**. Etykiety te reprezentują szuflady i 2 szuflady w profilu sprzętowym, odpowiednio. Po szufladzie jest zamknięty, jest wyświetlany obraz szuflady kasowej zamkniętych i nosi nazwę przycisku na szuflady kasowej zamkniętych **Otwórz szufladę**. Jeśli klikniesz ten przycisk, obraz jest zastępowany obraz szuflady kasowej otwarte, aby wskazać, że szuflada będzie otwarta. Etykietą przycisku na szuflady kasowej Otwórz **zamknij Panel**. Kilka operacji w punkcie sprzedaży może powodować szuflady kasowej otworzyć. Większość operacji nie może kontynuować, gdy szuflada kasowa jest otwarty. Wyjątkami są niektóre procedury na koniec dnia. Jeśli POS użytkownik otrzyma komunikat o błędzie z informacją, że nie można wykonać operacji, gdy szuflada kasowa jest otwarty, użytkownik należy zamknąć szuflady kasowej wirtualnej lub fizycznej, aby kontynuować. Jeśli szuflada kasowa jest oznaczony jako **Shared** w profilu sprzętu, system nie gwarantuje, że szuflada jest zamknięta przed operacji. Operacja wpływy w zwykły sposób, nawet jeśli jest otwarta szuflada kasowa. To zachowanie obsługuje scenariuszy, gdzie szuflady do kas są współużytkowane przez dystrybutorów, a jeden skojarzyć używa szuflady kasowej, a innej jednostki stowarzyszonej wykonuje zadania niepowiązanych na swój własny urządzenia POS. Zmiany wprowadzone do szuflady kasowej nie są widoczne, aż do zamknięcia bieżącej zmiany i otworzyć nową zmianę.

### <a name="msr-capabilities"></a>Możliwości MSR

Urządzenia peryferyjne symulator zapewnia obsługę niezawodne wirtualnego operacji MSR pracując w trybie OPOS lub w trybie klawiatury klina. Tryb OPOS wymaga, że MSR można skonfigurować w profilu sprzętu do pracy jako urządzenie OPOS. Tryb klawiatury klina tylko wysyła zdarzenia danych klina klawiatury Microsoft Windows. Poza tym różnice w ustawieniach trybów klina OPOS i klawiatury różnią się w następujący sposób:

-   Klient POS umożliwia urządzeń OPOS MSR w określonych scenariuszach, takich jak scenariusze, które umożliwiają danych magnetycznych lojalnościowych lub pozycję karty upominkowej.
-   W trybie klina klawiatury peryferyjnych symulator wysyła dane klina klawiatury do pola, które jest aktywne, gdy dane są przesyłane. To zachowanie jest podobne zachowanie występuje, jeśli są wprowadzane za pomocą klawiatury. Aby użyć partycji MSR jako klina klawiatury, użytkownik musi przełączyć się do sprzedaży detalicznej nowoczesnych POS (MPOS) do odbierania danych we właściwym polu. W związku z tym opóźnienia, można skonfigurować tak, aby użytkownik ma czas, aby upewnić się, że dane będą przesyłane do odpowiedniego pola.

#### <a name="testing-gift-and-payment-card-swipes"></a>Testowanie kiepskie piwo karty upominkowej i płatności

MSR wirtualnego, który obwodowych symulator zawiera również umożliwia skonfigurowanie określonych danych MSR, aby przetestować scenariusze kiepskie piwo karty upominkowej i płatności. Aby utworzyć kartę, kliknij znak plus (**+**) przycisk i wybierz odpowiedni typ karty. Następnie określ numer karty lub śledzenia danych, która może być wysłana do punktu sprzedaży, wraz z wygaśnięcia miesiąc i rok dla karty, który definiujesz. Wartość wybrana w **typu karty** pole jest tylko etykieta mogą być mapowane do karty. Etykieta ułatwia określenie karty, jeśli są one czytniku przez symulator obwodowych. Można wybrać karty, które zostały skonfigurowane w symulatorze peryferyjnych przy użyciu strzałki w lewo (**&lt;**) i strzałki w prawo (**&gt;**) przycisków nad obrazem karty. Można edytować i usuwać karty za pomocą **edytować** i **usunąć** przyciski obok znaku plusa (**+**) przycisk.

### <a name="pin-pad"></a>Konsola PIN

Można skonfigurować symulator Konsola PIN do symulacji multipleksera pad OPOS PIN. Gdy transakcja transferu (EFT) środków elektronicznych jest wykonywane w punkcie sprzedaży i wymaga wprowadzenia numeru PIN, stacja sprzętowa wywołania numeru PIN urządzenie na monitowanie o wprowadzanie numeru PIN. Aby pracować, Konsola PIN w symulatorze peryferyjnych wymaga obsługi łącznika płatności EFT.

### <a name="printer"></a>Drukarka

Wirtualna drukarka peryferyjnych po prostu pokazuje przychody podczas drukowania z punktu sprzedaży. Jeśli operacji drukowania wielu przychodów, można przewijać przyjęć.

#### <a name="configure-receipt-printing"></a>Skonfigurować drukowanie paragonu

1.  Przejdź do **detalicznych i commerce**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**profile POS**&gt;**profile sprzętu**.
2.  Wybierz profil sprzętu, który został utworzony dla wirtualnego urządzenia peryferyjne.
3.  Na **drukarki** skróconej, kliknij przycisk **edytować**.
4.  W **identyfikator profilu paragonów** wybierz profil paragonów.
5.  Click **Save**.

### <a name="scale"></a>Skalowanie

Gdy produkt ważony jest dodany do transakcji POS i skali jest skonfigurowany, punktu sprzedaży pobiera waga ze skali. Zarówno w wirtualnym i fizycznym skali produktu lub wagę należy określić przed dodaniem produktu do transakcji. Przed dodaniem produkt ważony do transakcji przejdź do skali w symulatorze obwodowych i użyj znaku plusa (**+**) i minus (**—**) przyciski, aby dostosować grubość skali powinna złożyć sprawozdanie. Można także wprowadzić bezpośrednio w pożądanej wagi **bieżącą wartość** pole. Jednostki masy dla skali można dostosować za pomocą znaku plus (**+**), **edytować**, i **usunąć** przyciski. W ten sposób można określić jednostek na podstawie ustawień regionalnych, których skala jest używany lub produktów, które są ważone.

#### <a name="configure-a-scale-product"></a>Konfiguruj produkt skali

1.  Przejdź do **detalicznych i****handlu**&gt;**produktów i kategorii**&gt;**Zwolnione produkty według kategorii**.
2.  Otwórz rekord produktu.
3.  Wybierz produkt do ważenia.
4.  Na **Retail** ustawić skróconej **produkt ważony** opcję **nr** do **tak**.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synchronizowanie zmian wprowadzonych do bazy danych kanałów

1.  Przejdź do **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramu dystrybucji**.
2.  Wybierz **1040** harmonogramu dystrybucji.
3.  Kliknij **Uruchom teraz** do synchronizowania zmian do punktu sprzedaży.

Po dane są synchronizowane, gdy produkt ważony jest dodawany do transakcji POS POS sprawdza skali wagi.

### <a name="signature-capture"></a>Przechwytywanie podpisu

Urządzenia do przechwytywania podpisu wirtualnego monituje użytkownika o dostarczyć podpisu na podkładce przechwytywania podpisu wirtualnych w przypadku przetargu, który jest używany wymaga podpisu. Użytkownik może zaakceptować podpisu, aby pokazać je w punkcie sprzedaży. Kasjer może przyjąć podpisu. Podpis jest następnie zapisywany wraz z oferty i zsynchronizowanie back office wraz z innymi danymi transakcji.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Konfigurowanie oferty wymagać podpisu

1.  Przejdź do **sieci sprzedaży i handlu**&gt;**kanałów**&gt;**sklepów detalicznych**&gt;**wszystkich sklepów detalicznych**.
2.  Wybierz sklep sieci sprzedaży.
3.  Kliknij przycisk **Edytuj**.
4.  Kliknij **skonfigurować**, a następnie w **skonfigurować** sekcji, kliknij **metody płatności**.
5.  Kliknij przycisk **Edytuj**.
6.  Wybierz metodę płatności, która wymaga podpisu.
7.  W **ogólne** sekcji **przechwytywania podpisu**, ustaw **urządzenia do przechwytywania podpisu użyj** opcji w celu **tak**.
8.  W **minimalna kwota przechwytywania podpisu** pole, wprowadź minimalną kwotę, która powinna uruchamiać przechwytywania podpisu.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synchronizowanie zmian wprowadzonych do bazy danych kanałów

1.  Przejdź do **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramu dystrybucji**.
2.  Wybierz **1070** harmonogramu dystrybucji.
3.  Kliknij **Uruchom teraz** do synchronizowania zmian do punktu sprzedaży.

Po dane są synchronizowane, gdy używany jest oferta, który wymaga podpisu, a kwota spełnia próg podpisu, POS monituje o podanie podpisu na urządzenia do przechwytywania podpisu wirtualnych.

## <a name="additional-configuration"></a>Dodatkowa konfiguracja
Można edytować plik konfiguracji symulator obwodowych na bardziej odpowiedni adres scenariuszy, które testujesz. Można znaleźć pliku konfiguracyjnego C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Plik konfiguracyjny definiuje jednostki, które są dostępne dla testów na skali, rodzaje kart, które są dostępne do testowania i typy kodów kreskowych. Na przykład zmieniając wartości tekstowe w pliku konfiguracji, można dodać nowy typ karty lub jednostki miary, który może być wybrany w czasie wykonywania. Nowe wartości pojawi się po ponownym uruchomieniu aplikacji.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Działania dla urządzenia peryferyjne simulator są rejestrowane w peryferyjnych symulatora. Dziennik można znaleźć w C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Urządzenia peryferyjne symulatora również raporty problemy w dzienniku zdarzeń systemu Windows są dostępne w **Dzienniki aplikacji i usług**&gt;**Microsoft**&gt;**systemu Dynamics AX**. Jeśli zmiany wprowadzone do profilu sprzętu lub inne obszary nie są widoczne podczas korzystania z MPOS lub peryferyjnych symulatora, sprawdź zadania harmonogramu dystrybucji, które służy do synchronizowania danych do bazy danych kanału. Jeśli zmiany zostały zsynchronizowane, ale nadal nie są widoczne w punkcie sprzedaży, uruchom ponownie klienta punktu sprzedaży. Zmiany szuflady do kas skonfigurowanych nie są skuteczne, dopóki nie zostanie utworzony nowy klawisz shift. W związku z tym jeśli wprowadzisz zmiany do szuflady do kas upewnij się, zawsze zamknąć istniejący shift, aby przetestować nowe ustawienia szuflady gotówki. Czasami jeśli po wspólnej kontroli obiekty z Monroe Consulting Services jest zainstalowany sterownik producenta, sterownik może powodować wspólnych obiektów kontroli przestał działać poprawnie. W takim przypadku należy ponownie zainstalować obiektów wspólnej kontroli.

<a name="see-also"></a>Informacje dodatkowe
--------

[Retail peripherals overview](retail-peripherals-overview.md)


