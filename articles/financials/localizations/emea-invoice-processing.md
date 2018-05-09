---
title: Przetwarzanie faktur
description: "Ten temat zawiera informacje dotyczące przetwarzania faktur dla Europy Wschodniej."
author: v-kikozl
manager: AnnBe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters, VendParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-kikozl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7486282d4fad1f9557d19f33b067242debc264f2
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="invoice-processing"></a><span data-ttu-id="39dfb-103">Przetwarzanie faktur</span><span class="sxs-lookup"><span data-stu-id="39dfb-103">Invoice processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39dfb-104">Ten temat zawiera krótki opis scenariuszy dla określonych krajów, takich jak wewnątrzwspólnotowy podatek VAT i podatek odroczony.</span><span class="sxs-lookup"><span data-stu-id="39dfb-104">This topic briefly describes some country-specific scenarios, such as intra-community value-added tax (VAT) and deferred tax.</span></span> <span data-ttu-id="39dfb-105">Wymagania prawne dla niektórych krajów europejskich wpływają na proces fakturowania.</span><span class="sxs-lookup"><span data-stu-id="39dfb-105">Legal requirements for some European countries affect the invoicing process.</span></span> <span data-ttu-id="39dfb-106">Ten temat zawiera także informacje o sposobie przetwarzania faktur odbiorców i dostawców dla tych krajów.</span><span class="sxs-lookup"><span data-stu-id="39dfb-106">This topic provides also an information about how customer and vendor invoices are processed for these countries.</span></span> 
<table>
<thead>
<tr>
<th><span data-ttu-id="39dfb-107">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="39dfb-107">Scenario</span></span></th>
<th><span data-ttu-id="39dfb-108">Kraje</span><span class="sxs-lookup"><span data-stu-id="39dfb-108">Countries</span></span></th>
<th><span data-ttu-id="39dfb-109">Opis zmian funkcji</span><span class="sxs-lookup"><span data-stu-id="39dfb-109">Description of the functionality changes</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="39dfb-110">Daty Rozrachunków z odbiorcami i Rozrachunków z dostawcami na potrzeby podatku VAT</span><span class="sxs-lookup"><span data-stu-id="39dfb-110">Accounts receivable and Accounts payable dates for VAT</span></span></td>
<td><span data-ttu-id="39dfb-111">Republika Czeska, Polska</span><span class="sxs-lookup"><span data-stu-id="39dfb-111">Czech Republic, Poland</span></span></td>
<td>
<p><span data-ttu-id="39dfb-112">Przy zakupie towarów z krajów Unii Europejskiej (UE) obowiązkowe jest samodzielne obliczenie podatku VAT:</span><span class="sxs-lookup"><span data-stu-id="39dfb-112">When goods are purchased from European Union (EU) countries, there is an obligation of self-assessment of VAT:</span></span></p>
<ul>
<li><span data-ttu-id="39dfb-113">Należny podatek VAT musi zostać zapłacony w okresie płatności podatku VAT, w którym wystawiono fakturę (data dokumentu).</span><span class="sxs-lookup"><span data-stu-id="39dfb-113">The output VAT must be paid in a VAT period where the invoice was issued (document date).</span></span></li>
<li><span data-ttu-id="39dfb-114">Naliczonego podatku VAT nie można odliczyć przed odebraniem dokumentu (data rejestracji VAT).</span><span class="sxs-lookup"><span data-stu-id="39dfb-114">The input VAT can’t be deducted before the document receipt (VAT register date).</span></span></li>
</ul>
<p><span data-ttu-id="39dfb-115">Aby użyć tego scenariusza, należy skonfigurować następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="39dfb-115">The following settings should be configured to support this scenario:</span></span></p>
<ul>
<li><span data-ttu-id="39dfb-116">Na stronie <strong>Parametry modułu rozrachunków z dostawcami</strong> włącz parametry <strong>Wewnątrzwspólnotowy podatek VAT</strong> i <strong>Data dokumentu na potrzeby wewnątrzwspólnotowego podatku VAT</strong>.</span><span class="sxs-lookup"><span data-stu-id="39dfb-116">On the <strong>Accounts payable parameters</strong> page, enable the <strong>Intra-community VAT</strong> and <strong>Document date for intra-community VAT</strong> parameters.</span></span></li>
<li><span data-ttu-id="39dfb-117">Skonfiguruj dwa kody podatków, jeden z dodatnią, a drugi z ujemną wartością procentową.</span><span class="sxs-lookup"><span data-stu-id="39dfb-117">Set up two sales tax codes, one that has a positive sales tax percentage and one that has a negative sales tax percentage.</span></span></li>
<li><span data-ttu-id="39dfb-118">Skonfiguruj grupę podatku zawierającą kody podatku dodatniego i ujemnego.</span><span class="sxs-lookup"><span data-stu-id="39dfb-118">Set up a sales tax group that includes both the positive and negative sales tax codes.</span></span> <span data-ttu-id="39dfb-119">W przypadku kodu podatku dodatniego ustaw parametr <strong>Wewnątrzwspólnotowy podatek VAT</strong> na <strong>Tak</strong>.</span><span class="sxs-lookup"><span data-stu-id="39dfb-119">For the negative sales tax code, set the <strong>Intracommunity VAT</strong> parameter to <strong>Yes</strong>.</span></span></li>
</ul>
<p><span data-ttu-id="39dfb-120">Po pomyślnej konfiguracji zakupy będą miały dwie zaksięgowane transakcje podatku:</span><span class="sxs-lookup"><span data-stu-id="39dfb-120">After successful setup, purchases will have two posted sales tax transactions:</span></span></p>
<ul>
<li><span data-ttu-id="39dfb-121">Transakcja dodatnia ma kierunek <strong>podatku naliczonego</strong> i datę rejestracji VAT równą dacie ze strony księgowania faktury.</span><span class="sxs-lookup"><span data-stu-id="39dfb-121">A positive transaction that has a direction of <strong>sales tax receivable</strong> and a VAT register date that equals the date from the invoice posting page.</span></span></li>
<li><span data-ttu-id="39dfb-122">Transakcja ujemna ma kierunek <strong>podatku należnego</strong> i datę rejestracji VAT równą dacie dokumentu.</span><span class="sxs-lookup"><span data-stu-id="39dfb-122">A negative transaction that has a direction of <strong>sales tax payable</strong> and a VAT register date that equals the document date.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="39dfb-123">Zmodyfikuj datę dokumentu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="39dfb-123">Modify a sales document date.</span></span></td>
<td><span data-ttu-id="39dfb-124">Wszystkie kraje Europy Wschodniej</span><span class="sxs-lookup"><span data-stu-id="39dfb-124">All Eastern European countries</span></span></td>
<td><p><span data-ttu-id="39dfb-125">Pole <strong>Data dokumentu</strong> na fakturze projektu można zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="39dfb-125">You can modify the <strong>Document date</strong> field on a project invoice.</span></span> <span data-ttu-id="39dfb-126">Ta data jest widoczna na wydrukowanej fakturze.</span><span class="sxs-lookup"><span data-stu-id="39dfb-126">This date appears on the printed invoice.</span></span></p>
<p><span data-ttu-id="39dfb-127">Dostępne jest także pole <strong>Data dokumentu</strong> na stronie <strong>Księgowanie faktury</strong> i <strong>Faktura niezależna</strong>.</span><span class="sxs-lookup"><span data-stu-id="39dfb-127">There is also a <strong>Document date</strong> field on the <strong>Posting invoice</strong> and <strong>Free text invoice</strong> pages.</span></span> <span data-ttu-id="39dfb-128">Po zaksięgowaniu faktury data dokumentu jest widoczna w nagłówku faktury.</span><span class="sxs-lookup"><span data-stu-id="39dfb-128">After you post an invoice, the document date appears on the invoice header.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="39dfb-129">Data dokumentu dla kursu wymiany</span><span class="sxs-lookup"><span data-stu-id="39dfb-129">Document date for exchange rates</span></span></td>
<td><span data-ttu-id="39dfb-130">Polska, Węgry, Republika Czeska</span><span class="sxs-lookup"><span data-stu-id="39dfb-130">Poland, Hungary, Czech Republic</span></span></td>
<td>
<p><span data-ttu-id="39dfb-131">Przepisy określają różne zasady wybierania prawidłowych kursów wymiany dla kursów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="39dfb-131">Legislation provides different rules for selecting valid exchange rates for business transactions.</span></span> <span data-ttu-id="39dfb-132">W polu <strong>Data kursu wymiany</strong> na stronach <strong>Parametry modułu rozrachunków z odbiorcami</strong> i <strong>Parametry modułu rozrachunków z dostawcami</strong> można wybrać datę, która ma być używana dla kwot w obliczeniu waluty rozliczeniowej w dokumentach zakupu i sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="39dfb-132">In the <strong>Exchange rate date</strong> field on the <strong>Accounts receivable parameters</strong> and <strong>Accounts payable parameters</strong> pages, you can select the date that should be used for amounts in the accounting currency calculation on purchase and sales documents.</span></span> <span data-ttu-id="39dfb-133">Podczas wprowadzania danych system pobiera kurs wymiany dla transakcji na podstawie tego parametru.</span><span class="sxs-lookup"><span data-stu-id="39dfb-133">During data entry, the system retrieves the exchange rate for the transaction, based on this parameter.</span></span></p>
<blockquote>[!NOTE]<br><span data-ttu-id="39dfb-134">Po ustawieniu pola <strong>Data kursu wymiany</strong> na <strong>Data dokumentu (tylko dla handlu z krajami UE)</strong> system używa grupy podatku.</span><span class="sxs-lookup"><span data-stu-id="39dfb-134">When you set the <strong>Exchange rate date</strong> field to <strong>Document date (for EU trade only)</strong>, the system uses the sales tax group.</span></span> <span data-ttu-id="39dfb-135">Dla grupy podatku dostępny jest parametr <strong>Handel Unijny</strong> na karcie <strong>Ogólne</strong>. Jeżeli opcja <strong>Handel Unijny</strong> jest ustawiona na <strong>Tak</strong> dla grupy podatku i jeżeli ta grupa podatku istnieje w nagłówku dokumentu, system pobiera kurs wymiany na podstawie daty dokumentu.</span><span class="sxs-lookup"><span data-stu-id="39dfb-135">For the sales tax group, there is a <strong>EU trade</strong> parameter on the <strong>General</strong> tab. If the <strong>EU trade</strong> option is set to <strong>Yes</strong> for the sales tax group, and if this sales tax group exists on the header of the document, the system retrieves the exchange rate based on the document date.</span></span> <span data-ttu-id="39dfb-136">Jeżeli opcja <strong>Handel Unijny</strong> jest ustawiona na <strong>Nie</strong> dla tej grupy podatku sprzedaży, system pobiera kurs wymiany na podstawie daty księgowania dokumentu.</span><span class="sxs-lookup"><span data-stu-id="39dfb-136">If the <strong>EU trade</strong> option is set to <strong>No</strong> for this sales tax group, the system retrieves the exchange rate based on the posting date of the document.</span></span></blockquote>
</td>
</tr>
<tr>
<td><span data-ttu-id="39dfb-137">Daty transakcji handlowych, daty rejestracji VAT oraz kontrola daty dokumentu i VAT</span><span class="sxs-lookup"><span data-stu-id="39dfb-137">Trade dates, VAT register dates, and document and VAT date control</span></span></td>
<td><span data-ttu-id="39dfb-138">Polska, Węgry, Republika Czeska</span><span class="sxs-lookup"><span data-stu-id="39dfb-138">Poland, Hungary, Czech Republic</span></span></td>
<td>
<p><span data-ttu-id="39dfb-139">Daty sprzedaży i przyjęcia dokumentu są wymagane do raportowania podatku VAT:</span><span class="sxs-lookup"><span data-stu-id="39dfb-139">The sales date and the document receipt date are required for VAT reporting:</span></span></p>
<ul>
<li><span data-ttu-id="39dfb-140">Data sprzedaży jest datą realizacji umowy dla transakcji w rozrachunkach z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="39dfb-140">The sales date is the fulfilment date of the transaction in Accounts receivable.</span></span></li>
<li><span data-ttu-id="39dfb-141">Data otrzymania dokumentu jest datą upoważnienia do odliczenia podatku VAT w rozrachunkach z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="39dfb-141">The document receipt date is a date that demonstrates the rights to claim a VAT deduction in Accounts payable.</span></span> <span data-ttu-id="39dfb-142">Każdy odebrany dokument ma datę dla celów inspekcji.</span><span class="sxs-lookup"><span data-stu-id="39dfb-142">Each document that is received has a date for audit purposes.</span></span></li>
</ul>
<p><span data-ttu-id="39dfb-143">Węgierską funkcją dla daty terminów, czeską dla dat realizacji oraz polską dla daty rejestru VAT obejmują wymóg raportowania informacji podatkowych oparte na dacie różniącej się od daty księgowania.</span><span class="sxs-lookup"><span data-stu-id="39dfb-143">The Hungarian functionality for date deadlines, the Czech Republic functionality for fulfill dates, and the Polish functionality for the VAT register date include the requirement for tax information reporting that is based on a date that differs from the posting date.</span></span></p>
<p><span data-ttu-id="39dfb-144">Pole <strong>Data rejestru VAT</strong> obsługuje ten wymóg i jest dostępne na ponad 20 stronach.</span><span class="sxs-lookup"><span data-stu-id="39dfb-144">The <strong>Date of VAT register</strong> field supports this requirement and appears on more than 20 pages.</span></span> <span data-ttu-id="39dfb-145">Te strony zawierają arkusze, zamówienia sprzedaży, zamówienia zakupu, faktury niezależne, arkusze faktur od dostawców i faktury projektu.</span><span class="sxs-lookup"><span data-stu-id="39dfb-145">These pages include journals, sales orders, purchase orders, free-text invoices, vendor invoice journals, and project invoices.</span></span> <span data-ttu-id="39dfb-146">Podczas aktualizacji lub księgowania dokumentów wszystkie podatki są księgowane przy użyciu odpowiedniej daty rejestru VAT i data ta jest uwzględniona na stronach, takich jak arkusze faktur dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="39dfb-146">When you update or post the documents, all taxes are posted by using the corresponding date of the VAT register, and the date is included on pages such as the customer and vendor invoice journals pages.</span></span></p>
<p><span data-ttu-id="39dfb-147">W przypadku Republiki Czeskiej pole <strong>Data rejestru VAT</strong> może być puste podczas księgowania w przypadku odroczonego księgowania VAT.</span><span class="sxs-lookup"><span data-stu-id="39dfb-147">Specifically, for the Czech Republic, the <strong>VAT register date</strong> field can be blank during posting, in the event of postponed VAT posting.</span></span> <span data-ttu-id="39dfb-148">W przeciwnym wypadku pole jest obowiązkowe i musi zostać wypełnione.</span><span class="sxs-lookup"><span data-stu-id="39dfb-148">Otherwise, the field is mandatory and must be filled in.</span></span></p>
<p><span data-ttu-id="39dfb-149">Parametry weryfikacji dat można ustawić na stronie <strong>Grupy podatków</strong>:</span><span class="sxs-lookup"><span data-stu-id="39dfb-149">Date validation parameters can be set on the <strong>Sales tax groups</strong> page:</span></span></p>
<ul>
<li><span data-ttu-id="39dfb-150">Parametry <strong>Wypełnianie daty rejestru VAT</strong> i <strong>Wypełnianie daty sprzedaży</strong> są używane jako domyślna metoda wypełniania dla odpowiednich dat.</span><span class="sxs-lookup"><span data-stu-id="39dfb-150">The <strong>Date of VAT register filling</strong> and <strong>Sales date filling</strong> parameters are used as a default filling method for appropriate dates.</span></span> <span data-ttu-id="39dfb-151">Dostępne jest także wprowadzanie ręczne i kilka metod zautomatyzowanego wprowadzania.</span><span class="sxs-lookup"><span data-stu-id="39dfb-151">Manual input and several automated input methods are also available.</span></span></li>
<li><span data-ttu-id="39dfb-152">Pole <strong>Wymagana data sprzedaży</strong> określa, czy data sprzedaży musi zostać wprowadzona przed zaksięgowaniem faktury sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="39dfb-152">The <strong>Mandatory sales date</strong> field indicates whether the sales date must be entered before a sales invoice is posted.</span></span></li>
</ul>
<p><span data-ttu-id="39dfb-153">Na stronie <strong>Transakcje rejestru VAT</strong> można uzupełnić puste daty rejestru VAT dla zaksięgowanych transakcji podatkowych.</span><span class="sxs-lookup"><span data-stu-id="39dfb-153">On the <strong>VAT Register transactions</strong> page, you can fill in blank dates for the VAT register for posted tax transactions.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="39dfb-154">Daty rejestru VAT które obejmują podatek odroczony</span><span class="sxs-lookup"><span data-stu-id="39dfb-154">VAT register dates that include deferred tax</span></span></td>
<td><span data-ttu-id="39dfb-155">Węgry</span><span class="sxs-lookup"><span data-stu-id="39dfb-155">Hungary</span></span></td>
<td>
<p><span data-ttu-id="39dfb-156">Węgierskie przepisy podatkowe wymagają utworzenia faktury w momencie realizacji umowy lub nie później niż 15 po realizacji umowy.</span><span class="sxs-lookup"><span data-stu-id="39dfb-156">Hungary tax regulations require that invoices be created at either the time of fulfilment or no later than 15 days after fulfilment.</span></span></p>
<p><span data-ttu-id="39dfb-157">Data realizacji umowy to dzień świadczenia zamówionych usług lub dostarczenia zamówionych towarów.</span><span class="sxs-lookup"><span data-stu-id="39dfb-157">The fulfilment date is either the date when the ordered services were provided or the date when ordered items were delivered.</span></span> <span data-ttu-id="39dfb-158">Po aktualizacji lub zaksięgowaniu dokumentów wszystkie podatki są księgowane przy użyciu odpowiedniej daty rejestru VAT, a data jest widoczna na odpowiednich stronach.</span><span class="sxs-lookup"><span data-stu-id="39dfb-158">When you update or post the documents, all taxes are posted by using the corresponding date of the VAT register, and the date appears on relevant pages.</span></span> <span data-ttu-id="39dfb-159">Ponadto przepisy wymagają, aby podatek VAT dotyczący ciągłego świadczenia usług, na przykład wynajmu, leasingu doradztwa czy ogrzewanie spełniał następujące kryteria:</span><span class="sxs-lookup"><span data-stu-id="39dfb-159">Additionally, regulations require that VAT on continuous delivery of services, such as renting, leasing, consulting, and heating, meet the following criteria:</span></span></p>
<ul>
<li><span data-ttu-id="39dfb-160">Podatek VAT musi być księgowany na dedykowanym koncie księgi głównej w dniu wystawienia faktury.</span><span class="sxs-lookup"><span data-stu-id="39dfb-160">VAT must be posted to a dedicated general ledger account on the invoice date.</span></span></li>
<li><span data-ttu-id="39dfb-161">Podatek VAT musi zostać przeniesiony ze specjalnych kont na konto naliczonego podatku lub konto rozrachunków z dostawcami i musi zostać uwzględniony w raporcie VAT w dniu wymagalności.</span><span class="sxs-lookup"><span data-stu-id="39dfb-161">VAT must be transferred from the special accounts to a sales tax receivable account or a payable account, and must be included in the VAT report on the due date.</span></span></li>
</ul>
<p><span data-ttu-id="39dfb-162">Aby spełnić te wymagania, można przenieść księgowania z księgi głównej na konto odroczonego podatku przychodzącego i konto odroczonego podatku wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="39dfb-162">To support these requirements, you can transfer General ledger postings to the Deferred incoming tax account and the Deferred outgoing tax account.</span></span> <span data-ttu-id="39dfb-163">Jednak najpierw należy spełnić następujące warunki wstępne:</span><span class="sxs-lookup"><span data-stu-id="39dfb-163">However, you must first complete the following prerequisites:</span></span></p>
<ul>
<li><span data-ttu-id="39dfb-164">Skonfiguruj konta księgi Odroczony VAT naliczony i Odroczony VAT należny w grupach księgowania.</span><span class="sxs-lookup"><span data-stu-id="39dfb-164">Set up the Deferred VAT Payable and Deferred VAT Receivable ledger accounts in ledger posting groups.</span></span></li>
<li><span data-ttu-id="39dfb-165">Włącz parametr <strong>Odroczony VAT</strong> dla grup podatków dla towarów.</span><span class="sxs-lookup"><span data-stu-id="39dfb-165">Enable the <strong>Deferred VAT</strong> parameter for item sales tax groups.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="39dfb-166">Data obowiązkowego podatku od towarów i usług</span><span class="sxs-lookup"><span data-stu-id="39dfb-166">Mandatory VAT date</span></span></td>
<td><span data-ttu-id="39dfb-167">Polska</span><span class="sxs-lookup"><span data-stu-id="39dfb-167">Poland</span></span></td>
<td>
<p><span data-ttu-id="39dfb-168">Można wymagać, aby data rejestru VAT była zawarta w rekordach transakcji zakupu i sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="39dfb-168">You can require that the date of the VAT register be included in purchase and sales transaction records.</span></span> <span data-ttu-id="39dfb-169">Dlatego datę rejestru VAT można przechwycić przed zaksięgowaniem transakcji.</span><span class="sxs-lookup"><span data-stu-id="39dfb-169">Therefore, the date of the VAT register can be captured before a transaction is posted.</span></span> <span data-ttu-id="39dfb-170">Ta funkcja ułatwia eliminację konieczności obsługi wielu transakcji na końcu okresu.</span><span class="sxs-lookup"><span data-stu-id="39dfb-170">This functionality helps you avoid having to handle multiple transactions at the end of the period.</span></span></p>
<p><span data-ttu-id="39dfb-171">Pole <strong>Data rejestru VAT</strong> można ustawić jako obowiązkowe przy księgowaniu transakcji odbiorcy lub dostawcy.</span><span class="sxs-lookup"><span data-stu-id="39dfb-171">You can make the <strong>Date of VAT register</strong> field mandatory when customer or vendor transactions are posted.</span></span> <span data-ttu-id="39dfb-172">Aby ustawić to pole jako obowiązkowe, włącz opcję <strong>Data podatku VAT jest wymagana</strong> dla powiązanego konta odbiorcy lub dostawcy.</span><span class="sxs-lookup"><span data-stu-id="39dfb-172">To make this field mandatory, enable the <strong>VAT date is required</strong> option for the related customer or vendor account.</span></span></p>
</td>
</tr>
</tbody>
</table>

