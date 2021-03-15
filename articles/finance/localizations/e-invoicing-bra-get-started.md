---
title: Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Brazylii
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Brazylii w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/04/2020
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
ms.openlocfilehash: 0320bd1d9e93cc30ed75f28e387ac2ec8dbfc226
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962842"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Brazylii 

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Dodatek Faktury elektroniczne dla Brazylii nie obsługuje obecnie wszystkich funkcji dostępnych w integracji dokumentu fiskalnego wbudowanej w Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.

Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Brazylii. Przeprowadza użytkownika przez kolejne etapy konfiguracji, które są zależne od kraju w usługach Regulatory Configuration Services (RCS) oraz w Finance i Supply Chain Management. Prowadzi również przez proces składania dokumentu fiskalnego NF-e (elektroniczny dokument fiskalny model 55) przez usługę i wyjaśnia, jak przeglądać wyniki przetwarzania i stan dokumentów fiskalnych.

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem kroków opisanych w tym temacie należy wykonać kroki opisane w temacie [Rozpoczynanie pracy z dodatkiem Faktury elektroniczne](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Konfiguracja RCS

Podczas instalacji RCS należy wykonać następujące zadania:

1. Importuj funkcję e-fakturowania dla dokumentów fiskalnych NF-e.
2. Przejrzyj formaty plików wymagane do przedłożenia dokumentów fiskalnych NF-e do autoryzacji.
3. Przejrzyj formaty plików wymagane do złożenia wniosku o anulowanie zatwierdzonego NF-e.
4. Skonfiguruj zdarzenie, które jest wymagane do przesłania dokumentów fiskalnych NF-e do autoryzacji.
5. Skonfiguruj zdarzenie wymagane do żądania anulowania zatwierdzonego NF-e.
6. Przypisz funkcję fakturowania elektronicznego do dodatkowego środowiska Faktury elektroniczne.
7. Opublikuj funkcję fakturowania elektronicznego.

> [!NOTE]
> „Funkcja fakturowania elektronicznego” to ogólna nazwa zasobu, który jest skonfigurowany i opublikowany w celu wykorzystania serwera dodatku Faktury elektroniczne. Konfiguracja funkcji fakturowania elektronicznego łączy między innymi wykorzystanie formatów konfiguracyjnych Raportowania elektronicznego (ER) do tworzenia konfigurowalnych plików eksportu i importu oraz wykorzystanie akcji i przepływów akcji, aby umożliwić tworzenie konfigurowalnych reguł wysyłania żądań, importuj odpowiedzi i analizuj treść odpowiedzi.

## <a name="import-the-e-invoicing-feature"></a>Importuj funkcję fakturowania elektronicznego

1. Zaloguj się do swojego konta RCS
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Fakturowanie elektroniczne**.
3. Na stronie **Funkcje fakturowania elektronicznego** wybierz opcję **Importuj** w celu zaimportowania funkcji fakturowania dokumentów fiskalnych NF-e z repozytorium globalnego.

    ![Przycisk Importuj](media/e-Invoicing-services-get-started-BRA-Select-Import-e-Invoicing-feature.png)

4. Wybierz funkcję dokumentu fiskalnego NF-e, a następnie wybierz opcję **Importuj**.

    ![Importowanie funkcji NF-e](media/e-Invoicing-services-get-started-BRA-Select-Import-NF-e-feature.png)

### <a name="create-a-new-version-of-the-nf-e-fiscal-document-feature"></a>Utwórz nową wersję funkcji dokumentu fiskalnego NF-e

- Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz **Nowa**.

![Dodawanie nowej wersji funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-BRA-Select-New-e-Invoicing-feature-version.png)

### <a name="update-the-configuration-version"></a>Aktualizacja wersji konfiguracji

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Konfiguracje** wybierz opcję **Dodaj** lub **Usuń**, aby zarządzać konfiguracjami wersji (konfiguracjami formatu pliku ER).

    ![Zarządzanie konfiguracjami funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-configurations.png)

    - Podczas tworzenia nowej wersji funkcji dokumentu fiskalnego NF-e wszystkie wersje konfiguracji (formaty plików ER) są dziedziczone z najnowszej wersji.
    - Aby przesłać dokument fiskalny NF-e w celu autoryzacji, wymagane są następujące wersje konfiguracji:

        - Format eksportu NFe przesyłania
        - Import komunikatu odpowiedzi NFe
        - Import dziennika błędów NFe

    - Aby przesłać anulowanie NF-e, wymagana jest następująca wersja konfiguracji:

        - Format eksportu anulowania NFe

2. Z listy wybierz wersję konfiguracji, a następnie wybierz opcję **Edytuj** lub **Wyświetl**, aby otworzyć stronę **Projektant formatów**, na której możesz edytować lub wyświetlić konfigurację.

    ![Otwieranie strony Projektanta formatów](media/e-Invoicing-services-get-started-BRA-Configuration-ER-fomat-designer.png)

3. Strona **Projektant formatów** umożliwia edytowanie i wyświetlanie konfiguracji plików formatu ER. Aby uzyskać więcej informacji, zobacz [Twórz konfiguracje dokumentów elektronicznych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Strona projektanta formatu](media/e-Invoicing-services-get-started-BRA-ER-Format-designer.png)

### <a name="manage-the-e-invoicing-feature-setups"></a>Zarządzaj konfiguracjami funkcji fakturowania elektronicznego

- Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** wybierz opcję **Dodaj** lub **Usuń**, aby zarządzać konfiguracjami funkcji fakturowania w systemie (tzn. zdarzeniami NF-e).

![Zarządzanie konfiguracjami funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-setup.png)

Podczas tworzenia nowej wersji funkcji dokumentu fiskalnego NF-e pochodzącej z innej funkcji fakturowania, wszystkie konfiguracje funkcji (zdarzenia NF-e) są dziedziczone z najnowszej wersji.

Aby przesłać dokumenty fiskalne NF-e do autoryzacji, wymagana jest konfiguracja funkcji **Prześlij**.

Aby przesłać anulowanie NF-e, wymagana jest konfiguracja funkcji **Anulowania**.

#### <a name="configure-the-submit-feature-setup"></a>Konfiguruj ustawienia funkcji przesyłania

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** w kolumnie **Ustawienia funkcji** wybierz opcję **Prześlij**.
2. Wybierz opcję **Edycja**.

    ![Edytuj konfigurację funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-BRA-Edit-e-Invoicing-feature-setup.png)

3. Na stronie **Ustawienia wersji funkcji** wybierz kartę **Akcje**, aby zarządzać listą akcji.

    ![Karta Akcje](media/e-Invoicing-services-get-started-BRA-Select-Actions.png)

4. Przejrzyj działania wymagane do przedłożenia NF-e do autoryzacji.

    | Identyfikator akcji | Nazwa akcji                  | Opis akcji                                                |
    |-----------|------------------------------|-------------------------------------------------------------------|
    | 1         | Przekształcanie dokumentu           | Utwórz plik XML NF-e do przesłania.                          |
    | 2         | Podpisz dokument                | Zastosuj certyfikat cyfrowy do pliku XML.                    |
    | 3         | Wywołaj usługę brazylijską SEFAZ | Prześlij podpisany plik XML do usługi sieci Web w celu autoryzacji. |
    | 4         | Przetwarzanie odpowiedzi             | Uzyskiwanie odpowiedzi usługi sieci Web.                                     |
    | 5         | Przekształcanie dokumentu           | Przeanalizuj zawartość pliku odebranego jako odpowiedź.     |
    | 6         | Przekształcanie dokumentu           | Utwórz plik XML w celu uzyskania informacji o stanie przesyłania.    |
    | 7         | Wywołaj usługę brazylijską SEFAZ | Prześlij plik XML, który żąda stanu przesłania.          |
    | 8         | Przetwarzanie odpowiedzi             | Uzyskiwanie odpowiedzi usługi sieci Web.                                     |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Ustaw adres URL dla SEFAZ usług sieci Web 

1. Na stronie **Ustawienia wersji funkcji** na karcie **Akcje** na skróconej karcie **Akcje** wybierz opcję **Wywołaj usługę brazylisją SEFAZ** (identyfikator akcji **3**).
2. Na skróconej karcie **Parametry** w polu **Parametr adresu URL**, wprowadź adres URL SEFAZ usługi sieci Web dla przesyłania NF-e.
3. Na skróconej karcie **Akcje** wybierz opcję **Wywołaj usługę brazylijską SEFAZ** (Identyfikator akcji **7**).
4. Na skróconej karcie **Parametry** w polu **Parametr adresu URL**, wprowadź adres URL SEFAZ usługi sieci Web dla przesyłania NF-e.

#### <a name="configure-the-cancellation-feature-setup"></a>Konfiguruj ustawienia funkcji anulowania

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** w kolumnie **Ustawienia funkcji** wybierz opcję **Anulowanie**.
2. Wybierz opcję **Edycja**.
3. Na stronie **Ustawienia wersji funkcji** wybierz kartę **Akcje**, aby zarządzać listą akcji.
4. Przejrzyj akcje wymagane do złożenia wniosku o anulowanie zatwierdzonego NF-e.

    | Identyfikator akcji | Nazwa akcji                  | Opis akcji                                               |
    |-----------|------------------------------|------------------------------------------------------------------|
    | 1         | Przekształcanie dokumentu           | Utwórz plik XML NF-e anulowania do przesłania.            |
    | 2         | Podpisz dokument                | Zastosuj certyfikat cyfrowy do pliku XML.                   |
    | 3         | Wywołaj usługę brazylijską SEFAZ | Prześlij podpisany plik XML do usługi sieci Web w celu anulowania. |
    | 4         | Przetwarzanie odpowiedzi             | Uzyskiwanie odpowiedzi usługi sieci Web.                                    |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Ustaw adres URL dla SEFAZ usług sieci Web

1. Na stronie **Ustawienia wersji funkcji** na karcie **Akcje** na skróconej karcie **Akcje** wybierz opcję **Wywołaj usługę brazylisją SEFAZ** (identyfikator akcji **3**).
2. Na skróconej karcie **Parametry** w polu **Parametr adresu URL**, wprowadź adres URL SEFAZ usługi sieci Web w celu anulowania zatwierdzonego NF-e

### <a name="make-an-e-invoicing-environment-available-and-assign-a-draft-version"></a>Udostępnij środowisko fakturowania elektronicznego i przypisz wersję roboczą

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Środowisko** wybierz **Włącz**.
2. W polu **Środowiska** wybierz środowisko.
3. W polu **Obowiązuje od** wybierz datę, kiedy nowe środowisko powinno zostać wprowadzone.
4. Wybierz **Włącz**.

![Włączanie środowiska fakturowania elektronicznego](media/e-Invoicing-services-get-started-BRA-Enable-e-Invoicing-environment.png)

### <a name="change-the-status-to-completed"></a>Zmień stan na Ukończone

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, która ma stan **Wersja robocza**.
2. Wybierz **Zmień status \> Zakończone**.

### <a name="change-the-status-to-publish"></a>Zmień stan na Opublikowano

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, która ma stan **Ukończono**.
2. Wybierz **Zmień status \> Opublikuj**.

![Publikowanie funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-BRA-Publish-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Skonfiguruj integrację dodatku Faktur elektronicznych w rozwiązaniach Finance lub Supply Chain Management

Podczas instalacji należy wykonać następujące zadania:

1. Włącz funkcję Federalne NF-e dla Brazylii.
2. Umożliwia zaimportowanie określonego modelu danych ER, mapowania modelu danych i formatów wymaganych dla dokumentów fiskalnych NF-e.
3. Zaimportuj konfigurację ER i skonfiguruj typy odpowiedzi, które są wymagane do zaktualizowania statusu dokumentu fiskalnego po zwróceniu procesu przedłożenia.

### <a name="turn-on-the-nf-e-federal-feature-for-brazil"></a>Włącz funkcję Federalne NF-e dla Brazylii

1. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
2. Na karcie **Funkcje** zaznacz pole wyboru **Włącz** w wierszu dla odwołania do funkcji **BR00053**.

### <a name="import-the-er-data-model-mapping-required-for-nf-e-fiscal-documents"></a>Importowanie mapowania modelu danych ER wymaganego dla dokumentów fiskalnych NF-e

1. Zaloguj się do Finance.
2. W module **Powiązane odnośniki**, w obszarze roboczym **Dostawcy konfiguracji** wybierz kafelek **Microsoft**. Upewnij się, że ten dostawca konfiguracji jest skonfigurowany jako **Aktywny**. Aby uzyskać informacje o tym, jak ustawić dostawcę jako **Aktywny**, zobacz [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Wybierz **Repozytoria**.
4. Wybierz pozycję **Zasób globalny \> Otwórz**.
5. Importowanie konfiguracji **Mapowania dokumentów fiskalnych**.

### <a name="import-er-configurations-and-set-up-the-response-types-for-fiscal-documents"></a>Importowanie konfiguracji modułu ER i konfigurowanie typów odpowiedzi dla dokumentów fiskalnych

1. W module **Powiązane odnośniki**, w obszarze roboczym **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.
2. Wybierz **Repozytoria**.
3. Wybierz pozycję **Zasób globalny \> Otwórz**.
4. Importowanie **Import dziennika błędów NF-e (BR)**, **Format importu danych odpowiedzi NF-e (BR)** i **Import komunikatu odpowiedzi NFe (BR)**.
5. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
6. Na karcie **Dokument elektroniczny** wybierz przycisk **Dodaj**.
6. W polu **Nazwa tabeli** wprowadź **Nagłówek dokumentu fiskalnego**.
7. W polu **Kontekst dokumentu** wybierz opcję **Model kontekstu faktury dla odbiorcy — kontekst dokumentu fiskalnego**.
8. Wybierz **Typy odpowiedzi**.
9. Wybierz **Nowe** i następnie w polu **Typ odpowiedzi** wybierz **Odpowiedź**.
10. W polu **Stan przesyłania** wybierz **W trakcie**.
11. W polu **Mapowanie modelu** wybierz opcję **Format importu wiadomości odpowiedzi - odwzorowanie modelu z wiadomości odpowiedzi**.
12. Wybierz opcję **Zapisz**.
13. Wybierz **Nowe** i następnie w polu **Typ odpowiedzi** wprowadź **ResponseData**.
14. W polu **Stan przesyłania** wybierz **W trakcie**.
15. W polu **Mapowanie modelu** wybierz opcję **Format importu danych odpowiedzi NF-e — Importowanie danych odpowiedzi**.
16. Wybierz opcję **Zapisz**.

## <a name="electronic-invoice-processing"></a>Przetwarzanie faktur elektronicznych

Podczas przetwarzania w Finance należy wykonać następujące zadania:

1. Umożliwia przesłanie dokumentu fiskalnego za pomocą dodatku Faktury elektroniczne.
2. Wyświetl dzienniki wykonywania przesyłania i przejrzyj wyniki przetwarzania.
3. Prześlij anulowanie dokumentu fiskalnego za pomocą dodatku Faktury elektroniczne.

### <a name="submit-nf-e-fiscal-documents-for-sefaz-authorization"></a>Prześlij dokumenty fiskalne NF-e dla autoryzacji SEFAZ 

Po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych** nie można już używać starego procesu przesyłania dokumentów fiskalnych NF-e do autoryzacji (**Proces eksportu/importu dokumentów NF-e**). Zastępuje go nowym procesem o nazwie **Prześlij dokumenty elektroniczne**.

> [!NOTE]
> Przed kontynuowaniem upewnij się, że istnieje co najmniej jeden model dokumentów fiskalnych odbiorcy 55, który został wystawiony przez zakład fiskalny odbiorcy. Kierunek dla tych dokumentów fiskalnych musi być określony jako **Wychodzący** i muszą mieć stan **Utworzony**. Aby uzyskać więcej informacji, przejrzyj [Wystawianie dokumentów fiskalnych dla odbiorców (Brazylia)](https://docs.microsoft.com/dynamics365/finance/localizations/tasks/br-00038-issuing-customer-fiscal-document).

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Prześlij dokumenty elektroniczne**.
2. W przypadku pierwszego przesłania dokumentu należy zawsze w ustawieniu opcji **Ponowne przesłanie dokumentów** wybrać wartość **Nie**. Jeśli konieczne jest ponowne przesłanie dokumentu za pośrednictwem usługi, należy skonfigurować tę opcję na wartość **Ttak**.
3. Na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj**, aby otworzyć okno dialogowe **Zapytania**, w którym można utworzyć kwerendę w celu wybrania dokumentów do przesłania.
4. Na karcie **Zakres** wybierz **Dodaj**.
5. W polu **Tabela** wybierz **Nagłówek dokumentu fiskalnego**.
6. W polu **Tabela pochodna** wybierz **Nagłówek dokumentu fiskalnego**.
6. W polu **Pole** wybierz pozycję **Numer**.
7. W polu **Kryterium** wprowadź numer dokumentu fiskalnego, który ma zostać przesłany.
8. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Zapytania**.
8. Wybierz przycisk **OK**, aby przesłać wybrane dokumenty.

> [!NOTE]
> Podczas pierwszej próby przesłania dokumentu za pośrednictwem usługi zostaniesz poproszony o potwierdzenie połączenia z dodatkiem Faktury elektroniczne. Wybierz **Kliknij tutaj, aby połaczyć się się z usługą Elektronicznego przesyłania dokumentów**.

### <a name="view-all-submission-logs"></a>Wyświetlanie wszystkich dzienników przesyłania

Po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych** dostępna jest nowa strona, na której możesz śledzić proces składania dokumentów. Możesz użyć tej strony, aby wyświetlić dzienniki przesyłania wszystkich przesłanych dokumentów.

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.
2. W polu **Typ dokumentu** wybierz opcję **Nagłówek dokumentu fiskalnego**, który ma być filtrowany tylko dla dokumentów fiskalnych.
3. W okienku akcji wybierz **Zapytania \> Szczegóły przesyłania**, aby wyświetlić szczegóły dzienników wykonywania przesyłania.

![Wyświetlanie szczegółów dziennika przesyłania](media/e-Invoicing-services-get-started-BRA-View-Submission-log-details.png)

> [!NOTE] 
> W przypadku dokumentów fiskalnych NF-e w kolumnie **Kod błędu** jest wyświetlany kod zwrotny zwrócony przez usługi sieci Web SEFAZ.

### <a name="view-submission-logs-through-the-fiscal-document-page"></a>Wyświetlanie dzienników przesyłania za pośrednictwem strony dokument fiskalny

Po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych** można również przeglądać dzienniki przesyłania, korzystając ze strony dokument fiskalny.

1. Przejdź do **Księga główna \> Zapytania i raporty \> Dokumenty fiskalne \> Wszystkie dokumenty fiskalne.**.
2. Umożliwia wybranie dokumentu fiskalnego, który został uprzednio przesłany za pomocą dodatku Faktury elektroniczne.
3. W okienku akcji na karcie **Federalne NF-e** wybierz opcję **Dziennik dokumentów elektronicznych**.

![Przeglądanie dzienników zgłoszeń ze strony dokumentu fiskalnego](media/e-Invoicing-services-get-started-BRA-View-Submission-log-from-Fiscal-document-viewer.png)

### <a name="submit-approved-nf-e-fiscal-documents-for-sefaz-cancellation"></a>Prześlij zatwierdzone dokumenty fiskalne NF-e do anulowania SEFAZ

Po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych** nie można już używać starego procesu anulowania dokumentów fiskalnych NF-e. Jest on zastępowany nowym procesem anulowania, który jest osadzony na stronie **Dziennik przsyłania dokumentów elektronicznych**.

> [!NOTE]
> Upewnij się, że zostało uruchomione anulowanie dokumentu fiskalnego odbiorcy dla zatwierdzonego dokumentu fiskalnego NF-e. Aby uzyskać więcej informacji, przejrzyj [Anulowanie dokumentów fiskalnych dla odbiorców (Brazylia)](https://docs.microsoft.com/dynamics365/finance/localizations/latam-bra-cancel-customer-fiscal-documents).

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.
2. Wybierz dokument fiskalny, a następnie wybierz **Funkcje \> Wyślij powiązane zgłoszenia**.
3. Wprowadź opis powiązanego przesyłania, a następnie kliknij przycisk **OK**.

### <a name="view-cancellation-submission-logs"></a>Wyświetlanie anulowania dzienników przesyłania

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.
2. W polu **Typ dokumentu** wybierz opcję **Nagłówek dokumentu fiskalnego**, który ma być filtrowany tylko dla dokumentów fiskalnych.
3. Wybierz dokument fiskalny, a następnie w okienku akcji wybierz **Zapytania \> Powiązane zgłoszenie**.

    Powiązane zgłoszenia to zgłoszenia związane z głównym zgłoszeniem, które zostało przesłane jako pierwsze. Na przykład przedłożenie, które autoryzuje określony NF-e, jest głównym przedłożeniem. Zgłoszenie żądające anulowania tego samego NF-e w SEFAZ jest zgłoszeniem powiązanym. Istnieje tylko, ponieważ żąda anulowania zadania, które zostało wykonane za pośrednictwem innego przesłania.

    Strona **Powiązane dokumenty** przedstawia wszystkie powiązane wnioski i ich status dla danego dokumentu fiskalnego. Na poniższej ilustracji pierwszy wiersz przedstawia przesłanie, które zażądało zatwierdzenia dokumentu fiskalnego. Drugi wiersz przedstawia zgłoszenie, które anulowało ten dokument fiskalny.

    ![Wyświetlanie anulowania dzienników przesyłania](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log.png)

4. W okienku akcji wybierz **Zapytania \> Szczegóły przesyłania**, aby wyświetlić szczegóły dzienników wykonywania przesyłania.

    ![Wyświetlanie anulowania dziennika przesyłania](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log-details.png)

## <a name="privacy-notice"></a>Klauzula prywatności
Włączenie funkcji BR-00053 (Federalne NF-e) może wymagać przesłania ograniczonych danych, w tym numeru identyfikacji podatkowej organizacji. Zostanie to przekazane agencjom zewnętrznym upoważnionym przez organ podatkowy w celu wysyłania faktur elektronicznych do tego organu podatkowego w predefiniowanym formacie wymaganym do integracji z rządową usługą internetową. Administrator może włączyć lub wyłączyć funkcję BR-00053 (Federalne NF-e), przechodząc do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**. Wybierz kartę **Funkcje**, wybierz wiersz zawierający funkcję BR-00053, a następnie dokonaj odpowiedniego wyboru. Dane importowane z tych zewnętrznych systemów do tej usługi online Dynamics 365 podlegają naszym [oświadczeniom o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcjami Uwagi dotyczące prywatności w dokumentacji funkcji dla danego kraju.


## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie dodatku Faktur elektronicznych](e-invoicing-service-overview.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne](e-invoicing-get-started.md)
- [Skonfiguruj dodatek Faktury elektroniczne](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]