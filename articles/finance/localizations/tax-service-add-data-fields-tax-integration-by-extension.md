---
title: Dodawanie pól danych w integracji podatków przy użyciu rozszerzeń
description: W tym temacie opisano, jak używać rozszerzeń X++ w celu dodawania pól danych w integracji podatków.
author: qire
ms.date: 04/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 79b51812eac354072ebf2a0ef6fe8d39610c6385
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8649109"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a>Dodawanie pól danych w integracji podatków przy użyciu rozszerzeń

[!include [banner](../includes/banner.md)]


W tym temacie opisano, jak używać rozszerzeń X++ w celu dodawania pól danych w integracji podatków. Te pola mogą być rozszerzone na model danych podatkowych usługi podatkowej i używane do określania kodów podatków. Aby uzyskać więcej informacji, zobacz temat [Dodawanie pól danych w konfiguracjach podatków](tax-service-add-data-fields-tax-configurations.md).

## <a name="data-model"></a>Model danych

Dane w modelu danych są realizowane przez obiekty i implementowane przez klasy.

Poniżej znajduje się lista dużych objektów:

* AxClass/TaxIntegration **Document** Object
* AxClass/TaxIntegration **Line** Object
* AxClass/TaxIntegration **TaxLine** Object

Na poniższej ilustracji pokazano, w jaki sposób są one powiązane.

[![Relacja obiektów modelu danych.](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)

Obiekt **Dokumentu** może zawierać wiele obiektów **Wiersza**. Każdy obiekt zawiera metadane usługi podatków.

- `TaxIntegrationDocumentObject` zawiera metadane `originAddress`, które zawierają informacje o adresie źródłowym, oraz metadane `includingTax`, które wskazują, czy kwota wiersza zawiera podatek.
- `TaxIntegrationLineObject` ma metadane `itemId`, `quantity` i `categoryId`.

> [!NOTE]
> `TaxIntegrationLineObject` implementuje również obiekty **Opłat**.

## <a name="integration-flow"></a>Przepływ integracji

Działaniami manipulują dane w przepływie.

### <a name="key-activities"></a>Kluczowe działania

* AxClass/TaxIntegration **Calculation** ActivityOnDocument
* AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument
* AxClass/TaxIntegration **DataPersistence** ActivityOnDocument
* AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument
* AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument

Działania są uruchamiane w następującej kolejności:

1. Ustawianie pobierania
2. Pobieranie danych
3. Usługa obliczania
4. Kurs wymiany waluty
5. Utrwalanie danych

Na przykład rozszerzenie **Pobierania danych** przed **Usługą obliczania**.

#### <a name="data-retrieval-activities"></a>Działania pobierania danych

Działania **Pobierania danych** pobierają dane z bazy danych. Adaptery dla różnych transakcji są dostępne do pobierania danych z różnych tabel transakcji:

- AxClass/TaxIntegration **PurchTable** DataRetrieval
- AxClass/TaxIntegration **PurchParmTable** DataRetrieval
- AxClass/TaxIntegration **PurchREQTable** DataRetrieval
- AxClass/TaxIntegration **PurchRFQTable** DataRetrieval
- AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval
- AxClass/TaxIntegration **SalesTable** DataRetrieval
- AxClass/TaxIntegration **SalesParm** DataRetrieval

W tych działaniach **Pobierania danych** dane są kopiowane z bazy danych do `TaxIntegrationDocumentObject` i `TaxIntegrationLineObject`. Ponieważ wszystkie te działania rozszerzają tę samą klasę szablonu abstrakcyjnego, mają wspólne metody.

#### <a name="calculation-service-activities"></a>Czynności związane z usługami obliczeniowymi

Działanie **Usługa obliczania** jest łączem między usługą podatkową a integracją podatkową. To działanie jest odpowiedzialne za następujące funkcje:

1. Skonstruuj żądanie.
2. Księguj wniosek do usługi podatkowej.
3. Pobierz odpowiedź od usługi podatkowej.
4. Analiza odpowiedzi.

Pole danych, które dodasz do żądania, zostanie zaksięgowane razem z innymi metadanymi. 

## <a name="extension-implementation"></a>Implementacja rozszerzenia

Ta sekcja zawiera szczegółowe kroki, które zawierają informacje dotyczące implementacji rozszerzenia. Jako przykłady używane są wymiary finansowe **Centrum kosztów** i **Projekt**.

### <a name="step-1-add-the-data-variable-in-the-object-class"></a>Krok 1. Dodaj zmienną danych do klasy obiektu

Klasa obiektów zawiera zmienną danych oraz metody getter/setter dla danych. W zależności od poziomu pola należy dodać pole `TaxIntegrationDocumentObject` lub `TaxIntegrationLineObject` do wybranego pola lub do jego poziomu. W poniższym przykładzie użyto poziomu wiersza i nazwy `TaxIntegrationLineObject_Extension.xpp`:

> [!NOTE]
> Jeśli dodajene pole danych jest na poziomie dokumentu, zmień nazwę pliku na `TaxIntegrationDocumentObject_Extension.xpp`.

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

**Centrum kosztów** i **Projekt** są dodawane jako zmienne prywatne. Aby operować danymi, należy utworzyć metody getter i setter dla tych pól danych.

### <a name="step-2-retrieve-data-from-the-database"></a>Krok 2. Pobierz dane z bazy danych

Określ transakcję i rozszerz odpowiednie klasy adaptera, aby pobrać dane. Na przykład w przypadku użycia transakcji **zamówienia zakupu** należy rozszerzyć `TaxIntegrationPurchTableDataRetrieval` i `TaxIntegrationVendInvoiceInfoTableDataRetrieval`. 

> [!NOTE]
> `TaxIntegrationPurchParmTableDataRetrieval` jest dziedziczone po `TaxIntegrationPurchTableDataRetrieval`. Nie należy zmieniać tej zmiany, chyba że logika tabel `purchTable` i `purchParmTable` różni się.

Jeśli pole danych powinno być dodane dla wszystkich transakcji, należy rozszerzać wszystkie klasy `DataRetrieval`.

Ponieważ wszystkie działania **Pobierania danych** rozszerzają tę samą klasę szablonu, struktury klas, zmienne i metody są podobne.

```X++
protected TaxIntegrationDocumentObject document;

/// <summary>
/// Copies to the document.
/// </summary>
protected abstract void copyToDocument()
{
    // It is recommended to implement as:
    //
    // this.copyToDocumentByDefault();
    // this.copyToDocumentFromHeaderTable();
    // this.copyAddressToDocument();
}
 
/// <summary>
/// Copies to the current line of the document.
/// </summary>
/// <param name = "_line">The current line of the document.</param>
protected abstract void copyToLine(TaxIntegrationLineObject _line)
{
    // It is recommended to implement as:
    //
    // this.copyToLineByDefault(_line);
    // this.copyToLineFromLineTable(_line);
    // this.copyQuantityAndTransactionAmountToLine(_line);
    // this.copyAddressToLine(_line);
    // this.copyToLineFromHeaderTable(_line);
}
```

W poniższym przykładzie pokazano podstawową strukturę podczas używania tabeli `PurchTable`.

```X++
public class TaxIntegrationPurchTableDataRetrieval extends TaxIntegrationAbstractDataRetrievalTemplate
{
    protected PurchTable purchTable;
    protected PurchLine purchLine;

    // Query builder methods
    [Replaceable]
    protected SysDaQueryObject getDocumentQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineQueryObject()
    [Replaceable]
    protected SysDaQueryObject getDocumentChargeQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineChargeQueryObject()

    // Data retrieval methods
    protected void copyToDocument()
    protected void copyToDocumentFromHeaderTable()
    protected void copyToLine(TaxIntegrationLineObject _line)
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    ...
}
```

Podczas wywoływania metody `CopyToDocument` bufor `this.purchTable` już istnieje. Celem tej metody jest skopiowanie wszystkich wymaganych danych z `this.purchTable` do obiektu `document` przy użyciu metody ustawień utworzonej w klasie `DocumentObject`.

Podobnie bufor `this.purchLine` już istnieje w metodzie `CopyToLine`. Celem tej metody jest skopiowanie wszystkich wymaganych danych z `this.purchLine` do obiektu `_line` przy użyciu metody ustawień utworzonej w klasie `LineObject`.

Najbardziej jednoznacznym podejściem jest rozszerzanie metod `CopyToDocument` i `CopyToLine`. Najpierw jednak zaleca się najpierw użycie metod `copyToDocumentFromHeaderTable` i `copyToLineFromLineTable`. Jeśli nie działają w wymagany sposób, implementuj swoją własną metodę, a następnie wywołaj ją w `CopyToDocument` i `CopyToLine`. Istnieją trzy typowe sytuacje, w których można użyć tego podejścia:

- Wymagane pole jest w `PurchTable` lub `PurchLine`. W tej sytuacji można rozszerzać `copyToDocumentFromHeaderTable` i `copyToLineFromLineTable`. Oto przykładowy kod.

    ```X++
    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        next copyToLineFromLineTable(_line);
        // if we already added XXX in TaxIntegrationLineObject
        _line.setXXX(this.purchLine.XXX);
    }
    ```

- Wymagane dane nie są w domyślnej tabeli transakcji. Istnieją jednak pewne relacje sprzężenia z tabelą domyślną, a pole jest wymagane w większości wierszy. W tej sytuacji należy zastąpić `getDocumentQueryObject` lub `getLineObject` na kwerendę przez relację sprzężenia. W poniższym przykładzie pole **Dostarcz teraz** jest zintegrowane z zamówieniem sprzedaży na poziomie wiersza.

    ```X++
    public class TaxIntegrationSalesTableDataRetrieval
    {
        protected MCRSalesLineDropShipment mcrSalesLineDropShipment;

        /// <summary>
        /// Gets the query for the lines of the document.
        /// </summary>
        /// <returns>The query for the lines of the document</returns>
        [Replaceable]
        protected SysDaQueryObject getLineQueryObject()
        {
            return SysDaQueryObjectBuilder::from(this.salesLine)
                .where(this.salesLine, fieldStr(SalesLine, SalesId)).isEqualToLiteral(this.salesTable.SalesId)
                .outerJoin(this.mcrSalesLineDropShipment)
                .where(this.mcrSalesLineDropShipment, fieldStr(MCRSalesLineDropShipment, SalesLine)).isEqualTo(this.salesLine, fieldStr(SalesLine, RecId))
                .toSysDaQueryObject();
        }
    }
    ```

    W tym przykładzie bufor `mcrSalesLineDropShipment` jest zadeklarowany, a kwerenda jest zdefiniowana w `getLineQueryObject`. Kwerenda używa relacji `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`. Podczas rozszerzania tej sytuacji można zastąpić `getLineQueryObject` własnym skonstruowanym obiektem kwerendy. Warto jednak pamiętać o następujących punktów:

    * Ponieważ zwracana wartość metody `getLineQueryObject` wynosząca `SysDaQueryObject`, musisz skonstruować ten obiekt przy użyciu metody SysDa.
    * Nie można usunąć tabeli, która istniała.

- Wymagane dane są powiązane z tabelą transakcji za pomocą złożonej relacji sprzężenia lub relacja nie jest jeden-do-jednego (1:1), tylko jeden-do-wielu (1:N). W tej sytuacji sytuacja może się nieco skomplikowane. Ta sytuacja ma zastosowanie do przykładu wymiarów finansowych. 

    W tej sytuacji można zaimplementować własną metodę pobierania danych. Oto przykładowy kod w pliku `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.

    ```X++
    [ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
    final class TaxIntegrationPurchTableDataRetrieval_Extension
    {
        private const str CostCenterKey = 'CostCenter';
        private const str ProjectKey = 'Project';

        /// <summary>
        /// Copies to the current line of the document from.
        /// </summary>
        /// <param name = "_line">The current line of the document.</param>
        protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
        {
            Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
            if (dimensionAttributeMap.exists(CostCenterKey))
            {
                _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
            }
            if (dimensionAttributeMap.exists(ProjectKey))
            {
                _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
            }
            next copyToLineFromLineTable(_line);
        }
        private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
        {
            DimensionAttribute dimensionAttribute;
            DimensionAttributeValue dimensionAttributeValue;
            DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
            Map ret = new Map(Types::String, Types::String);

            select Name, RecId from dimensionAttribute
                join dimensionAttributeValue
                    where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
                join DimensionAttributeValueSetItem
                    where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                        && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;

            while(dimensionAttribute.RecId)
            {
                ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
                next dimensionAttribute;
            }
            return ret;
        }
    }
    ```

### <a name="step-3-add-data-to-the-request"></a>Krok 3. Dodaj dane do żądania

Rozszerzaj metodę `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` lub `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` do dodawania danych do żądania. Oto przykładowy kod w pliku `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define the field name in the request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';
    // private const str IOEnumExample = 'Enum Example';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());

        // If the field to be extended is an enum type, use enum2Symbol to convert an enum variable exampleEnum of ExampleEnumType to a string
        // _destination.SetField(IOEnumExample, enum2Symbol(enumNum(ExampleEnumType), _source.getExampleEnum()));
    }
}
```

W tym kodzie `_destination` jest obiektem otoki, który jest używany do generowania żądania, a `_source` to obiekt `TaxIntegrationLineObject`.

> [!NOTE]
> Zdefiniuj nazwę pola, która jest używana w żądaniu jako **private const str**. Ciąg powinien być dokładnie taki sam, jak nazwa węzła (nie etykieta) dodana w temacie [Dodawanie pól danych w konfiguracjach podatkowych](tax-service-add-data-fields-tax-configurations.md).
> 
> Ustaw pole w metodzie **copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine**, używając **metody SetField**. Typem danych drugiego parametru musi być **ciąg**. Jeśli typ danych nie jest **ciąg**, przekonwertuj go na string.
> Jeśli typem danych jest X++ **typ enum**, zalecamy użycie metody **enum2Symbol** do konwersji wartości wyliczenia na ciąg znaków. Wartość wyliczenia dodana w konfiguracji podatku powinna być dokładnie taka sama jak nazwa wyliczenia. Poniżej znajduje się lista różnic pomiędzy wartością wyliczenia, etykietą i nazwą.
> 
>   - Nazwa wyliczenia jest nazwą symboliczną w kodzie. **enum2Symbol()** może przekształcić wartość wyliczenia na jego nazwę.
>   - Wartość wyliczenia jest liczbą całkowitą.
>   - Etykieta wyli roku może być różna w różnych preferowanych językach. **enum2Str()** może przekształcić wartość wyliczeniową na jej etykietę.

## <a name="model-dependency"></a>Zależność modelu

Aby pomyślnie skompilować projekt, dodaj następujące modele odwołania do zależności modeli:

- ApplicationPlatform
- ApplicationSuite
- Aparat podatków
- Wymiary, jeśli jest używany wymiar finansowy
- Inne potrzebne modele, do których odwołuje się kod

## <a name="validation"></a>Sprawdzenie poprawności

Po ukończeniu poprzednich kroków możesz sprawdzić poprawność wprowadzonych zmian.

1. W polu Finanse przejdź do **rozrachunków z dostawcami** i dodaj wartość **&debug=vs%2CconfirmExit&** do adresu URL. Na przykład https://usnconeboxax1aos.cloud.onebox.dynamics.com/?cmp=DEMF&mi=PurchTableListPage&debug=vs%2CconfirmExit&. Ostateczna **&** jest podstawowa.
2. Otwórz stronę **Zamówienie zakupu** i wybierz **Nowość**, aby utworzyć zamówienie zakupu.
3. Ustaw wartość niestandardowego pola, a następnie wybierz opcję **Podatek**. Plik rozwiązywania problemów z prefiksem **TaxServiceTroubleshootingLog** jest pobierany automatycznie. Ten plik zawiera informacje o transakcjach zaksięgowane w usłudze obliczania podatku. 
4. Sprawdź, czy dodane pole niestandardowe znajduje się w sekcji **Dane wejściowe obliczenia usługi podatkowej JSON** i czy jego wartość jest poprawna. Jeśli wartość jest błędna, sprawdź dwukrotnie kroki w tym dokumencie.

Przykład pliku:

```
===Tax service calculation input JSON:===
{
  "TaxableDocument": {
    "Header": [
      {
        "Lines": [
          {
            "Line Type": "Normal",
            "Item Code": "",
            "Item Type": "Item",
            "Quantity": 0.0,
            "Amount": 1000.0,
            "Currency": "EUR",
            "Transaction Date": "2022-1-26T00:00:00",
            ...
            /// The new fields added at line level
            "Cost Center": "003",
            "Project": "Proj-123"
          }
        ],
        "Amount include tax": true,
        "Business Process": "Journal",
        "Currency": "",
        "Vendor Account": "DE-001",
        "Vendor Invoice Account": "DE-001",
        ...
        // The new fields added at header level, no new fields in this example
        ...
      }
    ]
  },
}
...
```

## <a name="appendix"></a>Dodatek

Ten dodatek pokazuje pełny przykładowy kod integracji wymiarów finansowych **Centrum kosztów** i **Projekt** na poziomie wiersza.

### <a name="taxintegrationlineobject_extensionxpp"></a>TaxIntegrationLineObject_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a>TaxIntegrationPurchTableDataRetrieval_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
final class TaxIntegrationPurchTableDataRetrieval_Extension
{
    private const str CostCenterKey = 'CostCenter';
    private const str ProjectKey = 'Project';

    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
        if (dimensionAttributeMap.exists(CostCenterKey))
        {
            _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
        }
        if (dimensionAttributeMap.exists(ProjectKey))
        {
            _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
        }
        next copyToLineFromLineTable(_line);
    }
    private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
    {
        DimensionAttribute dimensionAttribute;
        DimensionAttributeValue dimensionAttributeValue;
        DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
        Map ret = new Map(Types::String, Types::String);
        select Name, RecId from dimensionAttribute
            join dimensionAttributeValue
                where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
            join DimensionAttributeValueSetItem
                where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                    && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;
        while(dimensionAttribute.RecId)
        {
            ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
            next dimensionAttribute;
        }
        return ret;
    }
}
```

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a>TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define the field name in the request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```
