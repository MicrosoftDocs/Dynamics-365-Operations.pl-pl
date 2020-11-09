---
title: Rozpocznij pracę z dodatkiem Faktury elektroniczne
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 10/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 7b2a3aae43d42060c7fcd9e1ea3db814fc5d8f22
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039853"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Rozpocznij pracę z dodatkiem Faktury elektroniczne

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne. Po pierwsze przeprowadzi użytkownika przez etapy konfiguracji Microsoft Dynamics Lifecycle Services (usługi LCS), Regulatory Configuration Services (RCS) oraz Dynamics 365 Finance. Następnie opisuje proces przesyłania dokumentów za pośrednictwem usługi Dynamics 365 Finance lub Dynamics 365 Supply Chain Management. Dowiesz się również, jak interpretować dzienniki przesyłania.

## <a name="availability"></a>Dostępność

Dodatek do Faktur elektronicznych jest początkowo dostępny dla kilku krajów. Dodatek obsługuje tworzenie faktur elektronicznych i przesyłanie następujących dokumentów biznesowych:

| Kraj/region  | Dokument biznesowy                          |
|-----------------|--------------------------------------------|
| Austria         | Faktury sprzedaży i projektu                 |
| Belgia         | Faktury sprzedaży i projektu                 |
| Brazylia          | Elektroniczny dokument fiskalny wzór 55 (NF-e) |
| Dania         | Faktury sprzedaży i projektu                 |
| Estonia         | Faktury sprzedaży i projektu                 |
| Finlandia         | Faktury sprzedaży i projektu                 |
| Francja          | Faktury sprzedaży i projektu                 |
| Niemcy         | Faktury sprzedaży i projektu                 |
| Włochy           | Faktury sprzedaży i projektu                 |
| Meksyk          | Faktura CFDI                               |
| Holandia     | Faktury sprzedaży i projektu                 |
| Norwegia          | Faktury sprzedaży i projektu                 |
| Hiszpania           | Faktury sprzedaży i projektu                 |
| Europa          | Faktury PEPPOL sprzedaży i projektu          |
    
## <a name="licensing"></a>Licencjonowanie

Możesz użyć dodatku Faktury elektroniczne z aktualną licencją. Do korzystania z tej usługi nie są wymagane żadne dodatkowe licencje.

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem czynności opisanych w tym temacie należy spełnić następujące wymagania wstępne:

- Dostęp do swojego konta usługi LCS.
- Projekt wdrożenia LCS, który obejmuje oprogramowanie Finance lub Supply Chain Management w wersji 10.0.13 lub nowszej.
- Dostęp do swojego konta usługi RCS.
- Włącz funkcję globalizacji dla konta RCS za pomocą modułu **Zarządzanie funkcjami**. Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md)
- Utwórz zasób magazynu kluczy i konto magazynu na platformie Azure. Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto usługi Azure Storage i usługę Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="overview"></a>Omówienie

Na poniższej ilustracji przedstawiono pięć głównych kroków, które należy wykonać w tym temacie.

![Omówienie pięciu czynności opisanych w tym temacie](media/e-invoicing-services-get-started-overview-5-steps.png)

1. **Konfiguracja zasobów systemu Azure:** Skonfiguruj Magazyn Azure i przekaż certyfikaty cyfrowe w magazynie kluczy Azure.
2. **Ustawienia usługi LCS:** Zainstaluj dodatek dla mikrousług.
3. **Konfiguracja RCS:** Należy skonfigurować funkcje środowiska, dostępu użytkownika i fakturowania elektronicznego.
4. **Konfiguracja klienta:** Skonfiguruj połączenie między klientem a dodatkiem do księgowania elektronicznego, a następnie wyłącz stare funkcje przesyłania i odbierania odpowiedzi dla dokumentów elektronicznych.
5. **Prześlij faktury:** umożliwia przesyłanie dokumentów elektronicznych za pomocą dodatku elektronicznego fakturowania i przyjmowanie odpowiedzi.

> [!NOTE]
> Niektóre kroki konfiguracji w tym temacie są typowe i niezależne od kraju/regionu. Kroki i procedury konfiguracji, które są specyficzne dla kraju/regionu, są opisane w tematach specyficznych dla kraju/regionu.

## <a name="lcs-setup"></a>Konfiguracja LCS

1. Zaloguj się do swojego konta LCS.
2. Wybierz kafelek **Zarządzanie funkcjami w wersji zapoznawczej** , a w grupie pól **Funkcje w publicznych wersjach zapoznawczych** wybierz **BusinessDocumentSubmission**.
3. Zaznacz pole **Funkcja wersji zapoznawczej włączona**.
4. Wybierz projekt wdrożenia usługi LCS. Zanim będzie można wybrać projekt, musi on być uruchomiony.
5. Na skróconej karcie **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
6. Wybierz **Przesyłanie dokumentów biznesowych**.
7. W oknie dialogowym **Konfiguracja dodatku** w polu **Identyfikator aplikacji AAD** wprowadź wartość **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Ta wartość jest stałą wartością.
8. W polu **Identyfikator dzierżawy usługi AAD** wprowadź identyfikator konta subskrypcji systemu Azure.

    ![Okno dialogowe konfiguracji dodatku w LCS](media/e-invoicing-services-get-started-lcs-addin-setup.png)

9. Zaznacz pole wyboru, aby zaakceptować warunki i postanowienia.
10. Wybierz **Zainstaluj**.

## <a name="rcs-setup"></a>Konfiguracja RCS

Podczas instalacji RCS należy wykonać następujące zadania:

1. Skonfiguruj Magazyn kluczy w RCS.
2. Skonfiguruj integrację RCS z serwerem dodatkowym Faktury elektroniczne.
3. Utwórz elektroniczny środowisko obsługi fakturowania dla swojej organizacji.

### <a name="set-up-the-key-vault-in-rcs"></a>Skonfiguruj Magazyn kluczy w RCS

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji** , a następnie w obszarze **Środowiska** wybierz kafelek **Fakturowanie elektroniczne**.
3. Wybierz **Środowiska usług**.

    ![Wybieranie środowisk usługowych](media/e-invoicing-services-get-started-select-service-environments.png)

> [!NOTE]
> Opcja **Połączone aplikacje** daje dostęp do automatycznej konfiguracji dodatku Faktur elektronicznych do w Finance lub Supply Management przez RCS. Obecnie ta funkcja jest jednak w trakcie opracowywania.

4. W okienku akcji wybierz pozycję **Parametry Key Vault**.

    ![Wybieranie parametru magazynu kluczy](media/e-invoicing-services-get-started-select-key-vault-parameters.png)

5. W okienku akcji wybierz opcję **Nowe** , aby dodać magazyn kluczy.
6. W polu **Identyfikator URI magazynu kluczy** wprowadź wartość atrybutu **Nazwy DNS** zasobu magazynu kluczy skonfigurowanego na Azure. Aby uzyskać informacje o tym, gdzie znaleźć wartość **Nazwy DNS** , przejrzyj temat [Tworzenie konta magazynu systemu Azure i magazynu kluczy](e-invoicing-create-azure-storage-account-key-vault.md).

    ![Pole URI magazynu kluczy](media/e-invoicing-services-get-started-enter-key-vault-uri.png)

7. Na skróconej karcie **Certyfikaty** wybierz pozycję **Dodaj** , aby wprowadzić wszystkie cyfrowe nazwy certyfikatów i wpisy tajne magazynu kluczy potrzebne do ustanowienia zaufanego połączenia. W kolumnie **Typ** można określić, czy jest to certyfikat, czy wpis tajny. Oba zestawy wartości są skonfigurowane w zasobie magazynu kluczy na platformie Azure.

    ![Dodawanie certyfikatów](media/e-invoicing-services-get-started-add-digital-certificates.png)

8. Jeśli faktura specyficzna dla kraju/regionu wymaga użycia łańcucha certyfikatów w celu zastosowania podpisu cyfrowego, należy wybrać **Łańcuch certyfikatów** w okienku akcji, a następnie wprowadzić sekwencję certyfikatów lub klucze tajne magazynu kluczy tworzące łańcuch.

### <a name="set-up-the-rcs-integration-with-the-electronic-invoicing-add-on-server"></a>Skonfiguruj integrację RCS z serwerem dodatkowym Faktury elektroniczne

1. W module **Funkcje globalizacji** , w obszarze roboczym **Ustawienia powiązane** wybierz łącze **Parametry raportowania elektronicznego**.
2. Wybierz opcję **Kliknij tutaj, aby połączyć się z Lifecycle Service**. Jeśli nie chcesz łączyć się z usługi LCS, wybierz przycisk **Anuluj**.
3. Na karcie **Usługi fakturowania elektronicznego** , w polu **Identyfikator URI punktu końcowego usługi** wprowadź wartość zgodnie z dostępnymi regionami: `https://businessdocumentsubmission.us.operations365.dynamics.com/`lub `https://businessdocumentsubmission.eu.operations365.dynamics.com/`.
4. W polu **Identyfikator aplikacji** sprawdź, czy zawiera on identyfikator **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Ta wartość jest stałą wartością.
5. W polu **Identyfikator środowiska usługi LCS** wprowadź identyfikator konta subskrypcji LCS.

![Wprowadzanie dodatkowych parametrów Faktur elektronicznych](media/e-invoicing-services-get-started-enter-e-invoicing-parameters.png)

### <a name="add-an-electronic-invoicing-add-on-environment"></a>Dodaj środowisko dodatku Faktur elektronicznych

Istnieje możliwość tworzenia różnych środowisk dla dodatku Faktur elektronicznych, takich jak środowisko Deweloperskie, Testowe czy Produkcyjne.

1. Otwórz nowy obszar roboczy **Funkcje globalizacji** , a następnie w obszarze **Środowiska** wybierz kafelek **Fakturowanie elektroniczne**.
2. Wybierz pozycję **Nowy** , aby utworzyć środowisko.
3. W polu **Konto tokenu sygnatury dostępu Współdzielonego magazynu** wprowadź nazwę wpisu tajnego zasobu magazynu kluczy skonfigurowanego w magazynie kluczy w RCS.

    ![Pole Konto tokenu sygnatury dostępu Współdzielonego magazynu](media/e-invoicing-services-get-started-enter-sas-token-secret.png)

4. Na skróconej karcie **Użytkownicy** wybierz opcję **Nowy** , aby udzielić dostępu do użytkowników dla tego środowiska.

    ![Dodawanie użytkowników usługi](media/e-invoicing-services-get-started-enter-service-users.png)

5. W okienku akcji wybierz opcję **Publikuj** , aby opublikować środowisko na serwerze dodatku Faktury elektroniczne.

    ![Przycisk Publikuj](media/e-invoicing-services-get-started-publish-service-environment.png)

### <a name="e-invoicing-feature-setup"></a>Konfiguracja funkcji fakturowania elektronicznego

„Funkcja fakturowania elektronicznego” to ogólna nazwa zasobu, który jest skonfigurowany i opublikowany w celu wykorzystania serwera dodatku Faktury elektroniczne. Konfiguracja funkcji fakturowania elektronicznego łączy między innymi wykorzystanie formatów konfiguracyjnych Raportowania elektronicznego (ER) do tworzenia konfigurowalnych plików eksportu i importu oraz wykorzystanie akcji i przepływów akcji, aby umożliwić tworzenie konfigurowalnych reguł wysyłania żądań, importuj odpowiedzi i analizuj treść odpowiedzi.

Ze względu na różnice w formatach faktur i przepływach działań konfiguracja funkcji e-fakturowania jest zależna od kraju/regionu.

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Skonfiguruj integrację dodatku Faktur elektronicznych w rozwiązaniach Finance lub Supply Chain Management 

Podczas tej konfiguracji wykonasz następujące zadania:

1. Otwórz funkcję flighting
2. Włącz funkcję integracji dodatku Faktury elektroniczne, aby umożliwić integrację z Finance.
3. Skonfiguruj adres URL punktu końcowego dodatku Faktury elektroniczne.
4. Zaimportuj konfiguracje ER, które są powiązane z funkcją fakturowania elektronicznego specyficzną dla kraju/regionu.
5. Włącz odpowiednią funkcję fakturowania elektronicznego dla odpowiednich krajów/regionów.
6. Zaimportuj konfiguracje ER i skonfiguruj typy odpowiedzi, które są wymagane do zaktualizowania dokumentu faktury dla danego kraju / regionu w wyniku procesu przesyłania.

### <a name="open-flighted-feature"></a>Otwórz funkcję flighting
Funkcja integracji faktur elektronicznych jest włączana za pośrednictwem funkcji zwanej flighting. Flighting jest pojęciem, które domyślnie zezwala na WŁĄCZANIE i WYŁĄCZANIE funkcji. Poniższe kroki umożliwiają włączenie funkcji w środowisku nieprodukcyjnym. 

1. Wykonaj następujące polecenie SQL:

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)
    
2. Po dokonaniu powyższej zmiany należy wykonać polecenie IISReset na każdym serwerze AOS

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Funkcja integracji faktur elektronicznych jest włączana za pośrednictwem terminów wyświetlania

1. Zaloguj się do modułu Finance lub Supply Chain Management.
2. W obszarze roboczym **Zarządzanie funkcjami** wyszukaj nową funkcję, **Konfigurowalna integracja z dodatkiem Faktur elektronicznych**. Jeśli ta funkcja nadal nie jest wyświetlana na stronie Zarządzanie funkcjami, uruchom funkcję **Sprawdzania aktualizacji**
3. Wybierz funkcję, a następnie wybierz **Wyłącz teraz**.

### <a name="set-up-the-service-endpoint-url"></a>Konfigurowanie adresu URL punktu końcowego usługi

1. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
2. Na karcie **Usługa przesyłania** w polu **Identyfikator URL punktu końcowego usługi** wprowadź wartość `https://businessdocumentsubmission.us.operations365.dynamics.com/`.
3. W polu **Środowisko** wprowadź nazwę środowiska dodatkowego Faktury elektroniczne, które zostało utworzone podczas konfiguracji RCS..

![Wprowadzanie parametrów usługi](media/e-invoicing-services-get-started-enter-service-endpoint.png)

### <a name="import-the-er-configurations"></a>Importowanie konfiguracji ER

Aby umożliwić zbieranie i wysyłanie danych biznesowych do dodatku Faktury elektroniczne, należy zaimportować model danych ER i konfigurację modelu danych ER, które są powiązane z funkcją e-fakturowania specyficzną dla kraju / regionu, której chcesz użyć.

1. W module **Powiązane odnośniki** , w obszarze roboczym **Dostawcy konfiguracji** wybierz kafelek **Microsoft**. Upewnij się, że ten dostawca konfiguracji jest skonfigurowany jako **Aktywny**. Aby uzyskać informacje o tym, jak ustawić dostawcę jako **Aktywny** , zobacz [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Wybierz **Repozytoria**.
4. Wybierz opcję **Zasób globalny** , a następnie wybierz opcję **Otwórz**.
5. W oknie dialogowym **Połącz z Lifecycle Services** wybierz opcję **Kliknij tutaj, aby połączyć się z Lifecycle Service**.
6. W zależności od kraju lub regionu, w którym chcesz korzystać z funkcji fakturowania elektronicznego, musisz zaimportować odpowiedni model danych, mapowanie modelu danych i formaty. Aby uzyskać informacje o konfiguracjach ER, które należy zaimportować, zobacz temat „Wprowadzenie do dodatku Faktury elektroniczne” dla danego kraju / regionu.
7. Importowanie **Modelu kontekstu faktury dla odbiorcy**. Model ten zawiera dodatkowe parametry, które opisują między innymi środowisko w Finance, które jest używane dla dodatku Faktury elektroniczne podczas przesyłania danych biznesowych.

### <a name="turn-on-countryregion-specific-e-invoicing-features"></a><a name="region-specific"></a>Włącz funkcje fakturowania elektronicznego dla odpowiednich krajów/regionów

Aby włączyć funkcje e-fakturowania specyficzne dla kraju / regionu, tak aby działały z dodatkiem Faktury elektroniczne, musisz włączyć tę funkcję w każdej firmie, w której chcesz jej używać. Później nie można już korzystać ze starej integracji fakturowania elektronicznego, a integracja z nowym dodatkiem Faktury elektroniczne jest włączona.

1. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
2. Na karcie **Funkcje** w wierszu funkcji powiązanej z określoną funkcją fakturowania elektronicznego dla danego kraju/regionu zaznacz pole wyboru w kolumnie **Włączone**. Aby uzyskać informacje o funkcjach, które należy włączyć, zobacz temat „Wprowadzenie do dodatku Faktury elektroniczne” dla danego kraju / regionu.

![Włączanie funkcji fakturowania elektronicznego](media/e-invoicing-services-get-started-enable-invoicing-feature.png)

> [!NOTE]
> Jeśli masz wiele firm skonfigurowanych dla różnych krajów lub regionów, możesz włączyć funkcję e-fakturowania specyficzną dla kraju / regionu dla każdej firmy.

### <a name="import-er-configurations-and-set-up-the-response-types-to-update-your-countryregion-specific-invoice-document"></a>Zaimportuj konfiguracje ER i skonfiguruj typy odpowiedzi, aby zaktualizować dokument faktury dla danego kraju / regionu

Jeśli przesłany dokument faktury wymaga aktualizacji po przesłaniu odpowiedzi do rządowych służb autoryzacyjnych, należy zaimportować specjalny model danych ER i konfiguracje, aby umożliwić aktualizację statusu dokumentu faktury lub dowolnego innego dodatkowego pola.

1. W module **Powiązane odnośniki** , w obszarze roboczym **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.
2. Wybierz **Repozytoria**.
3. Wybierz opcję **Zasób globalny** , a następnie wybierz opcję **Otwórz**.
4. Importuj **Model wiadomości odpowiedzi** , **Format importu wiadomości odpowiedzi** , **Mapowanie modelu komunikatów odpowiedzi do miejsca docelowego** i **Format importu zawartości pliku**.
5. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
6. Na karcie **Dokument elektroniczny** wybierz opcję **Dodaj** , aby wprowadzić nazwę tabeli powiązanej z danym dokumentem faktury specyficznym dla danego kraju/regionu. Aby uzyskać informacje o nazwach tabeli, które należy wybrać, zobacz temat „Wprowadzenie do dodatku Faktury elektroniczne” dla danego kraju / regionu.
7. Wybierz **Typy odpowiedzi** , aby skonfigurować typy odpowiedzi. Aby uzyskać informacje o nazwach tabeli, które należy wybrać, zobacz temat „Wprowadzenie do dodatku Faktury elektroniczne” dla danego kraju / regionu.

![Konfigurowanie typów odpowiedzi](media/e-invoicing-services-get-started-set-up-response-types.png)

## <a name="e-invoicing-feature-names-by-country"></a>Nazwy funkcji fakturowania elektronicznego według krajów 
W poniższej tabeli opisano inne funkcje fakturowania elektronicznego dostępne do pobrania z globalnego repozytorium raportów elektronicznych w celu wygenerowania faktur elektronicznych.
W RCS możesz pobrać funkcje e-fakturowania wymienione w tej tabeli, konfiguracje ER oraz dostępne konfiguracje funkcji e-fakturowania.
W module Finanse można włączyć odpowiednie odwołania do funkcji na stronie **Parametry dokumentu elektronicznego** , aby wystawić faktury elektroniczne dla tych krajów. Aby uzyskać więcej informacji, zajrzyj do sekcji [Włącz funkcje fakturowania elektronicznego dla odpowiednich krajów/regionów](#region-specific) znajdującej się we wcześniejszej części tego tematu.

| Nazwa funkcji                      | opis                                 | Konfiguracje ER                                                                                                  | Konfiguracje                                                                                                                                                         | Kraj/region  | Odwołanie do funkcji      |
|-----------------------------------|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|------------------------|
| Faktury elektroniczne w Austrii (AT) | Faktury sprzedaży i projektów dla Austrii      | - Faktura sprzedaży OIOUBL <br>- Faktura za projekt OIOUBL <br>- OIOUBL Faktura korygująca za sprzedaż <br>- Faktura korygująca za projekt OIOUBL | - Generowanie faktury sprzedaży (AT) <br>- Generowanie faktury projektu (AT) <br>- Generowanie faktury korygującej sprzedaży (AT) <br>- Generowanie faktury korygującej projektu (AT)         | Austria         | EUR-00023              |
| Faktura elektroniczna w Belgii (BE)   | Faktury sprzedaży i projektów dla Belgii      | - Faktura sprzedaży UBL BE <br>- Faktura projektu UBL BE <br>- Faktura korygująca za projekt UBL BE <br>- Faktura korygująca sprzedaż UBL BE | - Generowanie faktury sprzedaży (BE)<br>- Generowanie faktury projektu (BE) <br>- Generowanie faktury korygującej sprzedaży (BE) <br>- Generowanie faktury korygującej projektu (BE)         | Belgia         | EUR-00023              |
| Duńska faktura elektroniczna (DK)    | Faktury sprzedaży i projektów dla Danii      | - Faktura sprzedaży OIOUBL <br>- Faktura za projekt OIOUBL <br>- OIOUBL Faktura korygująca za sprzedaż <br>- Faktura korygująca za projekt   OIOUBL | - Generowanie faktury sprzedaży (DK) <br>- Generowanie faktury projektu (DK) <br>- Generowanie faktury korygującej sprzedaży (DK)<br>- Generowanie faktury korygującej projektu (DK)         | Dania         | EUR-00023<br> DK-00001 |
| Holenderska faktura elektroniczna (NL)     | Faktury sprzedaży i projektów dla Holandii  | - Faktura sprzedaży UBL NL <br>- Faktura projektu UBL NL <br>- Faktura korygująca sprzedaż UBL NL <br>- Faktura korygująca za projekt   UBL NL | - Generowanie faktury sprzedaży (NL) <br> - Generowanie faktury projektu (NL) <br> - Generowanie faktury korygującej sprzedaży (NL) <br>- Generowanie faktury korygującej projektu (NL)          | Holandia | EUR-00023              |
| Estońska faktura elektroniczna (EE)  | Faktury sprzedaży i projektów dla Estonii      | - Faktura sprzedaży (EE) <br> - Faktura projektu (EE)                                                                     | - Generowanie faktury sprzedaży (EE) <br>- Generowanie faktury projektu (EE)                                                                                           | Estonia         | EUR-00023              |
| Fińska faktura elektroniczna (FI)   | Faktury sprzedaży i projektów dla Finlandii      | - Faktura sprzedaży (FI) <br>- Generowanie faktury projektu (FI)                                                          | - Generowanie faktury sprzedaży (FI) <br>- Generowanie faktury projektu (FI)                                                                                           | Finlandia         | EUR-00023              |
| Francuska faktura elektroniczna (FR)    | Faktury sprzedaży i projektów dla Francji    | - Faktura sprzedaży UBL FR <br> - Faktura projektu UBL FR <br> - Faktura korygująca sprzedaż UBL FR <br>- Faktura korygująca za projekt   UBL FR | - Generowanie faktury sprzedaży (FR) <br> - Generowanie faktury projektu (FR) <br>- Generowanie faktury korygującej sprzedaży (FR) <br>- Generowanie faktury korygującej projektu (FR)         | Francja          | EUR-00023              |
| Niemiecka faktura elektroniczna (DE)    | Faktury sprzedaży i projektów dla Niemiec      |- Faktura sprzedaży (DE) <br> - Faktura projektu <DE>                                                                     | - Generowanie faktury sprzedaży (DE) <br>- Generowanie faktury projektu (DE)                                                                                           | Niemcy         | EUR-00023              |
| Norweska faktura elektroniczna (NIE) | Faktury sprzedaży i projektów dla Norwegii       | - Faktura sprzedaży OIOUBL <br>- Faktura za projekt OIOUBL <br>- OIOUBL Faktura korygująca za sprzedaż <br>- Faktura korygująca za projekt OIOUBL | - Generowanie faktury sprzedaży (NO) <br>- Generowanie faktury projektu (NO) <br>- Generowanie faktury korygującej sprzedaży (NO) <br>- Generowanie faktury korygującej projektu (NO)          | Norwegia          | EUR-00023<br> NO-00010 |
| Hiszpańska faktura elektroniczna (ES)   | Faktury sprzedaży i projektów dla Hiszpanii        | - Faktura sprzedaży (ES) <br>- Faktura projektu (ES)                                                                     | - Generowanie faktury sprzedaży (ES) <br>- Generowanie faktury projektu (ES)                                                                                           | Hiszpania           | EUR-00023 <br>ES-00025 |
| Włoska faktura elektroniczna (IT)   | Faktury sprzedaży i projektów dla Włoch        | - (Podgląd) faktura sprzedaży (IT) <br> - Faktura projektu (IT)                                                           | - Faktura sprzedaży <br> - Faktura   projektu                                                                                                                           | Włochy           | EUR-00023 <br>IT-00036 |
| Faktura elektroniczna PEPPOL         | PEPPOL Generowanie faktur sprzedaży i projektów | - Faktura sprzedaży PEPPOL <br>- Faktura za projekt PEPPOL <br>- PEPPOL Faktura korygująca za sprzedaż <br> - Faktura korygująca za projekt   PEPPOL | - Generowanie faktury sprzedaży PEPPOL <br>- Generowanie faktury projektu PEPPOL <br>- Generowanie faktury korygującej sprzedaży PEPPOL <br>- Generowanie faktury korygującej projektu PEPPOL |                 | EUR-00023              |


## <a name="electronic-invoice-processing-in-finance-and-supply-chain-management"></a>Przetwarzanie faktur elektronicznych w Finance i Supply Chain Management

Podczas przetwarzania należy wykonać następujące zadania:

1. Umożliwia przesłanie dokumentu biznesowego (faktury) za pomocą dodatku Faktury elektroniczne.
2. Wyświetl dzienniki wykonywania przesyłania.

### <a name="submit-business-documents"></a>Prześlij dokumenty biznesowe

Podczas zwykłego procesu przesyłania komunikacja między klientem a dodatkiem Faktury elektroniczne odbywa się dwukierunkowo. Celem jest wykonanie dwóch głównych zadań podczas przesyłania dokumentów elektronicznych:

1. Wyślij wszystkie dokumenty elektroniczne, które oczekują na przesłanie z Finance i mają prawidłowy stan do przesłania oraz spełniają kryteria wyboru.
2. Zaimportuj do programu Finance odpowiedź zwróconą przez dodatek Faktury elektroniczne dla wcześniej przesłanych dokumentów elektronicznych. Po zaimportowaniu są analizowane odpowiedzi, a stan dokumentów biznesowych zostanie odpowiednio zaktualizowany.

Dokumenty biznesowe można przesyłać ręcznie lub na podstawie wymagań harmonogramu.

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Prześlij dokumenty elektroniczne**.
2. W przypadku pierwszego przesłania dokumentu należy zawsze w ustawieniu opcji **Ponowne przesłanie dokumentów** wybrać wartość **Nie**. Jeśli konieczne jest ponowne przesłanie dokumentu za pośrednictwem usługi, należy skonfigurować tę opcję na wartość **Ttak**.
3. Na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj** , aby otworzyć okno dialogowe **Zapytania** , w którym można utworzyć kwerendę w celu wybrania dokumentów do przesłania.

![Przesyłanie dokumentów elektronicznych, okno dialogowe](media/e-invoicing-services-get-started-submission-form.png)

### <a name="filter-query"></a>Kwerenda filtra

1. W oknie dialogowym **Zapytanie** na karcie **Zakres** wprowadź kryteria filtrowania, używającpól **Tabela** , **Tabela pochodna** , **Pole** i **Kryteria**.
2. Wybierz przycisk **Dodaj** , aby dodać dowolną liczbę dodatkowych kryteriów wymaganych do wybrania dokumentów biznesowych.

    ![Konfigurowanie kryteriów filtru przesyłania](media/e-invoicing-services-get-started-set-up-submission-filter-criteria.png)

3. Kliknij przycisk **OK** , aby zamknąć okno dialogowe **Zapytania**.
4. Wybierz **OK** , aby przesłać wybrane dokumenty biznesowe do dodatku Faktury elektroniczne.

    > [!NOTE]
    > Podczas pierwszej próby przesłania dokumentu za pośrednictwem usługi zostaniesz poproszony o potwierdzenie połączenia z dodatkiem Faktury elektroniczne. Wybierz **Kliknij tutaj, aby połaczyć się się z usługą Elektronicznego przesyłania dokumentów**.
    >
    > ![Połącz się ze skrzynką komunikatów usługi elektronicznego przesyłania dokumentów](media/e-invoicing-services-get-started-dialog-form-connect-e-Invoicing-services.png)
    >
    > Jeśli połączenie zakończy się pomyślnie, zostanie wyświetlony komunikat z potwierdzeniem.
    >
    > ![Potwierdzenie połączenia z dodatkiem Faktury elektroniczne](media/e-invoicing-services-get-started-confirmation-connection-e-invoicing-services.png)

5. Zamknij okno dialogowe.

> [!NOTE]
> Po każdym przesłaniu w centrum akcji zostanie wyświetlona liczba przesłanych dokumentów.
>
> ![Komunikaty centrum akcji](media/e-invoicing-services-get-started-view-action-center-messages.png)

### <a name="submission-by-batch"></a>Przesłanie według partii

Zamiast ręcznie przesyłać dokumenty, możesz zautomatyzować proces przesyłania i uruchomić go w tle, w oparciu o skonfigurowaną częstotliwość wykonywania partii.

1. W okienku dialogowym **Prześlij dokumenty elektroniczne** na skróconej karcie **Uruchom w tle ustaw** wartość opcji **Przetwarzanie wsadowe** na **Tak**.
2. Na karcie **Cykl** skonfiguruj częstotliwość przetwarzania wsadowego.

![Konfigurowanie przesyłania według partii](media/e-invoicing-services-get-started-set-up-submission-batch.png)

### <a name="view-all-submission-logs"></a>Wyświetlanie wszystkich dzienników przesyłania

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.
2. W polu **Typ dokumentu** wybierz typ dokumentu, według którego ma być filtrowany filtr.

    ![Wybieranie typu dokumentu, dla którego mają być wyświetlone dzienniki przesyłania](media/e-invoicing-services-get-started-select-document-type-for-viewing-submission-log.png)

    > [!IMPORTANT]
    > Wartość wyświetlana w kolumnie **Stan przesyłania** reprezentuje stan związany z ukończeniem procesu przesyłania. Wskazuje on, czy przepływ akcji skonfigurowanych w RCS został uruchomiony do końca, niezależnie od tego, czy dokument elektroniczny został zatwierdzony czy odrzucony. Wartość w kolumnie **Stan przesyłania** nie reprezentuje stanu przesłanego dokumentu. Stan przesłanego dokumentu (czyli czy dokument został zatwierdzony, czy odrzucony) można wyświetlić na skróconej karcie **Dziennik czynności przetwarzania** w szczegółach dziennika przesyłania, zgodnie z opisem poniżej.

3. W okienku akcji wybierz **Zapytania \> Szczegóły przesyłania**.
4. Wyświetl szczegóły dziennika przesyłania.

    ![Szczegóły dziennika przesyłania](media/e-invoicing-services-get-started-view-submission-log-form.png)

Wyniki wyświetlane w dzienniku przedłożeń zależą od konfiguracji funkcji fakturowania elektronicznego w RCS. Jednak niezależnie od konfiguracji, dziennik przesyłania zawsze ma trzy karty skrócone:

- **Przetwarzanie akcji** – Ta skrócona karta przedstawia dziennik wykonywania działań skonfigurowanych w wersji funkcji skonfigurowanej w RCS. Kolumna **Stan** wskazuje, czy akcja została pomyślnie uruchomiona.
- **Pliki akcji** – Ta skrócona karta przedstawia pliki pośrednie, które zostały wygenerowane podczas wykonywania działań. Możesz wybrać **Widok** , aby pobrać plik i wyświetlić jego zawartość.
- **Dziennik akcji przetwarzania** – Ta skrócona karta przedstawia wyniki komunikacji między dodatkiem Fakturowanie elektroniczne a docelową usługą internetową. Pokazuje także, co zostało zwrócone przez usługę sieci Web przetwarzania.

## <a name="related-topics"></a>Powiązane tematy

- [Omówienie dodatku Faktur elektronicznych](e-invoicing-service-overview.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Brazylii](e-invoicing-bra-get-started.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Meksyku](e-invoicing-mex-get-started.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Włoch](e-invoicing-ita-get-started.md)
- [Skonfiguruj dodatek Faktury elektroniczne](e-invoicing-setup.md)
