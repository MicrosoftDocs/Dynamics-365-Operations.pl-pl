---
title: Zaprojektowanie nowego rozwiązania ER w celu wydrukowania raportu niestandardowego
description: W tym temacie opisano sposób projektowania rozwiązania do tworzenia raportów elektronicznych (ER) w celu wydrukowania raportu niestandardowego.
author: NickSelin
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a3e0e4a8389fdd6580f66004d86ef4b1980dd9f
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891800"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a>Zaprojektowanie nowego rozwiązania ER w celu wydrukowania raportu niestandardowego

[!include[banner](../includes/banner.md)]

Poniższe kroki wyjaśniają, w jaki sposób użytkownik pełniący rolę administratora systemu, dewelopera raportowania elektronicznego lub konsultanta funkcjonalnego raportowania elektronicznego może konfigurować parametry struktury ER, projektować wymagane konfiguracje ER nowego rozwiązania ER, aby uzyskać dostęp do danych z określonej domeny biznesowej, i wygeneruj niestandardowy raport w formacie Microsoft Office. Kroki można wykonać na danych firmy **USMF**.

- [Konfigurowanie struktury ER](#ConfigureFramework)

    - [Konfigurowanie parametrów modułu ER](#ConfigureParameters)
    - [Aktywowanie dostawcy konfiguracji ER](#ActivateProvider)

        - [Przejrzenie listy dostawców konfiguracji ER](#ReviewProvidersList)
        - [Dodawanie nowego dostawcy formatu ER](#AddProvider)
        - [Aktywowanie dostawcy konfiguracji ER](#ActivateAddedProvider)

- [Projektowanie modelu danych specyficznego dla domeny](#DesignModel)

    - [Importowanie nowej konfiguracji modelu danych](#ImportDataModel)
    - [Tworzenie nowej konfiguracji modelu danych](#DesignDataModel)

        - [Nazywanie modelu danych](#NameDataModel)
        - [Dodaj pola modelu danych](#FieldsEntry)
        - [Umożliwia zakończenie projektu modelu danych](#CompleteDataModel)

- [Umożliwia zaprojektowanie mapowania modelu dla skonfigurowanego modelu danych](#DesignMapping)

    - [Importowanie nowej konfiguracji mapowania modelu](#ImportModelMapping)
    - [Stwórz nowy model konfiguracji mapowania](#CreateModelMapping)

        - [Projektowanie nowego składnika mapowania modelu](#DesignMappingComponent)
        - [Dodawanie źródeł danych w celu uzyskania dostępu do tabel aplikacji](#AddMmDataSource1)
        - [Dodawanie źródeł danych w celu uzyskania dostępu do wyliczenia aplikacji](#AddMmDataSource2)
        - [Dodawanie etykiet ER w celu wygenerowania raportu w określonym języku](#AddMmLabels)
        - [Dodaj źródło danych w celu przekształcenia wyników porównywania wartości wyliczenia z wartością tekstową](#AddMmDataSource3)
        - [Powiąż źródła danych z polami modelu danych](#AddMmBindings1)
        - [Umożliwia zakończenie projektu mapowania modelu](#CompleteModelMapping)

- [Projektowanie szablonu raportu niestandardowego](#DesignReportTemplate)
- [Projektowanie formatu](#DesignFormat)

    - [Import zaprojektowanej konfiguracji formatu](#FormatImport)
    - [Utwórz nową konfigurację formatu.](#FormatCreate)

        - [Zaimportuj szablon raportu](#ImportReportTemplate)
        - [Konfigurowanie formatu](#ConfigureFormat)
        - [Definiowanie powiązania danych dla tytułu raportu](#DefineFormatBindings)
        - [Przejrzyj źródło danych modelu](#ReviewModelDataSource)
        - [Powiązanie elementów formatu na pola źródła danych](#BindFormatElements)

    - [Uruchamianie zaprojektowanego formatu od ER](#RunFormatFromER)

- [Dostrajanie zaprojektowanego formatu](#TuneFormat)

    - [Modyfikowanie formatu w celu zmiany nazwy wygenerowanego dokumentu](#ModifyToChangeName)
    - [Umożliwia zmodyfikowanie formatu w celu zmiany kolejności pytań](#ModifyToOrder)
    - [Uruchamianie zmodyfikowanego formatu od ER](#RunFormatFromER2)
    - [Zakończ projektowanie formatu](#CompleteFormat)

- [Opracowywanie Artefacts aplikacji w celu wywołania zaprojektowanego raportu](#DevelopCustomCode)

    - [Zmień kod źródłowy](#ModifySourceCode)

        - [Dodawanie klasy kontraktu danych](#DataContractClass)
        - [Dodaj klasę konstruktora UI](#UIBuilderClass)
        - [Dodawanie klasy dostawcy danych](#DataProviderClass)
        - [Dodaj plik etykiet](#LabelsFile)
        - [Dodawanie klasy usługi raportowania](#ServiceClass)
        - [Dodawanie klasy kontrolera raportowania](#ControllerClass)
        - [Dodaj element menu](#MenuItem)
        - [Dodawanie elementu menu do menu](#Menu)
        - [Budowanie projektu Visual Studio](#BuildVSProject)

    - [Umożliwia uruchomienie formatu z aplikacji](#RunFormatFromApp)

- [Dostrajanie zaprojektowanego rozwiązania ER](#TuneSolution)

    - [Modyfikowanie mapowania modelu](#ModifyModelMapping)

        - [Dodaj źródła danych, aby uzyskać dostęp do obiektu kontraktu danych](#AddDataSource1)
        - [Dodaj źródło danych, aby uzyskać dostęp do rekordów mapowania formatu ER](#AddDataSource2)
        - [Dodaj źródło danych, aby uzyskać dostęp do rekordu odwzorowania formatu działającego formatu ER](#AddDataSource3)
        - [Umożliwia wprowadzenie nazwy uruchomionego formatu ER w modelu danych](#AddBinding)
        - [Umożliwia zakończenie projektu mapowania modelu](#CompleteModelMapping2)

    - [Modyfikowanie formatu](#ModifyFormat)

        - [Dodaj nowy element formatu](#AddFormatElement)
        - [Powiąż dodany element formatu](#BindAddedFormatElement)
        - [Zakończ projektowanie formatu](#CompleteFormat2)

    - [Umożliwia uruchomienie formatu z aplikacji](#RunFormatFromApp2)
    - [Uruchamianie formatu od ER](#RunFormatFromER3)
    - [Skonfiguruj miejsce docelowe formatu dla podglądu na ekranie](#ConfigureDestination)
    - [Umożliwia uruchomienie formatu z aplikacji w celu wyświetlenia podglądu go jako dokumentu PDF](#RunFormatFromApp3)

- [Dodatkowe zasoby](#References)

W tym przykładzie zostanie utworzone nowe rozwiązanie ER dla modułu [kwestionariusza](../../../human-resources/hr-learning-questionnaires.md). To nowe rozwiązanie ER umożliwia zaprojektowanie raportu za pomocą arkusza Microsoft Excel jako szablonu. Następnie można wygenerować raport **kwestionariusza** w formacie programu Excel lub PDF, oprócz generowania istniejącego raportu usług SQL Server Reporting Services (SSRS). Nowy raport można także zmodyfikować później, na życzenie. Nie są wymagane umiejętności kodowania.

1. Aby uruchomić istniejący raport, przejdź do **Kwestionariusz** \> **Projektowanie** \> **Raport z kwestionariuszy**.

    ![Wybranie elementu menu raportu kwestionariuszy w module kwestionariusza w celu uruchomienia istniejącego raportu usług SSRS](./media/er-quick-start1-application-menu-origin.png)

2. W oknie dialogowym **Raport z kwestionariuszy** określ kryteria wyboru. Zastosuj filtr, aby raport zawierał tylko kwestionariusz **SBCCrsExam**.

    ![Określenie kryteriów wyboru w oknie dialogowym Raport z kwestionariuszy](./media/er-quick-start1-ssrs-report-dialog.png)

Na poniższej ilustracji przedstawiono wygenerowaną wersję raportu SSRS dla kwestionariusza **SBCCrsExam**.

![Wygenerowany raport SSRS](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a>Konfigurowanie struktury ER

Jako użytkownik w roli dewelopera raportowania elektronicznego, musisz skonfigurować minimalny zestaw parametrów ER, zanim będziesz mógł zacząć używać struktury ER do projektowania nowego rozwiązania ER.

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a>Konfigurowanie parametrów modułu ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. W obszarze roboczym **Raportowanie elektroniczne** wybierz łącze **Parametry raportowania elektronicznego**.
3. Na stronie **Parametry raportowania elektronicznego** na karcie **Ogólne** ustaw opcję **Włącz tryb projektowania** na **Tak**.
4. Na karcie **Załączniki** ustaw następujące parametry:

    - Ustaw pole **Konfiguracje** na **Plik** dla firmy **USMF**.
    - W polach **Archiwum zadań**, **Tymczasowe**, **Podstawowe** i **Inne** należy ustawić typ **Plik**.

Aby uzyskać więcej informacji o parametrach modułu ER, zapoznaj się z tematem [Konfiguracja struktury ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a>Aktywowanie dostawcy konfiguracji ER

Każda konfiguracja ER jest oznaczona jako posiadana przez dostawcę konfiguracji ER. Dlatego przed rozpoczęciem dodawania lub edytowania konfiguracji ER należy aktywować dostawcę konfiguracji ER w obszarze roboczym **Raportowanie elektroniczne**.

> [!NOTE]
> Tylko właściciel konfiguracji ER może ją edytować. Dlatego przed rozpoczęciem edytowania konfiguracji ER należy aktywować samą konfigurację w obszarze roboczym **Raportowanie elektroniczne**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a>Przejrzenie listy dostawców konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Dostawcy konfiguracji**.
3. Na stronie **Dostawcy konfiguracji** każde ustawienie dostawcy ma unikatową nazwę i adres URL. Przejrzyj zawartość tej strony. Jeśli rekord dla **Litware, Inc.** (`https://www.litware.com`) już istnieje, pomiń następną procedurę, [Dodawanie nowego dostawcy konfiguracji ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a>Dodawanie nowego dostawcy formatu ER

1. Na stronie **Dostawcy konfiguracji** wybierz opcję **Nowa**.
2. W polu **Nazwa** wpisz **Litware, Inc.**
3. W polu **Adres internetowy** wprowadź `https://www.litware.com`.
4. Wybierz opcję **Zapisz**.

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a>Aktywowanie dostawcy konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. W obszarze roboczym **Raportowanie elektroniczne** wybierz pozycję **Litware, Inc.** dla dostawcy konfiguracji.
3. Wybierz **Aktywuj**.

Dalsze informacje o dostawcach konfiguracji ER znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a>Projektowanie modelu danych specyficznego dla domeny

Należy utworzyć nową konfigurację ER, która zawiera składnik [modelu danych](general-electronic-reporting.md#data-model-and-model-mapping-components) dla domeny biznesowej **Kwestionariusz**. Ten model danych będzie później używany jako źródło danych podczas projektowania formatu ER w celu wygenerowania raportu **Kwestionariusza**.

Wykonując kroki opisane w sekcji [Importowanie nowej konfiguracji modelu danych](#ImportDataModel), można zaimportować wymagany model danych z podanego pliku XML. Można również wykonać kroki opisane w sekcji [Tworzenie nowej konfiguracji modelu danych](#DesignDataModel), aby zaprojektować ten model danych od podstaw.

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a>Importowanie nowej konfiguracji modelu danych

1. Pobierz [model kwestionariuszy.wersja.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) i zapisz go na komputerze lokalnym.
2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
4. W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.
5. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **model kwestionariuszy.wersja.1.xml**.
6. Wybierz przycisk **OK**, aby importować konfigurację.

Aby kontynuować, pomiń następną procedurę, [Utwórz nową konfigurację modelu danych](#DesignDataModel).

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a>Tworzenie nowej konfiguracji modelu danych

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
3. Wybierz **Utwórz konfigurację**.
4. W rozwijanym menu w polu **Nazwa** wpisz **Model kwestionariusza**.
5. Wybierz **Stwórz konfiguracj**, aby stworzyć konfigurację.

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a>Nazywanie modelu danych

1. Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Model kwestionariusza**.
2. Wybierz opcję **Konstruktor**.
3. Na stronie **Projektant modelu danych** na skróconej karcie **Ogólne** w polu **Nazwa** wprowadź <a name="DataModeName"></a>**Kwestionariusze**.

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a>Dodaj nowe pola modelu danych

1. Na stronie **Projektant modelu danych** wybierz opcję **Nowa**.
2. W oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:

    1. Wybierz **Element główny modelu** jako typ nowego węzła.
    2. W polu **Nazwa** wprowadź nazwę <a name="RootDefinitionName"></a>**Element główny**.
    3. Wybierz **Dodaj**, aby dodać nowy węzeł.

    Ten główny deskryptor będzie używany do dostarczania danych dla raportu **Kwestionariusza**. Jeden model danych może mieć wiele deskryptorów. Każdy deskryptor można określić dla pojedynczego formatu ER, aby zidentyfikować dane wymagane do wygenerowania raportu.

3. Wybierz ponownie **Nowe**, a następnie w oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:

    1. Wybierz **Element podrzędny aktywnego węzła** jako typ nowego węzła.
    2. W polu **Nazwa** wpisz **CompanyName**.
    3. W polu **Typ przedmiotu** wybierz **Ciąg**.
    4. Wybierz **Dodaj**, aby dodać nowe pole.

    To pole jest wymagane do przekazania nazwy bieżącej firmy do raportu o roli właściciela, który korzysta z tego modelu danych jako źródła danych.

4. Wybierz ponownie **Nowe**, a następnie w oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:

    1. Wybierz **Element podrzędny aktywnego węzła** jako typ nowego węzła.
    2. W polu **Nazwa** wpisz **Kwestionariusz**.
    3. W polu **Kod przedmiotu** wybierz **Lista tabel**.
    4. Wybierz **Dodaj**, aby dodać nowe pole.

    To pole będzie używane do przekazywania listy kwestionariuszy do raportu ER, który wykorzystuje ten model danych jako źródło danych.

5. Wybierz węzeł **Kwestionariusz**.
6. Umożliwia kontynuowanie dodawania wymaganych pól edytowalnego modelu danych w taki sam sposób, dopóki nie zostanie wykonana następująca struktura modelu danych.

    | Ścieżka pola                                                    | Typ danych   | Oznaczenie pola/wartość zwrócona |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | Element główny                                                          |             | Punkt odniesienia do żądania danych kwestionariusza. |
    | Element główny\\CompanyName                                             | Ciąg      | Nazwa bieżącej firmy. |
    | Element główny\\ExecutionContext                                        | Zarejestruj      | Szczegóły formatu wykonania. |
    | Element główny\\ExecutionContext\\FormatName                            | Ciąg      | Nazwa uruchamianego formatu ER. |
    | Element główny\\Kwestionariusz                                           | Lista rekordów | Lista kwestionariuszy |
    | Element główny\\Kwestionariusz\\Aktywny                                   | Ciąg      | Stan obecnego kwestionariusza. |
    | Element główny\\Kwestionariusz\\Kod                                     | Ciąg      | Kod obecnego kwestionariusza. |
    | Element główny\\Kwestionariusz\\Opis                              | Ciąg      | Opis obecnego kwestionariusza. |
    | Element główny\\Kwestionariusz\\TypKwestionariusza                        | Ciąg      | Typ obecnego kwestionariusza. |
    | Element główny\\Kwestionariusz\\QuestionOrder                            | Ciąg      | Kolejność numeryczna obecnego kwestionariusza. |
    | Element główny\\Kwestionariusz\\ResultsGroup                             | Zarejestruj      | Parametry wynikowe aktualnego kwestionariusza. |
    | Element główny\\Kwestionariusz\\ResultsGroup\\Kod                       | Ciąg      | Kod identyfikacyjny bieżącej grupy wyników. |
    | Element główny\\Kwestionariusz\\ResultsGroup\\Opis                | Ciąg      | Opis bieżącej grupy wyników. |
    | Element główny\\Kwestionariusz\\ResultsGroup\\MaxNumberOfPoints          | Rzeczywisty        | Maksymalna liczba punktów, jaka może zostać uzyskana. |
    | Element główny\\Kwestionariusz\\Pytanie                                 | Lista rekordów | Lista pytań dla bieżącego kwestionariusza. |
    | Element główny\\Kwestionariusz\\Pytanie\\CollectionSequenceNumber       | Wartość całkowita     | Numer sekwencyjny bieżącej kolekcji odpowiedzi. |
    | Element główny\\Kwestionariusz\\Pytanie\\Identyfikator                             | Ciąg      | Kod identyfikacyjny bieżącego pytania. |
    | Element główny\\Kwestionariusz\\Pytanie\\MustBeCompleted                | Ciąg      | Flaga wskazująca, czy ma być udzielona odpowiedź na bieżące pytanie. |
    | Element główny\\Kwestionariusz\\Pytanie\\PrimaryQuestion                | Ciąg      | Flaga wskazująca, czy bieżące pytanie jest podstawowe. |
    | Element główny\\Kwestionariusz\\Pytanie\\SequenceNumber                 | Wartość całkowita     | Numer porządkowy aktualnego pytania. |
    | Element główny\\Kwestionariusz\\Pytanie\\Tekst                           | Ciąg      | Tekst aktualnego pytania. |
    | Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź                         | Lista rekordów | Lista odpowiedzi na aktualne pytanie. |
    | Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź\\CorrectAnswer          | Ciąg      | Flaga wskazująca, czy aktualna odpowiedź jest poprawna. |
    | Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź\\Punkty                 | Rzeczywisty        | Punkty zdobyte po wybraniu bieżącej odpowiedzi. |
    | Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź\\SequenceNumber         | Wartość całkowita     | Numer kolejny bieżącej odpowiedzi. |
    | Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź\\Tekst                   | Ciąg      | Tekst aktualnej odpowiedzi. |

    Na poniższej ilustracji przedstawiono ukończony edytowalny model danych na stronie **Projektant modelu danych**.

    ![Skonfigurowany model danych w projektancie modeli danych ER](./media/er-quick-start1-model2.png)

7. Zapisz zmiany.
8. Zamknij stronę **Projektant modelu danych**.

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a>Ukończenie projektu modelu danych

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Model kwestionariusza**.
3. Na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.
4. Wybierz **Zmień status** \> **Zakończone**.

Stan wersja 1 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**. Wersja 1 nie może być już zmieniana. Ta wersja zawiera skonfigurowany model danych i może być używana jako podstawa dla innych konfiguracji ER. Wersja 2 tej konfiguracji jest utworzona i ma stan **Wersja robocza**. Tę wersję można edytować, aby skorygować model danych **Kwestionariusza**.

![Wersje edytowalnej konfiguracji ER na stronie konfiguracje](./media/er-quick-start1-model-configuration.png)

Aby uzyskać więcej informacji na temat wersji konfiguracji funkcji ER, zajrzyj do [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md#component-versioning).

> [!NOTE]
> Skonfigurowany model danych to abstrakcyjna reprezentacja domeny biznesowej **Kwestionariusza** i nie zawiera żadnych powiązań z artefaktami specyficznymi dla Microsoft Dynamics 365 Finance.

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a>Umożliwia zaprojektowanie mapowania modelu dla skonfigurowanego modelu danych

Jako użytkownik w roli Deweloper raportowania elektronicznego musisz utworzyć nową konfigurację ER zawierającą zawiera składnik [mapowania modelu](general-electronic-reporting.md#data-model-and-model-mapping-components) dla modelu danych **Kwestionariusza**. Ten składnik implementuje skonfigurowany model danych dla Finance, dlatego jest on związany z Finance. Należy skonfigurować składnik mapowanie modelu, aby określić obiekty aplikacji, które muszą być używane do wypełniania skonfigurowanego modelu danych za pomocą danych aplikacji w czasie wykonywania. Aby wykonać to zadanie, należy zapoznać się ze szczegółami implementacji struktury danych w domenie biznesowej **Kwestionariusza** w Finance.

Wykonując kroki opisane w następujaćej sekcji [Importowanie nowej konfiguracji mapowania modelu](#ImportModelMapping), można zaimportować wymagany model mapowania konfiguracji z podanego pliku XML. Można również wykonać kroki opisane w sekcji [Stwórz nowy model konfiguracji mapowania](#CreateModelMapping), aby zaprojektować ten model mapowania od podstaw.

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a>Importowanie nowej konfiguracji mapowania modelu

1. Pobierz [Mapowanie kwestionariuszy.wersja.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) i zapisz go na komputerze lokalnym.
2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
4. W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.
5. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Mapowanie kwestionariuszy.wersja.1.1.xml**.
6. Wybierz przycisk **OK**, aby importować konfigurację.

Aby kontynuować, pomiń następną procedurę, [Utwórz nową konfigurację modelu mapowania](#CreateModelMapping).

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a>Stwórz nowy model konfiguracji mapowania

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Model kwestionariusza**.
3. Wybierz **Utwórz konfigurację**.
4. W oknie dialogowym rozwijanym wykonaj następujące kroki:

    1. W polu **Nowy** wybierz **Mapowanie modelu oparte na modelu danych Kwestionariusza**.
    2. W polu **Nazwa** wpisz **Mapowanie kwestionariusza**.
    3. W polu **Definicja modelu danych** wybierz definicję **Główną**.
    4. Wybierz **Stwórz konfiguracj**, aby stworzyć konfigurację.

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a>Projektowanie nowego składnika mapowania modelu

1. Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Mapowanie kwestionariusza**.
2. Wybierz opcję **Projektant**, aby otworzyć listę mapowań.
3. Wybierz **Mapowanie kwestionariuszy**, które zostało dodane automatycznie do definicji **Głównej**
4. Wybierz opcję **Projektant**, aby rozpocząć konfigurowanie wybranego mapowania.

Nowe mapowanie jest automatycznie dodawane do definicji **Głównej**. Mapowanie ma kierunek **Do modelu**. Dlatego mapowanie może być używane do wypełniania modelu danych z wymaganymi danymi.

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a>Dodawanie źródeł danych w celu uzyskania dostępu do tabel aplikacji

Należy skonfigurować źródła danych, aby uzyskać dostęp do tabel aplikacji zawierających szczegóły kwestionariusza.

1. Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Rekordy tabeli**.
2. Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do tabeli KMCollection, gdzie każdy rekord reprezentuje jeden kwestionariusz:

    1. W okienku **Źródła danych** wybierz **Dodaj źródło**.
    2. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Kwestionariusz**.
    3. W polu **Tabela** wprowadź **KMCollection**.
    4. Ustaw wartość **Monituj o zapytanie** opcji **Włącz profil**. Będziesz wtedy mógł określić opcje [filtrowania](../../fin-ops/get-started/advanced-filtering-query-options.md) dla tej tabeli w oknie dialogowym zapytania systemowego w czasie wykonywania.
    5. Wybierz przycisk **OK**, aby dodać nowe źródło danych.

3. W okienku **Typy źródła danych** wybierz opcję **Dynamics 365 for Operations\\Rekordy tabeli**.
4. Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do tabeli KMQuestion, gdzie każdy rekord reprezentuje jedno pytanie w kwestionariuszu:

    1. W okienku **Źródła danych** wybierz **Dodaj źródło**.
    2. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Pytanie**.
    3. W polu **Tabela** wprowadź **KMQuestion**.
    4. Wybierz przycisk **OK**, aby dodać nowe źródło danych.

5. W okienku **Typy źródła danych** wybierz opcję **Dynamics 365 for Operations\\Rekordy tabeli**.
6. Dodaj nową próbę źródła danych, które będzie używane w celu uzyskania dostępu do tabeli KMQuestion, gdzie każdy rekord reprezentuje jedną odpowiedź w kwestionariuszu:

    1. W okienku **Źródła danych** wybierz **Dodaj źródło**.
    2. W polu **Nazwa** wprowadź nazwę **Odpowiedź**.
    3. W polu **Tabela** wprowadź **KMAnswer**.
    4. Wybierz przycisk **OK**, aby dodać nowe źródło danych.

7. W okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.
8. Dodaj nowe pole obliczeniowe, które będzie używane w celu uzyskania dostępu do rekordu tabeli KMQuestionResultGroup z każdego rekordu tabeli KMCollection nadrzędnego:

    1. W okienku **Źródła danych** wybierz **kwestionariusz**.
    2. Wybierz opcję **Dodaj**.
    3. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **\$ResultGroup**.
    4. Wybierz opcję **Edytuj formułę**.
    5. W [Edytorze formuł ER](general-electronic-reporting-formula-designer.md) w polu **Formuła** wprowadź **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** do używania [ścieżki](er-formula-language.md#paths) relacji jeden-do-wielu między tabelami KMCollection i KMQuestionResultGroup.
    6. Wybierz przycisk **Zapisz** i zamknij edytor formuł.
    7. Wybierz przycisk **OK**, aby dodać nowe pole obliczeniowe.

9. W okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.
10. Dodaj nowe pole obliczeniowe, które będzie używane do uzyskiwania dostępu do rekordów pytań w tabeli KMQuestion z każdego rekordu nadrzędnej tabeli KMCollectionQuestion:

    1. W okienku **Źródła danych** wybierz **kwestionariusz**.
    2. Rozwiń węzeł **\<Relacje**, który zawiera relacje jeden-do-wielu w tabeli KMCollection.
    3. Zaznacz powiązaną tabelę **KMCollectionQuestion**, a następnie wybierz przycisk **Dodaj**.
    4. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **\$Pytanie**.
    5. Wybierz opcję **Edytuj formułę**.
    6. W edytorze formuł, w polu **Formuła** wprowadź **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))**, aby zwrócić odpowiednie rekordy pytań z tabeli KMQuestion.
    7. Wybierz przycisk **Zapisz** i zamknij edytor formuł.
    8. Wybierz przycisk **OK**, aby dodać nowe pole obliczeniowe.

11. W okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.
12. Dodaj nowe pole obliczeniowe, które będzie używane do uzyskiwania dostępu do rekordów odpowiedzi tabeli KMAnswer z każdego rekordu nadrzędnej tabeli KMQuestion:

    1. W okienku **Źródła danych** wybierz opcję **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**, a następnie wybierz przycisk **Dodaj**.
    2. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **\$Odpowiedź**.
    3. Wybierz opcję **Edytuj formułę**.
    4. W edytorze formuł, w polu **Formuła** wprowadź **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)**, aby zwrócić odpowiednie rekordy odpowiedzi z tabeli KMAnswer.
    5. Wybierz przycisk **Zapisz** i zamknij edytor formuł.
    6. Wybierz przycisk **OK**, aby dodać nowe pole obliczeniowe.

13. W okienku **Typy źródła danych** wybierz opcję **Dynamics 365 for Operations\\Tabele**.
14. Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do metod tabeli CompanyInfo. Należy zauważyć, że metoda **find()** tej tabeli zwraca rekord reprezentujący firmę bieżącego wystąpienia Finance, które to mapowanie jest wywoływane w kontekście.

    1. W okienku **Źródła danych** wybierz **Dodaj źródło**.
    2. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **CompanyInfo**.
    3. W polu **Tabela** wprowadź **CompanyInfo**.
    4. Wybierz przycisk **OK**, aby dodać nowe źródło danych.

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a>Dodawanie źródeł danych w celu uzyskania dostępu do wyliczenia aplikacji

Należy skonfigurować źródła danych, aby uzyskać dostęp do wyliczeń aplikacji i porównać ich wartości z wartościami pól typu **Wyliczenie** w tabelach aplikacji. Aby wypełnić odpowiednie pola modelu danych, należy skorzystać z wyników porównania.

1. Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Wyliczenie**.
2. Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do wartości wyliczenia **EnumAppNoYes**:

    1. W okienku **Źródła danych** wybierz **Dodaj źródło**.
    2. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **EnumAppNoYes**.
    3. W polu **Wyliczenie** wprowadź **NoYes**.
    4. Wybierz przycisk **OK**, aby dodać nowe źródło danych.

3. W okienku **Typy źródła danych** wybierz opcję **Dynamics 365 for Operations\\Wyliczenie**.
4. Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do wartości wyliczenia **KMCollectionQuestionMode**:

    1. W okienku **Źródła danych** wybierz **Dodaj źródło**.
    2. W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **EnumAppQuestionOrder**.
    3. W polu **Wyliczenie** wprowadź **EnumAppQuestionOrder**.
    4. Wybierz przycisk **OK**, aby dodać nowe źródło danych.

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a>Dodawanie etykiet ER w celu wygenerowania raportu w określonym języku

Możesz dodać etykiety ER, aby skonfigurować niektóre źródła danych, aby zwracały wartości zależne od języka zdefiniowanego w kontekście wywołania mapowania modelu.

1. Na stronie **Projektant mapowania modelu** w okienku **Źródła danych** wybierz **Odpowiedź**, a następnie wybierz **Edytuj**.
2. Aktywuj pole **Etykieta**.
3. Wybierz **Tłumacz**.
4. W oknie dialogowym **Tłumaczenie tekstu** wykonaj następujące kroki:

    1. W polu **Identyfikator etykiety** wejdź do **PositiveAnswer**.
    2. W polu **tekst w języku domyślnym** wprowadź wartość **Tak**.
    3. Wybierz **Tłumacz**.
    4. W polu **Identyfikator etykiety** wejdź do **NegativeAnswer**.
    5. W polu **Tekst w języku domyślnym** wprowadź wartość **Nie**.
    6. Wybierz **Tłumacz**.

5. Zamknij okno dialogowe **Tłumaczenie tekstu**.
6. Wybierz **Anuluj**.

![Dodawanie etykiet ER dla mapowania edytowalnego modelu](./media/er-quick-start1-adding-labels.png)

Wprowadziłeś etykiety ER tylko dla języka domyślnego. Aby uzyskać informacje o tym, jak można tłumaczyć etykiety ER na inne języki, zobacz [Projektowanie raportów wielojęzycznych](er-design-multilingual-reports.md).

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a>Dodaj źródło danych w celu przekształcenia wyników porównywania wartości wyliczenia z wartością tekstową

Ponieważ należy kilkakrotnie przekształcić wyniki porównania między wartościami wyliczenia i wartościami tekstowymi w przypadku źródeł różnic, warto skonfigurować tę logikę jako pojedyncze źródło danych. Jednak aby to źródło danych było wielokrotnego użytku, należy skonfigurować je jako parametry źródła danych. Aby uzyskać więcej informacji, zobacz [Obsługa sparametryzowanych wywołań źródeł danych narzędzia Raportowanie elektroniczne typu pola obliczeniowego](er-calculated-field-type.md).

1. Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz **Ogólne\\Pusty kontener**.
2. Dodaj nowe źródło danych kontenera:

    1. W okienku **Źródła danych** wybierz **Dodaj źródło**.
    2. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Pomocnik**.
    3. Wybierz przycisk **OK**, aby dodać nowe źródło danych kontenera.

3. W okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.
4. Dodaj nowe źródło danych:

    1. W okienku **Źródła danych** wybierz **Pomocnik**.
    2. Wybierz opcję **Dodaj**.
    3. W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **NoYesEnumToString**.
    4. Wybierz opcję **Edytuj formułę**.
    5. W edytorze formuł wybierz opcję **Parametry**.
    6. Wykonaj następujące kroki, aby określić parametry dla skonfigurowanego wyrażenia:

        1. Wybierz pozycję **Nowy**.
        2. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Argument**.
        3. W polu **Typ** wybierz typ danych **Wartość logiczna**.
        4. Kliknij przycisk **OK**.

    7. W polu **Formuła** wprowadź **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")**, aby zwrócić tekst odpowiedniej etykiety ER, w zależności od języka kontekstu wykonywania i wartości określonego parametru.
    8. Wybierz przycisk **Zapisz** i zamknij edytor formuł.
    9. Wybierz przycisk **OK**, aby dodać nowe źródło danych.

![Skonfigurowany model mapowania w projektancie modeli mapowania ER](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a>Powiąż źródła danych z polami modelu danych

Aby określić sposób, w jaki model danych będzie wypełniał dane aplikacji w czasie wykonywania, należy powiązać skonfigurowane źródła danych z polami modelu danych.

1. Na stronie **Projektant mapowania modelu** w okienku **Model danych** wybierz **CompanyName**.
2. W okienku **Źródła danych** rozwiń węzeł **CompanyInfo**, a następnie wykonaj następujące kroki:

    1. Rozwiń węzeł **CompanyInfo.find()**, który reprezentuje metodę **find()** tabeli CompanyInfo.
    2. Wybierz **CompanyInfo.find().Name**.
    3. Wybierz opcję **Powiąż**, aby wpisać nazwę firmy, z której wywoływane jest skonfigurowane mapowanie modelu w kontekście at runtime.

3. W okienku **Model danych** wybierz **Kwestionariusz**.
4. W okienku **Źródła danych** wybierz opcję **Kwestionariusz**, a następnie wybierz **Powiąż**, aby wypełnić rekordy kwestionariusza.
5. W okienku **Model danych** rozwiń węzeł **Kwestionariusz**, a następnie wykonaj następujące kroki:

    1. W okienku **Model danych** wybierz **Aktywne**.
    2. W okienku **Model danych** wybierz **Edytuj**.
    3. W polu **Formuła** wprowadź wartość **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)**, aby wypełnić wynik porównania między wartościami wyliczenia zależne od tekstu i języka.

6. Kontynuuj wiązanie źródeł danych z polami modelu danych w ten sam sposób, aż uzyskasz następujący wynik.

    | Ścieżka pola                                              | Typ danych   | Akcja | Wyrażenie wiązania |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | CompanyName                                             | Ciąg      | Powiąż   | CompanyInfo.'find()'.Name |
    | Kwestionariusz                                           | Lista rekordów | Powiąż   | Kwestionariusz |
    | Kwestionariusz\\Aktywny                                   | Ciąg      | Edycja   | Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes) |
    | Kwestionariusz\\Kod                                     | Ciąg      | Powiąż   | \@.kmCollectionId |
    | Kwestionariusz\\Opis                              | Ciąg      | Powiąż   | \@.Opis |
    | Kwestionariusz\\TypKwestionariusza                        | Ciąg      | Powiąż   | \@.'&gt;Relations'.kmCollectionTypeId.Description |
    | Kwestionariusz\\QuestionOrder                            | Ciąg      | Edycja   | CASE (\@.questionMode,<br>EnumAppQuestionOrder.Conditional, "Conditional",<br>EnumAppQuestionOrder.Random, „Losowo (procent w kwestionariuszu)”,<br>EnumAppQuestionOrder.RandomGroup, „Losowo (procent w grupach wyników)”,<br>EnumAppQuestionOrder.Sequence, „Sekwencyjne”,<br>"") |
    | Kwestionariusz\\ResultsGroup                             | Zarejestruj      |        | |
    | Kwestionariusz\\ResultsGroup\\Kod                       | Ciąg      | Powiąż   | \@.'\$ResultGroup'.kmQuestionResultGroupId |
    | Kwestionariusz\\ResultsGroup\\Opis                | Ciąg      | Powiąż   | \@.'\$ResultGroup'.description |
    | Kwestionariusz\\ResultsGroup\\MaxNumberOfPoints          | Rzeczywisty        | Powiąż   | \@.'\$ResultGroup'.maxPoint |
    | Kwestionariusz\\Pytanie                                 | Lista rekordów | Powiąż   | \@.'&lt;Relations'.KMCollectionQuestion |
    | Kwestionariusz\\Pytanie\\CollectionSequenceNumber       | Wartość całkowita     | Powiąż   | \@.answerCollectionSequenceNumber |
    | Kwestionariusz\\Pytanie\\Identyfikator                             | Ciąg      | Powiąż   | \@.kmQuestionId |
    | Kwestionariusz\\Pytanie\\MustBeCompleted                | Ciąg      | Edycja   | Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes) |
    | Kwestionariusz\\Pytanie\\PrimaryQuestion                | Ciąg      | Powiąż   | \@.parentQuestionId |
    | Kwestionariusz\\Pytanie\\SequenceNumber                 | Wartość całkowita     | Powiąż   | \@.SequenceNumber |
    | Kwestionariusz\\Pytanie\\Tekst                           | Ciąg      | Powiąż   | \@.'\$Question'.text |
    | Kwestionariusz\\Pytanie\\Odpowiedź                         | Lista rekordów | Powiąż   | \@.'\$Question'.'\$Answer' |
    | Kwestionariusz\\Pytanie\\Odpowiedź\\CorrectAnswer          | Ciąg      | Edycja   | Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes) |
    | Kwestionariusz\\Pytanie\\Odpowiedź\\Punkty                 | Rzeczywisty        | Powiąż   | \@.point |
    | Kwestionariusz\\Pytanie\\Odpowiedź\\SequenceNumber         | Wartość całkowita     | Powiąż   | \@.sequenceNumber |
    | Kwestionariusz\\Pytanie\\Odpowiedź\\Tekst                   | Ciąg      | Powiąż   | \@.text |

    Na poniższej ilustracji przedstawiono ostatni stan skonfigurowanego mapowania modelu na stronie **Projektanta mapowania modeli**.

    ![W pełni skonfigurowany model mapowania w projektancie modeli mapowania ER](./media/er-quick-start1-mapping2.png)

7. Zapisz zmiany.
8. Zamknij stronę **Projektant mapowania modelu**.

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a>Umożliwia zakończenie projektu mapowania modelu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Mapowanie kwestionariusza**.
3. Na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.
4. Wybierz **Zmień status** \> **Zakończone**.

Stan wersja 1.1 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**. Wersja 1.1 nie może być już zmieniana. Ta wersja zawiera skonfigurowany model mapowania i może być używana jako podstawa dla innych konfiguracji ER. Wersja 1.2 tej konfiguracji jest utworzona i ma stan **Wersja robocza**. Tę wersję można edytować, aby skorygować konfigurację **Mapowanie kwestionariusza**.

![Wersje edytowalnej konfiguracji ER na stronie konfiguracje](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> Skonfigurowane mapowanie modelu to specyficzna dla finansów implementacja abstrakcyjnego modelu danych, który reprezentuje domenę biznesową **Kwestionariusz**.

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a>Projektowanie szablonu raportu niestandardowego

Struktura ER wykorzystuje predefiniowane szablony do generowania raportów w formatach Microsoft Office (skoroszyty programu Excel lub dokumenty Word). Podczas generowania wymaganego raportu szablon jest wypełniany wymaganymi danymi zgodnie ze skonfigurowanym przepływem danych. Dlatego należy najpierw zaprojektować szablon raportu niestandardowego. Ten szablon musi być zaprojektowany jako skoroszyt programu Excel, którego struktura reprezentuje układ raportu niestandardowego. Należy nazwać każdy element programu Excel, który ma być wypełniony wymaganymi danymi.

1. Pobierz [Szablon raportu kwestionariusza.xslx](https://go.microsoft.com/fwlink/?linkid=851448) i zapisz go na komputerze lokalnym.
2. Otwórz plik w programie Excel i przejrzyj strukturę skoroszytu.

Jak pokazuje poniższa ilustracja, pobrany szablon został zaprojektowany w celu wydrukowania określonych kwestionariuszy, które zawierają pytania zawarte w kwestionariuszu wraz z odpowiednimi odpowiedziami.

![Szablon programu Excel do drukowania określonych kwestionariuszy](./media/er-quick-start1-template-layout.png)

Do tego szablonu zostały dodane nazwy programu Excel, aby wypełnić szczegóły kwestionariusza. Do przeglądania nazw Excel można użyć Menedżera nazw.

![Przeglądanie nazw programu Excel w podanym szablonie programu Excel za pomocą Menedżera nazw](./media/er-quick-start1-template-names.png)

Etykiety raportów zostały dodane jako stały tekst w języku angielskim. Etykiety raportów można zastąpić nowymi nazwami programu Excel, które wypełniają etykiety tekstem zależnym od języka, używając [etykiet](#AddMmLabels) formatu ER, tak jak w przypadku wyrażeń zależnych od języka w skonfigurowanym mapowaniu modelu. W takim przypadku do edytowalnego formatu ER trzeba dodać etykiety ER.

Na poniższej ilustracji przedstawiono nagłówek raportu niestandardowego, który umożliwia stronicowanie w Excel.

![Niestandardowy nagłówek raportu w podanym szablonie programu Excel](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a>Projektowanie formatu

Jako użytkownik pełniący rolę konsultanta funkcjonalnego raportowania elektronicznego należy utworzyć nową konfigurację ER zawierającą komponent [formatu](general-electronic-reporting.md#FormatComponentOutbound). Należy skonfigurować składnik formatu w celu określenia sposobu, w jaki szablon raportu będzie wypełniał wymagane dane w czasie wykonywania.

Wykonując kroki opisane w sekcji [Import zaprojektowanej konfiguracji formatu](#FormatImport), można zaimportować wymagany format z podanego pliku XML. Można również wykonać kroki opisane w sekcji [Utwórz nową konfigurację formatu](#FormatCreate), aby zaprojektować ten format od podstaw.

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a>Import zaprojektowanej konfiguracji formatu

1. Pobierz [Kwestionariusze formatu.wersja.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) i zapisz go na komputerze lokalnym.
2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
4. W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.
5. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Format kwestionariuszy.wersja.1.1.xml**.
6. Wybierz przycisk **OK**, aby importować konfigurację.

Aby kontynuować, pomiń następną procedurę, [Utwórz nową konfigurację formatu](#FormatCreate).

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a>Utwórz nową konfigurację formatu.
 
1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Model kwestionariusza**.
3. Wybierz **Utwórz konfigurację**.
4. W oknie dialogowym rozwijanym wykonaj następujące kroki:

    1. W polu **Nowy** wybierz **Format oparty na modelu danych Kwestionariusza**.
    2. W polu **Nazwa** wpisz **Raport kwestionariusza**.
    3. W polu **Wersja modelu danych** wybierz **1**.

        > [!NOTE]
        > - W przypadku wybrania określonej wersji podstawowego modelu danych, struktura odpowiedniej wersji modelu danych zostanie przedstawiona jako struktura **Modelu** źródła danych w utworzonym formacie.
        > - Można pozostawić to pole puste. W takim przypadku struktura **Wersji roboczej** modelu danych zostanie przedstawiona jako struktura źródła danych **Modelu** w utworzonym formacie. Następnie można dostosować model i natychmiast zobaczyć te zmiany w formacie. Takie podejście może poprawić wydajność projektu rozwiązania ER podczas konfigurowania modelu danych, mapowania modelu i formatowania jednocześnie.
        > - W przypadku wybrania konkretnej wersji podstawowego modelu danych można użyć **Wersji roboczej** w późniejszym czasie, gdy zaczniesz edytować format.

    4. W polu **Definicja modelu danych** wybierz definicję **Główną**.

5. Wybierz **Stwórz konfiguracj**, aby stworzyć konfigurację.

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a>Zaimportuj szablon raportu

1. Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Raport kwestionariusza**.
2. Wybierz opcję **Projektant**, aby rozpocząć konfigurowanie formatu niestandardowego.
3. Na stronie **Projektant formatu** w okienku akcji wybierz **Importuj** \> **Importuj z programu Excel**.
4. W oknie dialogowym wykonaj następujące kroki:

    1. Wybierz **Dodaj szablon**.
    2. Znajdź i wybierz lokalnie zapisany plik **Szablon raportu kwestionariusza.xslx**, a następnie wybierz opcję **Otwórz**.
    3. Wybierz przycisk **OK**, aby importować szablon.

    ![Importowanie szablonu raportu](./media/er-quick-start1-template-import.png)

Element formatu **Excel\\Plik** jest automatycznie dodawany do formatu edytowalnego jako element główny. Dodatkowo, element formatu **Excel\\Zakres** lub element formatu **Excel\\Komórka** jest automatycznie dodawany do każdej rozpoznanej nazwy Excela importowanego szablonu. Format **Excel\\Nagłówek** z zagnieżdżonym elementem **Ciąg** jest dodawany automatycznie w celu odzwierciedlenia ustawień nagłówka zaimportowanego szablonu.

![Struktura formatu obejmująca automatycznie dodane elementy w projektancie operacji ER](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a>Konfigurowanie formatu

1. Na stronie **Projektant formatów** w drzewie formatu wybierz element główny programu **Excel**.
2. Na karcie **Format** po prawej stronie strony, w polu **Nazwa** wprowadź <a name="AddFormatRootElement"></a>**Raport**.
3. W polu **Preferencje języka** wybierz opcję **Preferencje użytkownika**, aby uruchomić raport w preferowanym języku użytkownika.
4. W polu **Preferencje dotyczące kultury** wybierz opcję **Preferencje użytkownika**, aby uruchomić raport dostosowany do preferencji kulturowych użytkownika.

    Aby uzyskać informacje dotyczące sposobu określania kontekstu języka i kultury dla procesu ER, zapoznaj się z tematem [Projektowanie raportów wielojęzycznych](er-design-multilingual-reports.md).

    ![Konfigurowanie ustawień języka i kultury dla zaprojektowanego raportu w projektancie operacji ER](./media/er-quick-start1-template-format-structure1.png)

5. W drzewie formatu rozwiń węzeł główny, a następnie wybierz pozycję **ResultsGroup**.
6. Na karcie **Format** w polu **Kierunek replikacji** wybierz opcję **Brak replikacji**, ponieważ nie ma oczekiwanego wielu grup wyników dla jednego kwestionariusza.

    ![Definiowanie kierunku replikacji dla elementów formatu zakresu w projektancie operacji ER](./media/er-quick-start1-template-format-structure2.png)

7. Wybierz opcję **Zapisz**.

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a>Definiowanie powiązania danych dla tytułu raportu

Należy określić powiązanie danych dla elementu formatu używanego do wypełniania tytułu wygenerowanego raportu.

1. Na stronie **Projektant formatów** na karcie **Mapowanie** po prawej stronie wybierz element pliku **Raport\\ReportTitle** w drzewie formatu.
2. Wybierz opcję **Edytuj formułę**.
3. W edytorze formuł wybierz opcję **Przetłumacz**.
4. W oknie dialogowym **Tłumaczenie tekstu** wykonaj następujące kroki:

    1. W polu **Identyfikator etykiety** wejdź do **ReportTitle**.
    2. W polu **Tekst w języku domyślnym** wprowadź wartość **Raport kwestionariusza**.
    3. Zaznacz element **Przetłumacz** i kliknij przycisk **Zapisz**.
    4. Wybierz opcję **Przetłumacz**, aby zamknąć okno dialogowe **Tłumaczenie tekstu**.

5. Zamknij edytor formuł.

    ![Konfigurowanie powiązania do wypełnienia w tytule wygenerowanego raportu](./media/er-quick-start1-add-report-title-label.png)

Tę technikę można stosować do tworzenia wszystkich etykiet zależnych od języka bieżącego szablonu. Aby uzyskać informacje dotyczące sposobu tłumaczenia dodanych etykiet jednej konfiguracji ER na wszystkie obsługiwane języki, zapoznaj się z tematami [Projektowanie raportów wielojęzycznych](er-design-multilingual-reports.md).

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a>Przejrzyj źródło danych modelu

1. Na stronie **Projektant formatów** na karcie **Mapowanie** wybierz <a name="ModelDSName"></a>**model** źródła danych, który reprezentuje podstawowy model danych tego formatu ER.
2. Wybierz opcję **Edycja**.
3. Przejrzyj informacje w oknie dialogowym **Właściwości źródła danych**. To źródło danych reprezentuje wersję 1 składnika modelu danych **Kwestionariuszy**, który znajduje się w konfiguracji ER dla **Modelu kwestionariuszy**.

![Właściwości źródła danych modelu w projektancie operacji ER](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a>Powiązanie elementów formatu na pola źródła danych

Aby określić sposób wypełniania szablonu w czasie wykonywania, należy powiązać każdy element formatu powiązany z odpowiednią nazwą programu Excel z pojedynczym polem źródła danych tego formatu.

1. Na stronie **Projektant formatów** w drzewie formatu wybierz element formatu **Raport\\CompanyName**.
2. Na karcie **Mapowanie** wybierz pole źródła danych **model.CompanyName** typu **Ciąg**.
3. Wybierz opcję **Powiąż**, aby wprowadzić nazwę firmy w szablonie.
4. W drzewie formatu zaznacz element **Report\\Kwestionariusz**.
5. Na karcie **Mapowanie** wybierz pole źródła danych **model.Questionnaire** typu **Lista rekordów**.
6. Wybierz **Powiąż**.
7. Wybierz opcję **Pokaż szczegóły**, aby wyświetlić więcej szczegółów dotyczących elementów formatu.

    Element formatu zakresu **Kwestionariusza** jest skonfigurowany jako replikowany pionowo. Jeśli jest powiązany ze źródłem danych typu **Lista rekordów**, odpowiedni zakres **Kwestionariusza** w szablonie programu Excel jest powtarzany dla każdego rekordu powiązanego źródła danych.
 
    ![Powiązanie elementu formatu zakresu kwestionariusza z odpowiednimi źródłami danych listy rekordów w projektancie operacji ER](./media/er-quick-start1-bindings1.png)

    Ponieważ zakres **Kwestionariusza** szablonu programu Excel jest zdefiniowany między wierszami od 5 do 14, te wiersze są powtarzane dla każdego raportowanego kwestionariusza.

    ![Wiersze w szablonie programu Excel, które zostaną powtórzone w wygenerowanym raporcie dla każdego rekordu źródeł danych Listy rekordów](./media/er-quick-start1-template-questionnaire-range.png)

8. Skonfiguruj podobne powiązania dla pozostałych elementów formatu, tak jak to opisano w poniższej tabeli.

    > [!NOTE]
    > W tej tabeli informacje w kolumnie „ścieżka źródła danych” zakładają, że funkcja ER [ścieżka względna](relative-path-data-bindings-er-models-format.md) jest włączona.

    | Ścieżka elementu formatu                                      | Ścieżka źródła danych |
    |----------------------------------------------------------|------------------|
    | Excel\\ReportTitle                                       | **\@"GER\_LABEL:ReportTitle"** |
    | Excel\\CompanyName                                       | **model.CompanyName** |
    | Excel\\Kwestionariusz                                     | **model.Questionnaire** |
    | Excel\\Kwestionariusz\\Aktywny                             | **\@.Active**, gdzie **\@** to **model.Questionnaire** |
    | Excel\\Kwestionariusz\\Kod                               | **\@.Code** |
    | Excel\\Kwestionariusz\\Opis                        | **\@.Opis** |
    | Excel\\Kwestionariusz\\TypKwestionariusza                  | **\@.QuestionnaireType** |
    | Excel\\Kwestionariusz\\QuestionOrder                      | **\@.QuestionOrder** |
    | Excel\\Kwestionariusz\\ResultsGroup\\Kod\_               | **\@.ResultsGroup.Code** |
    | Excel\\Kwestionariusz\\ResultsGroup\\Opis\_        | **\@.ResultsGroup.Description** |
    | Excel\\Kwestionariusz\\ResultsGroup\\MaxNumberOfPoints    | **\@.ResultsGroup.MaxNumberOfPoint** |
    | Excel\\Kwestionariusz\\Pytanie                           | **\@.Pytanie** |
    | Excel\\Kwestionariusz\\Pytanie\\CollectionSequenceNumber | **\@.CollectionSequenceNumber**, gdzie **\@** to **model.Questionnaire.Question** |
    | Excel\\Kwestionariusz\\Pytanie\\Identyfikator                       | **\@.Id** |
    | Excel\\Kwestionariusz\\Pytanie\\MustBeCompleted          | **\@.MustBeCompleted** |
    | Excel\\Kwestionariusz\\Pytanie\\PrimaryQuestion          | **\@.PrimaryQuestion** |
    | Excel\\Kwestionariusz\\Pytanie\\SequenceNumber           | **\@.SequenceNumber** |
    | Excel\\Kwestionariusz\\Pytanie\\Tekst                     | **\@.Text** |
    | Excel\\Kwestionariusz\\Pytanie\\Odpowiedź                   | **\@.Answer** |
    | Excel\\Kwestionariusz\\Pytanie\\Odpowiedź\\CorrectAnswer    | **\@.CorrectAnswer**, gdzie **\@** to **model.Questionnaire.Answer** |
    | Excel\\Kwestionariusz\\Pytanie\\Odpowiedź\\Punkty           | **\@.Points** |
    | Excel\\Kwestionariusz\\Pytanie\\Odpowiedź\\Tekst             | **\@.Text** |

9. Po zakończeniu wybierz przycisk **Zapisz**.

Na poniższej ilustracji przedstawiono ostatni stan skonfigurowanych powiązaniań danych na stronie **Projektanta formatów**.

![Skonfigurowane powiązania danych w projektancie operacji ER](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> Cała kolekcja określonych źródeł danych i powiązań reprezentuje składnik odwzorowania formatu skonfigurowanego formatu. To mapowanie formatu jest wywoływane w przypadku uruchomienia skonfigurowanego formatu generowania raportu.

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a>Uruchamianie zaprojektowanego formatu od ER

Możesz teraz uruchomić zaprojektowany format do celów testowych ze strony **Konfiguracje**.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Raport kwestionariusza**.
3. Wybierz opcję **Projektant** dla wersji formatu, która ma stan **Wersja robocza**.
4. Na stronie **Projektant formatów** wybierz opcję **Uruchom**.
5. W oknie dialogowym **Parametry ER**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.
6. Wybierz przycisk **OK**, aby filtrować opcje.
7. Wybierz przycisk **OK**, aby uruchomić raport.
8. Przejrzyj wygenerowany raport.

[Domyślnie](electronic-reporting-destinations.md#default-behavior) wygenerowany raport jest dostarczany jako plik programu Excel, który można pobrać. Na poniższych ilustracjach przedstawiono dwie strony wygenerowanego raportu w formacie programu Excel.

![Przykład wygenerowanego raportu w formacie programu Excel, Strona 1](./media/er-quick-start1-report1a.png)

![Przykład wygenerowanego raportu w formacie programu Excel, Strona 2](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a>Dostrajanie zaprojektowanego formatu

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a>Modyfikowanie formatu w celu zmiany nazwy wygenerowanego dokumentu

Domyślnie wygenerowany dokument ma nazwę, używając aliasu bieżącego użytkownika. Modyfikując format, można zmienić to zachowanie, tak aby wygenerowany dokument mógł zostać nazwany na podstawie logiki niestandardowej użytkownika. Na przykład nazwa wygenerowanego dokumentu może być oparta na dacie i godzinie bieżącej sesji oraz na tytule raportu.

1. Na stronie **Projektant formatów** wybierz element główny **Raport**.
2. Na karcie **Mapowanie** wybierz opcję **Edytuj nazwę pliku**.
3. W polu **Formuła** wprowadź **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.
4. Wybierz przycisk **Zapisz** i zamknij edytor formuł.
5. Wybierz opcję **Zapisz**.

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a>Umożliwia zmodyfikowanie formatu w celu zmiany kolejności pytań

Pytania nie są poprawnie uporządkowane w wygenerowanym raporcie. Kolejność można zmienić, modyfikując format.

1. Na stronie **Projektant formatów** wybierz element główny **Raport**.
2. Na karcie **Mapowanie** w drzewie formatu rozwiń **Raport\\Kwestionariusz\\Pytanie**.

    ![Element formatu pytań dla zakresu typu Projektant operacji ER](./media/er-quick-start1-bindings3.png)

3. Na karcie **Mapowanie** wybierz opcję **model.Questionnaire**.
4. Wybierz opcję **Dodaj** \> **Funkcje\\Pole obliczeniowe**, a następnie w polu **Nazwa** wprowadź **OrderedQuestions**.
5. Wybierz opcję **Edytuj formułę**.
6. W edytorze formuł w polu **Formuła** wprowadź **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** w celu uporządkowania listy pytań bieżącego kwestionariusza według numeru porządkowego.
7. Wybierz przycisk **Zapisz** i zamknij edytor formuł.
8. Wybierz przycisk **OK**, aby ukończyć wprowadzanie nowego pola obliczeniowego.
9. Na karcie **Mapowanie** wybierz opcję **model.Questionnaire.OrderedQuestions**.
10. W drzewie formatu wybierz **Excel\\Kwestionariusz\\Pytanie**.
11. Wybierz opcję **Powiąż**, a następnie potwierdź, że bieżąca ścieżka **model.Questionnaire.Questions** jest zastępowana nową ścieżką **model.Questionnaire.OrderedQuestions** we wszystkich powiązaniach elementów zagnieżdżonych.
12. Wybierz opcję **Zapisz**.

![Powiązanie elementu formatu pytania ze skonfigurowanym źródłem danych OrderedQuestions w projektancie operacji ER](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a>Uruchamianie zmodyfikowanego formatu od ER

Możesz teraz uruchomić zmodyfikowany format do celów testowych ze środowiska ER.

1. Na stronie **Projektant formatów** wybierz opcję **Uruchom**.
2. W oknie dialogowym **Parametry ER**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.
3. Wybierz przycisk **OK**, aby filtrować opcje.
4. Wybierz przycisk **OK**, aby uruchomić raport.
5. Przejrzyj wygenerowany raport.

Poniższa ilustracja przedstawia wygenerowany raport w formacie Excel, w którym pytania są poprawnie uporządkowane.

![Wygenerowany raport w formacie Excel z poprawnie uporządkowanymi pytaniami](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a>Zakończ projektowanie formatu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Raport kwestionariusza**.
3. Na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.
4. Wybierz **Zmień status** \> **Zakończone**.

Stan wersja 1.1 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**. Wersja 1.1 nie może być już zmieniana. Ta wersja zawiera skonfigurowany format i może być używana do drukowania raportu niestandardowego. Wersja 1.2 tej konfiguracji jest utworzona i ma stan **Wersja robocza**. Tę wersję można edytować, aby skorygować format raportu **Kwestionariusz**.

![Wersje edytowalnej konfiguracji ER na stronie konfiguracje](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> Skonfigurowany format to projekt raportu **Kwestionariusz** i nie zawiera żadnych relacji z artefaktami specyficznymi dla Finance.

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a>Opracowywanie Artefacts aplikacji w celu wywołania zaprojektowanego raportu

Jako użytkownik w roli administratora systemu musisz opracować nową logikę, tak aby skonfigurowany format ER mógł być wywoływany z interfejsu użytkownika aplikacji (UI) w celu wygenerowania raportu niestandardowego. Obecnie moduł ER nie oferuje żadnych możliwości konfigurowania tego typu logiki. W związku z tym wymagane są pewne prace technologiczne. 

Aby opracować nową logikę, należy wdrożyć topologię obsługującą ciągłe budowanie. Więcej informacji znajdziesz w [Wdrażanie topologii obsługujących ciągłą budowę i automatyzację testów](../perf-test/continuous-build-test-automation.md). Ponadto musisz także mieć dostęp do środowiska programowania dla tej topologii. Aby uzyskać więcej informacji na temat dostępnego interfejsu API ER, zapoznaj się z tematem [Interfejs API struktury modułu Raportowanie elektroniczne](er-apis-app73.md).

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a>Zmień kod źródłowy

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a>Dodawanie klasy kontraktu danych

Dodaj nową klasę **QuestionnairesErReportContract** do projektu programu Microsoft Visual Studio i wpisz kod określający kontrakt danych, który ma być używany do uruchamiania skonfigurowanego formatu ER.

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a>Dodaj klasę konstruktora UI

Dodaj nową klasę **QuestionnairesErReportUIBuilder** do projektu Visual Studio i wpisz kod, aby wygenerować okno dialogowe środowiska uruchomieniowego, które będzie używane do wyszukiwania identyfikatora mapowania formatu ER, który musi zostać uruchomiony. Podany kod wyszukuje tylko formaty ER, które zawierają źródło danych typu **modelu danych**, które odwołują się do modelu danych **[Kwestionariuszy](#DataModeName)** przy użyciu definicji **[głównej](#RootDefinitionName)**.

> [!NOTE]
> Alternatywnie możesz użyć punktów integracji ER do filtrowania formatów ER. Aby uzyskać więcej informacji, zobacz [API, aby wyświetlić wyszukiwanie mapowania formatu](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a>Dodawanie klasy dostawcy danych

Dodaj nową klasę **QuestionnairesErReportDP** do projektu programu Microsoft Visual Studio i napisz kod wprowadzający dostawcę danych, który powinien być używany do uruchamiania skonfigurowanego formatu ER. Podany kod zawiera tylko umowę dotyczącą danych dla tego dostawcy danych.

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a>Dodaj plik etykiet

Dodaj nowy plik etykiet **QuestionnairesErReportLabels\_en-US** do projektu Visual Studio, a następnie określ następujące etykiety dla nowych zasobów interfejsu użytkownika:

- Etykieta **\@QuestionnairesReport** dla nowego elementu menu, zawierająca następujący tekst w amerykańskiej odmianie języka angielskiego (en-US): **Raport z kwestionariuszy (zasilany przez ER)**
- Etykieta **\@QuestionnairesReportBatchJobDescription** dla stanowiska wsadowego, jeśli wybrany format ER jest zaplanowany do wykonania jako zadanie wsadowe

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a>Dodawanie klasy usługi raportowania

Dodaj nową klasę **QuestionnairesErReportService** do projektu Visual Studio i wpisz kod wywołujący format ER, identyfikując go za pomocą identyfikatora mapowania formatu i dostarcza kontrakt danych jako parametr.

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

Jeśli musisz użyć formatu ER, który uruchamia dane aplikacji, musisz skonfigurować źródło danych typu **Model danych** w mapowaniu formatu. To źródło danych odwołuje się do określonej części określonego modelu danych za pomocą jednej definicji głównej. Po uruchomieniu formatu ER, wywołuje to źródło danych w celu uzyskania dostępu do odpowiedniego mapowania modelu ER skonfigurowanego dla danego modelu i definicji katalogu głównego.

Wszystkie informacje, które można przygotować w kodzie źródłowym i przechowywać w ramach kontraktu danych, można przekazać do działającego formatu ER przy użyciu mapowania modelu ER tego typu. W mapowaniu modelu ER należy skonfigurować źródło danych typu **Obiektu**, który odwołuje się do klasy **[QuestionnairesErReportContract](#DataContractClass)**. Informacje, które można przygotować w kodzie źródłowym i dane w ramach kontraktu, można do działającego formatu ER przy użyciu mapowania modelu ER tego typu. W podanym kodzie to źródło danych określone przez stałą **ERModelDataSourceName**, która ma wartość **[modelu](#ModelDSName)**. Aby określić, które źródło danych jest używane do ujawnienia kontraktu danych w mapowaniu modeli, należy określić nazwę źródła danych. W podanym kodzie ta nazwa jest określona przez stałą **ParametersDataSourceName**, która ma wartość <a name="DataContractDSName"></a>**RunTimeParameters**.

> [!NOTE]
> W nowym środowisku może być konieczne odświeżenie metadanych ER, aby ten typ klasy był dostępny w projektancie mapowania modelu ER. Aby uzyskać więcej informacji, zobacz [Konfigurowanie struktury ER](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a>Dodawanie klasy kontrolera raportowania

Dodaj nową klasę **QuestionnairesErReportController** do projektu Visual Studio i wpisz kod uruchamiający format ER w trybie synchronicznym lub wsadowym, w zależności od preferowanego sposobu w oknie dialogowym, które jest oparte na logice dostarczonej klasy **QuestionnairesErReportUIBuilder**.

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a>Dodaj element menu

Dodaj nowy element menu **QuestionnairesErReport** do projektu Visual Studio. We właściwości **Obiektu** ten element menu odwołuje się do klasy **QuestionnairesErReportController** i jest używany do określania uprawnień użytkownika do wybierania i uruchamiania formatu ER. We właściwości **Etykieta** ten element menu odwołuje się do etykiety **\@QuestionnairesReport** utworzonej wcześniej, dzięki czemu w interfejsie aplikacji jest wyświetlany poprawny tekst.

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a>Dodawanie elementu menu do menu

Dodaj istniejące menu **KM** do projektu Visual Studio. Do tego menu należy dodać nowy element **QuestionnairesErReport** typu **Dane wyjściowe**. Ten element musi odwoływać się do elementu menu **QuestionnairesErReport** opisanego w poprzedniej sekcji.

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a>Budowanie projektu Visual Studio

Umożliwia utworzenie projektu w celu udostępnienia nowego elementu menu użytkownikom.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a>Umożliwia uruchomienie formatu z aplikacji

1. Przejdź do **Kwestionariusz** \> **Projektowanie** \> **Raport z kwestionariuszy (zasilany przez ER)**.

    ![Wybranie elementu menu Raport z kwestionariuszy (zasilany przez ER) w module kwestionariusza w celu uruchomienia skonfigurowanego formatu ER](./media/er-quick-start1-application-menu-modified.png)

2. W oknie dialogowym w polu **Mapowanie formatu** wybierz opcję **Raport kwestionariuszy**.
3. Kliknij przycisk **OK**.
4. W oknie dialogowym **Parametry raportu elektronicznego**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.
5. Wybierz przycisk **OK**, aby filtrować opcje.
6. Wybierz przycisk **OK**, aby uruchomić raport.

    ![Określenie kryteriów wyboru w oknie dialogowym Raport elektroniczny](./media/er-quick-start1-report-run-dialog-page.png)

7. Przejrzyj wygenerowany raport.

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a>Dostrajanie zaprojektowanego rozwiązania ER

Skonfigurowane rozwiązanie ER można zmodyfikować tak, aby korzystało z utworzonej przez siebie klasy dostawcy danych w celu uzyskania dostępu do szczegółów działającego formatu ER i wprowadzało nazwę tego formatu ER w wygenerowanym raporcie.

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a>Modyfikowanie mapowania modelu

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a>Dodaj źródła danych, aby uzyskać dostęp do obiektu kontraktu danych

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Mapowanie kwestionariusza**.
3. Wybierz opcję **Projektant**, aby otworzyć stronę **Modelowanie do mapowania źródła danych**.
4. Wybierz opcję **Projektant**, aby otworzyć wybrane mapowanie w konstruktorze mapowania modeli.
5. Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Objekt**.
6. W okienku **Źródła danych** wybierz **Dodaj źródło**.
7. W oknie dialogowym w polu **Nazwa** wprowadź **[RunTimeParameters](#DataContractDSName)**, zgodnie z definicją w kodzie źródłowym klasy **QuestionnairesErReportService**.
8. W polu **Klasa** wprowadź **[QuestionnairesErReportContract](#DataContractClass)**, który został wcześniej zakodowany.
9. Kliknij przycisk **OK**.
10. Rozwiń **RunTimeParameters**.

Dodane źródło danych zawiera informacje o identyfikatorze rekordu działającego mapowania formatu ER.

![Dodano źródło danych w konstruktorze mapowania modelu ER](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a>Dodaj źródło danych, aby uzyskać dostęp do rekordów mapowania formatu ER

Kontynuuj edycję wybranego mapowania modelu, dodając źródło danych w celu uzyskania dostępu do rekordów mapowania formatu ER.

1. Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Rekordy tabeli**.
2. W okienku **Źródła danych** wybierz **Dodaj źródło**.
3. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **ER1**.
4. W polu **Tabela** wprowadź **ERFormatMappingTable**.
5. Kliknij przycisk **OK**.

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a>Dodaj źródło danych, aby uzyskać dostęp do rekordu mapowania formatu działającego formatu ER

Kontynuuj edycję wybranego mapowania modelu, dodając źródło danych, aby uzyskać dostęp do rekordu mapowania formatu działającego formatu ER.

1. Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.
2. W okienku **Źródła danych** wybierz **Dodaj źródło**.
3. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **ER2**.
4. Wybierz opcję **Edytuj formułę**.
5. W edytorze formuł w polu **Formuła** wprowadź **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.
6. Wybierz przycisk **Zapisz** i zamknij edytor formuł.
7. Kliknij przycisk **OK**.

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a>Umożliwia wprowadzenie nazwy uruchomionego formatu ER w modelu danych

Kontynuuj edytowanie wybranego mapowania modelu, tak aby nazwa uruchomionego formatu ER była wprowadzana w modelu danych.

1. Na stronie **Projektant mapowania modelu** w okienku **Model danych** rozwiń **ExecutionContext**, a następnie wybierz **ExecutionContext\\FormatName**.
2. W okienku **Model danych** wybierz opcję **Edytuj**, aby skonfigurować powiązanie danych dla pola wybranego modelu danych.
3. W edytorze formuł w polu **Formuła** wprowadź **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.
4. Wybierz przycisk **Zapisz** i zamknij edytor formuł.

Ponieważ użyto pola **FormatName**, skonfigurowane mapowanie modelu ujawnia teraz nazwę formatu ER, który wywołuje to mapowanie modelu podczas wykonywania.

![Powiązanie pola modelu danych z metodą dodanego źródła danych w projektancie mapowania modelu ER](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a>Umożliwia zakończenie projektu mapowania modelu

1. Na stronie **Projektant mapowania modelu** wybierz opcję **Zapisz**.
2. Zamknij stronę.
3. Zamknij stronę mapowania modelu.
4. Na stronie **Konfiguracje** w drzewie konfiguracji upewnij się, że wybrana została konfiguracja **Mapowania kwestionariusza**. Następnie na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.
5. Wybierz **Zmień status** \> **Zakończone**.

Stan wersja 1.2 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**. Wersja 1.2 nie może być już zmieniana. Ta wersja zawiera skonfigurowany model mapowania i może być używana jako podstawa dla innych konfiguracji ER. Wersja 1.3 tej konfiguracji jest utworzona i ma stan **Wersja robocza**. Tę wersję można edytować, aby skorygować model mapowania **Kwestionariusza**.

### <a name="modify-a-format"></a><a name="ModifyFormat"></a>Modyfikowanie formatu

Skonfigurowany format ER można zmodyfikować, tak aby jego nazwa była wyświetlana w stopce raportu generowanego po uruchomieniu formatu ER.

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a>Dodaj nowy element formatu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Raport kwestionariusza**.
3. Wybierz opcję **Konstruktor**.
4. Na stronie **Projektant formatów** wybierz element główny **Raport**.
5. Wybierz przycisk **Dodaj**, aby dodać nowy element formatu zagnieżdżonego dla wybranego elementu głównego **Raportu**.
6. Wybierz **Excel\\Stopka**.
7. W polu **Nazwa** wprowadź nazwę **Stopka**.
8. Wybierz opcję **Raport\Stopka**, a następnie wybierz **Dodaj**.
9. Wybierz **Tekst\\Ciąg**.

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a>Powiąż dodany element formatu

1. Na stronie **Projektant formatów** na karcie **Mapowanie** w drzewie formatu dla aktywnego elementu **Stopka\\Ciąg** wybierz **Edytuj formułę**.
2. W edytorze formuł, w polu **Formuła** wprowadź **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.
3. Wybierz przycisk **Zapisz** i zamknij edytor formuł.
4. Wybierz opcję **Zapisz**.

Skonfigurowany format został zmodyfikowany, tak aby jego nazwa była wprowadzana do stopki wygenerowanego raportu przy użyciu elementu **Stopka\\Ciąg**.

![Dodanie elementu formatu Footer do skonfigurowanego formatu w projektancie operacji ER](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a>Zakończ projektowanie formatu

1. Zamknij stronę **Projektowanie formuły**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji upewnij się, że wybrana została konfiguracja **Raport kwestionariusza**. Następnie na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.
3. Wybierz **Zmień status** \> **Zakończone**.

Stan wersja 1.2 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**. Wersja 1.2 nie może być już zmieniana. Ta wersja zawiera skonfigurowany format i może być używana jako podstawa dla innych konfiguracji ER. Wersja 1.3 tej konfiguracji jest utworzona i ma stan **Wersja robocza**. Tę wersję można edytować, aby skorygować raport **Kwestionariusza**.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a>Umożliwia uruchomienie formatu z aplikacji

1. Przejdź do **Kwestionariusz** \> **Projektowanie** \> **Raport z kwestionariuszy (zasilany przez ER)**.
2. W oknie dialogowym w polu **Mapowanie formatu** wybierz opcję **Raport kwestionariuszy**.
3. Kliknij przycisk **OK**.
4. W oknie dialogowym **Parametry ER**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.
5. Wybierz przycisk **OK**, aby filtrować opcje.
6. Wybierz przycisk **OK**, aby uruchomić raport.
7. Przejrzyj wygenerowany raport w formacie Excel.

Należy zauważyć, że stopka wygenerowanego raportu zawiera nazwę formatu ER użytego do jego wygenerowania.

![Wygenerowany raport w formacie Excel](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a>Uruchamianie formatu od ER

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Raport kwestionariusza**.
3. W okienku akcji wybierz opcję **Uruchom**.
4. W oknie dialogowym **Parametry raportu elektronicznego**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.
5. Wybierz przycisk **OK**, aby filtrować opcje.
6. Wybierz przycisk **OK**, aby uruchomić raport.
7. Przejrzyj wygenerowany raport w formacie Excel.

Zwróć uwagę, że stopka wygenerowanego raportu nie zawiera nazwy formatu ER, który został użyty do jego wygenerowania, ponieważ obiekt kontraktu danych nie został przekazany do uruchomionego mapowania modelu, gdy został wywołany przez format ER, który został uruchomiony z ER.

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a>Skonfiguruj miejsce docelowe formatu dla podglądu na ekranie

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Aplikacja docelowa raportowania elektronicznego**.
2. Na stronie **Aplikacja docelowa raportowania elektronicznego** dodaj rekord docelowy dla skonfigurowanego formatu ER **Raport kwestionariusza**.
3. Na skróconej karcie **Lokalizacji docelowej pliku** skonfiguruj **Ekran**, czyli [miejsce docelowe](er-destination-type-screen.md), dla składnika formatu **Raportu**, który został [dodany](#AddFormatRootElement) jako element główny skonfigurowanego formatu ER **Raportu kwestionariusza**.
4. Na skróconej karcie **Ustawienia konwersji PDF** skonfiguruj lokalizację docelową w celu przekonwertowania raportu na [format PDF](electronic-reporting-destinations.md#OutputConversionToPDF), w którym jest używana **Pozioma** orientacja strony.

![Konfigurowanie niestandardowego miejsca docelowego ekranu dla formatu ER na stronie docelowej raportowania elektronicznego](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a>Umożliwia uruchomienie formatu z aplikacji w celu wyświetlenia podglądu go jako dokumentu PDF

1. Przejdź do **Kwestionariusz** \> **Projektowanie** \> **Raport z kwestionariuszy (zasilany przez ER)**.
2. W oknie dialogowym w polu **Mapowanie formatu** wybierz opcję **Raport kwestionariuszy**.
3. Kliknij przycisk **OK**.
4. W oknie dialogowym **Parametry raportu elektronicznego**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.
5. Wybierz przycisk **OK**, aby filtrować opcje.

    Na skróconej karcie **Miejsca docelowe** zwróć uwagę, że pole **Dane wyjściowe** jest ustawione na **Ekran**. Jeśli chcesz zmienić skonfigurowany cel, wybierz opcję **Zmień**.

    ![Okno dialogowe środowiska wykonawczego raportu ER, w którym można zmienić skonfigurowane miejsce docelowe](./media/er-quick-start1-run-settings.png)

6. Wybierz przycisk **OK**, aby uruchomić raport.
7. Przejrzyj wygenerowany raport w formacie PDF.

    ![Podgląd wygenerowanego raportu w formacie PDF na ekranie](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Język formuł raportowania elektronicznego](er-formula-language.md)
- [Projektowanie raportów wielojęzycznych](er-design-multilingual-reports.md)
- [Interfejs API struktury modułu Raportowanie elektroniczne](er-apis-app73.md)
- [Funkcja CASE](er-functions-logical-case.md)
- [Funkcja CONCATENATE](er-functions-text-concatenate.md)
- [Funkcja DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [Funkcja FILTER](er-functions-list-filter.md)
- [Funkcja FIRSTORNULL](er-functions-list-firstornull.md)
- [Funkcja FORMAT](er-functions-text-format.md)
- [Funkcja IF](er-functions-logical-if.md)
- [Funkcja ORDERBY](er-functions-list-orderby.md)
- [Funkcja SESSIONNOW](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]