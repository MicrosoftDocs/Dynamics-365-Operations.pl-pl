---
title: Profile certyfikatów zdefiniowane przez użytkownika dla sklepów detalicznych
description: Ten temat zawiera omówienie sposobu używania certyfikatów w sklepach detalicznych.
author: josaw
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0b8bf49a8eb78d0557ef105b40dd4cb5f0d24ce4
ms.sourcegitcommit: 83ec80382bfeb693d5c5949b6f65296bd50eed12
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973940"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Profile certyfikatów zdefiniowane przez użytkownika dla sklepów detalicznych

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

## <a name="overview"></a>Omówienie

Ten temat zawiera omówienie funkcji profili certyfikatów dostępnych w programie Microsoft Dynamics 365 Commerce. Ta funkcja rozszerza funkcję [zarządzania wpisami tajnymi dla kanałów detalicznych](../dev-itpro/manage-secrets.md), dodając obsługę certyfikatów lokalnych.

Gdy punkt sprzedaży (POS) działa w trybie offline, nie może uzyskać dostępu do certyfikatów przechowywanych w magazynie kluczy. Zamiast tego należy użyć certyfikatu lokalnego. Obsługiwane są następujące możliwości:

- Używanie certyfikatów lokalnych w scenariuszach rezerwowych magazynu kluczy
- Korzystanie z lokalnych certyfikatów bez magazynu kluczy (na przykład w przypadku instalacji lokalnej)
- Aktualizacja stopniowa certyfikatów, w której niektóre sklepy i terminale korzystają z nowej wersji certyfikatu, ale inne sklepy i terminale używają poprzedniej wersji

Funkcja profilów certyfikatów umożliwia określenie certyfikatu domyślnego i ustawienie kolejności wyszukiwania certyfikatów w tym samym profilu certyfikatów. Ta funkcja zapewnia podobne podejście do konfiguracji certyfikatów lokalnych i certyfikatów magazynu kluczy. Można dodawać specyficzne dla firmy ustawienia certyfikatów, ale unikatowy identyfikator międzyfirmowy dla każdego certyfikatu może być używany w międzyfirmowych kanałach Commerce.

### <a name="scenarios"></a>Scenariusze

Funkcja profili certyfikatów obsługuje następujące scenariusze w kanałach modułu Commerce:

- Użyj certyfikatu lokalnego w scenariuszach rezerwowych magazynu kluczy. Oto kilka scenariuszy rezerwowych:

    - Miejsce przechowywania magazynu kluczy jest niedostępne.
    - Nie znaleziono certyfikatu w miejscu przechowywania magazynu kluczy.
    - Punkt sprzedaży działa w trybie offline.

- Użyj lokalnych certyfikatów bez zapisywania ich w magazynie kluczy (na przykład w przypadku instalacji lokalnej).
- Wykonaj aktualizację stopniową certyfikatów, gdzie nowa wersja certyfikatu jest używana tylko w sklepach lub w terminalach, w których jest już dostępna.
- Użyj tego samego certyfikatu stosować w kilku firmach.

## <a name="set-up-certificate-profiles"></a>Konfigurowanie profili certyfikatów

Poniższa procedura wyjaśnia sposób konfigurowania profili certyfikatów. Przed użyciem profili certyfikatów w kanałach Commerce należy wykonać poniższe kroki, aby skonfigurować ustawienia.

1. W obszarze roboczym **Zarządzanie funkcjami** włącz funkcję **Zdefiniowane przez użytkownika profile certyfikatów dla sklepów detalicznych**.
2. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Profile certyfikatów**.
3. Utwórz rekord i podaj wartości w polach **Profil certyfikatu**, **Nazwa** i **Opis**.

    > [!NOTE]
    > Profil certyfikatu jest unikatowym identyfikatorem certyfikatu we wszystkich firmach i składnikach modułu Commerce.

3. Na karcie **Firmy** dodaj wiersz i wybierz firmę, dla której ma być używany bieżący profil certyfikatu. Jeśli profil certyfikatu ma być używany w wielu firmach, powtórz ten krok, aby dodać wiersz dla każdej dodatkowej firmy.
4. Wybierz opcję **Ustawienia**, aby otworzyć stronę **Ustawienia profilu certyfikatu**, na której możesz wprowadzić specyficzne dla firmy ustawienia profilu certyfikatu.

### <a name="certificate-profile-settings"></a>Ustawienia profilu certyfikatu

Po wybraniu opcji **Ustawienia** wierszy profilu certyfikatu zostanie wyświetlona strona **Ustawienia profilu certyfikatu**. Ta strona umożliwia określenie, które certyfikaty mogą być używane podczas wywoływania bieżącego profilu certyfikatu w kanałach modułu Commerce. Możesz również określić kolejność, w jakiej certyfikaty powinny być przeszukiwane.

> [!NOTE]
> Pole **Priorytet** jest ustawiane automatycznie. Wartość **1** oznacza najwyższy priorytet. Po dodaniu nowego wiersza na stronie **Ustawienia profilu certyfikatu** jego priorytet jest ustawiany na liczbę o jeden większą niż priorytet poprzedniego wiersza. Aby zmienić priorytet określonego wiersza, zaznacz wiersz, a następnie wybierz opcję **Przenieś w górę** w celu zwiększenia priorytetu lub przycisk **Przenieś w dół**, w celu zmniejszenia priorytetu.

Po dodaniu nowego wiersza do strony **Ustawienia profilu certyfikatu** podaj informacje w następujących polach:

- **Typ lokalizacji** — wybierz lokalizację, w której jest przechowywany dany certyfikat. To pole ma dwie możliwe wartości: **Certyfikat lokalny** i **Magazyn kluczy**.
- **Certyfikat magazynu kluczy** — to pole jest wymagane w przypadku ustawienia pola **Typ lokalizacji** na **Magazyn kluczy**. Za jego pomocą można określić wpis tajny certyfikatu magazynu kluczy.

    > [!NOTE]
    > Przed użyciem certyfikatu magazynu kluczy w profilach certyfikatów należy przekazać certyfikat do miejsca przechowywania magazynu kluczy, a następnie postępować zgodnie z instrukcjami w obszarze [Konfigurowanie klienta magazynu kluczy systemu Azure](https://docs.microsoft.com/dynamics365/finance/localizations/setting-up-azure-key-vault-client).

- **Nazwa sklepu** — to pole jest opcjonalne i dostępne tylko w przypadku ustawienia pola **Typ lokalizacji** na **Certyfikat lokalny**. Za jego pomocą można określić domyślną nazwę sklepu, która powinna być używana do wyszukiwania certyfikatów lokalnych.
- **Nazwa lokalizacji** — to pole jest opcjonalne i dostępne tylko w przypadku ustawienia pola **Typ lokalizacji** na **Certyfikat lokalny**. Za jego pomocą można określić domyślną lokalizację sklepu, która powinna być używana do wyszukiwania certyfikatów lokalnych.

    > [!NOTE]
    > Domyślna nazwa sklepu i lokalizacja sklepu są dodawane w celu uproszczenia procesu wyszukiwania lokalnych certyfikatów w środowisku uruchomieniowym Commerce Runtime. X509StoreProvider zawiera listę folderów, w których są przechowywane certyfikaty. Jeśli nie określono domyślnej nazwy i lokalizacji sklepu, X509StoreProvider próbuje znaleźć certyfikat w innych folderach na liście.

- **Odcisk palca** — to pole jest wymagane i dostępne tylko w przypadku ustawienia pola **Typ lokalizacji** na **Certyfikat lokalny**. Za jego pomocą można określić odcisk palca certyfikatu.
- **Komentarze** — to pole jest opcjonalne i umożliwia użytkownikom wprowadzanie notatek.

### <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Przepływ pracy: wyszukiwanie certyfikatów w środowisku uruchomieniowym Commerce Runtime

Poniżej znajduje się podstawowy przepływ pracy służący do wyszukiwania certyfikatu, gdy profil certyfikatu jest wywoływany w środowisku uruchomieniowym Commerce Runtime.

1. System określa, czy profil certyfikatów ma specyficzne dla firmy ustawienia dotyczące bieżącej firmy.
1. System próbuje znaleźć certyfikat za pomocą wartości na stronie **Ustawienia profilu certyfikatu** dla wiersza, w którym pole **Priorytet** ma wartość **1**.

    - Jeśli pole **Typ lokalizacji** jest ustawione na **Magazyn kluczy**, wartość pola **Wpis tajny magazynu kluczy** jest używana do wyszukiwania certyfikatu na stronie **Parametry magazynu kluczy**. Certyfikat jest następnie wyszukiwany w miejscu przechowywania magazynu kluczy.
    - Jeśli pole **Typ lokalizacji** jest ustawione na **Certyfikat lokalny**, X509StoreProvider najpierw szuka certyfikatu przy użyciu domyślnej nazwy i lokalizacji sklepu, jeśli te parametry są określone. Następnie są przeszukiwane wszystkie inne foldery na liście folderów.

1. Jeśli certyfikat nie zostanie znaleziony, proces jest powtarzany dla wiersza, w którym pole **Priorytet** ma wartość **2** itd.

> [!NOTE]
> Jeśli profil certyfikatu nie ma ustawień dla bieżącej firmy lub jeśli wyszukiwanie certyfikatu nie powiedzie się dla wszystkich wierszy na stronie **Ustawienia profilu certyfikatu**, certyfikat nie zostanie znaleziony.

#### <a name="caching-the-results-of-certificate-searches"></a>Buforowanie wyników wyszukiwań certyfikatów

Wyniki wyszukiwań certyfikatów są buforowane. Domyślny okres ważności pamięci podręcznej to jedna godzina. Czas ten można jednak dostosować i można go ustawić maksymalnie na 24 godziny.

### <a name="gradual-update"></a>Aktualizacja stopniowa

Jeśli zostanie wprowadzona nowa wersja certyfikatu, ale nie można jej aktualizować jednocześnie we wszystkich sklepach, profile certyfikatów umożliwiają stopniowe aktualizowanie certyfikatu.

1. Znajdź profil certyfikatu i wiersz, które powinny zostać zaktualizowane, a następnie wybierz **Ustawienia**.
1. Dodaj wiersz i określ ustawienia związane z najnowszą wersją certyfikatu.
1. Zwiększ wartość opcji **Priorytet** nowego wiersza. Użyj przycisku **Przenieś w górę** w celu przeniesienia wiersza w taki sposób, aby był umieszczony powyżej wiersza dla poprzedniej wersji tego samego certyfikatu.

> [!NOTE]
> W środowisku uruchomieniowym Commerce Runtime nowa wersja certyfikatu zostanie wywołana jako pierwsza. Jeśli certyfikat nie został jeszcze zaktualizowany w określonym sklepie lub na określonym terminalu, zostanie wywołana poprzednia wersja.
