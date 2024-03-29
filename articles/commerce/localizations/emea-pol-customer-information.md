---
title: Zarządzanie informacjami dotyczącymi klienta (Polska)
description: W tym artykule opisano sposób obsługi informacji o klientach w programie Retail POS dla Polski.
author: EvgenyPopovMBS
ms.date: 08/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Poland
ms.author: josaw
ms.search.validFrom: 2019-11-11
ms.openlocfilehash: 204bb9dc1f12e6f58f122fef388304655cb44478
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473974"
---
# <a name="customer-information-management-for-poland"></a>Zarządzanie informacjami dotyczącymi klienta (Polska)

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Wprowadzenie

W tym artykule opisano sposób obsługi informacji o odbiorcy, takich jak numer podatku VAT, w Retail Point of Sale (POS) dla Polski.

Numer VAT odbiorcy można określić podczas tworzenia lub edytowania głównego rekordu odbiorcy w punkcie sprzedaży. Można także określić numer VAT dla transakcji sprzedaży, kopiując go z odbiorcy transakcji lub wprowadzając go ręcznie. Informacje dotyczące odbiorcy mogą być następnie drukowane zarówno na stałych, jak i fiskalnych przychodach i mogą być używane do celów fakturowania.

> [!IMPORTANT]
> Nie można określić numeru VAT odbiorcy w POS, gdy w profilu funkcji POS włączono opcję **Tworzenie odbiorcy w trybie asynchronicznym**. Obsługę trybu tworzenia asynchronicznego odbiorcy można dodać w przyszłych aktualizacjach.

## <a name="setup"></a>Konfiguracja

Aby skorzystać z ten funkcji należy skonfigurować system w następujący sposób:

- Zarządzanie informacjami dotyczącymi klienta dla Polski.
- Ustawić typ rejestracji dla numeru VAT.
- Dodać operację **Dodaj informacje o kliencie** do układów ekranu.
- Aktywować zapytanie dotyczące informacji o odbiorcy.
- Konfigurować format paragonu.
- Konfiguracja składników kanału.

### <a name="enable-the-customer-information-management-feature-for-poland"></a>Zarządzanie informacjami dotyczącymi klienta dla Polski

Włącz funkcję **(Polska) Zarządzanie informacjami o odbiorcach w programie Retail POS** w obszarze roboczym **Zarządzanie funkcjami**.

### <a name="set-up-a-registration-type-for-the-vat-number"></a>Ustawić typ rejestracji dla numeru VAT

Przed określeniem numerów VAT w POS należy utworzyć odpowiedni typ rejestracji numeru VAT i połączyć go z kategorią rejestracyjną identyfikatora **VAT ID**. Aby uzyskać więcej informacji na temat pracy z typami rejestracji i identyfikatorami rejestracji, przejrzyj [Identyfikatory rejestracji](../../finance/localizations/emea-registration-ids.md).

> [!WARNING]
> Jeśli typ rejestracji nie zostanie utworzony lub nie jest połączony z kategorią rejestracji identyfikatorów **VAT ID**, w programie POS zostanie wygenerowany błąd, jeśli dla adresu odbiorcy zostanie wypełniony numer VAT.

### <a name="add-the-add-customer-information-operation-to-screen-layouts"></a>Dodaj operację Dodaj informacje o kliencie do układów ekranu

Za pomocą operacji **Dodawania informacji o kliencie** można dodawać informacje o odbiorcy do transakcji sprzedaży, takie jak np. numer VAT. Te informacje można skopiować z odbiorcy określonego dla transakcji lub ręcznie wprowadzić.

Na stronie **Siatki przycisków** wybierz siatkę przycisków, na której ma się pojawić operacja, a następnie otwórz Projektanta siatki przycisków. Dodaj nowy przycisk, nastepnie w polu **Działanie**, wybierz **Dodaj informacje o kliencie**. Aby uzyskać więcej informacji na temat pracy z układami ekranu i siatkami przycisków, należy zapoznać się z [Układami ekranu dla punkt sprzedaży (POS)](../pos-screen-layouts.md).

### <a name="activate-the-inquiry-for-customer-information"></a>Aktywuj zapytanie dotyczące informacji o odbiorcy

Jeśli dla transakcji sprzedaży nie określono informacji o odbiorcy, prośba o te informacje może zostać wyzwolona automatycznie po sfinalizowaniu transakcji. Ta metoda jest alternatywą dla operacji **Dodawania informacji o odbiorcy**.

Aby uaktywnić opcję żądania informacji o odbiorcy w centrali Commerce headquarters na stronie **Profile funkcji punktu sprzedaży**, na skróconej karcie **Funkcje**, w obszarze **Parametry podatków**, ustaw opcję **Włącz pytanie o informacje o odbiorcy w transakcjach sprzedaży** na wartość **Tak**.

### <a name="set-up-receipt-formats"></a>Konfiguracja formatów paragonu

Formaty paragonów można skonfigurować w taki sposób, aby numer VAT odbiorcy był na nich drukowany.

> [!NOTE]
> Domyślna firma użytkownika, który tworzy konfigurację paragonu, powinna być tą samą osobowością prawną, w której jest tworzone ustawienie tekstu w języku. Alternatywnie, można również utworzyć ten sam tekst językowy w domyślnej firmie użytkownika i dla tego samego bytu prawnego, dla którego utworzono konfigurację.

Na stronie **Tekst języka**, na karcie **Punkt sprzedaży** dodaj następujący rekord dla etykiety pola niestandardowego w przypadku formatów paragonów. Należy zwrócić uwagę, że przykłady **Identyfikatora języka**, **Identyfikatora tekstu** oraz wartości **tekstowe** przedstawione w poniższej tabeli są tylko przykładami. Można je zmienić, aby spełniały wymagania użytkownika. Jednak używana wartość **identyfikatora tekstu** musi być unikatowa i musi być równa lub większa niż 900001.

| Identyfikator języka | Identyfikator tekstu | Tekst       |
|-------------|---------|------------|
| en-US       | 900001  | Numer VAT |

Na stronie **Niestandardowe pola** dodaj następujący rekord dla pola niestandardowego w odniesieniu do formatów paragonów. Należy zauważyć, że wartość **identyfikatora tekstu podpisu** musi być zgodna z wartością **identyfikatora tekstu** podaną na **stronie tekstowej języka**.

| Nazwisko                      | Typ    | Identyfikator tekstu podpisu |
|---------------------------|---------|-----------------|
| FISCALCUSTOMER\_VATID\_pl | Odbiór | 900001          |

W projektancie formatów paragonów dodaj pole niestandardowe do odpowiedniej sekcji paragonu dla każdego wymaganego formatu paragonu. Aby uzyskać więcej informacji o sposobie pracy z formatami paragonów, zobacz [Szablony paragonów i drukowanie](../receipt-templates-printing.md).

### <a name="configure-channel-components"></a>Konfiguracja składników kanału.

> [!IMPORTANT]
> Kroki opisane w tej sekcji należy zaimplementować tylko w przypadku korzystania z wersji Microsoft Dynamics 365 Commerce 10.0.28 lub wcześniejszej. W wersji Commerce 10.0.29 wszystkie składniki kanału Commerce, które są wymagane do aktywowania zarządzania informacjami o klientach dla Polski, są włączone domyślnie. Jeśli korzystasz z wersji Commerce 10.0.28 lub starszej i migrujesz do wersji Commerce 10.0.29 lub nowszej, musisz wykonać kroki w tecie [Migracja do wersji 10.0.29 lub nowszej](#migrate-to-commerce-version-10029-or-later).

Aby udostępnić funkcje właściwe dla Polski, należy skonfigurować rozszerzenia dla składników kanału. Aby uzyskać więcej informacji, zobacz sekcję [Wskazówki dot. wdrożenia](#deployment-guidelines) w dalszej części tego artykułu.

## <a name="example-scenarios"></a>Przykładowe scenariusze

Poniższe przykładowe scenariusze przedstawiają sposób pracy z informacjami o odbiorcach w POS dla Polski.

### <a name="scenario-1-make-a-sale-to-an-anonymous-customer"></a>Scenariusz 1: dokonać sprzedaży anonimowemu odbiorcy

1. Zaloguj się w POS.
1. Dodaj pozycje do koszyka.
1. Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie wybierz **Wprowadź ręcznie**.
1. Wprowadź numer VAT odbiorcy, a następnie kliknij przycisk **OK**.
1. Zarejestruj płatności dla transakcji, a następnie zakończ transakcję.
1. Sprawdź, czy wydrukowany paragon zawiera numer VAT odbiorcy.

### <a name="scenario-2-make-a-sale-to-a-new-named-customer"></a>Scenariusz 2: dokonać sprzedaży nowemu, nazwanemu odbiorcy

1. Zaloguj się w POS.
1. Dodaj pozycje do koszyka.
1. Wybierz opcję **Dodaj odbiorcę**, a następnie wybierz **Nowy**.
1. Ustaw atrybuty nowego odbiorcy.
1. Wybierz **Stwórz nowy adres**. Następnie określ informacje kontaktowe nowego odbiorcy oraz adres.
1. W polu **Numer VAT** wprowadź numer VAT odbiorcy.
1. Zapisz rekord odbiorcy i rekord adresu odbiorcy, a następnie dodaj odbiorcę do transakcji.
1. Zarejestruj płatności dla transakcji, a następnie zakończ transakcję.
1. Ponieważ zostało aktywowane zapytanie o informacje o odbiorcy, ale informacje o odbiorcy nie zostały dodane do transakcji, zostanie otwarte okno dialogowe **Wprowadź informacje o odbiorcy** . Wybierz opcję **Tak**, a następnie wybierz opcję **Kopiuj z odbiorcy transakcji**.
1. Sprawdź numer VAT odbiorcy, a następnie kliknij przycisk **OK**.
1. Sprawdź, czy wydrukowany paragon zawiera numer VAT odbiorcy.

> [!NOTE]
> Jeśli trzeba określić innego odbiorcę dla transakcji, należy wyczyścić informacje o odbiorcy, a następnie skopiować je ponownie po dodaniu nowego odbiorcy.

### <a name="scenario-3-change-the-customer-information-for-a-sale-to-a-named-customer"></a>Scenariusz 3: zmiana informacji o odbiorcy sprzedaży na nazwanego odbiorcę

1. Zaloguj się w POS.
1. Dodaj pozycje do koszyka.
1. Wybierz **Dodaj odbiorcę**, a następnie wybierz konto odbiorcy i dodaj je do transakcji.
1. Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie wybierz opcję **Kopiuj z odbiorcy transakcji**.
1. Sprawdź numer VAT odbiorcy, a następnie kliknij przycisk **OK**.
1. Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie kliknij **Wyczyść**, aby wyczyścić informacje o odbiorcy z transakcji.
1. Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie wybierz **Wprowadź ręcznie**.
1. Podaj numer VAT odbiorcy, a następnie kliknij przycisk **OK**.
1. Zarejestruj płatności dla transakcji, a następnie zakończ transakcję.
1. Sprawdź, czy wydrukowany paragon zawiera numer VAT odbiorcy.

## <a name="deployment-guidelines"></a>Wskazówki dotyczące wdrażania

> [!IMPORTANT]
> Kroki opisane w tej sekcji należy zaimplementować tylko w przypadku korzystania z wersji Commerce 10.0.28 lub wcześniejszej. W wersji Commerce 10.0.29 wszystkie składniki kanału Commerce, które są wymagane do aktywowania zarządzania informacjami o klientach dla Polski, są włączone domyślnie. Jeśli korzystasz z wersji Commerce 10.0.28 lub starszej i migrujesz do wersji Commerce 10.0.29 lub nowszej, musisz wykonać kroki w tecie [Migracja do wersji 10.0.29 lub nowszej](#migrate-to-commerce-version-10029-or-later).

Ta sekcja zawiera wskazówki dotyczące wdrażania umożliwiające zarządzanie informacjami o klientach w lokalizacji Dynamics 365 Commerce dla Polski.

> [!NOTE]
> Jeśli chcesz włączyć integrację POS z drukarkami fiskalnymi w Polsce, a w szczególności, jeśli chcesz drukować numery podatku VAT od odbiorców na paragonach fiskalnych, musisz wdrożyć [próbkę integracji z drukarką fiskalną dla Polski](emea-pol-fpi-sample.md).

### <a name="update-customizations"></a>Dostosowanie aktualizacji

Jeśli dostosowania mają odwołania do usługi `TaxRegistrationIdFiscalCustomerService`, muszą zostać usunięte.

### <a name="update-a-development-environment"></a>Aktualizacja środowiska projektowego

Aby zaktualizować środowisko programistyczne, należy wykonać następujące kroki.

#### <a name="crt-extension-components"></a>CRT komponenty rozszerzenia

1. Znajdź plik konfiguracji rozszerzenia dla środowiska uruchomieniowego Commerce Runtime (CRT):

    - **Commerce Scale Unit:** znajdź plik **CommerceRuntime.Ext.config** w folderze **bin\\ext** w lokalizacji strony Microsoft Internet Information Services (IIS) Commerce Scale Unit site location.
    - **Lokalne wystąpienie CRT na Modern POS:** znajdź plik **CommerceRuntime.MPOSOffline.Ext.config** w lokalizacji brokera lokalnego klienta CRT.

1. Zarejestruj zmianę rozszerzenia CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików CommerceRuntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="modern-pos-extension-components"></a>Komponenty rozszerzenia nowoczesnego POS

Aby udostępnić rozszerzenie TaxRegistrationId.PL, należy wykonać następujące kroki.

1. Otwórz rozwiązanie w **RetailSdk\\POS\\ModernPOS.sln**.
1. W pliku **POS.Extensions\\extensions.json**, włącz rozszerzenie.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.PL"
            }
        ]
    }
    ```

1. Stwórz rozwiązanie.
1. Otwórz Modern POS i przetestuj te funkcje.

#### <a name="cloud-pos-extension-components"></a>Komponenty rozszerzenia Cloud POS

Aby udostępnić rozszerzenie TaxRegistrationId.PL, należy wykonać następujące kroki.

1. Otwórz rozwiązanie w **RetailSdk\\POS\\CloudPOS.sln**.
1. W pliku **POS.Extensions\\extensions.json**, włącz rozszerzenie.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.PL"
            }
        ]
    }
    ```

1. Stwórz rozwiązanie.
1. Otwórz Cloud POS i przetestuj te funkcje.

### <a name="update-a-production-environment"></a>Zaktualizuj środowisko produkcyjne

Wykonaj następujące kroki, aby utworzyć możliwe do wdrożenia pakiety, które zawierają składniki Commerce i aby stosować te pakiety w środowisku produkcyjnym.

1. W plikach konfiguracji **CommerceRuntime.Ext.config** i **CommerceRuntime.MPOSOffline.Ext.config**, w folderze **RetailSdk\\Assets** dodaj następujący wiersz w sekcji **Kompozycja**.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland" />
    ```

1. Włącz rozszerzenie POS **TaxRegistrationId.PL**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.PL"
            }
        ]
    }
    ```

1. Uruchom narzędzie **msbulid** dla całego zestawu Retail Software Development Kit (SDK), aby utworzyć pakiety do wdrożenia.
1. Zastosuj pakiety za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS) lub ręcznie. Aby uzyskać więcej informacji, zobacz [Pakiety Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="migrate-to-commerce-version-10029-or-later"></a>Migracja do wersji Commerce 10.0.29 lub nowszej

Kroki opisane w tej sekcji są wymagane w przypadku korzystania z programu Commerce w wersji 10.0.28 lub starszej oraz do wersji 10.0.29 lub nowszej. Aby poprawnie zaktualizować środowisko Commerce, należy wykonać następujące kroki.

1. Zaktualizuj centralę Commerce Headquarters.
1. Włącz [Funkcje specyficzne dla Polsk](#enable-the-customer-information-management-feature-for-poland) w obszarze roboczym **Zarządzanie funkcjami** i umieść zmiany w kanałach.
1. Zaktualizuj CRT, Cloud POS i Modern POS, a następnie wyklucz następujące starsze rozszerzenia specyficzne dla Polski:

    1. W plikach **commerceruntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** wyklucz rozszerzenie CRT **Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland**.
    1. W pliku **extensions.json** wykluczrozszerzenie punktu sprzedaży **Microsoft/TaxRegistrationId.PL**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
