---
title: Obsługiwane typy danych złożonych dla formuł raportowania elektronicznego
description: Ten temat zawiera ogólne informacje o funkcjach danych złożonych obsługiwanych w formułach Raportowania elektronicznego (ER).
author: NickSelin
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2593f3128ec103248e109f3c80f48b9d7a035f54
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355353"
---
# <a name="supported-composite-data-types-for-electronic-reporting-formulas"></a>Obsługiwane typy danych złożonych dla formuł raportowania elektronicznego

[!include [banner](../includes/banner.md)]

Ten temat zawiera ogólne informacje o funkcjach danych złożonych obsługiwanych w wyrażeniach [Raportowania elektronicznego (ER)](general-electronic-reporting.md). Typy danych złożonych to [klasa](#class), [kontener](#container), [rekord](#record), [lista rekordów](#record-list) i [obiekt](#object).

## <a name="class"></a><a name="class"></a>Klasa

Typ danych *klasy* odwołuje się do klasy aplikacji publicznej. W ER jest ona przedstawiana jako [*rekord*](#record) zawierający osobne pole dla każdej metody publicznej klasy, do których odwołuje się odwołanie. Gdy wywołanie metody jest parametryzowane, należy także określić wymagane argumenty odpowiednich typów w wyrażeniu ER skonfigurowanym do wywołania metody.

W składnikach [mapowania](general-electronic-reporting.md#data-model-and-model-mapping-components) i [formatu](general-electronic-reporting.md#FormatComponentOutbound) ER można dodać źródło danych **klasy**, które jest prezentowane jako źródło danych i zwraca wartość typu *klasa*. To źródło danych uwidocznia metody publiczne klasy, które można wywołać w czasie wykonywania.

> [!NOTE]
> Tylko metody, które zwracają wartość, mogą być wywoływane z wyrażeń ER.
>
> Z wyrażeń ER można wywoływać tylko metody o zakresie od zera do ośmiu argumentów.

Domyślna wartość *klasy* ma wartość **null**.

Na poniższej ilustracji pokazano, jak dodano źródło danych **Informacje systemowe (xInfo)** typu **klasa**, aby utworzyć wystąpienie klasy aplikacji **xInfo** i wywołać metodę **productName()** w celu otrzymania nazwy bieżącej aplikacji. Nazwa bieżącej aplikacji jest pobierana w czasie wykonywania poprzez wykonanie powiązania `xInfo.productName`, które zostało skonfigurowane dla pola **Nazwa oprogramowania (SoftwareName)** modelu danych ER. To powiązanie wywołuje metodę `productName()` klasy aplikacji **xInfo**, która jest reprezentowana w bieżącym mapowaniu modelu jako źródło **Informacji systemowych (xInfo)**.

[![Konfigurowanie źródła danych Klasa na stronie Projektant mapowania modelu ER.](./media/er-formula-supported-data-types-composite-class1.gif)](./media/er-formula-supported-data-types-composite-class1.gif)

Poniższa ilustracja pokazuje, jak jest skonfigurowany format ER, aby w generowanych dokumentach umieszczać podaną nazwę aplikacji. Pole **Nazwa oprogramowania (SoftwareName)** używanego modelu danych zostało powiązane ze składnikiem **Ciąg**, który jest zagnieżdżony w elemencie XML **softwareUsed** formatu ER. Tak więc nazwa bieżącej aplikacji jest umieszczana w czasie wykonywania w ramach elementu XML **softwareUsed** wygenerowanego dokumentu w formacie XML.

[![Konfigurowanie struktury elektronicznego dokumentu wychodzącego w konstruktorze formatu ER.](./media/er-formula-supported-data-types-composite-class2.png)](./media/er-formula-supported-data-types-composite-class2.png)

## <a name="container"></a><a name="container"></a>Kontener

Typ danych *kontener* zawiera zawartość binarną. Wartość *kontenera* może służyć do przekazania określonych informacji z magazynu do wygenerowanego dokumentu. W ramach ER ten typ danych jest często używany do wpisywania zawartości multimedialnej, takiej jak logo firmy, w generowanych dokumentach.

> [!NOTE]
> Każdy element multimedialny może być przedstawiany jako wartość *kontenera*, ale nie każdy kontener reprezentuje element *multimedialny*. Dlatego też, jeśli format ER zostanie skonfigurowany tak, że do umieszczenia obrazka w generowanych dokumentach będzie wykorzystywał *kontener*, ale odwołujący się do niego *container* nie zwróci zawartości medialnej, może zostać zwrócony wyjątek przypominający poniższy przykład: „Błąd wykonania kodu: Binary (obiekt), metoda constructFromContainer wywołana z niepoprawnymi parametrami”.

Domyślna wartość *kontenera* ma wartość **null**.

Na poniższej ilustracji pokazano, jak pole **Bitmap(Obraz)** typu *Kontener* jest powiązane z polem **Logo** modelu danych **kontenera** typu Mapowanie modelu **faktury sprzedaży**. To powiązanie udostępnia logo firmy do dowolnego formatu ER, który jest przeznaczony dla definicji katalogu głównego **SalesInvoice** i który używa tego mapowania modelu w czasie wykonywania.

[![Powiązanie pola kontenera typu projektant mapowania modelu ER.](./media/er-formula-supported-data-types-composite-container.png)](./media/er-formula-supported-data-types-composite-container.png)

## <a name="record"></a><a name="record"></a>Zarejestruj

*Rekord* jest kolekcją nazwanych pól, z których każde jest skojarzone z wartością [pierwotnego](er-formula-supported-data-types-primitive.md) typu danych lub złożonego typu danych. Zazwyczaj *rekord* jest używany do reprezentowania pojedynczego rekordu listy rekordów. W takim przypadku każdy element reprezentuje poszczególne pola, metody i relacje.

Domyślna wartość *rekordu* ma wartość **puste**.

> [!NOTE]
> Po otrzymaniu wartości pola pustego *rekordu* zwracana jest wartość domyślna odpowiedniego typu danych.

*Rekord* można uzyskać za pomocą następujących funkcji:

- [FIRST](er-functions-list-first.md)
- [FIRSTORNULL](er-functions-list-firstornull.md)
- [EMPTYRECORD](er-functions-record-emptyrecord.md)
- [NULLCONTAINER](er-functions-record-nullcontainer.md)

Aby uzyskać więcej informacji na temat przekształcania wartości *rekordów*, zobacz [Lista funkcji ER w kategorii listy](er-functions-category-list.md).

## <a name="record-list"></a><a name="record-list"></a>Lista rekordów

*Lista rekordów* to lista elementów typu *rekord*. Zazwyczaj *lista rekordów* jest używana do reprezentowania listy rekordów pobranych z tabeli bazy danych.

Domyślnie rekordy *listy rekordów* są dostępne sekwencyjnie. Aby uzyskać dostęp do określonego rekordu, można użyć funkcji [INDEX](er-functions-list-index.md) i określić indeks *liczby całkowitej*.

Domyślna wartość *listy rekordów* ma wartość **puste**. Za pomocą funkcji [ISEMPTY](/er-functions-list-isempty.md) można ocenić, czy *lista rekordów* jest pusta.

> [!NOTE]
> Jeśli *lista rekordów* jest pusta, każda próba uzyskania wartości pola dla *rekordu* w nim powoduje, że wyjątek jest zgłaszany w czasie wykonywania. Aby dowiedzieć się, jak zapobiec wyjątkom środowiska uruchomieniowego tego typu, zobacz [Rozpatrywanie pustych przypadków listy](er-components-inspections.md#i9).

*Listę rekordów* można rozpocząć za pomocą następujących funkcji:

- [ALLITEMS](er-functions-list-allitems.md)
- [ALLITEMSQUERY](er-functions-list-allitemsquery.md)
- [EMPTYLIST](er-functions-list-emptylist.md)
- [LIST](er-functions-list-list.md)
- [LISTDISTINCT](er-functions-list-listdistinct.md)

Aby uzyskać więcej informacji na temat przekształcania wartości *list rekordów*, zobacz [Lista funkcji ER w kategorii listy](er-functions-category-list.md). Aby dowiedzieć się, jak wprowadzać elementy *listy rekordów*, wypełnij je danymi aplikacji, a następnie użyj tych danych do wygenerowania dokumentów biznesowych, zobacz [Projektowanie nowego rozwiązania ER w celu wydrukowania raportu niestandardowego](er-quick-start1-new-solution.md).

## <a name="object"></a><a name="object"></a>Obiekt

*Obiekt* odwołuje się do wystąpienia stanowego *klasy*. Zwykle *obiekt* jest inicjowany w kodzie źródłowym. Następnie jest przekazywana do mapowania modelu ER i zawiera szczegółowe informacje o kontekście wykonywania.

Domyślna wartość *obiektu* ma wartość **null**.

Na poniższej ilustracji pokazano, jak źródło danych **ReportDataContract** typu *Obiekt* jest dodawane do przekazywania informacji o wygenerowanej fakturze z kodu źródłowego do mapowania modelu **faktury projektu**. Na przykład tekst wystąpienia faktury jest przekazywany jako część kontekstu wykonywania. Ten tekst jest pobierany z kodu źródłowego w czasie wykonywania przez wykonanie powiązania `ReportDataContract.parmInvoiceInstanceText`, które zostało skonfigurowane dla pola **Uwaga** modelu danych ER. To powiązanie wywołuje metodę `parmInvoiceInstanceText()` klasy aplikacji **PSAProjInvoiceContract**, która jest reprezentowana w bieżącym mapowaniu modelu jako źródło **ReportDataContract**.

[![Konfigurowanie źródła danych Obiekt na stronie Projektant mapowania modelu ER.](./media/er-formula-supported-data-types-composite-object.gif)](./media/er-formula-supported-data-types-composite-object.gif)

Aby dowiedzieć się, jak przekazać szczegóły kontekstu wykonywania z kodu źródłowego do uruchomionego rozwiązania ER, zobacz [Tworzenie artefaktów aplikacji, aby wywołać zaprojektowany raport](er-quick-start1-new-solution.md#DevelopCustomCode).

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Język formuł raportowania elektronicznego](er-formula-language.md)
- [Obsługiwane pierwotne typy danych](er-formula-supported-data-types-primitive.md)
