---
title: Dodawanie pól danych w integracji podatków przy użyciu rozszerzeń
description: W tym temacie opisano, jak używać rozszerzeń X++ w celu dodawania pól danych w integracji podatków.
author: qire
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 8e3573f9c9971d4a5af33ece08b7e0b43f2e813a
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921172"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a><span data-ttu-id="4013c-103">Dodawanie pól danych w integracji podatków przy użyciu rozszerzeń</span><span class="sxs-lookup"><span data-stu-id="4013c-103">Add data fields in the tax integration by using extension</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="4013c-104">W tym temacie opisano, jak używać rozszerzeń X++ w celu dodawania pól danych w integracji podatków.</span><span class="sxs-lookup"><span data-stu-id="4013c-104">This topic explains how to use X++ extensions to add data fields in the tax integration.</span></span> <span data-ttu-id="4013c-105">Te pola mogą być rozszerzone na model danych podatkowych usługi podatkowej i używane do określania kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="4013c-105">These fields can be extended to the tax data model of the tax service and used to determine tax codes.</span></span> <span data-ttu-id="4013c-106">Aby uzyskać więcej informacji, zobacz temat [Dodawanie pól danych w konfiguracjach podatków](tax-service-add-data-fields-tax-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="4013c-106">For more information, see [Add data fields in tax configurations](tax-service-add-data-fields-tax-configurations.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="4013c-107">Model danych</span><span class="sxs-lookup"><span data-stu-id="4013c-107">Data model</span></span>

<span data-ttu-id="4013c-108">Dane w modelu danych są realizowane przez obiekty i implementowane przez klasy.</span><span class="sxs-lookup"><span data-stu-id="4013c-108">The data in the data model is carried by objects and implemented by classes.</span></span>

<span data-ttu-id="4013c-109">Poniżej znajduje się lista dużych objektów:</span><span class="sxs-lookup"><span data-stu-id="4013c-109">Here is a list of the major objects:</span></span>

* <span data-ttu-id="4013c-110">AxClass/TaxIntegration **Document** Object</span><span class="sxs-lookup"><span data-stu-id="4013c-110">AxClass/TaxIntegration **Document** Object</span></span>
* <span data-ttu-id="4013c-111">AxClass/TaxIntegration **Line** Object</span><span class="sxs-lookup"><span data-stu-id="4013c-111">AxClass/TaxIntegration **Line** Object</span></span>
* <span data-ttu-id="4013c-112">AxClass/TaxIntegration **TaxLine** Object</span><span class="sxs-lookup"><span data-stu-id="4013c-112">AxClass/TaxIntegration **TaxLine** Object</span></span>

<span data-ttu-id="4013c-113">Na poniższej ilustracji pokazano, w jaki sposób są one powiązane.</span><span class="sxs-lookup"><span data-stu-id="4013c-113">The following illustration shows how these objects are related.</span></span>

<span data-ttu-id="4013c-114">[![Relacja obiektów modelu danych](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span><span class="sxs-lookup"><span data-stu-id="4013c-114">[![Data model object relationship](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span></span>

<span data-ttu-id="4013c-115">Obiekt **Dokumentu** może zawierać wiele obiektów **Wiersza**.</span><span class="sxs-lookup"><span data-stu-id="4013c-115">A **Document** object can contain many **Line** objects.</span></span> <span data-ttu-id="4013c-116">Każdy obiekt zawiera metadane usługi podatków.</span><span class="sxs-lookup"><span data-stu-id="4013c-116">Each object contains metadata for the tax service.</span></span>

- <span data-ttu-id="4013c-117">`TaxIntegrationDocumentObject` zawiera metadane `originAddress`, które zawierają informacje o adresie źródłowym, oraz metadane `includingTax`, które wskazują, czy kwota wiersza zawiera podatek.</span><span class="sxs-lookup"><span data-stu-id="4013c-117">`TaxIntegrationDocumentObject` has `originAddress` metadata, which contains information about the source address, and `includingTax` metadata, which indicates whether the line amount includes sales tax.</span></span>
- <span data-ttu-id="4013c-118">`TaxIntegrationLineObject` ma metadane `itemId`, `quantity` i `categoryId`.</span><span class="sxs-lookup"><span data-stu-id="4013c-118">`TaxIntegrationLineObject` has `itemId`, `quantity`, and `categoryId` metadata.</span></span>

> [!NOTE]
> <span data-ttu-id="4013c-119">`TaxIntegrationLineObject` implementuje również obiekty **Opłat**.</span><span class="sxs-lookup"><span data-stu-id="4013c-119">`TaxIntegrationLineObject` also implements **Charge** objects.</span></span>

## <a name="integration-flow"></a><span data-ttu-id="4013c-120">Przepływ integracji</span><span class="sxs-lookup"><span data-stu-id="4013c-120">Integration flow</span></span>

<span data-ttu-id="4013c-121">Działaniami manipulują dane w przepływie.</span><span class="sxs-lookup"><span data-stu-id="4013c-121">The data in the flow is manipulated by activities.</span></span>

### <a name="key-activities"></a><span data-ttu-id="4013c-122">Kluczowe działania</span><span class="sxs-lookup"><span data-stu-id="4013c-122">Key activities</span></span>

* <span data-ttu-id="4013c-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="4013c-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span></span>
* <span data-ttu-id="4013c-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="4013c-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span></span>
* <span data-ttu-id="4013c-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="4013c-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span></span>
* <span data-ttu-id="4013c-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="4013c-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span></span>
* <span data-ttu-id="4013c-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="4013c-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span></span>

<span data-ttu-id="4013c-128">Działania są uruchamiane w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="4013c-128">Activities are run in the following order:</span></span>

1. <span data-ttu-id="4013c-129">Ustawianie pobierania</span><span class="sxs-lookup"><span data-stu-id="4013c-129">Setting Retrieval</span></span>
2. <span data-ttu-id="4013c-130">Pobieranie danych</span><span class="sxs-lookup"><span data-stu-id="4013c-130">Data Retrieval</span></span>
3. <span data-ttu-id="4013c-131">Usługa obliczania</span><span class="sxs-lookup"><span data-stu-id="4013c-131">Calculation Service</span></span>
4. <span data-ttu-id="4013c-132">Kurs wymiany waluty</span><span class="sxs-lookup"><span data-stu-id="4013c-132">Currency Exchange</span></span>
5. <span data-ttu-id="4013c-133">Utrwalanie danych</span><span class="sxs-lookup"><span data-stu-id="4013c-133">Data Persistence</span></span>

<span data-ttu-id="4013c-134">Na przykład rozszerzenie **Pobierania danych** przed **Usługą obliczania**.</span><span class="sxs-lookup"><span data-stu-id="4013c-134">For example, extend **Data Retrieval** before **Calculation Service**.</span></span>

#### <a name="data-retrieval-activities"></a><span data-ttu-id="4013c-135">Działania pobierania danych</span><span class="sxs-lookup"><span data-stu-id="4013c-135">Data Retrieval activities</span></span>

<span data-ttu-id="4013c-136">Działania **Pobierania danych** pobierają dane z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="4013c-136">**Data Retrieval** activities retrieve data from the database.</span></span> <span data-ttu-id="4013c-137">Adaptery dla różnych transakcji są dostępne do pobierania danych z różnych tabel transakcji:</span><span class="sxs-lookup"><span data-stu-id="4013c-137">Adapters for different transactions are available to retrieve data from different transaction tables:</span></span>

- <span data-ttu-id="4013c-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="4013c-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span></span>
- <span data-ttu-id="4013c-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="4013c-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span></span>
- <span data-ttu-id="4013c-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="4013c-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span></span>
- <span data-ttu-id="4013c-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="4013c-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span></span>
- <span data-ttu-id="4013c-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="4013c-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span></span>
- <span data-ttu-id="4013c-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="4013c-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span></span>
- <span data-ttu-id="4013c-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="4013c-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span></span>

<span data-ttu-id="4013c-145">W tych działaniach **Pobierania danych** dane są kopiowane z bazy danych do `TaxIntegrationDocumentObject` i `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="4013c-145">In these **Data Retrieval** activities, data is copied from the database to `TaxIntegrationDocumentObject` and `TaxIntegrationLineObject`.</span></span> <span data-ttu-id="4013c-146">Ponieważ wszystkie te działania rozszerzają tę samą klasę szablonu abstrakcyjnego, mają wspólne metody.</span><span class="sxs-lookup"><span data-stu-id="4013c-146">Because all these activities extend the same abstract template class, they have common methods.</span></span>

#### <a name="calculation-service-activities"></a><span data-ttu-id="4013c-147">Czynności związane z usługami obliczeniowymi</span><span class="sxs-lookup"><span data-stu-id="4013c-147">Calculation Service activities</span></span>

<span data-ttu-id="4013c-148">Działanie **Usługa obliczania** jest łączem między usługą podatkową a integracją podatkową.</span><span class="sxs-lookup"><span data-stu-id="4013c-148">The **Calculation Service** activity is the link between the tax service and the tax integration.</span></span> <span data-ttu-id="4013c-149">To działanie jest odpowiedzialne za następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="4013c-149">This activity is responsible for the following functions:</span></span>

1. <span data-ttu-id="4013c-150">Skonstruuj żądanie.</span><span class="sxs-lookup"><span data-stu-id="4013c-150">Construct the request.</span></span>
2. <span data-ttu-id="4013c-151">Księguj wniosek do usługi podatkowej.</span><span class="sxs-lookup"><span data-stu-id="4013c-151">Post the request to the tax service.</span></span>
3. <span data-ttu-id="4013c-152">Pobierz odpowiedź od usługi podatkowej.</span><span class="sxs-lookup"><span data-stu-id="4013c-152">Get the response from the tax service.</span></span>
4. <span data-ttu-id="4013c-153">Analiza odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="4013c-153">Parse the response.</span></span>

<span data-ttu-id="4013c-154">Pole danych, które dodasz do żądania, zostanie zaksięgowane razem z innymi metadanymi.</span><span class="sxs-lookup"><span data-stu-id="4013c-154">A data field that you add to the request will be posted together with other metadata.</span></span> 

## <a name="extension-implementation"></a><span data-ttu-id="4013c-155">Implementacja rozszerzenia</span><span class="sxs-lookup"><span data-stu-id="4013c-155">Extension implementation</span></span>

<span data-ttu-id="4013c-156">Ta sekcja zawiera szczegółowe kroki, które zawierają informacje dotyczące implementacji rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="4013c-156">This section provides detailed steps that explain how to implement the extension.</span></span> <span data-ttu-id="4013c-157">Jako przykłady używane są wymiary finansowe **Centrum kosztów** i **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="4013c-157">It uses the **Cost center** and **Project** financial dimensions as examples.</span></span>

### <a name="step-1-add-the-data-variable-in-the-object-class"></a><span data-ttu-id="4013c-158">Krok 1.</span><span class="sxs-lookup"><span data-stu-id="4013c-158">Step 1.</span></span> <span data-ttu-id="4013c-159">Dodaj zmienną danych do klasy obiektu</span><span class="sxs-lookup"><span data-stu-id="4013c-159">Add the data variable in the object class</span></span>

<span data-ttu-id="4013c-160">Klasa obiektów zawiera zmienną danych oraz metody getter/setter dla danych.</span><span class="sxs-lookup"><span data-stu-id="4013c-160">The object class contains the data variable and getter/setter methods for the data.</span></span> <span data-ttu-id="4013c-161">W zależności od poziomu pola należy dodać pole `TaxIntegrationDocumentObject` lub `TaxIntegrationLineObject` do wybranego pola lub do jego poziomu.</span><span class="sxs-lookup"><span data-stu-id="4013c-161">Add the data field to either `TaxIntegrationDocumentObject` or `TaxIntegrationLineObject`, depending on the level of the field.</span></span> <span data-ttu-id="4013c-162">W poniższym przykładzie użyto poziomu wiersza i nazwy `TaxIntegrationLineObject_Extension.xpp`:</span><span class="sxs-lookup"><span data-stu-id="4013c-162">The following example uses the line level, and the file name is `TaxIntegrationLineObject_Extension.xpp`.</span></span>

> [!NOTE]
> <span data-ttu-id="4013c-163">Jeśli dodajene pole danych jest na poziomie dokumentu, zmień nazwę pliku na `TaxIntegrationDocumentObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="4013c-163">If the data field that you're adding is at the document level, change the file name to `TaxIntegrationDocumentObject_Extension.xpp`.</span></span>

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

<span data-ttu-id="4013c-164">**Centrum kosztów** i **Projekt** są dodawane jako zmienne prywatne.</span><span class="sxs-lookup"><span data-stu-id="4013c-164">**Cost center** and **Project** are added as private variables.</span></span> <span data-ttu-id="4013c-165">Aby operować danymi, należy utworzyć metody getter i setter dla tych pól danych.</span><span class="sxs-lookup"><span data-stu-id="4013c-165">Create getter and setter methods for these data fields to manipulate the data.</span></span>

### <a name="step-2-retrieve-data-from-the-database"></a><span data-ttu-id="4013c-166">Krok 2.</span><span class="sxs-lookup"><span data-stu-id="4013c-166">Step 2.</span></span> <span data-ttu-id="4013c-167">Pobierz dane z bazy danych</span><span class="sxs-lookup"><span data-stu-id="4013c-167">Retrieve data from the database</span></span>

<span data-ttu-id="4013c-168">Określ transakcję i rozszerz odpowiednie klasy adaptera, aby pobrać dane.</span><span class="sxs-lookup"><span data-stu-id="4013c-168">Specify the transaction, and extend the appropriate adapter classes to retrieve the data.</span></span> <span data-ttu-id="4013c-169">Na przykład w przypadku użycia transakcji **zamówienia zakupu** należy rozszerzyć `TaxIntegrationPurchTableDataRetrieval` i `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="4013c-169">For example, if you use a **Purchase order** transaction, you must extend `TaxIntegrationPurchTableDataRetrieval` and `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span></span> 

> [!NOTE]
> <span data-ttu-id="4013c-170">`TaxIntegrationPurchParmTableDataRetrieval` jest dziedziczone po `TaxIntegrationPurchTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="4013c-170">`TaxIntegrationPurchParmTableDataRetrieval` is inherited from `TaxIntegrationPurchTableDataRetrieval`.</span></span> <span data-ttu-id="4013c-171">Nie należy zmieniać tej zmiany, chyba że logika tabel `purchTable` i `purchParmTable` różni się.</span><span class="sxs-lookup"><span data-stu-id="4013c-171">It should not be changed unless the logic of the `purchTable` and `purchParmTable` tables differs.</span></span>

<span data-ttu-id="4013c-172">Jeśli pole danych powinno być dodane dla wszystkich transakcji, należy rozszerzać wszystkie klasy `DataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="4013c-172">If the data field should be added for all transactions, extend all `DataRetrieval` classes.</span></span>

<span data-ttu-id="4013c-173">Ponieważ wszystkie działania **Pobierania danych** rozszerzają tę samą klasę szablonu, struktury klas, zmienne i metody są podobne.</span><span class="sxs-lookup"><span data-stu-id="4013c-173">Because all **Data Retrieval** activities extend the same template class, the class structures, variables, and methods are similar.</span></span>

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

<span data-ttu-id="4013c-174">W poniższym przykładzie pokazano podstawową strukturę podczas używania tabeli `PurchTable`.</span><span class="sxs-lookup"><span data-stu-id="4013c-174">The following example shows the basic structure when the `PurchTable` table is used.</span></span>

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

<span data-ttu-id="4013c-175">Podczas wywoływania metody `CopyToDocument` bufor `this.purchTable` już istnieje.</span><span class="sxs-lookup"><span data-stu-id="4013c-175">When the `CopyToDocument` method is called, the `this.purchTable` buffer already exists.</span></span> <span data-ttu-id="4013c-176">Celem tej metody jest skopiowanie wszystkich wymaganych danych z `this.purchTable` do obiektu `document` przy użyciu metody ustawień utworzonej w klasie `DocumentObject`.</span><span class="sxs-lookup"><span data-stu-id="4013c-176">The purpose of this method is to copy all the required data from `this.purchTable` to the `document` object by using the setter method that was created in the `DocumentObject` class.</span></span>

<span data-ttu-id="4013c-177">Podobnie bufor `this.purchLine` już istnieje w metodzie `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="4013c-177">Likewise, a `this.purchLine` buffer already exists in the `CopyToLine` method.</span></span> <span data-ttu-id="4013c-178">Celem tej metody jest skopiowanie wszystkich wymaganych danych z `this.purchLine` do obiektu `_line` przy użyciu metody ustawień utworzonej w klasie `LineObject`.</span><span class="sxs-lookup"><span data-stu-id="4013c-178">The purpose of this method is to copy all the required data from `this.purchLine` to the `_line` object by using the setter method that was created in the `LineObject` class.</span></span>

<span data-ttu-id="4013c-179">Najbardziej jednoznacznym podejściem jest rozszerzanie metod `CopyToDocument` i `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="4013c-179">The most straightforward approach is to extend the `CopyToDocument` and `CopyToLine` methods.</span></span> <span data-ttu-id="4013c-180">Najpierw jednak zaleca się najpierw użycie metod `copyToDocumentFromHeaderTable` i `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="4013c-180">However, we recommend that you try the `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable` methods first.</span></span> <span data-ttu-id="4013c-181">Jeśli nie działają w wymagany sposób, implementuj swoją własną metodę, a następnie wywołaj ją w `CopyToDocument` i `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="4013c-181">If they don't work as you require, implement your own method, and call it in `CopyToDocument` and `CopyToLine`.</span></span> <span data-ttu-id="4013c-182">Istnieją trzy typowe sytuacje, w których można użyć tego podejścia:</span><span class="sxs-lookup"><span data-stu-id="4013c-182">There are three common situations where you might use this approach:</span></span>

- <span data-ttu-id="4013c-183">Wymagane pole jest w `PurchTable` lub `PurchLine`.</span><span class="sxs-lookup"><span data-stu-id="4013c-183">The required field is in `PurchTable` or `PurchLine`.</span></span> <span data-ttu-id="4013c-184">W tej sytuacji można rozszerzać `copyToDocumentFromHeaderTable` i `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="4013c-184">In this situation, you can extend `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable`.</span></span> <span data-ttu-id="4013c-185">Oto przykładowy kod.</span><span class="sxs-lookup"><span data-stu-id="4013c-185">Here is the sample code.</span></span>

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

- <span data-ttu-id="4013c-186">Wymagane dane nie są w domyślnej tabeli transakcji.</span><span class="sxs-lookup"><span data-stu-id="4013c-186">The required data isn't in the default table of the transaction.</span></span> <span data-ttu-id="4013c-187">Istnieją jednak pewne relacje sprzężenia z tabelą domyślną, a pole jest wymagane w większości wierszy.</span><span class="sxs-lookup"><span data-stu-id="4013c-187">However, there are some join relationships with the default table, and the field is required on most lines.</span></span> <span data-ttu-id="4013c-188">W tej sytuacji należy zastąpić `getDocumentQueryObject` lub `getLineObject` na kwerendę przez relację sprzężenia.</span><span class="sxs-lookup"><span data-stu-id="4013c-188">In this situation, replace `getDocumentQueryObject` or `getLineObject` to query the table by join relationship.</span></span> <span data-ttu-id="4013c-189">W poniższym przykładzie pole **Dostarcz teraz** jest zintegrowane z zamówieniem sprzedaży na poziomie wiersza.</span><span class="sxs-lookup"><span data-stu-id="4013c-189">In the following example, the **Deliver Now** field is integrated with the sales order at the line level.</span></span>

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

    <span data-ttu-id="4013c-190">W tym przykładzie bufor `mcrSalesLineDropShipment` jest zadeklarowany, a kwerenda jest zdefiniowana w `getLineQueryObject`.</span><span class="sxs-lookup"><span data-stu-id="4013c-190">In this example, a `mcrSalesLineDropShipment` buffer is declared, and the query is defined in `getLineQueryObject`.</span></span> <span data-ttu-id="4013c-191">Kwerenda używa relacji `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span><span class="sxs-lookup"><span data-stu-id="4013c-191">The query uses the relationship `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span></span> <span data-ttu-id="4013c-192">Podczas rozszerzania tej sytuacji można zastąpić `getLineQueryObject` własnym skonstruowanym obiektem kwerendy.</span><span class="sxs-lookup"><span data-stu-id="4013c-192">While you're extending in this situation, you can replace `getLineQueryObject` with your own constructed query object.</span></span> <span data-ttu-id="4013c-193">Warto jednak pamiętać o następujących punktów:</span><span class="sxs-lookup"><span data-stu-id="4013c-193">However, note the following points:</span></span>

    * <span data-ttu-id="4013c-194">Ponieważ zwracana wartość metody `getLineQueryObject` wynosząca `SysDaQueryObject`, musisz skonstruować ten obiekt przy użyciu metody SysDa.</span><span class="sxs-lookup"><span data-stu-id="4013c-194">Because the return value of the `getLineQueryObject` method is `SysDaQueryObject`, you must construct this object by using the SysDa approach.</span></span>
    * <span data-ttu-id="4013c-195">Nie można usunąć tabeli, która istniała.</span><span class="sxs-lookup"><span data-stu-id="4013c-195">Can't remove existed table.</span></span>

- <span data-ttu-id="4013c-196">Wymagane dane są powiązane z tabelą transakcji za pomocą złożonej relacji sprzężenia lub relacja nie jest jeden-do-jednego (1:1), tylko jeden-do-wielu (1:N).</span><span class="sxs-lookup"><span data-stu-id="4013c-196">The required data is related to the transaction table by a complicated join relationship, or the relation isn't one to one (1:1) but one to many (1:N).</span></span> <span data-ttu-id="4013c-197">W tej sytuacji sytuacja może się nieco skomplikowane.</span><span class="sxs-lookup"><span data-stu-id="4013c-197">In this situation, things become a little complicated.</span></span> <span data-ttu-id="4013c-198">Ta sytuacja ma zastosowanie do przykładu wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="4013c-198">This situation applies to the example of financial dimensions.</span></span> 

    <span data-ttu-id="4013c-199">W tej sytuacji można zaimplementować własną metodę pobierania danych.</span><span class="sxs-lookup"><span data-stu-id="4013c-199">In this situation, you can implement your own method to retrieve the data.</span></span> <span data-ttu-id="4013c-200">Oto przykładowy kod w pliku `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="4013c-200">Here is the sample code in the `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` file.</span></span>

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

### <a name="step-3-add-data-to-the-request"></a><span data-ttu-id="4013c-201">Krok 3.</span><span class="sxs-lookup"><span data-stu-id="4013c-201">Step 3.</span></span> <span data-ttu-id="4013c-202">Dodaj dane do żądania</span><span class="sxs-lookup"><span data-stu-id="4013c-202">Add data to the request</span></span>

<span data-ttu-id="4013c-203">Rozszerzaj metodę `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` lub `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` do dodawania danych do żądania.</span><span class="sxs-lookup"><span data-stu-id="4013c-203">Extend the `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` or `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method to add data to the request.</span></span> <span data-ttu-id="4013c-204">Oto przykładowy kod w pliku `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="4013c-204">Here is the sample code in the `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` file.</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
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

<span data-ttu-id="4013c-205">W tym kodzie `_destination` jest obiektem otoki, który jest używany do generowania żądania wpisu, a `_source` to obiekt `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="4013c-205">In this code, `_destination` is the wrapper object that is used to generate the post request, and `_source` is the `TaxIntegrationLineObject` object.</span></span> 

> [!NOTE]
> * <span data-ttu-id="4013c-206">Zdefiniuj klucz używany w formularzu żądania jako `private const str`.</span><span class="sxs-lookup"><span data-stu-id="4013c-206">Define the key that is used in the request form as `private const str`.</span></span>
> * <span data-ttu-id="4013c-207">Ustaw pole w metodzie `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` za pomocą metody `SetField`.</span><span class="sxs-lookup"><span data-stu-id="4013c-207">Set the field in the `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method by using the `SetField` method.</span></span> <span data-ttu-id="4013c-208">Typem danych drugiego parametru musi być `string`.</span><span class="sxs-lookup"><span data-stu-id="4013c-208">The data type of the second parameter should be `string`.</span></span> <span data-ttu-id="4013c-209">Jeśli typ danych nie jest `string`, przekonwertuj go na `string`.</span><span class="sxs-lookup"><span data-stu-id="4013c-209">If the data type isn't `string`, convert it to `string`.</span></span>

## <a name="appendix"></a><span data-ttu-id="4013c-210">Dodatek</span><span class="sxs-lookup"><span data-stu-id="4013c-210">Appendix</span></span>

<span data-ttu-id="4013c-211">Ten dodatek pokazuje pełny przykładowy kod integracji wymiarów finansowych (**Centrum kosztów** i **Projekt**) na poziomie wiersza.</span><span class="sxs-lookup"><span data-stu-id="4013c-211">This appendix shows the complete sample code for the integration of financial dimensions (**Cost center** and **Project**) at the line level.</span></span>

### <a name="taxintegrationlineobject_extensionxpp"></a><span data-ttu-id="4013c-212">TaxIntegrationLineObject_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="4013c-212">TaxIntegrationLineObject_Extension.xpp</span></span>

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

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a><span data-ttu-id="4013c-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="4013c-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span></span>

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

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a><span data-ttu-id="4013c-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="4013c-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
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
