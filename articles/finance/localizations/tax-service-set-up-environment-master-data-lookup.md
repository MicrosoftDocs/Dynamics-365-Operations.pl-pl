---
title: Włącz odnośniki danych główne do konfiguracji obliczania podatku
description: W tym artykule wyjaśniono, jak skonfigurować i włączyć funkcję wyszukiwania danych podstawowych obliczania podatku.
author: kai-cloud
ms.date: 07/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f9d882340171173e5e503f8b5e3aa856e8544b0
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306212"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Włącz odnośniki danych główne do konfiguracji obliczania podatku 

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak skonfigurować i włączyć funkcję wyszukiwania danych podstawowych obliczania podatku. Dostępna jest lista rozwijana, na podstawie których można wybrać wartości w konfiguracji obliczania podatku dla takich pól, jak **Osoba prawna**, **Konto dostawcy**, **Kod pozycji** czy **Termin dostawy**. Te wartości pochodzą ze połączonego środowiska Microsoft Dynamics 365 Finance, używając źródła danych Microsoft Dataverse.

> [!NOTE] 
> Funkcja wyszukiwania danych głównych obliczenia podatku jest opcjonalna. Możesz pominąć następujące kroki, jeśli włączysz funkcję **Obsługa źródeł danych w usłudze obliczania podatku Dataverse** w usłudze Regulatory Configuration Service (RCS). W takim przypadku lista rozwijana nie będzie jednak dostępna w konfiguracji obliczania podatku.

Aby włączyć listę rozwijaną w konfiguracji wersji funkcji Obliczanie podatku, wykonaj następujące kroki.

1. [Włącz integrację  Microsoft Power Platform i otwórz środowisko Dataverse.](#enable)
2. [Zainstaluj wirtualne jednostki finansów i operacji.](#install)
3. [Rejestrowanie aplikacji Azure Active Directory (Azure AD).](#register)
4. [Nadawanie uprawnień w aplikacjach finansowych i operacyjnych.](#grant)
5. [Konfiguracja źródła danych jednostki wirtualnej.](#configure)
6. [Włączanie jednostek wirtualnych usługi Dataverse.](#virtual)
7. [Skonfiguruj połączoną aplikację do obliczenia podatku.](#set-up)
8. [Zaimportuj i skonfiguruj plik mapowania modelu danych Dataverse.](#import)

## <a name="enable-microsoft-power-platform-integration-and-open-the-dataverse-environment"></a><a name='enable'></a>Włącz integrację Microsoft Power Platform i otwórz środowisko Dataverse

Integrację aplikacji finansowych i operacyjnych z Microsoft Power Platform można włączyć po utworzeniu nowego środowiska aplikacji finansowych i operacyjnych w Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Integracja Microsoft Power Platform - Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Po zakończeniu pracy w sekcji **Integracji Power Platform** się nazwa środowiska Microsoft Power Platform.

1. W LCS, w swoim środowisku finansowym i operacyjnym, w sekcji **Integracji Power Platform** znajdź i zanotuj wartość **Nazwa środowiska** dla połączonego środowiska.

    [![Wartość nazwy środowiska.](./media/tcs-dataverse-master-data-lookup-1.png)](./media/tcs-dataverse-master-data-lookup-1.png)

2. W [centrum administracyjnym Power Platform](https://admin.powerplatform.microsoft.com/environments), na karcie **Środowiska** wybierz środowisko, które pasuje do zapisanych wartości w **nazwie środowiska**.
3. Na stronie **Szczegóły** znajdź wartość **adresu URL środowiska** Dataverse. Zanotuj tę wartość, ponieważ będzie ona potrzebna w [Kroku 7. Skonfiguruj podłączoną aplikację do obliczania podatków](#set-up).
4. Upewnij się, że możesz otworzyć środowisko Dataverse w swojej przeglądarce, wybierając wartość **URL środowiska**.

    [![Strona środowiska Dataverse.](./media/tcs-dataverse-master-data-lookup-2.png)](./media/tcs-dataverse-master-data-lookup-2.png)

    > [!NOTE]
    > Pozostaw środowisko Dataverse otwarte w przeglądarce. Będzie ona potrzebna w [Kroku 5. Konfiguracja źródła danych encji wirtualnej](#configure).

Aby uzyskać więcej informacji, zobacz sekcję [Włączanie narzędzia integracji Microsoft Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

## <a name="install-finance-and-operations-virtual-entities"></a><a name='install'></a>Zainstaluj wirtualne jednostki finansów i operacji

Rozwiązanie Dataverse dla jednostek wirtualnych finansów i operacji musi być zainstalowane z rozwiązania jednostek wirtualnych Microsoft AppSource.

1. W AppSource znajdź [encję Finansowe i operacyjne jednostki wirtualne](https://appsource.microsoft.com/product/dynamics-365/mscrm.finance_and_operations_virtual_entity).
2. Wybierz **Zdobądź teraz**.
3. W polu **Wybierz środowisko** wprowadź wartość **Nazwa środowiska**, którą wcześniej zanotowałeś.
4. Zaznacz pola wyboru, a następnie wybierz pozycję **Zainstaluj**.

Po zakończeniu instalacji możesz znaleźć aplikację **Wirtualna encja ds. finansów i operacji** w [centrum administracyjnym Power Platform](https://admin.powerplatform.microsoft.com/), w zakładce **Zasoby** \> **Aplikacje Dynamics 365**.

Aby uzyskać więcej informacji, zobacz [Uzyskanie rozwiązania dla wirtualnej encji](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution).

## <a name="register-an-azure-ad-application"></a><a name='register'></a>Rejestrowanie aplikacji Azure AD

Musisz zarejestrować aplikację Azure AD na tej samej dzierżawie co aplikacje finansowe i operacyjne, aby Dataverse mogło je wywoływać.

1. W [portalu Azure](https://portal.azure.com) przejdź do **Azure Active Directory \> rejestracja aplikacji**.
2. Wybierz opcję **Nowa rejestracja** i wprowadź następujące informacje:

    - W polu **Nazwa** wprowadź unikalną nazwę.
    - **Typ konta** — wprowadź **dowolny katalog Azure AD** (z jednym dzierżawą lub z wieloma dzierżawami).
    - **Przekierowanie URI** – Pozostaw to pole puste.

3. Wybierz opcję **Zarejestruj**.
4. Zanotuj wartość pola **Identyfikator aplikacji (klienta)**, ponieważ będzie ona potrzebna później.

    [![Identyfikator klienta aplikacji platformy Azure AD](./media/tcs-dataverse-master-data-lookup-3.png)](./media/tcs-dataverse-master-data-lookup-3.png)

5. Utwórz klucz symetryczny dla aplikacji.
6. W nowym zgłoszeniu wybierz pozycję **Certyfikaty i klucze tajne**.
7. Wybierz **Nowy klucz tajny klienta**.
8. Wprowadź opis, wybierz datę ważności, a następnie wybierz opcję **Zapisz**. Zostanie utworzony i pokazany klucz. Skopiuj wartość, aby móc ją później wykorzystać.

Aby uzyskać więcej informacji, zobacz [Zarejestruj aplikację Azure AD](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#register-the-app-in-the-azure-portal).

## <a name="grant-app-permissions-in-finance-and-operations-apps"></a><a name='grant'></a>Nadawanie uprawnień w aplikacjach finansowych i operacyjnych

Dataverse używa aplikacji Azure AD, którą utworzyłeś, aby nazwać aplikacje finansowe i operacyjne. Dlatego aplikacja musi być zaufana przez aplikacje finansowe i operacyjne oraz powiązana z kontem użytkownika o odpowiednich uprawnieniach. W aplikacjach finansowych i operacyjnych musisz utworzyć specjalnego użytkownika serwisu, który ma prawa **tylko** do funkcji wirtualnej encji. Ten użytkownik nie może mieć żadnych innych praw. Po wykonaniu tego kroku każda aplikacja posiadająca sekret utworzonej aplikacji Azure AD będzie mogła wywołać środowisko aplikacji finansowych i operacyjnych i uzyskać dostęp do funkcji wirtualnej jednostki.

1. W swoim środowisku przejdź do **Administracji systemu** \> **Użytkownicy** \> **Użytkownicy**.
2. Wybierz pozycję **Nowy**, aby dodać nowego użytkownika, i wprowadź następujące informacje o polu:

    - **Identyfikator użytkownika** – Wprowadź **dataintegration** lub inną wartość.
    - **Nazwa użytkownika** – Wprowadź **dataverse integration** lub inną wartość.
    - **Dostawca** — ustaw w tym polu wartość **NonAAD**.
    - **E-mail** – Wprowadź **dataintegration** lub inną wartość. (Wartość nie musi być prawidłowym kontem e-mail).

3. Przydziel użytkownikowi rolę bezpieczeństwa **Aplikacja jednostki wirtualnej Dataverse**.
4. Usuń wszystkie inne role, w tym **Użytkownika systemu**.
5. Wybierz kolejno opcje **Administrowanie systemem** \> **Ustawienia** \>**Aplikacje Azure Active Directory**, aby zarejestrować Dataverse. 
6. Dodaj rząd, a następnie w polu **Identyfikator klienta** wprowadź wartość **Identyfikatora aplikacji (klienta)**, którą wcześniej zanotowałeś.
7. W polu **Nazwa** wprowadź nazwę. Na przykład wpisz **Integracja Dataverse**.
8. W polu **Identyfikator użytkownika** wprowadź identyfikator użytkownika, który utworzyłeś wcześniej.

Aby uzyskać więcej informacji, zobacz [Nadawanie uprawnień aplikacjom finansowym i operacyjnym](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#grant-app-permissions-in-finance-and-operations-apps).

## <a name="configure-the-virtual-entity-data-source"></a><a name='configure'></a>Konfiguracja źródła danych jednostki wirtualnej

Musisz podać Dataverse instancję aplikacji finansowych i operacyjnych, z którą chcesz się połączyć.

1. Twoje środowisko Dataverse powinno być nadal otwarte w przeglądarce od [Krok 1. Włącz integrację Microsoft Power Platform i otwórz środowisko Dataverse](#enable). Wybierz przycisk ustawień (symbol koła zębatego) w prawym górnym rogu, a następnie wybierz **Ustawienia zaawansowane**.

    [![Otwieranie ustawień zaawansowanych w środowisku Dataverse.](./media/tcs-dataverse-master-data-lookup-4.png)](./media/tcs-dataverse-master-data-lookup-4.png)

2. W menu rozwijanym **Ustawienia** wybierz **Administracja**.

    [![Administracja.](./media/tcs-dataverse-master-data-lookup-5.png)](./media/tcs-dataverse-master-data-lookup-5.png)

3. Wybierz **Wirtualne źródła danych o podmiotach**.

    [![Wirtualne źródła danych o podmiotach.](./media/tcs-dataverse-master-data-lookup-6.png)](./media/tcs-dataverse-master-data-lookup-6.png)

4. Wybierz źródło danych o nazwie **Finanse i operacje**.

    [![Źródło danych aplikacji finansowych i operacyjnych.](./media/tcs-dataverse-master-data-lookup-7.png)](./media/tcs-dataverse-master-data-lookup-7.png)

5. Wprowadź następujące informacje z poprzednich kroków:

    - **Docelowy adres URL** – Wpisz adres URL, pod którym masz dostęp do aplikacji finansowych i operacyjnych.
    - **Adres URL OAuth** – Wprowadź `https://login.windows.net/`.
    - **Identyfikator dzierżawcy** — określ identyfikator dzierżawcy. Tą wartością może być nazwa domeny firmowej poczty elektronicznej (np. contoso.com).
    - **ID Aplikacji AAD** - Wprowadź wartość **ID aplikacji (klienta)**, która została utworzona wcześniej.
    - **Tajny klucz aplikacji AAD** - Wpisz klucz, który został wygenerowany wcześniej.
    - **Zasób AAD** — wprowadź **00000015-0000-0000-c000-000000000000**. Ta wartość to aplikacja Azure AD reprezentująca aplikacje finansowe i operacyjne. Powinna to być zawsze ta sama wartość.

6. Zapisz zmiany.
7. Zamknij stronę, aby powrócić do strony **Administracja**, gdzie rozpoczniesz [Krok 6. Włączanie wirtualnych jednostek Dataverse](#virtual).

    [![Zamykanie encji do edycji.](./media/tcs-dataverse-master-data-lookup-8.png)](./media/tcs-dataverse-master-data-lookup-8.png)

Aby uzyskać więcej informacji, zobacz [Konfiguracja źródła danych encji wirtualnej](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#configure-the-virtual-entity-data-source).

## <a name="enable-dataverse-virtual-entities"></a><a name='virtual'></a>Włączanie jednostek wirtualnych usługi Dataverse

Widoczność wirtualnych jednostek z aplikacji finansowych i operacyjnych musi być ustawiona na **Tak**, zanim zostaną one wykorzystane przez konfigurację Obliczanie podatku.

> [!NOTE]
> Możesz pominąć ten krok, włączając wirtualne jednostki związane z Obliczaniem podatków jednym kliknięciem w [Kroku 8. Skonfiguruj podłączoną aplikację do Obliczeń podatkowych](#import). Zalecamy jednak ręczne włączenie co najmniej jednej wirtualnej jednostki, aby pokazać, że połączenie między aplikacjami finansowymi i operacyjnymi a Dataverse jest dobrze ugruntowane.

1. W swoim środowisku Dataverse, na stronie **Administracja** wybierz przycisk filtra (symbol lejka) w prawym górnym rogu.

    [![Przycisk filtra.](./media/tcs-dataverse-master-data-lookup-9.png)](./media/tcs-dataverse-master-data-lookup-9.png)

2. W oknie **Zaawansowane wyszukiwanie** w polu **Szukaj** wybierz **Dostępne jednostki finansowe i operacyjne**.
3. Dodaj następującą regułę: **Nazwa** - **Zawiera** - **CompanyInfoEntity**. Wybierz opcję **Wyniki**.

    [![Zaawansowane okno wyszukiwania.](./media/tcs-dataverse-master-data-lookup-10.png)](./media/tcs-dataverse-master-data-lookup-10.png)

4. W wynikach wyszukiwania wybierz **CompanyInfoEntity**, zaznacz **Widoczny**, a następnie wybierz **Zapisz**.

    [![Ustawianie widoczności encji.](./media/tcs-dataverse-master-data-lookup-11.png)](./media/tcs-dataverse-master-data-lookup-11.png)

5. Powtórz powyższe kroki dla następujących podmiotów, które są przywoływane w konfiguracji Obliczanie podatku:

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity
    - InventOperationalSiteV2Entity
    - TaxExemptCodeEntity
    - InventWarehouseEntity

    > [!NOTE]
    > Tylko pierwsze 5 000 rekordów podmiotu może zostać pobrane przez Dataverse i udostępnione na liście rozwijanej w konfiguracji Obliczanie podatku.

Aby uzyskać więcej informacji, zobacz [Włączanie wirtualnych encji Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="set-up-the-connected-application-for-tax-calculation"></a><a name='set-up'></a>Skonfiguruj połączoną aplikację do obliczenia podatku

1. Przejdź do **Raportu elektronicznego**, a następnie w sekcji **Powiązane linki** wybierz **Podłączone aplikacje**.

    [![Połączone aplikacje.](./media/tcs-dataverse-master-data-lookup-12.png)](./media/tcs-dataverse-master-data-lookup-12.png)

2. Wybierz pozycję **Nowy**, aby dodać rekord, i wprowadź następujące informacje.

    - **Nazwa** — wprowadź nazwę.
    - **Typ** – Wybierz typ **Dataverse**.
    - **Aplikacja** — Wpisz wartość **URL środowiska** środowiska Dataverse, którą zanotowałeś w [Kroku 1. Włącz integrację Microsoft Power Platform i otwórz swoje środowisko Dataverse](#enable).
    - **Dzierżawa** — wprowadź dzierżawę.
    - **URL niestandardowy** – Wprowadź swój adres URL Dataverse i dołącz do niego **/api/data/v9.1**.

3. Wybierz **Sprawdź połączenie**, a następnie w oknie dialogowym wybierz **Kliknij tutaj, aby połączyć się z wybraną aplikacją zdalną**.

    [![Test połączenia.](./media/tcs-dataverse-master-data-lookup-13.png)](./media/tcs-dataverse-master-data-lookup-13.png)
4. Upewnij się, że otrzymujesz komunikat „Sukces” informujący o pomyślnym nawiązaniu połączenia.

    [![Komunikat o powodzeniu.](./media/tcs-dataverse-master-data-lookup-14.png)](./media/tcs-dataverse-master-data-lookup-14.png)
    
5. W systemie RCS otwórz przestrzeń roboczą **Zarządzanie funkcjami** i włącz następujące funkcje:

    - Funkcje globalizacji
    - Obsługa elektronicznych źródeł danych raportowania Dataverse
    - Obsługa źródeł danych usługi podatkowej Dataverse

## <a name="import-and-set-up-the-dataverse-model-mapping-configuration"></a><a name='import'></a>Zaimportuj i skonfiguruj plik mapowania modelu danych Dataverse

Microsoft zapewnia domyślne konfiguracje mapowania modelu dla podmiotów z aplikacji finansowych i operacyjnych do Obliczeń podatkowych.

1. W RCS **Elektroniczne Raportowanie**.
2. W sekcji **Dostawcy konfiguracji**, na kafelku dostawcy **Microsoft**, wybierz **Repozytoria**.

    [![Repozytoria.](./media/tcs-dataverse-master-data-lookup-15.png)](./media/tcs-dataverse-master-data-lookup-15.png)

3. Wybierz pozycję **Rekord repozytorium konfiguracji globalnej**, a następnie wybierz **Otwórz**.
4. W sekcji **Model danych podatkowych** \> **Model danych obliczeniowych**, wybierz konfigurację **Mapowanie modelu Dataverse**.
5. Na skróconej karcie **Wersje** wybierz wersję, która pasuje do wersji aplikacji w finansach i operacjach, a następnie wybierz pozycję **Importuj**.

    [![Importowanie konfiguracji mapowania modelu Dataverse.](./media/tcs-dataverse-master-data-lookup-16.png)](./media/tcs-dataverse-master-data-lookup-16.png)

    > [!IMPORTANT]
    > Konfiguracja **Mapowanie modelu Dataverse** jest skuteczna tylko w najwyższej zaimportowanej wersji. Dlatego nie należy importować wersji konfiguracji **Mapowanie modelu Dataverse**, która jest wyższa niż wersja konfiguracji Obliczanie podatku, którą planujesz wdrożyć. Na przykład, jeśli planujesz wdrożyć wersję 40.50.225 konfiguracji Obliczanie podatku, powinieneś zaimportować tylko wersję 40.50.13 konfiguracji **Odwzorowanie modelu Dataverse**. Nie należy importować wersji 40.54.14. W przeciwnym razie w konfiguracji wystąpi niedopasowanie modelu danych.

6. Wróć do **Raportu elektronicznego** i wybierz kafelek **Konfiguracje podatkowe**.
7. Zaznacz importowaną konfigurację **Mapowanie modelu Dataverse**, a następnie wybierz **Edytuj**.
8. Ustaw opcję **domyślnego mapowania modelu** jako **Tak**.
9. W polu **Podłączona aplikacja** wybierz podłączoną aplikację, którą skonfigurowałeś w [Kroku 7. Skonfiguruj połączoną aplikację do obliczania podatków](#set-up).
10. Ustaw opcję **Widoczność tabeli wirtualnej** na **Tak**, aby wszystkie wirtualne elementy związane z Obliczaniem podatku były widoczne.

Zakończyłeś już konfigurację funkcji wyszukiwania danych podstawowych. Lista rozwijana dla pól takich jak **Podmiot prawny**, **Konto dostawcy**, **Kod artykułu** i **Termin dostawy** z Dynamics 365 Finance będzie teraz włączona w konfiguracji **Wersji funkcji obliczania podatku**.

[![Lista rozwijana Osoba prawna](./media/tcs-dataverse-master-data-lookup-17.png)](./media/tcs-dataverse-master-data-lookup-17.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
