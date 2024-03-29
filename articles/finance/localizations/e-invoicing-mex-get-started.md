---
title: Rozpoczynanie pracy z fakturowaniem elektronicznym dla Meksyku
description: Ten artykuł zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Meksyku.
author: gionoder
ms.date: 12/01/2020
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
ms.openlocfilehash: 46dfa03a3c90eea2d732f355396d148f475429d7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283125"
---
# <a name="get-started-with-electronic-invoicing-for-mexico"></a>Rozpoczynanie pracy z fakturowaniem elektronicznym dla Meksyku

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Faktury elektroniczne dla Meksyku może nie obsługiwać obecnie wszystkich funkcji dostępnych w dokumencie Comprobante Fiscal Digital por Internet (CFDI) i w powiązanej integracji, która jest wbudowana w Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management.

Ten artykuł zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Meksyku. Przeprowadza użytkownika przez kolejne etapy konfiguracji, które są zależne od kraju w usługach Regulatory Configuration Services (RCS) i Finance. Ponadto prowadzi użytkownika przez kroki, które należy wykonać w obszarze Finance, aby przesłać fakturę CFDI za pośrednictwem tej usługi, a także sposób przeglądu wyników przetwarzania i stanu faktur CFDI.

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem kroków opisanych w tym artykule należy wykonać kroki opisane w temacie [Rozpoczynanie pracy z administracją usługi Faktury elektroniczne](e-invoicing-get-started-service-administration.md) i [Rozpoczynanie pracy z fakturami elektronicznymi](e-invoicing-get-started.md).

## <a name="set-up-the-cadena-xslt"></a>Konfigurowanie środowiska usług Cadena XSLT

Aby dodać schemat Cadena XSLT do funkcji globalizacji w przetwarzaniu CFDI, należy wykonać następujące kroki.

1. Pobierz schemat z [witryny internetowej SAT](http://www.sat.gob.mx/sitio_internet/cfd/3/cadenaoriginal_3_3/cadenaoriginal_3_3.xslt).
2. Skompresuj schemat do pliku ZIP.
3. Zapisz plik XSLT na koncie magazynu platformy Azure ustawionym w środowisku usługi dla nowego kontenera.

## <a name="rcs-setup"></a>Konfiguracja RCS

Podczas instalacji RCS należy wykonać następujące zadania:

1. Importuj funkcję fakturowania elektronicznego do przetwarzania faktur CFDI.
2. Przejrzyj konfiguracje formatów wymagane do generowania, przesyłania i odbierania odpowiedzi na temat faktur CFDI oraz przesyłania i odbierania odpowiedzi na anulowanie.
3. Skonfiguruj zdarzenia obsługujące scenariusze przesyłania faktur CFDI.
4. Publikuj funkcję fakturowania elektronicznego do faktur CFDI.

> [!NOTE]
> „Funkcja fakturowania elektronicznego” to ogólna nazwa zasobu, który jest skonfigurowany i opublikowany w celu wykorzystania serwera Faktur elektronicznych. W takim przypadku faktura CFDI (MX) jest funkcją fakturowania elektronicznego, którą należy skonfigurować.

## <a name="import-the-e-invoicing-feature"></a>Importuj funkcję fakturowania elektronicznego

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Fakturowanie elektroniczne**.
3. Na stronie **Funkcje fakturowania elektronicznego** wybierz opcję **Importuj** w celu zaimportowania funkcji **faktury CFDI (MX)** z repozytorium globalnego.

    > [!NOTE]
    > Jeśli na liście nie ma funkcji, wybierz opcję **Synchronizuj**, a następnie powtórz krok 3.

![Importowanie funkcji fakturowania CFDI (MX).](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

Po zaimportowaniu funkcji **faktury CFDI (MX)** z repozytorium globalnego importowane są również wszystkie ustawienia funkcji, w tym konfiguracje i akcje.

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a>Utwórz nową wersję funkcji faktur CFDI (MX)

Nową wersję można utworzyć, jeśli na przykład adresy URL muszą zostać zaktualizowane. Aby uzyskać więcej informacji, zajrzyj do [faktury elektroniczne CFDI](tasks/mx-00010-e-invoicing-cfdi.md).

- Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz **Nowa**.

![Dodawanie nowej wersji funkcji fakturowania elektronicznego.](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a>Aktualizacja wersji konfiguracji

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Konfiguracje** wybierz opcję **Dodaj** lub **Usuń**, aby zarządzać konfiguracjami wersji (konfiguracjami formatu pliku ER).

    ![Zarządzanie konfiguracjami funkcji fakturowania elektronicznego.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    Podczas tworzenia nowej wersji wszystkie konfiguracje są dziedziczone z ostatniej opublikowanej wersji. Aby można było przetwarzać faktury CFDI, wymagane są następujące konfiguracje:

    - Faktura CFDI (BusinessDocumentService)
    - Import komunikatu odpowiedzi CFDI
    - Import dziennika błędów CFDI
    - Żądanie anulowania CFDI (MX) (BusinessDocumentService)
    - Faktura CFDI (BusinessDocumentService)

2. Z listy wybierz wersję konfiguracji, a następnie wybierz opcję **Edytuj** lub **Wyświetl**, aby otworzyć stronę **Projektant formatów**, na której możesz edytować lub wyświetlić konfigurację.

    ![Otwieranie strony Projektanta formatów.](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. Strona **Projektant formatów** umożliwia edytowanie i wyświetlanie konfiguracji plików formatu ER. Aby uzyskać więcej informacji, zobacz [Twórz konfiguracje dokumentów elektronicznych](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md).

    ![Strona projektanta formatu.](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Zarządzaj konfiguracjami funkcji fakturowania elektronicznego

- Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** wybierz opcję **Dodaj**, **Usuń** lub **Edytuj**, aby zarządzać konfiguracjami funkcji fakturowania w systemie.

![Zarządzanie konfiguracjami funkcji fakturowania elektronicznego.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

Aby przesłać faktury CFDI do autoryzacji (wygenerować plik XML, przesłać plik XML i przetworzyć odpowiedź), wymagane jest ustawienie funkcji **Faktura sprzedaży**.

Aby przesłać anulowanie faktury CFDI, wymagane są konfiguracje funkcji **Anulowania** i **Anuluj**.

### <a name="configure-the-sales-invoice-feature-setup"></a>Konfigurowanie ustawień funkcji faktur sprzedaży

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** w kolumnie **Ustawienia funkcji** wybierz opcję **Faktura sprzedaży**.
2. Wybierz opcję **Edytuj**, aby skonfigurować akcje, reguły stosowalności i zmienne.

    ![Edytowanie konfiguracji funkcji fakturowania elektronicznego.](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. Na stronie **Ustawienia wersji funkcji** wybierz kartę **Akcje**, aby zarządzać listą akcji. Akcje definiują listę operacji, które muszą być uruchomione w kolejności sekwencyjnej, aby wykonać pełne wykonanie zdarzenia.

    ![Karta Akcje.](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | Identyfikator akcji | Akcja                   | Nazwa akcji                                  | Opis akcji                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | 1         | Przekształć dokument       | Wygeneruj fakturę elektroniczną CFDI bez znaku cyfrowego | Generuj fakturę elektroniczą CFDI.                                |
    | 2         | Podpisz dokument            | Znak cyfrowy                                 | Podpisz cyfrowo fakturę elektroniczną do przesłania.                |
    | 3         | Wywołaj usługę meksykańskiego certyfikatu PAC | Prześlij fakturę elektroniczną CFDI                        | Klient Windows Communication Foundation (WCF) przesyła fakturę elektroniczną CFDI. |
    | 4         | Przetwarzanie odpowiedzi         | Analiza odpowiedzi usługi sieci Web                 | Przeanalizuj odpowiedź usługi sieci Web i zwróć dziennik błędów. |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a>Ustaw adres URL dla meksykańskich usług PAC sieci Web 

1. Na stronie **Ustawienia wersji funkcji** na karcie **Akcje** na skróconej karcie **Akcje** wybierz opcję **Wywołaj usługę meksykańskiego certyfikatu PAC**.
2. Na skróconej karcie **Parametry** w polu **Parametr adresu URL**, wprowadź adres URL usługi sieciowej do przesyłania faktur CFDI.

> [!NOTE]
> Wykonaj te same kroki w celu zaktualizowania adresu URL dla akcji **Wywołaj usługę meksykańskiego certyfikatu PAC** dla ustawień funkcji **Anuluj** i **Żądanie anulowania**.

### <a name="set-up-the-path-for-the-cadena-xlst-schema"></a>Ustawianie ścieżki dla schematu Cadena XSLT

1. Na stronie **Ustawienia wersji funkcji** na karcie **Zmienne** wybierz nazwę zmiennej **DigitalSignatureXSLT**.
2. W polu **Wartości** wprowadź: {"containerUrl":"https://&lt;AccountStorageName&gt;.blob.core.windows.net/&lt;ContainerName&gt;","path":"&lt;RelativePath&gt;"}
   
    gdzie: \<RelativePath\> = folder\\folder\\filename z podwójnym ukośnikiem odwrotnym, ContainerName musi oznaczać kontener używany dla usługi.
   
    Przykładową zmienną może być:
    
    {"path":"xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\\dev\\cadena_xslt","containerUrl":https://yyyyyyyyyy.blob.core.windows.net/containername}

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a>Przypisz wersję roboczą do środowiska fakturowania elektronicznego

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Środowisko** wybierz **Włącz**.
2. W polu **Środowiska** wybierz środowisko.
3. W polu **Obowiązuje od** wybierz datę, kiedy nowe środowisko powinno zostać wprowadzone.
3. Wybierz **Włącz**.

![Włączanie środowiska fakturowania elektronicznego.](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a>Zmień stan wersji na Ukończone

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, która ma stan **Wersja robocza**.
2. Wybierz **Zmień status \> Zakończone**.

## <a name="change-the-version-status-to-published"></a>Zmień stan wersji na Opublikowane

- Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz pozycję **Zmień stan \> Opublikuj**.

## <a name="publish-the-e-invoicing-feature"></a>Opublikuj funkcję fakturowania elektronicznego

1. Na stronie **Funkcje fakturowania elektronicznego** wybierz kartę **Wersje**, aby zarządzać stanem funkcji **faktury CFDI (MX)**.
2. Abyzmienić stan funkcji, wybierz opcję **Zmień stan**.

![Zmiana stanu funkcji fakturowania elektronicznego.](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing--integration-in-finance"></a>Skonfiguruj integrację Faktur elektronicznych w Finance

Aby skonfigurować Faktury elektroniczne w Finance, wykonaj następujące czynności:

1. Umożliwia zaimportowanie modelu danych ER, mapowania modelu danych ER i formatów wymaganych dla faktur CFDI.
2. Skonfiguruj typy odpowiedzi w celu zaktualizowania faktur CFDI. Te typy odpowiedzi są używane w odpowiedziach pochodzących od serwera autoryzowanego dostawcy certyfikatów (PAC).

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a>Importuj model danych modelu ER, mapowanie modelu danych ER i konfiguracje kontekstowe dla faktur CFDI

1. Zaloguj się do Finance.
2. W obszarze roboczym **Raportowanie elektroniczne** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**. Upewnij się, że ten dostawca konfiguracji jest skonfigurowany jako **Aktywny**. Aby uzyskać informacje o tym, jak ustawić dostawcę jako **Aktywny**, zobacz [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Wybierz **Repozytoria**.
4. Wybierz pozycję **Zasób globalny \> Otwórz**.
5. Importowanie **Model faktury**, **Mapowanie modelu faktury**, **Format faktury CFDI (MX)**, **Format żądania anulowania faktury CFDI (MX)** oraz **Format anulowania faktury CFDI (MX)**.

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a>Włącz funkcję przetwarzania faktur CFDI

1. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
2. Na karcie **Funkcje** zaznacz pole wyboru **Włącz** dla wierszy odnośników funkcji **MX-00010** i **MX-00016**.

![Włączanie funkcji przetwarzania faktur CFDI.](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a>Importowanie konfiguracji modułu ER i konfigurowanie typów odpowiedzi dla aktualizacji faktur CFDI

#### <a name="import-er-configurations"></a>Importowanie konfiguracji ER

1. W obszarze roboczym **Raportowanie elektroniczne** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.
3. Wybierz **Repozytoria**.
4. Wybierz pozycję **Zasób globalny \> Otwórz**.
5. Importowanie **Modelu wiadomości odpowiedzi**, **Import dziennika błędów CFDI (MX)** oraz **Import wiadomości odpowiedzi CFDI (MX)**.

#### <a name="set-up-the-response-types"></a>Konfigurowanie typów odpowiedzi

1. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
2. Na karcie **Dokument elektroniczny** wybierz przycisk **Dodaj**.
3. Wprowadź Arkusz faktur odbiorcy, a następnie w polu **Nazwa tabeli** wybierz fakturę projektu.
4. Dla każdej tabeli zdefiniuj powiązany kontekst dokumentu:

    - W przypadku **Arkusza faktur dla odbiorcy** wpisz **Kontekst faktury dla odbiorcy**.
    - W przypadku **Faktury projektu** wpisz **Kontekst faktury projektu**.

4. Wybierz **Typy odpowiedzi**, aby skonfigurować typy odpowiedzi, które mogą być zwracane z Faktur elektronicznych i uwzględnione w arkuszu faktur dla odbiorcy lub fakturze projektu.
5. Wybierz **Nowe** i następnie w polu **Typ odpowiedzi** wybierz **Odpowiedź**.
6. W polu **Stan przesyłania** wybierz **W trakcie**.
7. W polu **Mapowanie modelu** wybierz opcję **Format importu wiadomości odpowiedzi - odwzorowanie modelu z wiadomości odpowiedzi**.
8. Wybierz opcję **Zapisz**.
9. Wybierz **Nowe** i następnie w polu **Typ odpowiedzi** wybierz **ResponseData**.
10. W polu **Stan przesyłania** wybierz **W trakcie**.
11. W polu **Mapowanie modelu** wybierz opcję **Format importu danych odpowiedzi CFDI (szczegóły) - Import danych odpowiedzi**.
12. Wybierz opcję **Zapisz**.

## <a name="process-electronic-invoices-in-finance"></a>Przetwarzanie faktur elektronicznych w Finance 

Podczas przetwarzania faktur CFDI w Finance za pomocą Faktur elektronicznych możesz wykonywać następujące zadania:

- Prześlij faktury elektroniczne CFDI.
- Wyświetl dzienniki wykonywania przesyłania.
- Prześlij anulowanie faktury CFDI.

### <a name="submit-cfdi-invoices"></a>Prześlij faktury elektroniczne CFDI

Po włączeniu funkcji **Konfigurowalna integracja z Fakturami elektronicznymi** nie można już używać procesu **Eksport/Import faktury elektronicznej** (**Rozrachunki z odbiorcami \> Faktury \> Faktury elektroniczne**) do przesyłania faktrur CFDI. Zastępuje go nowym procesem o nazwie **Prześlij dokumenty elektroniczne**.

> [!NOTE]
> Przed użyciem nowego procesu **Przesyłania dokumentów elektronicznych** należy sprawdzić, czy zostało zakończone wymagane ustawienie meksykańskiego fakturowania elektronicznego. Aby uzyskać więcej informacji, zobacz [CFDI wersja układu 3.3](./latam-mex-cfdi-3-3.md).

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Prześlij dokumenty elektroniczne**.
2. W przypadku pierwszego przesłania dokumentu należy zawsze w ustawieniu opcji **Ponowne przesłanie dokumentów** wybrać wartość **Nie**. Jeśli konieczne jest ponowne przesłanie dokumentu za pośrednictwem usługi, należy skonfigurować tę opcję na wartość **Ttak**.
3. Na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj**, aby otworzyć okno dialogowe **Zapytania**, w którym można utworzyć kwerendę w celu wybrania dokumentów do przesłania.

![Przesyłanie dokumentu CFDI.](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> Podczas pierwszej próby przesłania dokumentu za pośrednictwem usługi zostaniesz poproszony o potwierdzenie połączenia z funkcją Faktury elektroniczne. Wybierz **Kliknij tutaj, aby połaczyć się się z usługą Elektronicznego przesyłania dokumentów**.

### <a name="view-submission-logs"></a>Wyświetlanie dzienników przesyłania

Dzienniki przesyłania można przeglądać dla wszystkich przesłanych dokumentów lub tylko dla jednego przesłanego dokumentu.

#### <a name="view-all-submission-logs"></a>Wyświetlanie wszystkich dzienników przesyłania

Po włączeniu funkcji **Konfigurowalna integracja z Fakturami elektronicznymi** dostępna jest nowa strona, na której możesz śledzić proces składania dokumentów. Możesz użyć tej strony, aby wyświetlić dzienniki przesyłania wszystkich przesłanych dokumentów.

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.
2. W polu **Typ dokumentu** wybierz opcję **Arkusz faktur dla odbiorcy**, aby odfiltrować wymagane dokumenty elektroniczne.

    ![Wybór typu dokumentu, aby wyświetlić dzienniki przedłożenia.](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. W okienku akcji wybierz **Zapytania \> Szczegóły przesyłania**, aby wyświetlić szczegóły dzienników wykonywania przesyłania.

    ![Wyświetlanie szczegółów dziennika przesyłania.](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

Informacje w dziennikach przesyłania dzielą się między trzy karty skrócone:

- **Przetwarzanie akcji** – Ta skrócona karta przedstawia dziennik wykonywania działań skonfigurowanych w wersji funkcji skonfigurowanej w RCS. Kolumna **Stan** wskazuje, czy akcja została pomyślnie uruchomiona.
- **Pliki akcji** – Ta skrócona karta przedstawia pliki pośrednie, które zostały wygenerowane podczas wykonywania działań. Możesz wybrać **Widok**, aby pobrać plik i wyświetlić go.
- **Dziennik akcji przetwarzania** – Ta skrócona karta przedstawia wyniki komunikacji między Fakturowaniem elektronicznym a docelową usługą internetową. Pokazuje również, co zostało zwrócone podczas przetwarzania z usługi internetowej. W kolumnie **Kod błędu** jest wyświetlany kod zwrotny zwrócony przez usługi autoryzacji sieci Web.

Po zatwierdzeniu przesłanej faktury CFDI jej stan jest aktualizowany do **Zatwierdzono**.

#### <a name="view-submission-logs-from-cfdi-invoices"></a>Wyświetl dzienniki przesyłania z faktur CFDI

Po włączeniu funkcji **Konfigurowalna integracja z Fakturami elektronicznymi** można również przeglądać dzienniki przesyłania z faktur CFDI.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Zapytania i raporty \> CFDI (faktury elektroniczne)**.
2. Wybierz fakturę CFDI, która została przesłana po włączeniu funkcji **Konfigurowalna integracja z Fakturami elektronicznymi**.
3. W okienku akcji na karcie **Historia** wybierz opcję **Dziennik dokumentów elektronicznych**.

![Wyświetlanie dzienników przesyłania z faktur CFDI.](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> Dla faktur CFDI, które zostały przesłane przed włączeniem funkcji **Konfigurowalna integracja z Fakturami elektronicznymi**, przycisk **Historia** jest dostępny. Przycisk **Historia** jest dostępny dla faktur CFDI, które zostały przesłane przed włączeniem funkcji **Konfigurowalna integracja z Fakturami elektronicznymi**.

### <a name="submit-cancellation-of-cfdi-invoices"></a>Prześlij anulowanie faktur CFDI

Po włączeniu funkcji **Konfigurowalna integracja z Fakturami elektronicznymi** nie można już używać starego procesu anulowania faktur CFDI. Jest on zastępowany nowym procesem anulowania, który jest osadzony na stronie **Dziennik przsyłania dokumentów elektronicznych**.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Zapytania i raporty \> CFDI (faktury elektroniczne)**.
2. Jeśli faktura CFDI ma stan **Zatwierdzono**, wybierz **Funkcje \> Anuluj CFDI**.
3. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.
4. Wybierz faktura CFDI, a następnie wybierz **Funkcje \> Wyślij powiązane zgłoszenia**.
5. Wprowadź opis powiązanego przesyłania, a następnie kliknij przycisk **OK**.

#### <a name="view-cancellation-submission-logs"></a>Wyświetlanie anulowania dzienników przesyłania

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.
2. W polu **Typ dokumentu** wybierz opcję **Arkusz faktur dla odbiorcy**, aby filtrować tylko dokumenty dziennika faktur klienta.
3. Wybierz fakturę CFDI, a następnie w okienku akcji wybierz **Zapytania \> Powiązane zgłoszenie**.

    Strona **Powiązane dokumenty** przedstawia wszystkie powiązane wnioski i ich status dla danej faktury CFDI. Na poniższej ilustracji pierwszy wiersz przedstawia przesłanie, które zażądało zatwierdzenia faktury CFDI. Drugi wiersz przedstawia zgłoszenie, które anulowało fakturę CFDI.

    ![Wyświetlanie anulowania dzienników przesyłania.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. W okienku akcji wybierz **Zapytania \> Szczegóły przesyłania**, aby wyświetlić szczegóły dzienników wykonywania przesyłania.

    ![Wyświetlanie anulowania dziennika przesyłania.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a>Klauzula prywatności
Włączenie i używanie funkcji **Meksykańska faktura elektroniczna CFDI (MX)** może wymagać przesłania ograniczonych danych, w tym numeru identyfikacji podatkowej organizacji. Zostanie to przekazane agencjom zewnętrznym upoważnionym przez organ podatkowy w celu wysyłania faktur elektronicznych do tego organu podatkowego w predefiniowanym formacie wymaganym do integracji z rządową usługą internetową. Administrator może włączyć lub wyłączyć funkcję **Meksykańska faktura elektroniczna CFDI (MX)**, przechodząc do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**. Wybierz kartę **Funkcje**, wybierz wiersze zawierające funkcję **Meksykańska faktura elektroniczna CFDI (MX)** a następnie dokonaj odpowiedniego wyboru. Dane importowane z tych zewnętrznych systemów do tej usługi online Dynamics 365 podlegają naszym [oświadczeniom o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcjami Uwagi dotyczące prywatności w dokumentacji funkcji dla danego kraju.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md)
- [Konfigurowanie fakturowania elektronicznego](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
