---
title: Projektowanie konfiguracji w celu generowania dokumentów zawierających dane aplikacji
description: W tym temacie opisano sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego. (część 1 — importowanie konfiguracji).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 417c419dc6925bac337fe74a2f057395316ec75d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092929"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a><span data-ttu-id="cb015-104">Projektowanie konfiguracji w celu generowania dokumentów zawierających dane aplikacji</span><span class="sxs-lookup"><span data-stu-id="cb015-104">Design configurations to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cb015-105">Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 1: Importowanie konfiguracji)”.</span><span class="sxs-lookup"><span data-stu-id="cb015-105">To complete the steps in this procedure, you must first complete the procedure, ER Generate documents with application data update (Part 1: Import configurations).</span></span>



<span data-ttu-id="cb015-106">Etapy w tej procedurze wyjaśniają sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="cb015-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="cb015-107">W tej procedurze uruchomisz zaimportowaną konfigurację formatu ER, którą utworzono dla przykładowej firmy Litware, Inc., w celu wygenerowania dokumentów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="cb015-107">In this procedure, you run the ER imported format configuration that has been created for the sample company, Litware, Inc. to generate electronic documents.</span></span>



<span data-ttu-id="cb015-108">Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="cb015-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="cb015-109">Kroki można wykonać przy użyciu zestawu danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="cb015-109">These steps can be completed using the DEMF dataset.</span></span> 



<span data-ttu-id="cb015-110">Przed rozpoczęciem zmień kontekst kraju firmy DEMF z DEU (Niemcy) na BEL (Belgia).</span><span class="sxs-lookup"><span data-stu-id="cb015-110">Before you begin, change the country context for the DEMF company from DEU (Germany) to BEL (Belgium).</span></span> <span data-ttu-id="cb015-111">Kliknij kolejno opcje Administrowanie organizacją > Organizacje > Firmy i zaktualizuj kod kraju w podstawowym adresie firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="cb015-111">Click Organization administration > Organizations > Legal entities to update the country code in the primary address of the legal entity DEMF.</span></span> <span data-ttu-id="cb015-112">Następnie ponownie uruchom aplikację.</span><span class="sxs-lookup"><span data-stu-id="cb015-112">Restart your application.</span></span>


## <a name="run-imported-er-format"></a><span data-ttu-id="cb015-113">Uruchamianie zaimportowanego formatu ER</span><span class="sxs-lookup"><span data-stu-id="cb015-113">Run imported ER format</span></span>
1. <span data-ttu-id="cb015-114">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="cb015-114">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="cb015-115">W drzewie rozwiń węzeł „Intrastat (model)”.</span><span class="sxs-lookup"><span data-stu-id="cb015-115">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="cb015-116">W drzewie zaznacz element „Intrastat (model)\Intrastat (format)”.</span><span class="sxs-lookup"><span data-stu-id="cb015-116">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="cb015-117">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="cb015-117">Click Run.</span></span>
    * <span data-ttu-id="cb015-118">Uruchom wersję roboczą konfiguracji formatu ER, aby wygenerować raport Intrastat.</span><span class="sxs-lookup"><span data-stu-id="cb015-118">Run the draft version of the ER format configuration to generate the Intrastat report.</span></span>  
5. <span data-ttu-id="cb015-119">W polu Wprowadź nazwę pliku wpisz „intrastat.xml”.</span><span class="sxs-lookup"><span data-stu-id="cb015-119">In the Enter file name field, type 'intrastat.xml'.</span></span>
    * <span data-ttu-id="cb015-120">Nadaj plikowi nazwę.</span><span class="sxs-lookup"><span data-stu-id="cb015-120">Specify the name of the file.</span></span>  
6. <span data-ttu-id="cb015-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cb015-121">Click OK.</span></span>
    * <span data-ttu-id="cb015-122">Przejrzyj wygenerowany plik XML.</span><span class="sxs-lookup"><span data-stu-id="cb015-122">Review the generated XML file.</span></span>  
7. <span data-ttu-id="cb015-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cb015-123">Close the page.</span></span>
8. <span data-ttu-id="cb015-124">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="cb015-124">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="cb015-125">Otwórz ten formularz, aby wyświetlić transakcje Intrastat zawarte w wygenerowanym dokumencie elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="cb015-125">Open this form to view the Intrastat transactions that are included in the generated electronic document.</span></span>  
9. <span data-ttu-id="cb015-126">Kliknij opcję Archiwum Intrastat.</span><span class="sxs-lookup"><span data-stu-id="cb015-126">Click Intrastat archive.</span></span>
    * <span data-ttu-id="cb015-127">Ponieważ wykonany format raportowania elektronicznego nie zawiera żadnych ustawień aktualizacji danych aplikacji, szczegóły gotowego raportu Intrastat nie zostały zarchiwizowane.</span><span class="sxs-lookup"><span data-stu-id="cb015-127">Because the executed ER format does not contain any settings for application data update, the details of the completed Intrastat report have not been archived.</span></span>  
10. <span data-ttu-id="cb015-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cb015-128">Close the page.</span></span>
11. <span data-ttu-id="cb015-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cb015-129">Close the page.</span></span>

