---
ms.openlocfilehash: a0c9850226ce1fedc54b9154e2336fa11d3863b4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286542"
---
# <a name="customer-information-management-for-poland"></a>Zarządzanie informacjami dotyczącymi klienta (Polska)
---

tytuł: Zarządzanie informacjami dotyczącymi klienta (Polska) [!include [banner](../includes/banner.md)]
opis: W tym artykule opisano sposób obsługi informacji o klientach w programie Retail POS dla Polski.

author: josaw1

ms.data: 2021-09-21
## <a name="introduction"></a>Wprowadzenie
ms.topic: artykuł

ms.prod: W tym artykule opisano sposób obsługi informacji o odbiorcy, takich jak numer podatku VAT, w Retail Point of Sale (POS) dla Polski.
ms.technology: 

odbiorcy: Użytkownik Aplikacji Numer VAT odbiorcy można określić podczas tworzenia lub edytowania głównego rekordu odbiorcy w punkcie sprzedaży. Można także określić numer VAT dla transakcji sprzedaży, kopiując go z odbiorcy transakcji lub wprowadzając go ręcznie. Informacje dotyczące odbiorcy mogą być następnie drukowane zarówno na stałych, jak i fiskalnych przychodach i mogą być używane do celów fakturowania.
ms.reviewer: josaw

ms.search.region: Polska
> [!NOTE]
ms.author: josaw Nie można określić numeru VAT odbiorcy w POS, gdy w profilu funkcji POS włączono opcję **Tworzenie odbiorcy w trybie asynchronicznym**. Obsługę trybu tworzenia asynchronicznego odbiorcy można dodać w przyszłych aktualizacjach.
> ms.search.validFrom: 2019-11-11

ms.dyn365.ops.version: 10.0.7
## <a name="setup"></a>Konfiguracja
ms.search.industry: handel detaliczny

ms.search.form: RetailFunctionalityProfile, RetailParameters Aby korzystać z tej funkcji, należy wykonać następującą konfigurację:

---
- Ustawić typ rejestracji dla numeru VAT.

- Dodać operację **Dodaj informacje o kliencie** do układów ekranu.
### <a name="update-a-development-environment"></a>Aktualizacja środowiska projektowego
- Aktywować zapytanie dotyczące informacji o odbiorcy.

- Konfigurować format paragonu.
Aby zaktualizować środowisko programistyczne, należy wykonać następujące kroki.
- Konfiguracja składników kanału.


#### <a name="crt-extension-components"></a>CRT komponenty rozszerzenia
### <a name="set-up-a-registration-type-for-the-vat-number"></a>Ustawić typ rejestracji dla numeru VAT


1. Znajdź plik konfiguracyjny rozszerzenia dla środowiska wykonawczego Commerce runtime (CRT): Przed określeniem numerów VAT w POS należy utworzyć odpowiedni typ rejestracji numeru VAT i połączyć go z kategorią rejestracyjną **identyfikatora VAT ID**. Aby uzyskać więcej informacji na temat pracy z typami rejestracji i identyfikatorami rejestracji, przejrzyj [Identyfikatory rejestracji](../../finance/localizations/emea-registration-ids.md).


    - **Commerce Scale Unit:** znajdź plik **CommerceRuntime.Ext.config** w folderze **bin\\ext** w lokalizacji strony Microsoft Internet Information Services (IIS) Commerce Scale Unit site location.
> [!WARNING]
    - **Lokalne wystąpienie CRT na Modern POS:** znajdź plik **CommerceRuntime.MPOSOffline.Ext.config** w lokalizacji brokera lokalnego klienta CRT.
> Jeśli typ rejestracji nie zostanie utworzony lub nie jest połączony z kategorią rejestracji identyfikatorów **VAT ID**, w programie POS zostanie wygenerowany błąd, jeśli dla adresu odbiorcy zostanie wypełniony numer VAT.


1. Zarejestruj zmianę rozszerzenia CRT w pliku konfiguracji rozszerzenia.
### <a name="add-the-add-customer-information-operation-to-screen-layouts"></a>Dodaj operację Dodaj informacje o kliencie do układów ekranu


    ``` xml
Za pomocą operacji **Dodawania informacji o kliencie** można dodawać informacje o odbiorcy do transakcji sprzedaży, takie jak np. numer VAT. Te informacje można skopiować z odbiorcy określonego dla transakcji lub ręcznie wprowadzić.
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland" />

    ```
Na stronie **Siatki przycisków** wybierz siatkę przycisków, na której ma się pojawić operacja, a następnie otwórz Projektanta siatki przycisków. Dodaj nowy przycisk, nastepnie w polu **Działanie**, wybierz **Dodaj informacje o kliencie**. Aby uzyskać więcej informacji na temat pracy z układami ekranu i siatkami przycisków, należy zapoznać się z [Układami ekranu dla punkt sprzedaży (POS)](../pos-screen-layouts.md).


    > [!WARNING]
### <a name="activate-the-inquiry-for-customer-information"></a>Aktywuj zapytanie dotyczące informacji o odbiorcy
    > Do **not** edit the CommerceRuntime.config and CommerceRuntime.MPOSOffline.config files. These files aren't intended for any customizations.


Jeśli dla transakcji sprzedaży nie określono informacji o odbiorcy, prośba o te informacje może zostać wyzwolona automatycznie po sfinalizowaniu transakcji. Ta metoda jest alternatywą dla operacji **Dodawania informacji o odbiorcy**.
#### <a name="modern-pos-extension-components"></a>Komponenty rozszerzenia nowoczesnego POS


Aby aktywować zapytanie o informacje o kliencie, włącz funkcję **(Polska) Zarządzanie informacjami o kliencie w Retail POS** w obszarze roboczym **Zarządzanie funkcjami** i ustaw **Włącz zapytanie o informacje o kliencie w transakcjach sprzedaży** opcja do **Tak** w sekcji **Parametry podatkowe** na skróconej karcie **Funkcje** na stronie **Profile funkcji POS**.
Aby udostępnić rozszerzenie TaxRegistrationId.PL, należy wykonać następujące kroki.


### <a name="set-up-receipt-formats"></a>Konfiguracja formatów paragonu
1. Otwórz rozwiązanie w **RetailSdk\\POS\\ModernPOS.sln**.

1. W **POS.Extensions\\extensions.json**, włącz rozszerzenie.
Formaty paragonów można skonfigurować w taki sposób, aby numer VAT odbiorcy był na nich drukowany.


    ``` json
> [!NOTE]
    {
> The default company of the user who creates the receipt setup should be the same legal entity where the language text setup is created. Alternatively, the same language texts should be created in both the user's default company and the legal entity of the store that the setup is created for.
        "extensionPackages": [

            {
On the **Language text** page, on the **POS** tab, add the following record for the label of the custom field for receipt formats. Note that the **Language ID**, **Text ID**, and **Text** values that are shown in the following table are just examples. You can change them to meet your requirements. However, the **Text ID** value that you use must be unique, and it must be equal to or more than 900001.
                "baseUrl": "Microsoft/TaxRegistrationId.PL"

            }
| Language ID | Text ID | Text       |
        ]
|-------------|---------|------------|
    }
| en-US       | 900001  | VAT number |
    ```


Na stronie **Niestandardowe pola** dodaj następujący rekord dla pola niestandardowego w odniesieniu do formatów paragonów. Należy zauważyć, że wartość **identyfikatora tekstu podpisu** musi być zgodna z wartością **identyfikatora tekstu** podaną na **stronie tekstowej języka**.
1. Stwórz rozwiązanie.

1. Otwórz Modern POS i przetestuj te funkcje.
| Nazwa                      | Typ    | Identyfikator tekstu podpisu |

|---------------------------|---------|-----------------|
#### <a name="cloud-pos-extension-components"></a>Komponenty rozszerzenia Cloud POS
| FISCALCUSTOMER\_VATID\_PL | Paragon | 900001          |


Aby udostępnić rozszerzenie TaxRegistrationId.PL, należy wykonać następujące kroki.
W projektancie formatów paragonów dodaj pole niestandardowe do odpowiedniej sekcji paragonu dla każdego wymaganego formatu paragonu. Aby uzyskać więcej informacji o sposobie pracy z formatami paragonów, zobacz [Szablony paragonów i drukowanie](../receipt-templates-printing.md).


1. Otwórz rozwiązanie w **RetailSdk\\POS\\CloudPOS.sln**.
### <a name="configure-channel-components"></a>Konfiguracja składników kanału.
1. W **POS.Extensions\\extensions.json**, włącz rozszerzenie.


Aby udostępnić funkcje właściwe dla Polski, należy skonfigurować rozszerzenia dla składników kanału. Aby uzyskać więcej informacji, zobacz sekcję [Wskazówki dot. wdrożenia](#deployment-guidelines) w dalszej części tego artykułu.
    ``` json

    {
## <a name="example-scenarios"></a>Przykładowe scenariusze
        "extensionPackages": [

            {
Poniższe przykładowe scenariusze przedstawiają sposób pracy z informacjami o odbiorcach w POS dla Polski.
„baseUrl”: „Microsoft/TaxRegistrationId.PL”

            }
### <a name="scenario-1-make-a-sale-to-an-anonymous-customer"></a>Scenariusz 1: dokonać sprzedaży anonimowemu odbiorcy
        ]

    }
1. Zaloguj się w POS.
    ```
1. Add items to the cart.

1. Select **Add customer information**, and then select **Enter manually**.
1. Build the solution.
1. Enter the customer's VAT number, and then select **OK**.
1. Open Cloud POS, and test the functionality.
1. Register payments for the transaction, and then finalize the transaction.

1. Verify that the printed receipt contains the customer's VAT number.
### Update a production environment


### Scenario 2: Make a sale to a new named customer
Follow these steps to create deployable packages that contain Commerce components, and to apply the packages in a production environment.


1. Sign in to POS.
1. In the **CommerceRuntime.Ext.config** and **CommerceRuntime.MPOSOffline.Ext.config** configuration files under the **RetailSdk\\Assets** folder, add the following lines to the **composition** section.
1. Add items to the cart.

1. Select **Add customer**, and then select **New**.
    ``` xml
1. Specify the new customer's attributes.
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland" />
1. Select **Create a new address**. Then specify the new customer's contact information and an address.
    ```
1. W polu **Numer VAT** wprowadź numer VAT odbiorcy.

1. Zapisz rekord odbiorcy i rekord adresu odbiorcy, a następnie dodaj odbiorcę do transakcji.
1. Włącz rozszerzenie POS **TaxRegistrationId.PL**.
1. Zarejestruj płatności dla transakcji, a następnie zakończ transakcję.

1. Ponieważ zostało aktywowane zapytanie o informacje o odbiorcy, ale informacje o odbiorcy nie zostały dodane do transakcji, zostanie otwarte okno dialogowe **Wprowadź informacje o odbiorcy** . Wybierz opcję **Tak**, a następnie wybierz opcję **Kopiuj z odbiorcy transakcji**.
    ``` json
1. Verify the customer's VAT number, and then select **OK**.
    {
1. Verify that the printed receipt contains the customer's VAT number.
        "extensionPackages": [

            {
> [!NOTE]
                "baseUrl": "Microsoft/TaxRegistrationId.PL"
> If you must specify a different customer for the transaction, you must clear the customer information and then copy it again after the new customer is added.
            }

        ]
### Scenario 3: Change the customer information for a sale to a named customer
    }

    ```
1. Zaloguj się w POS.

1. Dodaj pozycje do koszyka.
1. Uruchom narzędzie **msbulid** dla całego zestawu Retail Software Development Kit (SDK), aby utworzyć pakiety do wdrożenia.
1. Wybierz **Dodaj odbiorcę**, a następnie wybierz konto odbiorcy i dodaj je do transakcji.
1. Zastosuj pakiety za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS) lub ręcznie. Aby uzyskać więcej informacji, zobacz [Pakiety Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
1. Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie wybierz opcję **Kopiuj z odbiorcy transakcji**.

1. Sprawdź numer VAT odbiorcy, a następnie kliknij przycisk **OK**.

1. Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie kliknij **Wyczyść**, aby wyczyścić informacje o odbiorcy z transakcji.
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
1. Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie wybierz **Wprowadź ręcznie**.
1. Podaj numer VAT odbiorcy, a następnie kliknij przycisk **OK**.
1. Zarejestruj płatności dla transakcji, a następnie zakończ transakcję.
1. Sprawdź, czy wydrukowany paragon zawiera numer VAT odbiorcy.

## <a name="deployment-guidelines"></a>Wskazówki dotyczące wdrażania

Ta sekcja zawiera wskazówki dotyczące wdrażania umożliwiające zarządzanie informacjami o klientach w lokalizacji Dynamics 365 Commerce dla Polski.

> [!NOTE]
> Niektóre kroki opisane w tych procedurach różnią się w zależności od używanej wersji produktu. Aby uzyskać więcej informacji, zobacz [Nowości i zmiany w rozwiązaniu Dynamics 365 for Retail](../get-started/whats-new.md).
>
> Jeśli chcesz włączyć integrację POS z drukarkami fiskalnymi w Polsce, a w szczególności, jeśli chcesz drukować numery podatku VAT od odbiorców na paragonach fiskalnych, musisz wdrożyć [próbkę integracji z drukarką fiskalną dla Polski](emea-pol-fpi-sample.md).

### <a name="update-customizations"></a>Dostosowanie aktualizacji

Aby zaktualizować dostosowania, wykonaj następujące kroki.

# <a name="retail-1007-and-later"></a>[Wersja 10.0.7 Retail i nowsze](#tab/retail-10-0-7)

Jeśli dowolne dostosowania zawierają obsługę żądań dla `SaveCartRequest` lub `CreateSalesOrderServiceRequest`:

1. Znajdź obsługę żądania `SaveCartRequest`.
1. Znajdź wiersz kodu, w którym jest uruchomiona oryginalna obsługa żądania.
1. Przed wywołaniem oryginalnego programu obsługi żądań dodaj następujące wiersze:

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland.Services;

    ...

    new TaxRegistrationIdFiscalCustomerService().Execute(request);
    ```

1. Znajdź obsługę żądania `CreateSalesOrderServiceRequest`.
1. Znajdź wiersz kodu, w którym jest uruchomiona oryginalna obsługa żądania.
1. Zamień ją na następujący kod:

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland.Services;

    ...

    return new TaxRegistrationIdFiscalCustomerService().Execute(request);
    ```

# <a name="retail-10012-and-later"></a>[Wersja 10.0.12 Retail i nowsze](#tab/retail-10-0-12)

Jeśli dostosowania mają odwołania do usługi `TaxRegistrationIdFiscalCustomerService`, muszą zostać usunięte.

---
