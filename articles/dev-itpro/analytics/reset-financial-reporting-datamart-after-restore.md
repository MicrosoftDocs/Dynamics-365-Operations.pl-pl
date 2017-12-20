---
title: "Resetowanie składników danych aplikacji Raportowanie finansowe"
description: "W tym temacie opisano sposób resetowania składnicy danych modułu Raporty finansowe."
author: aolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: pl-pl
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a>Resetowanie składników danych aplikacji Raportowanie finansowe

[!include[banner](../includes/banner.md)]

W tym temacie objaśniono, w jaki sposób zresetować składnicę danych modułu Raporty finansowe w następujących wersjach:

- Microsoft Dynamics 365 for Finance and Operations — Raporty finansowe, wersja 7.2.6.0 lub nowsza
- Microsoft Dynamics 365 for Finance and Operations — Raporty finansowe, wersja 7.0.10000.4 lub nowsza
- Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (wersja lokalna)

Wersję 7.2.6.0 modułu Raporty finansowe oprogramowania Finance and Operations można uzyskać, pobierając plik KB 4052514 ze strony <https://support.microsoft.com/en-us/help/4052514>.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a>Resetowanie składnicy danych modułu Raporty finansowe w wersji 7.2.6.0 oprogramowania Finance and Operations lub nowszej

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a>Resetuj składnicy danych modułu Raporty finansowe z poziomu projektanta raportów

> [!NOTE]
> Kroki tej procedury dotyczą wyłącznie modułu Raporty finansowe w wersji 7.2.6.0 oprogramowania Finance and Operations lub nowszej. Jeśli masz starszą wersję, skontaktuj się z zespołem pomocy technicznej w celu uzyskania pomocy.

W określonych scenariuszach konieczne może być zresetowanie składnicy danych dla modułu Raporty finansowe. Zadanie to można wykonać za pomocą klienta z zainstalowanym projektantem raportów. Poniżej przedstawiono kilka scenariuszy, w których konieczne może być zresetowanie składnicy danych:

- Baza danych Finance and Operations została przywrócona, ale baza danych składnicy danych nie.
- Wyświetlane dane za okres są niepoprawne.
- Pomoc techniczna zaleciła zresetowanie składnicy danych w ramach procedury rozwiązywania problemów.

Składnicę danych należy resetować wyłącznie w okresach, gdy ilość przetwarzania bazy danych jest niewielka. W trakcie resetowania raporty finansowe będą niedostępne.

#### <a name="reset-the-data-mart"></a>Resetowanie składnicy danych

Aby zresetować składnicę danych, wybierz z menu **Narzędzia** w projektancie raportów opcję **Resetuj składnicę danych**. Pojawi się okno dialogowe składające się z dwóch części: **Statystyki** i **Reset**.

[![Okno dialogowe Resetowanie składnicy danych](./media/Statistics.png)](./media/Statistics.png)

##### <a name="integration-attempts"></a>Próby integracji

Siatka **Próby integracji** pokazuje, ile razy system podjął próbę integracji transakcji. Jeśli pierwsze kilka prób zakończy się niepowodzeniem, system będzie podejmował próby integracji danych w ciągu kilku dni. Składnicę danych należy zresetować, jeśli liczba prób wyniesie co najmniej 8, a także w przypadku wielu kombinacji wymiarów lub rekordów transakcji. W takiej sytuacji dane nie zostaną uwzględnione w raporcie.

##### <a name="data-status"></a>Stan danych

Siatka **Stan danych** zawiera migawkę transakcji, kursów wymiany i wartości wymiarów w składnicy danych. Duża liczba starych rekordów wskazuje na liczne ich aktualizacje. Taka sytuacja może spowodować wydłużenie czasu generowania raportów.

##### <a name="misaligned-main-account-categories"></a>Źle wyrównane kategorie konta głównego

Jeśli korzystasz z modułu Raporty finansowe w wersji starszej niż 7.2.1 oprogramowania Microsoft Dynamics 365 for Finance and Operations zresetowanie składnicy danych może być konieczne w przypadku zmiany nazw kont oraz przeniesienia kont między kategoriami kont. Te akcje mogą spowodować nieprawidłowe wyrównanie kategorii konta głównego. Pole **Źle wyrównane kategorie konta głównego** wskazuje, czy taki problem ma miejsce.

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a>Resetowanie składnicy danych modułu Raporty finansowe w wersji 7.2.6.0 oprogramowania Finance and Operations

Aby zresetować składnicę danych modułu Raporty finansowe w wersji 7.2.6.0 lub starszej oprogramowania Finance and Operations, w oknie dialogowym **Resetowanie składnicy danych** zaznacz pole wyboru **Resetuj składnicę danych**, a następnie wybierz opcję **OK**. Składnicę danych należy resetować wyłącznie w czasie zaplanowanego przestoju.

[![Pole wyboru Resetuj składnicę danych](./media/Reset-72.jpg)](./media/Reset-72.jpg)

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a>Zresetuj składnicę danych i wybierz przyczynę w module Raporty finansowe w wersji 7.3.0 oprogramowania Microsoft Dynamics 365 for Finance and Operations

W razie stwierdzenia konieczności zresetowania składnicy danych zaznacz pole wyboru **Resetuj składnicę danych**, a następnie w polu **Przyczyna** wybierz przyczynę. Dostępne są następujące opcje:

- **Dane nieprawidłowe lub ich brak** — na podstawie statystyk użytkownik stwierdził, że może brakować danych. Przed podjęciem dalszych czynności zaleca się konsultację z pomocą techniczną w celu określenia głównej przyczyny.
- **Przywróć bazę danych** — baza danych oprogramowania Finance and Operations została przywrócona, ale baza danych składnicy danych modułu Raporty finansowe – nie.
- **Inne** — resetowanie składnicy danych z innego powodu. Jeśli istnieje podejrzenie, że występuje problem, skontaktuj się z obsługą techniczną, aby go zidentyfikować.

> [!NOTE]
> Przed wykonaniem tych kroków sprawdź, czy wszystkie zadania ukończyły integrację. Stan integracji można wyświetlić, wybierając kolejno opcje **Narzędzia** &gt; **Stan integracji**.

#### <a name="clear-users-and-companies"></a>Usuń użytkowników i firmy

Jeśli baza danych została przywrócona, ale po jej przywróceniu wprowadzono zmiany w użytkownikach lub firmach, zaznacz pole wyboru **Usuń użytkowników i firmy**. Najczęściej nie ma potrzeby zaznaczania tego pola wyboru.

Aby rozpocząć proces resetowania, naciśnij przycisk **OK**. Zostanie wyświetlony monit o potwierdzenie gotowości do rozpoczęcia procesu. Należy pamiętać, że w trakcie resetowania oraz początkowej integracji danych, która nastąpi po jego zakończeniu, moduł Raporty finansowe będzie niedostępny.

Aby sprawdzić stan integracji, wybierz kolejno opcje **Narzędzia** &gt; **Stan integracji** w celu wyświetlenia czasu ostatniej integracji oraz jej stanu.

[![Wyświetlanie stanu integracji](./media/Integration.png)](./media/Integration.png)

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a>Resetowanie składnicy danych modułu Raporty finansowe w wersji 7.0.10000.4 lub nowszej oprogramowania Finance and Operations

Jeśli kiedykolwiek baza danych oprogramowania Finance and Operations będzie przywracana z kopii zapasowej lub kopii bazy danych z innego środowiska, należy wykonać kroki opisane w tej części, aby mieć pewność, że składnica danych modułu Raporty finansowe poprawnie wykorzystuje przywróconą bazę danych oprogramowania Finance and Operations.

> [!NOTE]
> Ta procedura dotyczy aplikacji Microsoft Dynamics AX w wersji 7.0.1 (maj 2016 r.) (wersja aplikacji 7.0.1265.23014 i wersja modułu Raporty finansowe 7.0.10000.4) lub nowszej. Jeśli posiadasz starszą wersję oprogramowania Finance and Operations, skontaktuj się z pomocą techniczną w celu uzyskania pomocy.

### <a name="export-report-definitions"></a>Eksportowanie definicji raportów

Najpierw wykonaj przedstawione kroki, aby wyeksportować projekty raportów z projektanta raportów.

1. W projektancie raportów wybierz kolejno opcje **Firma** &gt; **Grupy bloków konstrukcyjnych**.
2. Wybierz grupę bloków konstrukcyjnych do wyeksportowania, a następnie wybierz opcję **Eksportuj**.

    > [!NOTE]
    > W programie Finance and Operations obsługiwana jest tylko jedna grupa bloków konstrukcyjnych — **Domyślne**.

3. Wybierz definicje raportów do wyeksportowania:

    - Aby wyeksportować wszystkie istniejące definicje raportów i powiązane z nimi bloki konstrukcyjne, wybierz opcję **Zaznacz wszystko**.
    - Aby wyeksportować wybrane raporty, wiersze, kolumny, drzewa lub zestawy wymiarów, wybierz odpowiednią kartę i elementy do wyeksportowania. Naciśnij i przytrzymaj klawisz Ctrl, aby zaznaczyć kilka elementów na karcie. Po wybraniu raportów do wyeksportowania wybrane zostaną skojarzone wiersze, kolumny, drzewa i zestawy wymiarów.

4. Wybierz opcję **Eksportuj**.
5. Wprowadź nazwę pliku i wybierz bezpieczną lokalizację, w której chcesz zapisać wyeksportowane definicje raportów.
6. Wybierz opcję **Zapisz**.

Plik można skopiować lub wczytać do bezpiecznej lokalizacji. W ten sposób plik można zaimportować później do innego środowiska. Więcej informacji na temat korzystania z konta magazynu usługi Microsoft Azure, zobacz [Przenoszenie danych za pomocą narzędzia wiersza polecenia AzCopy](/azure/storage/storage-use-azcopy).

> [!NOTE]
> Firma Microsoft nie zapewnia konta magazynu w ramach umowy na usługę Finance and Operations. Należy we własnym zakresie kupić konto magazynu lub użyć konta magazynu z oddzielnej subskrypcji usługi Azure.

> [!WARNING]
> Należy pamiętać o zachowaniu dysku D na maszynach wirtualnych Azure (VM). Nie należy trwale przechowywać wyeksportowanych grup bloków konstrukcyjnych na dysku D. Aby uzyskać więcej informacji na temat dysków tymczasowych, zobacz [Opis koncepcji dysku tymczasowego na maszynach wirtualnych systemu Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

### <a name="stop-services"></a>Zatrzymywanie usług

Następujące usługi Microsoft Windows będą mieć otwarte połączenia z bazą danych programu Finance and Operations. W związku z tym należy połączyć się ze wszystkimi komputerami w środowisku za pomocą usługi pulpitu zdalnego firmy Microsoft, a następnie zatrzymać te usługi za pomocą konsoli services.msc.

- Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerami Application Object Server [AOS])
- Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)
- Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem Business Intelligence [BI])

### <a name="reset"></a>Zeruj

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a>Pobieranie najnowszego pakietu MinorVersionDataUpgrade.zip

Pobierz najnowszy pakiet MinorVersionDataUpgrade.zip. Aby dowiedzieć się, jak odnaleźć i pobrać odpowiednią wersję pakietu uaktualnienia danych, zobacz [Pobieranie najnowszego wdrażalnego pakietu uaktualniania danych](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). Uaktualnienie nie jest wymagane w celu pobrania pakietu MinorVersionDataUpgrade.zip. W związku z tym wystarczy wykonać kroki opisane w części „Pobieranie najnowszego wdrażalnego pakietu uaktualniania danych” tego tematu. Można pominąć wszystkie inne kroki opisane w tym temacie.

#### <a name="run-scripts-against-the-finance-and-operations-database"></a>Uruchamianie skryptów w bazie danych programu Finance and Operations

Uruchom następujące skrypty w bazie danych programu Finance and Operations (nie w bazie danych modułu Raporty finansowe):

- DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
- DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Te skrypty pomogą zagwarantować poprawność użytkowników, ról i ustawień śledzenia zmian.

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a>Resetowanie bazy danych za pomocą polecenia programu Windows PowerShell

Aby zresetować integrację między oprogramowaniem Finance and Operations a modułem Raporty finansowe, na komputerze z zainstalowanym serwerem AIS uruchom program Microsoft Windows PowerShell w roli administratora, a następnie uruchom podane polecenia.

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

Objaśnienie parametrów w poleceniu**Reset-DatamartIntegration**:

- Prawidłowe wartości parametru **-Reason** to **SERVICING**, **BADDATA** i **OTHER**.
- Parametr **-ReasonDetail** ma format zwykłego tekstu.
- Wartości przyczyny oraz szczegółów przyczyny zostaną zarejestrowane w funkcji telemetrii/monitorowania środowiska.

> [!NOTE]
> Po uruchomieniu polecenia wyświetli się monit o wprowadzenie **Y** w celu potwierdzenia resetu bazy danych.

#### <a name="restart-services"></a>Ponowne uruchamianie usług

Za pomocą konsoli services.msc uruchom usługi, które zostały wcześniej zatrzymane:

- Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerem AOS)
- Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)
- Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem BI)

#### <a name="import-report-definitions"></a>Importowanie definicji raportów

Zaimportuj projekty raportów z projektanta raportów, korzystając z pliku utworzonego podczas eksportu.

1. W projektancie raportów wybierz kolejno opcje **Firma** &gt; **Grupy bloków konstrukcyjnych**.
2. Wybierz grupę bloków konstrukcyjnych do wyeksportowania, a następnie wybierz opcję **Eksportuj**.

    > [!NOTE]
    > W programie Finance and Operations obsługiwana jest tylko jedna grupa bloków konstrukcyjnych — **Domyślne**.

3. Zaznacz blok konstrukcyjny **Domyślne** i wybierz opcję **Importuj**.
4. Zaznacz plik zawierający wyeksportowane definicje raportów i wybierz opcję **Otwórz**.
5. W oknie dialogowym **Import** zaznacz definicje raportów przeznaczone do zaimportowania:

    - Aby zaimportować wszystkie istniejące definicje raportów i powiązane z nimi bloki konstrukcyjne, wybierz opcję **Zaznacz wszystko**.
    - W celu zaimportowania konkretnych raportów, wierszy, kolumn, drzew lub zestawów wymiarów zaznacz te pozycje.

6. Wybierz opcję **Importuj**.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a>Resetowanie składnicy danych modułu Raporty finansowe dla oprogramowania Finance and Operations (lokalnie)

1. Poleć wszystkim użytkownikom zamknięcie projektanta raportów oraz modułu Raporty finansowe oprogramowania Finance and Operations.
2. Uruchom podany skrypt w bazie danych modułu Raporty finansowe (MRDB).

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. Przytnij lub usuń wszystkie rekordy z tabeli FINANCIALREPORTS w bazie danych oprogramowania Finance and Operations (AXDB).
4. Przytnij lub usuń wszystkie rekordy z tabeli FINANCIALREPORTVERSION w bazie danych oprogramowania Finance and Operations (jeśli taka tabela istnieje). Jeśli w bazie danych oprogramowania Finance and Operations nie ma takiej tabeli, pomiń ten krok.
5. Uruchom skrypt **ResetDatamaer.sql** w bazie danych modułu Raporty finansowe. Ten skrypt wyłącza integrację składnicy danych, powoduje usunięcie wszystkich danych ze składnicy danych, a następnie ponownie włącza integrację składnicy danych.

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. Po zresetowaniu użytkownik może ręcznie sprawdzić, czy dane zostały ponownie wczytane, uruchamiając następującą kwerendę w bazie danych modułu Raporty finansowe.

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    Sprawdź, czy we wszystkich wierszach występuje wartość **LastRunTime**, a parametr **StateType** ma wartość **5**. Ustawienie dla parametru **StateType** wartości **5** wskazuje, że dane zostały pomyślnie wczytane ponownie. Wartość **7** wskazuje stan błędu. Czasami mapa hierarchii organizacji ma taki stan przy pierwszym jej uruchomieniu. Jednak stan błędu powinien być automatycznie rozwiązywany.

