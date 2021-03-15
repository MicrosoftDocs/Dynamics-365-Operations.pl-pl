---
title: Skonfiguruj dodatek Faktury elektroniczne
description: W tym temacie opisano sposób konfigurowania dodatku Faktur elektronicznych w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
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
ms.openlocfilehash: 0561a3307f8b990c06dd25c9fc3fd7097254061f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988485"
---
# <a name="set-up-the-electronic-invoicing-add-on"></a>Skonfiguruj dodatek Faktury elektroniczne

[!include [banner](../includes/banner.md)]


Konfiguracja funkcji dodatku dla faktur elektronicznych to proces tworzenia wymaganej konfiguracji za pośrednictwem środowiska Regulatory Configuration Services (RCS) i publikowania tej konfiguracji na serwerze dodatku Faktury elektroniczne. Konfiguracja umożliwia tworzenie konfigurowalnych reguł, które umożliwiają dodatkowi Faktury elektroniczne używanie bezpiecznego protokołu przez Internet do komunikacji i wymiany danych z podmiotami zewnętrznymi za pośrednictwem usług internetowych.

Konfigurowalność opiera się na konfiguracji formatu raportowania elektronicznego (ER) jako środka do tworzenia treści, która jest wysyłana i odbierana za pośrednictwem plików cyfrowych. Zależy także od aranżacji akcji komunikacyjnych do wysyłania żądań i odbierania odpowiedzi z usług sieci Web innych firm bez konieczności pisania kodu.

## <a name="overview"></a>Omówienie

„Funkcja dodatku Faktury elektroniczne” to ogólna nazwa zasobu, który jest skonfigurowany i opublikowany w celu wykorzystania serwera dodatku Faktury elektroniczne. Konfiguracja funkcji łączy między innymi wykorzystanie formatów konfiguracyjnych ER do tworzenia konfigurowalnych plików eksportu i importu oraz wykorzystanie akcji i przepływów akcji, aby umożliwić tworzenie konfigurowalnych reguł wysyłania żądań, importuj odpowiedzi i analizuj treść odpowiedzi.

Na poniższej ilustracji przedstawiono główne składniki funkcji dodatkowej Faktury elektroniczne.

![Omówienie funkcji dodatku Faktur elektronicznych](media/e-Invoicing-services-feature-setup-Overview-e-Invoicing-feature.png)

Z powodu różnic w formatach faktur i przepływach akcji ustawienia funkcji mogą być różne w zależności od kraju lub regionu lub zgodnie z wymaganiami biznesowymi.

## <a name="set-up-the-electronic-invoicing-add-on-feature"></a>Skonfiguruj funkcje dodateku Faktury elektroniczne

Proces instalacji musi zostać ukończony w środowisku RCS. Wykonaj poniższe czynności, aby utworzyć nową funkcję dodatku Faktury elektroniczne.

1. Zaloguj się do swojego środowiska RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Dodatek Faktury elektroniczne**.
3. Na stronie **Funkcje dodatku Faktur elektronicznych** wybierz opcję **Importuj**, aby zaimportować konfigurację modelu danych ER z repozytorium globalnego.
4. Wybierz przycisk **Dodaj**, aby utworzyć elektroniczną funkcję dodawania dodatków do fakturowania. Funkcję można utworzyć od podstaw lub wyprowadzić z istniejącej funkcji dodatku Faktury elektroniczne.

    ![Dodawanie funkcji dodatku Faktur elektronicznych](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature.png)

> [!NOTE]
> Podczas tworzenia nowej funkcji dodawania dodatku Faktur elektronicznych jest ona ustawiona na numer wersji, a jej domyślnym stanem jest **Wersja robocza**.

### <a name="configurations"></a>Konfiguracje

Konfiguracje zawierają konfiguracje formatu ER, które są wymagane do przekształceń i tworzenia plików, które będą wymieniane podczas komunikacji z usługami sieci Web innych firm. Funkcja dodatkowa Faktury elektroniczne może mieć dowolną liczbę konfiguracji formatu pliku ER, jaka jest wymagana, w oparciu o specyfikację techniczną integracji dostarczoną przez dostawcę usług internetowych.

Wykonaj poniższe czynności, aby dodać formaty ER do funkcji dodatku Faktury elektroniczne.

1. Na stronie **Funkcje dodatku Faktur elektronicznych** na karcie **Konfiguracje** wybierz opcję **Dodaj**, aby dodać konfiguracje formatów plików ER dla funkcji dodatku Faktur elektronicznych.

    ![Dodawanie konfiguracji funkcji dodatku Faktur elektronicznych](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Podczas tworzenia od podstaw funkcji dodatku Faktury elektroniczne należy ręcznie dodać wszystkie konfiguracje formatu pliku ER. W przypadku wyprowadzenia funkcji dodatku Faktury elektroniczne z istniejącej funkcji konfiguracje formatu pliku ER są tworzone automatycznie, ponieważ są dziedziczone z oryginalnej funkcji dodatku Faktury elektroniczne.

2. Wybierz opcję **Edytuj**, aby otworzyć stronę **Projektant formatów**, na której możesz edytować konfigurację formatu pliku ER.

    ![Edytowanie konfiguracji funkcji dodatku Faktur elektronicznych](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Podczas edytowania formatu stan wersji konfiguracji jest ustawiany na **Wersja robocza**.

3. Strona **Projektant formatów** umożliwia zmianę konfiguracji pliku formatu ER. Aby uzyskać więcej informacji, zobacz [Twórz konfiguracje dokumentów elektronicznych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Strona projektanta formatu](media/e-Invoicing-services-feature-setup-ER-Format-designer.png)

### <a name="feature-setups"></a>Konfiguracje funkcji

Konfiguracje funkcji zawierają reguły komunikacji i zabezpieczeń z usługą sieci Web innej firmy. Dodatkowa funkcja Faktury elektroniczne może mieć tyle konfiguracji funkcji, ile jest wymaganych, w oparciu o regułę biznesową, którą chcesz zrealizować.

Wykonaj poniższe czynności, aby dodać ustawienia funkcji do funkcji dodatku Faktury elektroniczne.

1. Na stronie **Funkcje dodatku Faktur elektronicznych** na karcie **Ustawienia** wybierz opcję **Dodaj**, aby dodać ustawienia funkcji dla funkcji dodatku Faktur elektronicznych.

    ![Dodawanie ustawień funkcji dodatku Faktur elektronicznych](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Setups.png)

    > [!NOTE]
    > Podczas tworzenia od podstaw funkcji dodatku Faktury elektroniczne należy ręcznie dodać wszystkie wymagane ustawienia funkcji. W przypadku wyprowadzenia funkcji dodatku Faktury elektroniczne z istniejącej funkcji, wszystkie ustawienia funkcji są tworzone automatycznie, ponieważ są dziedziczone z oryginalnej funkcji dodatku Faktury elektroniczne.

2. Wybierz opcję **Edytuj**, aby edytować ustawienia wersji funkcji.

    ![Edycja ustawień funkcji dodatku Faktur elektronicznych](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Setups.png)

3. Strona **Ustawienia wersji funkcji** umożliwia konfigurowanie akcji, reguł stosowania i zmiennych.

    ![Akcje, reguły stosowalności i zmienne](media/e-Invoicing-services-feature-setup-View-Actions-Applicability-Rules-Variables.png)

### <a name="actions"></a>Akcje

Akcje to wstępnie zdefiniowana lista operacji, która jest uruchamiana w kolejności sekwencyjnej. Ta lista przedstawia podział kroków, które są wymagane do pełnego wykonania funkcji dodatku Faktury elektroniczne. Akcje mogą obejmować, w tej samej funkcji dodatku Faktury elektroniczne, komunikację w obu kierunkach: wysyłanie zapytania o miejsce docelowe oraz otrzymywanie odpowiedzi i analizowanie jej treści.

Każda akcja zawiera predefiniowaną listę parametrów, które są wymagane, aby akcja osiągnęła swój cel. Opcjonalnie można podać dodatkowe parametry.

#### <a name="actions-fasttab"></a>Skrócona karta Akcje

Na stronie **Ustawienia wersji funkcji** na karcie **Akcje** na skróconej karcie **Akcje** wykonaj jedną lub obie kroki, aby zarządzać akcjami:

- Wybierz opcję **Nowy** lub **Usuń**, aby dodać nowe akcje lub usunąć istniejące akcje.
- Wybierz opcję **W górę** lub **W dół**, aby przenieść wybrane akcje w górę lub w dół w siatce, a więc zmień kolejność, w jakiej są uruchamiane. Akcje są uruchamiane w kolejności, w jakiej są wyświetlane w siatce, od góry do dołu.

![Zarządzanie akcjami](media/e-Invoicing-services-feature-setup-Manage-Actions.png)

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Akcje**.

| Pole        | opis |
|--------------|-------------|
| Akcja       | Istnieje osiem wstępnie zdefiniowanych akcji.<ul><li><strong>Podpisz dokument</strong></li><li><strong>FileStoreActionName</strong></li><li><strong>Przekształcanie dokumentu</strong></li><li><strong>Przetwarzanie odpowiedzi</strong></li><li><strong>Wywołaj usługę sieci Web REST</strong></li><li><strong>Wywołaj usługę meksykańskiego certyfikatu PAC</strong></li><li><strong>Wywołaj usługę brazylijską SEFAZ</strong></li><li><strong>Wywołaj włoską usługę SDI</strong></li></ul> |
| Nazwa akcji  | Nazwa akcji i jej kolejność wykonywania. |
| opis  | Opis akcji. |
| Włącz ponawianie próby | Zaznaczone pole wyboru wskazuje, że akcja może zostać ponowiona, jeśli poprzednia próba nie powiedzie się. |
| Wykonaj ponownie akcję | W przypadku ponownej próby akcja, od której rozpoczyna się ponowienie. Ponowna próba zostanie zakończona dla bieżącej akcji (włącznie z ponowną próbą). W przypadku akcji, które je zawierają, parametry **Minimalne wycofanie** i **Maksymalne wycofanie** określają minimalną liczbę i maksymalną liczbę ponownych prób. |

#### <a name="parameters-fasttab"></a>Skrócona karta Parametry

Na skróconej karcie **Parametry** wyświetlają parametry akcji wybranej na skróconej karcie **Akcje**.

![Skrócona karta Parametry](media/e-Invoicing-services-feature-setup-View-Actions-Parameters.png)

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Parametry**.

| Pole       | opis |
|-------------|-------------|
| Imię i nazwisko        | Wstępnie zdefiniowana lista parametrów. Aby uzyskać więcej informacji, zajrzyj do sekcji [Lista parametrów według akcji](#list-of-parameters-by-action). |
| opis | Opis parametru. |
| Wartość       | Wartość parametru. |

#### <a name="list-of-parameters-by-action"></a>Lista parametrów według akcji

Dostępne parametry różnią się w zależności od akcji wybranej na skróconej karcie **Akcji**.

###### <a name="action-sign-document"></a>Akcja: Podpisz dokument

| Parametr                             | opis |
|---------------------------------------|-------------|
| Plik importu                            | Wejściowy plik dokumentu XML, który musi być podpisany za pomocą podpisu elektronicznego. |
| Nazwa certyfikatu                      | Nazwa certyfikatu w magazynie. |
| Typ podpisu                        | Typ podpisu, który ma być używany. |
| Nazwa metody podpisu                 | Nazwa metody podpisu, która jest używana do generowania podpisu elektronicznego. |
| Nazwa metody skrótu                    | Metoda skrótu używana do generowania ciągu skrótu w podpisie cyfrowym. |
| Nazwa metody konwertowania kanonicznego          | Metoda konwertowania kanonicznego używana do obliczania skrótu podpisu. |
| Nazwa atrybutu odwołania              | Nazwa atrybutu wskazująca miejsce wstawienia identyfikatora odwołania do elementu podpisu. |
| Nazwa elementu do podpisania               | Nazwa elementu XML w dokumencie, który należy podpisać przy użyciu podpisu elektronicznego. Jeśli nie określono żadnego elementu, jest on podpisywany jako element główny dokumentu. |
| Nazwa elementu do wstawienia podpisu   | Nazwa elementu XML, w którym powinien zostać wstawiony wygenerowany podpis cyfrowy. Jeśli nie określono żadnego elementu, podpis jest wstawiany w katalogu głównym dokumentu. |
| Plik XLST z przekształceniem skrótu       | Plik przekształcenia Extensible Stylesheet Language Transformations (XSLT), który zawiera reguły przekształcania szyfrowanego służący do generowania ciągów skrótu dla podpisu elektronicznego. |
| Ścieżka do wstawiania ciągu skrótu          | Ścieżka w **\<elementName\>.\<Attribute.Path\>** formacie lokalizacji, w której musi zostać wstawiony wygenerowany ciąg skrótu. |
| Lokalizacja numeru certyfikatu           | Nazwa elementu i atrybutu, w którym powinien być umieszczany numer certyfikatu. |
| Lokalizacja danych certyfikatu          | Nazwa elementu i atrybutu, w którym należy wstawić dane certyfikatu (base64). |
| Numer certyfikatu jest w formacie ASCII | Wartość określająca, czy numer certyfikatu jest kodowany w formacie ASCII. |

###### <a name="action-filestoreactionname"></a>Akcja: FileStoreActionName

| Parametr  | opis |
|------------|-------------|
| Plik importu | Plik wejściowy do zapisania. |

###### <a name="action-transform-document"></a>Akcja: Przekształcanie dokumentu

| Parametr                       | opis |
|---------------------------------|-------------|
| Plik importu                      | Plik źródłowy dostarczający dane, które muszą zostać wykonane w ramach akcji. |
| Kierunek                       | Wartość wskazująca, czy ma być używany format importu, czy format eksportu. |
| Identyfikator konfiguracji                | Format, który powinien być uruchamiany. |
| Wersja konfiguracji           | Jeśli nie określono wersji konfiguracji, zostanie użyta najnowsza wersja. |
| Punkt integracji konfiguracji | Plik źródłowy dostarczający dane do środowiska uruchomieniowego raportowania. |

###### <a name="action-process-response"></a>Akcja: Przetwarzanie odpowiedzi

| Parametr                    | opis |
|------------------------------|-------------|
| Plik importu                   | Odpowiedź do przeanalizowania. |
| Lista konfiguracji raportowania | Lista konfiguracji służących do analizy odpowiedzi. |

###### <a name="action-call-rest-web-service"></a>Akcja: Wywołaj usługę sieci Web REST

| Parametr                   | opis |
|-----------------------------|-------------|
| Adres URL usługi sieci Web             | Adres URL, do którego mają być wysłane żądania. |
| Upłynął limit czasu żądania sieci Web         | Maksymalny czas oczekiwania (w milisekundach) na odpowiedź usługi sieci Web. |
| Typ operacji żądania      | Typ operacji żądania HTTP (np **GET**, **POST** lub **DELETE**). |
| Nazwy certyfikatu           | Nazwy certyfikatu. |
| Kodowanie treści odpowiedzi      | Oczekiwane kodowanie treści odpowiedzi HTTP, aby można było ją poprawnie zdekodować. |
| Typ zawartości żądania HTTP   | Dane wejściowe z nagłówka typu zawartości żądania HTTP. |
| Typ zawartości treści HTTP   | Treść żądania HTTP. (Treść może być pusta.) |
| Wartości kwerendy parametrów HTTP | Wartości zapytania parametrów, które są używane do wypełnienia adresu URL parametrami zmiennymi. |
| Żądanie trasy               | Ścieżka trasy dla żądania HTTP. Parametry zmiennych można pisać w notacji **\{paramName\}**. Oto przykład: **"api/{id}/submit"**. |
| Lista parametrów tras        | Parametry trasy w notacji klucz-wartość, które są używane do wstawiania zmiennych do trasy. |
| Niestandardowe nagłówki HTTP         | Niestandardowe nagłówki HTTP, które mają zostać umieszczone w żądaniu. |
| Pliki cookie żądania HTTP        | Lista plików cookie w notacji klucz-wartość, która ma być umieszczona w żądaniu nagłówka plików cookie HTTP. |
| Protokół zabezpieczeń           | Protokół zabezpieczeń, który ma być używany dla żądań HTTP do komunikacji z serwerem. (Domyślnie jest używany Transport Layer Security \[TLS\] 1.2.) |

###### <a name="action-call-mexican-pac-service"></a>Akcja: Wywołaj usługę meksykańskiego certyfikatu PAC

| Parametr                | opis |
|--------------------------|-------------|
| Plik importu               | Plik zawierający dane XML, które zostaną wysłane do usługi sieci Web jako parametr wejściowy metody. |
| Adres URL              | Adres usługi sieci Web (punkt końcowy). |
| Nazwa metody sieci Web (akcji) | Nazwa metody sieci Web (akcji), która musi zostać uruchomiona. |
| Certyfikaty             | Łańcuch certyfikatów wymagany do uwierzytelniania klienta przez usługę sieci Web. Certyfikat klienta powinien być ostatnim certyfikatem w łańcuchu. Certyfikaty główne i pośrednie powinny być pierwsze. |
| Upłynął limit czasu żądania sieci Web      | Maksymalny czas oczekiwania (w milisekundach) na odpowiedź usługi sieci Web. |
| Interwał ponawiania prób           | Interwał między próbami wywołania i odebrania odpowiedzi z usługi sieci Web. Jeśli nie określono interwału, nie będą podejmowane dodatkowe próby, jeśli pierwsze wywołanie nie powiedzie się. |
| Liczba ponownych prób              | Maksymalna liczba ponownych prób wywołania i pobrania odpowiedzi z usługi sieci Web. |
| Ponów próbę do               | Maksymalny czas (w milisekundach), przez jaki mogą być kontynuowane wywołania. |
| Minimalne wycofanie         | Minimalny współczynnik wycofania dla obliczania wykładniczego interwałów ponawiania. |
| Maksymalne wycofanie         | Maksymalny współczynnik wycofania dla obliczania wykładniczego interwałów ponawiania. |
| Protokół zabezpieczeń        | Protokół zabezpieczeń, który ma być używany dla żądań HTTP do komunikacji z serwerem. (Domyślnie jest używany protokół TLS 1.2.) |

###### <a name="action-call-brazilian-sefaz-service"></a>Akcja: Wywołaj usługę brazylijską SEFAZ

| Parametr                | opis |
|--------------------------|-------------|
| Plik importu               | Plik zawierający dane XML, które zostaną wysłane do usługi sieci Web jako parametr wejściowy metody. |
| Adres URL              | Adres usługi sieci Web (punkt końcowy). |
| Nazwa metody sieci Web (akcji) | Nazwa metody sieci Web (akcji), która musi zostać uruchomiona. |
| Certyfikaty             | Łańcuch certyfikatów wymagany do uwierzytelniania klienta przez usługę sieci Web. Certyfikat klienta powinien być ostatnim certyfikatem w łańcuchu. Certyfikaty główne i pośrednie powinny być pierwsze. |
| Upłynął limit czasu żądania sieci Web      | Maksymalny czas oczekiwania (w milisekundach) na odpowiedź usługi sieci Web. |
| Interwał ponawiania prób           | Interwał między próbami wywołania i odebrania odpowiedzi z usługi sieci Web. Jeśli nie określono interwału, nie będą podejmowane dodatkowe próby, jeśli pierwsze wywołanie nie powiedzie się. |
| Liczba ponownych prób              | Maksymalna liczba ponownych prób wywołania i pobrania odpowiedzi z usługi sieci Web. |
| Ponów próbę do               | Maksymalny czas (w milisekundach), przez jaki mogą być kontynuowane wywołania. |
| Minimalne wycofanie         | Minimalny współczynnik wycofania dla obliczania wykładniczego interwałów ponawiania. |
| Maksymalne wycofanie         | Maksymalny współczynnik wycofania dla obliczania wykładniczego interwałów ponawiania. |
| Protokół zabezpieczeń        | Protokół zabezpieczeń, który ma być używany dla żądań HTTP do komunikacji z serwerem. (Domyślnie jest używany protokół TLS 1.2.) |

###### <a name="action-call-italian-sdi-service"></a>Akcja: Wywołaj włoską usługę SDI

| Parametr                | opis |
|--------------------------|-------------|
| Plik importu               | Plik zawierający dane XML, które zostaną wysłane do usługi sieci Web jako parametr wejściowy metody. |
| Adres URL              | Adres usługi sieci Web (punkt końcowy). |
| Nazwa metody sieci Web (akcji) | Nazwa metody sieci Web (akcji), która musi zostać uruchomiona. |
| Certyfikaty             | Łańcuch certyfikatów wymagany do uwierzytelniania klienta przez usługę sieci Web. Certyfikat klienta powinien być ostatnim certyfikatem w łańcuchu. Certyfikaty główne i pośrednie powinny być pierwsze. |
| Upłynął limit czasu żądania sieci Web      | Maksymalny czas oczekiwania (w milisekundach) na odpowiedź usługi sieci Web. |
| Interwał ponawiania prób           | Interwał między próbami wywołania i odebrania odpowiedzi z usługi sieci Web. Jeśli nie określono interwału, nie będą podejmowane dodatkowe próby, jeśli pierwsze wywołanie nie powiedzie się. |
| Liczba ponownych prób              | Maksymalna liczba ponownych prób wywołania i pobrania odpowiedzi z usługi sieci Web. |
| Ponów próbę do               | Maksymalny czas (w milisekundach), przez jaki mogą być kontynuowane wywołania. |
| Minimalne wycofanie         | Minimalny współczynnik wycofania dla obliczania wykładniczego interwałów ponawiania. |
| Maksymalne wycofanie         | Maksymalny współczynnik wycofania dla obliczania wykładniczego interwałów ponawiania. |
| Protokół zabezpieczeń        | Protokół zabezpieczeń, który ma być używany dla żądań HTTP do komunikacji z serwerem. (Domyślnie jest używany protokół TLS 1.2.) |

### <a name="applicability-rules"></a>Reguły zastosowania

Reguły stosowania umożliwiają tworzenie reguł logicznych, które określają kontekst użycia dla konfiguracji funkcji. Tym samym dopasowanie między kontekstem nadanym przez dokument biznesowy, który jest wysyłany do przetwarzania, wraz z kryteriami reguły zastosowania, określa, która funkcja dodatku Faktur elektronicznych jest używana do przetwarzania tego przesyłania.

#### <a name="set-up-applicability-rules"></a>Ustaw reguły zastosowania

1. Na stronie **Konfiguracja wersji funkcji** na karcie **Reguły zastosowania** wybierz opcję **Nowa**, aby dodać regułę stosowania.

    ![Zarządzanie regułami stosowania](media/e-Invoicing-services-feature-setup-Manage-Actions-Applicability-rules.png)

2. W siatce wybierz klauzule, które powinny być zgrupowane.
3. Wybierz **Klauzulę group**.

    ![Klauzule grupowania](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-clause.png)

    Gdy klauzule są zgrupowane, do siatki jest dodawana nowa kolumna. W tej kolumnie jest określany operator logiczny dla zgrupowanych klauzul.

    ![Operator logiczny dla klauzul zgrupowanych](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-criterias.png)

Aby rozgrupować klauzule, wybierz zgrupowane klauzule do rozgrupowania, a następnie wybierz **Rozgrupuj klauzury**.

![Rozgrupowanie klauzul](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-UnGroup-criterias.png)

> [!NOTE]
> Kiedy rozgrupowujesz klauzulę, zawsze zaczynaj od najbardziej wewnętrznego poziomu grupowania.

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Reguły zastosowania**.

| Pole         | opis |
|---------------|-------------|
| I/lub        | Operator logiczny. |
| Pole         | Pole służące do konstruowania reguły. |
| Typ operatora | Typ operatora:<ul><li>Taka sama</li><li>nie równa się</li><li>Większe niż/mniejsze niż</li><li>Większe lub równe/Mniejsze niż lub równe</li><li>Zawiera</li><li>Zacznij od</li></ul> |
| Wartość         | Kryterium reguły. |

### <a name="variables"></a>Zmienne

Zmienne można tworzyć, a następnie stosować jako wartości wejściowe dla parametrów konkretnej akcji. Za ich pomocą można również wymieniać między usługą dodatkową Faktury Elektroniczne a klientem informacje będące wynikiem wykonania określonej akcji w ramach przepływu zgłoszeń.

#### <a name="set-up-variables"></a>Ustaw zmienne

- Na stronie **Ustawienia wersji funkcji** na karcie **Zmienne** wybierz opcję **Nowy** lub **Usuń**, aby zarządzać zmiennymi.

    ![Zarządzanie zmiennymi](media/e-Invoicing-services-feature-setup-Manage-Variables.png)

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Zmienne**.

| Pole       | opis |
|-------------|-------------|
| Imię i nazwisko        | Nazwa zmiennej. |
| opis | Krótki opis zmiennej. |
| Typ        | Typ zmiennej:<ul><li><strong>Stała</strong> — zawartość zmiennej jest stała.</li><li><strong>Od klienta</strong> — zawartość zmiennej jest nabywana od klienta Microsoft Dynamics 365 w trakcie wykonywania procesu przesyłania.</li><li><strong>Do klienta</strong> – Zawartość zmiennej jest udostępniana do importu przez klienta Microsoft Dynamics 365 podczas realizacji procesu przesyłania.</li></ul> |
| Typ danych   | Typ danych zmiennej:<ul><li>Wartość logiczna</li><li>Data</li><li>Identyfikator</li><li>UUID</li><li>Ciąg</li><li>Plik</li></ul> |
| Wartość       | Wartość zmiennej lub nazwa akcji, która ustawia wartość zmiennej. |

### <a name="validate-the-feature-setup"></a>Sprawdź ustawienia funkcji

- Na stronie **Ustawienia wersji funkcji** w okienku akcji wybierz opcję **Weryfikuj**, aby sprawdzić konfigurację wersji funkcji.

   ![Wybranie przycisku Zatwierdź](media/e-Invoicing-services-feature-setup-Select-Validate-Button.png)

Podczas sprawdzania poprawności jest sprawdzana spójność całej konfiguracji. Jeśli na przykład określony parametr akcji jest obowiązkowy, ale jego wartość pozostanie pusta, sprawdzanie poprawności wykryje niespójność i pojawi się ostrzeżenie.

## <a name="environments"></a>Środowiska

Środowisko dodatkowe Faktury elektroniczne musi być skojarzone z funkcją dodatku Faktury elektroniczne i włączone dla niego. Środowiska dodatku Faktury elektroniczne muszą zostać utworzone i opublikowane z wyprzedzeniem, poprzez skonfigurowanie funkcji globalizacji na koncie RCS organizacji.

Wykonaj poniższe czynności, aby włączyć środowisko dodatkowe Faktury elektroniczne dla funkcji dodatku Faktury elektroniczne.

1. Na stronie **Funkcje dodatku Faktur elektronicznych** na karcie **Środowiska** wybierz opcję **Włącz**, aby dodać środowisko dodatku Faktur elektronicznych.
2. W polu **Obowiązuje od** wprowadź datę, kiedy nowe środowisko zostanie wprowadzone.

![Włączanie środowiska dodatku Faktur elektronicznych](media/e-Invoicing-services-feature-setup-Select-Enable-e-Invoicing-feature-Environment.png)

## <a name="organizations"></a>Organizacje

Dodatkową funkcję Faktury elektroniczne można udostępniać w wielu organizacjach.

- Na stronie **Funkcje dodatku Faktur elektronicznych** na karcie **organizacje** wybierz pozycję **Udostępnij z** w celu dodania organizacji, z którą ma być udostępniana funkcja dodatku Faktur elektronicznych.

Aby zatrzymać udostępnianie funkcji dodatku Faktur elektronicznych w organizacji, wybierz opcję **Cofnij udostępnianie**.

## <a name="versions"></a>Wersje

Wersje pomagają kontrolować czas trwania funkcji dodatku Faktur elektronicznych w sieci, zarządzając jej stanem. Można utworzyć nową wersję istniejącej funkcji dodatku Faktur elektronicznych, lub, jeśli została ukończona cała konfiguracja funkcji dodatku Faktur elektronicznych, można zmienić stan funkcji na **Zakończona**, a następnie **Opublikuj**.

### <a name="create-a-new-version-of-an-existing-electronic-invoicing-add-on-feature"></a>Utwórz nową wersję istniejącej funkcji dodatku Faktur elektronicznych

1. Na stronie **Funkcje dodatku Faktur elektronicznych** na siatce po lewej, wybierz funkcję dodatku Faktur elektronicznych.
2. Na karcie **Wersje** wybierz opcję **Nowa**, aby dodać nową wersję funkcji dodatku Faktur elektronicznych.

### <a name="change-the-status-of-the-electronic-invoicing-add-on-feature"></a>Zmiana stanu funkcji dodatku Faktur elektronicznych

Wykonaj poniższe czynności, aby zarządzać cyklem życia funkcji dodatku Faktury elektroniczne.

1. Na stronie **Funkcje dodatku Faktur elektronicznych** na siatce po lewej, wybierz funkcję dodatku Faktur elektronicznych.
2. Na karcie **Wersje** wybierz pozycję **Zmień stan**, a następnie zmień stan z **Wersja robocza** na **Ukończone**.
3. Zostanie wyświetlony monit o potwierdzenie zamiaru ukończenia funkcji dodatku Faktury elektroniczne i wszystkich jego składników. Wybierz opcję **Tak**, aby potwierdzić akcję, lub przycisk **Nie**, aby ją anulować.

    > [!NOTE]
    > Po wybraniu opcji **Tak**, stan wersji konfiguracji, które są składnikami funkcji dodatku Faktury elektroniczne, jest automatycznie zmieniany z **Wersji roboczej** na **Ukończona**.

4. Wybierz **Zmień stan**, a następnie zmień stan z **Ukończone** na **Opublikuj**.
5. Zostanie wyświetlony monit o potwierdzenie zamiaru publikacji funkcji dodatku Faktury elektroniczne i wszystkich jego składników dl globalnego repozytorium. Wybierz opcję **Tak**, aby potwierdzić akcję, lub przycisk **Nie**, aby ją anulować.

    > [!NOTE]
    > Po wybraniu opcji **Tak**, stan wersji konfiguracji zostanie automatycznie zmieniony z **Zakończono** na **Udostępnione**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]