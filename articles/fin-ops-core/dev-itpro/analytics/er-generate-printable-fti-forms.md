---
title: Generowanie drukowalnych formularzy FTI
description: W tym temacie opisano, jak za pomocą struktury raportowania elektronicznego (ER) generować drukowalne formularze faktur niezależnych (FTI) jako dokumenty pakietu Microsoft Office.
author: NickSelin
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: f5556195a1a787420061fbcaef5d97ac47823221
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359012"
---
# <a name="generate-printable-fti-forms"></a>Generowanie drukowalnych formularzy FTI

[!include[banner](../includes/banner.md)]

Struktura raportowania elektronicznego (ER) umożliwia generowanie drukowalnych formularzy faktur niezależnych (FTI) jako dokumentów pakietu Microsoft Office. Ten temat zawiera informacje dotyczące sposobu tworzenia własnych konfiguracji oraz szczegółowe informacje o dostępnych szablonach konfiguracji.

## <a name="overview"></a>Przegląd

Oprócz istniejącej wcześniej możliwości tworzenia drukowalnych formularzy faktur niezależnych za pomocą usługi Microsoft SQL Server Reporting Services (SSRS) teraz można używać struktury raportowania elektronicznego. Drukowalnymi formularzami faktur niezależnych można zarządzać w programach Microsoft Office Excel i Word. Można także modyfikować układ, przepływ danych i formatowanie w celu spełnienia określonych wymagań bez wprowadzania zmian w kodzie źródłowym.

> [!NOTE]
> Jeśli chcesz zacząć od przeglądu istniejących konfiguracji raportowania elektronicznego dla tego przykładu rozwiązania do tworzenia drukowalnych formularzy faktur niezależnych, możesz przejść bezpośrednio do punktu **Pobieranie przykładowych konfiguracji ER w celu generowania drukowalnych formularzy FTI** poniżej w tym temacie.

## <a name="create-customized-configurations-for-fti-printable-forms"></a>Tworzenie spersonalizowanych konfiguracji dla drukowalnych formularzy faktur niezależnych
W ramach niestandardowego rozwiązania do generowania drukowalnych formularzy faktur niezależnych należy utworzyć zestaw konfiguracji raportowania elektronicznego.

### <a name="configure-the-er-data-model"></a>Konfigurowanie modelu danych raportowania elektronicznego
Aplikacja musi zawierać konfigurację modelu danych raportowania elektronicznego z modelem danych, który opisuje dziedzinę biznesową fakturowania odbiorców. Model danych koniecznie musi się nazywać **CustomersInvoicing**. Aby uzyskać informacje o projektowaniu modeli danych raportowania elektronicznego, zobacz [ER Projektowanie modelu danych specyficznego dla domeny (ER)](tasks/er-design-domain-specific-data-model-2016-11.md).

### <a name="configure-the-er-model-mapping"></a>Konfigurowanie mapowania modelu raportowania elektronicznego
Aplikacja musi zawierać mapowanie modelu raportowania elektronicznego dla modelu danych CustomersInvoicing. Mapowanie modelu może się znajdować w konfiguracji modelu danych raportowania elektronicznego lub konfiguracji mapowania modelu raportowania elektronicznego. Jednak główny deskryptor mapowania modelu musi się nazywać **FreeTextInvoice**.

Mapowanie musi zawierać następujące źródła danych:

- Typ źródła danych: **Rekordy tabeli**

    - To źródło danych musi się nazywać **CustInvoiceJour**.
    - Musi się odwoływać do tabeli aplikacji CustInvoiceJour.
    - W czasie wykonywania przekazuje z aplikacji do mapowania modelu raportowania elektronicznego listę faktur, które zostały wybrane do drukowania.

- Typ źródła danych: **Obiekt**

    - To źródło danych musi się nazywać **PrintMgmtPrintSettingDetail**.
    - Musi się odwoływać do klasy aplikacji **PrintMgmtPrintSettingDetail**.
    - W czasie wykonywania przekazuje z aplikacji do mapowania modelu raportowania elektronicznego szczegóły ustawień zarządzania drukowaniem dla używanego formatu raportowania elektronicznego.

Szczegółowe informacje o integracji aplikacji ze strukturą ER znajdują się w klasie **ERPrintMgmtReportFormatSubscriber** (model integracji pakietu aplikacji w raportowaniu elektronicznym) w kodzie źródłowym aplikacji.

Aby uzyskać więcej informacji o projekcie mapowań modelu raportowania elektronicznego, zobacz [Definiowanie mapowań modelu ER i wybieranie źródeł danych](tasks/er-define-model-mapping-select-data-sources-2016-11.md).

### <a name="configure-the-er-format"></a>Konfigurowanie formatu raportowania elektronicznego
W wystąpieniu aplikacji musi istnieć konfiguracja formatu raportowania elektronicznego, która będzie używana do generowania formularzy faktur niezależnych. 

> [!NOTE]
> Ta konfiguracja formatu musi być utworzona dla modelu danych CustomersInvoicing oraz musi używać mapowania modelu mającego deskryptor główny **FreeTextInvoice**.

Aby uzyskać informacje o konfigurowaniu formatów raportowania elektronicznego, zobacz [ER Tworzenie konfiguracji formatu dla raportowania elektronicznego (listopad 2016)](tasks/er-format-configuration-2016-11.md). Aby uzyskać informacje o projektowaniu formatów raportowania elektronicznego w celu generowania raportów w formacie OpenXML, zobacz [ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML (listopad 2016)](tasks/er-design-reports-openxml-2016-11.md).

## <a name="configure-print-management"></a>Konfigurowanie zarządzania drukowaniem
Aby generować formularze faktur niezależnych przy użyciu struktury raportowania elektronicznego, można przypisywać formaty ER w taki sam sposób, jak się przypisuje raporty w usłudze SSRS. Aby skojarzyć format raportowania elektronicznego ze wszystkimi fakturami niezależnymi w module Rozrachunki z odbiorcami, wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Formularze** \> **Ustawienia formularza** \> **Ogólne** \> **Zarządzanie drukowaniem** \> **Faktura niezależna** \> **Oryginał**. Aby skojarzyć format ER z określonym odbiorcą lub fakturą, wykonaj następujące kroki:

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Wybierz fakturę niezależną, z którą chcesz skojarzyć format raportowania elektronicznego, i otwórz stronę **Konfiguracja zarządzania drukowaniem**.
3. Wybierz poziom dokumentu, aby określić zakres faktur do przetwarzania.
4. Wybierz format ER dla podanego poziomu dokumentu.

![Konfiguracja zarządzania drukowaniem.](media/FTIbyGER-PMSetting.png)

> [!NOTE]
> Tylko formaty ER używające deskryptora głównego **FreeTextInvoice** z modelu danych **CustomersInvoicing** są wyświetlane w polu wyszukiwania **Format raportu** dla wybranego formatu.

## <a name="generate-fti-forms"></a>Generowanie formularzy faktur niezależnych
Formularze faktur niezależnych są generowane w strukturze raportowania elektronicznego tak samo, jak się generuje raporty usługi SSRS.

Aby wygenerować formularze faktur niezależnych, można wybrać faktury według zakresu lub je zaznaczyć. 

![Wybór faktury.](media/FTIbyGER-InvoiceSelection.png)

![Podgląd faktury.](media/FTIbyGER-InvoiceExcelPreview.png)

Jeżeli formaty raportowania elektronicznego są używane do drukowania formularzy faktur niezależnych w ten sposób, są używane domyślne plikowe miejsca docelowe modułu Raportowanie elektroniczne. Nie można zmienić tego miejsca docelowego. Aby uzyskać więcej informacji o konfigurowaniu miejsc docelowych raportowania elektronicznego dla formatów raportowania elektronicznego, zobacz [Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md).

Można również generować formularze faktur niezależnych podczas księgowania faktur niezależnych. W tym celu należy włączyć opcję **Drukuj fakturę**, a wyłączyć opcję **Używanie miejsc docelowych zarządzania drukowaniem**.

> [!NOTE]
> Jeżeli formaty raportowania elektronicznego są używane do drukowania formularzy faktur niezależnych w ten sposób, są używane domyślne plikowe miejsca docelowe modułu Raportowanie elektroniczne. Domyślną lokalizacją docelową można zmienić w czasie wykonywania, jeśli ta druga lokalizacja została już skonfigurowana. Aby zmienić miejsce docelowe, trzeba mieć następujące uprawnienie zabezpieczeń:
>
> - **Nazwa:** ERFormatDestinationRuntimeMaintain
> - **Etykieta:** Zarządzanie lokalizacją docelową formatu raportowania elektronicznego w trakcie wykonywania

![Aplikacja docelowa raportowania elektronicznego.](media/FTIbyGER-ERFileDestinationSetting.png)

![Miejsca docelowe formatu raportowania elektronicznego.](media/FTIbyGER-ERFileDestinationUsage.png)

Obecnie struktura ER obsługuje następujące lokalizacje docelowe dla generowanych dokumentów:

- **Pobrany plik** — wygenerowane formularze są udostępniane jako pliki do pobrania, które można zapisać przy użyciu przeglądarki.
- **Ekran** — program Microsoft 365 Excel jest używany do wyświetlania podglądu wygenerowanych formularzy faktur niezależnych w formacie programu Excel.
- **Folder programu SharePoint** — wygenerowane formularze są przechowywane zgodnie z ustawieniami struktury zarządzania dokumentami.
- **Archiwum aplikacji** — wygenerowane formularze są przechowywane jako załączniki rekordów dziennika wykonywania w usłudze Microsoft Azure Storage.
- **Poczta e-mail** — wygenerowane formularze są wysyłane jako załączniki wiadomości e-mail.

> [!NOTE]
> Generowanych formularzy faktur niezależnych nie można wysłać bezpośrednio do drukarki, ponieważ aktualnie nie jest obsługiwana funkcja bezpośredniego drukowania wykorzystująca agenta rozsyłania do drukarek dostępnego w systemie Dynamics.

## <a name="download-sample-er-configurations-to-generate-printable-fti-forms"></a>Pobieranie przykładowych konfiguracji ER w celu generowania drukowalnych formularzy FTI
Można pobrać przykładowe konfiguracje raportowania elektronicznego i używać ich jako szablonów w rozwiązaniu służącym generowaniu faktur niezależnych. Konfiguracje są przechowywane w bibliotece udostępnionych elementów zawartości w usłudze Microsoft Dynamics Lifecycle Services (LCS). Istnieją następujące konfiguracje:

- Konfiguracja **Model fakturowania odbiorców** zawiera wymagany model danych i mapowanie modelu.
- Konfiguracja **Raport o fakturach niezależnych dla odbiorców (GER)** zawiera przykładowy format.

> [!NOTE]
> Konfiguracje te zostały utworzone jako przykłady ułatwiające wyjaśnienie możliwych scenariuszy. Przyszłość tych konfiguracji zależy od wyników tej oceny i wszelkich otrzymanych informacji zwrotnych.

### <a name="features-that-are-implemented-in-the-sample-er-format"></a>Funkcje zaimplementowane w przykładowym formacie ER
W przykładowej konfiguracji formatu raportowania elektronicznego plik programu Excel służy jako szablon do generowania formularzy faktur niezależnych.

![Projektant formatów.](media/FTIbyGER-ERFormat.png)

Obecnie ten przykładowy format raportowania elektronicznego obsługuje następujące funkcje generowania formularzy faktur niezależnych:

- Formularze faktur niezależnych są generowane zarówno dla oryginalnych faktur, które zostały zaksięgowane, jak i oryginalnych faktur, które nie zostały jeszcze zaksięgowane. Skorygowane faktury i faktury korygujące nie są obsługiwane.
- Formularze faktur niezależnych są generowane w języku faktury. Format wartości i dat w wygenerowanych formularzach bazuje na ustawieniach regionalnych urządzenia klienckiego użytkownika.
- Dla wygenerowanych faktur są wyświetlane powiadomienia o niedostępności danych, jeśli w przetwarzanych fakturach nie ma żadnych wierszy.
- Nagłówki generowanych faktur są oparte na formacie papierowym, która wybrano dla formularza faktury niezależnej na stronie **Parametry modułu rozrachunków z odbiorcami**. Szczegółowe informacje o firmie są wyświetlane w nagłówku wygenerowanego formularza faktury tylko wtedy, gdy format papierowy jest pusty.
- Wygenerowane formularze faktur zawierają numery identyfikacji podatkowej firmy i odbiorcy, gdy odpowiednia opcja została wybrana w formularzu faktur niezależnych na stronie **Parametry modułu rozrachunków z odbiorcami**.
- Wiersze i sekcje sum na wygenerowanej fakturze zawierają domyślne informacje pieniężne faktury w walucie rejestracji faktury.
- Sekcja sum na wygenerowanej fakturze może zawierać informacje pieniężne w walucie euro i walucie rejestracji faktury, jeśli włączono opcję **Drukuj kwotę w walucie reprezentującej euro** na stronie **Parametry modułu rozrachunków z odbiorcami**.
- Wygenerowane formularze faktur zawierają wszelkie uwagi o przetwarzaniu faktur wynikające z ustawień na stronie **Parametry modułu rozrachunków z odbiorcami**. Uwagi są uwzględniane zarówno dla całej faktury, jak i dla każdego wiersza faktury.
- Wygenerowane formularze faktur zawierają uwagi dla odbiorcy powiązanego z formularzem faktury niezależnej i uwagi w języku przetwarzanej faktury, jeżeli odpowiednie ustawienia skonfigurowano na liście uwag do formularza rozrachunków z odbiorcami.
- W zależności od ustawień zarządzania drukowaniem wygenerowane faktury zawierają niestandardowy tekst stopki, jeżeli go skonfigurowano dla języka faktury, formatu raportowania elektronicznego i zakresu dokumentów faktur niezależnych.
- Sekcja sum w wygenerowanych formularzach faktur zawiera wszelkie dostępne informacje o rabatach gotówkowych.
- Sekcja harmonogramu płatności w wygenerowanych formularzach faktur zawiera wszelkie dostępne szczegóły harmonogramu płatności.
- Sekcja narzutów w wygenerowanych formularzach faktur zawiera wszystkie dostępne transakcje opłat.
- Wygenerowane formularze faktur zawierają szczegóły podatku, zgodnie z ustawieniem **Specyfikacja podatku** na stronie **Parametry modułu rozrachunków z odbiorcami**. W tej sekcji mogą być wyświetlane szczegóły podatku tylko w walucie rejestracji faktury lub równocześnie w walucie rejestracji faktury i walucie rozliczeniowej firmy.
- Wygenerowane formularze faktur zawierają szczegóły powiadomień o poleceniach zapłaty. Na przykład przedstawiają, kiedy dla faktury wybrano metodę płatności zawierającą obowiązkowy identyfikator zgody na polecenie zapłaty, kiedy przetwarzana faktura została zarejestrowana w walucie euro i kiedy dla faktury zdefiniowano identyfikator zgody na polecenie zapłaty.
- Wygenerowane faktury przedstawiają wszelkie szczegóły przedpłat dostępne dla zaksięgowanych faktur.
- Wygenerowane formularze faktur można wysłać do odbiorcy powiązanego z fakturą jako załącznik wiadomości e-mail. Odpowiednie plikowe miejsce docelowe raportowania elektronicznego powinno być skonfigurowane dla używanego formatu ER.

### <a name="countryregion-specific-features"></a>Funkcje specyficzne dla kraju/regionu 
Następujące funkcje specyficzne dla kraju/regionu są uwzględnione w przykładowym formacie ER, aby pokazać możliwy sposób obsługi konkretnych wymagań w konfiguracjach raportowania elektronicznego.

#### <a name="norway"></a>Norwegia
Zwrot Rejestr przedsiębiorstw jest umieszczany w nagłówku generowanego formularza faktury podczas przetwarzania faktury dla firmy skonfigurowanej w następujący sposób:

- Jest używany kontekst kraju/regionu dla Norwegii.
- Parametr **Drukuj wartość Foretaksregisteret** jest aktywny w dokumentach sprzedaży.

#### <a name="spain"></a>Hiszpania
Zwrot **Specjalny tryb dla metody księgowania kasowego** jest umieszczany w nagłówku generowanego formularza faktury podczas przetwarzania faktury dla firmy skonfigurowanej w następujący sposób:

- Jest używany kontekst kraju/regionu dla Hiszpanii.
- Specjalny tryb dla metody księgowania kasowego jest włączony w dniu przetwarzania faktury.

Jeśli są dostępne szczegóły rabatu gotówkowego, takie jak kwota rabatu gotówkowego i kwota netto wiersza faktury, są one wyświetlane w sekcji sum faktury w wygenerowanym formularzu faktury, gdy został on przetworzony dla firmy skonfigurowanej w następujący sposób:

- Jest używany kontekst kraju/regionu dla Hiszpanii.
- Ustawienie **Rabat gotówkowy jest stosowany w fakturze** jest włączone w opcjach faktury (**Parametry księgi głównej** \> **Sekcja podatku**).

#### <a name="italy"></a>Włochy
Znacznik rabatu towarów jest umieszczany w wierszach wygenerowanej faktury, gdy jest ona przetwarzana dla firmy skonfigurowanej przy użyciu kontekstu kraju/regionu dla Włoch.

#### <a name="finland"></a>Finlandia
Oprócz generowania formularza faktury mogą być również generowane formularze przekazu GIRO w następujący sposób:

- Dla firmy używającej kontekstu kraju/regionu Finlandia, która ma co najmniej jedno konto bankowe z włączonymi ustawieniami **Konto GIRO** i **Kod kreskowy banku**. 
- Dla faktury oznaczonej jako wymagana dla załącznika powiązanych płatności z atrybutem **Fiński**.

![Przekaz Giro.](media/FTIbyGER-GiroSlip.PNG)

> [!NOTE]
> W przykładowym formacie raportowania elektronicznego skonfigurowano opcjonalne generowanie formularzy przekazu GIRO w osobnym arkuszu.

> [!NOTE]
> Najpierw należy zainstalować czcionkę używaną do generowania kodu kreskowego na komputerze lokalnym, gdzie będzie wyświetlany podgląd wygenerowanego formularza faktury w formacie programu Excel.

### <a name="use-the-sample-er-format-to-configure-email-destinations"></a>Używanie przykładowego formatu raportowania elektronicznego do konfigurowania pocztowych miejsc docelowych
Użyj poniższych elementów przykładowego formatu raportowania elektronicznego, aby skonfigurować pocztowe miejsca docelowe:

- Dostęp do adresu e-mail osoby kontaktowej u odbiorcy można uzyskać za pomocą następującego wyrażenia modułu ER: **model.InvoiceBase.Contact.ElectronicMail**.
- Dostęp do tekstu tematu wiadomości e-mail można uzyskać za pomocą następującego wyrażenia modułu ER: **Emailing.TxtToUse.Subject**.
- Dostęp do tekstu treści wiadomości e-mail można uzyskać za pomocą następującego wyrażenia modułu ER: **Emailing.TxtToUse.Body**.

![Ustawienia aplikacji docelowej.](media/FTIbyGER-ERFileDestinationSettingEmail.png)

Domyślne teksty tematu i treści wiadomości e-mail są zdefiniowane w przykładowym formacie raportowania elektronicznego. Język zależy od etykiet formatu. Ten domyślny tekst będzie używany w wiadomościach e-mail, jeśli nie dodano niestandardowego szablonu wiadomości e-mail organizacji ze wstępnie zdefiniowanym identyfikatorem **ERFTITMP**.

> [!NOTE]
> Identyfikator szablonu wiadomości e-mail **ERFTITMP** został zdefiniowany w przykładowym formacie raportowania elektronicznego. Można go zmienić w razie potrzeby w nowym formacie ER utworzonym na podstawie tego przykładowego formatu.

Jeśli szablon wiadomości e-mail organizacji ze wstępnie zdefiniowanym identyfikatorem **ERFTITMP** został dodany do firmy, której fakturę przetwarzasz, do wygenerowania wiadomości e-mail zostanie użyty szablon tematu i treści wiadomości e-mail. 

![Szablony wiadomości e-mail organizacji.](media/FTIbyGER-EmailTemplate.png)

![Przekaż szablon wiadomości e-mail.](media/FTIbyGER-EmailTemplateBody.png)

W wyrażeniu ER **Emailing.TxtToUse.Subject** w przykładowym formacie raportowania elektronicznego skonfigurowano zastępowanie wszystkich wystąpień symbolu zastępczego %1 identyfikatorem przetwarzanej faktury.

Dla wyrażenia **Emailing.TxtToUse.Body** w przykładowym formacie skonfigurowano następujące zastępowanie symboli zastępczych:

- „%1” jest zastępowany imieniem i nazwiskiem osoby kontaktowej u odbiorcy.
- „%2” jest zastępowany nazwą firmy.
- „%3” jest zastępowany nazwą odbiorcy.
- „%4” jest zastępowany imieniem i nazwiskiem osoby kontaktowej w firmie.
- „%5” jest zastępowany stanowiskiem osoby kontaktowej w firmie.
- „%6” jest zastępowany adresem e-mail osoby kontaktowej w firmie.

![E-mail.](media/FTIbyGER-Email.PNG)

## <a name="additional-resources"></a>Dodatkowe zasoby
[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]