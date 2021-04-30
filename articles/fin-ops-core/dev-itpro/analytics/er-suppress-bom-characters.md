---
title: Projektowanie konfiguracji ER w celu pomijania znaków BOM w generowanych plikach
description: W tym temacie wyjaśniono, jak skonfigurować format raportowania elektronicznego (ER) w celu generowania raportów pomijających znaki typu znacznik kolejności bajtów (BOM).
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5ada93c0192aadac70c38c8c8c4f3af86ff6fc3
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893283"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a><span data-ttu-id="28fd5-103">Projektowanie konfiguracji ER w celu pomijania znaków BOM w generowanych plikach</span><span class="sxs-lookup"><span data-stu-id="28fd5-103">Design ER configurations to suppress BOM characters in generated files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28fd5-104">Możesz w module [Raportowanie elektronicznej (ER)](general-electronic-reporting.md) zaprojektować [rozwiązanie](er-quick-start1-new-solution.md) do generowania dokumentów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="28fd5-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md) to generate outgoing documents.</span></span> <span data-ttu-id="28fd5-105">Aby wygenerować dokumenty jako pliki tekstowe lub XML, rozwiązanie musi zawierać [konfigurację](general-electronic-reporting.md#Configuration) ER zawierającą składnik [formatu](general-electronic-reporting.md#FormatComponentOutbound) ER.</span><span class="sxs-lookup"><span data-stu-id="28fd5-105">To generate the documents as text or XML files, the solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="28fd5-106">Aby określić [kodowanie znaków](/windows/win32/intl/character-sets) reprezentujące zestaw znaków w generowanych plikach, format ER musi zawierać element formatu pliku **Wspólne\\Plik**.</span><span class="sxs-lookup"><span data-stu-id="28fd5-106">To specify the [character encoding](/windows/win32/intl/character-sets) that represents the set of characters in generated files, the ER format must contain the **Common\\File** format element.</span></span> <span data-ttu-id="28fd5-107">Aby skonfigurować składnik formatu ER, należy otworzyć [wersję roboczą](general-electronic-reporting.md#component-versioning) utworzonej konfiguracji ER w projektancie formatów ER i dodać element **Wspólne\\Plik**.</span><span class="sxs-lookup"><span data-stu-id="28fd5-107">To configure the ER format component, open the [draft](general-electronic-reporting.md#component-versioning) version of the ER configuration in the ER format designer, and add the **Common\\File** element.</span></span> <span data-ttu-id="28fd5-108">W polu **Kodowanie** określ kodowanie plików wychodzących generowanych w czasie wykonywania za pomocą tego składnika.</span><span class="sxs-lookup"><span data-stu-id="28fd5-108">In the **Encoding** field, specify the encoding of outbound files that are generated at runtime by using this component.</span></span>

> [!NOTE]
> <span data-ttu-id="28fd5-109">Jeśli format zawiera niepoprawną nazwę kodowania, podczas zapisywania zmian ustawień formatu zgłaszany jest błąd.</span><span class="sxs-lookup"><span data-stu-id="28fd5-109">If the format contains an incorrect encoding name, an error is thrown when you save your changes to the format's settings.</span></span>

![Dodawanie elementu głównego na stronie Projektant formatów](./media/er-suppress-bom-characters-image1.gif)

<span data-ttu-id="28fd5-111">Jeśli wybierzesz kodowanie **UTF-8**, **UTF-16** lub **UTF-32**, opcja **Pomiń znaki BOM** stanie się dostępna.</span><span class="sxs-lookup"><span data-stu-id="28fd5-111">If you specify **UTF-8**, **UTF-16**, or **UTF-32** as the encoding, the **Suppress BOM characters** option becomes available.</span></span> <span data-ttu-id="28fd5-112">Ustaw tę opcję na wartość **Tak**, aby pomijać [znaki znaczników kolejności bajtów (BOM)](/globalization/encoding/byte-order-mark) w plikach wychodzących, które są generowane w czasie wykonywania po uruchomieniu edytowalnego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="28fd5-112">Set this option to **Yes** to suppress [byte order mark (BOM) characters](/globalization/encoding/byte-order-mark) in outbound files that are generated at runtime when the editable ER format is run.</span></span>

> [!NOTE]
> <span data-ttu-id="28fd5-113">Jeśli pole **Kodowanie** pozostanie puste, będzie używane domyślne kodowanie **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="28fd5-113">If you leave the **Encoding** field blank, the default **UTF-8** encoding is used.</span></span>

![Ustawianie opcji Pomiń znaki BOM na stronie Projektant formatów](./media/er-suppress-bom-characters-image2.gif)

<span data-ttu-id="28fd5-115">Aby przejrzeć funkcje w czasie wykonywania, należy wykonać odpowiednią procedurę.</span><span class="sxs-lookup"><span data-stu-id="28fd5-115">To review the functionality at runtime, complete the appropriate procedure.</span></span> <span data-ttu-id="28fd5-116">Na przykład wykonaj kroki w temacie [Odraczanie wykonania elementów XML w formatach ER](er-defer-xml-element.md).</span><span class="sxs-lookup"><span data-stu-id="28fd5-116">For example, complete the steps in the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic.</span></span> <span data-ttu-id="28fd5-117">Po ukończeniu kroków z sekcji [Modyfikowanie formatu, aby obliczenie było oparte na wygenerowanych danych wyjściowych](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) tego tematu należy wykonać następujące dodatkowe kroki.</span><span class="sxs-lookup"><span data-stu-id="28fd5-117">After you've completed the steps in the [Modify the format so that the calculation is based on generated output](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) section of that topic, follow these additional steps.</span></span>

1. <span data-ttu-id="28fd5-118">Określ kodowanie UTF:</span><span class="sxs-lookup"><span data-stu-id="28fd5-118">Specify the UTF encoding:</span></span>

    1. <span data-ttu-id="28fd5-119">Wybierz element **Raport** typu **Wspólne\\Plik**.</span><span class="sxs-lookup"><span data-stu-id="28fd5-119">Select the **Report** element of the **Common\\File** type.</span></span>
    2. <span data-ttu-id="28fd5-120">W polu **Kodowanie** określ kodowanie **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="28fd5-120">In the **Encoding** field, specify the **UTF-8** encoding.</span></span>

2. <span data-ttu-id="28fd5-121">Wygeneruj plik XML, który zawiera znak BOM:</span><span class="sxs-lookup"><span data-stu-id="28fd5-121">Generate an XML file that includes a BOM character:</span></span>

    1. <span data-ttu-id="28fd5-122">Ustaw opcję **Pomiń znaki BOM** na **Nie**, aby w generowanych plikach XML uwzględnić znaki BOM.</span><span class="sxs-lookup"><span data-stu-id="28fd5-122">Set the **Suppress BOM characters** option to **No** to include BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="28fd5-123">Wykonaj kroki w sekcji [Odraczanie wykonania zbiorczego elementu XML, tak aby była używana obliczona suma](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) tematu [Odraczanie wykonania elementów XML w formatach ER](er-defer-xml-element.md) i zapisz wygenerowany plik jako **SampleXmlReport.xml**.</span><span class="sxs-lookup"><span data-stu-id="28fd5-123">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport.xml**.</span></span>

3. <span data-ttu-id="28fd5-124">Wygeneruj plik XML, który nie zawiera znaku BOM:</span><span class="sxs-lookup"><span data-stu-id="28fd5-124">Generate an XML file that doesn't include a BOM character:</span></span>

    1. <span data-ttu-id="28fd5-125">Ustaw opcję **Pomiń znaki BOM** na **Tak**, aby w generowanych plikach XML pomijać znaki BOM.</span><span class="sxs-lookup"><span data-stu-id="28fd5-125">Set the **Suppress BOM characters** option to **Yes** to suppress BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="28fd5-126">Wykonaj kroki w sekcji [Odraczanie wykonania zbiorczego elementu XML, tak aby była używana obliczona suma](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) tematu [Odraczanie wykonania elementów XML w formatach ER](er-defer-xml-element.md) i zapisz wygenerowany plik jako **SampleXmlReport (1).xml**.</span><span class="sxs-lookup"><span data-stu-id="28fd5-126">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport (1).xml**.</span></span>

4. <span data-ttu-id="28fd5-127">W narzędziu do porównywania plików porównaj wygenerowane pliki.</span><span class="sxs-lookup"><span data-stu-id="28fd5-127">In a file comparison utility, compare the generated files.</span></span>

    <span data-ttu-id="28fd5-128">Pierwsza różnica, która zostanie zauważona, znajduje się w nagłówku pliku.</span><span class="sxs-lookup"><span data-stu-id="28fd5-128">The first difference that you will notice is in the file header.</span></span> <span data-ttu-id="28fd5-129">Plik SampleXmlReport.xml zawiera znak BOM, a plik SampleXmlReport (1).xml nie.</span><span class="sxs-lookup"><span data-stu-id="28fd5-129">The SampleXmlReport.xml file contains a BOM character, where the SampleXmlReport (1).xml file doesn't.</span></span>

    ![Porównywanie wygenerowanych plików przy użyciu narzędzia do porównywania plików](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a><span data-ttu-id="28fd5-131">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="28fd5-131">See also</span></span>

- [<span data-ttu-id="28fd5-132">Odłóż wykonanie elementów XML w formatach raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="28fd5-132">Defer the execution of XML elements in ER formats</span></span>](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]