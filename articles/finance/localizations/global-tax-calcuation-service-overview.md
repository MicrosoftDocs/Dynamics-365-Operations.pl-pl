---
title: Obliczanie podatku (wersja zapoznawcza)
description: W tym temacie wyjaśniono ogólny zakres i funkcje obliczania podatku.
author: wangchen
ms.date: 06/03/2021
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
ms.openlocfilehash: 9daa6e001200d03a2639974fb6de618d77ddf09d
ms.sourcegitcommit: cb282e8d2306ab71adf80a84346a6863d2d019e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184108"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="1a82a-103">Obliczanie podatku (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="1a82a-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="1a82a-104">Obliczanie podatku to hyper-skalowalna usługa wielowątkowa, która umożliwia aparatowi Global tax engine automatyzowanie i upraszczanie procesu określania i obliczania podatków.</span><span class="sxs-lookup"><span data-stu-id="1a82a-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="1a82a-105">Aparat podatków jest w pełni konfigurowalny.</span><span class="sxs-lookup"><span data-stu-id="1a82a-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="1a82a-106">Elementy, które można konfigurować, obejmują model danych podlegających opodatkowaniu, kod podatku, macierz możliwości stosowania podatku oraz formułę obliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="1a82a-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="1a82a-107">Aparat podatków działa na podstawowej platformie usług Microsoft Azure i oferuje nowoczesne technologie oraz skalowalność.</span><span class="sxs-lookup"><span data-stu-id="1a82a-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="1a82a-108">Obliczanie podatku jest zintegrowane z Dynamics 365 Finance i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1a82a-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="1a82a-109">Można ją także zintegrować Dynamics 365 Project Operations i Dynamics 365 Commerce z innymi aplikacjami firmy i innych firm.</span><span class="sxs-lookup"><span data-stu-id="1a82a-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a82a-110">Po włączeniu usługi Obliczanie podatku niektóre operacje na powiązanych danych mogą być wykonywane w centrum danych innym niż centrum danych, w którym przechowywane są dane usługi.</span><span class="sxs-lookup"><span data-stu-id="1a82a-110">When you enable the Tax Calculation service, some operations on related data might be performed in a data center other than the data center that maintains your service data.</span></span> <span data-ttu-id="1a82a-111">Zapoznaj się z [Regulaminem korzystania](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) przed włączeniem usługi Obliczanie podatku.</span><span class="sxs-lookup"><span data-stu-id="1a82a-111">Review the [Terms and Conditions](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) before you enable the Tax Calculation service.</span></span> <span data-ttu-id="1a82a-112">Prywatność użytkowników jest dla nas bardzo ważna.</span><span class="sxs-lookup"><span data-stu-id="1a82a-112">Your privacy is important to us.</span></span> <span data-ttu-id="1a82a-113">Więcej informacji na ten temat znajduje się w [Oświadczeniu o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=521839).</span><span class="sxs-lookup"><span data-stu-id="1a82a-113">To learn more, read our [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839).</span></span>

<span data-ttu-id="1a82a-114">Obliczanie podatku jest mikrousługą opartą na firmie Microsoft aparatem podatków, która oferuje wystawczą skalowalność.</span><span class="sxs-lookup"><span data-stu-id="1a82a-114">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="1a82a-115">Możne pomóc wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="1a82a-115">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="1a82a-116">Skonfiguruj usługę Obliczania podatku za pomocą Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="1a82a-116">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="1a82a-117">Usługa RCS jest rozszerzoną wersją konstruktora raportowania elektronicznego i jest dostępna jako autonomiczna usługa.</span><span class="sxs-lookup"><span data-stu-id="1a82a-117">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="1a82a-118">Umożliwia konfigurowanie macierzy podatków w celu automatycznego określania kodów i stawek podatkowych.</span><span class="sxs-lookup"><span data-stu-id="1a82a-118">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="1a82a-119">Skonfiguruj macierz podatkową, aby automatycznie określić numer rejestracji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="1a82a-119">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="1a82a-120">Skonfiguruj projektanta obliczeń podatku w celu zdefiniowania formuł i warunków.</span><span class="sxs-lookup"><span data-stu-id="1a82a-120">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="1a82a-121">Udostępnij rozwiązanie dotyczące określania podatków i obliczania w różnych firmach.</span><span class="sxs-lookup"><span data-stu-id="1a82a-121">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="1a82a-122">Aby użyć usługi obliczania podatku, zainstaluj dodatek usługi obliczania podatku z swojego projektu w usłudze Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="1a82a-122">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="1a82a-123">Następnie należy ukończyć konfigurację w rcs i włączyć usługę obliczania podatku w Finance i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1a82a-123">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="1a82a-124">Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z usługą podatkową](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="1a82a-124">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="1a82a-125">Dostępność</span><span class="sxs-lookup"><span data-stu-id="1a82a-125">Availability</span></span>

<span data-ttu-id="1a82a-126">Obliczanie podatku jest dostępne tylko w środowiskach piaskownicy i dla wybranych klientów za pośrednictwem publicznego programu w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="1a82a-126">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="1a82a-127">Ostatecznie stają się one ogólnie dostępne dla wszystkich odbiorców oraz w środowiskach produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="1a82a-127">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="1a82a-128">Nowe funkcje będą nadal dostarczane, więc pamiętaj, aby często sprawdzać najbardziej aktualną dokumentację, aby dowiedzieć się o zasięgu i zakresie obsługiwanych funkcji.</span><span class="sxs-lookup"><span data-stu-id="1a82a-128">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="1a82a-129">Obliczanie podatku jest wdrożone w następujących lokalizacjach geograficznych systemu Azure.</span><span class="sxs-lookup"><span data-stu-id="1a82a-129">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="1a82a-130">Zostanie on również wdrożony w większej liczby geografów systemu Azure w zależności od potrzeb klientów:</span><span class="sxs-lookup"><span data-stu-id="1a82a-130">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="1a82a-131">Stany Zjednoczone</span><span class="sxs-lookup"><span data-stu-id="1a82a-131">United States</span></span>
- <span data-ttu-id="1a82a-132">Europa</span><span class="sxs-lookup"><span data-stu-id="1a82a-132">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="1a82a-133">Obliczanie podatku nie obsługuje lokalnych wdrożeń rozwiązania Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1a82a-133">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="1a82a-134">Nie obsługuje także wcześniejszych wersji, takich jak Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="1a82a-134">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="1a82a-135">Najważniejsze cechy</span><span class="sxs-lookup"><span data-stu-id="1a82a-135">Feature highlights</span></span>

- <span data-ttu-id="1a82a-136">Konfigurowalna macierz podatkowa do automatycznego określania i obliczania podatku</span><span class="sxs-lookup"><span data-stu-id="1a82a-136">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="1a82a-137">Obsługa wielu numerów rejestracji podatkowej</span><span class="sxs-lookup"><span data-stu-id="1a82a-137">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="1a82a-138">Obsługa zamówień przeniesienia do określania i obliczania podatku</span><span class="sxs-lookup"><span data-stu-id="1a82a-138">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="1a82a-139">Obsługa zamówień przeniesienia w celu określenia wielu numerów rejestracji podatkowej</span><span class="sxs-lookup"><span data-stu-id="1a82a-139">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="1a82a-140">Obsługiwane transakcje</span><span class="sxs-lookup"><span data-stu-id="1a82a-140">Supported transactions</span></span>

<span data-ttu-id="1a82a-141">Obliczanie podatku może być włączone przez firmę i transakcję.</span><span class="sxs-lookup"><span data-stu-id="1a82a-141">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="1a82a-142">Obsługiwane są następujące transakcje:</span><span class="sxs-lookup"><span data-stu-id="1a82a-142">The following transactions are supported:</span></span>

- <span data-ttu-id="1a82a-143">Proces sprzedaży</span><span class="sxs-lookup"><span data-stu-id="1a82a-143">Sales process</span></span>

    - <span data-ttu-id="1a82a-144">Oferta sprzedaży</span><span class="sxs-lookup"><span data-stu-id="1a82a-144">Sales quotation</span></span>
    - <span data-ttu-id="1a82a-145">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="1a82a-145">Sales order</span></span>
    - <span data-ttu-id="1a82a-146">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="1a82a-146">Confirmation</span></span>
    - <span data-ttu-id="1a82a-147">Lista pobrania</span><span class="sxs-lookup"><span data-stu-id="1a82a-147">Picking list</span></span>
    - <span data-ttu-id="1a82a-148">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="1a82a-148">Packing slip</span></span>
    - <span data-ttu-id="1a82a-149">Faktura sprzedaży</span><span class="sxs-lookup"><span data-stu-id="1a82a-149">Sales invoice</span></span>
    - <span data-ttu-id="1a82a-150">Faktura kredytowa</span><span class="sxs-lookup"><span data-stu-id="1a82a-150">Credit note</span></span>
    - <span data-ttu-id="1a82a-151">Zwróć zamówienie</span><span class="sxs-lookup"><span data-stu-id="1a82a-151">Return order</span></span>
    - <span data-ttu-id="1a82a-152">Nagłówek Opłaty dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1a82a-152">Header miscellaneous charge</span></span>
    - <span data-ttu-id="1a82a-153">Pozostały koszt dotyczący danej pozycji</span><span class="sxs-lookup"><span data-stu-id="1a82a-153">Line miscellaneous charge</span></span>

- <span data-ttu-id="1a82a-154">Proces zakupu</span><span class="sxs-lookup"><span data-stu-id="1a82a-154">Purchase process</span></span>

    - <span data-ttu-id="1a82a-155">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="1a82a-155">Purchase order</span></span>
    - <span data-ttu-id="1a82a-156">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="1a82a-156">Confirmation</span></span>
    - <span data-ttu-id="1a82a-157">Lista przychodu</span><span class="sxs-lookup"><span data-stu-id="1a82a-157">Receipts list</span></span>
    - <span data-ttu-id="1a82a-158">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="1a82a-158">Product receipt</span></span>
    - <span data-ttu-id="1a82a-159">Faktura zakupu</span><span class="sxs-lookup"><span data-stu-id="1a82a-159">Purchase invoice</span></span>
    - <span data-ttu-id="1a82a-160">Nagłówek Opłaty dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1a82a-160">Header miscellaneous charge</span></span>
    - <span data-ttu-id="1a82a-161">Pozostały koszt dotyczący danej pozycji</span><span class="sxs-lookup"><span data-stu-id="1a82a-161">Line miscellaneous charge</span></span>
    - <span data-ttu-id="1a82a-162">Faktura kredytowa</span><span class="sxs-lookup"><span data-stu-id="1a82a-162">Credit note</span></span>
    - <span data-ttu-id="1a82a-163">Zwróć zamówienie</span><span class="sxs-lookup"><span data-stu-id="1a82a-163">Return order</span></span>
    - <span data-ttu-id="1a82a-164">Zapotrzebowanie na zakup</span><span class="sxs-lookup"><span data-stu-id="1a82a-164">Purchase requisition</span></span>
    - <span data-ttu-id="1a82a-165">Różne obciążenia wiersza zapotrzebowania na zakup</span><span class="sxs-lookup"><span data-stu-id="1a82a-165">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="1a82a-166">Zapytanie ofertowe</span><span class="sxs-lookup"><span data-stu-id="1a82a-166">Request for quotation</span></span>
    - <span data-ttu-id="1a82a-167">Różne opłaty od nagłówka zapytania ofertowego</span><span class="sxs-lookup"><span data-stu-id="1a82a-167">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="1a82a-168">Różne opłaty od wiersza zapytania ofertowego</span><span class="sxs-lookup"><span data-stu-id="1a82a-168">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="1a82a-169">Proces zapasów</span><span class="sxs-lookup"><span data-stu-id="1a82a-169">Inventory process</span></span>

    - <span data-ttu-id="1a82a-170">Przeniesienie zamówienia - wysyłka</span><span class="sxs-lookup"><span data-stu-id="1a82a-170">Transfer order – ship</span></span>
    - <span data-ttu-id="1a82a-171">Zamówienie przeniesienia - odbiór</span><span class="sxs-lookup"><span data-stu-id="1a82a-171">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="1a82a-172">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="1a82a-172">Related resources</span></span>

[<span data-ttu-id="1a82a-173">Rozpocznij pracę z usługą podatkową</span><span class="sxs-lookup"><span data-stu-id="1a82a-173">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="1a82a-174">Wielokrotny numer rejestracji VAT</span><span class="sxs-lookup"><span data-stu-id="1a82a-174">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="1a82a-175">Obsługa funkcji podatków dla zamówienia przeniesienia</span><span class="sxs-lookup"><span data-stu-id="1a82a-175">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="1a82a-176">Jak utworzyć rozszerzenie w usłudze podatków</span><span class="sxs-lookup"><span data-stu-id="1a82a-176">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)
