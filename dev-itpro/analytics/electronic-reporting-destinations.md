---
title: Miejsca docelowe raportowania elektronicznego
description: "Można skonfigurować miejsce docelowe dla każdej konfiguracji formatu raportowania elektronicznego (ER) i jej składnika wyjściowego (folderu lub pliku). Użytkownicy, którym udzielono odpowiednich praw dostępu, mogą także modyfikować ustawienia miejsca docelowego w czasie wykonywania. Ten artykuł wyjaśnia problematykę zarządzania miejscami docelowymi w ER, obsługiwane typy miejsc docelowych oraz zagadnienia dotyczące zabezpieczeń."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: d38d05fe445bf0326d408038dff84ccf8c0ff64c
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-destinations"></a>Miejsca docelowe raportowania elektronicznego

Można skonfigurować miejsce docelowe dla każdej konfiguracji formatu raportowania elektronicznego (ER) i jej składnika wyjściowego (folderu lub pliku). Użytkownicy, którym udzielono odpowiednich praw dostępu, mogą także modyfikować ustawienia miejsca docelowego w czasie wykonywania. Ten artykuł wyjaśnia problematykę zarządzania miejscami docelowymi w ER, obsługiwane typy miejsc docelowych oraz zagadnienia dotyczące zabezpieczeń.

Konfiguracje formatów w module raportowania elektronicznego (ER) zwykle zawierają co najmniej jeden składnik wyjściowy: plik. Przeważnie konfiguracje zawierają wiele składników wyjściowych w postaci plików różnego typu (na przykład XML, TXT lub XLSX), które są zgrupowane w jednym folderze lub wielu folderach. Funkcje zarządzania miejscami docelowymi raportowania elektronicznego pozwalają wstępnie skonfigurować, co się dzieje po uruchomieniu każdego składnika. Domyślnie po uruchomieniu konfiguracji, pojawi się okno dialogowe użytkownik może zapisać lub otworzyć plik. Takie samo zachowanie występuje również podczas importowania konfiguracji ER, gdy nie ustawiono dla niej żadnych konkretnych miejsc docelowych. Po utworzeniu miejsca docelowego dla głównego składnika wyjściowego miejsce to zastępuje domyślne zachowanie, a folder lub plik jest wysyłany zgodnie z ustawieniami tego miejsca docelowego.

## <a name="availability-and-general-prerequisites"></a>Dostępność i ogólne warunki wstępne
ER miejsc docelowych nie jest dostępny w usłudze Microsoft Dynamics 365 dla wersji 7.0 operacji (luty 2016). W związku z tym należy zainstalować usługi Microsoft Dynamics 365 dla operacji (listopad 2016 release) korzystać ze wszystkich funkcji, które są opisane w tym temacie. Alternatywnie można zainstalować jeden z następujących warunków wstępnych. Należy jednak pamiętać, że te alternatywne zapewniają bardziej ograniczone doświadczenie przeznaczenia encja-Relacja.

-   Microsoft Dynamics 365 dla wersji aplikacji operacji 7.0.1 (maja 2016)
-   [Poprawkę aplikacji](https://fix.lcs.dynamics.com/issue/results/?q=3160213) do zarządzania miejscami docelowymi w ER

Miejsca docelowe można ustawiać tylko dla konfiguracji ER, które zostały zaimportowane, oraz dla formatów, które są dostępne na stronie **Konfiguracje raportowania elektronicznego**.

## <a name="overview"></a>Przegląd
Funkcje zarządzania ER docelowego jest dostępna w **Administrowanie organizacją**&gt;**elektroniczny w**. W tym oknie można zastąpić domyślne zachowanie konfiguracji. Zaimportowane konfiguracje są tutaj wyświetlane dopiero wtedy, gdy klikniesz przycisk **Nowy**, a następnie w polu **Odwołanie** wybierzesz konfigurację, dla której mają zostać utworzone ustawienia miejsca docelowego.

[![Wybieranie konfiguracji w polu odwołania](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg) 

Po utworzeniu odwołanie, można utworzyć plik docelowy dla każdego folderu lub pliku. 

[![Tworzenie miejsca docelowego pliku](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

**Uwaga:** Można utworzyć jedno plikowe miejsce docelowe dla każdego składnika wyjściowego tego samego formatu, takiego jak folder lub plik wybrany w polu **Nazwa pliku**. Można następnie włączać i wyłączać poszczególne cele, plik docelowy w **ustawienia docelowego miejsca** okno dialogowe. Przycisk **Ustawienia** pozwala kontrolować wszystkie miejsca docelowe należące do wybranego plikowego miejsca docelowego. W oknie dialogowe **Ustawienia aplikacji docelowej** można kontrolować każde miejsce docelowe osobno, ustawiając dla niego opcję **Włączone**.

[![Okno dialogowe Ustawienia docelowego](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Typy miejsc docelowych
Obsługiwane są różne typy miejsc docelowych. Można wyłączyć lub włączyć wszystkie typy w tym samym czasie. W ten sposób można albo nic nie robić, albo wysłać składnik do wszystkich skonfigurowanych lokalizacji. W poniższych sekcjach opisano obsługiwane miejsca docelowe.

### <a name="email-destination"></a>Pocztowe miejsce docelowe

W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać plik wyjściowy pocztą e-mail. Po włączeniu tej opcji można określić adresatów wiadomości e-mail i wpisz temat i treść wiadomości e-mail. Można zdefiniować tekstów stałych dla tematu wiadomości e-mail i treści lub ER formuł można używać do dynamicznego tworzenia tekstów wiadomości e-mail. Adresy e-mail można skonfigurować dla ER na dwa sposoby. Konfigurację można zrealizować w tak samo jak funkcja zarządzania wydruku w usłudze Dynamics 365 dla operacji wykonuje je. Alternatywnie można rozwiązać adres e-mail przy użyciu bezpośredniego odwołania do konfiguracji ER przez formułę.

### <a name="email-address-types"></a>Typy adresów e-mail

Po kliknięciu przycisku **edytować** dla **do** lub **Cc** pole, **pocztą E-mail do** pojawi się okno dialogowe. Następnie można wybrać typ adresu e-mail, którego należy użyć.

[![Wyślij wiadomość e-mail do okno dialogowe](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Zarządzanie drukowaniem

Jeśli wybierzesz **e-mail Zarządzanie drukowaniem** typu, można wprowadzić adresy e-mail środka w **do** pole. Aby używać adresów e-mail, które nie są rozwiązane, należy wybrać typ źródła wiadomości e-mail plik docelowy. Obsługiwane są następujące wartości: **klienta**, **dostawcy**, **prospektu**, **kontakt**, **konkurenta**, **pracownika**, **wnioskodawcy**, **potencjalnego dostawcy**, i **dostawcy niedozwolone**. Po wybraniu typu źródła wiadomości e-mail, użyj przycisku Dalej, aby **źródło konta e-mailowego** pole, aby otworzyć ** Projektant formuł ** formularza. Ten formularz do dołączania formułę, która reprezentuje konto wybranej jednostki do miejsca docelowego poczty e-mail.

[![Konfigurowanie zarządzania drukowaniem e-mail typu](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg) 

Należy zauważyć, że formuły są specyficzne dla konfiguracji ER. W polu **Formuła** wprowadź specyficzne dla dokumentu odwołanie do podmiotu typu Odbiorca lub Dostawca. Zamiast wpisywać informacje ręcznie, można odszukać węzeł źródła danych reprezentujący konto odbiorcy lub dostawcy, a następnie kliknąć przycisk **Dodaj źródło danych**, aby zaktualizować formułę. Na przykład jeśli używasz konfiguracji przelewu bankowego ISO 20022, węzłem reprezentującym konto dostawcy jest **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. W przeciwnym razie wpisz dowolny ciąg tekstowy, np. **DE-001**, aby zapisać formułę.

[![Formula designer](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

W **pocztą E-mail do** okno dialogowe, kliknij przycisk Kosz dalej, aby **źródło konta e-mailowego** pole, aby trwale usunąć formułę dla konta źródłowego wiadomości e-mail. Alternatywnie Otwórz Projektant formuł, aby zmienić formułę, który został wcześniej zapisany. Aby przypisać adresy e-mail, kliknij przycisk **edytować** otworzyć **przypisywanie adresów e-mail** okno dialogowe.

[![Przydzielanie adresów e-mail dla miejsca docelowego poczty e-mail](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Adres e-mail konfiguracji

Użyj tego typu wiadomości e-mail, jeśli węzeł w źródłach danych, który reprezentuje adres e-mail ma konfigurację, której używasz. Można użyć źródła danych i funkcji w projektancie formuł uzyskanie poprawnie sformatowany adres e-mail.

[![Przypisywanie źródła danych adres e-mail dla miejsca docelowego poczty e-mail](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg) 

**Uwaga:** Serwer usługi Simple Mail Transfer Protocol (SMTP) musi być skonfigurowany i dostępny. Można określić serwer SMTP w usłudze Dynamics 365 dla operacji, o **Administracja systemu**&gt;**instalacji**&gt;**E-mail**&gt;**wysłał parametry**.

### <a name="archive-destination"></a>Archiwalne miejsce docelowe

Ta opcja służy do wysyłania danych wyjściowych do folderu programu Microsoft SharePoint lub magazynu w usłudze Microsoft Azure. W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać dane wyjściowe do miejsca docelowego zdefiniowanego przez wybrany typ dokumentu. Do wyboru są dostępne tylko typy dokumentów, dla których ustawiono grupę **Plik**. Definiowanie typów dokumentów o **Administrowanie organizacją**&gt;**Zarządzanie dokumentami**&gt;**typów dokumentów**. Konfiguracja miejsc docelowych ER jest taka sama, jak konfiguracja w systemie zarządzania dokumentami.

[![Strona typów dokumentu](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg) 

Lokalizacja określa, gdzie plik jest zapisywany. Po **archiwum** miejsce docelowe jest włączone, wyniki wykonania konfiguracji mogą być zapisane w archiwum zadania. Można wyświetlić wyniki w **Administrowanie organizacją**&gt;**raportowania elektronicznego**&gt;**raportowania elektronicznego zarchiwizowane zadania**. **Uwaga:** można wybrać typ dokumentu dla archiwum zadania w usłudze Dynamics 365 dla operacji, o **Administrowanie organizacją**&gt;**obszary robocze**&gt;**raportowania elektronicznego**&gt;**Electronic parametry raportowania**.

#### <a name="sharepoint"></a>SharePoint

Plik można zapisać w wyznaczonym folderze programu SharePoint. Zdefiniuj domyślny serwer programu SharePoint o **Administrowanie organizacją**&gt;**Zarządzanie dokumentami**&gt;**parametry zarządzania dokumentami**, na **programu SharePoint** kartę. Po skonfigurowaniu folderu programu SharePoint, można wybrać go jako folder, w której będą zapisywane dane wyjściowe ER dla typu dokumentu. 

[![Wybieranie folderu programu SharePoint](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Magazyn Azure

Gdy w ustawieniu lokalizacji typu dokumentu zostanie zaznaczona wartość **Folder archiwum**, można zapisać plik do magazynu usługi Azure.

### <a name="file-destination"></a>Aplikacja docelowa pliku

Jeśli ustawisz **Enabled** do **tak**, Otwórz lub Zapisz okno dialogowe pojawia się po zakończeniu konfiguracji.

### <a name="screen-destination"></a>Ekran docelowy

Jeśli ustawisz **Enabled** do **tak**, Podgląd danych wyjściowych jest tworzony. Niektórych typów plików, takich jak XML, TXT lub PDF, można wyświetlić bezpośrednio w oknie przeglądarki. Dla innych typów plików, takiego programu Microsoft Excel lub Word, usługi Microsoft Office Online jest używany.

### <a name="power-bi-destination"></a>Miejsce docelowe BI zasilania

Ustaw **Enabled** do **tak** umożliwia konfigurację ER organizują transfer danych z wystąpienia usługi Dynamics 365 dla operacji do usług Microsoft Power BI. Przesłane pliki są przechowywane w wystąpieniu programu Microsoft SharePoint Server, który musi być skonfigurowany do tego celu. Aby uzyskać więcej informacji, zobacz [umożliwia dostarczanie Power BI danych z systemu Dynamics 365 dla operacji elektronicznych konfiguracji raportowania](general-electronic-reporting-report-configuration-get-data-powerbi.md). **Wskazówka:** Aby zastąpić domyślne zachowanie (czyli wyświetlanie okno dialogowego konfiguracji), można utworzyć odwołanie do miejsca docelowego oraz plikowe miejsce docelowe dla głównego składnika wyjściowego, a następnie wyłączyć wszystkie miejsca docelowe.

## <a name="security-considerations"></a>Zagadnienia dotyczące zabezpieczeń
Dla miejsc docelowych ER są używane dwa typy uprawnień i obowiązków. Jeden typ kontroluje możliwość utrzymania ogólnej miejsc, które są skonfigurowane dla podmiotu prawnego (czyli kontroluje dostęp do **Electronic zgłoszenie miejsca docelowe** strony). Drugi typ kontroluje zdolność użytkownika aplikacji do zastępowania — w czasie wykonywania — ustawień miejsc docelowych skonfigurowanych przez programistę lub konsultanta funkcjonalnego ER.

| Rola (nazwa w drzewie obiektów aplikacji [AOT])                     | Nazwa roli                                  | Obowiązek (nazwa w drzewie obiektów aplikacji [AOT])                     | Nazwa obowiązku                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Deweloper raportowania elektronicznego             | ERFormatDestinationConfigure        | Konfigurowanie aplikacji docelowej formatu raportowania elektronicznego                |
| ERFunctionalConsultant              | Konsultant funkcjonalny raportowania elektronicznego | ERFormatDestinationConfigure        | Konfigurowanie aplikacji docelowej formatu raportowania elektronicznego                |
| PaymAccountsPayablePaymentsClerk    | Pracownik ds. płatności rozrachunków z dostawcami            | ERFormatDestinationRuntimeConfigure | Konfigurowanie aplikacji docelowej formatu raportowania elektronicznego w trakcie wykonywania |
| PaymAccountsReceivablePaymentsClerk | Pracownik ds. płatności rozrachunków z odbiorcami         | ERFormatDestinationRuntimeConfigure | Konfigurowanie aplikacji docelowej formatu raportowania elektronicznego w trakcie wykonywania |

**Uwaga:** W omówionych wyżej obowiązkach są używane dwa uprawnienia. Te uprawnienia mają takie same nazwy, jak odpowiadające im obowiązki: **ERFormatDestinationConfigure** i **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Często zadawane pytania
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Mam zaimportowane konfiguracje elektroniczne i widzę je na stronie konfiguracji raportowania elektronicznego. Ale Dlaczego nie widać ich na stronie elektronicznej miejsca docelowe raportowania?

Upewnij się, że możesz kliknąć **nowy** a następnie wybierz konfigurację w **odwołania** pole. Na stronie **Miejsca docelowe raportowania elektronicznego** widać tylko konfiguracje, dla których skonfigurowano miejsca docelowe.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Czy jest jakiś sposób, aby zdefiniować, które konta Azure magazynu i magazynu obiektów Blob są używane?

Nr Jest używany Magazyn Azure Blob domyślne, które jest zdefiniowane i używane do zarządzania dokumentami.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Do czego służy plik docelowy w ustawienia docelowego miejsca? Do czego służy to ustawienie?

Miejsce docelowe **Plik** jest używane do sterowania oknem dialogowym. Po włączeniu tego miejsca docelowego lub przeznaczenia nie jest zdefiniowany dla konfiguracji, zobacz Otwórz lub Zapisz okno dialogowe po utworzeniu pliku wyjściowego.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Czy możecie dać przykład formuły powodującej odwołanie do konta dostawcy, któremu można wysłać wiadomość e-mail?

Formuła jest specyficzna dla konfiguracji ER. Na przykład jeśli używasz konfiguracji przelewu bankowego ISO 20022, można użyć formuły **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** lub **model.Payments.Creditor.Identification.SourceID**, aby uzyskać skojarzone konto dostawcy.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Jedna z moich konfiguracji formatu zawiera wiele plików zgrupowanych w jeden folder (na przykład Folder1 zawiera pliki Plik1, Plik2 i Plik3). Jak skonfigurować miejsca docelowe, aby plik Folder1.zip nie był tworzony w ogóle, Plik1 był wysyłany pocztą elektroniczną, Plik2 był wysyłany do programu SharePoint, a Plik3 można było otworzyć natychmiast po zakończeniu sesji konfiguracji?

Warunkiem jest, że dany format musi być dostępny w konfiguracjach encja-Relacja. Jeśli masz format, otwórz stronę **Aplikacja docelowa raportowania elektronicznego** i utwórz nowe odwołanie do tej konfiguracji. Następnie trzeba utworzyć cztery plikowe miejsca docelowe, po jednym dla każdego składnika wyjściowego. Utwórz pierwsze plikowe miejsce docelowe, nadaj mu nazwę np. **Folder** i wybierz plik, który reprezentuje folder w Twojej konfiguracji. Następnie kliknij przycisk **Ustawienia** i upewnij się, że wszystkie miejsca docelowe są wyłączone. Dla tego plikowego miejsca docelowego folder nie będzie tworzony. Domyślnie ze względu na zależności hierarchiczne między plikami i folderami nadrzędnymi pliki będą się zachowywać w ten sam sposób. Innymi słowy nie będą nigdzie wysyłane. Aby zastąpić to domyślne zachowanie, należy utworzyć trzy kolejne plikowe miejsca docelowe, po jednym dla każdego pliku. W ustawieniach miejsca docelowego każdego z nich należy włączyć miejsce docelowe, do którego plik ma być wysyłany.

# <a name="see-also"></a>Informacje dodatkowe

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)


