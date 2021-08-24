---
title: Moduł kart upominkowych
description: W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5a4aaf8e072f6547fe1dcf6fa156d2e144fd03ed806a2dc809a2cedb991461f7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728346"
---
# <a name="gift-card-module"></a>Moduł karty upominkowej

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduły kart upominkowych można używać w module realizacji transakcji w celu przyjmowania kart upominkowych, bardzo popularnej metody płatności w transakcjach handlu elektronicznego. Moduł kart upominkowych wspiera Dynamics 365, SVS i karty upominkowe Givex. Karty upominkowe SVS i Givex są realizowane przez dostawcę płatności Adyen. Aby uzyskać więcej informacji na temat obsługi zewnętrznych kart upominkowych, takich jak SVS i Givex, zajrzyj do [Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md).

> [!NOTE]
> Obsługa realizowania kart upominkowych SVS i Givex w procesie realizacji transakcji jest dostępna w wydaniu Dynamics 365 Commerce 10.0.11. 

Dostępne są dwa moduły karty upominkowej:

- **Karta upominkowa** — ten moduł może być używany na stronie realizacji transakcji, aby zrealizować kartę upominkową jako ofertę płatności. 
- **Sprawdzanie salda karty upominkowej** — ten moduł może być używany na dowolnej stronie w celu sprawdzenia salda na karcie upominkowej. Ten moduł jest dostępny w Commerce w wersji 10.0.14 i nowszej.

> [!NOTE]
> Obsługa modułu kontroli salda kart upominkowych jest dostępna w wydaniu Dynamics 365 Commerce 10.0.14.

Poniższy obraz pokazuje przykład modułu karty podarunkowej na stronie realizacji zamówienia.

![Przykład modułu na karty upominkowej.](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Właściwości modułu

- **Pokaż dodatkowe pola** — ta właściwość określa pola, które mają być wyświetlane w przypadku kart upominkowych, oprócz numeru karty upominkowej, który jest zawsze domyślnie wyświetlany. Na przykład niektóre karty upominkowe umożliwiają wyświetlanie osobistego numeru identyfikacyjnego (PIN), a inne umożliwiają wyświetlanie numeru PIN i daty ważności. Można również ustawić tę właściwość na „Brak”, co spowoduje wyświetlenie numeru karty upominkowej bez dodatkowych pól.

    Obsługiwane są następujące wartości:

    - PIN
    - Data wygaśnięcia
    - Numer PIN i data ważności 
    - None

- **Włącz dla użytkowników-gości** — gdy ta właściwość jest włączona, użytkownicy-goście mogą realizować lub sprawdzać salda na kartach upominkowych. Ta właściwość wymaga, aby anonimowy (gość) dostęp do kart upominkowych był włączony w siedzibie firmy Commerce. Aby uzyskać więcej informacji, zobacz [Włączanie płatności kartą upominkową do realizacji transakcji gościa](#enable-gift-card-payments-for-guest-checkout).

> [!IMPORTANT]
> Właściwość **Włącz dla użytkowników-gości** jest dostępna w Commerce od wersji 10.0.21. Wymaga, pakietu biblioteki modułów Commerce w wersji 9.31.

## <a name="site-settings-for-gift-card-modules"></a>Ustawienia witryny dla modułów kart upominkowych

W konstruktorze witryn Commerce w **Ustawienia witryny \> Rozszerzenia** istnieje ustawienie modułu kart upominkowych o nazwie **Obsługiwany typ karty upominkowej**. To ustawienie obsługuje trzy wartości:
- **Dynamics 365 — karta upominkowa** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365. To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.
- **Karty upominkowe SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych SVS i Givex. To ustawienie jest obsługiwane dla użytkowników anonimowych oraz zalogowanych w witrynie handlu elektronicznego.
- **Karty upominkowe Dynamics 365, SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365, SVS i Givex. To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.

> [!IMPORTANT]
> Te ustawienia są dostępne w wydaniu Dynamics 365 Commerce 10.0.11 i są wymagane tylko wtedy, gdy potrzebna jest pomoc techniczna dla kart upominkowych SVS i Givex. W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json. Aby uzyskać instrukcje dotyczące aktualizowania pliku appsettings.json, zajrzyj do [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a>Rozszerzanie wewnętrznych kart upominkowych do użytku w witrynach handlu elektronicznego

Domyślnie wewnętrzne karty upominkowe nie są przystosowane do używania w witrynach handlu elektronicznego. Dlatego zanim zezwolisz na to, aby wewnętrzne karty upominkowe zostały użyte do płatności, musisz je skonfigurować za pomocą rozszerzeń, które ułatwiają ich zabezpieczanie. Oto obszary kart upominkowych, które należy rozszerzyć, zanim zezwolisz na używanie w środowisku produkcyjnym wewnętrznych kart upominkowych:

- **Numer karty upominkowej** — Sekwencje numerów służą do generowania numerów kart upominkowych dla wewnętrznych kart upominkowych. Ponieważ sekwencje numerów można łatwo przewidzieć, należy rozszerzyć generowanie numerów kart upominkowych, tak aby numery wystawianych kart upominkowych były wybierane losowo, w sposób kryptograficznie bezpieczny.
- **GetBalance** — Interfejs API **GetBalance** służy do odczytywania sald karty upominkowej. Domyślnie ten interfejs API jest publiczny. Jeśli do wyszukiwania sald karty upominkowej nie jest wymagany numer PIN, istnieje ryzyko użycia interfejsu API **GetBalance** do wyszukiwania numerów kart upominkowych z saldami. Wdrożenie zarówno wymagań dotyczących numeru PIN dla wewnętrznych kart upominkowych, jak i dławienie interfejsu API pomaga złagodzić ryzyko.
- **PIN** — domyślnie wewnętrzne karty upominkowe nie obsługują numeru PIN. Wewnętrzne karty upominkowe należy rozszerzyć o wymóg podania PIN w celu odczytania salda. Ta funkcja umożliwia także blokowanie kart upominkowych po kolejnych niepoprawnych próbach wprowadzenia numeru PIN.

## <a name="enable-gift-card-payments-for-guest-checkout"></a>Włączanie płatności kartą upominkową podczas realizacji transakcji przez gościa

Domyślnie płatności kartą upominkową nie są dostępne podczas realizacji transakcji przez gościa (anonimowego). Aby je włączyć, wykonaj następujące kroki.

1. W centrali Commerce przejdź do lokalizacji **Retail i Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Operacje punktu sprzedaży**.
1. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) nagłówek siatki, a następnie wybierz polecenie **Wstaw kolumny**.
1. W oknie dialogowym **Wstawianie kolumn** zaznacz pole wyboru **AllowAnonymousAccess**.
1. Wybierz **Aktualizuj**.
1. W przypadku operacji **520** (saldo na karcie upominkowej) i **214** ustaw wartość **AllowAnonymousAccess** na **1**.
1. Wybierz opcję **Zapisz**.
1. Wykonaj zadanie harmonogram **1090**, aby zsynchronizować zmiany z bazą danych kanału. 

## <a name="add-a-gift-card-module-to-a-page"></a>Dodawanie modułu kart upominkowych do strony

Aby uzyskać instrukcje dotyczące dodawania modułu kart upominkowych do strony realizacji transakcji i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł płatności](payment-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł opcji dostawy](delivery-options-module.md)

[Moduł informacji o odbiorze](pickup-info-module.md)

[Moduł szczegółów zamówienia](order-confirmation-module.md)

[Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md)

[Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
