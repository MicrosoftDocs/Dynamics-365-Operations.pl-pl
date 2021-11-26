---
title: Dedykowane terminale płatności oraz monity o drukarkę i szuflady kasowe
description: Ten temat zawiera informacje o możliwości uzyskania dedykowanego terminalu płatności i powiadamiania użytkownika o wybranie szuflady kasowej oraz drukarki paragonów.
author: BrianShook
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: b955e55271471ac43ff4c2b217c6448b30536e06
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779777"
---
# <a name="dedicated-payment-terminals-and-prompts-for-a-printer-and-cash-drawer"></a>Dedykowane terminale płatności oraz monity o drukarkę i szuflady kasowe

[!include [banner](includes/banner.md)]

Ten temat zawiera informacje o możliwości uzyskania dedykowanego terminalu płatności i powiadamiania użytkownika o wybranie szuflady kasowej oraz drukarki paragonów.

## <a name="overview"></a>Omówienie

Współcześni sprzedawcy detaliczni szukają sposobów na usprawnienie zakupów w sklepie. Najnowsze trendy w zakresie płatności elektronicznych bez uzycia papieru nie tylko ułatwiają dokonywanie zakupów, ale także zmniejszają potrzebę posiadania pełnego zestawu urządzeń peryferyjnych dla każdego pracownika sklepu.

Microsoft Dynamics 365 Commerce wspiera te trendy, włączając scenariusz, w którym do urządzenia punktu sprzedaży (POS) przypisany jest dedykowany terminal płatności, ale nie ma własnej drukarki paragonów ani szuflady kasowej. Jeśli pracownicy muszą wydrukować paragon lub zabrać płatność gotówką, zostanie wyświetlony monit o wybranie stacji sprzętowej, w której te urządzenia są skonfigurowane.

## <a name="key-terms"></a>Kluczowe terminy

| Okres | opis |
|---|---|
| Rejestracja | Jednostka używana do konfigurowania wystąpienia kasy punktu sprzedaży. |
| Urządzenie | Reprezentacja fizycznej wystapienia kasy punktu sprzedaży i przypisanej do niej aplikacji Modern POS. |
| Dedykowana stacja sprzętowa | Stacja sprzętowa logiki biznesowej, która jest wbudowana w aplikacji Modern POS dla Windows oraz Modern POS dla Android. |
| Port szuflady typu kick (d/k) | Tradycyjna metoda łączenia szuflady kasowej z drukarką paragonu. |
| Sieciowe urządzenia peryferyjne | Wbudowana obsługa terminali płatniczych podłączonych do sieci, drukarek paragonów i szuflad kasowych. |

## <a name="supported-pos-clients-and-devices"></a>Obsługiwani klienci i urządzenia punktu sprzedaży

Funkcja opisana w tym temacie jest obsługiwana przez Modern POS dla Windows i Modern POS dla klientów punktu sprzedaży korzystających z Android.

Ta funkcja obsługuje terminale płatności obsługiwane w sieci i drukarki paragonów. Obsługę szuflady kasowej można uzyskać, łącząc szufladę kasową z drukarką z obsługą sieci za pośrednictwem portu d/k.

Gotowe wsparcie dla tej funkcji zapewnia [Łącznik płatności usługi Dynamics 365 dla Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3). Jednak inne łączniki płatności mogą być obsługiwane za pośrednictwem zestawu Commerce Software Development Kit (SDK) dla płatności. Obsługiwane drukarki paragonów obejmują drukarki paragonów z obsługą sieci od Star Micronics i Epson.

Aby skonfigurować drukarki pokwitowań Star Micronics, użyj narzędzia Star Micronics Printer Utility do skonfigurowania urządzenia, aby mogło być używane przez sieć. To narzędzie umożliwia również podanie adresu IP urządzenia.

Aby skonfigurować drukarki paragonów Epson, należy za pomocą narzędzia drukowania ePOS-Print firmy Epson skonfigurować urządzenie do używania protokołów sieciowych.

Aby uzyskać więcej informacji dotyczących sposobu konfigurowania urządzeń peryferyjnych, zajrzyj do [Omówienie obsługi urządzeń peryferyjnych w sieci](./dev-itpro/network-peripherals.md).

## <a name="set-up-a-dedicated-payment-terminal-and-a-prompt-for-a-printer-and-cash-drawer"></a>Skonfiguruj dedykowany terminal płatniczy i monit o drukarkę i szufladę kasową

### <a name="set-up-hardware-profiles"></a>Konfigurowanie profilów sprzętowych

Trzeba mieć dwa typy profilów sprzętu. Pierwszy jest przypisany do kasy. Drugi jest przypisany do stacji sprzętowej na poziomie sklepu i służy do logicznego grupowania sieciowych drukarek pokwitowań i szuflad kasowych.

#### <a name="set-up-a-hardware-profile-for-the-register"></a>Skonfiguruj profil sprzętu dla kasy

Aby skonfigurować profil sprzętu przypisany do kasy, wykonaj następujące kroki.

1. W Dynamics 365 Commerce wyszukaj **Profil sprzętu**.
2. Wybierz pozycję **Nowy**.
3. Przypisz profil sprzętu, a następnie wprowadź opis. Ten profil sprzętu zostanie przypisany do samej kasy. W związku z tym wystarczające jest określenie opisu, jak na przykład **Dedykowany z rezerwą**.
4. Na karcie skróconej dla różnych typów urządzeń należy skonfigurować następujące typy urządzeń:

    | Urządzenie | Typ | Nazwa urządzenia | Dodatkowe szczegóły |
    |---|---|---|---|
    | Drukarka | Sieć | *Jakikolwiek* | W nazwie urządzenia jest rozróżniana wielkość liter. **Identyfikator profilu paragonów** powinien być taki sam jak **Identyfikator profilu paragonów** mapowany do drukarki sieciowej skonfigurowanej w profilu sprzętowym przypisanym do stacji sprzętowej na poziomie kanału. |
    | Szuflada kasowa | Sieć | *Jakikolwiek* | W nazwie urządzenia jest rozróżniana wielkość liter. W opcji **Używaj zmiany udostępnionej** zaznacz wartość **Tak**. |
    | Usługa EFT | Adyen | Nie dotyczy | Aby uzyskać informacje o konfigurowaniu aktualnego, gotowego do użytku łącznika płatności Adyen dla sklepów internetowych, zobacz temat [Łącznik płatności usługi Dynamics 365 dla Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3). Inne łączniki płatności mogą być obsługiwane za pośrednictwem [zestawu Commerce Software Development Kit (SDK) dla płatności](./dev-itpro/end-to-end-payment-extension.md). |
    | Konsola PIN | Sieć | **MicrosoftAdyenDeviceV001** | Brak. |

5. W Dynamics 365 Commerce wyszukaj **Kasy**.
6. Wybierz kasę, wybierając numer kasy, a następnie wybierz opcję **Edytuj**.
7. Przypisz właśnie utworzony profil sprzętu do kasy, która powinna używać dedykowanego terminalu płatności. Urządzenie, które jest mapowane na tę kasę musi używać aplikacji Modern POS dla Windows lub Modern POS dla aplikacji Android.
8. Wybierz opcję **Zapisz**.
9. W okienku akcji na karcie **Kasy** wybierz opcję **Skonfiguruj adresy IP**.
10. Na skróconej karcie **Konsola PIN** wprowadź adres IP terminalu płatności. Aby uzyskać informacje na temat pobierania adresu IP terminalu płatności przy użyciu łącznika Adyen, zapoznaj się z [Łącznik płatności usługi Dynamics 365 dla Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3).
11. Wybierz opcję **Zapisz**.

#### <a name="set-up-a-hardware-profile-for-the-receipt-printer-and-cash-drawer"></a>Konfigurowanie profilu sprzętu dla drukarki paragonów i szuflady kasowej

Aby skonfigurować profil sprzętowy używany do grupowania sieciowej drukarki paragonów i szuflady kasowej, wykonaj następujące kroki.

1. W Dynamics 365 Commerce wyszukaj **Profil sprzętu**.
2. Wybierz pozycję **Nowy**.
3. Przypisz profil sprzętu, a następnie wprowadź opis. Ten profil sprzętu będzie używany do grupowania drukarki paragonów i szuflady kasowej. Dlatego wystarczy opis, np. **Drukarka sieciowa i szuflada kasowa**.
4. Na karcie skróconej dla różnych typów urządzeń należy skonfigurować następujące typy urządzeń:

    | Urządzenie | Typ | opis | Dodatkowe szczegóły |
    |---|---|---|---|
    | Drukarka | Sieć | **Epson** lub **Star** | W nazwie urządzenia jest rozróżniana wielkość liter. **Identyfikator profilu paragonów** powinien być taki sam jak **Identyfikator profilu paragonów** mapowany do drukarki skonfigurowanej w profilu sprzętowym przypisanym do kasy. |
    | Szuflada kasowa | Alternatywa | **Epson** lub **Star** | W nazwie urządzenia jest rozróżniana wielkość liter. w opcji **Używaj zmiany udostępnionej** zaznacz wartość **Tak**. |

5. Wybierz opcję **Zapisz**.

### <a name="set-up-hardware-stations"></a>Konfigurowanie stacji sprzętowych

Trzeba mieć dwie stacje sprzętowe. Pierwsza zostanie zamapowana na kasę. Druga zostanie wybrana jako wymagana, ilekroć musi być wydrukowany paragon lub musi zostać otwarta szuflada kasowa.

#### <a name="register-a-hardware-station"></a>Rejestrowanie stacji sprzętowej

1. W Dynamics 365 Commerce, wyszukaj **Wszystkie sklepy**.
2. Wybierz sklep, wybierając jego wartości **Identyfikatora kanału sieci sprzedaży**, a następnie wybierz opcję **Edytuj**.
3. Na skróconej karcie **Stacje sprzętowe** wybierz pozycję **Dodaj**.
4. W polu **Typ stacji sprzętowej** określ wartość **Dedykowane**.
5. Wprowadź opis, ale nie ustawiaj żadnych innych wartości dla tej stacji sprzętowej. Ta stacja sprzętowa będzie zawsze używana dla kasy. 

#### <a name="set-up-a-hardware-station-for-the-receipt-printer-and-cash-drawer"></a>Konfigurowanie stacji sprzętowej dla drukarki paragonów i szuflady kasowej

1. W Dynamics 365 Commerce, wyszukaj **Wszystkie sklepy**.
2. Wybierz sklep, wybierając jego wartości **Identyfikatora kanału sieci sprzedaży**, a następnie wybierz opcję **Edytuj**.
3. Na skróconej karcie **Stacje sprzętowe** wybierz pozycję **Dodaj**.
4. W polu **Typ stacji sprzętowej** określ wartość **Dedykowane**.
5. Wprowadź opis. Ta stacja sprzętowa będzie używany do drukarki paragonów i szuflady kasowej.
6. W polu **Profil sprzętu** wybierz utworzony wcześniej profil sprzętu dla drukarki paragonów i szuflady kasowej.
7. Wybierz opcję **Zapisz**.
8. Gdy stacja sprzętowa dla drukarki paragonów i szuflady kasowej jest wciąż zaznaczona, wybierz opcję **Konfiguruj adresy IP**.
9. Uzyskaj adres IP drukarki i wprowadź go jako adres IP dla drukarki paragonów i szuflady kasowej.
10. Wybierz opcję **Zapisz**
11. Umożliwia wyszukiwanie **Harmonogramów dystrybucji**.
12. Wybierz harmonogram dystrybucji **1090**, a następnie wybierz opcję **Uruchom teraz**.
13. Wybierz harmonogram dystrybucji **1070**, a następnie wybierz opcję **Uruchom teraz**.

### <a name="set-up-the-system-to-prompt-for-receipt-printer-and-cash-drawer-selection-as-its-required"></a>Skonfiguruj system tak, aby monitował o wybór drukarki pokwitowań i szuflady kasowej zgodnie z wymaganiami

1. W obsługiwanym kliencie punktu sprzedaży zamknij bieżącą zmianę, jeśli jest otwarta zmiana.
2. Zaloguj się, a następnie wybierz **Operacje szuflady bez szuflady**.
3. Aby włączyć stację sprzętową, należy skorzystać z operacji **Zarządzaj stacjami sprzętowymi**.
4. Wybierz stację sprzętową utworzoną dla kasy, aby ją uaktywnić.
5. Wyloguj się z kasy POS, ponownie zaloguj się i otwórz zmianę.

Terminal płatności przypisany do profilu sprzętu będzie teraz zawsze aktywny i pojawi się monit, jeśli jest wymagana drukarka paragonów lub szuflada kasowa.

Wielu sprzedawców, którzy zamówili tę funkcję, jest zainteresowanych zmniejszeniem ilości odpadów poprzez dostarczanie potwierdzeń e-mail i zachęcanie do płatności elektronicznych. W zależności od konfiguracji POS, pracownicy sklepu są proszeni o wybranie drukarki paragonów lub szuflady kasowej tylko wtedy, gdy klient chce fizycznego paragonu lub chce zapłacić gotówką.

Pracownicy sklepu są proszeni o wybranie stacji sprzętowej tylko raz na transakcję, chyba że należy wydrukować paragon i użyć gotówki do płatności, ale pierwotnie wybrany profil sprzętowy nie obejmuje obu urządzeń. W takim przypadku ponownie zostanie wyświetlony monit z prośbą o wybranie stacji sprzętowej, która może zostać użyta do ukończenia transakcji.

## <a name="related-articles"></a>Powiązane artykuły

- [Konfigurowanie aplikacji POS hybrid w systemach Android i iOS](./dev-itpro/hybridapp.md)
- [Łącznik płatności usługi Dynamics 365 dla Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3)
- [Omówienie obsługi urządzeń peryferyjnych w sieci](./dev-itpro/network-peripherals.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
