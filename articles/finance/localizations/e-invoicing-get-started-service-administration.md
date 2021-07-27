---
title: Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami
description: W tym temacie opisano sposób rozpoczęcia pracy z funkcją Faktur elektronicznych.
author: gionoder
ms.date: 05/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8adbe577e5111a6a4afdba6aed32855b2e30b39b
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2021
ms.locfileid: "6335697"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a>Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem procedur opisanych w tym temacie muszą być spełnione następujące wymagania wstępne:

- Musisz mieć dostęp do konta Microsoft Dynamics Lifecycle Services (LCS).
- Musisz mieć projekt usługi LCS z wersją 10.0.17 lub nowszą firmy Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management. Ponadto te aplikacje muszą zostać wdrożone w jednej z następujących lokalizacji geograficznych platformy Azure:

    - Stany Zjednoczone
    - Europa
    - Wielka Brytania
    - Azja

- Musisz mieć dostęp do swojego konta Dynamics 365 Regulatory Configuration Services (RCS).
- Musisz aktywować funkcję globalizacji dla swojego konta RCS w zarządzaniu funkcjami. Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md).
- Musisz utworzyć magazyn kluczy i konto magazynu na platformie Azure. Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Zainstaluj dodatek dla mikrousług w Lifecycle Services

1. Zaloguj się do swojego konta LCS, i na pulpicie nawigacyjnym projektu LCS, wybierz projekt LCS.
2. W projekcie, na pulpicie nawigacyjnym, wybierz swój projekt wdrożeniowy LCS. Wybrany projekt musi być uruchomiony.
3. Na karcie **Integracja Power Platform** w grupie pól **Dodatki środowiska** wybierz pozycję **Zainstaluj nowy dodatek**.
4. Wybierz **Fakturowanie elektroniczne**.
5. W polu **Identyfikator aplikacji AAD** wprowadź nazwę **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Ta wartość jest stałą wartością.
6. W polu **Identyfikator dzierżawy usługi AAD** wprowadź identyfikator dzierżawy konta subskrypcji systemu Azure.
7. Przejrzyj warunki, a następnie zaznacz pole wyboru.
8. Wybierz **Zainstaluj**.


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Skonfiguruj parametry RCS z Faktury elektroniczne

1. Zaloguj się do swojego konta RCS.
2. W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**.
3. Na karcie **Usługa fakturowania elektronicznego** w polu **Identyfikator URI punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.

    | Geografia platformy Datacenter Azure | Adres URI punktu końcowego usługi                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Stany Zjednoczone              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Wielka Brytania             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Azja                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

4. Upewnij się, że pole **Identyfikator aplikacji** ma ustawioną wartość **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Ta wartość jest stałą wartością.
5. W polu **Identyfikator środowiska usługi LCS** wprowadź identyfikator środowiska LCS.
6. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="create-key-vault-references"></a>Tworzenie zasobu magazynu kluczy

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Faktury elektroniczne**.
3. Na stronie **Ustawienia środowiska**, w okienku akcji wybierz **Środowisko serwisu**, a następnie wybierz opcję **Parametry Key Vault**.
4. Wybierz opcję **Nowy**, aby utworzyć klucz tajny referencji.
5. W polu **Nazwa** wprowadź nazwę wpisu tajnego magazynu kluczy referencji. W polu **Opis wprowadź** opis.
6. W polu **URI magazynu kluczy** wklej klucz tajny z Azure Key Vault. Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).
7. Wybierz opcję **Zapisz**.

## <a name="create-storage-account-secret"></a>Utwórz klucz tajny konta magazynu

1. Na stronie **Ustawienia środowiska**, w okienku akcji wybierz **Środowisko usługi** > **Parametry Key Vault**.
2. Wybierz **Referencje wpisu tajnego** i w sekcji **Certyfikaty** wybierz opcję **Dodaj**.
3. W polu **Nazwa** wprowadź ten nazwę klucza tajnyego konta magazynu. Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).
4. W polu **Opis wprowadź** opis.
5. W polu **Typ** wybierz **Wpis tajny**.
6. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="create-a-digital-certificate-secret"></a>Utwórz tajny kod certyfikatu cyfrowego

1. Na stronie **Ustawienia środowiska**, w okienku akcji wybierz **Środowisko serwisu**, a następnie wybierz opcję **Parametry Key Vault**.
2. Wybierz **Referencje wpisu tajnego** i w sekcji **Certyfikaty** wybierz opcję **Dodaj**.
3. W polu **Nazwa** wprowadź ten nazwę klucza tajnego cyfrowego certyfikatu. Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).
4. W polu **Opis wprowadź** opis.
5. W polu **Typ** zaznacz opcję **Certyfikat**.
6. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="create-a-service-environment"></a>Tworzenie środowiska usługi

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Faktury elektroniczne**.
3. Na stronie **Ustawienia środowiska** w okienku akcji wybierz pozycję **Środowisko usługi**.
4. Wybierz pozycję **Nowy**, aby utworzyć nowe środowisko usługi.
5. W polu **Nazwa** wprowadź nazwę środowiska e-fakturowania. W polu **Opis wprowadź** opis.
6. W polu **Tajny klucz tokenu sygnatury dostępu Współdzielonego magazynu** wybierz nazwę klucza tajnego konta magazynu, który musi być używany do uwierzytelniania dostępu do konta magazynu.
7. W sekcji **Użytkownicy** wybierz opcję **Dodaj**, aby dodać użytkownika, który może przesyłać faktury elektroniczne za pośrednictwem środowiska, a także połączyć się z kontem magazynu.
8. W polu **Identyfikator użytkownika** wprowadź alias użytkownika. W polu **Adres e-mail** wprowadź adres e-mail dla użytkownika.
9. Wybierz opcję **Zapisz**.
10. Jeśli faktury dotyczące Twojego kraju / regionu wymagają łańcucha certyfikatów do stosowania podpisów cyfrowych, w okienku Akcja wybierz **Parametry Key Vault**, a następnie wybierz **Łańcuch certyfikatów** i wykonaj następujące kroki:
    1. Wybierz pozycję **Nowy**, aby utworzyć łańcuch certyfikatów.
    2. W polu **Nazwa** wprowadź nazwę łańcucha certyfikatów. W polu **Opis wprowadź** opis.
    3. W sekcji **Certyfikaty** wybierz pozycję **Dodaj**, aby dodać certyfikat do łańcucha.
    4. Przycisk **W górę** lub **W dół** umożliwia zmianę pozycji certyfikatu w łańcuchu.
    5. Wybierz przycisk **Zapisz** i zamknij stronę.
    6. Zamknij stronę.
11. Na stronie **Środowisko usługi** w okienku akcji wybierz opcję **Publikuj**, aby opublikować środowisko w chmurze. Wartość pola **Stan** jest zmieniana na **Opublikowana**.

## <a name="create-a-connected-application"></a>Utwórz połączoną aplikację

1. Na stronie **Ustawienia środowiska** w okienku akcji wybierz pozycję **Połączone aplikacje**.
2. Wybierz pozycję **Nowy**, aby utworzyć połączoną aplikację.
3. W polu **Nazwa** wprowadź nazwę aplikacji do połączenia.
4. W polu **Aplikacja** wprowadź adres URL środowiska Finance and Supply Chain Management, aby nawiązać połączenie.
4. W polu **Dzierżawca** wprowadź dzierżawcę Finance and Supply Chain Management.
5. Wybierz opcję **Zapisz**.
6. W okienku akcji wybierz opcję **Sprawdź połączenie**, aby przetestować połączenie ze środowiskiem. Następnie zamknij stronę.

## <a name="link-connected-applications-to-environments"></a>Połącz połączone aplikacje ze środowiskami

1. Na stronie **Ustawienia środowiska** wybierz pozycję **Nowy**, aby przypisać połączoną aplikację do środowiska.
2. W polu **Połączona aplikacja** wybierz połączoną aplikację.
3. W polu **Środowisko usługi** wybierz środowisko usługi.
4. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a>Skonfiguruj integrację Faktur elektronicznych w rozwiązaniach Finance lub Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a>Funkcja integracji faktur elektronicznych jest włączana za pośrednictwem terminów wyświetlania

1. Zaloguj się do wystąpienia Finance lub Supply Chain Management.
2. W obszarze roboczym **Zarządzanie funkcjami** wyszukaj funkcję **Integracja elektronicznego fakturowania**. Jeśli ta funkcja nie jest wyświetlana na stronie, wybierz pozycję **Sprawdź, czy nie są aktualizacje**.
3. Wybierz funkcję, a następnie wybierz **Wyłącz teraz**.

### <a name="set-up-the-service-endpoint-url"></a>Konfigurowanie adresu URL punktu końcowego usługi

1. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
2. Na karcie **Usługa przesyłania** w polu **Identyfikator URL punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.

    | Geografia platformy Datacenter Azure | Adres URI punktu końcowego usługi                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Stany Zjednoczone              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Wielka Brytania             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Azja                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. W polu **Środowisko** wprowadź nazwę środowiska usługowego opublikowaną w Fakturowaniu elektronicznym.
4. Wybierz przycisk **Zapisz** i zamknij stronę.

### <a name="enable-flighting-keys"></a>Włącz klucze lotów

Włącz klucze lotów dla rozwiązania Microsoft Dynamics 365 Finance lub Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.17 lub wcześniejszych. 
1. Wykonaj następujące polecenie SQL:

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)

2. Wykonaj polecenie IISreset dla wszystkich AOS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
