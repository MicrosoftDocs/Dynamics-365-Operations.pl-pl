---
title: Importowanie przychodzących wcześniejszych powiadomień o wysyłce za pomocą jednostki danych V2
description: W tym temacie wyjaśniono sposób zarządzania importem przychodzących zaawansowanych zawiadomień o wysyłce (ASN) za pomocą elementu danych Przychodzące ASN V2.
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: WHSInboundASNV2Entity, WHSInboundASNEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 470cc0c39f211a5d0f106c4c6e193867388e2b53
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249153"
---
# <a name="import-inbound-asns-through-the-v2-data-entity"></a><span data-ttu-id="4d03b-103">Importowanie przychodzących wcześniejszych powiadomień o wysyłce za pomocą jednostki danych V2</span><span class="sxs-lookup"><span data-stu-id="4d03b-103">Import inbound ASNs through the V2 data entity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4d03b-104">Zaawansowane zawiadomienia o wysyłce (ASN) informują o dostawach od sprzedawców.</span><span class="sxs-lookup"><span data-stu-id="4d03b-104">Advanced shipping notices (ASNs) notify you about vendor deliveries.</span></span> <span data-ttu-id="4d03b-105">Pomagają one nadawcy opisać zawartość przesyłki oraz dodatkowe informacje o niej, takie jak przedmioty i opakowanie.</span><span class="sxs-lookup"><span data-stu-id="4d03b-105">They help the sender describe the contents of a shipment and additional information about it, such as the items and packaging.</span></span>

<span data-ttu-id="4d03b-106">ASN mogą pomóc pracownikom magazynu dowiedzieć się, co i kiedy jest dostarczane.</span><span class="sxs-lookup"><span data-stu-id="4d03b-106">ASNs can help warehouse workers learn what is arriving when.</span></span> <span data-ttu-id="4d03b-107">W związku z tym mogą się przygotować.</span><span class="sxs-lookup"><span data-stu-id="4d03b-107">Therefore, they can prepare.</span></span> <span data-ttu-id="4d03b-108">Ponadto pracownicy magazynu mogą używać numerów ASN, aby dopasować szczegóły przesyłki do powiązanego z nią, utworzonego wcześniej zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="4d03b-108">In addition, warehouse workers can use ASNs to match the details of a shipment to the related purchase order that was previously created.</span></span>

<span data-ttu-id="4d03b-109">W tym temacie przedstawiono zbiór scenariuszy przedstawiających, za pomocą przykładów, sposób pracy z plikami ASN.</span><span class="sxs-lookup"><span data-stu-id="4d03b-109">This topic presents a collection of scenarios that show, through examples, how to work with ASN files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d03b-110">*Import przychodzący ASN* dotyczy tylko pozycji, które są włączone do zaawansowanego zarządzania magazynem (WMS).</span><span class="sxs-lookup"><span data-stu-id="4d03b-110">*Inbound ASN* import applies only to items that are enabled for advanced warehouse management (WMS).</span></span> <span data-ttu-id="4d03b-111">Zanim otrzymasz ASN, zamówienie zakupu musi być zarejestrowane w systemie w stosunku do sprzedawcy, który wysyła ten ASN.</span><span class="sxs-lookup"><span data-stu-id="4d03b-111">Before you receive an ASN, a purchase order must be registered in the system against the vendor who is sending that ASN.</span></span>

## <a name="inbound-asn-v2-entity"></a><span data-ttu-id="4d03b-112">Jednostka Przychodzące ASN V2</span><span class="sxs-lookup"><span data-stu-id="4d03b-112">Inbound ASN V2 entity</span></span>

<span data-ttu-id="4d03b-113">Importujesz przychodzące ASN używając złożonej encji danych *Przychodzące ASN V2*.</span><span class="sxs-lookup"><span data-stu-id="4d03b-113">You import inbound ASNs by using the *Inbound ASN V2* composite data entity.</span></span> <span data-ttu-id="4d03b-114">*Przychodzące ASN V2* ma następujące jednostki:</span><span class="sxs-lookup"><span data-stu-id="4d03b-114">*Inbound ASN V2* takes advantage of the following entities:</span></span>

- <span data-ttu-id="4d03b-115">Nagłówek ładunku przychodzącego</span><span class="sxs-lookup"><span data-stu-id="4d03b-115">Inbound load header</span></span>
- <span data-ttu-id="4d03b-116">Nagłówek wysyłki przychodzącej</span><span class="sxs-lookup"><span data-stu-id="4d03b-116">Inbound shipment header</span></span>
- <span data-ttu-id="4d03b-117">Struktury paczek ładunków przychodzących</span><span class="sxs-lookup"><span data-stu-id="4d03b-117">Inbound load packing structures</span></span>
- <span data-ttu-id="4d03b-118">Skrzynie w strukturze paczek ładunków przychodzących</span><span class="sxs-lookup"><span data-stu-id="4d03b-118">Inbound load packing structure cases</span></span>
- <span data-ttu-id="4d03b-119">Wiersze skrzyni w strukturze paczek ładunków przychodzących</span><span class="sxs-lookup"><span data-stu-id="4d03b-119">Inbound load packing structure case lines</span></span>
- <span data-ttu-id="4d03b-120">Wiersze struktury paczek ładunków przychodzących</span><span class="sxs-lookup"><span data-stu-id="4d03b-120">Inbound load packing structure lines</span></span>

<span data-ttu-id="4d03b-121">Złożona encja danych *Przychodzące ASN V2* jest przeznaczona dla scenariuszy integracji asynchronicznej, w których wykorzystywany jest import oparty na plikach XML.</span><span class="sxs-lookup"><span data-stu-id="4d03b-121">The *Inbound ASN V2* composite data entity is intended for asynchronous integration scenarios where XML file–based imports are used.</span></span>

## <a name="xml-format-for-importing-asns"></a><span data-ttu-id="4d03b-122">Format XML do importowania ASN</span><span class="sxs-lookup"><span data-stu-id="4d03b-122">XML format for importing ASNs</span></span>

<span data-ttu-id="4d03b-123">Microsoft Dynamics 365 Supply Chain Management obsługuje następujący format XML na potrzeby importu ASN.</span><span class="sxs-lookup"><span data-stu-id="4d03b-123">Microsoft Dynamics 365 Supply Chain Management supports the following XML format for importing ASNs.</span></span> <span data-ttu-id="4d03b-124">Każdy węzeł w pliku XML reprezentuje atrybut z pojedynczej encji.</span><span class="sxs-lookup"><span data-stu-id="4d03b-124">Each node in the XML file represents an attribute from an individual entity.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV2Entity>
                    </WHSInboundPackingStructureCaseLineV2Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV2Entity>
                </WHSInboundLoadPackingStructureLineV2Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a><span data-ttu-id="4d03b-125">Przykłady</span><span class="sxs-lookup"><span data-stu-id="4d03b-125">Examples</span></span>

<span data-ttu-id="4d03b-126">Poniższe podsekcji zawierają przykłady plików importu ASN XML dla wysyłek dostawców.</span><span class="sxs-lookup"><span data-stu-id="4d03b-126">The following subsections provide examples of ASN XML import files for vendor shipments.</span></span>

### <a name="example-1"></a><span data-ttu-id="4d03b-127">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="4d03b-127">Example 1</span></span>

<span data-ttu-id="4d03b-128">Poniższy przykład pokazuje plik XML służący do importowania wysyłek od dostawców dla jednego zamówienia zakupu, gdy nie są dołączone szczegóły sprawy.</span><span class="sxs-lookup"><span data-stu-id="4d03b-128">The following example shows an XML file for importing vendor shipments for one purchase order when no case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a><span data-ttu-id="4d03b-129">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="4d03b-129">Example 2</span></span>

<span data-ttu-id="4d03b-130">Poniższy przykład pokazuje plik XML służący do importowania wysyłek od dostawców dla jednego zamówienia zakupu, gdy są dołączone szczegóły sprawy.</span><span class="sxs-lookup"><span data-stu-id="4d03b-130">The following example shows an XML file for importing vendor shipments for one purchase order when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a><span data-ttu-id="4d03b-131">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="4d03b-131">Example 3</span></span>

<span data-ttu-id="4d03b-132">Poniższy przykład pokazuje plik XML służący do importowania wysyłek od dostawców dla wielu zamówień zakupu, gdy są dołączone szczegóły sprawy.</span><span class="sxs-lookup"><span data-stu-id="4d03b-132">The following example shows an XML file for importing vendor shipments for multiple purchase orders when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a><span data-ttu-id="4d03b-133">Sprawdzenie wyników importu pliku ASN</span><span class="sxs-lookup"><span data-stu-id="4d03b-133">Inspect the results of importing an ASN file</span></span>

<span data-ttu-id="4d03b-134">Wykonaj poniższe kroki, aby sprawdzić wyniki importu pliku ASN.</span><span class="sxs-lookup"><span data-stu-id="4d03b-134">Follow these steps to inspect the results of importing an ASN file.</span></span>

1. <span data-ttu-id="4d03b-135">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="4d03b-135">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="4d03b-136">Znajdź i otwórz ładunek, który został utworzony jako część importu ASN.</span><span class="sxs-lookup"><span data-stu-id="4d03b-136">Find and open a load that was created as part of an ASN import.</span></span>
1. <span data-ttu-id="4d03b-137">Na skróconej karcie **ładunku** powinny zostać wyświetlone wartości oparte na pliku XML.</span><span class="sxs-lookup"><span data-stu-id="4d03b-137">On the **Load** FastTab, you should see values that are based on the XML file.</span></span>
1. <span data-ttu-id="4d03b-138">Na skróconej karcie **Wiersze ładunków**, powinieneś zobaczyć numery zamówień zakupu i szczegóły pozycji, które są oparte na pliku XML.</span><span class="sxs-lookup"><span data-stu-id="4d03b-138">On the **Load lines** FastTab, you should see purchase order numbers and item details that are based on the XML file.</span></span>
1. <span data-ttu-id="4d03b-139">Na pasku akcji, na karcie **Wysyłka i odbiór**, w grupie **Odbiór** **Sztuka pakowania** , aby przejrzeć strukturę pakowania ładunku.</span><span class="sxs-lookup"><span data-stu-id="4d03b-139">On the Action Pane, on the **Ship and receive** tab, in the **Receive** group, select **Packing structure** to review the packing structure of the load.</span></span>
1. <span data-ttu-id="4d03b-140">Na skróconej karcie **Palety** powinny zostać wyświetlone numery identyfikacyjne oparte na pliku XML.</span><span class="sxs-lookup"><span data-stu-id="4d03b-140">On the **Pallets** FastTab, you should see license plates that are based on the XML file.</span></span>
1. <span data-ttu-id="4d03b-141">Na skróconej karcie **Pojemniki** powinny zostać wyświetlone pojemniki oparte na pliku XML.</span><span class="sxs-lookup"><span data-stu-id="4d03b-141">On the **Cases** FastTab, you should see cases that are based on the XML file.</span></span>
1. <span data-ttu-id="4d03b-142">Na skróconej karcie **Elementy** powinny zostać wyświetlone elementy i ilości oparte na pliku XML.</span><span class="sxs-lookup"><span data-stu-id="4d03b-142">On the **Items** FastTab, you should see items and quantities that are based on the XML file.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
