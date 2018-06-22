---
title: "Dzielenie wygenerowanych plików na podstawie rozmiaru pliku i ilości treści"
description: "Ten temat zawiera informacje dotyczące dzielenia plików generowanych na podstawie rozmiaru pliku i ilości elementu zawartości."
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: afdf5b2596af7641182be50ced8159967164b115
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2018

---

# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a><span data-ttu-id="a40ab-103">Dzielenie wygenerowanych plików XML na podstawie rozmiaru pliku i ilości treści</span><span class="sxs-lookup"><span data-stu-id="a40ab-103">Split generated XML files based on file size and content quantity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a40ab-104">Można zaprojektować formaty raportów elektronicznych ER w taki sposób, aby generowały wychodzące dokumenty w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="a40ab-104">You can design Electronic reporting (ER) formats to generate outgoing documents in XML format.</span></span> <span data-ttu-id="a40ab-105">Czasami te dokumenty mogą być akceptowane tylko wtedy, gdy spełniają określone kryteria, np. maksymalnego rozmiaru pliku lub maksymalnej liczby niektórych węzłów XML.</span><span class="sxs-lookup"><span data-stu-id="a40ab-105">Sometimes, those documents can be accepted only when they meet specific criteria, such a maximum file size or a maximum number of some XML nodes.</span></span> <span data-ttu-id="a40ab-106">Można zaprojektować formaty ER w taki sposób, aby generowały dokumenty elektroniczne zgodnie z wymogami wyznaczonymi przez ich odbiorców.</span><span class="sxs-lookup"><span data-stu-id="a40ab-106">You can design ER formats to generate electronic documents that satisfy the requirements that the recipients of those documents specify.</span></span>

- <span data-ttu-id="a40ab-107">Dla elementu formatu FILE można zdefiniować limit rozmiaru pliku jako wyrażenie ER.</span><span class="sxs-lookup"><span data-stu-id="a40ab-107">For the FILE format element, you can define a limit on the file size as an ER expression.</span></span> <span data-ttu-id="a40ab-108">Jeśli zdefiniowany limit zostanie przekroczony podczas generowania raportu modułu ER, moduł ER zakończy tworzenie bieżącego pliku, a następnie przejdzie do tworzenia następnego pliku.</span><span class="sxs-lookup"><span data-stu-id="a40ab-108">If the defined limit is exceeded when an ER report is generated, ER finishes creating the current file and then moves on to create the next file.</span></span>
- <span data-ttu-id="a40ab-109">Dla każdego elementu formatu XML ELEMENT można zdefiniować limit liczby elementów jako wyrażenie ER.</span><span class="sxs-lookup"><span data-stu-id="a40ab-109">For any XML ELEMENT format, you can define a limit on the number of elements as an ER expression.</span></span> <span data-ttu-id="a40ab-110">Jeśli liczba węzłów XML w wygenerowanym pliku przekracza zdefiniowany limit podczas tworzenia raportu modułu ER, moduł ER zakończy tworzenie bieżącego pliku, a następnie przejdzie do tworzenia następnego pliku.</span><span class="sxs-lookup"><span data-stu-id="a40ab-110">If the number of XML nodes in the file that is generated exceeds the defined limit when an ER report is run, ER finishes creating the current file and then moves on to create the next file.</span></span>
- <span data-ttu-id="a40ab-111">Dla każdego elementu formatu XML SEQUENCE można zdefiniować limit liczby elementów podrzędnych jako wyrażenie ER.</span><span class="sxs-lookup"><span data-stu-id="a40ab-111">For any XML SEQUENCE format element, you can define a limit on the number of child elements as an ER expression.</span></span> <span data-ttu-id="a40ab-112">Jeśli liczba zagnieżdżonych węzłów XML elementu formatu w wygenerowanym pliku przekracza zdefiniowany limit podczas tworzenia raportu modułu ER, moduł ER zakończy tworzenie bieżącego pliku, a następnie przejdzie do tworzenia następnego pliku.</span><span class="sxs-lookup"><span data-stu-id="a40ab-112">If the number of nested XML nodes of the format element in the generated file exceeds the defined limit when an ER report is run, ER finishes creating the current file and then moves on to create the next file.</span></span>
- <span data-ttu-id="a40ab-113">Można zaznaczyć dowolny element formatu XML ELEMENT jako nieprzenoszony.</span><span class="sxs-lookup"><span data-stu-id="a40ab-113">You can mark any XML ELEMENT format element as non-breakable.</span></span> <span data-ttu-id="a40ab-114">W ten sposób można zachować zagnieżdżone obiekty węzłów XML, które zostały wygenerowane pod elementem formatu, w jednym pliku.</span><span class="sxs-lookup"><span data-stu-id="a40ab-114">In this way, you can keep the nested items of XML nodes that are generated under the format element in a single generated file.</span></span>

<span data-ttu-id="a40ab-115">Poza używaniem elementów formatu XML ELEMENT i XML SEQUENCE w celu dodania węzłów kodu źródłowego XML do wygenerowanego pliku można również używać elementu formatu XML RAW.</span><span class="sxs-lookup"><span data-stu-id="a40ab-115">In addition to using the XML ELEMENT and XML SEQUENCE format elements to add XML nodes to the generated file, you can use the RAW XML format element.</span></span> <span data-ttu-id="a40ab-116">Jednak węzły dodawane przy użyciu elementu formatu XML RAW nie są brane pod uwagę podczas obliczania liczby węzłów w celu oceny przestrzegania ograniczenia liczby elementów.</span><span class="sxs-lookup"><span data-stu-id="a40ab-116">However, nodes that you add by using the RAW XML format element aren't considered when the number of nodes is calculated to evaluate the limits on the number of elements.</span></span>

<span data-ttu-id="a40ab-117">Jeśli skonfigurowano plikowe miejsca docelowe dla elementu formatu FILE, w którym ustawiono dzielenie wygenerowanych danych wyjściowych po każdym przekroczeniu określonego limitu, każda część wygenerowanych danych wyjściowych jest wysyłana do skonfigurowanego plikowego miejsca docelowego jako osobny plik.</span><span class="sxs-lookup"><span data-stu-id="a40ab-117">If you configured file destinations for a FILE format element that has been configured to split the generated output whenever specific limits are exceeded, each piece of generated output is sent to the configured file destination as an individual file.</span></span> <span data-ttu-id="a40ab-118">Aby nadać niepowtarzalne nazwy plików, które są tworzone przez podział danych wyjściowych, należy skonfigurować wyrażenie RE dla elementu formatu pliku.</span><span class="sxs-lookup"><span data-stu-id="a40ab-118">To uniquely name the files that are created by splitting the output, you must configure an ER expression for the FILE format element.</span></span> <span data-ttu-id="a40ab-119">Po dołączeniu źródła danych raportowania elektronicznego o typie NUMERACJA numer będzie zwiększany dla każdego kolejnego fragmentu podzielonych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="a40ab-119">If you include an ER data source of the NUMBER SEQUENCE type, the number sequence will be incremented for each piece of the split output.</span></span>

<span data-ttu-id="a40ab-120">Aby dowiedzieć się więcej o tej funkcji, należy odtworzyć przewodnik po zadaniach **pliki XML podziału ER na podstawie rozmiaru pliku lub ilość zawartości pozycji**, wchodzący w skład procesu biznesowego **7.5.4.3 Pobierania/opracowywanie składników usług/rozwiązań informatycznych (10677)** i można go pobrać z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="a40ab-120">To learn more about this feature, play the **ER Split XML files based on the file size or content item quantity** task guide, which is part of the **7.5.4.3 Acquire/Develop IT service/solution components (10677)** business process and can be downloaded from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span> <span data-ttu-id="a40ab-121">Ten przewodnik zadania przeprowadzi Cię przez proces konfigurowania formatu ER w celu podzielenia wygenerowanych plików na podstawie ograniczeń rozmiaru pliku i ilości pozycji zawartości.</span><span class="sxs-lookup"><span data-stu-id="a40ab-121">This task guide walks you through the process of configuring an ER format to split generated files based on limits on the file size and content item quantity.</span></span> <span data-ttu-id="a40ab-122">Aby ukończyć przewodnik po zadaniach, należy pobrać następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="a40ab-122">To complete the task guide, you must download the following files:</span></span>

- [<span data-ttu-id="a40ab-123">Konfiguracja modelu ER — XmlFilesSplittingModel.xml</span><span class="sxs-lookup"><span data-stu-id="a40ab-123">ER model configuration - XmlFilesSplittingModel.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111)
- [<span data-ttu-id="a40ab-124">Konfiguracja formatu ER — XmlFilesSplittingFormat.xml</span><span class="sxs-lookup"><span data-stu-id="a40ab-124">ER format configuration - XmlFilesSplittingFormat.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111)

## <a name="additional-resources"></a><span data-ttu-id="a40ab-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a40ab-125">Additional resources</span></span>
[<span data-ttu-id="a40ab-126">Aplikacje docelowe Raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="a40ab-126">Electronic reporting destinations</span></span>](electronic-reporting-destinations.md)

[<span data-ttu-id="a40ab-127">Projektant formuł w Raportowaniu elektronicznym</span><span class="sxs-lookup"><span data-stu-id="a40ab-127">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)


