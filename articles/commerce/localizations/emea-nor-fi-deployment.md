---
title: Przewodniki wdrażania kas fiskalnych w Norwegii
description: Ten artykuł zawiera wskazówki dotyczące włączania funkcji kasy fiskalnej w lokalizacji Microsoft Dynamics 365 Commerce Norwegii.
author: EvgenyPopovMBS
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 9149e9da7222699e9ca996b69e56fff07b77a737
ms.sourcegitcommit: 1dbff0b5fa1f4722a1720fac35cce94606fa4320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2022
ms.locfileid: "9345999"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway"></a>Przewodniki wdrażania kas fiskalnych w Norwegii

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Kroki opisane w tym artykule należy zaimplementować tylko w przypadku korzystania z wersji Microsoft Dynamics 365 Commerce 10.0.29 lub późniejsze. W wersji Commerce 10.0.28 lub wcześniejszej musisz użyć poprzedniej wersji zestawu SDK do Retail na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania kas fiskalnych dla Norwegii (starsza wersja)](./emea-nor-loc-deployment-guidelines.md). Jeśli korzystasz z wersji Commerce 10.0.28 lub starszej i migrujesz do wersji Commerce 10.0.29 lub nowszej, musisz wykonać kroki w tecie [Migracja ze starszej wersji Commerce dla Norway](./emea-nor-fi-migration.md).

Ten artykuł zawiera wskazówki dotyczące włączania funkcji kasy fiskalnej w lokalizacji Commerce dla Norwegii. Lokalizacja składa się z kilku rozszerzeń składników, które umożliwiają wykonywanie takich akcji, jak drukowanie niestandardowych pól na paragonach, rejestrowanie dodatkowych zdarzeń inspekcji, transakcji sprzedaży i transakcji płatności w programie punkt sprzedaży (POS), cyfrowe podpisywanie transakcji sprzedaży i drukowanie raportów w formatach lokalnych. Aby uzyskać więcej informacji o lokalizacji dla Norwegii, zobacz temat [Funkcje kas fiskalnych dla Norwegii](./emea-nor-cash-registers.md). Aby uzyskać informacje dotyczące konfigurowania rozwiązania Commerce dla Norwegii, patrz [Konfiguracja rozwiązania Commerce dla Norwegii](./emea-nor-cash-registers.md#setting-up-commerce-for-norway).

## <a name="set-up-fiscal-registration-for-norway"></a>Konfiguracja procesu rejestracji fiskalnej dla Norwegii

Przykład rejestracji fiskalnej dla Norwegii jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu SDK do Commerce. Próbka znajduje się w folderze **src\\FiscalIntegration\\SequentialSignatureNorway** w repozytorium [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). [Przykład](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) składa się z dostawcy dokumentów fiskalnych i łącznika fiskalnego, które są rozszerzeniami środowiska uruchomieniowego Commerce Runtime (CRT). Aby uzyskać więcej informacji dotyczących sposobu używania zestawu SDK do Commerce, zobacz [Pobieranie próbek i pakietów referencyjnych zestawu SDK do Retail z GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md) i [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

Wykonaj kroki konfiguracji rejestracji fiskalnej w sposób opisany w [Konfiguracja integracji fiskalnej dla kanałów Commerce](./setting-up-fiscal-integration-for-retail-channel.md):

1. [Konfigurowanie procesu rejestracji fiskalnej](./setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Pamiętaj, aby zanotować ustawienia procesu rejestracji fiskalnej, które są [specyficzne dla](#configure-the-fiscal-registration-process) Norwegii.
1. [Określanie ustawienia ustawień obsługi błędów](./setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Konfiguracja składników kanału](#configure-channel-components).

### <a name="configure-the-fiscal-registration-process"></a>Konfiguracja procesu rejestracji fiskalnej

Aby włączyć proces rejestracji fiskalnej centrali w rozwiązaniu Commerce dla Norwegii, wykonaj następujące kroki.

1. Pobierz pliki konfiguracji dla dostawcy dokumentów fiskalnych i łącznika fiskalnego z zestawu Commerce SDK:

    1. Otwórz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Otwórz ostatnią dostępną gałąź wydania.
    1. Otwórz **src \> FiscalIntegration \> SequentialSignatureNorway \> CommerceRuntime**.
    1. Pobierz plik konfiguracji dostawcy dokumentów fiskalnych z **DocumentProvider.SequentialSignNorway \> Konfiguracja \> DocumentProviderSequentialSignatureNorwaySample.xml**.
    1. Pobierz plik konfiguracji łącznika fiskalnego z lokalizacji konfiguracji **Connector.SequentialSignNorway \> Konfiguracja \> ConnectorSequentialSignatureNorwaySample.xml**.

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry współdzielone**. Na karcie **Ogólne** ustaw dla opcji **Włącz integrację fiskalną** wartość **Tak**.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Łączniki fiskalne** i załaduj pobrany wcześniej plik konfiguracji łącznika fiskalnego.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Dostawcy dokumentów fiskalnych** i załaduj pobrany wcześniej plik konfiguracji dostawcy dokumentów fiskalnych.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile funkcjonalności łącznika**. Utwórz nowy profil funkcji łącznika i wybierz dostawcę dokumentów i łącznik załadowany w poprzednich krokach.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile techniczne łącznika**. Utwórz nowy profil techniczny łącznika i wybierz załadowany wcześniej łącznik. Ustaw typ łącznika na **Wewnętrzny**.
1. Przejdź do **Retail i Commerce \> Konfiguracja kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**, i utwórz nową grupę łączników fiskalnych dla profilu funkcji łącznika utworzonego wcześniej.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnej**. Utwórz nowy proces rejestracji fiskalnej oraz krok procesu rejestracji fiskalnej, a następnie wybierz utworzoną wcześniej grupę łączników fiskalnych.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**. Wybierz profil funkcjonalności połączony ze sklepem, w którym należy aktywować proces rejestracji. Na skróconej karcie **Proces rejestracji fiskalnej** wybierz utworzony wcześniej proces rejestracji fiskalnej. Na skróconej karcie **Usługi fiskalne** wybierz utworzony wcześniej profil techniczny łącznika. 
1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**. Otwórz harmonogram dystrybucji i wybierz zadanie **1070** i **1090**, aby przenieść dane do bazy danych kanału.

### <a name="configure-the-digital-signature-parameters"></a>Konfiguracja parametrów podpisu cyfrowego

Należy skonfigurować certyfikaty, które będą używane do cyfrowego podpisywania transakcji sprzedaży w sklepie. Do podpisywania stosowany jest certyfikat cyfrowy przechowywany w Azure Key Vault. W przypadku trybu offline programu Modern POS podpisywanie można również wykonać za pomocą certyfikatu cyfrowego przechowywanego w magazynie lokalnym komputera, na którym jest zainstalowany program Modern POS.

Przed użyciem certyfikatu cyfrowego zapisanego w magazynie Key Vault należy wykonać następujące kroki.

1. Należy utworzyć magazyn Key Vault. Zalecane jest wdrożenie magazynu w tym samym obszarze geograficznym co jednostka skalowania Commerce Scale Unit.
1. Certyfikat musi zostać przekazany do magazynu Key Vault w postaci ciągu tajnego base64.
1. Aplikacja Application Object Server (AOS) musi mieć autoryzację do odczytu danych z magazynu Key Vault.

Aby uzyskać więcej informacji na temat pracy z Key Vault, zobacz temat [Wprowadzenie do Azure Key Vault](/azure/key-vault/key-vault-get-started).

Następnie na stronie **Parametry Key Vault** należy określić parametry uzyskiwania dostępu do magazynu Key Vault:

- **Nazwa** i **Opis** – nazwa i opis magazynu Key Vault.
- **Key Vault URL** – adres URL magazynu Key Vault.
- **Klient usługi Key Vault** – interaktywny identyfikator klienta aplikacji Azure Active Directory (Azure AD) powiązany z magazynem Key Vault w celu uwierzytelnienia. Ten klient powinien mieć dostęp do odczytu z magazynu.
- **Tajny klucz Key Vault** – tajny klucz skojarzony z aplikacją Azure AD, stosowany do uwierzytelniania w magazynie Key Vault.
- **Nazwa**, **opis**, i **tajne odwołanie** – nazwa, opis i tajne odwołanie certyfikatu.

Następnie należy skonfigurować łącznik dla certyfikatów przechowywanych w magazynie Key Vault lub magazynie certyfikatów lokalnych. Ten łącznik jest używany do podpisywania po stronie kanału.

1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile techniczne łącznika**.
1. Na skróconej karcie **Ustawienia** określ następujące parametry podpisów cyfrowych:

    - **Tajna nazwa** – umożliwia wybór tajnej nazwy skonfigurowanej wcześniej na stronie **Parametry Key Vault**.
    - **Odcisk palca certyfikatu lokalnego** – zapewnia odcisk palca certyfikatu, który jest przechowywany lokalnie.
    - **Algorytm wyznaczania wartości skrótu** – umożliwia określenie jednego z algorytmów skrótów kryptograficznych, które są obsługiwane przez Microsoft .NET, na przykład **SHA1**.
    - **Nazwa magazynu certyfikatów** – to pole jest opcjonalne. Za jego pomocą można określić domyślną nazwę sklepu, która powinna być używana do wyszukiwania certyfikatów lokalnych.
    - **Lokalizacja magazynu certyfikatów** – to pole jest opcjonalne. Za jego pomocą można określić domyślną lokalizację sklepu, która powinna być używana do wyszukiwania certyfikatów lokalnych.
    - **Najpierw wypróbuj certyfikat lokalny** – wybierz tę opcję, aby domyślnie używać certyfikatu z lokalnego sklepu do podpisywania danych, a nie certyfikatu z Key Vault.
    - **Aktywuj sprawdzanie kondycji** – Aby uzyskać więcej informacji dotyczących procedury sprawdzania kondycji, patrz [Sprawdzanie kondycji rejestracji fiskalnej](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

> [!NOTE]
> - W Norwegii można obecnie akceptować tylko algorytm skrótu kryptograficznego **SHA1**.
> - Domyślna nazwa sklepu i lokalizacja sklepu są dodawane w celu uproszczenia procesu wyszukiwania lokalnych certyfikatów w środowisku CRT. X509StoreProvider zawiera listę folderów, w których są przechowywane certyfikaty. Jeśli nie określono domyślnej nazwy i lokalizacji sklepu, X509StoreProvider próbuje znaleźć certyfikat we wszystkich folderach na liście.

### <a name="configure-channel-components"></a>Konfiguracja składników kanału.

#### <a name="development-environment"></a>Środowiska programistyczne

Wykonaj poniższe kroki, aby skonfigurować środowisko projektowe, co umożliwi testowanie i rozszerzanie przykładu.

1. Sklonuj lub pobierz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions). Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji. Aby uzyskać więcej informacji, zobacz [Pobieranie przykładów i pakietów referencyjnych zestawu SDK do Commerce z witryn GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Otwórz rozwiązanie **SequentialSignatureNorway.sln** w lokalizacji **Dynamics365Commerce.Solutions\\FiscalIntegration\\SequentialSignatureNorway**, i skompiluj je.
1. Zainstaluj rozszerzenia kolekcji CRT:

    1. Znajdź instalatora rozszerzeń kolekcji CRT:

        - **Commerce Scale Unit:** znajdź w folderze **SequentialSignatureNorway\\ScaleUnit\\ScaleUnit.SequentialSignNorway.Installer\\bin\\Debug\\net461** instalatora **ScaleUnit.SequentialSignNorway.Installer**.
        - **Lokalny CRT w aplikacji Modern POS:** znajdź w folderze **SequentialSignatureNorway\\ModernPOS\\ModernPos.SequentialSignNorway.Installer\\bin\\Debug\\net461** instalatora **ModernPos.SequentialSignNorway.Installer**.

    1. Uruchom instalatora rozszerzeń kolekcji CRT z poziomu wiersza polecenia:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

        - **Lokalna kolekcja CRT w aplikacji Modern POS:**

            ```Console
            ModernPOS.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Środowisko produkcyjne

Wykonaj kroki opisane w artykule [Konfigurowanie potoku kompilacji dla przykładu integracji fiskalnej](fiscal-integration-sample-build-pipeline.md), aby wygenerować i wydać rozwiązanie Cloud Scale Unit oraz samoobsługowe wdrażalne pakiety dla przykładu integracji fiskalnej. Plik YAML szablonu **SequentialSignatureNorway build-pipeline.yaml** można znaleźć w folderze **Pipeline\\YAML_Files** repozytorium [rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Włączanie podpisu cyfrowego w trybie offline dla aplikacji Modern POS

Aby włączyć podpis cyfrowy w trybie offline dla aplikacji Modern POS, po uaktywnieniu aplikacji Modern POS na nowym urządzeniu należy wykonać następujące kroki.

1. Zaloguj się w POS.
1. Na stronie **Stan połączenia z bazą danych** upewnij się, że baza danych w trybie offline jest w pełni zsynchronizowana. Gdy wartość pola **Oczekujące pobrania** wynosi **0** (zero), baza danych jest w pełni zsynchronizowana.
1. Wyloguj się z punktu sprzedaży.
1. Poczekaj na pełną synchronizację bazy danych offline.
1. Zaloguj się w POS.
1. Na stronie **Stan połączenia z bazą danych** upewnij się, że baza danych w trybie offline jest w pełni zsynchronizowana. Gdy wartość pola **Oczekujące transakcje w bazie danych offline** wynosi **0** (zero), baza danych jest w pełni zsynchronizowana.
1. Otwórz ponownie system Modern POS.
