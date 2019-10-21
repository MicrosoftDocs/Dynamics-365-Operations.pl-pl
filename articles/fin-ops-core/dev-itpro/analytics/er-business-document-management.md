---
title: Omówienie zarządzania dokumentami biznesowymi
description: Ten temat zawiera informacje dotyczące sposobu korzystania z funkcji zarządzania dokumentami biznesowymi w ramach modułu raportowania elektronicznego.
author: NickSelin
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c84b08ec45dfa7aa9c7b913087a2518bfeedf87
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181572"
---
# <a name="business-document-management-overview"></a>Omówienie zarządzania dokumentami biznesowymi

Użytkownicy biznesowi używają [modułu Raportowanie elektroniczne (ER)](general-electronic-reporting.md), który umożliwia konfigurowanie formatów dokumentów wychodzących zgodnie z wymogami prawnymi obowiązującymi w różnych krajach/regionach. Użytkownicy mogą również zdefiniować przepływ danych w celu określenia, które dane aplikacji są umieszczane w wygenerowanych dokumentach. Struktura ER generuje dokumenty wychodzące w formatach Microsoft Office (skoroszyty programu Excel lub dokumenty programu Word) przy użyciu wstępnie zdefiniowanych szablonów. Szablony są wypełniane zgodnie z wymaganymi danymi, zgodnie z konfiguracją przepływu danych, podczas gdy wymagane dokumenty są generowane. Każdy skonfigurowany format może zostać opublikowany jako część rozwiązania ER w celu wygenerowania określonych dokumentów wychodzących. Ta funkcja jest reprezentowana przez konfigurację formatu ER, która może zawierać szablony, które mogą być używane do generowania różnych dokumentów wychodzących. Użytkownicy biznesowi mogą stosować tę strukturę do zarządzania wymaganymi dokumentami biznesowymi.

**Zarządzanie dokumentami biznesowymi** jest oparte na górnej części struktury ER i umożliwia użytkownikom biznesowym edytowanie szablonów dokumentów biznesowych przy użyciu usługi Microsoft Office 365 lub odpowiedniej aplikacji klasycznych pakietu Microsoft Office. Edycja dokumentów może obejmować zmianę projektów dokumentów biznesowych i dodanie symboli zastępczych dla dodatkowych danych bez zmian kodu źródłowego i nowych wdrożeń. Do aktualizacji szablonów dokumentów biznesowych nie jest wymagana znajomość struktury ER.

> [!NOTE]
> Należy pamiętać, że zarządzanie dokumentami biznesowymi umożliwia modyfikowanie szablonów używanych do generowania dokumentów biznesowych, takich jak zamówienia, faktury itp. Po zmodyfikowaniu szablonu i opublikowaniu jego nowej wersji, ta wersja jest używana do generowania wymaganych dokumentów biznesowych. Do modyfikacji już wygenerowanych dokumentów biznesowych nie można używać narzędzia zarządzania dokumentami biznesowymi.

## <a name="supported-deployments"></a>Obsługiwane wdrożenia

Obecnie funkcja zarządzania dokumentami biznesowymi jest zaimplementowana tylko w przypadku wdrożeń w chmurze. Jeśli ta funkcja jest istotna dla wdrożenia lokalnego, daj nam o tym znać, przekazując informacje zwrotne na witrynie [Pomysły](https://experience.dynamics.com/ideas/).

## <a name="supported-microsoft-office-applications"></a>Obsługiwane aplikacje pakietu Microsoft Office

Aby używać funkcji zarządzania dokumentami biznesowymi do edytowania szablonów w formatach programu Excel lub Word poprzez użycie aplikacji klasycznych pakietu Microsoft Office, należy zainstalować pakiet Microsoft Office  2010 lub nowszy. Jest obługiwana w chmurze i nie jest ona obsługiwana w przypadku wdrożeń lokalnych.

## <a name="business-document-availability"></a>Dostępność dokumentu biznesowego

Następujące raporty z szablonami opartymi na programie Excel są dostępne przy wydaniu publicznej wersji zapoznawczej:

**Rozrachunki z odbiorcami** (Sierpień 2019 r.)

- Faktura zaliczkowa sprzedaży
- Dokument dostawy dla zamówienia sprzedaży

**Rozrachunki z dostawcami** (Sierpień 2019 r.)

- Faktura zaliczkowa zakupu
- Zamówienie zakupu
- Dokument dostawy dla zamówienia zakupu

Dostępnych będzie więcej raportów. Powiadomienia specjalne o dodatkowych raportach będą wysyłane oddzielnie. 

Kompletną listę raportów planowanych na dzień wydania w październiku 2019 można znaleźć w [Konfigurowalne raporty dotyczące dokumentów biznesowych w programach Word i Excel](https://docs.microsoft.com/en-us/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details).

# <a name="example-enable-configure-and-use-business-document-management"></a>Przykład: włączanie, konfigurowanie i korzystanie z zarządzania dokumentami biznesowymi

Wykonaj przykład z tego tematu, aby dowiedzieć się więcej na temat tej funkcji.

## <a name="configure-er-parameters"></a>Konfigurowanie parametrów modułu ER

Ponieważ zarządzanie dokumentami biznesowymi jest tworzone na strukturze ER, należy skonfigurować parametry ER, aby rozpocząć pracę z zarządzaniem dokumentami biznesowymi. W tym celu należy skonfigurować parametry ER, postępując zgodnie z opisem w [Konfigurowanie struktury ER](electronic-reporting-er-configure-parameters.md). Należy również dodać nowego dostawcę konfiguracji, postępując zgodnie z opisem w [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Obszar roboczy ER](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>Importowanie rozwiązań ER

Należy zaimportować konfiguracje ER zawierające szablony dokumentów biznesowych do bieżącego wystąpienia. Aby wykonać tę procedurę, należy pobrać i lokalnie zapisać poniższe pliki.

**Przykładowe rozwiązanie fakturowania dla odbiorcy ER**

| **Plik**                                  | **Zawartość**                                |
|-------------------------------------------|--------------------------------------------|
| Model fakturowania odbiorcy.wersja.2.xml    | [Konfiguracja modelu danych ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Raport FTI odbiorcy (GER).wersja.2.3.xml | [Konfiguracja darmowego formularza ER faktury niezależnej](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Rozwiązanie do sprawdzania płatności przykładowego ER**

| **Plik**                                  | **Zawartość**                                |
|-------------------------------------------|--------------------------------------------|
| Model czeków.wersja.10.xml          | [Konfiguracja modelu danych ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Formularz drukowania czeków.wersja.10.9.xml  | [Konfiguracja formatu ER czeku płatności](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Przykładowe rozwiązanie ER w handlu zagranicznym**

| **Plik**                                  | **Zawartość**                                |
|-------------------------------------------|--------------------------------------------|
| Model Intrastat.wersja.1.xml             | [Konfiguracja modelu danych ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Raport Intrastat.version.1.9.xml          | [Konfiguracja formatu ER raportu kontroli Intrastat](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Aby zaimportować każdy plik, należy wykonać poniższą procedurę Dokonaj importu konfiguracji *modelu danych* ER dla każdego rozwiązania ER w tabelach powyżej zanim zimportujesz odpowiadającą konfigurację *formatu* ER.

1. Otwórz stronę **Administracja organizacji** \> **Raportowanie elektroniczne** \> **Konfiguracje**.
2. Wybierz **Import/eksport** u góry strony.
3. Wybierz **Załaduj z pliku XML**.
4. Wybierz przycisk **Przeglądaj**, aby załadować wymagany plik XML.
5. Wybierz przycisk **OK**, aby potwierdzić import konfiguracji.

![Strona konfiguracji raportowania elektronicznego](./media/BDM-Overview-ERSolutions.png)

Aby uzyskać więcej informacji o importowaniu konfiguracji ER, zapoznaj się z [Zarządzanie cyklem życia konfiguracji Raportowania elektronicznego](general-electronic-reporting-manage-configuration-lifecycle.md).

## <a name="enable-business-document-management"></a>Włącz zarządzanie dokumentem biznesowym

Aby rozpocząć zarządzanie dokumentem biznesowym, należy otworzyć obszar roboczy **Zarządzanie funkcjami** i włączyć funkcję **Zarządzanie dokumentem biznesowym**.

Aby włączyć funkcję zarządzania dokumentem biznesowym dla wszystkich firm, należy wykonać poniższą procedurę.

1. Otwórzz obszar roboczy **Zarządzanie funkcjami**.
2. Na karcie **Nowe** wybierz funkcję **Zarządzanie dokumentem biznesowym**.
3. Wybierz opcję **Włącz teraz**, aby włączyć wybraną funkcję.
4. Odśwież stronę, aby uzyskać dostęp do nowej funkcji.

![Obszar roboczy zarządzanie funkcjami](./media/BDM-Overview-FMEnabling.png)

Aby uzyskać więcej informacji o aktywowaniu nowych funkcji, zapoznaj się z [Zarządzanie funkcjami — omówienie](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-parameters"></a>Konfigurowanie parametrów

Informacje zawarte w poniższych sekcjach służą do konfigurowania podstawowych parametrów zarządzania dokumentem biznesowym.

### <a name="prerequisites-for-parameter-setup"></a>Wymagania wstępne dotyczące ustawień parametrów
Aby można było skonfigurować zarządzanie dokumentami biznesowymi, należy skonfigurować wymagany typ dokumentu w strukturze zarządzania dokumentami. Ten typ dokumentu służy do określania tymczasowego przechowywania dokumentów w formatach pakietu Office (programy Excel i Word), które są używane jako szablony raportów ER. Tymczasowy szablon magazynu można edytować przy użyciu aplikacji klasycznych pakietu Office.

Dla tego typu dokumentu muszą być wybrane następujące wartości atrybutów:

| **Nazwa atrybutu**  | **Wartość atrybutu**   |
|---------------------|-----------------------|
| Klasa               | Dołącz plik           |
| Grupa               | Plik                  |
| Lokalizacja            | SharePoint            |

Aby uzyskać informacje dotyczące konfigurowania wymaganych parametrów zarządzania dokumentami i typów dokumentów, należy zapoznać się z [Konfigurowanie zarządzania dokumentami](../../fin-and-ops/organization-administration/configure-document-management.md).

![Ustaw tyo dokumentu Zarządzania dokumentami](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a>Konfigurowanie parametrów

Do konfigurowania parametrów podstawowych zarządzania dokumentami biznesowymi służy strona parametry **Parametry dokumentu biznesowego**. Tylko określeni użytkownicy mają dostęp do strony. W tym:

- Użytkownicy przypisani do roli **Administratora systemu**.
- Użytkownicy przypisani do dowolnej roli, która jest skonfigurowana do pełnienia obowiązków, **Obsługa parametrów zarządzania dokumentami biznesowymi** (nazwa drzewa obiektów aplikacji (AOT) **ERBDMaintainParameters**).

Aby skonfigurować podstawowe parametry dla wszystkich firm, należy wykonać poniższą procedurę

1. Zaloguj się jako użytkownik z dostępem do strony **Parametry dokumentu biznesowego**.
2. Przejdź do **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zarządzanie dokumentem biznesowym** \> **Parametry dokumentu biznesowego**.
3.  Na stronie **Parametry dokumentu biznesowego** na karcie **Załączniki** w polu **SharePoint typu dokumentu** określ typ dokumentu, który ma być używany do tymczasowego przechowywania szablonów w formatach pakietu Office, podczas gdy są edytowane przy użyciu aplikacji klasycznych pakietu Office. 

> [!NOTE]
> Dla tego parametru są dostępne tylko typy dokumentów skonfigurowane przy użyciu lokalizacji SharePoint.

![Konfiguracja parametrów zarządzania dokumentami biznesowymi](./media/BDM-Overview-BDMSetting.png)

Wybrany typ dokumentu jest specyficzny dla firmy i będzie używany, gdy użytkownik pracuje z Zarządzaniem dokumentami biznesowymi w firmie, dla której jest konfigurowany wybrany typ dokumentu. Gdy użytkownik pracuje z Zarządzaniem dokumentami biznesowymi w innej firmie, ten sam wybrany typ dokumentu brdzie używany jeśli inny typ nie został skonfigurowany dla tej firmy. Jeśli typ dokumentu został skonfigurowany, będzie używany zamiast wybranego w polu **SharePoint typu dokumentu**.

## <a name="configure-access-permissions"></a>Skonfiguruj uprawnienia dostępu do pól

Domyślnie, gdy dostęp do uprawnień Zarządzania dokumentami biznesowymi nie jest włączony, każdy użytkownik mający dostęp do obszaru roboczego Zarządzania dokumentami biznesowymi będzie widział wszystkie szablony rozwiązań ER, które są dostępne. W obszarze roboczym Zarządzania dokumentami biznesowymi zostaną wyświetlone tylko te szablony, które znajdują się w konfiguracjach formatów ER i są oznaczone tagiem **Typ dokumentu biznesowego**.

![Strona konfiguracji raportowania elektronicznego](./media/BDM-Overview-ERFormatTags.png)

Lista szablonów dostępnych w obszarze roboczym zarządzania dokumentami biznesowymi może być ograniczona przez skonfigurowanie uprawnień dostępu. Może to być ważne w przypadku użycia różnych szablonów do tworzenia dokumentów biznesowych dla różnych domen biznesowych (obszarów funkcjonalnych) oraz umożliwiania określonym użytkownikom dostępu do różnych szablonów do edycji w obszarze roboczym zarządzania dokumentami biznesowymi.

Uprawnienia dostępu do zarządzania dokumentami biznesowymi można ustawiać w **Konfiguratorze uprawnień dostępu**. Tylko następujący użytkownicy mają dostęp do strony:

- Użytkownicy przypisani do roli **Administratora systemu**.
- Użytkownicy przypisani do każdej innej roli skonfigurowanej do pełnienia obowiązków **Skonfigurowania uprawnienia dostępu do szablonów dokumentów biznesowych do edycji** (AOT o nazwie **ERBDTemplatesSecurity**).

Aby włączyć funkcję dostępu do zarządzania dokumentem biznesowym dla wszystkich firm, należy wykonać poniższą procedurę.

1. Zaloguj się jako użytkownik z dostępem do strony **Konfigurator uprawnień dostępu**.
2. Przejdź do **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zarządzanie dokumentem biznesowym** \> **Zarządzaj uprawnieniami dostępu**.

Zwróć uwagę na powiadomienie informujące, że użycie uprawnień dostępu dla zarządzania dokumentem biznesowym nie jest obecnie włączone.

![Strona konfigurator uprawnień dostępu do zarządzania dokumentami biznesowymi](./media/BDM-Overview-TemplatesAccess1.png)

W przypadku tego ustawienia każdy użytkownik przypisany do dowolnej roli zabezpieczeń skonfigurowanej do obsługi **szablonów dokumentów biznesowych** (AOT nazwa **ERBDManageTemplates**) ma możliwość otwarcia zarządzania dokumentami biznesowymi w obszarze roboczym i może edytować dowolny dostępny szablon.

Na poniższym rysunku pokazano, co jest dostępne w obszarze roboczym zarządzanie dokumentami biznesowymi dla użytkowników przypisanych do roli **Pracownik ds. rozrachunków z odbiorcami**. Korzystając z bieżącego ustawienia uprawnień dostępu, użytkownik może edytować szablony dokumentów biznesowych z różnych obszarów funkcjonalnych, w tym fakturowania, raportowania i płatności wykonawczych.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-TemplatesForAlice1.png)

3. Na stronie **konfigurator uprawnień dostępu** wybierz **Ustawienia uprawnień dostępu**.
4. W oknie **ustawienia uprawnień dostępu do edytowania szablonów** włącz opcję **Zastosuj skonfigurowane uprawnienia dostępu**.
5. Wybierz **OK**, aby potwierdzić włączenie uprawnień dostępu zarządzanie dokumentami biznesowymi.

![Konfiguracja uprawnień dostępu do zarządzania dokumentami biznesowymi](./media/BDM-Overview-TemplatesAccess2.png)

6. Wybierz przycisk **Dodaj**, aby wprowadzić nową rolę biznesową, dla której mają być skonfigurowane uprawnienia dostępu do szablonów zarządzania dokumentami biznesowymi.
7. W oknie dialogowym **Role zabezpieczeń** wybierz rolę **pracownika rozrachunków z odbiorcami**, a następnie wybierz przycisk **OK**, aby potwierdzić wybór roli.
8. Na karcie **Uprawnienia dostępu wg znaczników konfiguracji** konfiguracji wybierz opcję **Nowy**.
9. W polu **typ znacznika** wybierz opcję **obszar funkcjonalny**, a następnie w polu **identyfikator** wybierz opcję **fakturowanie**.
10. Wybierz opcję **Zapisz**, aby zapisać skonfigurowane uprawnienia dostępu dla wybranej roli.

  Bieżące ustawienie oznacza każdego użytkownika przypisanego do roli **Pracownik ds. rozrachunków z odbiorcami** i wykonującego obowiązki, **Zarządzaj szablonami dokumentów biznesowych** (AOT o nazwie **ERBDManageTemplates**), format ER szablonów konfiguracji, które mają wartość **fakturowania** dla znacznika **obszaru funkcjonalnego**, będą dostępne do edycji w obszarze roboczym zarządzanie dokumentami biznesowymi.

11. Przełącz **pokrewne okienko informacyjne** od prawej strony bieżącej strony. W okienku **informacji pokrewnych** są wyświetlane informacje o sposobie stosowania skonfigurowanych uprawnień dostępu, w tym o tym, jakie szablony konfiguracji ról będą dostępne dla użytkowników przypisanych do roli **Pracownik ds. rozrachunków z odbiorcami**.

![Konfiguracja uprawnień dostępu do zarządzania dokumentami biznesowymi](./media/BDM-Overview-TemplatesAccess3.png)

12. Na karcie **Uprawnienia dostępu wg znaczników konfiguracji** konfiguracji wybierz opcję **Dodaj**.
13. W oknie dialogowym **wybierz konfigurację** zaznacz opcję Konfiguracja formatu ER **Raport Intrastat**.
14. Wybierz **OK**, aby potwierdzić wprowadzanie wybranych konfiguracji, a następnie wybierz **Zapisz**, aby zapisać skonfigurowane uprawnienia dostępu dla wybranej roli.

Bieżące ustawienie oznacza każdego użytkownika przypisanego do roli **Pracownik ds. rozrachunków z odbiorcami** i wykonującego obowiązki, **Zarządzaj szablonami dokumentów biznesowych** (AOT o nazwie **ERBDManageTemplates**), następujące szablony konfiguracji, które mają wartość fakturowania dla znacznika obszaru funkcjonalnego, będą dostępne do edycji w obszarze roboczym zarządzanie dokumentami biznesowymi:

- Szablony mające wartość, czyli **fakturowanie** dla znacznika **obszaru funkcjonalnego**.
- Szablony z konfiguracji formatów ER, które są wymienione na karcie **Uprawnienia dostępu wg konfiguracji** (szablony z konfiguracji formatu **raportu Intrastat** w domenie **raportowania ustawowego** w tym przykładzie).

![Konfiguracja uprawnień dostępu do zarządzania dokumentami biznesowymi](./media/BDM-Overview-TemplatesAccess4.png)

Na poniższym rysunku pokazano, co jest dostępne w obszarze roboczym zarządzanie dokumentami biznesowymi dla użytkowników przypisanych do roli **Pracownik ds. rozrachunków z odbiorcami**. Przy użyciu bieżącego ustawienia uprawnień dostępu zarządzanie dokumentami biznesowymi użytkownik może edytować szablony dokumentów biznesowych za pomocą domeny **fakturowania** oraz konfiguracji formatu w **raportach Intrastat**. Szablony z domeny **płatności** są niedostępne dla roli **Pracownik ds. rozrachunków z odbiorcami**.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> Reguły **Uprawnienia dostępu wg konfiguracji** są przechowywane przy użyciu unikatowego identyfikatora konfiguracji formatu ER. Oznacza to, że te reguły nie zostaną usunięte po usunięciu konfiguracji ER odwołującej się do tych reguł. Po zaimportowaniu usuniętych konfiguracji z powrotem do wystąpienia te reguły będą odnosiły się do nich na nowo. Nie ma potrzeby ponownego konfigurowania reguł po ponownym zaimportowaniu usuniętych konfiguracji.

## <a name="use-business-document-management-to-edit-templates"></a>Edytowanie szablonów przy użyciu funkcji zarządzania dokumentami biznesowymi

Użytkownicy biznesowi mogą uzyskiwać dostęp do szablonów dokumentów biznesowych do edycji w obszarze roboczym zarządzanie dokumentami biznesowymi. Tylko następujący użytkownicy mogą uzyskać dostęp do obszaru roboczego zarządzanie dokumentami biznesowymi:

- Użytkownicy przypisani do roli **Administratora systemu**.
- Użytkownicy przypisani do dowolnej roli, która jest skonfigurowana do pełnienia obowiązków, **Zarządzaj szablonami dokumentów biznesowych** (nazwa drzewa obiektów aplikacji (AOT) **ERBDMaintainParameters**).

Aby edytować szablony faktur niezależnych w obszarze roboczym zarządzanie dokumentami biznesowymi, należy wykonać poniższą procedurę. Przed wykonaniem tej procedury należy wykonać wszystkie opisane powyżej procedury przedstawione w tym temacie.

1. Zaloguj się jako użytkownik z dostępem do strony obszaru roboczego zarządzania dokumentami biznesowymi.
2. Otwórz obszaru roboczy zarządzania dokumentami biznesowymi.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingTemplate1.png)

Zawartość wybranego szablonu jest przedstawiana na karcie **szablony**. Wybierz kartę **szczegóły**, aby przejrzeć szczegóły wybranego szablonu, a także szczegóły konfiguracji formatu ER, w którym znajduje się ten szablon. Zauważ, że wszystkie szablony mają stan **opublikowane** i nie zawierają szczegółów w kolumnie **korekta**. Oznacza to, że te szablony nie są obecnie edytowane.

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>Inicjuj Edytowanie szablonów należących do Twojego dostawcy konfiguracji.

1. W obszarze roboczym zarządzanie dokumentami biznesowymi wybierz szablon **drukowania czeków z listy**.
2. Kliknij kartę **Szczegóły**.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingTemplate2.png)

Opcja **Edytuj szablon** jest dostępna dla wybranego szablonu. Ta opcja jest zawsze dostępna dla szablonu w konfiguracji formatu modułu, który jest własnością aktywnego dostawcy konfiguracji usługi ER (**Litware, Inc.** w tym przykładzie). Po wybraniu opcji **Edytuj szablon**, istniejący szablon z wersji roboczej w źródłowej konfiguracji formatu w module ER będzie dostępny do edycji.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Inicjuj Edytowanie szablonów należących do innych dostawców.

1. W obszarze roboczym zarządzanie dokumentami biznesowymi wybierz szablon **Raport FTI odbiorcy (GER)**.
2. Kliknij kartę **Szczegóły**.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingTemplate3.png)

Opcja **Nowy dokument** jest dostępna dla wybranego szablonu. Ta opcja jest zawsze dostępna dla szablonu w konfiguracji formatu ER, który jest własnością innego dostawcy (**Litware, Inc.** w tym przykładzie). Po wybraniu **Nowy dokument** do edycji będzie dostępny nowy szablon. Edytowany szablon zostanie następnie zapisany w nowej konfiguracji formatu, która jest generowana automatycznie.

### <a name="start-editing-a-template"></a>Rozpocznij edycję szablonu

1. Z wybranego szablonu wybierz opcję **nowy dokument**.
2. W polu **tytuł**, w razie potrzeby, Zmień tytuł szablonu edytowalnego. Tekst będzie używany do napełniania nazwy tworzonej automatycznie konfiguracji formatu ER. Należy zauważyć, że wersja robocza tej konfiguracji (**Raport o fakturach niezależnych dla odbiorców (GER)**) będzie zawierać edytowany szablon, zostanie automatycznie oznaczona do uruchomienia tego formatu ER dla bieżącego użytkownika. W tym samym czasie, niezmodyfikowany oryginalny szablon z podstawowej konfiguracji formatu źródłowego będzie używany do uruchamiania tego formatu ER dla innego użytkownika.
3. W polu **nazwa** Zmień nazwę pierwszej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.
4. W polu **Komentarz** zmień uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingTemplate4.png)

5. Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.

Otworzy się strona **Edytor szablonów BDM**. Wybrany szablon będzie dostępny do edycji w trybie online za pomocą Office 365.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-office-365"></a>Edytuj szablon w formularzu Office 365

Zmodyfikuj szablon, korzystając z funkcji systemu Office 365. Na przykład w przypadku witryny Office Online w nagłówku szablonu należy zmienić czcionkę z pola **zwykły** na **pogrubiony**. Te zmiany są automatycznie przechowywane dla szablonu edytowalnego, który jest przechowywany w magazynie podstawowego szablonu (domyślnie magazyn obiektów BLOB systemu Azure) skonfigurowanym dla struktury ER.

![Strona edytora szablonów zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a>Edytowanie szablonu w aplikacji pulpitu pakietu Office

1. Wybierz opcję **Otwórz w aplikacji klasycznej**, aby zmodyfikować szablon za pomocą funkcji aplikacji pulpitu pakietu Office (w tym przykładzie programu Excel). Szablon edytowalny jest kopiowany z magazynu trwałego do tymczasowego magazynu skonfigurowanego w parametrach zarządzania dokumentami biznesowymi SharePoint jako folder.
2. Potwierdź, że chcesz otworzyć szablon z tymczasowego przechowywania plików w aplikacji klasycznej programu Office Excel.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingLayout3.png)

3. Modyfikowanie szablonu. Na przykład zmień czcionkę pól podpowiedzi w nagłówku szablonu, zmieniając kolor z **Czarny** na **Niebieski**.

![Strona edytora szablonów zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingLayout4.png)

4. Wybierz **Zapisz** w aplikacji klasycznej programu Excel, aby zapisać zmiany w szablonie w magazynie tymczasowym.

![Strona edytora szablonów zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingLayout5.png)

5. Zamknij aplikację pulpitu programu Excel.
6. Wybierz opcję **Synchronizuj przechowywaną kopię**, aby zsynchronizować tymczasowy magazyn szablonu z trwałym magazynem szablonów.

> [!NOTE]
> Kopia szablonu edytowalnego w magazynie plików tymczasowych jest przechowywana tylko w bieżącej sesji edytowania szablonu. Po zakończeniu tej sesji przez zamknięcie strony **edytora szablonów BDM** ta kopia zostanie usunięta. Jeśli szablon został dostosowany do tymczasowego magazynu plików i nie wybrano opcji **Synchronizuj kopięprzechowywaną**, podczas próby zamknięcia strony **edytora szablonów BDM** zostanie wyświetlony komunikat z pytaniem, czy mają być przechowywane wprowadzone zmiany. Wybierz **Tak**, jeśli chcesz zapisać zmiany w szablonie w trwałej lokalizacji pliku.

### <a name="validate-a-template"></a>Weryfikuj szablon

1. Na stronie **Edytor szablonów BDM** wybierz opcję **Sprawdź, czy występują problemy**, aby sprawdzić zmodyfikowany szablon zgodnie z podstawową konfiguracją formatu ER. Postępuj zgodnie z zaleceniami (jeśli istnieją), aby wyrównać szablon zgodnie ze strukturą formatu w podstawowej konfiguracji formatu ER.
2. Wybierz opcję **Pokaż format**, aby wyświetlić bieżącą strukturę formatu z podstawowej konfiguracji formatu w formacie encji, która musi być wyrównana do szablonu edytowalnego. 
3. Aby zamknąć okienko, wybierz opcję **Ukryj format**.

![Strona edytora szablonów BDM BDM](./media/BDM-Overview-EditingTemplate6.png)

4. Zamknij stronę **Edytor szablonów BDM**.

Zaktualizowany szablon jest wyświetlany na karcie **szablon**. Zauważ, że stan edytowanego szablonu to teraz **wersja robocza**, a bieżąca wersja nie jest już pusta. Oznacza to, że proces edycji tego szablonu został rozpoczęty.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>Testowanie zmodyfikowanego szablonu 

1. W rozliczeniu Zmień firmę na **USMF**.
2. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
3. Wybierz fakturę **FTI-00000002**, a następnie wybierz opcję **Zarządzanie drukowaniem**.
4. Wybierz **Moduł - Rozrachunki z odbiorcami** \> **Dokumenty** \> **Faktura niezależna** \> **Dokument oryginalny**, aby określić zakres faktur do przetwarzania.
5. W polu **format raportu** wybierz format **Raport o fakturach niezależnych dla odbiorców (GER)** formatu ER dla określonego poziomu dokumentu.

![Strona ustawień zarządzania drukowaniem](./media/BDM-Overview-TestRun1.png)

6. Naciśnij klawisz **Escape**, aby zamknąć bieżącą stronę
7. Wybierz opcję **Drukuj**, a następnie kliknij opcję **wybrane**.
8. Pobierz dokument i otwórz go za pomocą aplikacji pulpitu programu Excel.

![Strona faktur niezależnych](./media/BDM-Overview-TestRun2.png)

Zmodyfikowany szablon jest używany do generowania raportu faktury niezależnej dla wybranego towaru. Aby przeanalizować sposób, w jaki ten raport ma wpływ na zmiany wprowadzone w szablonie, można uruchomić ten raport bezpośrednio po zmodyfikowaniu szablonu w innej sesji aplikacji.

### <a name="create-an-alternative-template-revision"></a>Tworzenie alternatywnego szablonu korekty

1. Umożliwia otwarcie strony **edytora szablonów BDM** i wybranie szablonu **kopii FTI raportu odbiorcy (GER)**.
2. Na karcie **poprawki** wybierz opcję **nowa**.
3. W razie potrzeby w polu **nazwa** zmień nazwę drugiej poprawki i oprzyj ją na aktualnie aktywnej pierwszej korekcie.
4. Jeśli istnieje potrzeba, w polu **Komentarz** zmień uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-AddRevision.png)

Utworzono nową wersję szablonu, która została zapisana w magazynie trwałego szablonu. Teraz możesz kontynuować edytowanie szablonu drugiej poprawki, która jest obecnie wybrana jako aktywna.

5. Wybierz pierwszą poprawkę, a następnie wybierz **Ustaw jako aktywną**. Można wybrać inną poprawkę jako aktywną, jeśli użytkownik chce powrócić do tej wersji szablonu.
6. Wybierz drugą poprawkę i wybierz przycisk **Usuń**.
7. Wybierz opcję **OK**, aby potwierdzić usunięcie danych. Jeśli nie są już potrzebne, można usunąć wszystkie nieaktywne korekty.

### <a name="delete-a-modified-template"></a>Usuwanie szablonu zmodyfikowanego

1. Na stronie **Edytor szablonów BDM** wybierz kartę **szablon**.
2. Wybierz opcję **Usuń**.
3. Jeśli zostanie wybrana **OK** w celu potwierdzenia usunięcia, zostanie usunięty format ER **kopia raportu o fakturach niezależnych dla odbiorców (GER)** z zmodyfikowanym szablonem. Wybierz **Anuluj**, aby poznać inne opcje.

### <a name="revoke-changes-of-template"></a>Cofnij zmiany szablonu

Podczas edytowania szablonu z formatu ER, który jest własnością bieżącego aktywnego dostawcy, zostanie zaproponowana opcja odwołania wprowadzonych zmian w szablonie.

![Omówienie obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-Overview-RevokeChanges.png)

1. Na stronie **Edytor szablonów BDM** wybierz kartę **szablon**.
2. Wybierz **Cofnij**.
3. Jeśli wybierzesz **OK**, aby anulować zmiany wprowadzone dla szablonu, zmodyfikowany szablon zostanie zastąpiony oryginalnym szablonem, a wszystkie zmiany zostaną usunięte. Po cofnięciu zmian w szablonie będzie można usunąć szablon. Wybierz **Anuluj**, aby poznać inne opcje.

### <a name="publish-a-modified-template"></a>Publikacja szablonu zmodyfikowanego
1. Na stronie **Edytor szablonów BDM** wybierz kartę **szablon** i wybierz **Opublikuj**.
2. Jeśli zostanie wybrana **OK** w celu potwierdzenia publikowania, wersja robocza raportu **kopii FTI raportu odbiorcy (GER)** formatu ER, która zawiera zmodyfikowany szablon, zostanie oznaczona jako zakończona. Zmodyfikowany szablon staje się dostępny dla innych użytkowników. Wersje ukończone tego formatu ER zachowają tylko ostatnią aktywną korektę szablonu. Inne zmiany zostaną usunięte. Wybierz **Anuluj**, aby poznać inne opcje.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

#### <a name="i-selected-new-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-office-365-web-page"></a>Wybrałem **nowy dokument**, ale zamiast otwierania strony **edytora szablonów BDM** w Finance and Operations, został wysłany do strony Office 365 sieci Web.
Jest to znany błąd dotyczący Office 365 przekierowania. Dzieje się tak po pierwszym zalogowaniu Office 365. W celu obejścia tego problemu należy wybrać **Wstecz** w przeglądarce, aby przejść z powrotem.

#### <a name="i-understand-how-to-edit-a-template-by-using-office-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-adjusting-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-do-this-using-the-office-desktop-application"></a>Wiem, jak edytować szablon, używając Office 365 w pierwszej sesji aplikacji i jak używać szablonu w drugiej sesji aplikacji podczas dopasowywania szablonu, aby zobaczyć, jak zmiany wpływają na wygenerowany dokument biznesowy. Czy można to zrobić za pomocą aplikacji pulpitu Office?
Tak, można. W pierwszej sesji aplikacji wybierz opcję **Otwórz w aplikacji klasycznej**. Szablon będzie przechowywany w tymczasowym magazynie plików i otwarty w aplikacji pulpitu Office. Następnie wykonaj następujące kroki, aby przejrzeć zmiany w szablonie w wygenerowanym dokumencie biznesowym:

1. Wprowadź zmiany w szablonie przy użyciu aplikacji pulpitu pakietu Office.
2. Wybierz opcję **Zapisz** w aplikacji pulpitu Office.
3. Na stronie **Edytor szablonów BDM** w pierwszej sesji aplikacji wybierz opcję **Synchronizuj kopię przechowywaną**.
4. Wykonaj ten szablon formatu ER aplikacji w drugiej sesji aplikacji.

#### <a name="i-get-the-error-value-cannot-be-null-parameter-name-externalid-when-i-select-open-in-desktop-app-how-do-i-work-around-this"></a>Jest wyświetlany komunikat o błędzie „Wartość nie może być zerowa". Nazwa parametru: externalId’ po wybraniu **Otwórz w aplikacji klasycznej** Jak mogę to obejść? 
Najprawdopodobniej zalogowano się do bieżącego wystąpienia aplikacji w domenie Azure AD, które różnią się od domeny Azure AD, która została użyta do wdrożenia tego wystąpienia. Ponieważ usługa SharePoint, która jest używana do przechowywania szablonów do udostępniania ich do edycji za pomocą aplikacji klasycznych pakietu Office, należy do tej samej domeny, nie ma żadnych uprawnień dostępu do usługi SharePoint. Aby rozwiązać ten problem, zaloguj się do bieżącego wystąpienia, używając poświadczeń użytkownika z poprawną domeną Azure AD.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego](general-electronic-reporting.md)

[Projektowanie konfiguracji do generowania raportów w formacie OPENXML](tasks/er-design-reports-openxml-2016-11.md)

[Projektowanie konfiguracji raportowania elektronicznego w celu generowania raportów w formacie programu Word](tasks/er-design-configuration-word-2016-11.md)

[Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md)

[Konfigurowanie w module Raportowanie elektroniczne ściągania danych do usługi Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)
