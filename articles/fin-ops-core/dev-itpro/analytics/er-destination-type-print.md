---
title: Typ miejsca docelowego drukarka
description: Ten temat wyjaśnia w jaki sposób konfigurować lokalizację docelową drukarka dla poszczególnych składników FOLDER lub FILE formatu sprawozdawczości elektronicznej (ER) skonfigurowanych do generowania dokumentów wychodzących w formacie PDF lub formatach Microsoft Office (Word\Excel).
author: NickSelin
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 148da191ce4ea99c237895c40ec007a1aa0cd537
ms.sourcegitcommit: 0d9ca44b48fb2e33d8160faccc1e6bd932e58934
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150799"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a><span data-ttu-id="ad692-103">Miejsce docelowe drukarka</span><span class="sxs-lookup"><span data-stu-id="ad692-103">Printer destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad692-104">Wygenerowany dokument można wysłać bezpośrednio do drukarki sieciowej w celu bezpośredniego drukowania.</span><span class="sxs-lookup"><span data-stu-id="ad692-104">You can send a generated document directly to a network printer for direct printing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ad692-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ad692-105">Prerequisites</span></span>

<span data-ttu-id="ad692-106">Przed rozpoczęciem należy zainstalować i skonfigurować agenta rozsyłania dokumentów, a następnie zarejestrować drukarki sieciowe.</span><span class="sxs-lookup"><span data-stu-id="ad692-106">Before you begin, you must install and configure the Document Routing Agent, and then register the network printers.</span></span> <span data-ttu-id="ad692-107">W celu zdobycia większezj ilości informacji, zobacz [Instalowanie Agenta rozsyłania dokumentów w celu obsługi druku przez sieć](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span><span class="sxs-lookup"><span data-stu-id="ad692-107">For more information, see [Install the Document Routing Agent to enable network printing](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span></span>

## <a name="make-the-printer-destination-available"></a><span data-ttu-id="ad692-108">Umożliwia udostępnienie drukarki jako miejsca docelowego</span><span class="sxs-lookup"><span data-stu-id="ad692-108">Make the Printer destination available</span></span>

<span data-ttu-id="ad692-109">Aby udostępnić **drukarkę** jako miejsce docelowe w bieżącej instancji rozwiązania Microsoft Dynamics 365 Finance, przejdź do obszaru roboczego **zarządzanie funkcją** i włącz funkcje w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="ad692-109">To make the **Printer** destination available in the current instance of Microsoft Dynamics 365 Finance, go to the **Feature management** workspace, and turn on the following features, in this order:</span></span>

1. <span data-ttu-id="ad692-110">Konwertuj dokumenty wychodzące raportowania elektronicznego z formatów Microsoft Office na PDF</span><span class="sxs-lookup"><span data-stu-id="ad692-110">Convert Electronic Reporting outbound documents from Microsoft Office formats to PDF</span></span>
2. <span data-ttu-id="ad692-111">Agent rozsyłania dokumentów jako cel raportowania elektronicznego dla dokumentów wychodzących</span><span class="sxs-lookup"><span data-stu-id="ad692-111">Document Routing Agent as Electronic Reporting destination for outbound documents</span></span>

<span data-ttu-id="ad692-112">[![Włączanie funkcji lokalizacji docelowej drukarka ER w module Zarządzanie funkcjami](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span><span class="sxs-lookup"><span data-stu-id="ad692-112">[![Turning on the ER printer destination feature in Feature management](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span></span>

### <a name="applicability"></a><span data-ttu-id="ad692-113">Możliwość zastosowania</span><span class="sxs-lookup"><span data-stu-id="ad692-113">Applicability</span></span>

<span data-ttu-id="ad692-114">Lokalizację docelową **Drukarka** można skonfigurować tylko dla składników plików używanych do generowania danych wyjściowych w formacie PDF (format PDF lub w formacie PDF) lub Microsoft Office Excel / formacie Word (plik programu Excel).</span><span class="sxs-lookup"><span data-stu-id="ad692-114">The **Printer** destination can be configured only for file components that are used to generate output in either printable PDF format (PDF Merger or PDF file format elements) or Microsoft Office Excel/Word format (Excel file).</span></span> <span data-ttu-id="ad692-115">Jeśli dane wyjściowe są generowane w formacie PDF, są one wysyłane do drukarki.</span><span class="sxs-lookup"><span data-stu-id="ad692-115">When output is generated in PDF format, it's sent to a printer.</span></span> <span data-ttu-id="ad692-116">Jeśli dane wyjściowe są generowane w formacie Microsoft Office, są automatycznie konwertowane na format PDF, a następnie wysyłane na drukarkę.</span><span class="sxs-lookup"><span data-stu-id="ad692-116">When output is generated in Microsoft Office format, it's automatically converted to PDF format and then sent to a printer.</span></span>

### <a name="limitations"></a><span data-ttu-id="ad692-117">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="ad692-117">Limitations</span></span>

<span data-ttu-id="ad692-118">Ta funkcja jest funkcją podglądu i podlega warunkom użytkowania opisanym w [Temacie uzupełniającym warunki użytkowania w podglądzie Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2105274).</span><span class="sxs-lookup"><span data-stu-id="ad692-118">This feature is a preview feature and is subject to the terms of use that are described in [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://go.microsoft.com/fwlink/?linkid=2105274).</span></span>

<span data-ttu-id="ad692-119">Lokalizacja docelowa **Drukarka** jest zaimplementowana tylko dla wdrożeń w chmurze.</span><span class="sxs-lookup"><span data-stu-id="ad692-119">The **Printer** destination is implemented only for cloud deployments.</span></span>

### <a name="use-the-printer-destination"></a><span data-ttu-id="ad692-120">Użyj miejsca docelowego drukarka</span><span class="sxs-lookup"><span data-stu-id="ad692-120">Use the Printer destination</span></span>

1. <span data-ttu-id="ad692-121">Ustawienie opcji **włączone** na wartość **Tak** powoduje wysłanie wygenerowanego dokumentu do drukarki.</span><span class="sxs-lookup"><span data-stu-id="ad692-121">Set the **Enabled** option to **Yes** to send a generated document to a printer.</span></span>
2. <span data-ttu-id="ad692-122">W polu **Nazwa drukarki** wybierz żądaną drukarkę sieciową.</span><span class="sxs-lookup"><span data-stu-id="ad692-122">In the **Printer name** field, select the required network printer.</span></span>
3. <span data-ttu-id="ad692-123">Ustawienie parametrt **Zapisywanie w archiwum drukowania?** na wartość **Tak** spowoduje przechowywanie wygenerowanych danych wyjściowych w archiwum drukowania, tak aby było dostępne do dalszego drukowania.</span><span class="sxs-lookup"><span data-stu-id="ad692-123">Set the **Save in print archive?** option to **Yes** to store the generated output in the print archive, so that it's available for further printing.</span></span> <span data-ttu-id="ad692-124">Aby później uzyskać dostęp do zarchiwizowanych danych wyjściowych **Zarządzanie organizacją** \> **Raporty i zapytania** \> **Archiwum raportów**.</span><span class="sxs-lookup"><span data-stu-id="ad692-124">To access archived output later, go to **Organization administration** \> **Inquiries and reports** \> **Report archive**.</span></span>

<span data-ttu-id="ad692-125">[![Używanie miejsca docelowego drukarka](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span><span class="sxs-lookup"><span data-stu-id="ad692-125">[![Using the Printer destination](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span></span>

> [!NOTE]
> <span data-ttu-id="ad692-126">Opcja **Konwertuj na plik PDF** nie musi być włączona podczas konfigurowania miejsca docelowego **Drukarka**.</span><span class="sxs-lookup"><span data-stu-id="ad692-126">The **Convert to PDF** option doesn't have to be turned on when you configure the **Printer** destination.</span></span> <span data-ttu-id="ad692-127">Konwersja plików PDF na potrzeby drukowania nastąpi nawet wtedy, gdy opcja jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="ad692-127">The PDF conversion for printing purposes will occur even if the option is turned off.</span></span>

<span data-ttu-id="ad692-128">Aby podczas drukowania dokumentu wychodzącego w formacie programu Excel używana była określona [orientacja strony](electronic-reporting-destinations.md#SelectPdfPageOrientation), należy włączyć opcję **Konwertuj na PDF**.</span><span class="sxs-lookup"><span data-stu-id="ad692-128">To use a specific [page orientation](electronic-reporting-destinations.md#SelectPdfPageOrientation) when you print an outbound document in Excel format, you must turn on the **Convert to PDF** option.</span></span> <span data-ttu-id="ad692-129">Ustawienie opcji **Konwertuj na PDF** na wartość **Tak**powoduje, że staje się dostępne pole **Orientacja strony**.</span><span class="sxs-lookup"><span data-stu-id="ad692-129">When you set the **Convert to PDF** option to **Yes**, the **Page orientation** field becomes available.</span></span> <span data-ttu-id="ad692-130">W polu **Orientacja strony** możesz wybrać orientację strony.</span><span class="sxs-lookup"><span data-stu-id="ad692-130">In the **Page orientation** field, you can select a page orientation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ad692-131">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ad692-131">Additional resources</span></span>

- [<span data-ttu-id="ad692-132">Omówienie raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="ad692-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="ad692-133">Miejsca docelowe raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="ad692-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
