---
title: Zacznij od administrowania usługą dodatkową dotyczącą fakturowania elektronicznego
description: W tym temacie opisano sposób rozpoczęcia pracy z dodatkiem Faktur elektronicznych.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592533"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a>Zacznij od administrowania usługą dodatkową dotyczącą fakturowania elektronicznego

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem procedur opisanych w tym temacie muszą być spełnione następujące wymagania wstępne:

- Musisz mieć dostęp do konta Microsoft Dynamics Lifecycle Services (LCS).
- Musisz mieć projekt usługi LCS z wersją 10.0.17 lub nowszą firmy Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management. Ponadto te aplikacje muszą zostać wdrożone w jednej z następujących lokalizacji geograficznych platformy Azure:

    - Wschodnie stany USA
    - Zachodnie stany USA
    - Europa Północna
    - Europa Zachodnia

- Musisz mieć dostęp do swojego konta Dynamics 365 Regulatory Configuration Services (RCS).
- Musisz aktywować funkcję globalizacji dla swojego konta RCS w zarządzaniu funkcjami. Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md).
- Musisz utworzyć magazyn kluczy i konto magazynu na platformie Azure. Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a>Zainstaluj dodatek dla mikrousług w Lifecycle Services

1. Zaloguj się do swojego konta LCS.
2. Wybierz kafelek **Zarządzanie funkcjami w wersji zapoznawczej**.
3. W sekcji **Funkcje w publicznych wersjach zapoznawczych** wybierz **usługę fakturowania elektronicznego**.
4. Sprawdź, czy w opcji **Funkcja wersji zapoznawczej włączona** jest ustawiona wartość **Tak**.
5. Na pulpicie nawigacyjnym usługi LCS wybierz projekt wdrożenia usługi LCS. Projekt usługi LCS musi być uruchomiony.
7. Na karcie **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
8. Wybierz **usługi fakturowania elektronicznego** i w polu Identyfikator aplikacji usługi **AAD** wprowadź wartość **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Ta wartość jest stałą wartością.
10. W polu **Identyfikator dzierżawy usługi AAD** wprowadź identyfikator dzierżawy konta subskrypcji systemu Azure.
11. Przejrzyj warunki, a następnie zaznacz pole wyboru.
12. Wybierz **Zainstaluj**.


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a>Skonfiguruj parametry RCS z dodatkiem Faktury elektroniczne

1. Zaloguj się do swojego konta RCS.
2. W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**.
3. Na karcie **Usługa fakturowania elektronicznego** w polu **Identyfikator URI punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.

    | Geografia platformy Datacenter Azure | Adres URI punktu końcowego usługi                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Wschodnie stany USA                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Zachodnie stany USA                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Europa Północna                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Europa Zachodnia                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. Upewnij się, że pole **Identyfikator aplikacji** ma ustawioną wartość **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Ta wartość jest stałą wartością.
5. W polu **Identyfikator środowiska usługi LCS** wprowadź identyfikator konta subskrypcji LCS.
6. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="create-key-vault-secret"></a>Utwórz wpis tajny magazynu kluczy

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Dodatek Faktury elektroniczne**.
3. Na stronie **Ustawienia środowiska**, w okienku akcji wybierz **Środowisko serwisu**, a następnie wybierz opcję **Parametry Key Vault**.
4. Wybierz opcję **Nowy**, aby utworzyć klucz tajny.
5. W polu **Nazwa** wprowadź nazwę wpisu tajnego magazynu kluczy. W polu **Opis wprowadź** opis.
6. W polu **URI magazynu kluczy** wklej klucz tajny z Azure Key Vault.
7. Wybierz opcję **Zapisz**.

## <a name="create-storage-account-secret"></a>Utwórz klucz tajny konta magazynu

1. Przejdź do **Administrowanie systemem** > **Ustawienia** > **Parametry Key Vault** i wybierz klucz tajny klucz.
2. W sekcji **Certyfikaty** wybierz opcję **Dodaj**.
3. W polu **Nazwa** wprowadź nazwę tajnych kont magazynowania, a w polu **Opis** wprowadź opis.
4. W polu **Typ** zaznacz opcję **Certyfikat**.
5. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="create-a-digital-certificate-secret"></a>Utwórz tajny kod certyfikatu cyfrowego

1. Przejdź do **Administrowanie systemem** > **Ustawienia** > **Parametry Key Vault** i wybierz klucz tajny klucz.
2. W sekcji **Certyfikaty** wybierz opcję **Dodaj**.
3. W polu **Nazwa** wprowadź nazwę tajnych certyfikatów wirtualnych, a w polu **Opis** wprowadź opis.
4. W polu **Typ** zaznacz opcję **Certyfikat**.
5. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="create-an-electronic-invoicing-add-on-environment"></a>Tworzenie środowiska dodatku Faktur elektronicznych

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Dodatek Faktury elektroniczne**.

## <a name="create-a-service-environment"></a>Tworzenie środowiska usługi

1. Na stronie **Ustawienia środowiska** w okienku akcji wybierz pozycję **Środowisko usługi**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowe środowisko usługi.
3. W polu **Nazwa** wprowadź nazwę środowiska e-fakturowania. W polu **Opis wprowadź** opis.
4. W polu **Tajny klucz tokenu sygnatury dostępu Współdzielonego magazynu** wybierz nazwę klucza tajnego konta magazynu, który musi być używany do uwierzytelniania dostępu do konta magazynu.
5. W sekcji **Użytkownicy** wybierz opcję **Dodaj**, aby dodać użytkownika, który może przesyłać faktury elektroniczne za pośrednictwem środowiska, a także połączyć się z kontem magazynu.
6. W polu **Identyfikator użytkownika** wprowadź alias użytkownika. W polu **Adres e-mail** wprowadź adres e-mail dla użytkownika.
7. Wybierz opcję **Zapisz**.
8. Jeśli faktury dotyczące Twojego kraju / regionu wymagają łańcucha certyfikatów do stosowania podpisów cyfrowych, w okienku Akcja wybierz **Parametry Key Vault**, a następnie wybierz **Łańcuch certyfikatów** i wykonaj następujące kroki:

    1. Wybierz pozycję **Nowy**, aby utworzyć łańcuch certyfikatów.
    2. W polu **Nazwa** wprowadź nazwę łańcucha certyfikatów. W polu **Opis wprowadź** opis.
    3. W sekcji **Certyfikaty** wybierz pozycję **Dodaj**, aby dodać certyfikat do łańcucha.
    4. Przycisk **W górę** lub **W dół** umożliwia zmianę pozycji certyfikatu w łańcuchu.
    5. Wybierz przycisk **Zapisz** i zamknij stronę.
    6. Zamknij stronę.
9. Na stronie **Środowisko usługi** w okienku akcji wybierz opcję **Publikuj**, aby opublikować środowisko w chmurze. Wartość pola **Stan** jest zmieniana na **Opublikowana**.

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

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a>Skonfiguruj integrację dodatku Faktur elektronicznych w rozwiązaniach Finance i Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Funkcja integracji faktur elektronicznych jest włączana za pośrednictwem terminów wyświetlania

1. Zaloguj się do wystąpienia Finance lub Supply Chain Management.
2. W obszarze roboczym **Zarządzanie funkcjami** wyszukaj funkcję **Integracja dodatku do elektronicznego fakturowania**. Jeśli ta funkcja nie jest wyświetlana na stronie, wybierz pozycję **Sprawdź, czy nie są aktualizacje**.
3. Wybierz funkcję, a następnie wybierz **Wyłącz teraz**.

### <a name="set-up-the-service-endpoint-url"></a>Konfigurowanie adresu URL punktu końcowego usługi

1. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
2. Na karcie **Usługa przesyłania** w polu **Identyfikator URL punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.

    | Geografia platformy Datacenter Azure | Adres URL punktu końcowego usługi                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Wschodnie stany USA                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Zachodnie stany USA                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Europa Północna                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Europa Zachodnia                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. W polu **Środowisko** wprowadź nazwę środowiska dodatkowego fakturowania elektronicznego.
4. Wybierz przycisk **Zapisz** i zamknij stronę.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
