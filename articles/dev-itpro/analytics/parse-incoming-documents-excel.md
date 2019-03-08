---
title: Analizowanie dokumentów przychodzących w formacie programu Excel
description: Ten temat zawiera informacje na temat projektowania formatów raportowania elektronicznego (RE), aby przeanalizować zawartość znajdującą się w przychodzących plikach programu Microsoft Excel.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 490a9325be25908564a40478a1ee29feea67fc02
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "367485"
---
# <a name="parse-incoming-documents-in-excel-format"></a><span data-ttu-id="0c05b-103">Analizowanie dokumentów przychodzących w formacie programu Excel</span><span class="sxs-lookup"><span data-stu-id="0c05b-103">Parse incoming documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0c05b-104">Można zaprojektować formaty raportów elektronicznych ER w taki sposób, aby analizowały przychodzące pliki programu Microsoft Excel reprezentujące dane skoroszytów programu Microsoft Excel (pliki w formacie XLSX).</span><span class="sxs-lookup"><span data-stu-id="0c05b-104">You can design Electronic reporting (ER) formats to parse incoming Microsoft Excel files that represent data in Microsoft Excel workbooks (files in XLSX format).</span></span> <span data-ttu-id="0c05b-105">Następnie można użyć zawartości tych plików do aktualizacji danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0c05b-105">You can then use the content from these files to update application data.</span></span> <span data-ttu-id="0c05b-106">Jest to użyteczne w następujących przypadkach:</span><span class="sxs-lookup"><span data-stu-id="0c05b-106">This is useful if you:</span></span>

- <span data-ttu-id="0c05b-107">Projektujesz nowy model i format i chcesz je przetestować w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="0c05b-107">Design a new model and format and want to test them at run-time.</span></span> <span data-ttu-id="0c05b-108">W tym wypadku program Excel będzie symulował rzeczywiste dane aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0c05b-108">In this case, Excel will simulate the actual application data.</span></span>
- <span data-ttu-id="0c05b-109">Zarządzasz danymi poza aplikacją w programie Excel i chcesz zaimportować te dane, aby przesłać określony raport.</span><span class="sxs-lookup"><span data-stu-id="0c05b-109">Manage data beyond your application in Excel and want to import this data to submit a specific report.</span></span>

<span data-ttu-id="0c05b-110">Aby dowiedzieć się więcej o tej funkcji, odtwórz przewodników po zadaniach **ER importowanie danych z pliku programu Microsoft Excel (część 1: format projektu)** i **ER importowanie danych z pliku programu Microsoft Excel (część 2: importowanie danych)** (części procesu biznesowego 7.5.4.3 Pobierania/opracowywanie składników usług/rozwiązań informatycznych (10677)).</span><span class="sxs-lookup"><span data-stu-id="0c05b-110">To learn more about this feature, play the task guides **ER Import data from a Microsoft Excel file (Part 1: Design format)** and **ER Import data from a Microsoft Excel file (Part 2: Import data)** (parts of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span> <span data-ttu-id="0c05b-111">Te wskazówki zadania pokażą Ci, jak można przeanalizować przychodzący plik Excel przy użyciu formatu ER, aby zaimportować informacje z dokumentów przychodzących i zaktualizować dane aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0c05b-111">These task guides walk through how the incoming Excel file can be parsed by using the ER format to import information from incoming documents and update application data.</span></span> <span data-ttu-id="0c05b-112">Możesz pobrać pliki przewodnika zadań z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="0c05b-112">You can download the task guide files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

<span data-ttu-id="0c05b-113">Aby ukończyć przewodnik po zadaniach wymienione powyżej, należy pobrać następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="0c05b-113">Download the following files to complete the task guides mentioned above.</span></span>

| <span data-ttu-id="0c05b-114">Opis zawartości</span><span class="sxs-lookup"><span data-stu-id="0c05b-114">Content description</span></span>                         | <span data-ttu-id="0c05b-115">Plik</span><span class="sxs-lookup"><span data-stu-id="0c05b-115">File</span></span>                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="0c05b-116">Przychodzący plik w formacie .XLSX — szablon</span><span class="sxs-lookup"><span data-stu-id="0c05b-116">Incoming file in .XLSX format - template</span></span>    | [<span data-ttu-id="0c05b-117">1099import-template.xlsx</span><span class="sxs-lookup"><span data-stu-id="0c05b-117">1099import-template.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
| <span data-ttu-id="0c05b-118">Przychodzący plik w formacie .XLSX — przykładowe dane</span><span class="sxs-lookup"><span data-stu-id="0c05b-118">Incoming file in .XLSX format - sample data</span></span> | [<span data-ttu-id="0c05b-119">1099import-data.xlsx</span><span class="sxs-lookup"><span data-stu-id="0c05b-119">1099import-data.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)     |

<span data-ttu-id="0c05b-120">Jeśli jeszcze nie odtwarzano przewodnika po zadaniu [ER Tworzenie wymaganych konfiguracji do importowania danych z pliku zewnętrznego](./tasks/er-required-configurations-import-data.md) w bieżącej aplikacji Dynamics 365 for Finance and Operation, pobierz następujący plik:</span><span class="sxs-lookup"><span data-stu-id="0c05b-120">If you have not yet played the following task guide, [ER Create required configurations to import data from an external file](./tasks/er-required-configurations-import-data.md) in the current Dynamics 365 for Finance and Operation application, download the following file.</span></span>

| <span data-ttu-id="0c05b-121">Opis zawartości</span><span class="sxs-lookup"><span data-stu-id="0c05b-121">Content description</span></span>    | <span data-ttu-id="0c05b-122">Plik</span><span class="sxs-lookup"><span data-stu-id="0c05b-122">File</span></span>                                                            |
|------------------------|-----------------------------------------------------------------|
| <span data-ttu-id="0c05b-123">Konfiguracja modelu ER</span><span class="sxs-lookup"><span data-stu-id="0c05b-123">ER model configuration</span></span> | [<span data-ttu-id="0c05b-124">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="0c05b-124">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
