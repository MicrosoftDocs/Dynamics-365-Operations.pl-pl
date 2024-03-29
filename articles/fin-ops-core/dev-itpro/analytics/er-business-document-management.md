---
title: Omówienie zarządzania dokumentami biznesowymi
description: Ten artykuł zawiera informacje dotyczące sposobu korzystania z funkcji zarządzania dokumentami biznesowymi w ramach modułu raportowania elektronicznego.
author: kfend
ms.date: 04/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.assetid: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERSecurityAccessEditor
ms.openlocfilehash: 0fab7e1a36d9b4092cf4353533704859e83bed26
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288297"
---
# <a name="business-document-management-overview"></a>Omówienie zarządzania dokumentami biznesowymi

[!include [banner](../includes/banner.md)]

Użytkownicy biznesowi używają platformy [Raportowanie elektroniczne (ER)](general-electronic-reporting.md), która umożliwia konfigurowanie formatów dokumentów wychodzących zgodnie z wymogami prawnymi obowiązującymi w różnych krajach/regionach. Użytkownicy mogą również zdefiniować przepływ danych w celu określenia, które dane aplikacji są umieszczane w wygenerowanych dokumentach. Struktura ER generuje dokumenty wychodzące w formatach Microsoft Office (skoroszyty programu Excel lub dokumenty programu Word) przy użyciu wstępnie zdefiniowanych szablonów. Szablony są wypełniane zgodnie z wymaganymi danymi, zgodnie z konfiguracją przepływu danych, podczas gdy wymagane dokumenty są generowane. Każdy skonfigurowany format może zostać opublikowany jako część rozwiązania ER w celu wygenerowania określonych dokumentów wychodzących. Ta funkcja jest reprezentowana przez konfigurację formatu ER, która może zawierać szablony, które mogą być używane do generowania różnych dokumentów wychodzących. Użytkownicy biznesowi mogą stosować tę strukturę do zarządzania wymaganymi dokumentami biznesowymi.

**Zarządzanie dokumentami biznesowymi** jest oparte na górnej części struktury ER i umożliwia użytkownikom biznesowym edytowanie szablonów dokumentów biznesowych przy użyciu usługi Microsoft 365 lub odpowiedniej aplikacji klasycznych pakietu Microsoft Office. Edycja dokumentów może obejmować zmianę projektów dokumentów biznesowych i dodanie symboli zastępczych dla dodatkowych danych bez zmian kodu źródłowego i nowych wdrożeń. Do aktualizacji szablonów dokumentów biznesowych nie jest wymagana znajomość struktury ER.

> [!NOTE]
> Należy pamiętać, że zarządzanie dokumentami biznesowymi umożliwia modyfikowanie szablonów używanych do generowania dokumentów biznesowych, takich jak zamówienia, faktury itp. Po zmodyfikowaniu szablonu i opublikowaniu jego nowej wersji, ta wersja jest używana do generowania wymaganych dokumentów biznesowych. Do modyfikacji już wygenerowanych dokumentów biznesowych nie można używać narzędzia zarządzania dokumentami biznesowymi.

## <a name="supported-deployments"></a>Obsługiwane wdrożenia

Obecnie funkcja zarządzania dokumentami biznesowymi jest zaimplementowana tylko w przypadku wdrożeń w chmurze. Jeśli ta funkcja jest istotna dla wdrożenia lokalnego, daj nam o tym znać, przekazując informacje zwrotne na witrynie [Pomysły](https://experience.dynamics.com/ideas/).

## <a name="supported-microsoft-office-applications"></a>Obsługiwane aplikacje pakietu Microsoft Office

Aby używać funkcji zarządzania dokumentami biznesowymi do edytowania szablonów w formatach programu Excel lub Word poprzez użycie aplikacji klasycznych pakietu Microsoft Office, należy zainstalować pakiet Microsoft Office  2010 lub nowszy. To rozwiązanie jest obsługiwane we wdrożeniach w chmurze i lokalnych.

Aby używać funkcji zarządzania dokumentami biznesowymi do edytowania szablonów w formatach programu Excel lub Word poprzez użycie aplikacji platformy Microsoft 365, należy zainstalować pakiet Microsoft 365 Office w ramach subskrypcji internetowej. To rozwiązanie jest obsługiwane we wdrożeniu w chmurze.

## <a name="business-document-availability"></a>Dostępność dokumentu biznesowego

Kompletna lista raportów planowanych na dzień wydania w październiku 2019 znajduje się w temacie [Konfigurowalne raporty dotyczące dokumentów biznesowych w programach Word i Excel](/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details).

Kompletna lista raportów planowanych na dzień wydania w październiku 2020 znajduje się w temacie [Konfigurowalne raporty dotyczące dokumentów biznesowych — szablony programu Word](/dynamics365-release-plan/2020wave1/dynamics365-finance/configurable-business-documents-word-templates).

Więcej raportów będzie dostępnych w przyszłych wersjach. Powiadomienia specjalne o dodatkowych raportach będą wysyłane oddzielnie. Aby się dowiedzieć, jak przejrzeć listę dostępnych obecnie raportów, zobacz poniżej sekcję [Lista konfiguracji ER wydanych w aplikacji Finance w celu obsługi konfigurowalnych dokumentów biznesowych](#list-of-configurations-cbd).

Wykonaj przykład z tego artykułu, aby dowiedzieć się więcej na temat tej funkcji.

## <a name="configure-er-parameters"></a>Konfigurowanie parametrów modułu ER

Ponieważ zarządzanie dokumentami biznesowymi jest tworzone na strukturze ER, należy skonfigurować parametry ER, aby rozpocząć pracę z zarządzaniem dokumentami biznesowymi. W tym celu należy skonfigurować parametry ER, postępując zgodnie z opisem w [Konfigurowanie struktury raportowania elektronicznego (ER)](electronic-reporting-er-configure-parameters.md). Należy również dodać nowego dostawcę konfiguracji, postępując zgodnie z opisem w [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Obszar roboczy ER.](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>Importowanie rozwiązań ER

Przykładowe konfiguracje ER są używane w przykładzie tej procedury. Do bieżącego wystąpienia aplikacji Dynamics 365 Finance należy zaimportować konfiguracje ER, które zawierają szablony dokumentów biznesowych, które można edytować za pomocą funkcji zarządzania dokumentami biznesowymi. Aby wykonać tę procedurę, należy pobrać i następnie lokalnie zapisać poniższe pliki.

**Przykładowe rozwiązanie fakturowania dla odbiorcy ER**

| Plik                                      | Zawartość |
|-------------------------------------------|---------|
| Model fakturowania odbiorcy.wersja.2.xml    | [Konfiguracja modelu danych ER](https://download.microsoft.com/download/b/f/a/bfa5cb52-e6e2-42bc-a4c0-77014a4c54e6/Customerinvoicingmodel.version.2.xml) |
| Raport FTI odbiorcy (GER).wersja.2.3.xml | [Konfiguracja darmowego formularza ER faktury niezależnej](https://download.microsoft.com/download/3/c/2/3c2e58f2-6e56-43d9-85ea-4c97252a108d/CustomerFTIreportGER.version.2.3.xml) |

**Rozwiązanie do sprawdzania płatności przykładowego ER**

| Plik                                     | Zawartość |
|------------------------------------------|---------|
| Model czeków.wersja.10.xml         | [Konfiguracja modelu danych ER](https://download.microsoft.com/download/3/7/6/376cb0f6-181a-4895-a432-390ffca64162/Modelforcheques.version.10.xml) |
| Formularz drukowania czeków.wersja.10.9.xml | [Konfiguracja formatu ER czeku płatności](https://download.microsoft.com/download/6/d/6/6d61bfff-3d89-4377-9e34-2e3ee6d6df91/Chequesprintingformat.version.10.9.xml) |

**Przykładowe rozwiązanie ER w handlu zagranicznym**

| Plik                             | Zawartość |
|----------------------------------|---------|
| Model Intrastat.wersja.1.xml    | [Konfiguracja modelu danych ER](https://download.microsoft.com/download/2/0/0/200d6ed1-eff8-48ec-ab75-175a4acf9714/Intrastatmodel.version.1.xml) |
| Raport Intrastat.version.1.9.xml | [Konfiguracja formatu ER raportu kontroli Intrastat](https://download.microsoft.com/download/7/a/2/7a2a27c3-a8a5-42a1-9d04-f0a8e1ec1707/Intrastatreport.version.1.9.xml) |

Aby zaimportować każdy plik, należy wykonać poniższą procedurę Dokonaj importu konfiguracji *modelu danych* ER dla każdego rozwiązania ER w tabelach powyżej zanim zimportujesz odpowiadającą konfigurację *formatu* ER.

1. Otwórz stronę **Administracja organizacji** \> **Raportowanie elektroniczne** \> **Konfiguracje**.
2. Wybierz **Import/eksport** u góry strony.
3. Wybierz **Załaduj z pliku XML**.
4. Wybierz przycisk **Przeglądaj**, aby załadować wymagany plik XML.
5. Wybierz przycisk **OK**, aby potwierdzić import konfiguracji.

![Strona konfiguracji ER z potwierdzeniem importu konfiguracji.](./media/BDM-Overview-ERSolutions.png)

Alternatywnie można zaimportować oficjalnie opublikowane konfiguracje formatów w formacie ER z Microsoft Dynamics Lifecycle Service (usługi LCS). Na przykład aby wykonać tę procedurę, można zaimportować najnowszą wersję konfiguracji formatu modułu **Darmowy tekst faktury (Excel)**. Odpowiednie konfiguracje mapowań modelu danych i modelu ER zostaną zaimportowane automatycznie.

![Strona zawartości biblioteki składników współużytkowanych usługi LCS.](./media/BDM-Overview-SharedAssetLibrary.png)

Aby uzyskać więcej informacji o importowaniu konfiguracji ER, zapoznaj się z [Zarządzanie cyklem życia konfiguracji Raportowania elektronicznego](general-electronic-reporting-manage-configuration-lifecycle.md).

## <a name="enable-business-document-management"></a>Włącz zarządzanie dokumentem biznesowym

Aby rozpocząć zarządzanie dokumentem biznesowym, należy otworzyć obszar roboczy **Zarządzanie funkcjami** i włączyć funkcję **Zarządzanie dokumentem biznesowym**.

Aby włączyć funkcję zarządzania dokumentem biznesowym dla wszystkich firm, należy wykonać poniższą procedurę.

1. Otwórzz obszar roboczy **Zarządzanie funkcjami**.
2. Na karcie **Nowe** wybierz funkcję **Zarządzanie dokumentem biznesowym**.
3. Wybierz opcję **Włącz teraz**, aby włączyć wybraną funkcję.
4. Odśwież stronę, aby uzyskać dostęp do nowej funkcji.

> [!NOTE]
> Aby uzyskać więcej informacji o korzystaniu z interfejsu użytkownika dla nowego dokumentu w zarządzaniu dokumentami biznesowymi, należy zapoznać się z tematem [Nowy interfejs użytkownika dokumentu w module Zarządzanie dokumentami biznesowymi](er-business-document-management-new-template-ui.md).

![Obszar roboczy zarządzanie funkcjami.](./media/BDM-Overview-FMEnabling.png)

Aby uzyskać więcej informacji o aktywowaniu nowych funkcji, zapoznaj się z [Zarządzanie funkcjami — omówienie](../../fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-parameters"></a>Konfigurowanie parametrów

Informacje zawarte w poniższych sekcjach służą do konfigurowania podstawowych parametrów zarządzania dokumentem biznesowym.

### <a name="prerequisites-for-parameter-setup"></a>Wymagania wstępne dotyczące ustawień parametrów

Aby można było skonfigurować zarządzanie dokumentami biznesowymi, należy skonfigurować wymagany typ dokumentu w strukturze zarządzania dokumentami. Ten typ dokumentu służy do określania tymczasowego przechowywania dokumentów w formatach pakietu Office (programy Excel i Word), które są używane jako szablony raportów ER. Tymczasowy szablon magazynu można edytować przy użyciu aplikacji klasycznych pakietu Office.

Dla tego typu dokumentu muszą być wybrane następujące wartości atrybutów:

| Nazwa atrybutu | Wartość atrybutu |
|----------------|-----------------|
| Klasa          | Dołącz plik     |
| Grupa          | Plik            |
| Lokalizacja       | SharePoint      |

Aby uzyskać informacje dotyczące konfigurowania wymaganych parametrów zarządzania dokumentami i typów dokumentów, należy zapoznać się z [Konfigurowanie zarządzania dokumentami](../../fin-ops/organization-administration/configure-document-management.md).

![Ustaw tyo dokumentu Zarządzania dokumentami.](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a><a name="SetupBdmParameters"></a>Konfigurowanie parametrów

Do konfigurowania parametrów podstawowych zarządzania dokumentami biznesowymi służy strona parametry **Parametry dokumentu biznesowego**. Tylko określeni użytkownicy mają dostęp do strony. W tym:

- Użytkownicy przypisani do roli **Administratora systemu**.
- Użytkownicy przypisani do dowolnej roli, która jest skonfigurowana do pełnienia obowiązków, **Obsługa parametrów zarządzania dokumentami biznesowymi** (nazwa drzewa obiektów aplikacji (AOT) **ERBDMaintainParameters**).

Aby skonfigurować podstawowe parametry dla wszystkich firm, należy wykonać poniższą procedurę

1. Zaloguj się jako użytkownik z dostępem do strony **Parametry dokumentu biznesowego**.
2. Przejdź do **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zarządzanie dokumentem biznesowym** \> **Parametry dokumentu biznesowego**.
3. Na stronie **Parametry dokumentu biznesowego** na karcie **Załączniki** w polu **SharePoint typu dokumentu** określ typ dokumentu, który ma być używany do tymczasowego przechowywania szablonów w formatach pakietu Office, podczas gdy są edytowane przy użyciu aplikacji klasycznych pakietu Office. 

> [!NOTE]
> Dla tego parametru są dostępne tylko typy dokumentów skonfigurowane przy użyciu lokalizacji SharePoint.

![Konfiguracja parametrów zarządzania dokumentami biznesowymi.](./media/BDM-Overview-BDMSetting.png)

Wybrany typ dokumentu jest specyficzny dla firmy i będzie używany, gdy użytkownik pracuje z Zarządzaniem dokumentami biznesowymi w firmie, dla której jest konfigurowany wybrany typ dokumentu. Gdy użytkownik pracuje z Zarządzaniem dokumentami biznesowymi w innej firmie, ten sam wybrany typ dokumentu brdzie używany jeśli inny typ nie został skonfigurowany dla tej firmy. Jeśli typ dokumentu został skonfigurowany, będzie używany zamiast wybranego w polu **SharePoint typu dokumentu**.

> [!NOTE]
> Parametr **Typ dokumentu SharePoint** definiuje folder SharePoint jako magazyn tymczasowy dla szablonów, które można edytować za pomocą Microsoft Excel lub programu Word. Ten parametr należy skonfigurować, jeśli te aplikacje pakietu Office mają być używane do edytowania szablonów. Aby uzyskać więcej informacji, zajrzyj do [edytowania szablonu w aplikacji pakietu Office](#EditInOfficeDesktopApp). Ten parametr można pozostawić pusty, jeśli planujesz zmodyfikować szablon, korzystając tylko z funkcji w systemie Microsoft 365. Aby uzyskać więcej informacji, zobacz temat [Edytowanie szablonów użytkownika w Microsoft 365](#EditInOffice365).

## <a name="configure-access-permissions"></a>Skonfiguruj uprawnienia dostępu do pól

Domyślnie, gdy dostęp do uprawnień Zarządzania dokumentami biznesowymi nie jest włączony, każdy użytkownik mający dostęp do obszaru roboczego Zarządzania dokumentami biznesowymi będzie widział wszystkie szablony rozwiązań ER, które są dostępne. W obszarze roboczym Zarządzania dokumentami biznesowymi zostaną wyświetlone tylko te szablony, które znajdują się w konfiguracjach formatów ER i są oznaczone tagiem **Typ dokumentu biznesowego**.

![Strona konfiguracji ER z tagiem typu dokumentu biznesowego.](./media/BDM-Overview-ERFormatTags.png)

Lista szablonów dostępnych w obszarze roboczym zarządzania dokumentami biznesowymi może być ograniczona przez skonfigurowanie uprawnień dostępu. Może to być ważne w przypadku użycia różnych szablonów do tworzenia dokumentów biznesowych dla różnych domen biznesowych (obszarów funkcjonalnych) oraz umożliwiania określonym użytkownikom dostępu do różnych szablonów do edycji w obszarze roboczym zarządzania dokumentami biznesowymi.

Uprawnienia dostępu do zarządzania dokumentami biznesowymi można ustawiać w **Konfiguratorze uprawnień dostępu**. Tylko następujący użytkownicy mają dostęp do strony:

- Użytkownicy przypisani do roli **Administratora systemu**.
- Użytkownicy przypisani do każdej innej roli skonfigurowanej do pełnienia obowiązków **Skonfigurowania uprawnienia dostępu do szablonów dokumentów biznesowych do edycji** (AOT o nazwie **ERBDTemplatesSecurity**).

Aby włączyć funkcję dostępu do zarządzania dokumentem biznesowym dla wszystkich firm, należy wykonać poniższą procedurę.

1. Zaloguj się jako użytkownik z dostępem do strony **Konfigurator uprawnień dostępu**.
2. Przejdź do **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zarządzanie dokumentem biznesowym** \> **Zarządzaj uprawnieniami dostępu**.

    Zwróć uwagę na powiadomienie informujące, że użycie uprawnień dostępu dla zarządzania dokumentem biznesowym nie jest obecnie włączone.

    ![Strona konfigurator uprawnień dostępu do zarządzania dokumentami biznesowymi.](./media/BDM-Overview-TemplatesAccess1.png)

    W przypadku tego ustawienia każdy użytkownik przypisany do dowolnej roli zabezpieczeń skonfigurowanej do obsługi **szablonów dokumentów biznesowych** (AOT nazwa **ERBDManageTemplates**) ma możliwość otwarcia zarządzania dokumentami biznesowymi w obszarze roboczym i może edytować dowolny dostępny szablon.

    Na poniższym rysunku pokazano, co jest dostępne w obszarze roboczym zarządzanie dokumentami biznesowymi dla użytkowników przypisanych do roli **Pracownik ds. rozrachunków z odbiorcami**. Korzystając z bieżącego ustawienia uprawnień dostępu, użytkownik może edytować szablony dokumentów biznesowych z różnych obszarów funkcjonalnych, w tym fakturowania, raportowania i płatności wykonawczych.

    ![Strona obszaru roboczego Zarządzanie dokumentami biznesowymi dla urzędnika z działu rozrachunków z odbiorcami.](./media/BDM-Overview-TemplatesForAlice1.png)

3. Na stronie **konfigurator uprawnień dostępu** wybierz **Ustawienia uprawnień dostępu**.
4. W oknie **ustawienia uprawnień dostępu do edytowania szablonów** włącz opcję **Zastosuj skonfigurowane uprawnienia dostępu**.
5. Wybierz **OK**, aby potwierdzić włączenie uprawnień dostępu zarządzanie dokumentami biznesowymi.

    ![Potwierdzanie uprawnień dostępu do zarządzania dokumentami biznesowymi.](./media/BDM-Overview-TemplatesAccess2.png)

6. Wybierz przycisk **Dodaj**, aby wprowadzić nową rolę biznesową, dla której mają być skonfigurowane uprawnienia dostępu do szablonów zarządzania dokumentami biznesowymi.
7. W oknie dialogowym **Role zabezpieczeń** wybierz rolę **pracownika rozrachunków z odbiorcami**, a następnie wybierz przycisk **OK**, aby potwierdzić wybór roli.
8. Na karcie **Uprawnienia dostępu wg znaczników konfiguracji** konfiguracji wybierz opcję **Nowy**.
9. W polu **typ znacznika** wybierz opcję **obszar funkcjonalny**, a następnie w polu **identyfikator** wybierz opcję **fakturowanie**.
10. Wybierz opcję **Zapisz**, aby zapisać skonfigurowane uprawnienia dostępu dla wybranej roli.

    Bieżące ustawienie oznacza każdego użytkownika przypisanego do roli **Pracownik ds. rozrachunków z odbiorcami** i wykonującego obowiązki, **Zarządzaj szablonami dokumentów biznesowych** (AOT o nazwie **ERBDManageTemplates**), format ER szablonów konfiguracji, które mają wartość **fakturowania** dla znacznika **obszaru funkcjonalnego**, będą dostępne do edycji w obszarze roboczym zarządzanie dokumentami biznesowymi.

11. Przełącz **pokrewne okienko informacyjne** od prawej strony bieżącej strony. W okienku **informacji pokrewnych** są wyświetlane informacje o sposobie stosowania skonfigurowanych uprawnień dostępu, w tym o tym, jakie szablony konfiguracji ról będą dostępne dla użytkowników przypisanych do roli **Pracownik ds. rozrachunków z odbiorcami**.

    ![Okienko informacji pokrewnych na stronie konfiguratora uprawnień dostępu.](./media/BDM-Overview-TemplatesAccess3.png)

12. Na karcie **Uprawnienia dostępu wg znaczników konfiguracji** konfiguracji wybierz opcję **Dodaj**.
13. W oknie dialogowym **wybierz konfigurację** zaznacz opcję Konfiguracja formatu ER **Raport Intrastat**.
14. Wybierz **OK**, aby potwierdzić wprowadzanie wybranych konfiguracji, a następnie wybierz **Zapisz**, aby zapisać skonfigurowane uprawnienia dostępu dla wybranej roli.

Bieżące ustawienie oznacza każdego użytkownika przypisanego do roli **Pracownik ds. rozrachunków z odbiorcami** i wykonującego obowiązki, **Zarządzaj szablonami dokumentów biznesowych** (AOT o nazwie **ERBDManageTemplates**), następujące szablony konfiguracji, które mają wartość fakturowania dla znacznika obszaru funkcjonalnego, będą dostępne do edycji w obszarze roboczym zarządzanie dokumentami biznesowymi:

- Szablony mające wartość, czyli **fakturowanie** dla znacznika **obszaru funkcjonalnego**.
- Szablony z konfiguracji formatów ER, które są wymienione na karcie **Uprawnienia dostępu wg konfiguracji** (szablony z konfiguracji formatu **raportu Intrastat** w domenie **raportowania ustawowego** w tym przykładzie).

![Skrócone karty uprawnień dostępu na stronie konfiguratora uprawnień dostępu.](./media/BDM-Overview-TemplatesAccess4.png)

Na poniższym rysunku pokazano, co jest dostępne w obszarze roboczym zarządzanie dokumentami biznesowymi dla użytkowników przypisanych do roli **Pracownik ds. rozrachunków z odbiorcami**. Przy użyciu bieżącego ustawienia uprawnień dostępu zarządzanie dokumentami biznesowymi użytkownik może edytować szablony dokumentów biznesowych za pomocą domeny **fakturowania** oraz konfiguracji formatu w **raportach Intrastat**. Szablony z domeny **płatności** są niedostępne dla roli **Pracownik ds. rozrachunków z odbiorcami**.

![Edytowanie szablonów dokumentów biznesowych na stronie obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> Reguły **Uprawnienia dostępu wg konfiguracji** są przechowywane przy użyciu unikatowego identyfikatora konfiguracji formatu ER. Oznacza to, że te reguły nie zostaną usunięte po usunięciu konfiguracji ER odwołującej się do tych reguł. Po zaimportowaniu usuniętych konfiguracji z powrotem do wystąpienia te reguły będą odnosiły się do nich na nowo. Nie ma potrzeby ponownego konfigurowania reguł po ponownym zaimportowaniu usuniętych konfiguracji.

## <a name="use-business-document-management-to-edit-templates"></a>Edytowanie szablonów przy użyciu funkcji zarządzania dokumentami biznesowymi

Użytkownicy biznesowi mogą uzyskiwać dostęp do szablonów dokumentów biznesowych do edycji w obszarze roboczym zarządzanie dokumentami biznesowymi. Tylko następujący użytkownicy mogą uzyskać dostęp do obszaru roboczego zarządzanie dokumentami biznesowymi:

- Użytkownicy przypisani do roli **Administratora systemu**.
- Użytkownicy przypisani do dowolnej roli, która jest skonfigurowana do pełnienia obowiązków, **Zarządzaj szablonami dokumentów biznesowych** (nazwa drzewa obiektów aplikacji (AOT) **ERBDMaintainParameters**).

Aby edytować szablony faktur niezależnych w obszarze roboczym zarządzanie dokumentami biznesowymi, należy wykonać poniższą procedurę. Przed wykonaniem tej procedury należy wykonać wszystkie opisane powyżej procedury przedstawione w tym artykule.

1. Zaloguj się jako użytkownik z dostępem do strony obszaru roboczego zarządzania dokumentami biznesowymi.
2. Otwórz obszaru roboczy zarządzania dokumentami biznesowymi.

Jeśli jest wyłączona funkcja **Wyglądający jak Office interfejs użytkownika na potrzeby zarządzania dokumentami** w obszarze roboczym **Zarządzanie funkcjami**, główna siatka w obszarze roboczyme **Zarządzanie dokumentami biznesowymi** wyświetla następujące szablony:

- Szablony, których właścicielem jest dostawca konfiguracji ER, (czyli dostawca aktualnie oznaczony jako aktywny w obszarze roboczym **Raportowanie elektroniczne**). Po wybraniu jednego z tych szablonów można wybrać opcję **Edytuj szablon**, aby rozpocząć lub kontynuować edycję szablonu.
- Szablony, które są własnością innych dostawców konfiguracji ER. Po wybraniu jednego z tych szablonów można wybrać **Nowy dokument** w celu utworzenia kopii, która jest własnością dostawcy konfiguracji ER, a następnie rozpocząć edycję kopii.

![Listy szablonów na stronie obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM-Overview-EditingTemplate1.png)

Zawartość wybranego szablonu jest przedstawiana na karcie **szablony**. Wybierz kartę **szczegóły**, aby przejrzeć szczegóły wybranego szablonu, a także szczegóły konfiguracji formatu ER, w którym znajduje się ten szablon. Zauważ, że wszystkie szablony mają stan **opublikowane** i nie zawierają szczegółów w kolumnie **korekta**. Oznacza to, że te szablony nie są obecnie edytowane.

Jeśli jest włączona funkcja **Wyglądający jak Office interfejs użytkownika na potrzeby zarządzania dokumentami** w obsarze roboczym **Zarządzanie funkcjami** główna siatka w obszarze roboczym **Zarządzanie dokumentami biznesowymi** zawiera szablony będące własnością dostawcy konfiguracji ER (czyli dostawcę aktualnie oznaczonego jako aktywny w obszarze roboczym **Raportowanie elektroniczne**). Po wybraniu jednego z tych szablonów można wybrać opcję **Edytuj szablon**, aby rozpocząć lub kontynuować edycję szablonu.

Aby pracować z szablonami należącymi do innych dostawców konfiguracji ER, należy wybrać opcję **Nowy dokument**, aby utworzyć kopię szablonu będącego własnością dostawcy ER. Wtedy można zacząć edytować kopię. Więcej informaci można przeczytać w [Nowy interfejs użytkownika dokumentu w zarządzaniu dokumentami biznesowymi](er-business-document-management-new-template-ui.md).

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>Inicjuj Edytowanie szablonów należących do Twojego dostawcy konfiguracji.

1. W obszarze roboczym zarządzanie dokumentami biznesowymi wybierz szablon **drukowania czeków z listy**.
2. Kliknij kartę **Szczegóły**.

![Strona obszaru roboczego zarządzania dokumentami biznesowymi, karta Szczegóły.](./media/BDM-Overview-EditingTemplate2.png)

Opcja **Edytuj szablon** jest dostępna dla wybranego szablonu. Ta opcja jest zawsze dostępna dla szablonu w konfiguracji formatu modułu, który jest własnością aktywnego dostawcy konfiguracji usługi ER (**Litware, Inc.** w tym przykładzie). Po wybraniu opcji **Edytuj szablon**, istniejący szablon z wersji roboczej w źródłowej konfiguracji formatu w module ER będzie dostępny do edycji.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Inicjuj Edytowanie szablonów należących do innych dostawców.

1. W obszarze roboczym zarządzanie dokumentami biznesowymi wybierz dokument, który ma być używany jako szablon.

    ![Wybierz dokument na stronie obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM-Overview-EditingTemplate3.png)

2. Wybierz opcję **Nowy dokument**, a w polu tytuł **Tytuł**, w razie potrzeby, zmień tytuł szablonu edytowalnego. Tekst będzie używany do napełniania nazwy tworzonej automatycznie konfiguracji formatu ER. Należy zauważyć, że wersja robocza tej konfiguracji (**Raport o fakturach niezależnych dla odbiorców (GER)**) będzie zawierać edytowany szablon, zostanie automatycznie oznaczona do uruchomienia tego formatu ER dla bieżącego użytkownika. W tym samym czasie, niezmodyfikowany oryginalny szablon z podstawowej konfiguracji formatu źródłowego będzie używany do uruchamiania tego formatu ER dla innego użytkownika.
3. W polu **nazwa** Zmień nazwę pierwszej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.
4. W polu **Komentarz** zmień komentarz dla automatycznie wygenerowanej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.
5. Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.

![Potwierdź rozpoczęcie procesu edycji w celu utworzenia nowego szablonu.](./media/BDM-Overview-EditingTemplate4.png)

Jeśli nie ma żadnego dostawcy, zostanie zaproponowane utworzenie. Jeśli nie ma aktywnego dostawcy, zostanie zaproponowane wybranie go do aktywacji.

Aby utworzyć dostawcę, zmień nazwę dostawcy w polu **Nazwa**, zaktualizuj adres internetowy nowego dostawcy w polu **Adresu internetowego** i wybierz przycisk **OK**, aby potwierdzić.

   ![Utwórz nowego dostawcę w BDM.](./media/bdm_create_provider.png)

Aby uaktywnić istniejącego dostawcę, wybierz nazwę dostawcy w polu **Dostawca konfiguracji** i wybierz przycisk **OK**, aby ustawić dostawcę jako aktywnego.

   ![Aktywuj dostawcę w BDM.](./media/bdm_choose_provider.png)

> [!NOTE]
> Każdy szablon BDM odnosi się do dostawcy jako autora konfiguracji. Z tego względu dla szablonu jest wymagany aktywny dostawca.


Opcja **Nowy dokument** jest zawsze dostępna dla szablonu w konfiguracji formatu ER, który jest własnością tego i innego dostawcy (Microsoft w tym przykładzie), a który nie ma żadnych poprawek. Edytowany szablon zostanie następnie zapisany w nowej konfiguracji formatu, która jest generowana automatycznie.



### <a name="start-editing-a-template"></a>Rozpocznij edycję szablonu

1. Z wybranego szablonu wybierz opcję **Edytuj dokument**.
2. W polu **nazwa** Zmień nazwę pierwszej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.
3. W polu **Komentarz** zmień uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.

    ![Edytowanie szablonu na stronie obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM-Overview-EditingTemplate5.png)

4. Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.

Otworzy się strona **Edytor szablonów BDM**. Wybrany szablon będzie dostępny do edycji w trybie online za pomocą Microsoft 365.

![Strona edytora szablonów zarządzania dokumentami biznesowymi.](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-microsoft-365"></a><a name="EditInOffice365"></a>Edytuj szablon w Microsoft 365

Szablony można modyfikować za pomocą Microsoft 365. Na przykład w przypadku witryny Office Online w nagłówku szablonu należy zmienić czcionkę z pola **zwykły** na **pogrubiony**. Te zmiany są automatycznie przechowywane jako szablon edytowalny, który jest przechowywany w magazynie podstawowego szablonu (domyślnie magazyn obiektów BLOB systemu Azure). Jest to skonfigurowane dla struktury ER systemu.

![Zmiana czcionki na pogrubioną w nagłówku szablonu na stronie edytora szablonu zarządzania dokumentami biznesowymi.](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a><a name="EditInOfficeDesktopApp"></a>Edytowanie szablonu w aplikacji pulpitu pakietu Office

> [!NOTE]
> Ta funkcja jest dostępna tylko w przypadku, gdy parametr **Typ dokumentu SharePoint** jest poprawnie skonfigurowany. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie narzędzia integracji](#SetupBdmParameters).

1. Wybierz opcję **Otwórz w aplikacji klasycznej**, aby zmodyfikować szablon za pomocą funkcji aplikacji pulpitu pakietu Office (w tym przykładzie programu Excel). Szablon edytowalny jest kopiowany z magazynu trwałego do tymczasowego magazynu skonfigurowanego w parametrach zarządzania dokumentami biznesowymi SharePoint jako folder.
2. Potwierdź, że chcesz otworzyć szablon z tymczasowego przechowywania plików w aplikacji klasycznej programu Office Excel.

    ![Szablon otwarty w aplikacji klasycznej Excel.](./media/BDM-Overview-EditingLayout3.png)

3. Modyfikowanie szablonu. Na przykład zmień czcionkę pól podpowiedzi w nagłówku szablonu, zmieniając kolor z **Czarny** na **Niebieski**.

    ![Modyfikowanie koloru czcionki w nagłówku szablonu za pomocą aplikacji klasycznej Excel.](./media/BDM-Overview-EditingLayout4.png)

4. Wybierz **Zapisz** w aplikacji klasycznej programu Excel, aby zapisać zmiany w szablonie w magazynie tymczasowym.

    ![Zapisywanie zmian na stronie edytora szablonów zarządzania dokumentami biznesowymi za pomocą aplikacji klasycznej Excel.](./media/BDM-Overview-EditingLayout5.png)

5. Zamknij aplikację pulpitu programu Excel.
6. Wybierz opcję **Synchronizuj przechowywaną kopię**, aby zsynchronizować tymczasowy magazyn szablonu z trwałym magazynem szablonów.

> [!NOTE]
> Kopia szablonu edytowalnego w magazynie plików tymczasowych jest przechowywana tylko w bieżącej sesji edytowania szablonu. Po zakończeniu tej sesji przez zamknięcie strony **edytora szablonów BDM** ta kopia zostanie usunięta. Jeśli szablon został dostosowany do tymczasowego magazynu plików i nie wybrano opcji **Synchronizuj kopięprzechowywaną**, podczas próby zamknięcia strony **edytora szablonów BDM** zostanie wyświetlony komunikat z pytaniem, czy mają być przechowywane wprowadzone zmiany. Wybierz **Tak**, jeśli chcesz zapisać zmiany w szablonie w trwałej lokalizacji pliku.

### <a name="validate-a-template"></a>Weryfikuj szablon

1. Na stronie **Edytor szablonów BDM** wybierz opcję **Sprawdź, czy występują problemy**, aby sprawdzić zmodyfikowany szablon zgodnie z podstawową konfiguracją formatu ER. Postępuj zgodnie z zaleceniami (jeśli istnieją), aby wyrównać szablon zgodnie ze strukturą formatu w podstawowej konfiguracji formatu ER.
2. Wybierz opcję **Pokaż format**, aby wyświetlić bieżącą strukturę formatu z podstawowej konfiguracji formatu w formacie encji, która musi być wyrównana do szablonu edytowalnego. 
3. Aby zamknąć okienko, wybierz opcję **Ukryj format**.

    ![Strona edytora szablonów BDM BDM.](./media/BDM-Overview-EditingTemplate6.png)

4. Zamknij stronę **Edytor szablonów BDM**.

Zaktualizowany szablon jest wyświetlany na karcie **szablon**. Zauważ, że stan edytowanego szablonu to teraz **wersja robocza**, a bieżąca wersja nie jest już pusta. Oznacza to, że proces edycji tego szablonu został rozpoczęty.

![Wyświetlanie zaktualizowanego szablonu na stronie obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>Testowanie zmodyfikowanego szablonu 

1. W rozliczeniu Zmień firmę na **USMF**.
2. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
3. Wybierz fakturę **FTI-00000002**, a następnie wybierz opcję **Zarządzanie drukowaniem**.
4. Wybierz **Moduł - Rozrachunki z odbiorcami** \> **Dokumenty** \> **Faktura niezależna** \> **Dokument oryginalny**, aby określić zakres faktur do przetwarzania.
5. W polu **format raportu** wybierz format **Raport o fakturach niezależnych dla odbiorców (GER)** formatu ER dla określonego poziomu dokumentu.

    ![Strona ustawień zarządzania drukowaniem.](./media/BDM-Overview-TestRun1.png)

6. Naciśnij klawisz **Escape**, aby zamknąć bieżącą stronę
7. Wybierz opcję **Drukuj**, a następnie wybierz opcję **Wybrane**.
8. Pobierz dokument i otwórz go za pomocą aplikacji pulpitu programu Excel.

![Strona faktur niezależnych.](./media/BDM-Overview-TestRun2.png)

Zmodyfikowany szablon jest używany do generowania raportu faktury niezależnej dla wybranego towaru. Aby przeanalizować sposób, w jaki ten raport ma wpływ na zmiany wprowadzone w szablonie, można uruchomić ten raport bezpośrednio po zmodyfikowaniu szablonu w innej sesji aplikacji.

### <a name="create-an-alternative-template-revision"></a>Tworzenie alternatywnego szablonu korekty

1. Umożliwia otwarcie strony **edytora szablonów BDM** i wybranie szablonu **kopii FTI raportu odbiorcy (GER)**.
2. Na karcie **poprawki** wybierz opcję **nowa**.
3. W razie potrzeby w polu **nazwa** zmień nazwę drugiej poprawki i oprzyj ją na aktualnie aktywnej pierwszej korekcie.
4. Jeśli istnieje potrzeba, w polu **Komentarz** zmień uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.

    ![Tworzenie wersji szablonu na stronie obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM-Overview-AddRevision.png)

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

![Odrzucanie zmian szablonu na stronie obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM-Overview-RevokeChanges.png)

1. Na stronie **Edytor szablonów BDM** wybierz kartę **szablon**.
2. Wybierz **Cofnij**.
3. Jeśli wybierzesz **OK**, aby anulować zmiany wprowadzone dla szablonu, zmodyfikowany szablon zostanie zastąpiony oryginalnym szablonem, a wszystkie zmiany zostaną usunięte. Po cofnięciu zmian w szablonie będzie można usunąć szablon. Wybierz **Anuluj**, aby poznać inne opcje.

### <a name="publish-a-modified-template"></a>Publikacja szablonu zmodyfikowanego

1. Na stronie **Edytor szablonów BDM** wybierz kartę **szablon** i wybierz **Opublikuj**.
2. Jeśli zostanie wybrana **OK** w celu potwierdzenia publikowania, wersja robocza raportu **kopii FTI raportu odbiorcy (GER)** formatu ER, która zawiera zmodyfikowany szablon, zostanie oznaczona jako zakończona. Zmodyfikowany szablon staje się dostępny dla innych użytkowników. Wersje ukończone tego formatu ER zachowają tylko ostatnią aktywną korektę szablonu. Inne zmiany zostaną usunięte. Wybierz **Anuluj**, aby poznać inne opcje.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="i-selected-edit-document-but-instead-of-going-to-the-bdm-template-editor-page-in-finance-i-was-sent-to-the-microsoft-365-webpage"></a>Po wybraniu pozycji Edytuj dokument zamiast strony edytora szablonów BDM w aplikacji Finanse nastąpiło przekierowanie do strony internetowej Microsoft 365.

Jest to znany problem z przekierowaniem do platformy Microsoft 365. Występuje on po pierwszym zalogowaniu do Microsoft 365. Aby obejść ten problem, wybierz opcję **Wstecz** w przeglądarce, aby powrócić do poprzedniej strony.

### <a name="i-understand-how-to-edit-a-template-by-using-microsoft-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-and-adjust-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-use-the-office-desktop-application-in-the-same-way"></a>Wiem, jak edytować szablon, używając Microsoft 365 w pierwszej sesji aplikacji i jak używać szablonu w drugiej sesji aplikacji podczas dopasowywania szablonu, aby zobaczyć, jak zmiany wpływają na wygenerowany dokument biznesowy. Czy mogę używać aplikacji klasycznej Office w taki sam sposób?

Tak, można. W pierwszej sesji aplikacji wybierz opcję **Otwórz w aplikacji klasycznej**. Szablon będzie przechowywany w tymczasowym magazynie plików i otwarty w aplikacji pulpitu Office. Następnie wykonaj następujące kroki, aby przejrzeć zmiany w szablonie w wygenerowanym dokumencie biznesowym:

1. Wprowadź zmiany w szablonie przy użyciu aplikacji pulpitu pakietu Office.
2. Wybierz opcję **Zapisz** w aplikacji pulpitu Office.
3. Na stronie **Edytor szablonów BDM** w pierwszej sesji aplikacji wybierz opcję **Synchronizuj kopię przechowywaną**.
4. Wykonaj ten szablon formatu ER aplikacji w drugiej sesji aplikacji.

### <a name="when-i-select-open-in-desktop-app-i-receive-the-following-error-message-value-cannot-be-null-parameter-name-externalid-how-do-i-work-around-this-issue"></a>Gdy w aplikacji klasycznej wybiorę opcję Otwórz, pojawia się następujący komunikat o błędzie: „Wartość nie może być wartością null. Nazwa parametru: externalId”. Jak mogę obejść ten problem?

Najprawdopodobniej zalogowano się do bieżącego wystąpienia aplikacji w domenie Azure AD, które różnią się od domeny Azure AD, która została użyta do wdrożenia tego wystąpienia. Ponieważ usługa SharePoint, która jest używana do przechowywania szablonów do udostępniania ich do edycji za pomocą aplikacji klasycznych pakietu Office, należy do tej samej domeny, nie ma żadnych uprawnień dostępu do usługi SharePoint. Aby rozwiązać ten problem, zaloguj się do bieżącego wystąpienia, używając poświadczeń użytkownika z poprawną domeną Azure AD.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (RE)](general-electronic-reporting.md)

[ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML (listopad 2016)](tasks/er-design-reports-openxml-2016-11.md)

[Projektowanie konfiguracji raportowania elektronicznego w celu generowania raportów w formacie programu Word](tasks/er-design-configuration-word-2016-11.md)

[Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md)

[Konfigurowanie raportowania elektronicznego (ER) do ściągania danych do usługi Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)

## <a name="list-of-er-configurations-that-have-been-released-in-finance-to-support-configurable-business-documents"></a><a name="list-of-configurations-cbd"></a>Lista konfiguracji ER zwolnionych w aplikacji Finance na potrzeby obsługi konfigurowalnych dokumentów biznesowych

[Lista](general-electronic-reporting.md#list-of-configurations) konfiguracji ER elektronicznego dla aplikacji Finance jest aktualizowana w sposób ciągły. Otwórz [repozytorium globalne](er-download-configurations-global-repo.md), aby przejrzeć listę aktualnie obsługiwanych konfiguracji ER. Repozytorium globalne można [filtrować](../../../finance/localizations/enhanced-filtering-global-repo.md) w celu przejrzenia listy konfiguracji ER używanych do obsługi konfigurowalnych dokumentów biznesowych.

![Filtrowanie zawartości repozytorium globalnego na stronie Repozytorium konfiguracji.](./media/bdm-overview-filterglobalrepo.gif)

W poniższej tabeli pokazano listę konfiguracji ER, które obsługują konfigurowalne dokumenty biznesowe, wydane w aplikacji Finance do grudnia 2020 r.

| Konfiguracja modelu danych    | Konfiguracje formatu                           |
|-----------------------------|-------------------------------------------------|
| Model listu przewozowego        | List przewozowy (Excel)                          |
|                             | List przewozowy (Word)                           |
| Model certyfikatu pochodzenia | Certyfikat pochodzenia (Excel)                   |
|                             | Certyfikat pochodzenia (Word)                    |
| Model faktury               | Nota debetowa i kredytowa dla klienta (Excel)          |
|                             | Nota debetowa i kredytowa dla klienta (Word)           |
|                             | Faktura niezależna (Excel)                       |
|                             | Faktura niezależna (Excel) (BH)                  |
|                             | Faktura niezależna (FR) (Excel)                  |
|                             | Faktura niezależna (LT) (Excel)                  |
|                             | Faktura niezależna (LV) (Excel)                  |
|                             | Faktura niezależna (PL) (Excel)                  |
|                             | Faktura niezależna (CZ) (Excel)                  |
|                             | Faktura niezależna (EE) (Excel)                  |
|                             | Faktura niezależna (HU) (Excel)                  |
|                             | Faktura niezależna (TH) (Excel)                  |
|                             | Faktura niezależna (Word)                        |
|                             | Pozycje wiersza umowy dotyczącej projektu (Excel)             |
|                             | Pozycje wiersza umowy dotyczącej projektu (CZ) (Excel)        |
|                             | Pozycje wiersza umowy dotyczącej projektu (Excel) (BH)        |
|                             | Pozycje wiersza umowy dotyczącej projektu (HU) (Excel)        |
|                             | Pozycje wiersza umowy dotyczącej projektu (LT) (Excel)        |
|                             | Pozycje wiersza umowy dotyczącej projektu (PL) (Excel)        |
|                             | Pozycje wiersza umowy dotyczącej projektu (Word)              |
|                             | Wydanie zatrzymania klienta dla projektu (Excel)      |
|                             | Wydanie zatrzymania klienta dla projektu (CZ) (Excel) |
|                             | Wydanie zatrzymania klienta dla projektu (HU) (Excel) |
|                             | Wydanie zatrzymania klienta dla projektu (LT) (Excel) |
|                             | Wydanie zatrzymania klienta dla projektu (PL) (Excel) |
|                             | Wydanie zatrzymania klienta dla projektu (TH) (Excel) |
|                             | Wydanie zatrzymania klienta dla projektu (Word)       |
|                             | Faktura projektu (Excel)                         |
|                             | Faktura projektu (Word)                          |
|                             | Faktura projektu (AE) (Excel)                    |
|                             | Faktura projektu (CZ) (Excel)                    |
|                             | Faktura projektu (Excel) (BH)                    |
|                             | Faktura projektu (HU) (Excel)                    |
|                             | Faktura projektu (JP) (Excel)                    |
|                             | Faktura projektu (LT) (Excel)                    |
|                             | Faktura projektu (PL) (Excel)                    |
|                             | Faktura projektu (TH) (Excel)                    |
|                             | Pełna faktura projektu (MY) (Excel)               |
|                             | Prosta faktura projektu (MY) (Excel)             |
|                             | Faktura dotycząca zarządzania projektem (Excel)                  |
|                             | Faktura dotycząca zarządzania projektem (CZ) (Excel)             |
|                             | Faktura dotycząca zarządzania projektem (Excel) (BH)             |
|                             | Faktura dotycząca zarządzania projektem (HU) (Excel)             |
|                             | Faktura dotycząca zarządzania projektem (JP) (Excel)             |
|                             | Faktura dotycząca zarządzania projektem (LT) (Excel)             |
|                             | Faktura dotycząca zarządzania projektem (PL) (Excel)             |
|                             | Faktura dotycząca zarządzania projektem (Word)                   |
|                             | Faktura zaliczkowa zakupu (Excel)                |
|                             | Faktura zaliczkowa zakupu (Word)                 |
|                             | Faktura zaliczkowa sprzedaży (Excel)                   |
|                             | Faktura zaliczkowa sprzedaży (Word)                    |
|                             | Faktura zaliczkowa sprzedaży (PL) (Excel)              |
|                             | Faktura sprzedaży (Excel)                           |
|                             | Faktura sprzedaży (Excel) (BH)                      |
|                             | Faktura sprzedaży (Excel) (CZ)                      |
|                             | Faktura sprzedaży (Excel) (EE)                      |
|                             | Faktura sprzedaży (Excel) (FR)                      |
|                             | Faktura sprzedaży (Excel) (HU)                      |
|                             | Faktura sprzedaży (Excel) (IN)                      |
|                             | Faktura sprzedaży (Excel) (LT)                      |
|                             | Faktura sprzedaży (Excel) (LV)                      |
|                             | Faktura sprzedaży (Excel) (PL)                      |
|                             | Faktura sprzedaży (Excel) (TH)                      |
|                             | Faktura sprzedaży (Word)                            |
|                             | Faktura handlowa TMS (Excel)                  |
|                             | Faktura handlowa TMS (Word)                   |
|                             | Dokument faktury od dostawcy (Excel)                 |
|                             | Dokument faktury od dostawcy (CZ) (Excel)            |
|                             | Dokument faktury od dostawcy (HU) (Excel)            |
|                             | Dokument faktury od dostawcy (IN) (Excel)            |
|                             | Dokument faktury od dostawcy (LT) (Excel)            |
|                             | Dokument faktury od dostawcy (LV) (Excel)            |
|                             | Dokument faktury od dostawcy (MY) (Excel)            |
|                             | Dokument faktury od dostawcy (Word)                  |
| Model zamówienia                 | Potwierdzenie umowy (Excel)                  |
|                             | Potwierdzenie umowy (Word)                   |
|                             | Potwierdzenie umowy zakupu (Excel)         |
|                             | Potwierdzenie umowy zakupu (Word)          |
|                             | Zamówienie zakupu (Excel)                          |
|                             | Zamówienie zakupu (CZ) (Excel)                     |
|                             | Zapytanie dotyczące zamówienia zakupu (CZ) (Excel)             |
|                             | Zamówienie zakupu (HU) (Excel)                     |
|                             | Zapytanie dotyczące zamówienia zakupu (HU) (Excel)             |
|                             | Zamówienie zakupu (Word)                           |
|                             | Zapytanie dotyczące zamówienia zakupu (Excel)                  |
|                             | Zapytanie dotyczące zamówienia zakupu (Word)                   |
|                             | Potwierdzenie zamówienia sprzedaży (Excel)                |
|                             | Potwierdzenie zamówienia sprzedaży (CZ) (Excel)           |
|                             | Potwierdzenie zamówienia sprzedaży (HU) (Excel)           |
|                             | Potwierdzenie zamówienia sprzedaży (Word)                 |
| Model listy pobrania          | Zawartość kontenera (Excel)                      |
|                             | Zawartość kontenera (Word)                       |
|                             | Lista ładunków (Excel)                               |
|                             | Lista ładunków (Word)                                |
|                             | Lista pobrania (Excel)                            |
|                             | Lista pobrania (CZ) (Excel)                       |
|                             | Lista pobrania (Word)                             |
|                             | Lista pobrania dla produkcji (Excel)                    |
|                             | Lista pobrania dla produkcji (Word)                     |
|                             | Lista odbioru wysyłki dla ładunku (Excel)             |
|                             | Lista odbioru wysyłki dla ładunku (Word)              |
|                             | Lista odbioru wysyłki dla wysyłki (Excel)         |
|                             | Lista odbioru wysyłki dla wysyłki (Word)          |
|                             | Lista odbioru wysyłki dla grupy czynności (Excel)             |
|                             | Lista odbioru wysyłki dla grupy czynności (Word)              |
| Model płatności               | Zawiadomienie o płatności klienta (Excel)                 |
|                             | Zawiadomienie o płatności klienta (Word)                  |
|                             | Zawiadomienie o płatności dostawcy (Excel)                   |
|                             | Zawiadomienie o płatności dostawcy (Word)                    |
| Model oferty             | Oferta dotycząca projektu (Excel)                       |
|                             | Oferta dotycząca projektu (Word)                        |
|                             | Zapytanie ofertowe (Excel)                   |
|                             | Zapytanie ofertowe (akceptacja) (Excel)          |
|                             | Zapytanie ofertowe (akceptacja) (Word)           |
|                             | Zapytanie ofertowe (odrzucenie) (Excel)          |
|                             | Zapytanie ofertowe (odrzucenie) (Word)           |
|                             | Zapytanie ofertowe (zwrot) (Excel)          |
|                             | Zapytanie ofertowe (zwrot) (Word)           |
|                             | Zapytanie ofertowe (Word)                    |
|                             | Oferta sprzedaży (Excel)                         |
|                             | Oferta sprzedaży (CZ) (Excel)                    |
|                             | Oferta sprzedaży (HU) (Excel)                    |
|                             | Oferta sprzedaży (Word)                          |
|                             | Potwierdzenie oferty sprzedaży (Excel)            |
|                             | Potwierdzenie oferty sprzedaży (Word)             |
| Model uzgodnienia        | Wyciąg z konta klienta, zewnętrzny (Excel)             |
|                             | Wyciąg z konta klienta, zewnętrzny (CN) (Excel)        |
|                             | Wyciąg z konta klienta, zewnętrzny (Word)              |
|                             | Wyciąg z konta klienta, Francja (Excel)          |
| Model przypomnienia              | Ponaglenie (Excel)                  |
|                             | Ponaglenie (CN) (Excel)             |
|                             | Ponaglenie (Word)                   |
|                             | Nota odsetkowa klienta (Excel)                  |
|                             | Nota odsetkowa klienta (Word)                   |
| Model listu przewozowego               | Oferta przetargowa dotycząca ładunku (Excel)                             |
|                             | Oferta przetargowa dotycząca ładunku (Word)                              |
|                             | Dokument dostawy dla zamówienia zakupu (Excel)             |
|                             | Dokument dostawy dla zamówienia zakupu (CZ) (Excel)        |
|                             | Dokument dostawy dla zamówienia zakupu (Word)              |
|                             | Marszruta (Excel)                                   |
|                             | Marszruta (Word)                                    |
|                             | Dokument dostawy dla zamówienia sprzedaży (Excel)                |
|                             | Dokument dostawy dla zamówienia sprzedaży (CZ) (Excel)           |
|                             | Dokument dostawy dla zamówienia sprzedaży (LT) (Excel)           |
|                             | Dokument dostawy dla zamówienia sprzedaży (PL) (Excel)           |
|                             | Dokument dostawy dla zamówienia sprzedaży (Word)                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
