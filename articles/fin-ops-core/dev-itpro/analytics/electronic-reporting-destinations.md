---
title: Miejsca docelowe raportowania elektronicznego (ER)
description: Ten artykuł zawiera informacje dotyczące zarządzania miejscami docelowymi raportowania elektronicznego, typów obsługiwanych miejsc docelowych oraz względów bezpieczeństwa.
author: kfend
ms.date: 08/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: DocuType, ERSolutionTable
ms.openlocfilehash: b1bf6289e80769dfe8858f307cbb9b217b42dbb4
ms.sourcegitcommit: f2edc193003564c5bee1747f9c2b800feee342bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2022
ms.locfileid: "9360987"
---
# <a name="electronic-reporting-er-destinations"></a>Miejsca docelowe raportowania elektronicznego (ER)

[!include [banner](../includes/banner.md)]

Można skonfigurować miejsce docelowe dla każdej konfiguracji formatu raportowania elektronicznego (ER) i jej składnika wyjściowego (folderu lub pliku). Użytkownicy mający odpowiednie prawa dostępu mogą także modyfikować ustawienia miejsca docelowego w czasie wykonywania. Ten artykuł wyjaśnia problematykę zarządzania miejscami docelowymi w ER, obsługiwane typy miejsc docelowych oraz zagadnienia dotyczące zabezpieczeń.

Konfiguracje formatów w module raportowania elektronicznego (ER) zwykle zawierają co najmniej jeden składnik wyjściowy: plik. Przeważnie konfiguracje zawierają wiele składników wyjściowych w postaci plików różnego typu (na przykład XML, TXT, XLSX, DOC lub PDF), które są zgrupowane w jednym folderze lub wielu folderach. Funkcje zarządzania miejscami docelowymi raportowania elektronicznego pozwalają wstępnie skonfigurować, co się dzieje po uruchomieniu każdego składnika. Domyślnie podczas sesji konfiguracji jest wyświetlane okno dialogowe, które pozwala Ci zapisać lub otworzyć plik. Takie samo zachowanie występuje również podczas importowania konfiguracji ER, gdy nie ustawiono dla niej żadnych konkretnych miejsc docelowych. Po utworzeniu miejsca docelowego dla głównego składnika wyjściowego miejsce to zastępuje domyślne zachowanie, a folder lub plik jest wysyłany zgodnie z ustawieniami tego miejsca docelowego.

## <a name="availability-and-general-prerequisites"></a>Dostępność i ogólne warunki wstępne

Funkcjonalność miejsc docelowych w raportowaniu elektronicznym nie jest dostępna w wersji Microsoft Dynamics AX 7.0 (luty 2016 r.). Dlatego należy zainstalować Microsoft Dynamics 365 for Operations w wersji 1611 (listopad 2016) lub późniejszej, aby można było wykorzystać następujące typy miejsc docelowych:

- [E-mail](er-destination-type-email.md)
- [Archiwizuj](er-destination-type-archive.md)
- [Plik](er-destination-type-file.md)
- [Ekran](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

Alternatywnie można zainstalować jeden z poniższych wstępnie wymaganych składników. Należy jednak pamiętać, że te alternatywy zapewniają bardziej ograniczoną funkcjonalność miejsc docelowych raportowania elektronicznego.

- Aplikacja Microsoft Dynamics AX w wersji 7.0.1 (z maja 2016 r.)
- [Poprawka aplikacji zarządzania miejscami docelowymi raportowania elektronicznego](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

Istnieje również typ docelowy [drukowania ](er-destination-type-print.md). Aby je wykorzystać, należy zainstalować rozwiązanie Microsoft Dynamics 365 Finance w wersji 10.0.9 (kwiecień 2020).

## <a name="overview"></a>Omówienie

Miejsca docelowe można ustawiać tylko dla konfiguracji ER, które zostały [zaimportowane](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally), oraz dla formatów, które są dostępne na stronie **Konfiguracje raportowania elektronicznego**. Funkcje zarządzania miejscami docelowymi ER są dostępne w oknie **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Miejsce docelowe raportowania elektronciznego**.

### <a name="default-behavior"></a>Zachowanie domyślne

Zachowanie domyślne konfiguracji formatu ER jest uzależnione od typu wykonania określonego w momencie uruchomienia formatu ER.

W oknie dialogowym **Raport Intrastat**, na skróconej karcie **Uruchom w tle**, jeśli dla opcji **Przetwarzanie wsadowe** zostanie ustawiona wartość **Nie**, format ER zostanie natychmiast uruchomiony w trybie interaktywnym. Po pomyślnym zakończeniu tego wykonania wygenerowany dokument wychodzący zostanie udostępniony do pobrania.

Jeśli opcja **Przetwarzanie wsadowe** zostanie ustawiona na wartość **Tak**, format ER zostanie uruchomiony w trybie [wsadowym](../sysadmin/batch-processing-overview.md). Odpowiednie zadanie wsadowe zostanie utworzone na podstawie parametrów określonych na karcie **Uruchamianie w tle** okna dialogowego **Parametry modułu ER**.

> [!NOTE]
> Opis zadania informuje Cię o uruchomieniu mapowania formatu ER. Zawiera on również nazwę uruchamianego składnika ER.

[![Uruchamianie formatu ER.](./media/ER_Destinations-RunInBatchMode.png)](./media/ER_Destinations-RunInBatchMode.png)

Informacje o tym zadaniu można znaleźć w kilku miejscach:

- Przejdź do pozycji **Wspólne** \> **Zapytania** \> **Zadania wsadowe** \> **Moje zadania wsadowe**, aby sprawdzić stan zaplanowanego zadania.
- Przejdź do pozycji **Administracja organizacją** \> **Raportowanie elektroniczne** \> **Zadania raportowania elektronicznego**, aby sprawdzić stan zaplanowanego zadania i wyniki wykonania zakończonego zadania. Po pomyślnym zakończeniu wykonywania zadania wybierz pozycję **Pokaż pliki** na stronie **Zadania raportowania elektronicznego**, aby pobrać wygenerowany dokument wychodzący.

    > [!NOTE]
    > Ten dokument jest przechowywany jako załącznik bieżącego rekordu zadania i jest kontrolowany przez strukturę [zarządzania dokumentami](../../fin-ops/organization-administration/configure-document-management.md). [Typ dokumentu](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) używany do przechowywania artefaktów ER tego typu jest konfigurowany w obszarze [parametrów ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

- Na stronie **Zadania raportowania elektronicznego** wybierz pozycję **Pokaż pliki**, aby wyświetlić listę błędów i ostrzeżeń wygenerowanych podczas wykonywania zadania.

    [![Przeglądanie listy zadań ER.](./media/ER_Destinations-ReviewERJobs.png)](./media/ER_Destinations-ReviewERJobs.png)

### <a name="user-configured-behavior"></a>Zachowanie konfigurowane przez użytkownika

Na stronie **Strona docelowa raportowania elektronicznego** można zastąpić domyślne zachowanie konfiguracji. Zaimportowane konfiguracje są wyświetlane na tej stronie dopiero wtedy, gdy klikniesz przycisk **Nowy**, a następnie w polu **Odwołanie** wybierzesz konfigurację, dla której mają zostać utworzone ustawienia miejsca docelowego.

[![Wybieranie konfiguracji w polu Odwołanie.](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

Po utworzeniu odwołania można utworzyć plik docelowy dla każdego **Folderu** lub składnika wyjściowego **Pliku**, do którego istnieje odwołanie w formacie ER.

[![Tworzenie plikowego miejsca docelowego.](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

Następnie można włączać i wyłączać poszczególne miejsca docelowe dla danego miejsca w oknie dialogowym **Ustawienia aplikacji docelowej**. Przycisk **Ustawienia** pozwala kontrolować wszystkie miejsca docelowe należące do wybranego plikowego miejsca docelowego. W oknie dialogowe **Ustawienia aplikacji docelowej** można kontrolować każde miejsce docelowe osobno, ustawiając dla niego opcję **Włączone**.

W wersjach Finance **wcześniejszych niż 10.0.9** można utworzyć **jedno miejsce docelowe pliku** dla każdego składnika wyjściowego tego samego formatu, takiego jak folder lub plik wybrany w polu **Nazwa pliku**. Jednak w **wersji 10.0.9 lub nowszej** można utworzyć **wiele miejsc docelowych plików** dla każdego składnika wyjściowego tego samego formatu.

Można na przykład użyć tej możliwości do skonfigurowania lokalizacji docelowych plików dla składnika pliku używanego do generowania dokumentu wychodzącego w formacie programu Excel. Jeden cel ([archiwalny](er-destination-type-archive.md)) można skonfigurować do przechowywania oryginalnego pliku programu Excel w archiwum zadań ER, a następnie można skonfigurować inne miejsce docelowe ([e-mail](er-destination-type-email.md)), aby jednocześnie [konwertować](#OutputConversionToPDF)  plik programu Excel na format PDF i wysłać plik PDF pocztą elektroniczną.

[![Konfigurowanie wielu lokalizacji docelowych dla pojedynczego elementu formatu.](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

Po uruchomieniu formatu ER są zawsze uruchamiane wszystkie miejsca docelowe skonfigurowane dla składników tego formatu. Ponadto w aplikacji Finance w **wersji 10.0.17 i nowszych** funkcja miejsc docelowych ER została poprawiona i teraz umożliwia skonfigurowanie różnych zestawów miejsc docelowych dla jednego formatu ER. Każdy zestaw jest oznaczany jako skonfigurowany dla określonej akcji użytkownika. Interfejs API ER został [rozszerzony](er-apis-app10-0-17.md), dzięki czemu można określić, że użytkownik wykonuje akcję, uruchamiając format ER. Podany kod akcji jest przekazywany do miejsc docelowych ER. W zależności od podanego kodu akcji można uruchamiać różne miejsca docelowe w formacie ER. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie miejsc docelowych ER zależnych od akcji](er-action-dependent-destinations.md).

## <a name="destination-types"></a>Typy miejsc docelowych

Następujące miejsca docelowe są obecnie obsługiwane w przypadku formatów ER. Można wyłączyć lub włączyć wszystkie typy w tym samym czasie. W ten sposób można albo nic nie robić, albo wysłać składnik do wszystkich skonfigurowanych lokalizacji.

- [E-mail](er-destination-type-email.md)
- [Archiwizuj](er-destination-type-archive.md)
- [Plik](er-destination-type-file.md)
- [Ekran](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [Drukowanie](er-destination-type-print.md)

## <a name="applicability"></a>Możliwość zastosowania

Miejsca docelowe można ustawiać tylko dla konfiguracji ER, które zostały zaimportowane, oraz dla formatów, które są dostępne na stronie **Konfiguracje raportowania elektronicznego**.

> [!NOTE]
> Skonfigurowane miejsca docelowe są specyficzne dla firmy. Jeśli jest planowane użycie formatu ER w różnych firmach w ramach bieżącego Finance, należy skonfigurować miejsca docelowe dla formatu ER dla każdej z tych firm.

Konfigurując miejsca docelowe plików dla wybranego formatu, należy skonfigurować je dla całego formatu.

[![Łącze do konfiguracji.](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

Jednocześnie może istnieć wiele wersji formatu zaimportowanych do bieżącego Finance. Można je wyświetlić w przypadku wybrania łącza **Konfiguracja** oferowanego po zaznaczeniu pola **Odwołanie**.

[![Wersje konfiguracji.](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

Domyślnie skonfigurowane miejsca docelowe są stosowane tylko w przypadku uruchamiania wersji formatu ER o stanie **Ukończony** lub **Udostępniony**. Czasami jednak należy używać skonfigurowanych miejsc docelowych, gdy jest uruchamiana wersja robocza formatu ER. Na przykład można zmodyfikować wersję roboczą formatu, a użytkownik chce użyć skonfigurowanych miejsc docelowych do testowania sposobu dostarczania wygenerowanych danych wyjściowych. Wykonaj poniższe kroki, aby zastosować lokalizacje docelowe dla formatu ER w momencie uruchomienia wersji roboczej.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. Ustawienie opcji **Używaj miejsc docelowych w wersji roboczej** spowoduje, że wartość zmieni się na **Tak**.

[![Opcja Używaj miejsc docelowych w wersji roboczej.](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

Aby można było skorzystać z wersji roboczej formatu ER, należy odpowiednio go oznaczyć format.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. Ustaw wartość **Tak** opcji **Uruchomić**.

[![Opcja ustawienia uruchamiania.](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

Po zakończeniu tego ustawienia opcja **Uruchom wersję roboczą** będzie dostępna dla zmodyfikowanych formatów ER. Tę opcję należy skonfigurować na **Tak** w celu używania wersji roboczej formatu w przypadku uruchomienia formatu.

[![Opcja Uruchom wersję roboczą.](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="destination-failure-handling"></a><a name="DestinationFailure"></a>Obsługa niepowodzeń związanych z miejscem docelowym

Zazwyczaj format ER jest uruchamiany w zakresie określonego procesu biznesowego. Jednak dostarczenie dokumentu wychodzącego, który jest generowany w trakcie wykonywania formatu ER, musi być niekiedy traktowane jako część tego procesu biznesowego. W takim przypadku, jeśli dostawa wygenerowanego dokumentu wychodzącego do skonfigurowanego miejsca docelowego nie powiedzie się, wykonanie procesu biznesowego musi być anulowane. Aby skonfigurować odpowiednie miejsce docelowe ER, wybierz opcję **Zatrzymaj przetwarzanie przy błędzie**.

Można na przykład skonfigurować przetwarzanie płatności dostawcy, tak aby był uruchamiany format schematu ER **ISO20022 Transfer kredytowy** w celu wygenerowania pliku płatności i dokumentów dodatkowych (np. Listu przewodniego i Raportu kontrolnego). Jeśli płatność powinna zostać rozpatrzona pomyślnie, tylko jeśli pozostała część dokumentu zostanie dostarczona pocztą e-mail, należy zaznaczyć pole wyboru **Zatrzymaj przetwarzanie przy błędzie** dla składnika **CoveringLetter** w odpowiednim miejscu docelowym pliku, tak jak to pokazano na poniższej ilustracji. W takim przypadku stan płatności wybranej do przetworzenia zostanie zmieniony z **Brak** na **Wysłane** tylko wtedy, gdy wygenerowany list przewodni zostanie zaakceptowany do dostarczenia przez dostawcę poczty e-mail skonfigurowanego w instancji Finance.

[![Konfigurowanie obsługi procesów dla niepowodzenia miejsca docelowego pliku.](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

Jeśli wyczyścisz pole **Zatrzymaj przetwarzanie przy błędzie** dla składnika **CoveringLetter** w miejscu docelowym pliku, płatność będzie uznana za rozpatrzoną pomyślnie, nawet jeśli list przewodni nie zostanie dostarczony pocztą e-mail. Stan płatności zostanie zmieniony z **Brak** na **Wysłane**, nawet jeśli nie można wysłać listu przewodniego, ponieważ na przykład brakuje adresu e-mail odbiorcy lub nadawcy lub jest on niepoprawny.

## <a name="output-conversion-to-pdf"></a><a name="OutputConversionToPDF"></a>Konwersja danych wyjściowych do formatu PDF

Opcja konwersji pliku PDF umożliwia konwertowanie danych wyjściowych z formatu Microsoft Office (Excel lub Word) na format PDF.

### <a name="make-pdf-conversion-available"></a>Udostępnij konwersję PDF

Aby w bieżącej instancji Finance była dostępna opcja konwersji plików PDF, otwórz obszar roboczy **Zarządzanie funkcjami** i włącz funkcję **Konwertuj wychodzące raporty elektroniczne z formatów Microsoft Office na PDF**.

[![Włączanie funkcji konwersji dokumentów wychodzących na format PDF w module Zarządzanie funkcjami.](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>Możliwość stosowania

W wersjach aplikacji Finance **wcześniejszych niż 10.0.18** opcję konwersji PDF można włączyć tylko w przypadku składników typu **Excel\\File** używanych do generowania danych wyjściowych w formacie pakietu Office (Excel lub Word). Gdy ta opcja jest włączona, dane wyjściowe generowane w formacie pakietu Office są automatycznie konwertowane na format PDF. Jednak w **wersji 10.0.18 i nowszej** można włączyć tę opcję dla składników typu **Common\\File**.

> [!NOTE]
> Należy pamiętać o komunikacie ostrzegawczym, który jest wyświetlany po włączeniu opcji konwersji w formacie PDF dla składnika ER typu **Common\\File**. Ten komunikat informuje, że nie ma możliwości zagwarantowania, w czasie projektowania, że wybrany składnik pliku uwidacznia zawartość w formacie PDF lub konwertowalnym w formacie PDF w czasie wykonywania. Dlatego tę opcję należy włączyć tylko wtedy, gdy użytkownik upewnić się, że wybrany składnik pliku został skonfigurowany tak, aby uwidaczniać zawartość w formacie PDF lub w konwertowalnym formacie PDF w czasie wykonywania.
> 
> Jeśli włączysz opcję konwersji PDF składnika formatu, jeśli ten składnik uwidacznia zawartość w formacie innym niż PDF i jeśli nie można przekonwertować udostępnianej zawartości na format PDF, w czasie wykonywania wystąpi wyjątek. Z dostarczanego komunikatu wynika, że wygenerowanej zawartości nie można przekonwertować na format PDF.

### <a name="limitations"></a>Ograniczenia

Od wersji Finance **10.0.9** opcja konwersji PDF jest dostępna tylko dla wdrożeń w chmurze. Począwszy od wersji Finance **10.0.27** opcja konwersji PDF jest dostępna dla każdego wdrożenia lokalnego, które ma włączoną opcję [Łączność z internetem](../user-interface/client-disconnected.md).

Wygenerowany dokument PDF jest ograniczony do maksymalnej długości wynoszącej 300 stron.

Od Finance w **wersji 10.0.9** w dokumencie PDF wytwarzanym z formatu wyjściowego programu Excel jest obsługiwana tylko pozioma orientacja strony. Począwszy od aplikacji Finance w **wersji 10.0.10 lub nowszych** można określić [orientację strony](#SelectPdfPageOrientation) w dokumencie PDF, który jest tworzony na podstawie danych wyjściowych programu Excel podczas konfigurowania miejsca docelowego ER.

Tylko typowe czcionki systemowe systemu operacyjnego Windows są używane do konwertowania danych wyjściowych, które nie zawierają czcionek osadzonych.

### <a name="resources"></a>Zasoby

Zanim wersja finansowa 10.0.29, konwersja w formacie PDF będzie mogła być wykonywana tylko poza bieżącym wystąpieniem finansów. Wygenerowany plik został wysłany z finansów do usługi konwersji, a następnie usługa zwróciła przekonwertowany dokument. Jednak w wersji **10.0.29 i nowszych** oprócz funkcji **Konwertuj dokumenty wychodzące z formatów Microsoft Office na PDF** możesz włączyć **Wykorzystaj zasoby aplikacji do wykonywania dokumentów CBD konwersja z formatu Word do formatu PDF**. Ta funkcja umożliwia lokalne konwertowanie wygenerowanych dokumentów programu Word na format PDF za pomocą zasobów serwera aplikacji w bieżącym wystąpieniu finansów. 

Oto zalety lokalnej konwersji PDF, gdy włączona jest funkcja **Wykorzystaj zasoby aplikacji do konwersji dokumentów CBD z formatu Word do formatu PDF**:

- Wygenerowany dokument PDF jest [ograniczony](#limitations) do maksymalnej długości wynoszącej liczbę stron.
- Konwertowany dokument programu Word może zawierać wiele [formantów zawartości](https://fix.lcs.dynamics.com/Issue/Details?bugId=647877&dbType=3).
- Łączność internetową nie jest wymagana we wdrożeniach lokalnych.

### <a name="use-the-pdf-conversion-option"></a>Użyj opcji konwersji na PDF

Aby włączyć konwersję pliku PDF dla pliku docelowego, zaznacz pole wyboru **Konwertuj na PDF**.

[![Włączanie konwersji pliku PDF dla miejsca docelowego pliku.](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

### <a name=""></a><a name="SelectPdfPageOrientation">Wybierz orientację strony do konwersji na format PDF</a>

W przypadku generowania konfiguracji ER w formacie programu Excel i konwersji na format PDF można jawnie określić orientację strony dokumentu PDF. Po zaznaczeniu pola wyboru **Konwertuj na PDF** w celu włączenia konwersji do formatu PDF dla pliku docelowego, który generuje plik wyjściowy w formacie programu Excel, pole **Orientacja strony** staje się dostępne w **Ustawieniach konwersji PDF** na skróconej karcie. W polu **Orientacja strony** możesz wybrać preferowaną orientację strony.

[![Wybierz orientację strony do konwersji na format PDF.](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)

Aby można było wybrać orientację strony PDF, zainstaluj rozwiązanie Finance w wersji 10.0.10 lub nowszej. W wersjach aplikacji Finance wcześniejszych niż **10.0.23** ta opcja oferuje następujące opcje orientacji strony:

- Pionowo
- Pozioma

Wybrana orientacja strony jest stosowana do wszystkich stron dokumentu wychodzącego, które są generowane w formacie programu Excel, a następnie konwertowane na format PDF.

Jednak w **wersji 10.0.23 i późniejszych** lista opcji orientacji strony została rozszerzona w następujący sposób:

- Pionowo
- Pozioma
- Specyficzne dla arkusza

Po wybraniu opcji **Specyficzne dla arkusza** każdy arkusz wygenerowanego skoroszytu programu Excel jest konwertowany na plik PDF przy użyciu orientacji strony, która została skonfigurowana dla tego arkusza w używanym szablonie programu Excel. Może to być ostateczny dokument PDF zawierający strony pionowe i poziome. 

Jeśli konfiguracja ER w formacie programu Word jest konwertowana na PDF, orientacja strony dokumentu PDF jest zawsze pobierana z dokumentu programu Word.

## <a name="output-unfolding"></a>Rozwijanie wyjścia

Podczas konfigurowania miejsca docelowego dla komponentu **Folder** formatu ER można określić sposób dostarczania danych wyjściowych z tego komponentu do skonfigurowanego miejsca docelowego.

### <a name="make-output-unfolding-available"></a>Udostępnianie rozwijania danych wyjściowych

Aby udostępnić opcję rozwijania danych wyjściowych w bieżącej instancji programu Finance, należy otworzyć obszar roboczy **Zarządzanie cechami** i włączyć funkcję **Zezwalaj na konfigurowanie miejsc docelowych ER w celu wysyłania zawartości folderów jako oddzielnych plików**.

### <a name="applicability"></a>Możliwość stosowania

Opcja rozwijania wyjścia może być skonfigurowana tylko dla składników formatu typu **Folder**. Po rozpoczęciu konfiguracji komponentu **Folder** na stronie **Elektroniczne miejsce docelowe raportowania** dostępna jest szybka karta **Ogólne**. 

### <a name="use-the-output-unfolding-option"></a>Użyj opcji rozkładania danych wyjściowych

Na skróconej karcie **Ogólne**, w polu **Wyślij folder jako**, wybierz jedną z następujących wartości:

- **Archiwum ZIP** — dostarcza wygenerowany plik jako plik ZIP.
- **Osobne pliki** — dostarcza każdy plik wygenerowanego pliku ZIP jako pojedynczy plik.

    > [!NOTE]
    > Po wybraniu opcji **Oddzielne pliki**, wygenerowane dane wyjściowe zostaną zebrane w pamięci w stanie zmapowana. Dlatego maksymalny [limit rozmiaru pliku](er-compress-outbound-files.md) jest stosowany dla zamapowanych danych wyjściowych, gdy rzeczywisty rozmiar pliku może przekroczyć ten limit. Zaleca się wybranie tej wartości, jeśli oczekiwano, że rozmiar wygenerowanych danych będzie zbyt duży.

[![Konfigurowanie miejsca docelowego składnika formatu folderu.](./media/er_destinations-set-unfolding-option.png)](./media/er_destinations-set-unfolding-option.png)

### <a name="limitations"></a>Ograniczenia

Jeśli ustawisz pole **Wyślij folder jako** na **Oddziel pliki** dla komponentu **Folder**, który zawiera inne zagnieżdżone komponenty **Folder**, ustawienie to nie jest stosowane rekursywnie do zagnieżdżonych komponentów **Folder**.

## <a name="change-page-layout-properties-of-a-template"></a><a name="change-page-layout-properties-of-a-template"></a> Zmień właściwości układu strony szablonu

Można skonfigurować docelowe raportowanie elektroniczne dla składnika raportowania elektronicznego, który został zaprojektowany do użycia szablonu w formacie programu Microsoft Office (Excel lub Word) do generowania raportu. Jeśli nie jesteś właścicielem tego formatu i musisz zmienić właściwości układu strony szablonu formatu, w wersjach rozwiązania Finance wcześniejszych niż 10.0.29 musisz utworzyć format pochodny i zmodyfikować właściwości szablonu. Następnie należy zarządzać konfiguracją formatu pochodnego. Jednak w wersji 10.0.29 i nowszej można zmieniać właściwości układu strony szablonu w czasie wykonywania, aby uniknąć tworzenia i obsługi konfiguracji pochodnego formatu. W tym celu należy skonfigurować żądane właściwości jako część ustawień skonfigurowanego docelowego raportowania elektronicznego. Po uruchomieniu formatu raportowania elektronicznego i uruchomieniu docelowego raportowania elektronicznego, który jest skofingurowany do użycia z właściwościami układu strony wartości właściwości układu strony wykonanego miejsca docelowego są stosowane do szablonu, który jest używany, zastępując właściwości oryginalnego szablonu. Dla składnika tego samego formatu można skonfigurować różne lokalizacje docelowe, konfigurując różne właściwości układu strony dla używanego szablonu.

W lokalizacji docelowej raportowania elektronicznego można skonfigurować następujące właściwości dla składnika formatu, który jest przeznaczony do użycia w formatach programów Excel lub Word:

- Orientacja strony
    - Pionowo
    - Pozioma
- Rozmiar papieru
    - A3
    - A4
    - A5
    - B4
    - B5
    - Executive
    - Informacje prawne
    - Litera
    - Statement
    - Tabloid
- Marginesy strony
    - U góry
        - Nagłówek
    - U dołu
        - Stopka
    - Lewo
    - Prawo

> [!NOTE]
> Orientacja strony szablonu skonfigurowanego w ten sposób musi być wyrównana z [orientacją strony dla konwersji w formacie PDF](#select-a-page-orientation-for-pdf-conversion), jeśli jest skonfigurowana konwersja do formatu PDF.

Musisz wybrać jednostkę długości do ustawienia marginesów strony:

- Cale
- Centymetry
- Milimetry

![Konfigurowanie właściwości układu strony na stronie docelowego raportowania elektronicznego.](./media/er_destinations-set-page-layout-properties.png)

> [!TIP]
> Gdy wartość marginesu jest w centymetrach i określana z wieloma miejscami dziesiętnymi, jest ona zaokrąglana w czasie wykonywania do najbliższej wartości z dokładnością do 1 miejsca dziesiętnego.
>
> Gdy wartość marginesu jest w milimetrach i określana z miejscami dziesiętnymi, jest ona zaokrąglana w czasie wykonywania dla programu Excel do najbliższej wartości liczby całkowitej bez wartości dziesiętnej.
>
> Gdy wartość marginesu jest w milimetrach i określana z wieloma miejscami dziesiętnymi, jest ona zaokrąglana w czasie wykonywania dla programu Word do najbliższej wartości z dokładnością do jednego miejsca dziesiętnego.

## <a name="security-considerations"></a>Zagadnienia dotyczące zabezpieczeń

Dla miejsc docelowych ER są używane dwa typy uprawnień i obowiązków. Jeden typ kontroluje możliwość obsługi ogólnych miejsc docelowych skonfigurowanych dla firmy przez użytkownika (to znaczy kontroluje dostęp do strony **Miejsca docelowe raportowania elektronicznego**). Drugi typ kontroluje zdolność użytkownika aplikacji do zastępowania — w czasie wykonywania — ustawień miejsc docelowych skonfigurowanych przez programistę lub konsultanta funkcjonalnego ER.

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

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>Czy istnieje sposób określenia, które konta magazynu Microsoft Azure i magazynu dużych obiektów binarnych usługi Azure Blob mają być używane?

Nie. Jest używany domyślny magazyn dużych obiektów binarnych usługi Microsoft Azure, który został zdefiniowany i jest wykorzystywany do zarządzania dokumentami.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Jaki jest cel opcji Aplikacja docelowa pliku w ustawieniach miejsca docelowego? Do czego służy to ustawienie?

Miejsce docelowe **Plik** służy do sterowania oknem dialogowym przeglądarki internetowej po uruchomieniu formatu ER w trybie interaktywnym. Jeśli włączysz tę lokalizację docelową lub jeśli dla konfiguracji nie zdefiniowano żadnego miejsca docelowego, po utworzeniu pliku wyjściowego w przeglądarce internetowej pojawi się okno dialogowe otwierania lub zapisywania.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Czy możecie dać przykład formuły powodującej odwołanie do konta dostawcy, któremu można wysłać wiadomość e-mail?

Formuła jest specyficzna dla konfiguracji ER. Na przykład jeśli używasz konfiguracji przelewu bankowego ISO 20022, można użyć formuły **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** lub **model.Payments.Creditor.Identification.SourceID**, aby uzyskać skojarzone konto dostawcy.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Jedna z moich konfiguracji formatu zawiera wiele plików zgrupowanych w jeden folder (na przykład Folder1 zawiera pliki Plik1, Plik2 i Plik3). Jak skonfigurować miejsca docelowe, aby plik Folder1.zip nie był tworzony w ogóle, Plik1 był wysyłany pocztą elektroniczną, Plik2 był wysyłany do programu SharePoint, a Plik3 można było otworzyć natychmiast po zakończeniu sesji konfiguracji?

Twój format musi być dostępny w konfiguracjach raportowania elektronicznego. Jeśli tak jest, otwórz stronę **Aplikacja docelowa raportowania elektronicznego** i utwórz nowe odwołanie do tej konfiguracji. Następnie trzeba utworzyć cztery plikowe miejsca docelowe, po jednym dla każdego składnika wyjściowego. Utwórz pierwsze plikowe miejsce docelowe, nadaj mu nazwę np. **Folder** i wybierz plik, który reprezentuje folder w Twojej konfiguracji. Następnie kliknij przycisk **Ustawienia** i upewnij się, że wszystkie miejsca docelowe są wyłączone. Dla tego plikowego miejsca docelowego folder nie będzie tworzony. Domyślnie ze względu na zależności hierarchiczne między plikami i folderami nadrzędnymi pliki będą się zachowywać w ten sam sposób. Innymi słowy nie będą nigdzie wysyłane. Aby zastąpić to domyślne zachowanie, należy utworzyć trzy kolejne plikowe miejsca docelowe, po jednym dla każdego pliku. W ustawieniach miejsca docelowego każdego z nich należy włączyć miejsce docelowe, do którego plik ma być wysyłany.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)

[Konfigurowanie miejsc docelowych raportowania elektronicznego zależnych od akcji](er-action-dependent-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
