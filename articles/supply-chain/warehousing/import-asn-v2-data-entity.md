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
# <a name="import-inbound-asns-through-the-v2-data-entity"></a>Importowanie przychodzących wcześniejszych powiadomień o wysyłce za pomocą jednostki danych V2

[!include [banner](../../includes/banner.md)]

Zaawansowane zawiadomienia o wysyłce (ASN) informują o dostawach od sprzedawców. Pomagają one nadawcy opisać zawartość przesyłki oraz dodatkowe informacje o niej, takie jak przedmioty i opakowanie.

ASN mogą pomóc pracownikom magazynu dowiedzieć się, co i kiedy jest dostarczane. W związku z tym mogą się przygotować. Ponadto pracownicy magazynu mogą używać numerów ASN, aby dopasować szczegóły przesyłki do powiązanego z nią, utworzonego wcześniej zamówienia zakupu.

W tym temacie przedstawiono zbiór scenariuszy przedstawiających, za pomocą przykładów, sposób pracy z plikami ASN.

> [!IMPORTANT]
> *Import przychodzący ASN* dotyczy tylko pozycji, które są włączone do zaawansowanego zarządzania magazynem (WMS). Zanim otrzymasz ASN, zamówienie zakupu musi być zarejestrowane w systemie w stosunku do sprzedawcy, który wysyła ten ASN.

## <a name="inbound-asn-v2-entity"></a>Jednostka Przychodzące ASN V2

Importujesz przychodzące ASN używając złożonej encji danych *Przychodzące ASN V2*. *Przychodzące ASN V2* ma następujące jednostki:

- Nagłówek ładunku przychodzącego
- Nagłówek wysyłki przychodzącej
- Struktury paczek ładunków przychodzących
- Skrzynie w strukturze paczek ładunków przychodzących
- Wiersze skrzyni w strukturze paczek ładunków przychodzących
- Wiersze struktury paczek ładunków przychodzących

Złożona encja danych *Przychodzące ASN V2* jest przeznaczona dla scenariuszy integracji asynchronicznej, w których wykorzystywany jest import oparty na plikach XML.

## <a name="xml-format-for-importing-asns"></a>Format XML do importowania ASN

Microsoft Dynamics 365 Supply Chain Management obsługuje następujący format XML na potrzeby importu ASN. Każdy węzeł w pliku XML reprezentuje atrybut z pojedynczej encji.

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

## <a name="examples"></a>Przykłady

Poniższe podsekcji zawierają przykłady plików importu ASN XML dla wysyłek dostawców.

### <a name="example-1"></a>Przykład 1

Poniższy przykład pokazuje plik XML służący do importowania wysyłek od dostawców dla jednego zamówienia zakupu, gdy nie są dołączone szczegóły sprawy.

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

### <a name="example-2"></a>Przykład 2

Poniższy przykład pokazuje plik XML służący do importowania wysyłek od dostawców dla jednego zamówienia zakupu, gdy są dołączone szczegóły sprawy.

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

### <a name="example-3"></a>Przykład 3

Poniższy przykład pokazuje plik XML służący do importowania wysyłek od dostawców dla wielu zamówień zakupu, gdy są dołączone szczegóły sprawy.

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

## <a name="inspect-the-results-of-importing-an-asn-file"></a>Sprawdzenie wyników importu pliku ASN

Wykonaj poniższe kroki, aby sprawdzić wyniki importu pliku ASN.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Znajdź i otwórz ładunek, który został utworzony jako część importu ASN.
1. Na skróconej karcie **ładunku** powinny zostać wyświetlone wartości oparte na pliku XML.
1. Na skróconej karcie **Wiersze ładunków**, powinieneś zobaczyć numery zamówień zakupu i szczegóły pozycji, które są oparte na pliku XML.
1. Na pasku akcji, na karcie **Wysyłka i odbiór**, w grupie **Odbiór** **Sztuka pakowania** , aby przejrzeć strukturę pakowania ładunku.
1. Na skróconej karcie **Palety** powinny zostać wyświetlone numery identyfikacyjne oparte na pliku XML.
1. Na skróconej karcie **Pojemniki** powinny zostać wyświetlone pojemniki oparte na pliku XML.
1. Na skróconej karcie **Elementy** powinny zostać wyświetlone elementy i ilości oparte na pliku XML.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
