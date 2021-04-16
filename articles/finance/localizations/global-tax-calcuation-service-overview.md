---
title: Usługa obliczania podatku (wersja zapoznawcza)
description: W tym temacie wyjaśniono ogólny zakres i funkcje usługi obliczania podatku.
author: wangchen
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818231"
---
# <a name="tax-calculation-service-preview"></a><span data-ttu-id="6e2b5-103">Usługa obliczania podatku (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="6e2b5-103">Tax calculation service (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="6e2b5-104">Usługa obliczania podatku to hyper-skalowalna usługa wielowątkowa, która umożliwia aparatowi Global tax engine automatyzowanie i upraszczanie procesu określania i obliczania podatków.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-104">The tax calculation service is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="6e2b5-105">Aparat podatków jest w pełni konfigurowalny.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="6e2b5-106">Elementy, które można konfigurować, obejmują model danych podlegających opodatkowaniu, kod podatku, macierz możliwości stosowania podatku oraz formułę obliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="6e2b5-107">Aparat podatków działa na podstawowej platformie usług Microsoft Azure i oferuje nowoczesne technologie oraz skalowalność.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="6e2b5-108">Usługa obliczania podatku jest zintegrowana z Dynamics 365 Finance i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-108">The tax calculation service integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="6e2b5-109">Można ją także zintegrować Dynamics 365 Project Operations i Dynamics 365 Commerce z innymi aplikacjami firmy i innych firm.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="6e2b5-110">Usługa obliczania podatku jest opartym na firmie Microsoft aparatem podatków, który oferuje wystawczą skalowalność.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-110">The tax calculation service is a Microsoft-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="6e2b5-111">Możne pomóc wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="6e2b5-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="6e2b5-112">Skonfiguruj usługę obliczania podatku za pomocą usługi konfiguracji przepisów (RCS).</span><span class="sxs-lookup"><span data-stu-id="6e2b5-112">Configure the tax calculation service through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="6e2b5-113">Usługa RCS jest rozszerzoną wersją konstruktora raportowania elektronicznego i jest dostępna jako autonomiczna usługa.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="6e2b5-114">Umożliwia konfigurowanie macierzy podatków w celu automatycznego określania kodów i stawek podatkowych.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="6e2b5-115">Skonfiguruj macierz podatkową, aby automatycznie określić numer rejestracji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="6e2b5-116">Skonfiguruj projektanta obliczeń podatku w celu zdefiniowania formuł i warunków.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="6e2b5-117">Udostępnij rozwiązanie dotyczące określania podatków i obliczania w różnych firmach.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="6e2b5-118">Aby użyć usługi obliczania podatku, zainstaluj dodatek usługi obliczania podatku z swojego projektu w usłudze Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6e2b5-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="6e2b5-119">Następnie należy ukończyć konfigurację w rcs i włączyć usługę obliczania podatku w Finance i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="6e2b5-120">Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z usługą podatkową](https://go.microsoft.com/fwlink/?linkid=2138482).</span><span class="sxs-lookup"><span data-stu-id="6e2b5-120">For more information, see [Get started with tax service](https://go.microsoft.com/fwlink/?linkid=2138482).</span></span>

## <a name="availability"></a><span data-ttu-id="6e2b5-121">Dostępność</span><span class="sxs-lookup"><span data-stu-id="6e2b5-121">Availability</span></span>

<span data-ttu-id="6e2b5-122">Usługa obliczania podatku jest dostępna tylko w środowiskach piaskownicy i dla wybranych klientów za pośrednictwem publicznego programu w wersji Preview.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-122">The tax calculation service is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="6e2b5-123">Ostatecznie stają się one ogólnie dostępne dla wszystkich odbiorców oraz w środowiskach produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="6e2b5-124">W usłudze obliczania podatku będą dostarczane nowe funkcje.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-124">New features will continue to be delivered in the tax calculation service.</span></span> <span data-ttu-id="6e2b5-125">Dlatego należy często sprawdzać najczęściej dostępną dokumentację, aby dowiedzieć się o zakresie i zakresie obsługiwanych funkcji.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-125">Therefore, be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="6e2b5-126">Usługa obliczania podatku jest wdrożona w następujących lokalizacjach geograficznych systemu Azure.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-126">The tax calculation service is deployed in the following Azure geographies.</span></span> <span data-ttu-id="6e2b5-127">Zostanie on również wdrożony w większej liczby geografów systemu Azure w zależności od potrzeb klientów:</span><span class="sxs-lookup"><span data-stu-id="6e2b5-127">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="6e2b5-128">Stany Zjednoczone</span><span class="sxs-lookup"><span data-stu-id="6e2b5-128">United States</span></span>
- <span data-ttu-id="6e2b5-129">Europa</span><span class="sxs-lookup"><span data-stu-id="6e2b5-129">Europe</span></span>
- <span data-ttu-id="6e2b5-130">Francja</span><span class="sxs-lookup"><span data-stu-id="6e2b5-130">France</span></span>
- <span data-ttu-id="6e2b5-131">Wielka Brytania</span><span class="sxs-lookup"><span data-stu-id="6e2b5-131">United Kingdom</span></span>

> [!NOTE]
> <span data-ttu-id="6e2b5-132">Usługa obliczania podatku nie obsługuje lokalnych wdrożeń rozwiązania Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-132">The tax calculation service doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="6e2b5-133">Nie obsługuje także wcześniejszych wersji, takich jak Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-133">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="6e2b5-134">Najważniejsze cechy</span><span class="sxs-lookup"><span data-stu-id="6e2b5-134">Feature highlights</span></span>

- <span data-ttu-id="6e2b5-135">Konfigurowalna macierz podatkowa do automatycznego określania i obliczania podatku</span><span class="sxs-lookup"><span data-stu-id="6e2b5-135">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="6e2b5-136">Obsługa wielu numerów rejestracji VAT</span><span class="sxs-lookup"><span data-stu-id="6e2b5-136">Support for multiple value-added tax (VAT) registration numbers</span></span>
- <span data-ttu-id="6e2b5-137">Obsługa zamówień przeniesienia do określania i obliczania podatku</span><span class="sxs-lookup"><span data-stu-id="6e2b5-137">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="6e2b5-138">Obsługa zamówień przeniesienia w celu określenia wielu numerów rejestracji VAT</span><span class="sxs-lookup"><span data-stu-id="6e2b5-138">Transfer order support for determination of multiple VAT registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="6e2b5-139">Obsługiwane transakcje</span><span class="sxs-lookup"><span data-stu-id="6e2b5-139">Supported transactions</span></span>

<span data-ttu-id="6e2b5-140">Usługa obliczania podatku może być włączona przez firmę i transakcję.</span><span class="sxs-lookup"><span data-stu-id="6e2b5-140">The tax calculation service can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="6e2b5-141">Obsługiwane są następujące transakcje:</span><span class="sxs-lookup"><span data-stu-id="6e2b5-141">The following transactions are supported:</span></span>

- <span data-ttu-id="6e2b5-142">Proces sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6e2b5-142">Sales process</span></span>

    - <span data-ttu-id="6e2b5-143">Oferta sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6e2b5-143">Sales quotation</span></span>
    - <span data-ttu-id="6e2b5-144">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6e2b5-144">Sales order</span></span>
    - <span data-ttu-id="6e2b5-145">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="6e2b5-145">Confirmation</span></span>
    - <span data-ttu-id="6e2b5-146">Lista pobrania</span><span class="sxs-lookup"><span data-stu-id="6e2b5-146">Picking list</span></span>
    - <span data-ttu-id="6e2b5-147">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="6e2b5-147">Packing slip</span></span>
    - <span data-ttu-id="6e2b5-148">Faktura sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6e2b5-148">Sales invoice</span></span>
    - <span data-ttu-id="6e2b5-149">Faktura kredytowa</span><span class="sxs-lookup"><span data-stu-id="6e2b5-149">Credit note</span></span>
    - <span data-ttu-id="6e2b5-150">Zwróć zamówienie</span><span class="sxs-lookup"><span data-stu-id="6e2b5-150">Return order</span></span>
    - <span data-ttu-id="6e2b5-151">Nagłówek Opłaty dodatkowe</span><span class="sxs-lookup"><span data-stu-id="6e2b5-151">Header miscellaneous charge</span></span>
    - <span data-ttu-id="6e2b5-152">Pozostały koszt dotyczący danej pozycji</span><span class="sxs-lookup"><span data-stu-id="6e2b5-152">Line miscellaneous charge</span></span>

- <span data-ttu-id="6e2b5-153">Proces zakupu</span><span class="sxs-lookup"><span data-stu-id="6e2b5-153">Purchase process</span></span>

    - <span data-ttu-id="6e2b5-154">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="6e2b5-154">Purchase order</span></span>
    - <span data-ttu-id="6e2b5-155">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="6e2b5-155">Confirmation</span></span>
    - <span data-ttu-id="6e2b5-156">Lista przychodu</span><span class="sxs-lookup"><span data-stu-id="6e2b5-156">Receipts list</span></span>
    - <span data-ttu-id="6e2b5-157">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="6e2b5-157">Product receipt</span></span>
    - <span data-ttu-id="6e2b5-158">Faktura zakupu</span><span class="sxs-lookup"><span data-stu-id="6e2b5-158">Purchase invoice</span></span>
    - <span data-ttu-id="6e2b5-159">Nagłówek Opłaty dodatkowe</span><span class="sxs-lookup"><span data-stu-id="6e2b5-159">Header miscellaneous charge</span></span>
    - <span data-ttu-id="6e2b5-160">Pozostały koszt dotyczący danej pozycji</span><span class="sxs-lookup"><span data-stu-id="6e2b5-160">Line miscellaneous charge</span></span>
    - <span data-ttu-id="6e2b5-161">Faktura kredytowa</span><span class="sxs-lookup"><span data-stu-id="6e2b5-161">Credit note</span></span>
    - <span data-ttu-id="6e2b5-162">Zwróć zamówienie</span><span class="sxs-lookup"><span data-stu-id="6e2b5-162">Return order</span></span>
    - <span data-ttu-id="6e2b5-163">Zapotrzebowanie na zakup</span><span class="sxs-lookup"><span data-stu-id="6e2b5-163">Purchase requisition</span></span>
    - <span data-ttu-id="6e2b5-164">Różne obciążenia wiersza zapotrzebowania na zakup</span><span class="sxs-lookup"><span data-stu-id="6e2b5-164">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="6e2b5-165">Zapytanie ofertowe</span><span class="sxs-lookup"><span data-stu-id="6e2b5-165">Request for quotation</span></span>
    - <span data-ttu-id="6e2b5-166">Różne opłaty od nagłówka zapytania ofertowego</span><span class="sxs-lookup"><span data-stu-id="6e2b5-166">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="6e2b5-167">Różne opłaty od wiersza zapytania ofertowego</span><span class="sxs-lookup"><span data-stu-id="6e2b5-167">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="6e2b5-168">Proces zapasów</span><span class="sxs-lookup"><span data-stu-id="6e2b5-168">Inventory process</span></span>

    - <span data-ttu-id="6e2b5-169">Przeniesienie zamówienia - wysyłka</span><span class="sxs-lookup"><span data-stu-id="6e2b5-169">Transfer order – ship</span></span>
    - <span data-ttu-id="6e2b5-170">Zamówienie przeniesienia - odbiór</span><span class="sxs-lookup"><span data-stu-id="6e2b5-170">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="6e2b5-171">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="6e2b5-171">Related resources</span></span>

[<span data-ttu-id="6e2b5-172">Rozpocznij pracę z usługą podatkową</span><span class="sxs-lookup"><span data-stu-id="6e2b5-172">Get started with tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138482)

[<span data-ttu-id="6e2b5-173">Wielokrotny numer rejestracji VAT</span><span class="sxs-lookup"><span data-stu-id="6e2b5-173">Multiple VAT registration number</span></span>](https://go.microsoft.com/fwlink/?linkid=2153387)

[<span data-ttu-id="6e2b5-174">Obsługa funkcji podatków dla zamówienia przeniesienia</span><span class="sxs-lookup"><span data-stu-id="6e2b5-174">Tax feature support for transfer order</span></span>](https://go.microsoft.com/fwlink/?linkid=2153388)

[<span data-ttu-id="6e2b5-175">Jak utworzyć rozszerzenie w usłudze podatków</span><span class="sxs-lookup"><span data-stu-id="6e2b5-175">How to build extension in tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138483)
