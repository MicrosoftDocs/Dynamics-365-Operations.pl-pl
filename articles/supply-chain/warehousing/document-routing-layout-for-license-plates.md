---
title: Układ rozsyłania dokumentów dla etykiet numerów identyfikacyjnych
description: W tym temacie opisano sposób używania metod formatowania do drukowania wartości na etykietach.
author: perlynne
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 66ba73ab5c790aa4a67419842f63f6f741bf0d3a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973767"
---
# <a name="document-routing-layout-for-license-plate-labels"></a>Układ rozsyłania dokumentów dla etykiet numerów identyfikacyjnych

[!include [banner](../includes/banner.md)]

Układ rozsyłania dokumentów określa układ etykiet numeru identyfikacyjnego oraz dane, które są na nich drukowane. Punkty wyzwalacza drukowania konfiguruje się podczas konfigurowania elementów menu urządzeń przenośnych i szablonów pracy.

W typowym scenariuszu pracownik etatowy magazynu drukuje etykiety numerów identyfikacyjnych bezpośrednio po zarejestrowaniu zawartości palet, które przybywają w obszarze przyjęcia. Etykiety fizyczne są używane do oznaczania palet. Mogą być one używane do sprawdzania poprawności jako część procesu odłożenia, który następuje, i w przyszłych operacjach pobrania wychodzącego.

Można drukować bardzo skomplikowane etykiety, pod warunkiem, że urządzenie drukujące może zinterpretować wysłany do niego tekst. Na przykład układ Zebra Programming Language (ZPL), który zawiera kod kreskowy, może być podobny do poniższego przykładu.

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

W ramach procesu drukowania etykiet tekst `$LicensePlateId$` w tym przykładzie zostanie zastąpiony wartością danych.

Aby wyświetlić wartości, które będą drukowane, należy przejść do **Zarządzanie magazynem \> Zapytania i raporty \> Etykiety numerów identyfikacyjnych**.

Wiele narzędzi do generowania etykiet ułatwia formatowanie tekstu w układzie etykiety. Wiele z tych narzędzi obsługuje ten format `$FieldName$`. Ponadto Microsoft Dynamics 365 Supply Chain Management stosuje specjalną logikę formatowania jako część mapowania pól dla układu rozsyłania dokumentów.

## <a name="custom-number-formats"></a>Niestandardowe formaty liczb

Można dostosować formatowanie wartości pól numerycznych, które są drukowane przy użyciu kodów o następującym formacie:

```dos
$FieldName:FormatString$
```

Oto wyjaśnienie tego formatu:

- `FieldName` to nazwa pola danych (np. **Ilość**).
- `FormatString` określa sposób, w jaki dane muszą być drukowane.

Poniższe przykłady pokazują, jak można dostosować wartość w polu Ilość pracy (**Ilość**):

- Aby zawsze były wyświetlane cztery cyfry (przy użyciu zer jako symboli zastępczych), należy użyć formularza `$Qty:0000$`. Na przykład, jeśli ilość wynosi 10, etykieta będzie zawierać „0010”.
- Aby zawsze były wyświetlane dwa miejsca dziesiętne, należy zastosować zapis `$Qty:0.00$`. Na przykład, jeśli ilość wynosi 10, etykieta będzie zawierać „10.00”.

Aby uzyskać pełną listę dostępnych ciągów formatu liczb, zajrzyj do [Niestandardowe ciągi formatów liczb](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).

## <a name="custom-string-formats"></a>Niestandardowe formaty ciągów

Aby usunąć pierwsze znaki ciągu, należy użyć poniższego pola i kodu formatu.

```dos
$FieldName:#..$
```

W tym miejscu `#` jest określana liczba znaków, które mają zostać pominięte. Na przykład, aby wydrukować numer identyfikacyjny Numer seryjny kontenera wysyłkowego (SSCC), który nie zawiera pierwszych dwóch znaków, należy użyć opcji `$LicensePlateId:2..$`. W takim przypadku numer identyfikacyjny 0011111111111222221 będzie drukowany jako „11111111111222221”.

## <a name="custom-datetime-formats"></a>Niestandardowe formaty daty/godziny

W poniższym przykładzie pokazano, jak można kontrolować format używany do drukowania dat.

```dos
$PrintedDate:dd-MM-yyyy$
```

W tym przykładzie data 30 kwietnia 2020 będzie drukowana jako „30-04-2020”.

Aby uzyskać pełną listę dostępnych formatów daty/czasu, zajrzyj do [Niestandardowe formaty daty/czasu](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="print-individual-lines-from-multiline-data"></a>Drukowanie pojedynczych wierszy z danych wielowierszowych

Jeśli pole danych zawiera wiele wierszy (czyli wiersze rozdzielone znakami podziału wierszy), można wydrukować pojedynczy wiersz, korzystając z następującego formatu:

```dos
$FieldName[#]$
```

W tym miejscu `#` jest numer wiersza, który ma zostać wydrukowany. (Należy zastosować 1 dla pierwszego wiersza.)

Na przykład w systemie znajduje się pole `AdditionalAddress`, w którym jest przechowywany następujący adres wielowierszowy:

Contoso Inc.  
123 Nazwa ulicy  
Jakieś miasto, Jakiś stan

Można wydrukować ten adres, po jednym wierszu, używając następujących kodów.

| Kod | Tekst wydrukowany |
|---|---|
| `$AdditionalAddress[1]$` | Contoso Inc. |
| `$AdditionalAddress[2]$` | 123 Nazwa ulicy |
| `$AdditionalAddress[3]$` | Jakieś miasto, Jakiś stan |

## <a name="print-and-format-from-a-display-method"></a>Drukowanie i formatowanie za pomocą metody wyświetlania

Można drukować za pomocą metody wyświetlania przy użyciu następującego formatu:

```dos
$DisplayMethod()$
```

Ten format można łączyć z innymi typami opisanymi wcześniej w tym temacie. Na przykład istnieje metoda wyświetlania o nazwie `DisplayListOfItemsNumbers()` i ma zostać wydrukowany pierwszy numer pozycji tej metody. W takim przypadku można użyć następującego kodu.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>Dodatkowe informacje dotyczące sposobu drukowania etykiet

Aby uzyskać więcej informacji o konfigurowaniu i drukowaniu etykiet, należy zapoznać się z tematem [Włączanie drukowania etykiet numerów identyfikacyjnych](tasks/license-plate-label-printing.md).
