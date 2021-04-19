---
title: Układ rozsyłania dokumentów dla etykiet numerów identyfikacyjnych
description: W tym temacie opisano sposób używania metod formatowania do drukowania wartości na etykietach.
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: faf54fec2885f868c66987a7b481559d0c5615d0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838281"
---
# <a name="document-routing-layout-for-license-plate-labels"></a><span data-ttu-id="a8bcc-103">Układ rozsyłania dokumentów dla etykiet numerów identyfikacyjnych</span><span class="sxs-lookup"><span data-stu-id="a8bcc-103">Document routing layout for license plate labels</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a8bcc-104">Układ rozsyłania dokumentów określa układ etykiet numeru identyfikacyjnego oraz dane, które są na nich drukowane.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-104">The document routing layout defines the layout of license plate labels, and the data that is printed on them.</span></span> <span data-ttu-id="a8bcc-105">Punkty wyzwalacza drukowania konfiguruje się podczas konfigurowania elementów menu urządzeń przenośnych i szablonów pracy.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-105">You configure the printing trigger points when you set up mobile device menu items and work templates.</span></span>

<span data-ttu-id="a8bcc-106">W typowym scenariuszu pracownik etatowy magazynu drukuje etykiety numerów identyfikacyjnych bezpośrednio po zarejestrowaniu zawartości palet, które przybywają w obszarze przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-106">In a typical scenario, warehouse receiving clerks print license plate labels immediately after they record the contents of pallets that arrive in the receiving area.</span></span> <span data-ttu-id="a8bcc-107">Etykiety fizyczne są używane do oznaczania palet.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-107">The physical labels are applied to the pallets.</span></span> <span data-ttu-id="a8bcc-108">Mogą być one używane do sprawdzania poprawności jako część procesu odłożenia, który następuje, i w przyszłych operacjach pobrania wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-108">They can then be used for validation as part of the put-away process that follows and future outbound picking operations.</span></span>

<span data-ttu-id="a8bcc-109">Można drukować bardzo skomplikowane etykiety, pod warunkiem, że urządzenie drukujące może zinterpretować wysłany do niego tekst.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-109">You can print highly complex labels, provided that the printing device can interpret the text that is sent to it.</span></span> <span data-ttu-id="a8bcc-110">Na przykład układ Zebra Programming Language (ZPL), który zawiera kod kreskowy, może być podobny do poniższego przykładu.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-110">For example, a Zebra Programming Language (ZPL) layout that includes a bar code might resemble the following example.</span></span>

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

<span data-ttu-id="a8bcc-111">W ramach procesu drukowania etykiet tekst `$LicensePlateId$` w tym przykładzie zostanie zastąpiony wartością danych.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-111">As part of the label printing process, the text `$LicensePlateId$` in this example will be replaced with a data value.</span></span>

<span data-ttu-id="a8bcc-112">Aby wyświetlić wartości, które będą drukowane, należy przejść do **Zarządzanie magazynem \> Zapytania i raporty \> Etykiety numerów identyfikacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-112">To see the values that will be printed, go to **Warehouse management \> Inquiries and reports \> License plate labels**.</span></span>

<span data-ttu-id="a8bcc-113">Wiele narzędzi do generowania etykiet ułatwia formatowanie tekstu w układzie etykiety.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-113">Several widely available label generation tools can help you format the text for the label layout.</span></span> <span data-ttu-id="a8bcc-114">Wiele z tych narzędzi obsługuje ten format `$FieldName$`.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-114">Many of these tools support the `$FieldName$` format.</span></span> <span data-ttu-id="a8bcc-115">Ponadto Microsoft Dynamics 365 Supply Chain Management stosuje specjalną logikę formatowania jako część mapowania pól dla układu rozsyłania dokumentów.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-115">In addition, Microsoft Dynamics 365 Supply Chain Management uses special formatting logic as part of the field mapping for the document routing layout.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="a8bcc-116">Włączanie funkcji w systemie</span><span class="sxs-lookup"><span data-stu-id="a8bcc-116">Turn on this feature for your system</span></span>

<span data-ttu-id="a8bcc-117">Jeśli Twój system nie zawiera jeszcze funkcji opisanych w tym temacie, przejdź do [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Ulepszone układy etykiet tablic rejestracyjnych*.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Enhanced license plate label layouts* feature.</span></span>

## <a name="custom-number-formats"></a><span data-ttu-id="a8bcc-118">Niestandardowe formaty liczb</span><span class="sxs-lookup"><span data-stu-id="a8bcc-118">Custom number formats</span></span>

<span data-ttu-id="a8bcc-119">Można dostosować formatowanie wartości pól numerycznych, które są drukowane przy użyciu kodów o następującym formacie:</span><span class="sxs-lookup"><span data-stu-id="a8bcc-119">You can customize the formatting of numerical field values that are printed by using codes that have the following format.</span></span>

```dos
$FieldName:FormatString$
```

<span data-ttu-id="a8bcc-120">Oto wyjaśnienie tego formatu:</span><span class="sxs-lookup"><span data-stu-id="a8bcc-120">Here is an explanation of this format:</span></span>

- <span data-ttu-id="a8bcc-121">`FieldName` to nazwa pola danych (np. **Ilość**).</span><span class="sxs-lookup"><span data-stu-id="a8bcc-121">`FieldName` is the name of the data field (such as **Qty**).</span></span>
- <span data-ttu-id="a8bcc-122">`FormatString` określa sposób, w jaki dane muszą być drukowane.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-122">`FormatString` defines how the data must be printed.</span></span>

<span data-ttu-id="a8bcc-123">Poniższe przykłady pokazują, jak można dostosować wartość w polu Ilość pracy (**Ilość**):</span><span class="sxs-lookup"><span data-stu-id="a8bcc-123">The following examples show how you can customize the work quantity (**Qty**) field:</span></span>

- <span data-ttu-id="a8bcc-124">Aby zawsze były wyświetlane cztery cyfry (przy użyciu zer jako symboli zastępczych), należy użyć formularza `$Qty:0000$`.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-124">To always show four digits (by using zeros as placeholders), use `$Qty:0000$`.</span></span> <span data-ttu-id="a8bcc-125">Na przykład, jeśli ilość wynosi 10, etykieta będzie zawierać „0010”.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-125">For example, if the quantity is 10, the label will show "0010."</span></span>
- <span data-ttu-id="a8bcc-126">Aby zawsze były wyświetlane dwa miejsca dziesiętne, należy zastosować zapis `$Qty:0.00$`.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-126">To always show two decimal places, use `$Qty:0.00$`.</span></span> <span data-ttu-id="a8bcc-127">Na przykład, jeśli ilość wynosi 10, etykieta będzie zawierać „10.00”.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-127">For example, if the quantity is 10, the label will show "10.00."</span></span>

<span data-ttu-id="a8bcc-128">Aby uzyskać pełną listę dostępnych ciągów formatu liczb, zajrzyj do [Niestandardowe ciągi formatów liczb](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span><span class="sxs-lookup"><span data-stu-id="a8bcc-128">For a complete list of the available number format strings, see [Custom numeric format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="custom-string-formats"></a><span data-ttu-id="a8bcc-129">Niestandardowe formaty ciągów</span><span class="sxs-lookup"><span data-stu-id="a8bcc-129">Custom string formats</span></span>

<span data-ttu-id="a8bcc-130">Aby usunąć pierwsze znaki ciągu, należy użyć poniższego pola i kodu formatu.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-130">You can remove the first characters of a string by using the following field and format code.</span></span>

```dos
$FieldName:#..$
```

<span data-ttu-id="a8bcc-131">W tym miejscu `#` jest określana liczba znaków, które mają zostać pominięte.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-131">Here, `#` specifies the number of characters to skip.</span></span> <span data-ttu-id="a8bcc-132">Na przykład, aby wydrukować numer identyfikacyjny Numer seryjny kontenera wysyłkowego (SSCC), który nie zawiera pierwszych dwóch znaków, należy użyć opcji `$LicensePlateId:2..$`.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-132">For example, to print a Serial Shipping Container Code (SSCC) license plate number that doesn't include the first two characters, use `$LicensePlateId:2..$`.</span></span> <span data-ttu-id="a8bcc-133">W takim przypadku numer identyfikacyjny 0011111111111222221 będzie drukowany jako „11111111111222221”.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-133">In this case, the license plate number 0011111111111222221 will be printed as "11111111111222221."</span></span>

## <a name="custom-datetime-formats"></a><span data-ttu-id="a8bcc-134">Niestandardowe formaty daty/godziny</span><span class="sxs-lookup"><span data-stu-id="a8bcc-134">Custom date/time formats</span></span>

<span data-ttu-id="a8bcc-135">W poniższym przykładzie pokazano, jak można kontrolować format używany do drukowania dat.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-135">The following example shows how you can control the format that is used to print dates.</span></span>

```dos
$PrintedDate:dd-MM-yyyy$
```

<span data-ttu-id="a8bcc-136">W tym przykładzie data 30 kwietnia 2020 będzie drukowana jako „30-04-2020”.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-136">In this example, the date April 30, 2020, will be printed as "30-04-2020."</span></span>

<span data-ttu-id="a8bcc-137">Aby uzyskać pełną listę dostępnych formatów daty/czasu, zajrzyj do [Niestandardowe formaty daty/czasu](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="a8bcc-137">For a complete list of the available date/time formats, see [Custom date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="print-individual-lines-from-multiline-data"></a><span data-ttu-id="a8bcc-138">Drukowanie pojedynczych wierszy z danych wielowierszowych</span><span class="sxs-lookup"><span data-stu-id="a8bcc-138">Print individual lines from multiline data</span></span>

<span data-ttu-id="a8bcc-139">Jeśli pole danych zawiera wiele wierszy (czyli wiersze rozdzielone znakami podziału wierszy), można wydrukować pojedynczy wiersz, korzystając z następującego formatu:</span><span class="sxs-lookup"><span data-stu-id="a8bcc-139">If a data field contains multiple lines (that is, lines that are separated by line breaks), you can print an individual line by using the following format.</span></span>

```dos
$FieldName[#]$
```

<span data-ttu-id="a8bcc-140">W tym miejscu `#` jest numer wiersza, który ma zostać wydrukowany.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-140">Here, `#` is the line number that you want to print.</span></span> <span data-ttu-id="a8bcc-141">(Należy zastosować 1 dla pierwszego wiersza.)</span><span class="sxs-lookup"><span data-stu-id="a8bcc-141">(Use 1 for the first line.)</span></span>

<span data-ttu-id="a8bcc-142">Na przykład w systemie znajduje się pole `AdditionalAddress`, w którym jest przechowywany następujący adres wielowierszowy:</span><span class="sxs-lookup"><span data-stu-id="a8bcc-142">For example, your system has an `AdditionalAddress` field that stores the following multiline address:</span></span>

<span data-ttu-id="a8bcc-143">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-143">Contoso Inc.</span></span>  
<span data-ttu-id="a8bcc-144">123 Nazwa ulicy</span><span class="sxs-lookup"><span data-stu-id="a8bcc-144">123 Street Name</span></span>  
<span data-ttu-id="a8bcc-145">Jakieś miasto, Jakiś stan</span><span class="sxs-lookup"><span data-stu-id="a8bcc-145">Some City, Some State</span></span>

<span data-ttu-id="a8bcc-146">Można wydrukować ten adres, po jednym wierszu, używając następujących kodów.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-146">You can print this address, one line at a time, by using the following codes.</span></span>

| <span data-ttu-id="a8bcc-147">Kod</span><span class="sxs-lookup"><span data-stu-id="a8bcc-147">Code</span></span> | <span data-ttu-id="a8bcc-148">Tekst wydrukowany</span><span class="sxs-lookup"><span data-stu-id="a8bcc-148">Text that is printed</span></span> |
|---|---|
| `$AdditionalAddress[1]$` | <span data-ttu-id="a8bcc-149">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-149">Contoso Inc.</span></span> |
| `$AdditionalAddress[2]$` | <span data-ttu-id="a8bcc-150">123 Nazwa ulicy</span><span class="sxs-lookup"><span data-stu-id="a8bcc-150">123 Street Name</span></span> |
| `$AdditionalAddress[3]$` | <span data-ttu-id="a8bcc-151">Jakieś miasto, Jakiś stan</span><span class="sxs-lookup"><span data-stu-id="a8bcc-151">Some City, Some State</span></span> |

## <a name="print-and-format-from-a-display-method"></a><span data-ttu-id="a8bcc-152">Drukowanie i formatowanie za pomocą metody wyświetlania</span><span class="sxs-lookup"><span data-stu-id="a8bcc-152">Print and format from a display method</span></span>

<span data-ttu-id="a8bcc-153">Można drukować za pomocą metody wyświetlania przy użyciu następującego formatu:</span><span class="sxs-lookup"><span data-stu-id="a8bcc-153">You can print from a display method by using the following format.</span></span>

```dos
$DisplayMethod()$
```

<span data-ttu-id="a8bcc-154">Ten format można łączyć z innymi typami opisanymi wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-154">You can combine this format with other types that were described earlier in this topic.</span></span> <span data-ttu-id="a8bcc-155">Na przykład istnieje metoda wyświetlania o nazwie `DisplayListOfItemsNumbers()` i ma zostać wydrukowany pierwszy numer pozycji tej metody.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-155">For example, you have a display method that is named `DisplayListOfItemsNumbers()`, and you want to print the first item number of this method.</span></span> <span data-ttu-id="a8bcc-156">W takim przypadku można użyć następującego kodu.</span><span class="sxs-lookup"><span data-stu-id="a8bcc-156">In this case, you can use the following code.</span></span>

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a><span data-ttu-id="a8bcc-157">Dodatkowe informacje dotyczące sposobu drukowania etykiet</span><span class="sxs-lookup"><span data-stu-id="a8bcc-157">More information about how to print labels</span></span>

<span data-ttu-id="a8bcc-158">Aby uzyskać więcej informacji o konfigurowaniu i drukowaniu etykiet, należy zapoznać się z tematem [Włączanie drukowania etykiet numerów identyfikacyjnych](tasks/license-plate-label-printing.md).</span><span class="sxs-lookup"><span data-stu-id="a8bcc-158">For more information about how to set up and print labels, see [Enable license plate label printing](tasks/license-plate-label-printing.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]