---
title: Obliczanie podatku (wersja zapoznawcza)
description: W tym temacie wyjaśniono ogólny zakres i funkcje obliczania podatku.
author: wangchen
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: b26472e195d9bdbba340a118c106de1a4dc79b34
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021939"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="27674-103">Obliczanie podatku (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="27674-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="27674-104">Obliczanie podatku to hyper-skalowalna usługa wielowątkowa, która umożliwia aparatowi Global tax engine automatyzowanie i upraszczanie procesu określania i obliczania podatków.</span><span class="sxs-lookup"><span data-stu-id="27674-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="27674-105">Aparat podatków jest w pełni konfigurowalny.</span><span class="sxs-lookup"><span data-stu-id="27674-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="27674-106">Elementy, które można konfigurować, obejmują model danych podlegających opodatkowaniu, kod podatku, macierz możliwości stosowania podatku oraz formułę obliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="27674-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="27674-107">Aparat podatków działa na podstawowej platformie usług Microsoft Azure i oferuje nowoczesne technologie oraz skalowalność.</span><span class="sxs-lookup"><span data-stu-id="27674-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="27674-108">Obliczanie podatku jest zintegrowane z Dynamics 365 Finance i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="27674-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="27674-109">Można ją także zintegrować Dynamics 365 Project Operations i Dynamics 365 Commerce z innymi aplikacjami firmy i innych firm.</span><span class="sxs-lookup"><span data-stu-id="27674-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="27674-110">Obliczanie podatku jest mikrousługą opartą na firmie Microsoft aparatem podatków, która oferuje wystawczą skalowalność.</span><span class="sxs-lookup"><span data-stu-id="27674-110">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="27674-111">Możne pomóc wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="27674-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="27674-112">Skonfiguruj usługę Obliczania podatku za pomocą Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="27674-112">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="27674-113">Usługa RCS jest rozszerzoną wersją konstruktora raportowania elektronicznego i jest dostępna jako autonomiczna usługa.</span><span class="sxs-lookup"><span data-stu-id="27674-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="27674-114">Umożliwia konfigurowanie macierzy podatków w celu automatycznego określania kodów i stawek podatkowych.</span><span class="sxs-lookup"><span data-stu-id="27674-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="27674-115">Skonfiguruj macierz podatkową, aby automatycznie określić numer rejestracji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="27674-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="27674-116">Skonfiguruj projektanta obliczeń podatku w celu zdefiniowania formuł i warunków.</span><span class="sxs-lookup"><span data-stu-id="27674-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="27674-117">Udostępnij rozwiązanie dotyczące określania podatków i obliczania w różnych firmach.</span><span class="sxs-lookup"><span data-stu-id="27674-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="27674-118">Aby użyć usługi obliczania podatku, zainstaluj dodatek usługi obliczania podatku z swojego projektu w usłudze Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="27674-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="27674-119">Następnie należy ukończyć konfigurację w rcs i włączyć usługę obliczania podatku w Finance i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="27674-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="27674-120">Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z usługą podatkową](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="27674-120">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="27674-121">Dostępność</span><span class="sxs-lookup"><span data-stu-id="27674-121">Availability</span></span>

<span data-ttu-id="27674-122">Obliczanie podatku jest dostępne tylko w środowiskach piaskownicy i dla wybranych klientów za pośrednictwem publicznego programu w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="27674-122">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="27674-123">Ostatecznie stają się one ogólnie dostępne dla wszystkich odbiorców oraz w środowiskach produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="27674-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="27674-124">Nowe funkcje będą nadal dostarczane, więc pamiętaj, aby często sprawdzać najbardziej aktualną dokumentację, aby dowiedzieć się o zasięgu i zakresie obsługiwanych funkcji.</span><span class="sxs-lookup"><span data-stu-id="27674-124">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="27674-125">Obliczanie podatku jest wdrożone w następujących lokalizacjach geograficznych systemu Azure.</span><span class="sxs-lookup"><span data-stu-id="27674-125">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="27674-126">Zostanie on również wdrożony w większej liczby geografów systemu Azure w zależności od potrzeb klientów:</span><span class="sxs-lookup"><span data-stu-id="27674-126">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="27674-127">Stany Zjednoczone</span><span class="sxs-lookup"><span data-stu-id="27674-127">United States</span></span>
- <span data-ttu-id="27674-128">Europa</span><span class="sxs-lookup"><span data-stu-id="27674-128">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="27674-129">Obliczanie podatku nie obsługuje lokalnych wdrożeń rozwiązania Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="27674-129">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="27674-130">Nie obsługuje także wcześniejszych wersji, takich jak Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="27674-130">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="27674-131">Najważniejsze cechy</span><span class="sxs-lookup"><span data-stu-id="27674-131">Feature highlights</span></span>

- <span data-ttu-id="27674-132">Konfigurowalna macierz podatkowa do automatycznego określania i obliczania podatku</span><span class="sxs-lookup"><span data-stu-id="27674-132">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="27674-133">Obsługa wielu numerów rejestracji podatkowej</span><span class="sxs-lookup"><span data-stu-id="27674-133">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="27674-134">Obsługa zamówień przeniesienia do określania i obliczania podatku</span><span class="sxs-lookup"><span data-stu-id="27674-134">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="27674-135">Obsługa zamówień przeniesienia w celu określenia wielu numerów rejestracji podatkowej</span><span class="sxs-lookup"><span data-stu-id="27674-135">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="27674-136">Obsługiwane transakcje</span><span class="sxs-lookup"><span data-stu-id="27674-136">Supported transactions</span></span>

<span data-ttu-id="27674-137">Obliczanie podatku może być włączone przez firmę i transakcję.</span><span class="sxs-lookup"><span data-stu-id="27674-137">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="27674-138">Obsługiwane są następujące transakcje:</span><span class="sxs-lookup"><span data-stu-id="27674-138">The following transactions are supported:</span></span>

- <span data-ttu-id="27674-139">Proces sprzedaży</span><span class="sxs-lookup"><span data-stu-id="27674-139">Sales process</span></span>

    - <span data-ttu-id="27674-140">Oferta sprzedaży</span><span class="sxs-lookup"><span data-stu-id="27674-140">Sales quotation</span></span>
    - <span data-ttu-id="27674-141">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="27674-141">Sales order</span></span>
    - <span data-ttu-id="27674-142">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="27674-142">Confirmation</span></span>
    - <span data-ttu-id="27674-143">Lista pobrania</span><span class="sxs-lookup"><span data-stu-id="27674-143">Picking list</span></span>
    - <span data-ttu-id="27674-144">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="27674-144">Packing slip</span></span>
    - <span data-ttu-id="27674-145">Faktura sprzedaży</span><span class="sxs-lookup"><span data-stu-id="27674-145">Sales invoice</span></span>
    - <span data-ttu-id="27674-146">Faktura kredytowa</span><span class="sxs-lookup"><span data-stu-id="27674-146">Credit note</span></span>
    - <span data-ttu-id="27674-147">Zwróć zamówienie</span><span class="sxs-lookup"><span data-stu-id="27674-147">Return order</span></span>
    - <span data-ttu-id="27674-148">Nagłówek Opłaty dodatkowe</span><span class="sxs-lookup"><span data-stu-id="27674-148">Header miscellaneous charge</span></span>
    - <span data-ttu-id="27674-149">Pozostały koszt dotyczący danej pozycji</span><span class="sxs-lookup"><span data-stu-id="27674-149">Line miscellaneous charge</span></span>

- <span data-ttu-id="27674-150">Proces zakupu</span><span class="sxs-lookup"><span data-stu-id="27674-150">Purchase process</span></span>

    - <span data-ttu-id="27674-151">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="27674-151">Purchase order</span></span>
    - <span data-ttu-id="27674-152">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="27674-152">Confirmation</span></span>
    - <span data-ttu-id="27674-153">Lista przychodu</span><span class="sxs-lookup"><span data-stu-id="27674-153">Receipts list</span></span>
    - <span data-ttu-id="27674-154">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="27674-154">Product receipt</span></span>
    - <span data-ttu-id="27674-155">Faktura zakupu</span><span class="sxs-lookup"><span data-stu-id="27674-155">Purchase invoice</span></span>
    - <span data-ttu-id="27674-156">Nagłówek Opłaty dodatkowe</span><span class="sxs-lookup"><span data-stu-id="27674-156">Header miscellaneous charge</span></span>
    - <span data-ttu-id="27674-157">Pozostały koszt dotyczący danej pozycji</span><span class="sxs-lookup"><span data-stu-id="27674-157">Line miscellaneous charge</span></span>
    - <span data-ttu-id="27674-158">Faktura kredytowa</span><span class="sxs-lookup"><span data-stu-id="27674-158">Credit note</span></span>
    - <span data-ttu-id="27674-159">Zwróć zamówienie</span><span class="sxs-lookup"><span data-stu-id="27674-159">Return order</span></span>
    - <span data-ttu-id="27674-160">Zapotrzebowanie na zakup</span><span class="sxs-lookup"><span data-stu-id="27674-160">Purchase requisition</span></span>
    - <span data-ttu-id="27674-161">Różne obciążenia wiersza zapotrzebowania na zakup</span><span class="sxs-lookup"><span data-stu-id="27674-161">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="27674-162">Zapytanie ofertowe</span><span class="sxs-lookup"><span data-stu-id="27674-162">Request for quotation</span></span>
    - <span data-ttu-id="27674-163">Różne opłaty od nagłówka zapytania ofertowego</span><span class="sxs-lookup"><span data-stu-id="27674-163">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="27674-164">Różne opłaty od wiersza zapytania ofertowego</span><span class="sxs-lookup"><span data-stu-id="27674-164">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="27674-165">Proces zapasów</span><span class="sxs-lookup"><span data-stu-id="27674-165">Inventory process</span></span>

    - <span data-ttu-id="27674-166">Przeniesienie zamówienia - wysyłka</span><span class="sxs-lookup"><span data-stu-id="27674-166">Transfer order – ship</span></span>
    - <span data-ttu-id="27674-167">Zamówienie przeniesienia - odbiór</span><span class="sxs-lookup"><span data-stu-id="27674-167">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="27674-168">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="27674-168">Related resources</span></span>

[<span data-ttu-id="27674-169">Rozpocznij pracę z usługą podatkową</span><span class="sxs-lookup"><span data-stu-id="27674-169">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="27674-170">Wielokrotny numer rejestracji VAT</span><span class="sxs-lookup"><span data-stu-id="27674-170">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="27674-171">Obsługa funkcji podatków dla zamówienia przeniesienia</span><span class="sxs-lookup"><span data-stu-id="27674-171">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="27674-172">Jak utworzyć rozszerzenie w usłudze podatków</span><span class="sxs-lookup"><span data-stu-id="27674-172">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)