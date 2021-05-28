---
title: Omówienie podatku indyjskiego potrąconego w źródle (TDS)
description: Ten temat zawiera szczegółowe informacje na temat podatku indyjskiego potrąconego w źródle (TDS). Dokumentacja dokumentów TDS zawiera funkcje tej funkcji.
author: kailiang
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 28ee843036e11bd37b97a065ce53d2eb860c79d9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023521"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a><span data-ttu-id="109b4-104">Omówienie podatku indyjskiego potrąconego w źródle (TDS)</span><span class="sxs-lookup"><span data-stu-id="109b4-104">Indian Tax Deducted at Source (TDS) overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="109b4-105">Ten temat zawiera szczegółowe informacje na temat podatku indyjskiego potrąconego w źródle (TDS).</span><span class="sxs-lookup"><span data-stu-id="109b4-105">This topic provides detailed information about Indian Tax Deducted at Source (TDS).</span></span>

<span data-ttu-id="109b4-106">Dokumentacja dokumentów TDS zawiera funkcje tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="109b4-106">The TDS documentation covers the functionality of this capability.</span></span> <span data-ttu-id="109b4-107">Wyjaśnia również, jak wykonać podstawową konfigurację TDS, obliczać TDS dla transakcji, zakończyć proces rozliczania TDS, rejestrować numery zaświadczeń TDS i generować zapytania TDS, wyciągi TDS i zaświadczenia TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-107">It also explains how to do the basic setup for TDS, calculate TDS on transactions, complete the TDS settlement process, record TDS certificate numbers, and generate TDS inquiries, TDS statements, and TDS certificates.</span></span> <span data-ttu-id="109b4-108">Dokumentacja obejmuje następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="109b4-108">The documentation includes the following topics:</span></span>

- [<span data-ttu-id="109b4-109">Podstawowa konfiguracja TDS</span><span class="sxs-lookup"><span data-stu-id="109b4-109">Basic setup for TDS</span></span>](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [<span data-ttu-id="109b4-110">Funkcjonalność projektanta formuł i limitu progowego używana do obliczania TDS</span><span class="sxs-lookup"><span data-stu-id="109b4-110">Formula designer and threshold limit functionality used for TDS calculation</span></span>](apac-ind-TDS-Formula-designer.md)
- [<span data-ttu-id="109b4-111">Obliczanie TDS dla faktur, płatności, skryptów dłużnych i transakcji międzyfirmowych</span><span class="sxs-lookup"><span data-stu-id="109b4-111">Calculation of TDS on invoices, payments, promissory notes, and intercompany transactions</span></span>](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [<span data-ttu-id="109b4-112">Okresowy proces rozliczenia KDPW i rozliczenia kwoty KDPW na rzecz sprzedawców upoważnionych do uiszczania podatku dochodowego</span><span class="sxs-lookup"><span data-stu-id="109b4-112">Periodic TDS settlement process and settlement of TDS amounts to TDS authority vendors</span></span>](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [<span data-ttu-id="109b4-113">Rejestracja i aktualizacja numerów i dat certyfikatów TDS</span><span class="sxs-lookup"><span data-stu-id="109b4-113">Recording and updating TDS certificate numbers and dates</span></span>](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a><span data-ttu-id="109b4-114">Wprowadzenie do TDS</span><span class="sxs-lookup"><span data-stu-id="109b4-114">Introduction to TDS</span></span>

<span data-ttu-id="109b4-115">Zgodnie z ustawą o podatku dochodowym z 1961 r., Podatek dochodowy jest potrącany u źródła przez odbiorcę usługi w momencie wpłaty zaliczki lub rozliczenia kredytu, w zależności od tego, co nastąpi wcześniej.</span><span class="sxs-lookup"><span data-stu-id="109b4-115">Per the Income tax Act, 1961, income tax is deducted at the source by the receiver of the service at the time of advance payment or accounting of credit, whichever occurs first.</span></span> <span data-ttu-id="109b4-116">Osoba dokonująca płatności musi odliczyć kwotę podatku i zapłacić dostawcy usługi jedynie saldo netto.</span><span class="sxs-lookup"><span data-stu-id="109b4-116">The person who makes the payment must deduct the tax amount and pay only the net balance to the provider of the service.</span></span> <span data-ttu-id="109b4-117">TDS jest stosowany do usług określonych przez rząd, a podatek jest odliczany przy użyciu stawek określonych przez rząd na dany okres.</span><span class="sxs-lookup"><span data-stu-id="109b4-117">TDS is applied on services that the government specifies, and the tax is deducted by using the rates that the government specifies for a period.</span></span> <span data-ttu-id="109b4-118">Stawka potrącenia jest oparta na stanie jednostki, która otrzymuje płatność lub zapewnia usługę.</span><span class="sxs-lookup"><span data-stu-id="109b4-118">The rate of deduction is based on the status of the entity that receives the payment or provides the service.</span></span> <span data-ttu-id="109b4-119">Do stanów należą: **Osoba**, **Hindu Undivided Family** (**HUF**), **Spółka**, **Firma**, **Stowarzyszenie osób** (**Association of Persons - AOP**), **Grupa osób** (**Body of Individuals - BOI**) i **Władze lokalne**.</span><span class="sxs-lookup"><span data-stu-id="109b4-119">Statuses include **Individual**, **Hindu Undivided Family** (**HUF**), **Company**, **Firm**, **Association of Persons** (**AOP**), **Body of Individuals** (**BOI**), and **Local authority**.</span></span>

<span data-ttu-id="109b4-120">W poniższych sekcjach znajduje się lista usług, których według dokumentów TDS dotyczy rząd Indii.</span><span class="sxs-lookup"><span data-stu-id="109b4-120">The following sections list the services that TDS is applied on, as specified by the Government of India.</span></span>

<span data-ttu-id="109b4-121">**Mieszkańców**</span><span class="sxs-lookup"><span data-stu-id="109b4-121">**Residents**</span></span>

- <span data-ttu-id="109b4-122">Dochód z wynagrodzenia (zgodnie z art. 192)</span><span class="sxs-lookup"><span data-stu-id="109b4-122">Income from salaries (Under section 192)</span></span>
- <span data-ttu-id="109b4-123">Dochód z odsetek od papierów wartościowych (zgodnie z art. 193)</span><span class="sxs-lookup"><span data-stu-id="109b4-123">Income from interest on securities (Under section 193)</span></span>
- <span data-ttu-id="109b4-124">Dochód z dywidendy (zgodnie z art. 194)</span><span class="sxs-lookup"><span data-stu-id="109b4-124">Income from dividend (Under section 194)</span></span>
- <span data-ttu-id="109b4-125">Dochód z odsetek (zgodnie z art. 194A)</span><span class="sxs-lookup"><span data-stu-id="109b4-125">Income from interest (Under section 194A)</span></span>
- <span data-ttu-id="109b4-126">Dochód na loteriach lub na loteriach (zgodnie z art. 194B)</span><span class="sxs-lookup"><span data-stu-id="109b4-126">Income from lotteries or puzzles (Under section 194B)</span></span>
- <span data-ttu-id="109b4-127">Wygranie z pul itp. (zgodnie z art. 194BB)</span><span class="sxs-lookup"><span data-stu-id="109b4-127">Winning from horse races etc. (Under section 194BB)</span></span>
- <span data-ttu-id="109b4-128">Zleceniobiorcy i podwykonawcy (zgodnie z art. 194C)</span><span class="sxs-lookup"><span data-stu-id="109b4-128">Contractors and sub-contractors (Under section 194C)</span></span>
- <span data-ttu-id="109b4-129">Prowizja ubezpieczeniowa (zgodnie z art. 194D)</span><span class="sxs-lookup"><span data-stu-id="109b4-129">Insurance commission (Under section 194D)</span></span>
- <span data-ttu-id="109b4-130">Dochód z depozytu w ramach krajowego programu oszczędnościowego (zgodnie z art. 194EE)</span><span class="sxs-lookup"><span data-stu-id="109b4-130">Income from deposit under national saving scheme (Under section 194EE)</span></span>
- <span data-ttu-id="109b4-131">Dochód z fundusz wspólnego inwestowania lub UTI (zgodnie z art. 194F)</span><span class="sxs-lookup"><span data-stu-id="109b4-131">Income from mutual fund or UTI (Under section 194F)</span></span>
- <span data-ttu-id="109b4-132">Prowizja, wynagrodzenie, nagroda itp. w przypadku sprzedaży lub loterii (zgodnie z art. 194G)</span><span class="sxs-lookup"><span data-stu-id="109b4-132">Commission, Remuneration, Prize etc., on sale or lottery (Under section 194G)</span></span>
- <span data-ttu-id="109b4-133">Płatność prowizji lub opłaty brokerskie (zgodnie z art. 194H)</span><span class="sxs-lookup"><span data-stu-id="109b4-133">Payment of Commission or brokerage (Under section 194H)</span></span>
- <span data-ttu-id="109b4-134">Wynajem (zgodnie z art. 194I)</span><span class="sxs-lookup"><span data-stu-id="109b4-134">Rent (Under section 194I)</span></span>
- <span data-ttu-id="109b4-135">Serwis zawodowy (zgodnie z art. 194J)</span><span class="sxs-lookup"><span data-stu-id="109b4-135">Professional service (Under section 194J)</span></span>
- <span data-ttu-id="109b4-136">Dochód z jednostek (zgodnie z art. 194K)</span><span class="sxs-lookup"><span data-stu-id="109b4-136">Income from Units (Under section 194K)</span></span>
- <span data-ttu-id="109b4-137">Płatność kompensacie w momencie nabycia pewnego majątku (zgodnie z art. 194LA)</span><span class="sxs-lookup"><span data-stu-id="109b4-137">Payment of compensation on acquisition of certain immovable property (Under section 194LA)</span></span>

<span data-ttu-id="109b4-138">**Nierezydenci**</span><span class="sxs-lookup"><span data-stu-id="109b4-138">**Non-residents**</span></span>

- <span data-ttu-id="109b4-139">Płatności dla organizacji sportowej lub sportowej nierezydentów (zgodnie z art. 194E)</span><span class="sxs-lookup"><span data-stu-id="109b4-139">Payments to Non-resident sportsmen or sports association (Under section 194E)</span></span>
- <span data-ttu-id="109b4-140">Inne sumy (zgodnie z art. 195)</span><span class="sxs-lookup"><span data-stu-id="109b4-140">Other sums (Under section 195)</span></span>
- <span data-ttu-id="109b4-141">Dochody w odniesieniu do jednostek nierezydentów (zgodnie z art. 196A)</span><span class="sxs-lookup"><span data-stu-id="109b4-141">Income in respect of units of non-residents (Under section 196A)</span></span>

    - <span data-ttu-id="109b4-142">Dochód z obligacji w walucie obcej lub akcji spółki indyjskiej (zgodnie z art. 196C)</span><span class="sxs-lookup"><span data-stu-id="109b4-142">Income from foreign currency bonds or shares of Indian Company (Under section 196C)</span></span>
    - <span data-ttu-id="109b4-143">Dochody zagranicznych inwestorów instytucjonalnych z tytułu papierów wartościowych (zgodnie z art. 196D)</span><span class="sxs-lookup"><span data-stu-id="109b4-143">Incomes of foreign institutional investors from securities (Under section 196D)</span></span>
    - <span data-ttu-id="109b4-144">Wynagrodzenie i wszystkie inne dodatnie dochody w ramach dowolnego dochodu (sekcja 192)</span><span class="sxs-lookup"><span data-stu-id="109b4-144">Salary and all other positive incomes under any head on income (Section 192)</span></span>
    - <span data-ttu-id="109b4-145">Odsetki od papierów wartościowych (zgodnie z art. 193)</span><span class="sxs-lookup"><span data-stu-id="109b4-145">Interest on securities (Section 193)</span></span>
    - <span data-ttu-id="109b4-146">Odsetki inne niż odsetki od papierów wartościowych (zgodnie z art. 194A)</span><span class="sxs-lookup"><span data-stu-id="109b4-146">Interest other than interest on securities (Section 194A)</span></span>
    - <span data-ttu-id="109b4-147">Płatności na rzecz wykonawców i podwykonawców (zgodnie z art. 194C)</span><span class="sxs-lookup"><span data-stu-id="109b4-147">Payments to contractors and sub-contractors (Section 194C)</span></span>
    - <span data-ttu-id="109b4-148">Wygrane na loteriach lub w krzyżykach (zgodnie z art. 194B)</span><span class="sxs-lookup"><span data-stu-id="109b4-148">Winnings from Lottery or crossword puzzles (Section 194B)</span></span>
    - <span data-ttu-id="109b4-149">Wygrane z wyścigów konnych (zgodnie z art. 194BB)</span><span class="sxs-lookup"><span data-stu-id="109b4-149">Winnings from horse races (Section 194BB)</span></span>
    - <span data-ttu-id="109b4-150">Komisja ubezpieczeniowa pokrywająca wszystkie płatności związane z zakupem działalności ubezpieczeniowej (zgodnie z art. 194D)</span><span class="sxs-lookup"><span data-stu-id="109b4-150">Insurance Commission covering all payments for procuring Insurance business (Section 194D)</span></span>
    - <span data-ttu-id="109b4-151">Wszelkie odsetki inne niż odsetki od papierów wartościowych należne nierezydentom niebędącym spółką lub spółce zagranicznej (zgodnie z art. 195)</span><span class="sxs-lookup"><span data-stu-id="109b4-151">Any interest other than interest on securities payable to non-residents not being a company or to a foreign company (Section 195)</span></span>
    - <span data-ttu-id="109b4-152">Wypłata dla sportowca niebędącego rezydentem, w tym sportowca lub stowarzyszenia lub instytucji sportowej.</span><span class="sxs-lookup"><span data-stu-id="109b4-152">Payment to non-resident sportsman including athlete or sports association or institution.</span></span> <span data-ttu-id="109b4-153">W przypadku sportowca niebędącego rezydentem, płatności z tytułu reklam i artykułów dotyczących dowolnej gry / sportu w Indiach w gazetach, magazynach itp.</span><span class="sxs-lookup"><span data-stu-id="109b4-153">In case of non-resident sportsman, payments in respect of advertisements as well as articles on any game/sports in India in newspapers, magazines, and so.</span></span> <span data-ttu-id="109b4-154">hest włączony (zgodnie z art. 194E)</span><span class="sxs-lookup"><span data-stu-id="109b4-154">is included (Section 194E)</span></span>
    - <span data-ttu-id="109b4-155">Płatność z tytułu depozytów w ramach NSS \[krajowego programu oszczędnościowego\] (zgodnie z art. 194EE)</span><span class="sxs-lookup"><span data-stu-id="109b4-155">Payment in respect of deposits under NSS \[National Savings Scheme\] (Section 194EE)</span></span>
    - <span data-ttu-id="109b4-156">Płatność na konto ponownego wykupu jednostek według funduszu wspólnego inwestowania lub UTI (zgodnie z art. 194F)</span><span class="sxs-lookup"><span data-stu-id="109b4-156">Payment on account of repurchase of Units by Mutual Fund or UTI (Section 194F)</span></span>
    - <span data-ttu-id="109b4-157">Płatność prowizji lub opłaty brokerskie (zgodnie z art. 194H)</span><span class="sxs-lookup"><span data-stu-id="109b4-157">Payment for Commission or brokerage (Section 194H)</span></span>
    - <span data-ttu-id="109b4-158">Zapłata za wynajem (sekcja 194I)</span><span class="sxs-lookup"><span data-stu-id="109b4-158">Payment of rent (Section 194I)</span></span>
    - <span data-ttu-id="109b4-159">Zapłata za usługi techniczne i zawodowe (sekcja 194J)</span><span class="sxs-lookup"><span data-stu-id="109b4-159">Payment of fees for professional or technical services (Section 194J)</span></span>
    - <span data-ttu-id="109b4-160">Prowizja dla magazynu, dystrybutorów, kupców i sprzedających biletów na loterię, w tym kupony (sekcja 194G)</span><span class="sxs-lookup"><span data-stu-id="109b4-160">Commission to Stockiest, distributors, buyers and sellers of Lottery tickets including remuneration or prize on such tickets (Section 194G)</span></span>
    - <span data-ttu-id="109b4-161">Przychód z jednostek nabytych w walucie obcej lub długoterminowych zyskach z kapitału powstałych w wyniku przeniesienia takich jednostek nabytych w walucie obcej (sekcja 196B)</span><span class="sxs-lookup"><span data-stu-id="109b4-161">Income from Units purchased in foreign currency or long-term capital gain arising from the transfer of such Units purchased in foreign currency (Section 196B)</span></span>
    - <span data-ttu-id="109b4-162">Płatność wszelkich dochodów niemówiąca rezydentów z tytułu odsetek lub dywidend od obligacji i akcji (sekcja 196C)</span><span class="sxs-lookup"><span data-stu-id="109b4-162">Payment of any income to non-residents in respect of interest or dividend on bonds and shares (Section 196C)</span></span>

<span data-ttu-id="109b4-163">Identyfikatory TDS są obliczane dla transakcji zakupu, sprzedaży, zwrotów sprzedaży, not korygjących, nabyć środków trwałych, przedpłat, płatności zaliczek, skryptów dłużnych, podatku od pracy i transakcji międzyfirmowych.</span><span class="sxs-lookup"><span data-stu-id="109b4-163">TDS is calculated on purchases, sales, sales returns, credit notes, fixed asset acquisitions, prepayments, advance payments, promissory notes, works tax, and intercompany transactions.</span></span>

> [!NOTE]
> <span data-ttu-id="109b4-164">W obecnym indyjskim scenariuszu podatku TDS nie jest obliczany na podstawie transakcji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="109b4-164">In the current Indian tax scenario, TDS isn't calculated on sales transactions.</span></span> <span data-ttu-id="109b4-165">Jednak system zawiera także przepisy służące do obliczania TDS, które mogą być odzyskane w przypadku transakcji sprzedaży, w szczególności w przypadku transakcji międzyfirmowych.</span><span class="sxs-lookup"><span data-stu-id="109b4-165">However, the system includes a provision to calculate TDS recoverable on sales transactions, especially for intercompany transactions.</span></span>

<span data-ttu-id="109b4-166">W obliczeniu TDS zawsze jest uwzględniany próg i próg wyjątków, które są zdefiniowane dla składnika TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-166">The calculation of TDS always considers the threshold and the exception threshold that are defined for the TDS component.</span></span>

<span data-ttu-id="109b4-167">Należy uruchomić okresowy proces rozliczenia podatku potrącanego u źródła, a płatności podatku potrącanego u źródła muszą zostać rozliczone na rzecz dostawców urzędu podatku potrącanego u źródła.</span><span class="sxs-lookup"><span data-stu-id="109b4-167">The periodic TDS settlement process must be run, and the TDS payments must be settled to TDS authority vendors.</span></span>

<span data-ttu-id="109b4-168">Numery i daty certyfikatów TDS otrzymanych od dostawców lub odbiorców mogą być rejestrowane i aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="109b4-168">The certificate numbers and dates for TDS certificates that are received from vendors or customers can be recorded and updated.</span></span> <span data-ttu-id="109b4-169">Dodatkowo wyciągi kwartalne na formularzu 26Q i formularzu 27Q oraz zaświadczenie na formularzu 16A dla TDS można wygenerować w Finance.</span><span class="sxs-lookup"><span data-stu-id="109b4-169">Additionally, Form 26Q and Form 27Q quarterly statements, and the Form 16A certificate for TDS, can be generated in Finance.</span></span>

## <a name="setting-up-and-working-with-tds"></a><span data-ttu-id="109b4-170">Konfigurowanie i praca z TDS</span><span class="sxs-lookup"><span data-stu-id="109b4-170">Setting up and working with TDS</span></span>

<span data-ttu-id="109b4-171">Oto przegląd procesu konfiguracji i pracy z TDS:</span><span class="sxs-lookup"><span data-stu-id="109b4-171">Here is an overview of the process for setting up and working with TDS:</span></span>

1. <span data-ttu-id="109b4-172">**Konfiguracja TDS:**</span><span class="sxs-lookup"><span data-stu-id="109b4-172">**TDS setup:**</span></span>

    - <span data-ttu-id="109b4-173">Konfigurowanie parametrów:</span><span class="sxs-lookup"><span data-stu-id="109b4-173">Parameter setup:</span></span>

        - <span data-ttu-id="109b4-174">W parametrach księgi głównej aktywuj parametry związane z TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-174">In General ledger parameters, activate parameters that are related to TDS.</span></span>
        - <span data-ttu-id="109b4-175">W parametrach księgi głównej skonfiguruj sekwencję numerów dla płatności potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="109b4-175">In General ledger parameters, set up the number sequence for withholding tax payments.</span></span>
        - <span data-ttu-id="109b4-176">Konfigurowanie parametrów podatku TDS w modułach Rozrachunki z dostawcami i Rozrachunki z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="109b4-176">Set up parameters in Accounts payable and Accounts receivable.</span></span>

    - <span data-ttu-id="109b4-177">Konfiguracja podstawowa:</span><span class="sxs-lookup"><span data-stu-id="109b4-177">Basic setup:</span></span>

        - <span data-ttu-id="109b4-178">Skonfiguruj numery rejestracji TDS firmy, odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="109b4-178">Set up TDS registration numbers for a company, customers, and vendors.</span></span>
        - <span data-ttu-id="109b4-179">Skonfiguruj grupy składników TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-179">Set up TDS component groups.</span></span>
        - <span data-ttu-id="109b4-180">Skonfiguruj składniki TDS, dołącz do nich grupy składników TDS oraz zdefiniuj dla nich próg i próg wyjątków.</span><span class="sxs-lookup"><span data-stu-id="109b4-180">Set up TDS components, attach TDS component groups to them, and define the threshold and exception threshold for them.</span></span>
        - <span data-ttu-id="109b4-181">Ustawianie urzędów TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-181">Set up TDS authorities.</span></span>
        - <span data-ttu-id="109b4-182">Ustaw okresy rozliczeniowe TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-182">Set up TDS settlement periods.</span></span>
        - <span data-ttu-id="109b4-183">Skonfiguruj kody podatków TDS i dołącz do nich składniki TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-183">Set up TDS tax codes, and attach TDS components to them.</span></span>
        - <span data-ttu-id="109b4-184">Skonfiguruj grupy podatkowe TDS i dołącz do nich kody podatków TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-184">Set up TDS tax groups, and attach TDS tax codes to them.</span></span>
        - <span data-ttu-id="109b4-185">W projektancie formuły zdefiniuj formułę, aby obliczyć TDS dla grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-185">In the formula designer, define a formula to calculate TDS for a TDS group.</span></span>
        - <span data-ttu-id="109b4-186">Rejestrowanie numerów certyfikatów koncesji TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-186">Record TDS concession certificate numbers.</span></span>

    - <span data-ttu-id="109b4-187">Konta księgowe i ustawienia firmy:</span><span class="sxs-lookup"><span data-stu-id="109b4-187">Ledger accounts and company setup:</span></span>

        - <span data-ttu-id="109b4-188">Skonfiguruj konta zobowiązań i należności TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-188">Set up TDS payable and receivable ledger accounts.</span></span>
        - <span data-ttu-id="109b4-189">Skonfiguruj odliczenie podatku i numer konta windykacyjnego (TAN) oraz kategorię typu odliczenia dla firmy.</span><span class="sxs-lookup"><span data-stu-id="109b4-189">Set up a Tax Deduction and Collection Account Number (TAN) and a deductor type category for the company.</span></span>

    - <span data-ttu-id="109b4-190">Inne ustawienia:</span><span class="sxs-lookup"><span data-stu-id="109b4-190">Other setup:</span></span>

        - <span data-ttu-id="109b4-191">Skonfiguruj harmonogram płatności, który zawiera alokację TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-191">Set up a payment schedule that includes TDS allocation.</span></span>
        - <span data-ttu-id="109b4-192">Skonfiguruj rodzaj opłaty za płatności na rzecz organu TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-192">Set up a payment fee type for payments to the TDS authority.</span></span>
        - <span data-ttu-id="109b4-193">Skonfiguruj informacje o grupach TDS, stałych numerach kont (PAN) i TAN dla dostawców i klientów.</span><span class="sxs-lookup"><span data-stu-id="109b4-193">Set up information about TDS groups, permanent account numbers (PANs), and TANs for vendors and customers.</span></span>

2. <span data-ttu-id="109b4-194">**Obliczanie TDS w transakcjach**</span><span class="sxs-lookup"><span data-stu-id="109b4-194">**Calculation of TDS in transactions:**</span></span>

    - <span data-ttu-id="109b4-195">Faktury i płatności</span><span class="sxs-lookup"><span data-stu-id="109b4-195">Invoices and payments</span></span>
    - <span data-ttu-id="109b4-196">Skrypty dłużne</span><span class="sxs-lookup"><span data-stu-id="109b4-196">Promissory notes</span></span>
    - <span data-ttu-id="109b4-197">Zaliczki</span><span class="sxs-lookup"><span data-stu-id="109b4-197">Advance payments</span></span>
    - <span data-ttu-id="109b4-198">Zaliczki</span><span class="sxs-lookup"><span data-stu-id="109b4-198">Prepayments</span></span>

3. <span data-ttu-id="109b4-199">**Rozliczenie TDS**</span><span class="sxs-lookup"><span data-stu-id="109b4-199">**TDS settlement:**</span></span>

    - <span data-ttu-id="109b4-200">Okresowy proces rozliczania TDS</span><span class="sxs-lookup"><span data-stu-id="109b4-200">Periodic TDS settlement process</span></span>
    - <span data-ttu-id="109b4-201">Rozliczenie płatności podatku potrącanego u źródła na rzecz dostawców urzędu podatku potrąconego u źródła i wygenerowanie dokumentu informacyjnego TDS</span><span class="sxs-lookup"><span data-stu-id="109b4-201">Settlement of TDS payments to TDS authority vendors and generation of TDS challan</span></span>

4. <span data-ttu-id="109b4-202">**Zapytania, wyciągi i certyfikaty TDS:**</span><span class="sxs-lookup"><span data-stu-id="109b4-202">**TDS inquiries, statements, and certificate:**</span></span>

    - <span data-ttu-id="109b4-203">Rejestruj i aktualizuj numery i daty certyfikatów TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-203">Record and update TDS certificate numbers and dates.</span></span>
    - <span data-ttu-id="109b4-204">Wygeneruj zapytanie dotyczące TDS i zaksięgowanego zapytania TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-204">Generate a TDS inquiry and a posted TDS inquiry.</span></span>
    - <span data-ttu-id="109b4-205">Generowanie formularzy 27A, formularzy 26Q i formularzy 27Q TDS oraz kwartalnych wyciągów e-TDS.</span><span class="sxs-lookup"><span data-stu-id="109b4-205">Generate Form 27A, Form 26Q, and Form 27Q TDS and e-TDS quarterly statements.</span></span>
    - <span data-ttu-id="109b4-206">Wygeneruj certyfikat TDS na formularzu 16A.</span><span class="sxs-lookup"><span data-stu-id="109b4-206">Generate a Form 16A TDS certificate.</span></span>
