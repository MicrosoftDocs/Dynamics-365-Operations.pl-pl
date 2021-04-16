---
title: Eksplorator źródeł księgowania
description: Ten artykuł zawiera informacje o Eksplorator źródeł księgowania, którego można używać do szczegółowej analizy informacji źródłowych stojących za wpisami księgowymi w księgi głównej.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: roschlom
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4624a740538493c247b6c3a0f051ed6208c52504
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820938"
---
# <a name="accounting-source-explorer"></a><span data-ttu-id="964a5-103">Eksplorator źródeł księgowania</span><span class="sxs-lookup"><span data-stu-id="964a5-103">Accounting source explorer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="964a5-104">Ten artykuł zawiera informacje o Eksplorator źródeł księgowania, którego można używać do szczegółowej analizy informacji źródłowych stojących za wpisami księgowymi w księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="964a5-104">This article provides information about Accounting source explorer, which you can use for detailed analysis of the source information behind general ledger accounting entries.</span></span>

<span data-ttu-id="964a5-105">Eksplorator źródeł księgowania to nowa strona, która pokazuje informacje o źródle.</span><span class="sxs-lookup"><span data-stu-id="964a5-105">Accounting source explorer is a new page that shows source information.</span></span> <span data-ttu-id="964a5-106">Może służyć albo jako autonomiczne narzędzie, albo do analizy szczegółów zapisów księgowych w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="964a5-106">You can use Accounting source explorer either as a stand-alone tool or to analyze the details behind general ledger accounting entries.</span></span> <span data-ttu-id="964a5-107">Można na przykład uzyskać najbardziej szczegółowe informacje o źródle dla salda bilansu próbnego lub dla transakcji na załączniku.</span><span class="sxs-lookup"><span data-stu-id="964a5-107">For example, you can use Accounting source explorer to get the most detailed source information for a balance in Trail balance or for a voucher transaction.</span></span> <span data-ttu-id="964a5-108">Następnie za pomocą funkcji eksportu do MS Excel można dalej dzielić informacje w programie Microsoft Excel (na przykład w tabeli przestawnej lub raporcie tabeli przestawnej).</span><span class="sxs-lookup"><span data-stu-id="964a5-108">You can then use the Export to MS Excel feature to further slice and dice the information in Microsoft Excel (for example, in a PivotTable or on a PivotTable report).</span></span>

<span data-ttu-id="964a5-109">Eksplorator źródeł księgowania zawsze pokazuje tę samą sumę według konta księgowego co Księga główna (np. w bilansie próbnym).</span><span class="sxs-lookup"><span data-stu-id="964a5-109">Accounting source explorer always shows the same total amount per ledger account as General ledger shows (for example, in Trial balance).</span></span> <span data-ttu-id="964a5-110">W bilansie próbnym można wyświetlić segmenty w osobnych kolumnach.</span><span class="sxs-lookup"><span data-stu-id="964a5-110">As in Trial balance, you can display segments in separate columns.</span></span> <span data-ttu-id="964a5-111">Wystarczy zaznaczyć odpowiedni zestaw wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="964a5-111">Just select the appropriate financial dimension set.</span></span> 

<span data-ttu-id="964a5-112">Za pomocą parametrów można zdefiniować interwał dat dla analizy.</span><span class="sxs-lookup"><span data-stu-id="964a5-112">You can use parameters to define a date interval for the analysis.</span></span> <span data-ttu-id="964a5-113">Ta funkcja przypomina też funkcję bilansu próbnego.</span><span class="sxs-lookup"><span data-stu-id="964a5-113">This functionality also resembles the functionality in Trial balance.</span></span>

<span data-ttu-id="964a5-114">Dla wszystkich dokumentów, które używają struktury dokumentów źródłowych, Eksplorator źródeł księgowania zawiera dodatkowe informacje oparte o zasady podziału księgowań i (jeśli dotyczy) o zasady podziału księgowań dla projektu.</span><span class="sxs-lookup"><span data-stu-id="964a5-114">For all documents that use the source document framework, Accounting source explorer shows additional information, based on accounting distributions and, if applicable, project accounting distributions.</span></span> <span data-ttu-id="964a5-115">Te informacje obejmują typ kwoty pieniężnej, projekt, działanie, kategorię i właściwość wiersza.</span><span class="sxs-lookup"><span data-stu-id="964a5-115">This information includes the monetary amount type, project, activity, category, and line property.</span></span> <span data-ttu-id="964a5-116">Oto kilka przykładów dostępnych analiz:</span><span class="sxs-lookup"><span data-stu-id="964a5-116">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="964a5-117">Odchylenia między zamówieniami zakupu i fakturami od dostawcy, ponieważ każde odchylenie jest reprezentowane przez typ kwoty pieniężnej, np. odchylenie opłaty</span><span class="sxs-lookup"><span data-stu-id="964a5-117">Variances between purchase orders and vendor invoices, because each variance is represented by a monetary amount type, such as charge variance</span></span>
-   <span data-ttu-id="964a5-118">Rozliczane i nierozliczane godziny i wydatki według projektu, jednostki biznesowej i konta głównego</span><span class="sxs-lookup"><span data-stu-id="964a5-118">Billable versus non-billable hours and expenses per project, business unit, and main account</span></span>

<span data-ttu-id="964a5-119">Dla dokumentów źródłowych, które używają koncepcji tożsamości odwołania do dokumentu Eksplorator źródeł księgowań pokazuje jeszcze więcej szczegółów, takich jak odbiorcy, dostawcy, pracownik, produkt, ilość, tekst jednostki i opisy.</span><span class="sxs-lookup"><span data-stu-id="964a5-119">For source documents that use the source document reference identities concept, Accounting source explorer shows even more details, such as the customer, vendor, worker, product, quantity, unit text, and descriptions.</span></span> <span data-ttu-id="964a5-120">Oto kilka przykładów dostępnych analiz:</span><span class="sxs-lookup"><span data-stu-id="964a5-120">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="964a5-121">Wydatki na hotele na jednostkę biznesową i markę hotelu dla okresu obrachunkowego w oparciu o raporty z wydatków</span><span class="sxs-lookup"><span data-stu-id="964a5-121">Hotel expenses per business unit and hotel brand for a fiscal period, based on expense reports</span></span>
-   <span data-ttu-id="964a5-122">Rabaty na dostawcę, produkt, dział</span><span class="sxs-lookup"><span data-stu-id="964a5-122">Discounts per vendor, product, department</span></span>

<span data-ttu-id="964a5-123">W przypadku tych dokumentów Eksplorator źródeł księgowania pozwala też przejść do rzeczywistych dokumentów źródłowych.</span><span class="sxs-lookup"><span data-stu-id="964a5-123">For these documents, you can also navigate to the actual source document from Accounting source explorer.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]