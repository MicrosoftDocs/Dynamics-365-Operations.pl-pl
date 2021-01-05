---
title: Analizowanie dokumentów przychodzących w formacie JSON
description: W tym temacie opisano sposób konfigurowania formatów modułu raportowania elektronicznego (ER) w celu analizy dokumentów przychodzących w formacie notacji obiektów JavaScript (JavaScript).
author: kfend
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b4ed81bb5527ea8e02caaa1262a57960dd7cdf29
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685770"
---
# <a name="parse-incoming-documents-in-json-format"></a><span data-ttu-id="8bbbc-103">Analizowanie dokumentów przychodzących w formacie JSON</span><span class="sxs-lookup"><span data-stu-id="8bbbc-103">Parse incoming documents in JSON format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8bbbc-104">Istnieje możliwość zaprojektowania formatów sprawozdawczości elektronicznej (ER) w celu przeanalizowania przychodzących dokumentów elektronicznych reprezentujących dane w formacie tekstowym opartym na języku JavaScript (innymi słowy — pliki w JavaScript Object Notation w formacie notacji \[JSON\] ).</span><span class="sxs-lookup"><span data-stu-id="8bbbc-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents that represent data in a text format that is based on JavaScript (in other words, files in JavaScript Object Notation \[JSON\] format).</span></span>

<span data-ttu-id="8bbbc-105">Aby dowiedzieć się więcej o tej funkcji, pobierz pliki w poniższej tabeli, a następnie odtwórz ER Utwórz konfigurację formatu w celu zaimportowania danych z zewnętrznego przewodnika zadań pliku JSON.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-105">To learn more about this feature, download the files in the following table, and then play the ER Create a format configuration to import data from an external JSON file task guide.</span></span> <span data-ttu-id="8bbbc-106">W tym podręczniku zadań pokazano, w jaki sposób można użyć formatu ER do przeanalizowania przychodzącego pliku JSON w celu zaktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-106">This task guide shows how an ER format can be used to parse an incoming JSON file to update application data.</span></span>

| <span data-ttu-id="8bbbc-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="8bbbc-107">Title</span></span>                                  | <span data-ttu-id="8bbbc-108">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="8bbbc-108">File name</span></span> |
|----------------------------------------|-----------|
| <span data-ttu-id="8bbbc-109">ER format konfiguracji</span><span class="sxs-lookup"><span data-stu-id="8bbbc-109">ER format configuration</span></span>                | [<span data-ttu-id="8bbbc-110">Format importowania dostawców trans_JSON. XML</span><span class="sxs-lookup"><span data-stu-id="8bbbc-110">Format for importing vendors' trans_JSON.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
| <span data-ttu-id="8bbbc-111">Przykład pliku przychodzącego w formacie .csv</span><span class="sxs-lookup"><span data-stu-id="8bbbc-111">Sample of incoming file in .csv format</span></span> | [<span data-ttu-id="8bbbc-112">1099entries_JSON. txt</span><span class="sxs-lookup"><span data-stu-id="8bbbc-112">1099entries_JSON.txt</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a><span data-ttu-id="8bbbc-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8bbbc-113">Requirements</span></span>

<span data-ttu-id="8bbbc-114">Przed ukończeniem modułu ER Utwórz konfigurację formatu w celu zaimportowania danych z zewnętrznego przewodnika zadań pliku JSON należy spełnić następujące wymagania:</span><span class="sxs-lookup"><span data-stu-id="8bbbc-114">Before you complete the ER Create a format configuration to import data from an external JSON file task guide, the following requirement must be met:</span></span>

- <span data-ttu-id="8bbbc-115">Elementy nadrzędne w pliku JSON mogą być tylko elementami obiektowymi.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-115">Parent elements in the JSON file can be only object elements.</span></span>
- <span data-ttu-id="8bbbc-116">Zagnieżdżone elementy obiektu powinny być elementami właściwości, dzięki czemu tworzona jest prawidłowa struktura JSON.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-116">Nested elements for an object should be property elements, so that a valid JSON structure is created.</span></span>
- <span data-ttu-id="8bbbc-117">Tablice JSON mogą być tylko elementami zagnieżdżonymi elementów właściwości obiektu.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-117">JSON arrays can be only nested elements of the property elements of an object.</span></span>
- <span data-ttu-id="8bbbc-118">Tablice JSON mogą zawierać tylko obiekty JSON.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-118">JSON arrays can contain only JSON objects.</span></span> <span data-ttu-id="8bbbc-119">Nie mogą zawierać bezpośrednich wartości ciągów/liczb i tablic zagnieżdżonych.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-119">They can't contain direct string/numeric values and nested arrays.</span></span> <span data-ttu-id="8bbbc-120">Elementy w tych tablicach zostaną przeanalizowane w kolejności, w jakiej zostały określone w formacie.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-120">Elements in these arrays will be parsed in order, as they are specified in the format.</span></span> <span data-ttu-id="8bbbc-121">Zostaną uwzględnione ustawienia wielokrotności dla każdego obiektu JSON.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-121">Multiplicity settings on each JSON object will be considered.</span></span>

<span data-ttu-id="8bbbc-122">Ponadto, należy wypełnić [ER Utwórz wymagane konfiguracje do zaimportowania danych z zewnętrznego pliku](tasks/er-required-configurations-import-data.md) przewodnik po zadaniach, jeśli jeszcze tego nie wykonano.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-122">Additionally, you must complete the [ER Create required configurations to import data from an external file](tasks/er-required-configurations-import-data.md) task guide if you haven't already completed it.</span></span> <span data-ttu-id="8bbbc-123">Aby ukończyć przewodnik zadań należy pobrać następujący plik.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-123">Download the following file to complete the task guide.</span></span>

| <span data-ttu-id="8bbbc-124">Nazwa</span><span class="sxs-lookup"><span data-stu-id="8bbbc-124">Title</span></span>                  | <span data-ttu-id="8bbbc-125">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="8bbbc-125">File name</span></span> |
|------------------------|-----------|
| <span data-ttu-id="8bbbc-126">Konfiguracja modelu ER</span><span class="sxs-lookup"><span data-stu-id="8bbbc-126">ER model configuration</span></span> | [<span data-ttu-id="8bbbc-127">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="8bbbc-127">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
