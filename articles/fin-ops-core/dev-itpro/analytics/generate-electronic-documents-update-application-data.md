---
title: Generowanie dokumentów elektronicznych i aktualizowanie danych aplikacji przy użyciu modułu ER
description: Można projektować formaty raportowania elektronicznego (ER), które będą używane w aplikacji do generowania wychodzących dokumentów elektronicznych.
author: NickSelin
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 863c69446e9a7d447847483ec129788e85a8fd58
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750041"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a><span data-ttu-id="de760-103">Generowanie dokumentów elektronicznych i aktualizowanie danych aplikacji przy użyciu raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="de760-103">Generate electronic documents and update application data by using ER</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de760-104">Można projektować formaty raportowania elektronicznego (ER), które będą używane w aplikacji do generowania wychodzących dokumentów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="de760-104">You can design Electronic reporting (ER) formats that can be used in the application to generate outgoing electronic documents.</span></span> <span data-ttu-id="de760-105">Można także zaprojektować formaty ER, które analizują składnię przychodzących dokumentów elektronicznych i używają zawartości tych dokumentów do aktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="de760-105">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span>

<span data-ttu-id="de760-106">Dzięki tej funkcjonalności jeden format ER może służyć do generowania wychodzących dokumentów elektronicznych, a następnie aktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="de760-106">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="de760-107">Tej funkcji można używać w następujących scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="de760-107">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="de760-108">Aby uniknąć wielokrotnego wykorzystywania danych aplikacji w kolejnych procesach, można oznaczyć dane aplikacje bezpośrednio po ich użyciu do wygenerowania dokumentów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="de760-108">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="de760-109">Na przykład można oznaczyć transakcje płatności jako już przetworzone natychmiast po ich umieszczeniu w wygenerowanym komunikacie płatniczym.</span><span class="sxs-lookup"><span data-stu-id="de760-109">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="de760-110">Aby zapisać szczegóły przetwarzania dokumentów elektronicznych, które zostały wygenerowane za pomocą logiki modułu ER.</span><span class="sxs-lookup"><span data-stu-id="de760-110">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="de760-111">Na przykład unikatowy identyfikator komunikatu płatniczego wygenerowanego za pomocą wyrażenia ER.</span><span class="sxs-lookup"><span data-stu-id="de760-111">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="de760-112">Wyrażenie bazuje na informacjach wprowadzonych w oknie dialogowym modułu ER po uruchomieniu formatu ER w celu wygenerowania dokumentów.</span><span class="sxs-lookup"><span data-stu-id="de760-112">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="de760-113">Aby dowiedzieć się więcej o tej funkcji, odtwórz przewodniki po zadaniach ER Generowanie dokumentów z aktualizacją danych aplikacji (część 7.5.4.3 procesu biznesowego Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)), które prowadzą przez kolejne etapy procesu sprawozdawczości i archiwizacji Intrastat.</span><span class="sxs-lookup"><span data-stu-id="de760-113">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="de760-114">Następujące pliki są wymagane do wykonania pewnych kroków w tych przewodnikach po zadaniach.</span><span class="sxs-lookup"><span data-stu-id="de760-114">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="de760-115">Pobierz i zapisz te pliki na swoim lokalnym komputerze.</span><span class="sxs-lookup"><span data-stu-id="de760-115">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="de760-116">Konfiguracja modelu danych ER: Intrastat (model)</span><span class="sxs-lookup"><span data-stu-id="de760-116">ER data model configuration: Intrastat (model)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="de760-117">Konfiguracja mapowania modelu ER: Intrastat (mapowanie)</span><span class="sxs-lookup"><span data-stu-id="de760-117">ER model mapping configuration: Intrastat (mapping)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="de760-118">Konfiguracja formatu ER: Intrastat (format)</span><span class="sxs-lookup"><span data-stu-id="de760-118">ER format configuration: Intrastat (format)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]