---
title: Miejsca docelowe raportowania elektronicznego
description: "Można skonfigurować miejsce docelowe dla każdej konfiguracji formatu raportowania elektronicznego (ER) i jej składnika wyjściowego (folderu lub pliku). Użytkownicy, którym udzielono odpowiednich praw dostępu, mogą także modyfikować ustawienia miejsca docelowego w czasie wykonywania. Ten artykuł wyjaśnia problematykę zarządzania miejscami docelowymi w ER, obsługiwane typy miejsc docelowych oraz zagadnienia dotyczące zabezpieczeń."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fb7d0dc8b3ff9e8f1e4ade5cacfeed8f1a6871ab
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="electronic-reporting-destinations"></a>Miejsca docelowe raportowania elektronicznego

[!include [banner](../includes/banner.md)]

Można skonfigurować miejsce docelowe dla każdej konfiguracji formatu raportowania elektronicznego (ER) i jej składnika wyjściowego (folderu lub pliku). Użytkownicy, którym udzielono odpowiednich praw dostępu, mogą także modyfikować ustawienia miejsca docelowego w czasie wykonywania. Ten artykuł wyjaśnia problematykę zarządzania miejscami docelowymi w ER, obsługiwane typy miejsc docelowych oraz zagadnienia dotyczące zabezpieczeń.

Konfiguracje formatów w module raportowania elektronicznego (ER) zwykle zawierają co najmniej jeden składnik wyjściowy: plik. Przeważnie konfiguracje zawierają wiele składników wyjściowych w postaci plików różnego typu (na przykład XML, TXT lub XLSX), które są zgrupowane w jednym folderze lub wielu folderach. Funkcje zarządzania miejscami docelowymi raportowania elektronicznego pozwalają wstępnie skonfigurować, co się dzieje po uruchomieniu każdego składnika. Domyślnie podczas sesji konfiguracji jest wyświetlane okno dialogowe, które pozwala użytkownikowi zapisać lub otworzyć plik. Takie samo zachowanie występuje również podczas importowania konfiguracji ER, gdy nie ustawiono dla niej żadnych konkretnych miejsc docelowych. Po utworzeniu miejsca docelowego dla głównego składnika wyjściowego miejsce to zastępuje domyślne zachowanie, a folder lub plik jest wysyłany zgodnie z ustawieniami tego miejsca docelowego.

## <a name="availability-and-general-prerequisites"></a>Dostępność i ogólne warunki wstępne
Funkcjonalność miejsc docelowych w raportowaniu elektronicznym nie jest dostępna w wersji Microsoft Dynamics AX 7.0 (z lutego 2016 r.). W związku z tym aby móc korzystać ze wszystkich funkcji opisanych w tym temacie, należy zainstalować program Microsoft Dynamics 365 for Operations w wersji 1611 (z listopada 2016 r.). Alternatywnie można zainstalować jeden z poniższych wstępnie wymaganych składników. Należy jednak pamiętać, że te alternatywne rozwiązania zapewniają bardziej ograniczoną funkcjonalność miejsc docelowych raportowania elektronicznego.

-   Aplikacja Microsoft Dynamics AX w wersji 7.0.1 (z maja 2016 r.)
-   [Poprawkę aplikacji](https://fix.lcs.dynamics.com/issue/results/?q=3160213) do zarządzania miejscami docelowymi w ER

Miejsca docelowe można ustawiać tylko dla konfiguracji ER, które zostały zaimportowane, oraz dla formatów, które są dostępne na stronie **Konfiguracje raportowania elektronicznego**.

## <a name="overview"></a>Przegląd
Funkcje zarządzania miejscami docelowymi ER są dostępne w oknie **Administrowanie organizacją** &gt; **Raportowanie elektroniczne**. W tym oknie można zastąpić domyślne zachowanie konfiguracji. Zaimportowane konfiguracje są tutaj wyświetlane dopiero wtedy, gdy klikniesz przycisk **Nowy**, a następnie w polu **Odwołanie** wybierzesz konfigurację, dla której mają zostać utworzone ustawienia miejsca docelowego.

[![Wybieranie konfiguracji w polu Odwołanie](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg) 

Po utworzeniu odwołania można utworzyć plikowe miejsce docelowe dla każdego folderu lub pliku. 

[![Tworzenie plikowego miejsca docelowego](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

> [!NOTE] 
> Można utworzyć jedno plikowe miejsce docelowe dla każdego składnika wyjściowego tego samego formatu, takiego jak folder lub plik wybrany w polu **Nazwa pliku**. Następnie można włączać i wyłączać poszczególne miejsca docelowe w plikowym miejscu docelowym w oknie dialogowym **Ustawienia aplikacji docelowej**. Przycisk **Ustawienia** pozwala kontrolować wszystkie miejsca docelowe należące do wybranego plikowego miejsca docelowego. W oknie dialogowe **Ustawienia aplikacji docelowej** można kontrolować każde miejsce docelowe osobno, ustawiając dla niego opcję **Włączone**.

[![Okno dialogowe Ustawienia aplikacji docelowej](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Typy miejsc docelowych
Obsługiwane są różne typy miejsc docelowych. Można wyłączyć lub włączyć wszystkie typy w tym samym czasie. W ten sposób można albo nic nie robić, albo wysłać składnik do wszystkich skonfigurowanych lokalizacji. W poniższych sekcjach opisano obsługiwane miejsca docelowe.

### <a name="email-destination"></a>Pocztowe miejsce docelowe

W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać plik wyjściowy pocztą e-mail. Po włączeniu tej opcji można określić adresatów wiadomości e-mail oraz edytować jej temat i treść. Można zdefiniować stałe teksty tematu i treści wiadomości e-mail lub używać formuł moduł ER w celu dynamicznego tworzenia tekstów wiadomości e-mail. Adresy e-mail dla modułu ER można konfigurować na dwa sposoby. Konfigurację można wprowadzić w taki sam sposób, jak wykonuje ją funkcja Zarządzanie drukowaniem w programie Finance and Operations. Alternatywnie adres e-mail można rozpoznać przy użyciu bezpośredniego odwołania do konfiguracji raportowania elektronicznego za pośrednictwem formuły.

### <a name="email-address-types"></a>Typy adresów e-mail

Po kliknięciu przycisku **Edytuj** dla pola **Do** lub **DW** pojawi się okno dialogowe **Wiadomość e-mail do**. Następnie można wybrać typ adresu e-mail, który ma być używany.

[![Okno dialogowe Wiadomość e-mail do](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Zarządzanie drukowaniem

Jeśli wybierzesz typ **Wiadomość e-mail zarządzania drukowaniem**, można wprowadzić stałe adresy e-mail w polu **Do**. Aby używać adresów e-mail, które nie są stałe, należy wybrać typ źródła wiadomości e-mail dla plikowego miejsca docelowego. Obsługiwane są następujące wartości: **Odbiorca**, **Dostawca**, **Prospekt**, **Kontakt**, **Konkurent**, **Pracownik**, **Kandydat**, **Potencjalny dostawca** i **Niezatwierdzony dostawca**. Po wybraniu typu źródła wiadomości e-mail użyj przycisku obok pola **Konto źródłowe poczty e-mail**, aby otworzyć formularz **Projektant formuł**. Ten formularz pozwala dołączyć formułę reprezentującą konto wybranej strony do miejsca docelowego poczty e-mail.

[![Konfigurowanie typu Wiadomość e-mail zarządzania drukowaniem](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg) 

Należy zauważyć, że formuły są specyficzne dla konfiguracji ER. W polu **Formuła** wprowadź specyficzne dla dokumentu odwołanie do podmiotu typu Odbiorca lub Dostawca. Zamiast wpisywać informacje ręcznie, można odszukać węzeł źródła danych reprezentujący konto odbiorcy lub dostawcy, a następnie kliknąć przycisk **Dodaj źródło danych**, aby zaktualizować formułę. Na przykład jeśli używasz konfiguracji przelewu bankowego ISO 20022, węzłem reprezentującym konto dostawcy jest **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. W przeciwnym razie wpisz dowolny ciąg tekstowy, np. **DE-001**, aby zapisać formułę.

[![Projektant formuł](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

W oknie dialogowym **Wiadomość e-mail do** kliknij przycisk kosza obok pola **Konto źródłowe poczty e-mail**, aby trwale usunąć formułę dotyczącą konta źródłowego wiadomości e-mail. Alternatywnie otwórz projektanta formuł i zmień wcześniej zapisaną formułę. Aby przypisać adresy e-mail, kliknij przycisk **Edytuj**, co spowoduje otwarcie okna dialogowego **Przypisz adresy e-mail**.

[![Przypisywanie adresów e-mail do pocztowego miejsca docelowego](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Adres e-mail konfiguracji

Użyj tego typu wiadomości e-mail, jeśli używana konfiguracja ma w źródłach danych węzeł reprezentujący adres e-mail. W projektancie formuł można użyć źródeł danych i funkcji, aby uzyskać poprawnie sformatowany adres e-mail.

[![Przypisywanie źródła danych adresu e-mail do pocztowego miejsca docelowego](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg) 

**Uwaga:** Serwer usługi Simple Mail Transfer Protocol (SMTP) musi być skonfigurowany i dostępny. Serwer SMTP można określić w programie Finance and Operations w oknie **Administrowanie systemem** &gt; **Ustawienia** &gt; **E-mail** &gt; **Parametry poczty e-mail**.

### <a name="archive-destination"></a>Archiwalne miejsce docelowe

Ta opcja służy do wysyłania danych wyjściowych do folderu programu Microsoft SharePoint lub magazynu w usłudze Microsoft Azure. W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać dane wyjściowe do miejsca docelowego zdefiniowanego przez wybrany typ dokumentu. Do wyboru są dostępne tylko typy dokumentów, dla których ustawiono grupę **Plik**. Definiowanie typów dokumentów odbywa się w oknie **Administrowanie organizacją** &gt; **Zarządzanie dokumentami** &gt; **Typy dokumentów**. Konfiguracja miejsc docelowych ER jest taka sama, jak konfiguracja w systemie zarządzania dokumentami.

[![Strona Typy dokumentów](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg) 

Lokalizacja określa, gdzie plik jest zapisywany. Po włączeniu miejsca docelowego **Archiwum** wyniki wykonania konfiguracji mogą być zapisywane w archiwum zadania. Wyniki można obejrzeć w oknie **Administrowanie organizacją** &gt; **Raportowanie elektroniczne** &gt; **Zarchiwizowane zadania raportowania elektronicznego**. **Uwaga:** Można wybrać typ dokumentu dla archiwum zadań w programie Finance and Operations. Odpowiednie opcje są w oknie **Administrowanie organizacją** &gt; **Obszary robocze** &gt; **Raportowanie elektroniczne** &gt; **Parametry raportowania elektronicznego**.

#### <a name="sharepoint"></a>SharePoint

Plik można zapisać w wyznaczonym folderze programu SharePoint. Domyślny serwer programu SharePoint można zdefiniować w oknie **Administrowanie organizacją** &gt; **Zarządzanie dokumentami** &gt; **Parametry zarządzania dokumentami** na karcie **SharePoint**. Po skonfigurowaniu folderu programu SharePoint można wybrać go jako folder, w którym będą zapisywane dane wyjściowe raportowania elektronicznego dla typu dokumentu. 

[![Wybieranie folderu programu SharePoint](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Magazyn Azure

Gdy w ustawieniu lokalizacji typu dokumentu zostanie zaznaczona wartość **Folder archiwum**, można zapisać plik do magazynu usługi Azure.

### <a name="file-destination"></a>Aplikacja docelowa pliku

Jeśli w ustawieniu **Włączone** zaznaczono wartość **Tak**, po zakończeniu sesji konfiguracji będzie wyświetlane okno dialogowe otwierania lub zapisywania.

### <a name="screen-destination"></a>Miejsce docelowe na ekranie

Jeśli ustawisz w opcji **Włączone** wartość **Tak**, będzie tworzony podgląd danych wyjściowych. Niektóre typy plików, takie jak XML, TXT i PDF, można wyświetlać bezpośrednio w oknie przeglądarki internetowej. Dla innych typów plików, takich jak pliki programów Microsoft Excel lub Word, jest używana usługa Microsoft Office Online.

### <a name="power-bi-destination"></a>Miejsce docelowe w usłudze Power BI

W opcji **Włączone** ustaw wartość **Tak**, aby wykorzystywać konfigurację raportowania elektronicznego (ER) do organizowania przesyłania danych z wystąpienia programu Finance and Operations do usług Microsoft Power BI. Przesłane pliki są przechowywane w wystąpieniu serwera programu Microsoft SharePoint, który musi skonfigurowany do tego celu. Aby uzyskać więcej informacji, zobacz [Używanie konfiguracji raportowania elektronicznego w celu dostarczania do usługi Power BI danych z rozwiązania Finance and Operations](general-electronic-reporting-report-configuration-get-data-powerbi.md). **Wskazówka:** Aby zastąpić domyślne zachowanie (czyli wyświetlanie okno dialogowego konfiguracji), można utworzyć odwołanie do miejsca docelowego oraz plikowe miejsce docelowe dla głównego składnika wyjściowego, a następnie wyłączyć wszystkie miejsca docelowe.

## <a name="security-considerations"></a>Zagadnienia dotyczące zabezpieczeń
Dla miejsc docelowych ER są używane dwa typy uprawnień i obowiązków. Jeden typ kontroluje możliwość obsługi ogólnych miejsc docelowych skonfigurowanych dla firmy (to znaczy kontroluje dostęp do strony **Miejsca docelowe raportowania elektronicznego**). Drugi typ kontroluje zdolność użytkownika aplikacji do zastępowania — w czasie wykonywania — ustawień miejsc docelowych skonfigurowanych przez programistę lub konsultanta funkcjonalnego ER.

| Rola (nazwa w drzewie obiektów aplikacji [AOT])                     | Nazwa roli                                  | Obowiązek (nazwa w drzewie obiektów aplikacji [AOT])                     | Nazwa obowiązku                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Deweloper raportowania elektronicznego             | ERFormatDestinationConfigure        | Konfigurowanie aplikacji docelowej formatu raportowania elektronicznego                |
| ERFunctionalConsultant              | Konsultant funkcjonalny raportowania elektronicznego | ERFormatDestinationConfigure        | Konfigurowanie aplikacji docelowej formatu raportowania elektronicznego                |
| PaymAccountsPayablePaymentsClerk    | Pracownik ds. płatności rozrachunków z dostawcami            | ERFormatDestinationRuntimeConfigure | Konfigurowanie aplikacji docelowej formatu raportowania elektronicznego w trakcie wykonywania |
| PaymAccountsReceivablePaymentsClerk | Pracownik ds. płatności rozrachunków z odbiorcami         | ERFormatDestinationRuntimeConfigure | Konfigurowanie aplikacji docelowej formatu raportowania elektronicznego w trakcie wykonywania |

> [!NOTE]
> W omówionych wyżej obowiązkach są używane dwa uprawnienia. Te uprawnienia mają takie same nazwy, jak odpowiadające im obowiązki: **ERFormatDestinationConfigure** i **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Często zadawane pytania
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Mam zaimportowane konfiguracje elektroniczne i widzę je na stronie konfiguracji raportowania elektronicznego. Ale dlaczego nie widzę ich na stronie miejsc docelowych raportowania elektronicznego?

Kliknij przycisk **Nowy** i wybierz konfigurację w polu **Odwołanie**. Na stronie **Miejsca docelowe raportowania elektronicznego** widać tylko konfiguracje, dla których skonfigurowano miejsca docelowe.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Czy istnieje sposób określenia, które konta magazynu Azure i magazynu dużych obiektów binarnych usługi Azure mają być używane?

Nr Jest używany domyślny magazyn dużych obiektów binarnych usługi Azure, który został zdefiniowany i jest wykorzystywany do zarządzania dokumentami.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Jaki jest cel opcji Aplikacja docelowa pliku w ustawieniach miejsca docelowego? Do czego służy to ustawienie?

Miejsce docelowe **Plik** jest używane do sterowania oknem dialogowym. Jeśli włączysz tę lokalizację docelową lub jeśli dla konfiguracji nie zdefiniowano żadnego miejsca docelowego, po utworzeniu pliku wyjściowego zobaczysz okno dialogowe otwierania lub zapisywania.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Czy możecie dać przykład formuły powodującej odwołanie do konta dostawcy, któremu można wysłać wiadomość e-mail?

Formuła jest specyficzna dla konfiguracji ER. Na przykład jeśli używasz konfiguracji przelewu bankowego ISO 20022, można użyć formuły **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** lub **model.Payments.Creditor.Identification.SourceID**, aby uzyskać skojarzone konto dostawcy.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Jedna z moich konfiguracji formatu zawiera wiele plików zgrupowanych w jeden folder (na przykład Folder1 zawiera pliki Plik1, Plik2 i Plik3). Jak skonfigurować miejsca docelowe, aby plik Folder1.zip nie był tworzony w ogóle, Plik1 był wysyłany pocztą elektroniczną, Plik2 był wysyłany do programu SharePoint, a Plik3 można było otworzyć natychmiast po zakończeniu sesji konfiguracji?

Warunkiem wstępnym jest to, aby format był dostępny w konfiguracjach raportowania elektronicznego. Jeśli masz format, otwórz stronę **Aplikacja docelowa raportowania elektronicznego** i utwórz nowe odwołanie do tej konfiguracji. Następnie trzeba utworzyć cztery plikowe miejsca docelowe, po jednym dla każdego składnika wyjściowego. Utwórz pierwsze plikowe miejsce docelowe, nadaj mu nazwę np. **Folder** i wybierz plik, który reprezentuje folder w Twojej konfiguracji. Następnie kliknij przycisk **Ustawienia** i upewnij się, że wszystkie miejsca docelowe są wyłączone. Dla tego plikowego miejsca docelowego folder nie będzie tworzony. Domyślnie ze względu na zależności hierarchiczne między plikami i folderami nadrzędnymi pliki będą się zachowywać w ten sam sposób. Innymi słowy nie będą nigdzie wysyłane. Aby zastąpić to domyślne zachowanie, należy utworzyć trzy kolejne plikowe miejsca docelowe, po jednym dla każdego pliku. W ustawieniach miejsca docelowego każdego z nich należy włączyć miejsce docelowe, do którego plik ma być wysyłany.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego](general-electronic-reporting.md)




