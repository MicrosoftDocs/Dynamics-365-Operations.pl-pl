---
title: Konfigurowanie alternatywnego przepływu danych dla rekomendacji
description: W tym artykule opisano sposób konfigurowania środowiska przy użyciu alternatywnego przepływu danych w celu zapewnienia danych do usługi rekomendacji.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: b507b9bb57c68aca9424b53f8ccc009efea733bc
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460167"
---
# <a name="set-up-an-alternate-dataflow-for-recommendations"></a>Konfigurowanie alternatywnego przepływu danych dla rekomendacji

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób konfigurowania środowiska przy użyciu alternatywnego przepływu danych w celu zapewnienia danych do usługi rekomendacji.

## <a name="comparison-of-out-of-the-box-dataflow-with-alternate-dataflow"></a>Porównanie gotowego przepływu danych z alternatywnym przepływem danych

Na poniższej ilustracji przedstawiono gotowy przepływ danych w środowisku.

![Gotowy przepływ danych w środowisku](media/reco-out-of-the-box-dataflow-2.png)

Na poniższej ilustracji przedstawiono alternatywny przepływ danych, w którym zadanie wsadowe synchronizacji jednostki jest zastępowane alternatywnymi krokami przepływu danych.

![Alternatywny przepływ danych w środowisku](media/reco-alternate-dataflow-2.png)

## <a name="assumptions"></a>Założenia

- W tym artykule założono, że włączono już usługę rekomendacji dla tego środowiska. Aby uzyskać więcej informacji, zobacz [Włącz rekomendacje produktów](enable-product-recommendations.md).
- Podczas pracy z plikami i folderami na koncie magazynu Microsoft Azure Data Lake Storage:

    - Możesz użyć interfejsu portalu sieci web Azure lub aplikacji Azure Storage Explorer.
    - Punkty początkowe pracy z plikami i folderami należą do kontenera **dynamics365-financeandoperations** znajdującego się w folderze o nazwie zgodnej z adresem URL środowiska.
    - Jeśli nazwa środowiska piaskownicy to **MyUAT**, podstawowy adres URL środowiska to `myuat.sandbox.operations.dynamics.com`.
    - Jeśli do tego samego konta magazynu jest podłączone więcej niż jedno środowisko, każde środowisko będzie mieć własny folder główny.

## <a name="prerequisites"></a>Wymagania wstępne

Muszą być spełnione następujące warunki wstępne przed wdrożeniem alternatywnego przepływu pracy.

### <a name="set-up-microsoft-power-platform"></a>Konfigurowanie Microsoft Power Platform

Aby skonfigurować Microsoft Power Platform, postępuj zgodnie z instrukcjami w artykule [ Włącz integrację Microsoft Power Platform](../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

### <a name="install-the-export-to-data-lake-add-in"></a>Instalowanie dodatku Eksportowanie do usługi Data Lake

Aby zainstalować dodatek Eksportowanie do danych Data Lake, postępuj zgodnie z instrukcjami w artykule [Instalowanie dodatku Eksportowanie do usługi Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

> [!NOTE]
> Należy pamiętać o wartościach konfiguracji, ponieważ będą one potrzebne w niektórych poniższych krokach.

### <a name="configure-tables-to-export-in-dynamics-365"></a>Konfigurowanie tabel do eksportu w usłudze Dynamics 365

Synchronizacją tabel z usługi Dynamics 365 do Azure Data Lake Storage można zarządzać na stronie **Eksportuj do danych Data Lake**. Ponieważ na tej stronie nie ma obecnie elementu menu, mogą ją otworzyć tylko użytkownicy z rolą zabezpieczeń **Administrator systemu**.

Aby skonfigurować tabele do eksportu do systemu Dynamics 365, należy wykonać następujące kroki.

1. Aby otworzyć stronę **Eksportuj do danych Data Lake**, dodaj ciąg `?mi=DataFeedsDefinitionWorkspace` do podstawowego adresu URL środowiska, tak jak pokazano w poniższym przykładzie:

    `https://<environment-URL>/?mi=DataFeedsDefinitionWorkspace`

1. Na stronie **Eksport do danych Data Lake** skopiuj tabele wymienione w sekcji [ listy tabel modułów RetailSales](#list-of-retailsales-cube-tables) tego artykułu.
1. W kolumnie **Nazwa systemu** rozwiń listę opcji filtru.
1. Dla typu filtru wybierz **jest jedną z**. Następnie umieść kursor w polu tekstowym i wklej listę tabel skopiowanych ze strony **Eksportuj do danych Data Lake**.
1. W dolnej części listy opcji filtru wybierz pozycję **Zastosuj**.
1. Zaznacz wszystkie wiersze w siatce, a następnie **Aktywuj**.

> [!NOTE]
> Przed przejściem do następnego kroku wszystkie wiersze muszą zostać zaktualizowane do stanu **Uruchomione**. W razie potrzeby rozwiąż wszystkie ewentualne błędy.

### <a name="create-a-synapse-workspace"></a>Utwórz obszar roboczy Synapse

Aby utworzyć obszar roboczy Synapse, jeśli jeszcze go jeszcze nie masz, postępuj zgodnie z instrukcjami wyświetlanymi w obszarze roboczym [Szybki start: tworzenie obszaru roboczego Synapse](/azure/synapse-analytics/quickstart-create-workspace)

Aby zachować organizację zasobów systemu Azure, zaleca się, aby w systemie Azure w grupie zasobów umieścić razem konta magazynu danych Data Lake Storage i obszaru roboczego Synapse. Można ponownie użyć konta magazynu utworzonego podczas instalacji dodatku Eksportuj do danych Data Lake.

## <a name="create-a-database-in-synapse-for-recommendation-data-processing"></a>Utwórz bazę danych w Synapse w celu przetworzenia danych rekomendacji

Użyj aplikacji konsoli narzędzia Common Data Model (CDMUtil_ConsoleApp), aby utworzyć bazę danych w obszarze roboczym Synapse i wypełnić ją z tabel Common Data Model w magazynie danych Data Lake Storage. Zaleca się, aby w środowisku dewelopera używać narzędzia Common Data Model z bazą danych w przypadku jakichkolwiek rozszerzeń.

> [!NOTE]
> W poniższych krokach założono, że do modułu RetailSales nie są dodawane dane rozszerzenia.

Aby utworzyć bazę danych w Synapse, wykonaj poniższe kroki.

1. Przejdź do strony [GitHub Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Analytics/CDMUtilSolution#2-cdmutil-console-app) i wykonaj następujące kroki, aby pobrać plik **CDMUtilConsoleApp.zip**.
1. Wyodrębnij plik ZIP do folderu lokalnego.
1. Otwórz plik **CDMUtil_ConsoleApp.dll.config** w edytorze tekstu i zaktualizuj następujące wartości:

    1. Ustaw wartość **Identyfikator dzierżawcy** (identyfikator dzierżawcy platformy Azure).
    1. Ustaw wartość **Klucz dostępu** (klucz dostępu dla konta magazynu Data Lake Storage).

        1. W portalu Azure otwórz konto magazynu.
        1. W menu po lewej stronie strony wybierz **Klucze dostępu**.
        1. Wybierz **Pokaż klucze** u góry strony.
        1. Wybierz przycisk kopiowania dla jednego z dwóch pól klucza, a następnie wklej wartość między dwoma cudzysłowami w pliku konfiguracji.

    1. Ustaw wartość **ManifestURL** jako adres URL pliku **Tables.manifest.cdm.json** w programie Azure Data Lake Storage. Aby uzyskać adres URL, przejdź do pliku w portalu Azure Portal, wybierz wielokropek (**...**) po prawej stronie widoku, a następnie wybierz opcję **Właściwości**. Adres URL jest pierwszą właściwością wyświetlaną na karcie **Przegląd**.
    1. Ustaw wartość **TargetDbConnectionString** na ciąg połączenia dla wbudowanej nieserwerowej puli SQL obszaru roboczego Synapse.

        1. W obszarze roboczym Synapse wybierz kartę **Zarządzaj**.
        1. Z podmenu wybierz **Pule SQL**.
        1. Wybierz nazwę **Wbudowane**, aby wyświetlić właściwości puli.
        1. W oknie dialogowym właściwości wybierz typ połączenia ADO.NET, którego chcesz użyć. Następnie skopiuj wartość ciągu połączenia i wklej ją między dwoma cudzysłowami w pliku konfiguracji.

        > [!NOTE]
        > Musisz mieć uprawnienia do tworzenia baz danych. Dla ułatwienia użycia może być konieczne użycie wbudowanego konta administratora **sqladminuser**.

    1. Usuń komentarz z węzła **ProcessEntities** i ustaw dla jego wartości wartość na **true** (na przykład `<add key="ProcessEntities" value ="true"/>`).

1. Zapisz i zamknij plik **CDMUtil_ConsoleApp.dll.config**.
1. Skopiuj plik **EntityList.json** do katalogu **/Manifest**.
1. W oknie wiersza polecenia uruchom program **cdmutil_consoleapp.exe**.

> [!NOTE]
> Podczas przeglądania danych wyjściowych powinno być 35 jednostek/widoków, co najmniej 75 tabel i nie powinno być błędów.

## <a name="prepare-the-data-lake-retailsales-aggregate-measurements-directory"></a>Przygotowywanie katalogu miar agregacji RetailSales bazy Data Lake

### <a name="back-up-your-current-retailsales-cube-data-from-data-lake-storage"></a>Zrób kopię zapasową bieżących danych modułu RetailSales z magazynu Data Lake Storage

Najprostszy sposób tworzenia kopii zapasowej bieżących danych modułu RetailSales to zmiana nazwy katalogu **RetailSales** w magazynie Data Lake Storage na **RetailSales-backup** lub podobną. Ta metoda zachowuje istniejące dane, jeśli później będzie wymagane rozwiązywanie problemów.

Folder modułu **/RetailSales** znajduje się w następującej lokalizacji:

`<storage-account>/dynamics365-financeandoperations/<environment-url (for example, myuat.sandbox.operations.dynamics.com)>/AggregateMeasurements/RetailSales`

### <a name="create-a-new-retailsales-folder-and-upload-the-model-file"></a>Utwórz nowy folder RetailSales i przekaż plik modelu

Aby utworzyć nowy katalog **RetailSales** i przekazać plik **model.json** do magazynu Data Lake Storage, wykonaj następujące kroki.

1. Utwórz nowy pusty katalog na poziomie poprzedniego katalogu i nadaj nazwę **RetailSales**.
1. Przekaż plik **model.json** do nowego katalogu.

## <a name="create-a-pipeline-to-copy-the-retailsales-cube-data"></a>Tworzenie potoku w celu skopiowania danych modułu RetailSales

Potok odczyta widoki modułów RetailSales i wyeksportuje dane do plików CSV w magazynie Data Lake Storage.

Aby utworzyć potok w celu skopiowania danych modułu RetailSales, wykonaj poniższe kroki.

1. W obszarze roboczym Synapse wybierz kartę **Integruj**.
1. Wybierz znak plusa (**+**), a następnie **Importuj z szablonu potoku**.
1. Pobierz, a następnie wybierz [plik ExportRetailSalesCubeViews.zip](https://aka.ms/reco-alternate-dataflow-files).
1. Wybierz połączoną usługę z bazą danych SQL.
1. Wybierz połączoną usługę konta magazynu.
1. Otwórz narzędzie **Kopiuj dane** i zmień wartość właściwości **Ścieżki folderu** na **\<environment_name\>/...**.

### <a name="test-execution-of-the-pipeline"></a>Wykonanie testu potoku

Zaleca się przetestowanie potoku za pomocą tylko jednego widoku. Widok **RetailSales_RetailMediaTemplateView** działa dobrze, ponieważ zawiera zwykle mniej niż 10 wierszy.

## <a name="schedule-the-pipeline-to-run-on-a-recurring-schedule"></a>Planowanie potoku do uruchomienia zgodnie z harmonogramem cyklicznym

Po każdym uruchomienia potoku ma miejsce zużycie systemu Azure. Zaleca się zaplanowanie wykonań co 48 godzin lub dłużej. Zawsze można uruchomić potok ręcznie, jeśli trzeba natychmiast zsynchronizować dane. 
 
## <a name="table-list-for-synchronization-from-dynamics-365-to-data-lake-storage"></a>Lista tabel do synchronizacji z usługi Dynamics 365 do magazynu Data Lake Storage

Następująca lista tabel jest podzestawem wszystkich tabel wymaganych dla całego modułu RetailSales. Usługa rekomendacji używa tylko 15 widoków w module RetailSales i lista wymaganych tabel została odpowiednio przefiltrowana.

### <a name="list-of-retailsales-cube-tables"></a>Lista tabel modułów RetailSales

- BICalendarOffsets
- BIDateDimension
- BIDateDimensionValue
- Wykaz
- CatalogProduct
- CatalogProductCategory
- CustInvoiceJour
- CustInvoiceTrans
- CustTable
- DataArea
- DimensionAttributeValueCombination
- DimensionAttributeValueSet
- DirPartyTable
- EcoResCategory
- EcoResCategoryHierarchy
- EcoResCategoryHierarchyRole
- EcoResColor
- EcoResConfiguration
- EcoResProduct
- EcoResProductCategory
- EcoResProductTranslation
- EcoResSize
- EcoResStyle
- HcmWorker
- InventDim
- InventDimCombination
- InventItemGroup
- InventItemGroupItem
- InventItemSetupSupplyType
- InventTable
- InventTrans
- LogisticsAddressCountryRegion
- LogisticsAddressCountryRegionTranslation
- LogisticsLocation
- LogisticsPostalAddress
- OMHIERARCHYPURPOSE
- RetailAssortmentLookup
- RetailAssortmentLookupChannelGroup
- RetailChannelProfile
- RetailChannelProfileProperty
- RetailChannelTable
- RetailChannelTableExt
- RetailConnDatabaseProfile
- RetailCustInvoiceJourTable
- RetailCustTable
- RetailMediaTemplate
- RetailOfflineProfile
- RetailPeriodicDiscount
- RetailRecoListConfigurationParameters
- RetailSalesTaxOverrideGroup
- RetailSharedParameters
- RetailSpecialCategoryMember
- RetailTenderTypeCardTable
- RetailTenderTypeTable
- RetailTerminalTable
- RetailTmpProductMedia
- RetailTransactionDiscountTrans
- RetailTransactionPaymentTrans
- RetailTransactionPaymentTransExt
- RetailTransactionSalesTrans
- RetailTransactionSalesTransExt
- RetailTransactionTable
- SalesLine
- SalesTable
- SystemParameters
- RETAILCATALOGINTERNALORG
- RETAILGROUPMEMBERLINE
- RETAILINTERNALORGANIZATION
- RETAILSPECIALCATEGORYPRODUCT
- RETAILPRODUCTCATEGORY
- ECORESCONFIGURATION
- DIMENSIONATTRIBUTE
- DIMENSIONATTRIBUTEVALUESET
- DIMENSIONHIERARCHY
- DIMENSIONHIERARCHYINTEGRATION
- DIMENSIONHIERARCHYLEVEL
- DIMENSIONPARAMETER
- OMExplodedOrganizationSecurityGraph

### <a name="view-list-for-the-parameter-to-pass-to-the-synapse-pipeline"></a>Wyświetl listę parametrów, która ma być przeniesiona do potoku Synapse

Na poniższej liście rozdzielonej przecinkami znajdują się widoki modułu RetailSales, w których potok wykona operację „wybierz”. Spowoduje to skopiowanie wyników do magazynu Data Lake Storage.

RetailSales_RetailAssortmentRulesView,RetailSales_RetailChannelNavigationHierarchiesView,RetailSales_RetailChannelNavigationHierarchyCatalogProductsView,RetailSales_RetailChannelNavigationHierarchyCategoryNodesView,RetailSales_RetailChannelNavigationHierarchyCategoryProductsView,RetailSales_RetailMediaBaseUrlChannelView,RetailSales_RetailMediaRelativeUrlProductView,RetailSales_RetailMediaTemplateView,RetailSales_RetailOptOutCustomersView,RetailSales_RetailProductCategory,RetailSales_RetailProductTransaction,RetailSales_RetailProductVariantDimensionsView,RetailSales_RetailRecoListConfigurationParametersView,RetailSales_RetailRecoListsSharedParametersView,RetailSales_RetailEcoResProductTranslation

> [!IMPORTANT]
> Parametr potoku musi być listą nazw widoków, które są rozdzielane pojedynczymi przecinkami. Nie może być spacji ani znaków nowego wiersza.

## <a name="environment-specific-fixes"></a>Poprawki specyficzne dla środowiska

### <a name="retailchannelview-fix"></a>Poprawka RETAILCHANNELVIEW

Widok **RETAILCHANNELVIEW** zawiera stałą zakodowaną liczbą całkowitą, która reprezentuje organizację typu „kanał sprzedaży detalicznej”. Rzeczywista wartość typu może być różna między środowiskami lub dzierżawami.

```SQL
CREATE OR ALTER   VIEW [dbo].[RETAILCHANNELVIEW]
AS
SELECT T1.RECID AS RECID1,
       T1.STOREAREA AS STOREAREA,
       T1.OMOPERATINGUNITID AS OMOPERATINGUNITID,
       T1.DEFAULTCUSTACCOUNT AS DEFAULTCUSTOMER,
       T1.RETAILCHANNELID AS RETAILCHANNELID,
       T1.CHANNELTYPE AS CHANNELTYPE,
       T1.PARTITION AS PARTITION,
       T1.RECID AS RECID,
       T2.OMOPERATINGUNITNUMBER AS OMOPERATINGUNITNUMBER,
       T3.NAME AS NAME
FROM   dbo.RETAILCHANNELTABLE AS T1 CROSS JOIN dbo.DIRPARTYTABLE AS T2 CROSS JOIN dbo.DIRPARTYTABLE AS T3
WHERE  ((((T1.OMOPERATINGUNITID = T2.RECID)
          )
         AND ((T2.RECID = T3.RECID)
              ))
        AND T2.INSTANCERELATIONTYPE IN (8363));
```

Aby zaktualizować zakodowane stałe liczby całkowite, wykonaj następujące czynności.

1. W Dynamics 365 odszukaj wartość **ChannelID** kanału online.
1. W wystąpieniu programu SQL Server Management Studio (SSMS) dołączonego do bazy danych Synapse uruchom następujące zapytanie.

    ```SQL
    select INSTANCERELATIONTYPE, NAME, NAMEALIAS, * from dbo.DIRPARTYTABLE where RECID IN (select OMOPERATINGUNITID from dbo.RETAILCHANNELTABLE where RETAILCHANNELID =     <channelID>)
    ```

1. Skopiuj wartość z pierwszej kolumny (**INSTANCERELATIONTYPE**) i wklej ją do definicji widoku.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="pipeline-task-fails"></a>Zadanie potoku zakończyło się niepowodzeniem

Powinno być 15 wykonywań zadań potoku dla zadania **CopyData**. Jeśli wykonanie nie powiedzie się, należy sprawdzić, czy istnieją wszystkie zależne obiekty SQL i czy zapytania są uruchamiane. Najprostszy sposób uzyskania dostępu do wszystkich zależności to użycie SSMS do nawiązania połączenia z bazą danych. Następnie można wybrać i przytrzymać (lub kliknąć prawym przyciskiem myszy) widok i wybrać polecenie **Generuj UTWÓRZ, tak aby nowe okno było nowe**.

Komunikat o błędzie może zawierać następujący tekst:

- Błąd: wystąpił błąd po stronie „Źródło”
- Błąd podczas obsługi pliku zewnętrznego: „Maksymalna liczba błędów”.
- /RetailSales/RetailSales_xxxxxx

#### <a name="example-scenario"></a>Przykładowy scenariusz

W tym przykładzie zadanie **RetailSales_RetailProductCategory** nie powiedzie się i zostanie wyświetlony komunikat o błędzie „Maksymalna liczba błędów”.

Aby debudować ten błąd wykonaj poniższe kroki.

1. Otwórz plik **EntityList.json** w edytorze tekstów (na przykład Visual Studio Code).
1. Znajdź definicję widoku dla **RetailSales_RetailProductCategory**.

    ```SQL
    CREATE  VIEW [dbo].[RetailSales_RetailProductCategory] AS SELECT 0 AS ROW_UNIQUEKEY ,CATEGORY AS CATEGORYID ,PRODUCT AS PRODUCTID ,PRODUCTNAME ,CATEGORYNAME     ,PARENTCATEGORY AS PARENTCATEGORYID ,PARTITION ,RECID FROM RetailProductCategoryView
    ```

1. Ten widok zależy tylko od jednego widoku: **RetailProductCategoryView** _. Znajdź definicję widoku dla _*RetailProductCategoryView**.

    ```SQL
    CREATE VIEW [DBO].[RETAILPRODUCTCATEGORYVIEW] AS SELECT T1.CATEGORY AS CATEGORY, T1.PRODUCT AS PRODUCT, T1.PARTITION AS PARTITION, T1.RECID AS RECID, T2.PRODUCTNAME AS PRODUCTNAME, T2.PARTITION AS PARTITION#2, T3.NAME AS CATEGORYNAME, T3.PARENTCATEGORY AS PARENTCATEGORY, T3.PARTITION AS PARTITION#3 FROM RETAILPRODUCTCATEGORY T1 CROSS JOIN ECORESPRODUCTTRANSLATIONS T2 CROSS JOIN RETAILCATEGORYEXPANDED T3 WHERE((( T1.PRODUCT = T2.PRODUCT) AND ( T1.PARTITION = T2.PARTITION)) AND (( T1.CATEGORY = T3.RECID) AND ( T1.PARTITION = T3.PARTITION)))
    ```

1. Ten widok zależy od trzech innych widoków: **RETAILPRODUCTCATEGORY**, **ECORESPRODUCTTRANSLATIONS** i **RETAILCATEGORYEXPANDED**. Znajdź definicję dla każdego z tych widoków i wyświetl listę jej zależności. Kontynuuj aż do znalezienia wszystkich widoków zależnych.

    Oto cała lista w kolejności drzewa zależności. Należy zweryfikować trzynaście widoków.

    - RetailSales_RetailProductCategory

        - RetailProductCategoryView

            - RETAILPRODUCTCATEGORY

                - ECORESPRODUCTCATEGORY
                - ECORESCATEGORYHIERARCHYROLE
                - RETAILSPECIALCATEGORYPRODUCT

                    - ECORESPRODUCT
                    - RETAILGROUPMEMBERLINE
                    - RETAILSPECIALCATEGORYMEMBER

            - ECORESPRODUCTTRANSLATIONS

                - ECORESPRODUCT
                - ECORESPRODUCTTRANSLATION
                - SYSTEMPARAMETERS

            - RETAILCATEGORYEXPANDED

                - ECORESCATEGORY
                - ECORESCATEGORYHIERARCHYROLE

1. W programie Excel utwórz następujące 13 instrukcji **wybierz liczba(\*) z \<view_name\>**. Uruchom te instrukcje w programie SSMS i wyślij wyniki do tekstu. Następnie przewiń wyniki, aby sprawdzić, czy któryś z widoków nie powiódł się. Początkowy błąd wskazuje, że co najmniej jeden widok nie powiedzie się.

    ```SQL
    select count(*) from RetailProductCategoryView
    select count(*) from RETAILPRODUCTCATEGORY
    select count(*) from ECORESPRODUCTCATEGORY
    select count(*) from ECORESCATEGORYHIERARCHYROLE
    select count(*) from RETAILSPECIALCATEGORYPRODUCT
    select count(*) from ECORESPRODUCT
    select count(*) from RETAILGROUPMEMBERLINE
    select count(*) from RETAILSPECIALCATEGORYMEMBER
    select count(*) from ECORESPRODUCTTRANSLATIONS
    select count(*) from ECORESPRODUCTTRANSLATION
    select count(*) from SYSTEMPARAMETERS
    select count(*) from RETAILCATEGORYEXPANDED
    select count(*) from ECORESCATEGORY
    ```

1. Jednym ze sposobów sprawdzania poprawności jest utworzenie widoku zależnego od głównego w celu wygenerowania definicji widoku w programie SSMS. Następnie upewnij się, że istnieje kolumna pliku systemu Azure Data Lake, o nazwie **r.filepath**. Obecność tej kolumny wskazuje, że widok, który jest sprawdzany, jest odczytem danych z magazynu Data Lake Storage.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Włącz rekomendacje „Kup podobne”](shop-similar-looks.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
