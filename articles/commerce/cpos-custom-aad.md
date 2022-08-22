---
title: Konfigurowanie aplikacji CPOS do używania aplikacji niestandardowej Azure AD
description: W tym artykule opisano, jak skonfigurować program Cloud POS (CPOS) do używania niestandardowej aplikacji Azure Active Directory (Azure AD).
author: boycez
ms.date: 08/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: baa0c3da25308345037b5dd1b4c5907d6213e7f7
ms.sourcegitcommit: bd3b55e1af28e592c97b540de1e87cd8ba9c35a8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2022
ms.locfileid: "9222973"
---
# <a name="configure-cpos-to-use-a-custom-azure-ad-app"></a>Konfigurowanie aplikacji CPOS do używania aplikacji niestandardowej Azure AD

[!include [banner](includes/banner.md)]

Domyślnie Cloud POS (CPOS) w Microsoft Dynamics 365 Commerce wskazuje na zarejestrowaną własną aplikację firmy Microsoft w Azure Active Directory (Azure AD). W związku z tym można używać funkcji CPOS bez konieczności zmieniania w programie Azure AD. Można jednak wskazać wystąpienie aplikacji CPOS do niestandardowej aplikacji Azure AD, którą kontrolujesz. W tym artykule wyjaśniono, jak skonfigurować CPOS do korzystania z niestandardowej aplikacji Azure AD.

## <a name="set-up-a-custom-retail-server-app-in-azure-ad"></a>Skonfiguruj niestandardową aplikację Retail Server w programie Azure AD

Aby utworzyć i skonfigurować niestandardową aplikację Retail Server Azure AD, wykonaj następujące kroki.

1. Zaloguj się do [centrum administracyjnego Azure Active Directory](https://aad.portal.azure.com), używając odpowiedniego konta użytkownika Azure AD. Konto użytkownika nie musi mieć uprawnień administratora.
1. Wybierz **Azure Active Directory**.
1. Wybierz **opcję Rejestracje aplikacji**, a następnie wybierz opcję **Nowa** rejestracja, aby **otworzyć** okno dialogowe Rejestrowanie zgłoszenia.
1. Ustaw wartości w następujących polach:

    - **Nazwa** – Wpisz niestandardową nazwę aplikacji. Na przykład wprowadź niestandardowy **program Retail Server**.
    - **Typy kont pomocy technicznej** — wybierz opcję domyślną. **Konta są dostępne tylko w tym katalogu organizacyjnym (tylko rozwiązanie Microsoft — jedna dzierżawa)**.
    - **URI przekierowania** – To pole jest opcjonalne. Pozostaw to pole puste.
    - **Identyfikator Service Tree** – To pole jest opcjonalne. Pozostaw to pole puste.
    
1. Wybierz opcję **Zarejestruj**. Zostanie wyświetlona strona konfiguracji dla nowo zarejestrowanej aplikacji.
1. W sekcji **Podstawowe \> informacje ogólne** wybierz **pozycję Dodaj identyfikator URI** aplikacji, **a następnie wybierz pozycję Ustaw** obok **identyfikatora aplikacji URI**. Zanotuj sugerowaną wartość, a następnie wybierz przycisk **Zapisz**, aby zaakceptować tę wartość. 
1. Wybierz pozycję **Dodaj zasięg**, a następnie ustaw wymienione poniżej pola:

    - **Nazwa zakresu** — Wpisz niestandardową nazwę zakresu. Na przykład wprowadź wartość **Legacy.Access.Full**.
    - **Kto może wyrazić zgodę?** — umożliwia określenie, czy zgoda może być wyrażana przez administratorów i użytkowników, czy tylko administratorów na podstawie zasad zabezpieczeń danej organizacji.
    - **Nazwa wyświetlana zgody administratora** — wprowadź nazwę wyświetlaną. Na przykład wprowadź **Uzyskaj dostęp do serwera detalicznego Retail Server**.
    - **Opis zgody administratora** — wprowadź opis. Na przykład wprowadź **Daje dostęp do interfejsów API serwera detalicznego**.

1. Wybierz **opcję Dodaj zakres**, aby zakończyć proces tworzenia zakresu.

## <a name="set-up-a-custom-cpos-app-in-azure-ad"></a>Skonfiguruj niestandardową aplikację CPOS w Azure AD

Aby utworzyć i skonfigurować niestandardową aplikację CPOS Azure AD, wykonaj następujące kroki.

1. Zaloguj się do [centrum administracyjnego Azure Active Directory](https://aad.portal.azure.com), używając odpowiedniego konta użytkownika Azure AD. Konto użytkownika nie musi mieć uprawnień administratora.
1. Wybierz **Azure Active Directory**.
1. Wybierz **opcję Rejestracje aplikacji**, a następnie wybierz opcję **Nowa** rejestracja, aby **otworzyć** okno dialogowe Rejestrowanie zgłoszenia.
1. Ustaw wartości w następujących polach:

    - **Nazwa** – wprowadź nazwę dla aplikacji. Na przykład wprowadź **Niestandardowy punkt sprzedaży w chmurze**.
    - **Typy kont pomocy technicznej** — wybierz opcję domyślną. **Konta są dostępne tylko w tym katalogu organizacyjnym (tylko rozwiązanie Microsoft — jedna dzierżawa)**.
    - **Przekieruj adres URI** — wybierz z listy rozwijanej **Aplikacja jednostronicowa (SPA)**, a następnie wprowadź adres URI CPOS.
    - **Identyfikator Service Tree** – To pole jest opcjonalne. Pozostaw to pole puste.

1. Wybierz opcję **Zarejestruj**. Zostanie wyświetlona strona konfiguracji dla nowo zarejestrowanej aplikacji.
1. W sekcji **Manifest** dla parametrów **oauth2AllowIdTokenImplicitFlow** i **oauth2AllowImplicitFlow** ustaw wartość **prawda**, a następnie wybierz pozycję **Zapisz**.
1. W sekcji **Konfiguracja tokenu** wykonaj następujące kroki, aby dodać dwa roszczenia:

    - Wybierz **Dodaj opcjonalne roszczenie**. Ustaw w **polu Typ tokenu** wartość **Identyfikator**, a następnie wybierz roszczenie **identyfikatora sid**. Wybierz opcję **Dodaj**.
    - Wybierz **Dodaj opcjonalne roszczenie**. Ustaw w **polu Typ tokenu** wartość **Dostęp**, a następnie wybierz roszczenie **identyfikatora sid**. Wybierz opcję **Dodaj**.

1. W **Uprawnienia do interfejsu API** wybierz opcję **Dodaj uprawnienie**.
1. Na karcie **Interfejsy API używane przeze mnie** organizacja wyszukaj aplikację Retail Server utworzoną w sekcji [Konfigurowanie niestandardowej aplikacji usługi Retail Server Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad). Wybierz opcję **Dodaj uprawnienia**.
1. W sekcji **Przegląd** zanotuj wartość w polu **Identyfikator aplikacji (klienta)**.

## <a name="update-the-cpos-configuration-file"></a>Zaktualizuj plik konfiguracyjny CPOS

Otwórz plik CPOS config.json i dokonaj w nim następujących aktualizacji.

1. Zastąp wartość klucza **AADClientId** wartością **identyfikatora aplikacji (klienta)** niestandardowej aplikacji CPOS utworzonej w sekcji [Konfigurowanie niestandardowej aplikacji CPOS Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
1. Zastąp wartość klucza **AADRetailServerResourceId** wartością **Identyfikator URI aplikacji** niestandardowej aplikacji Retail Server utworzonej w sekcji [Konfigurowanie niestandardowej aplikacji Retail Server Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

CPOS będzie używać obu parametrów podczas wysyłania żądań do usługi Azure AD w celu uzyskania tokenu zabezpieczającego.

## <a name="update-identity-providers-settings-in-commerce-headquarters"></a>Aktualizowanie ustawień dostawców tożsamości w programie Commerce Headquarters

Następnie musisz zaktualizować ustawienia dostawców tożsamości w Commerce headquarters.

1. W centrali Commerce headquarters przejdź do **CWspólne parametry Commerce**.
1. Na karcie **Dostawcy tożsamości** w **sekcji Dostawcy tożsamości** wybierz wiersz, w którym jest ustawione pole **Typ** na **Azure Active Directory**, a pole **Wystawca** wskazuje Twojej dzierżawy Azure AD. To ustawienie deklaruje, że będzie działać z siatkami podrzędnym, które zawierają dane związane z dostawcą tożsamości, który odpowiada Twojej dzierżawie Azure AD.
1. W sekcji **Jednostki zależne** wybierz opcję **Dodaj**, aby dodać wiersz.
1. Ustaw wartości w następujących polach:

    - **ClientId** – wpisz wartość **identyfikatora aplikacji (klienta)** niestandardowej aplikacji CPOS utworzonej w sekcji [Konfigurowanie niestandardowej aplikacji CPOS Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
    - **Typ** – Wybierz **Publiczny**.
    - **UserType** – Wybierz **Pracownik**.

1. Wybierz dodany wiersz. Sekcja **Identyfikatory zasobów serwera** poniżej sekcji **Strony ufające** zawiera identyfikatory aplikacji Retail Server, do których można uzyskać dostęp za pomocą aplikacji wybranej w siatce **Strony zależne**.
1. W sekcji **Identyfikatory zasobów serwera** wybierz pozycję **Dodaj**, aby dodać wiersz.
1. W polu **Identyfikator zasobu serwera** wpisz **Identyfikator URI aplikacji** niestandardowej aplikacji Retail Server utworzonej w sekcji [Konfigurowanie niestandardowej aplikacji Retail Server Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

    > [!IMPORTANT]
    > W przypadku wszystkich pól wymienionych w poprzednich krokach jest to wielkość liter. Wprowadzanie wartości musi dokładnie odpowiadać wartościom skonfigurowanym w centrum administratora Azure AD.

1. Przejdź do **Retail i Commerce \> Harmonogram dystrybucji** i uruchom zadanie **1110** (**Konfiguracja globalna**).

Urządzenia CPOS można teraz aktywować za pomocą własnej aplikacji Azure AD.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Aktywacja urządzenia w punkcie sprzedaży (POS)](dev-itpro/retail-device-activation.md)

[Zarządzanie kontami aktywacji i weryfikowanie urządzeń](set-up-activation-accounts-validate-devices-hq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
