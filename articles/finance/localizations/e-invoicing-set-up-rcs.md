---
title: Włącz Regulatory Configuration Service (RCS)
description: W tym artykule wyjaśniono, jak skonfigurować usługę Regulatory Configuration Service (RCS).
author: gionoder
ms.date: 10/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 32ced98925ee66e02f0b073b4acbd586666ac20c
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710789"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>Włącz Regulatory Configuration Service (RCS)

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak skonfigurować usługę Regulatory Configuration Service (RCS).

## <a name="turn-on-globalization-features"></a>Włączanie funkcji globalizacji

1. Zaloguj się do swojego konta RCS.
2. Wybierz kafelek **Zarządzanie funkcjami**.
3. W obszarze roboczym **Zarządzanie funkcjami** wybierz z listy **Funkcje globalizacji**, a następnie wybierz pozycję **Włącz teraz**.

Kafelki dla obszaru roboczego **Funkcje globalizacji** powinny teraz być widoczne na głównym pulpicie nawigacyjnym usługi RCS.

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Skonfiguruj parametry RCS z Faktury elektroniczne

1. W module **Funkcje globalizacji**, w obszarze roboczym **Ustawienia powiązane** wybierz opcję **Parametry raportowania elektronicznego**.
2. Przy pierwszym ustawianiu parametrów wyświetlany jest monit o połączenie z usługą Life Cycle Services (LCS). Wybierz **Kliknij tutaj, aby nawiązać połączenie z usługą Lifecycle Services** i po nawiązaniu połączenia wybierz przycisk **OK**.

    > [!IMPORTANT]
    > W krajach lub regionach, w których jest wymuszana usługa zamieszkania danych i jeśli usługa RCS została zainicjowana w innym regionie, w którym usługa LCS jest inicjowana, może zostać wyświetlony następujący komunikat o błędzie połączenia w usługach RCS: „Nie znaleziono zasobu HTTP, który pasuje do identyfikatora URI żądania”. Kliknij przycisk **OK**. Możesz otrzymać kolejny komunikat wiadomości w RCS: „Nie można wygenerować tokenu użytkownika dla usługi Dynamics Lifecycle Services w imieniu użytkownika (). Skontaktuj się z administratorem systemu”.
    >  
    > Dzieje się tak, ponieważ usługa LCS jest usługą globalną i jest inicjowana w regionie USA. Z powodu zasad dotyczących pobytu danych usługi RCS z bieżącego regionu nie może nawiązać połączenia z usługi LCS. W tych warunkach są dostępne 2 możliwe rozwiązania:
    > - Usuń RCS z bieżącego regionu i utwórz go ponownie w regionie USA.
    > - Ignoruj błędy i kontynuuj, korzystanie z ustawień fakturowania elektronicznego. Te błędy nie mają wpływu na funkcję fakturowania elektronicznego.

3. Na karcie **Fakturowanie elektroniczne** w polu **Identyfikator URI punktu końcowego** usługi wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Microsoft Azure, tak jak pokazano w poniższej tabeli.

    | Geografia platformy Datacenter Azure | Adres URI punktu końcowego usługi |
    |----------------------------|----------------------|
    | Stany Zjednoczone              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Zjednoczone Królestwo             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Azja                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japonia                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Szwajcaria                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brazylia                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Zjednoczone Emiraty Arabskie       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Australia                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Kanada                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Francja                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Indie                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Norwegia                     | <p>`https://gw.no-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Republika Południowej Afryki               | <p>`https://gw.za-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. Przejrzyj i wprowadź w polu **Identyfikator zgłoszenia** stałą wartość **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Należy upewnić się, że wprowadzany jest tylko unikatowy globalnie identyfikator (GUID) i że wartość nie zawiera żadnych innych symboli, takich jak spacje, przecinka, kropki czy cudzysłów.
4. W polu **Identyfikator środowiska usługi LCS** wprowadź identyfikator środowiska Microsoft Dynamics Lifecycle Services (LCS). Ta wartość jest odwołaniem do środowiska Zarządzania finansami lub Supply Chain Management, które będzie korzystać z usługi fakturowania elektronicznego. Aby uzyskać identyfikator, [zaloguj się do usługi LCS](https://lcs.dynamics.com/), otwórz projekt,a następnie na karcie **Zarządzaj środowiskiem** w **sekcji Szczegóły środowiska** sprawdź **pole Identyfikator środowiska**.

    > [!IMPORTANT]
    > Jeśli dodatek Fakturowanie elektroniczne jest zainstalowany w wielu środowiskach zarządzania finansami lub Supply Chain Management w u usługach LCS, zawsze używaj identyfikatora środowiska ostatnio zainstalowanego środowiska. Jeśli użytkownik zdecyduje się zainstalować dodatek w nowym środowisku po skonfigurowaniu funkcji fakturowania elektronicznego i pracy z nim, zaktualizuj pole Identyfikator **środowiska usługi LCS w aplikacji RCS**, tak aby zawierała najnowszą wartość.

5. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="configuration-providers"></a>Dostawcy konfiguracji

Dostawcy konfiguracji mogą odróżniać właścicieli konfiguracji raportowania elektronicznego używanych w procesach fakturowania elektronicznego oraz w funkcjach globalizacji właścicieli. W przypadku wszystkich funkcji globalizacji dostarczanych przez firmę Microsoft i opublikowanych w repozytorium globalnym dostawca konfiguracji jest ustawiony na **firmę Microsoft** (`http://microsoft.com`).

Można korygować tylko konfiguracje ER i funkcje globalizacji należące do aktywnego dostawcy konfiguracji. Tych konfiguracji i funkcji można używać jako szablonów do tworzenia konfiguracji i funkcji należących do aktywnego dostawcy konfiguracji, co umożliwia ich korygowanie.

Najpierw utwórz dostawców konfiguracji. Następnie ustaw jedną z nich jako aktywną. Nie można ustawić dostawcy konfiguracji firmy **Microsoft** jako aktywnego.

### <a name="create-a-configuration-provider"></a>Utwórz dostawcę konfiguracji

1. W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Dostawcy konfiguracji**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** wprowadź unikalną nazwę dostawcy konfiguracji.
4. W polu **Adres internetowy** wpisz unikalny adres URL dostawcy konfiguracji.
5. Wybierz przycisk **Zapisz** i zamknij stronę.

### <a name="select-a-configuration-provider-as-active"></a>Wybierz dostawcę konfiguracji jako aktywnego

1. Z listy dostawców konfiguracji wybierz dostawcę konfiguracji, który ma być ustawiony jako aktywny.
2. Wybierz **Aktywuj**.

## <a name="import-er-configurations-from-the-global-repository"></a>Importuj konfiguracje ER z globalnego repozytorium

1. W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Dostawcy konfiguracji**.
2. Z listy dostawców konfiguracji wybierz **Microsoft**, a następnie **Repozytoria**.
3. Wybierz opcję **Globalna** i w okienku akcji wybierz opcję **Otwórz**.
4. Importuj następujące modele ER:

    - **Model kontekstowy faktur sprzedaży**
    - **Model faktury**
    - **Dokumenty fiskalne** (w scenariuszach brazylijskich, jeśli są wymagane)
    - **Model komunikatu odpowiedzi**

5. Jeśli **mapowanie modelu faktury** nie było automatycznie importowane, importuj je.
6. Zamknij stronę.
