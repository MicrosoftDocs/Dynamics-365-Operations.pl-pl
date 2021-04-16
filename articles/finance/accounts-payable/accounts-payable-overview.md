---
title: Omówienie konfiguracji Zobowiązań
description: Ten artykuł zawiera opis stron, które służą do konfigurowania podstawowych i opcjonalnych funkcji modułu Rozrachunki z dostawcami. Opisano również kroki konfiguracji, które należy wykonać przed rozpoczęciem konfigurowania modułu Rozrachunki z dostawcami.
author: abruer
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable, DeliveryReason, DeliveryTerms, DestinationCode
audience: Application User
ms.reviewer: roschlom
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e334c6351814db191731ce94c4a704863679dd85
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820890"
---
# <a name="configure-accounts-payable-overview"></a><span data-ttu-id="5b5fe-104">Omówienie konfiguracji Zobowiązań</span><span class="sxs-lookup"><span data-stu-id="5b5fe-104">Configure Accounts payable overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b5fe-105">Ten artykuł zawiera opis stron, które służą do konfigurowania podstawowych i opcjonalnych funkcji modułu Rozrachunki z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-105">This article describes the pages that you use to set up basic and optional functionality for Accounts payable.</span></span> <span data-ttu-id="5b5fe-106">Opisano również kroki konfiguracji, które należy wykonać przed rozpoczęciem konfigurowania modułu Rozrachunki z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-106">It also describes setup steps that you must complete before you start to set up Accounts payable.</span></span>

<a name="prerequisites-for-accounts-payable-setup"></a><span data-ttu-id="5b5fe-107">Wymagania wstępne do konfiguracji modułu Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="5b5fe-107">Prerequisites for Accounts payable setup</span></span>
----------------------------------------

<span data-ttu-id="5b5fe-108">Przed skonfigurowaniem modułu Rozrachunki z dostawcami, trzeba wykonać następującą konfigurację:</span><span class="sxs-lookup"><span data-stu-id="5b5fe-108">Before you can set up Accounts payable, you must complete the following setup:</span></span>

-   <span data-ttu-id="5b5fe-109">W księdze głównej:</span><span class="sxs-lookup"><span data-stu-id="5b5fe-109">In General ledger:</span></span>
    -   <span data-ttu-id="5b5fe-110">Jeśli mają być używane arkuszy płatności, skonfiguruj arkusze płatności.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-110">If you plan to use payment journals, set up payment journals.</span></span>
    -   <span data-ttu-id="5b5fe-111">Jeśli mają być uruchamiane korekty kursu wymiany, ustaw kody waluty na stronie Waluty, skonfiguruj typy kursu wymiany na stronie Typy kursu wymiany i skonfiguruj kursy wymiany walut na stronie Kursy wymiany walut.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-111">If you plan to run exchange rate adjustments, set up currency codes on the Currencies page, set up exchange rate types on the Exchange rate types page, and set up currency exchange rates on the Currency exchange rates page.</span></span>
-   <span data-ttu-id="5b5fe-112">W sekcji Zarządzanie gotówką i bankami skonfiguruj konta bankowe używane z metodami płatności.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-112">In Cash and bank management, set up bank accounts to use with methods of payment.</span></span>

## <a name="setup-pages-for-accounts-payable"></a><span data-ttu-id="5b5fe-113">Strony ustawień modułu Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="5b5fe-113">Setup pages for Accounts payable</span></span>

<span data-ttu-id="5b5fe-114">Poniższe strony umożliwiają konfigurowanie podstawowych funkcji rozrachunków z dostawcami dla każdej firmy.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-114">Use the following pages to set up the basic functionality of Accounts payable for each legal entity.</span></span> <span data-ttu-id="5b5fe-115">Strony są wymienione w zalecanej kolejności ustawień.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-115">The pages are listed in the recommended order of setup.</span></span> <span data-ttu-id="5b5fe-116">Aby ułatwić proces ustawień, można tworzyć szablony na podstawie pierwszych utworzonych rekordów.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-116">To make the setup process easier, you can create templates from the first records that you create.</span></span> <span data-ttu-id="5b5fe-117">W szablonie wartości są zwykle wprowadzane w wielu polach, aby odzwierciedlić funkcje, które organizacja chce zaimplementować dla określonego typu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-117">In a template, values are typically entered in many fields to reflect the features that the organization wants to implement for a particular type of vendor.</span></span>
1.  <span data-ttu-id="5b5fe-118">Na stronie Warunki płatności można definiować warunki płatności przypisywane do zamówień sprzedaży, zamówień zakupu, odbiorców i dostawców oraz określających terminy płatności faktur.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-118">On the Terms of payment page, define the terms of payment that you assign to sales orders, purchase orders, customers, and vendors, and that determine invoice due dates.</span></span> <span data-ttu-id="5b5fe-119">Aby uzyskać więcej informacji, zobacz [Definiowanie opłat od płatności dostawcy](tasks/define-vendor-payment-fees.md).</span><span class="sxs-lookup"><span data-stu-id="5b5fe-119">For more information, see [Define vendor payment fees](tasks/define-vendor-payment-fees.md).</span></span>
2.  <span data-ttu-id="5b5fe-120">Na stronie Metody płatności — Dostawcy można tworzyć i obsługiwać informacji o tym, jak organizacja płaci swoim dostawcom.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-120">On the Methods of payment - vendors page, create and maintain information about how the organization pays its vendors.</span></span>
3.  <span data-ttu-id="5b5fe-121">Strona Grupy dostawców umożliwia tworzenie i obsługiwanie grup dostawców, którzy mają wspólne kluczowe parametry dotyczące księgowania, rozliczania i płatności, raportowania oraz prognozowania.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-121">On the Vendor groups page, create and maintain groups of vendors that share important parameters for posting, settlement and payment, reporting, and forecasting.</span></span>
4.  <span data-ttu-id="5b5fe-122">Strona Profile księgowania dostawców pozwala zdefiniować, jak transakcje dostawcy są księgowane w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-122">On the Vendor posting profiles page, define how vendor transactions are posted to the general ledger.</span></span>
5.  <span data-ttu-id="5b5fe-123">Strona Parametry modułu rozrachunków z dostawcami umożliwia konfigurowanie ustawień domyślnych stosowanych w przypadku braku bardziej szczegółowego ustawienia, parametrów różnego rodzaju funkcji oraz różnych sekwencji numerów do rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-123">On the Accounts payable parameters page, set up default settings that are applied if a more specific setting isn't specified, parameters for various kinds of functionality, and the various number sequences for Accounts payable.</span></span>
6.  <span data-ttu-id="5b5fe-124">Strona Ustawienia formularza umożliwia definiowanie formatu różnych dokumentów związanych z dostawcami oraz używanych w firmie do śledzenia przychodów od dostawców i wprowadzania przyczyn przepływu płatności do dostawców.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-124">On the Form setup page, define the format of various documents that are related to vendors, and that the organization uses to keep track of receipts from vendors and enter reasons for the flow of payments to vendors.</span></span>
7.  <span data-ttu-id="5b5fe-125">Strona Dostawcy umożliwia tworzenie i obsługiwanie kont dostawców, w tym urzędów skarbowych, do których organizacja przesyła deklaracje podatkowe.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-125">On the Vendors page, create and maintain vendor accounts, and also the tax authorities that your organization reports sales taxes to.</span></span>

## <a name="optional-setup-pages-for-accounts-payable"></a><span data-ttu-id="5b5fe-126">Opcjonalne strony ustawień rozrachunków z dostawcami</span><span class="sxs-lookup"><span data-stu-id="5b5fe-126">Optional setup pages for Accounts payable</span></span>
<span data-ttu-id="5b5fe-127">Oprócz podstawowych funkcji moduł Rozrachunki z dostawcami ma inne funkcje, które można skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-127">In addition to the basic functionality, Accounts payable has other functionality that you can set up.</span></span>

<span data-ttu-id="5b5fe-128">Dodatkowe strony ustawień są zorganizowane według funkcji.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-128">The additional setup pages are organized by functionality.</span></span>

<span data-ttu-id="5b5fe-129">**Zasady**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-129">**Policies**</span></span>
-   <span data-ttu-id="5b5fe-130">Na stronie Zasady dotyczące faktur od dostawców można ustawić zasady dotyczące faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-130">On the Vendor invoice policy page, set up vendor invoice policies.</span></span>

<span data-ttu-id="5b5fe-131">**Uzgadnianie faktur**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-131">**Invoice matching**</span></span>

-   <span data-ttu-id="5b5fe-132">Strona Dozwolone rozbieżności sum faktury pozwala ustawić tolerancje dla sum faktury.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-132">On the Invoice totals tolerances page, set up tolerances for invoice totals.</span></span>
-   <span data-ttu-id="5b5fe-133">Strona Zasady uzgadniania pozwala ustawić zasady uzgadniania dwuelementowego i trzyelementowego.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-133">On the Matching policy page, set up two-way and three-way matching policies.</span></span>
-   <span data-ttu-id="5b5fe-134">Strona Rozbieżności cenowe pozwala ustawić rozbieżności dla cen jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-134">On the Price tolerances page, set up tolerances for unit prices.</span></span>
-   <span data-ttu-id="5b5fe-135">Strona Grupy rozbieżności cenowych pozycji pozwala ustawić grupy rozbieżności dla cen jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-135">On the Item price tolerance groups page, set up tolerance groups for item prices.</span></span>
-   <span data-ttu-id="5b5fe-136">Strona Grupy rozbieżności cenowych dostawcy pozwala ustawić grupy rozbieżności dla cen dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-136">On the Vendor price tolerance groups page, set up  tolerance groups for vendor prices.</span></span>
-   <span data-ttu-id="5b5fe-137">Strona Dozwolone rozbieżności opłat pozwala ustawić rozbieżności dla opłat.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-137">On the Charges tolerances page, set up tolerances for charges.</span></span>

<span data-ttu-id="5b5fe-138">**Przepływ pracy**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-138">**Workflow**</span></span>

-   <span data-ttu-id="5b5fe-139">Strona Przepływy pracy dla rozrachunków z dostawcami pozwala ustawić konfiguracje przepływu pracy dla zatwierdzeń dziennika i zapotrzebowań na zakup.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-139">On the Accounts payable workflows page, set up workflow configurations for journal approvals and purchase requisitions.</span></span>

<span data-ttu-id="5b5fe-140">**Przyczyny**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-140">**Reasons**</span></span>

-   <span data-ttu-id="5b5fe-141">Strona Przyczyny dotyczące dostawcy pozwala ustawić kody przyczyn.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-141">On the Vendor reasons page, set up reason codes.</span></span>

<span data-ttu-id="5b5fe-142">**Opłaty**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-142">**Charges**</span></span>

-   <span data-ttu-id="5b5fe-143">Strona Kody opłat pozwala ustawić kody dla opłat używane na zamówieniach zakupu.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-143">On the Charges code page, set up codes for the charges that are used in purchase orders.</span></span>
-   <span data-ttu-id="5b5fe-144">Strona Grupa opłat dla dostawcy pozwala utworzyć i obsługiwać grupy opłat dla dostawców.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-144">On the Vendor charges group page, create and maintain charges groups for vendors.</span></span>
-   <span data-ttu-id="5b5fe-145">Strona Grupy opłaty dla towaru pozwala utworzyć i obsługiwać grupy opłat dla towarów.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-145">On the Item charge groups page, create and maintain charges groups for items.</span></span>
-   <span data-ttu-id="5b5fe-146">Strona Opłaty automatyczne pozwala zdefiniować opłaty, które są automatycznie przypisywane do zamówień.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-146">On the Auto charges page, define the charges that are automatically assigned to orders.</span></span>

<span data-ttu-id="5b5fe-147">**Pozycje dodatkowe**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-147">**Supplementary items**</span></span>

-   <span data-ttu-id="5b5fe-148">Strona Grupy towarów dodatkowych - Dostawcy pozwala utworzyć i obsługiwać grupy towarów dodatkowych dla dostawców.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-148">On the Supplementary item groups - Vendor page, create and maintain supplementary item groups for vendors.</span></span>
-   <span data-ttu-id="5b5fe-149">Strona Grupy towarów dodatkowych - zapasy pozwala utworzyć i obsługiwać grupy towarów dodatkowych dla towarów.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-149">On the Supplementary item groups - Inventory page, create and maintain supplementary item groups for items.</span></span>

<span data-ttu-id="5b5fe-150">**Dystrybucja**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-150">**Distribution**</span></span>

-   <span data-ttu-id="5b5fe-151">Strona Warunki dostawy pozwala utworzyć i obsługiwać warunki dotyczące przekazywania towaru kupcowi przez sprzedającego.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-151">On the Terms of delivery page, create and maintain the conditions for an item's transfer from seller to buyer.</span></span>
-   <span data-ttu-id="5b5fe-152">Strona Metody dostawy pozwala umożliwia tworzenie i obsługiwanie metod transportu używanych przy dostawie zamówienia kupcowi przez sprzedającego.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-152">On the Modes of delivery page, create and maintain the methods of transport that are used when an order is delivered from the seller to the buyer.</span></span>
-   <span data-ttu-id="5b5fe-153">Strona Kody przeznaczenia  umożliwia tworzenie i obsługiwanie identyfikatorów i opisów dotyczących miejsc przeznaczenia dostaw.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-153">On the Destination codes page, create and maintain identifiers and descriptions for delivery destinations.</span></span>

<span data-ttu-id="5b5fe-154">**Formularze**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-154">**Forms**</span></span>

-   <span data-ttu-id="5b5fe-155">Strona Notatki umożliwia tworzenie standardowego tekstu wyświetlanego na różnych stronach.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-155">On the Form notes page, create the standard text that appears on various pages.</span></span>
-   <span data-ttu-id="5b5fe-156">Strona Sortowanie formularza umożliwia konfigurowanie kolejności sortowania zapotrzebowań, list przychodów, dokumentów dostawy i faktur.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-156">On the Form sorting parameters page, set up the sorting order for requisitions, receipt lists, packing slips, and invoices.</span></span>
-   <span data-ttu-id="5b5fe-157">Strona Konfiguracja zarządzania drukowaniem  umożliwia drukowanie informacji o zarządzaniu dla oryginałów i kopii stron.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-157">On the Print management setup page, set up print management information for originals and copies of pages.</span></span>

<span data-ttu-id="5b5fe-158">**Płatności**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-158">**Payments**</span></span>

-   <span data-ttu-id="5b5fe-159">Strona Rabaty gotówkowe umożliwia konfigurowanie warunków uzyskiwania rabatów gotówkowych i zarządzanie nimi.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-159">On the Cash discounts page, set up and manage the terms for obtaining cash discounts.</span></span> <span data-ttu-id="5b5fe-160">Kody rabatów gotówkowych są połączone z dostawcami i stosowane do zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-160">The cash discount codes are linked to vendors and are applied to purchase orders.</span></span>
-   <span data-ttu-id="5b5fe-161">Strona Harmonogramy płatności umożliwia ustawienie harmonogramów płatności, które są używane do zarządzania płatnościami rat dla dostawców.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-161">On the Payment schedules page, set up the payment schedules that are used to manage installment payments to vendors.</span></span>
-   <span data-ttu-id="5b5fe-162">Strona Dni płatności umożliwia definiowanie dni płatności, które są używane w obliczeniach terminów płatności, oraz określanie dni płatności dla określonego dnia tygodnia lub miesiąca.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-162">On the Payment days page, define the payment days that are used to calculate due dates, and specify payment days for a specific day of the week or month.</span></span>
-   <span data-ttu-id="5b5fe-163">Strona Opłata umożliwia tworzenie i obsługiwanie opłat skojarzonych z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-163">On the Payment fee page, create and maintain the payment fees that are associated with vendors.</span></span>
-   <span data-ttu-id="5b5fe-164">Strona Instrukcja płatności umożliwia tworzenie i obsługiwanie instrukcji płatności.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-164">On the Payment instruction page, create and maintain payment instructions.</span></span>

<span data-ttu-id="5b5fe-165">**Statystyki**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-165">**Statistics**</span></span>

-   <span data-ttu-id="5b5fe-166">Strona Definicje okresów wiekowania umożliwia konfigurowanie zdefiniowanych przez użytkownika interwałów służących do analizy rozkładu terminów płatności dla kont dostawców.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-166">On the Aging period definitions page, set up user-defined intervals that are used to analyze the maturity distribution of vendor accounts.</span></span>
-   <span data-ttu-id="5b5fe-167">Strona Branża umożliwia tworzenie kodów branż (LOB) przypisanych do dostawców.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-167">On the Line of business page, create the line of business (LOB) codes that are assigned to vendors.</span></span>

<span data-ttu-id="5b5fe-168">**Podatek 1099**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-168">**Tax 1099**</span></span>

-   <span data-ttu-id="5b5fe-169">Strona **Pola 1099** umożliwia sprawdzenie i aktualizację minimalnych kwot, które należy podać do urzędu skarbowego zgodnie z najnowszymi wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-169">On the **1099 fields** page, verify and update the minimum amounts that must be reported to the Internal Revenue Service (IRS), based on the latest IRS requirements.</span></span>

## <a name="optional-setup-for-other-modules"></a><span data-ttu-id="5b5fe-170">**Ustawienia opcjonalne dla innych modułów**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-170">**Optional setup for other modules**</span></span>
<span data-ttu-id="5b5fe-171">**Administrowanie organizacją**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-171">**Organization administration**</span></span>

-   <span data-ttu-id="5b5fe-172">Strona Sekwencja identyfikatorów umożliwia konfigurowanie grup sekwencji identyfikatorów dla numerów faktur.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-172">On the Number sequences page, set up number sequence groups for invoice numbers.</span></span>
-   <span data-ttu-id="5b5fe-173">Na poniższych stronach ustaw informacje dotyczące adresu:</span><span class="sxs-lookup"><span data-stu-id="5b5fe-173">On the following pages, set up address information:</span></span>
    -   <span data-ttu-id="5b5fe-174">Ustawienia adresu</span><span class="sxs-lookup"><span data-stu-id="5b5fe-174">Address setup</span></span>
    -   <span data-ttu-id="5b5fe-175">Kody NAF</span><span class="sxs-lookup"><span data-stu-id="5b5fe-175">NAF codes</span></span>
    -   <span data-ttu-id="5b5fe-176">Import kodów pocztowych</span><span class="sxs-lookup"><span data-stu-id="5b5fe-176">Import ZIP/postal codes</span></span>

<span data-ttu-id="5b5fe-177">**Księga główna**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-177">**General ledger**</span></span>

-   <span data-ttu-id="5b5fe-178">Strona Wymiary finansowe umożliwia konfigurowanie wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-178">On the Financial dimensions page, set up financial dimensions.</span></span>
-   <span data-ttu-id="5b5fe-179">Na poniższych stronach ustaw informacje dotyczące podatku:</span><span class="sxs-lookup"><span data-stu-id="5b5fe-179">On the following pages, set up tax information:</span></span>
    -   <span data-ttu-id="5b5fe-180">Kody podatków</span><span class="sxs-lookup"><span data-stu-id="5b5fe-180">Sales tax codes</span></span>
    -   <span data-ttu-id="5b5fe-181">Grupy podatków</span><span class="sxs-lookup"><span data-stu-id="5b5fe-181">Sales tax groups</span></span>
    -   <span data-ttu-id="5b5fe-182">Grupy podatków dla pozycji</span><span class="sxs-lookup"><span data-stu-id="5b5fe-182">Item sales tax groups</span></span>
    -   <span data-ttu-id="5b5fe-183">Grupa kont</span><span class="sxs-lookup"><span data-stu-id="5b5fe-183">Account group</span></span>
    -   <span data-ttu-id="5b5fe-184">Kody zwolnienia z podatku</span><span class="sxs-lookup"><span data-stu-id="5b5fe-184">Sales tax exempt codes</span></span>
    -   <span data-ttu-id="5b5fe-185">Właściwe miejscowo urzędy skarbowe</span><span class="sxs-lookup"><span data-stu-id="5b5fe-185">Sales tax jurisdictions</span></span>
    -   <span data-ttu-id="5b5fe-186">Urzędy skarbowe</span><span class="sxs-lookup"><span data-stu-id="5b5fe-186">Sales tax authorities</span></span>
    -   <span data-ttu-id="5b5fe-187">Okresy rozliczania podatku</span><span class="sxs-lookup"><span data-stu-id="5b5fe-187">Sales tax settlement periods</span></span>

<span data-ttu-id="5b5fe-188">**Zarządzanie gotówką i bankami**</span><span class="sxs-lookup"><span data-stu-id="5b5fe-188">**Cash and bank management**</span></span>

-   <span data-ttu-id="5b5fe-189">Strona Kody celów płatności umożliwia ustawieni kodu celu banku centralnego.</span><span class="sxs-lookup"><span data-stu-id="5b5fe-189">On the Payment purpose codes page, set up the Central Bank purpose code.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]