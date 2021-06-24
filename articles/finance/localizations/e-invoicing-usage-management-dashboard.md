---
title: Pulpit zarządzania użytkowaniem
description: W tym temacie wyjaśniono, jak korzystać z pulpitu nawigacyjnego Zarządzanie użytkowaniem w celu monitorowania korzystania z usługi fakturowania elektronicznego i zachowania zgodności z przepisami.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130513"
---
# <a name="usage-management-dashboard"></a><span data-ttu-id="c54cd-103">Pulpit zarządzania użytkowaniem</span><span class="sxs-lookup"><span data-stu-id="c54cd-103">Usage management dashboard</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c54cd-104">Pulpit **Zarządzania użytkowaniem** pomaga monitorować wykorzystanie usługi Elektronicznego Fakturowania, a tym samym pomaga organizacji zachować zgodność z przepisami w zakresie miesięcznego wykorzystania.</span><span class="sxs-lookup"><span data-stu-id="c54cd-104">The **Usage management** dashboard helps you monitor usage of the Electronic Invoicing service, and therefore helps your organization remain compliant in terms of its monthly usage.</span></span> <span data-ttu-id="c54cd-105">Zgodność jest określana poprzez obliczenie ilości zgłoszeń i porównanie jej z nabytą ilością zgłoszeń w celu zidentyfikowania wszelkich odchyleń pomiędzy ilością nabytą a wykorzystaną.</span><span class="sxs-lookup"><span data-stu-id="c54cd-105">Compliance is determined by calculating the submission volume and comparing it with the acquired volume of submissions to identify any deviations between the acquired volume and the used volume.</span></span>

<span data-ttu-id="c54cd-106">Pulpit zawiera następujące wskaźniki:</span><span class="sxs-lookup"><span data-stu-id="c54cd-106">The dashboard includes the following indicators:</span></span>

- <span data-ttu-id="c54cd-107">Jeden ze wskaźników kosztów, który można wykorzystać do monitorowania zużycia dla celów zgodności licencyjnej:</span><span class="sxs-lookup"><span data-stu-id="c54cd-107">One cost indicator that you can use to monitor consumption for licensing compliance purposes:</span></span>

    - <span data-ttu-id="c54cd-108">Użycie na miesiąc (eksport)</span><span class="sxs-lookup"><span data-stu-id="c54cd-108">Usage per month (export)</span></span>

- <span data-ttu-id="c54cd-109">Trzy wskaźniki operacyjne, które można wykorzystać do śledzenia korzystania z usługi elektronicznego fakturowania w celach zarządzania:</span><span class="sxs-lookup"><span data-stu-id="c54cd-109">Three operational indicators that you can use to track usage of the Electronic Invoicing service for management purposes:</span></span>

    - <span data-ttu-id="c54cd-110">Użycie według funkcji</span><span class="sxs-lookup"><span data-stu-id="c54cd-110">Usage by feature</span></span>
    - <span data-ttu-id="c54cd-111">Użycie według środowiska</span><span class="sxs-lookup"><span data-stu-id="c54cd-111">Usage by environment</span></span>
    - <span data-ttu-id="c54cd-112">Użycie na miesiąc (import)</span><span class="sxs-lookup"><span data-stu-id="c54cd-112">Usage per month (import)</span></span>

## <a name="measurement-scope"></a><span data-ttu-id="c54cd-113">Zakres pomiaru</span><span class="sxs-lookup"><span data-stu-id="c54cd-113">Measurement scope</span></span>

- <span data-ttu-id="c54cd-114">Jednostka miary:</span><span class="sxs-lookup"><span data-stu-id="c54cd-114">Unit of measure:</span></span> 

    <span data-ttu-id="c54cd-115">Na pulpicie nawigacyjnym **zarządzania używaniem** jest zliczane przesyłanie dokumentów biznesowych i importowanych faktur elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="c54cd-115">The **Usage management** dashboard counts the submission of business documents and imported electronic invoices.</span></span>

- <span data-ttu-id="c54cd-116">Organizacja:</span><span class="sxs-lookup"><span data-stu-id="c54cd-116">Organization:</span></span> 

    <span data-ttu-id="c54cd-117">Zliczanie jest podsumowywane na podstawie identyfikatora dzierżawcy organizacji, niezależnie od liczby instancji Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management, czy też liczby podmiotów prawnych, w których włączona jest usługa elektronicznego fakturowania.</span><span class="sxs-lookup"><span data-stu-id="c54cd-117">Counting is summarized by the tenant ID of your organization, regardless of the number of instances of Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management, or the number of legal entities where the Electronic Invoicing service is enabled.</span></span>


## <a name="indicator-usage-per-month-export"></a><span data-ttu-id="c54cd-118">Wskaźnik: Użycie na miesiąc (eksport)</span><span class="sxs-lookup"><span data-stu-id="c54cd-118">Indicator: Usage per month (export)</span></span>

<span data-ttu-id="c54cd-119">Ten wskaźnik dostarcza szczegółowych informacji na temat faktur elektronicznych wystawionych przez Twoją organizację w określonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c54cd-119">This indicator provides details about the electronic invoices that your organization issues during a defined period.</span></span>

### <a name="scope"></a><span data-ttu-id="c54cd-120">Zakres</span><span class="sxs-lookup"><span data-stu-id="c54cd-120">Scope</span></span>
- <span data-ttu-id="c54cd-121">Liczba dokumentów handlowych, które są przekazywane z Finance i Supply Chain Management do usługi elektronicznego fakturowania, niezależnie od liczby wierszy, które te dokumenty handlowe zawierają.</span><span class="sxs-lookup"><span data-stu-id="c54cd-121">The number of business documents that are submitted from Finance and Supply Chain Management to the Electronic Invoicing service, regardless of number of lines that those business documents contain.</span></span>
- <span data-ttu-id="c54cd-122">Liczba złożonych dokumentów handlowych, które zostały pomyślnie przetworzone przez usługę Elektronicznego Fakturowania.</span><span class="sxs-lookup"><span data-stu-id="c54cd-122">The number of submitted business documents that are successfully processed by the Electronic Invoicing service.</span></span> <span data-ttu-id="c54cd-123">Dokument uznaje się za przetworzony pomyślnie, gdy zakończy się przepływ czynności zdefiniowanych w konfiguracji funkcji.</span><span class="sxs-lookup"><span data-stu-id="c54cd-123">A document is considered successfully processed when the flow of actions that are defined in the feature setup is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="c54cd-124">Gdy faktura elektroniczna jest przesyłana do zewnętrznej usługi sieciowej, liczenie jest niezależne od wyników przetwarzania usługi sieciowej (akceptacja, odrzucenie lub błąd walidacji schematu).</span><span class="sxs-lookup"><span data-stu-id="c54cd-124">When an electronic invoice is submitted to an external web service, counting is independent of the results of web service processing (accepted, rejected, or schema validation error).</span></span> <span data-ttu-id="c54cd-125">Jeśli usługa sieciowa otrzymała i odpowiedziała na żądanie z usługi fakturowania elektronicznego, zgłoszenie jest uważane za prawidłowe zliczenie.</span><span class="sxs-lookup"><span data-stu-id="c54cd-125">If the web service received and responded to the request from the Electronic Invoicing service, the submission is considered a valid counting.</span></span>

- <span data-ttu-id="c54cd-126">**Wyjątek:** Dokumenty biznesowe nie są zliczane, jeśli są ponownie przesyłane z Finance i Supply Chain Management do usługi Fakturowanie Elektroniczne, np. w sytuacji, gdy ponowne przesłanie tego samego dokumentu biznesowego jest wymagane do zmiany statusu faktury elektronicznej.</span><span class="sxs-lookup"><span data-stu-id="c54cd-126">**Exception:** Business documents aren't counted if they are resubmitted from Finance and Supply Chain Management to the Electronic Invoicing service, such as in the scenarios where a resubmission of the same business document is required to change the status of the electronic invoice.</span></span> <span data-ttu-id="c54cd-127">Na przykład, wystawienie brazylijskiej faktury elektronicznej (dokumentu fiskalnego) jest liczone jako ważne, ale wniosek o jej anulowanie nie jest liczony.</span><span class="sxs-lookup"><span data-stu-id="c54cd-127">For example, issuance of a Brazilian electronic invoice (fiscal document) is counted as valid, but the cancellation request for it isn't counted.</span></span>


### <a name="calculation"></a><span data-ttu-id="c54cd-128">Obliczenie</span><span class="sxs-lookup"><span data-stu-id="c54cd-128">Calculation</span></span>

<span data-ttu-id="c54cd-129">Obliczanie salda odbywa się w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c54cd-129">The calculation of the balance is calculated as follows:</span></span>

<span data-ttu-id="c54cd-130">Saldo = Wolne + Zakupione – Używane</span><span class="sxs-lookup"><span data-stu-id="c54cd-130">Balance = Free + Purchased – Used</span></span>

<span data-ttu-id="c54cd-131">Gdzie:</span><span class="sxs-lookup"><span data-stu-id="c54cd-131">Where:</span></span>

- <span data-ttu-id="c54cd-132">Wolne:</span><span class="sxs-lookup"><span data-stu-id="c54cd-132">Free:</span></span>
  
    <span data-ttu-id="c54cd-133">Bezpłatna ilość dokumentów biznesowych, które klient może przesłać w ciągu miesiąca.</span><span class="sxs-lookup"><span data-stu-id="c54cd-133">A free volume of business documents the customer can submit per month.</span></span> <span data-ttu-id="c54cd-134">Zawiera pakiet 100 dokumentów biznesowych, które można przesłać do usługi fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="c54cd-134">It includes a package of 100 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="c54cd-135">Wolny wolumen nie kumuluje się, a pozostałe saldo nie jest przenoszone na następny okres.</span><span class="sxs-lookup"><span data-stu-id="c54cd-135">Free volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="c54cd-136">Zakupione:</span><span class="sxs-lookup"><span data-stu-id="c54cd-136">Purchased:</span></span>
  
    <span data-ttu-id="c54cd-137">Zawiera pakiet 1,000 dokumentów biznesowych, które można przesłać do usługi fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="c54cd-137">A package of 1,000 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="c54cd-138">Ten pakiet musi być nabywany co miesiąc dla organizacji.</span><span class="sxs-lookup"><span data-stu-id="c54cd-138">This package must be acquired for your organization on a monthly basis.</span></span> <span data-ttu-id="c54cd-139">Zakupiony wolumen nie kumuluje się, a pozostałe saldo nie jest przenoszone na następny okres.</span><span class="sxs-lookup"><span data-stu-id="c54cd-139">Purchased volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="c54cd-140">Wykorzystane:</span><span class="sxs-lookup"><span data-stu-id="c54cd-140">Used:</span></span> 

    <span data-ttu-id="c54cd-141">Liczba zgłoszeń dokumentów biznesowych do usługi Elektronicznego Fakturowania według zdefiniowanych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="c54cd-141">The count of business document submissions to the Electronic Invoicing service according to defined criteria.</span></span>
   
> [!IMPORTANT]
> <span data-ttu-id="c54cd-142">Jeśli Twoja firma planuje przekroczyć miesięczny wolumen 100 bezpłatnych zgłoszeń, wykup maksymalną ilość, aby zapewnić zgodność z zasadami licencjonowania usługi fakturowania elektronicznego firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c54cd-142">If your organization plans to exceed the monthly volume of 100 free submissions, purchase the peak volume to ensure that you remain compliant with the Microsoft licensing policy for the Electronic Invoicing service.</span></span>
>
> <span data-ttu-id="c54cd-143">Obecnie zakupiony wolumen musi być wprowadzony ręcznie, zgodnie z datą nabycia, jako wiele pakietów po 1 000 sztuk.</span><span class="sxs-lookup"><span data-stu-id="c54cd-143">Currently, purchased volume must be manually entered, according to the date of acquisition, as multiple packages of 1,000 submissions.</span></span>

## <a name="indicator-usage-by-feature"></a><span data-ttu-id="c54cd-144">Wskaźnik: użycie według funkcji</span><span class="sxs-lookup"><span data-stu-id="c54cd-144">Indicator: Usage by feature</span></span>

<span data-ttu-id="c54cd-145">Wskaźnik pokazuje wykorzystanie funkcji elektronicznego fakturowania do wystawiania faktur elektronicznych w określonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c54cd-145">This indicator shows the usage of electronic invoicing features for issuance of electronic invoices during a defined period.</span></span>

- <span data-ttu-id="c54cd-146">Obliczenie:</span><span class="sxs-lookup"><span data-stu-id="c54cd-146">Calculation:</span></span>
  
    <span data-ttu-id="c54cd-147">Użyte = zliczenie, ile razy każda z funkcji fakturowania elektronicznego została użyta podczas przesyłania dokumentów handlowych do usługi Fakturowanie Elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="c54cd-147">Used = The count of how many times each electronic invoicing feature was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-by-environment"></a><span data-ttu-id="c54cd-148">Wskaźnik: użycie według środowiska</span><span class="sxs-lookup"><span data-stu-id="c54cd-148">Indicator: Usage by environment</span></span>

<span data-ttu-id="c54cd-149">Ten wskaźnik pokazuje wykorzystanie środowiska usług elektronicznego fakturowania w określonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c54cd-149">This indicator shows the usage of electronic invoicing service environments during a defined period.</span></span>

- <span data-ttu-id="c54cd-150">Obliczenie:</span><span class="sxs-lookup"><span data-stu-id="c54cd-150">Calculation:</span></span>
    
    <span data-ttu-id="c54cd-151">Użyte = zliczenie, ile razy każda z funkcji środowiska fakturowania elektronicznego została użyta podczas przesyłania dokumentów handlowych do usługi Fakturowanie Elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="c54cd-151">Used = The count of how many times each electronic invoicing service environment was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-per-month-import"></a><span data-ttu-id="c54cd-152">Wskaźnik: Użycie na miesiąc (import)</span><span class="sxs-lookup"><span data-stu-id="c54cd-152">Indicator: Usage per month (import)</span></span>

<span data-ttu-id="c54cd-153">Wskaźnik pokazuje wielkość importu faktur elektronicznych przez usługę Elektronicznego Fakturowania do Finance i Supply Chain Management w określonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c54cd-153">This indicator shows the volume of importation of electronic invoices by Electronic Invoicing service into Finance and Supply Chain Management during a defined period.</span></span>

- <span data-ttu-id="c54cd-154">Zakres:</span><span class="sxs-lookup"><span data-stu-id="c54cd-154">Scope:</span></span>

    <span data-ttu-id="c54cd-155">Faktury elektroniczne importowane do Finance i Supply Chain Management, niezależnie od liczby wierszy zawartych w tych fakturach elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="c54cd-155">Electronic invoices that are imported into Finance and Supply Chain Management, regardless of the number of lines that those electronic invoices contain.</span></span>

- <span data-ttu-id="c54cd-156">Obliczenie:</span><span class="sxs-lookup"><span data-stu-id="c54cd-156">Calculation:</span></span>

    <span data-ttu-id="c54cd-157">Odebrano = liczba zaimportowanych faktur elektronicznych do Finance i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c54cd-157">Received = The count of imported electronic invoices into Finance and Supply Chain Management.</span></span>

## <a name="functions"></a><span data-ttu-id="c54cd-158">Funkcje</span><span class="sxs-lookup"><span data-stu-id="c54cd-158">Functions</span></span>
### <a name="purchase"></a><span data-ttu-id="c54cd-159">Zakup</span><span class="sxs-lookup"><span data-stu-id="c54cd-159">Purchase</span></span>

<span data-ttu-id="c54cd-160">Na karcie **Użycie na miesiąc (eksport)** wybierz pozycję **Zakup**, aby ręcznie zarejestrować kwotę nabytych zgłoszeń.</span><span class="sxs-lookup"><span data-stu-id="c54cd-160">On the **Usage per month (export)** tab, select **Purchase** to manually register the amount of acquired submissions.</span></span>

<span data-ttu-id="c54cd-161">W tym celu należy wybrać opcję **Nowe** i wprowadzić liczbę **Pakietów** nabytych na ten dzień.</span><span class="sxs-lookup"><span data-stu-id="c54cd-161">For a given date, select **New** and enter the number of **Packages** acquired for on that date.</span></span>

<span data-ttu-id="c54cd-162">**Ilość** jest obliczana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c54cd-162">The **Quantity** is calculated as:</span></span>

<span data-ttu-id="c54cd-163">Ilość = Pakiety \* 1000</span><span class="sxs-lookup"><span data-stu-id="c54cd-163">Quantity = Packages \* 1.000</span></span>

<span data-ttu-id="c54cd-164">Obliczona **ilość** odzwierciedla wartość **Zakupione** ze wskaźnika **Zużycie na miesiąc (eksport)**.</span><span class="sxs-lookup"><span data-stu-id="c54cd-164">The calculated **Quantity** reflects in the **Purchased** from the indicator **Usage per month (export)**.</span></span>

### <a name="update"></a><span data-ttu-id="c54cd-165">Aktualizowanie</span><span class="sxs-lookup"><span data-stu-id="c54cd-165">Update</span></span>

<span data-ttu-id="c54cd-166">W okienku akcji wybierz opcję **Aktualizuj**, aby odświeżyć obliczenia i zaktualizować dane wyświetlane na stronie i na wykresie.</span><span class="sxs-lookup"><span data-stu-id="c54cd-166">On the Action Pane, select **Update** to refresh the calculation and update the data shown on the page and in the chart.</span></span>

### <a name="reset-history-data"></a><span data-ttu-id="c54cd-167">Resetuj dane historii</span><span class="sxs-lookup"><span data-stu-id="c54cd-167">Reset history data</span></span>

<span data-ttu-id="c54cd-168">W okienku akcji wybierz opcję **Resetuj dane historii**, aby odświeżyć bazę danych, z której wskaźniki są obliczane.</span><span class="sxs-lookup"><span data-stu-id="c54cd-168">On the Action Pane, select **Reset history data** to refresh the database from where the indicators are calculated.</span></span>




> [!NOTE]
> <span data-ttu-id="c54cd-169">Na pulpicie nawigacyjnym **zarządzania użyciem** nie są wyświetlane kwoty pieniężne.</span><span class="sxs-lookup"><span data-stu-id="c54cd-169">The **Usage management** dashboard doesn't show monetary amounts.</span></span> <span data-ttu-id="c54cd-170">Zamiast tego jest przedstawiana tylko liczba zliczanych zgłoszeń i zaimportowanych dokumentów.</span><span class="sxs-lookup"><span data-stu-id="c54cd-170">Instead, it shows only the volume of counted submissions and imported documents.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
