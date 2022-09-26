---
title: Profile certyfikatów zdefiniowane przez użytkownika dla sklepów detalicznych
description: Ten artykuł zawiera omówienie funkcji profili certyfikatów dostępnych w programie Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: v-chgriffin
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.search.industry: Retail
ms.search.form: RetailFormLayout, RetailParameters
ms.openlocfilehash: 5baf043a43210d819b605546089e981c86922ca9
ms.sourcegitcommit: 4f28f262cfb8f047cb5c0070261aa0748835e74b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2022
ms.locfileid: "9558445"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Profile certyfikatów zdefiniowane przez użytkownika dla sklepów detalicznych

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie funkcji profili certyfikatów dostępnych w programie Microsoft Dynamics 365 Commerce. Ta funkcja rozszerza funkcję [zarządzania wpisami tajnymi dla kanałów detalicznych](../dev-itpro/manage-secrets.md), dodając obsługę certyfikatów lokalnych.

Gdy punkt sprzedaży (POS) działa w trybie offline, nie może uzyskać dostępu do certyfikatów przechowywanych w magazynie Microsoft Azure Key Vault. Zamiast tego należy użyć certyfikatu lokalnego. Obsługiwane są następujące możliwości:

- Używanie certyfikatów lokalnych w scenariuszach rezerwowych magazynu Key Vault
- Korzystanie z lokalnych certyfikatów bez magazynu Key Vault (na przykład w przypadku instalacji lokalnej)
- Aktualizacja stopniowa certyfikatów, w której niektóre sklepy i terminale korzystają z nowej wersji certyfikatu, ale inne sklepy i terminale używają poprzedniej wersji

Funkcja profilów certyfikatów umożliwia określenie certyfikatu domyślnego i ustawienie kolejności wyszukiwania certyfikatów w tym samym profilu certyfikatów. Ta funkcja zapewnia podobne podejście do konfiguracji certyfikatów lokalnych i certyfikatów magazynu kluczy. Można dodawać specyficzne dla firmy ustawienia certyfikatów, ale unikatowy identyfikator międzyfirmowy dla każdego certyfikatu może być używany w międzyfirmowych kanałach Commerce.

### <a name="scenarios"></a>Scenariusze

Funkcja profili certyfikatów obsługuje następujące scenariusze w kanałach modułu Commerce:

- Użyj certyfikatu lokalnego w scenariuszach rezerwowych magazynu Key Vault. Oto kilka scenariuszy rezerwowych:

    - Miejsce przechowywania magazynu kluczy jest niedostępne.
    - Nie znaleziono certyfikatu w miejscu przechowywania magazynu kluczy.
    - Punkt sprzedaży działa w trybie offline.

- Użyj lokalnych certyfikatów bez zapisywania ich w magazynie Key Vault (na przykład w przypadku instalacji lokalnej).
- Wykonaj aktualizację stopniową certyfikatów, gdzie nowa wersja certyfikatu jest używana tylko w sklepach lub w terminalach, w których jest już dostępna.
- Użyj tego samego certyfikatu stosować w kilku firmach.

## <a name="set-up-certificate-profiles"></a>Konfigurowanie profili certyfikatów

Poniższa procedura wyjaśnia sposób konfigurowania profili certyfikatów.

### <a name="set-up-key-vault"></a>Ustawianie magazynu Key Vault

Przed użyciem certyfikatu cyfrowego zapisanego w magazynie Key Vault należy wykonać następujące kroki.

1. Tworzenie konta magazynu Key Vault Zalecane jest wdrożenie konta magazynu w tym samym obszarze geograficznym co jednostka skalowania Commerce Scale Unit.
1. Przekazanie certyfikatu cyfrowego do konta magazynu Key Vault.
1. Autoryzacja aplikacji Application Object Server (AOS) do odczytu danych z konta magazynu Key Vault.

Aby uzyskać więcej informacji na temat pracy z Key Vault, zobacz temat [Wprowadzenie do Azure Key Vault](/azure/key-vault/key-vault-get-started).

### <a name="set-up-system-parameters"></a>Konfigurowanie parametrów systemowych

Przed skonfigurowaniem profilów certyfikatów w kanałach rozwiązania Commerce należy włączyć funkcję Commerce do używania obu certyfikatów, które są przechowywane w magazynie Key Vault i profilach certyfikatów.

Aby skonfigurować parametry systemu w centrali Commerce headquarters, wykonaj kroki opisane poniżej.

1. Na stronie **Parametry systemu** ustaw wartość **Tak** w opcji **Użyj zaawansowanego magazynu certyfikatów**.
1. W obszarze roboczym **Zarządzanie funkcjami** włącz funkcję **Zdefiniowane przez użytkownika profile certyfikatów dla sklepów detalicznych**.

### <a name="set-up-key-vault-parameters"></a>Ustawianie parametrów usługi Key Vault

Na stronie **Parametry Key Vault** należy określić następujące parametry uzyskiwania dostępu do magazynu Key Vault:

- **Nazwa** i **Opis** — nazwa i opis konta magazynu Key Vault.
- **Adres URL magazynu Key Vault URL** — adres URL konta magazynu Key Vault.
- **Klient usługi Key Vault** — interaktywny identyfikator klienta aplikacji Azure Active Directory (Azure AD) powiązany z kontem magazynu Key Vault w celu uwierzytelnienia. Ten klient powinien mieć dostęp do odczytu z konta magazynu.
- **Tajny klucz Key Vault** — klucz tajny skojarzony z aplikacją Azure AD, stosowany do uwierzytelniania na koncie magazynu Key Vault.
- **Nazwa**, **opis**, i **tajne odwołanie** – nazwa, opis i tajne odwołanie certyfikatu.

Aby uzyskać więcej informacji, przejrzyj temat [Konfigurowanie klienta usługi Azure Key Vault](../../finance/localizations/setting-up-azure-key-vault-client.md).

### <a name="configure-a-certificate-profile"></a>Konfigurowanie profilu certyfikatu

Aby skonfigurować profil certyfikatów w centrali Commerce headquarters, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Profile certyfikatów**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć nowy rekord.
1. Wprowadź wartości w polach **Profil certyfikatów**, **Nazwa** i **Opis**.

    > [!NOTE]
    > Profil certyfikatu jest unikatowym identyfikatorem certyfikatu we wszystkich firmach i składnikach modułu Commerce.

1. Na skróconej karcie **Osoby prawne**, wybierz opcję **Dodaj**, by dodać wiersz.
1. Na karcie **Osoba prawna** dodaj wiersz i wybierz osobę prawną (firmę), dla której ma być używany bieżący profil certyfikatu.

    Jeśli profil certyfikatu ma być używany w wielu firmach, powtórz krok 4 i 5, aby dodać wiersz dla każdej dodatkowej osoby prawnej.

1. Wybierz opcję **Ustawienia**, aby otworzyć stronę **Ustawienia profilu certyfikatu**, na której możesz wprowadzić specyficzne dla firmy ustawienia profilu certyfikatu. Określ, które certyfikaty mogą być używane podczas wywoływania bieżącego profilu certyfikatu w kanałach modułu Commerce. Dodaj tyle certyfikatów, ile to konieczne, i ustaw dla nich priorytety. Jeśli nie jest dostępny certyfikat o wyższym priorytecie, następny certyfikat będzie używany na podstawie priorytetu. Aby uzyskać więcej informacji, zobacz sekcję [Przepływ pracy: wyszukiwanie certyfikatów w środowisku uruchomieniowym Commerce Runtime](#workflow-searching-certificates-in-the-commerce-runtime).

    > [!NOTE]
    > Pole **Priorytet** jest ustawiane automatycznie. Wartość **1** oznacza najwyższy priorytet. Po dodaniu nowego wiersza na stronie **Ustawienia profilu certyfikatu** jego priorytet jest ustawiany na liczbę o jeden większą niż priorytet poprzedniego wiersza. Aby zmienić priorytet określonego wiersza, zaznacz wiersz, a następnie wybierz opcję **Przenieś w górę** w celu zwiększenia priorytetu lub przycisk **Przenieś w dół**, w celu zmniejszenia priorytetu.

1. Po dodaniu nowego wiersza na stronie **Ustawienia profilu certyfikatu** podaj informacje w następujących polach:

    - **Typ lokalizacji** — wybierz lokalizację, w której jest przechowywany dany certyfikat. To pole ma dwie możliwe wartości: **Certyfikat lokalny** i **Magazyn kluczy**.
    - **Certyfikat magazynu kluczy** — to pole jest wymagane w przypadku ustawienia pola **Typ lokalizacji** na **Magazyn kluczy**. Za jego pomocą można określić wpis tajny certyfikatu magazynu kluczy.
    - **Nazwa sklepu** — to pole jest opcjonalne i dostępne tylko w przypadku ustawienia pola **Typ lokalizacji** na **Certyfikat lokalny**. Za jego pomocą można określić domyślną nazwę sklepu, która powinna być używana do wyszukiwania certyfikatów lokalnych.
    - **Nazwa lokalizacji** — to pole jest opcjonalne i dostępne tylko w przypadku ustawienia pola **Typ lokalizacji** na **Certyfikat lokalny**. Za jego pomocą można określić domyślną lokalizację sklepu, która powinna być używana do wyszukiwania certyfikatów lokalnych.

        > [!NOTE]
        > Domyślna nazwa sklepu i lokalizacja sklepu są dodawane w celu uproszczenia procesu wyszukiwania lokalnych certyfikatów w środowisku uruchomieniowym Commerce Runtime. X509StoreProvider zawiera listę folderów, w których są przechowywane certyfikaty. Jeśli nie określono domyślnej nazwy i lokalizacji sklepu, X509StoreProvider próbuje znaleźć certyfikat w innych folderach na liście. Aby uzyskać więcej informacji dotyczących dostępnych wartości dla nazwy i lokalizacji sklepu, zobacz [Wyliczenie StoreName](/dotnet/api/system.security.cryptography.x509certificates.storename) i [Wyliczenie StoreLocation](//dotnet/api/system.security.cryptography.x509certificates.storelocation).

    - **Odcisk palca** — to pole jest wymagane i jest dostępne tylko w przypadku ustawienia pola **Typ lokalizacji** na **Certyfikat lokalny**. Za jego pomocą można określić odcisk palca certyfikatu.

        > [!IMPORTANT]
        > Musisz upewnić się, że użytkownik, który uruchomi aplikację, który musi używać certyfikatu lokalnego (na przykład Modern POS w trybie offline), ma co najmniej dostęp do klucza prywatnego certyfikatu tylko do odczytu.

    - **Komentarze** — to pole jest opcjonalne i umożliwia użytkownikom wprowadzanie notatek.

## <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Przepływ pracy: wyszukiwanie certyfikatów w środowisku uruchomieniowym Commerce Runtime

Poniżej znajduje się podstawowy przepływ pracy służący do wyszukiwania certyfikatu, gdy profil certyfikatu jest wywoływany w środowisku uruchomieniowym Commerce Runtime.

1. System określa, czy profil certyfikatów ma specyficzne dla firmy ustawienia dotyczące bieżącej firmy.
1. System próbuje znaleźć certyfikat za pomocą wartości na stronie **Ustawienia profilu certyfikatu** dla wiersza, w którym pole **Priorytet** ma wartość **1**.

    - Jeśli pole **Typ lokalizacji** jest ustawione na **Magazyn kluczy**, wartość pola **Wpis tajny magazynu kluczy** jest używana do wyszukiwania certyfikatu na stronie **Parametry magazynu kluczy**. Certyfikat jest następnie wyszukiwany w miejscu przechowywania magazynu kluczy.
    - Jeśli pole **Typ lokalizacji** jest ustawione na **Certyfikat lokalny**, X509StoreProvider najpierw szuka certyfikatu przy użyciu domyślnej nazwy i lokalizacji sklepu, jeśli te parametry są określone. Następnie są przeszukiwane wszystkie inne foldery na liście folderów.

1. Jeśli certyfikat nie zostanie znaleziony, proces jest powtarzany dla wiersza, w którym pole **Priorytet** ma wartość **2** itd.

> [!NOTE]
> Jeśli profil certyfikatu nie ma ustawień dla bieżącej firmy lub jeśli wyszukiwanie certyfikatu nie powiedzie się dla wszystkich wierszy na stronie **Ustawienia profilu certyfikatu**, certyfikat nie zostanie znaleziony.

### <a name="caching-the-results-of-certificate-searches"></a>Buforowanie wyników wyszukiwań certyfikatów

Wyniki wyszukiwań certyfikatów są buforowane. Domyślny okres ważności pamięci podręcznej to jedna godzina. Czas ten można jednak dostosować i można go ustawić maksymalnie na 24 godziny.

## <a name="gradual-update"></a>Aktualizacja stopniowa

Jeśli zostanie wprowadzona nowa wersja certyfikatu, ale nie można jej aktualizować jednocześnie we wszystkich sklepach, profile certyfikatów umożliwiają stopniowe aktualizowanie certyfikatu.

1. Znajdź profil certyfikatu i wiersz, które powinny zostać zaktualizowane, a następnie wybierz **Ustawienia**.
1. Dodaj wiersz i określ ustawienia związane z najnowszą wersją certyfikatu.
1. Zwiększ wartość opcji **Priorytet** nowego wiersza. Użyj przycisku **Przenieś w górę** w celu przeniesienia wiersza w taki sposób, aby był umieszczony powyżej wiersza dla poprzedniej wersji tego samego certyfikatu.
> [!NOTE]
> W środowisku uruchomieniowym Commerce Runtime nowa wersja certyfikatu zostanie wywołana jako pierwsza. Jeśli certyfikat nie został jeszcze zaktualizowany w określonym sklepie lub na określonym terminalu, zostanie wywołana poprzednia wersja.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
