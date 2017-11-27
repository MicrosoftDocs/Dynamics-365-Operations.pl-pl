---
title: "Wyświetlanie wpisów w arkuszu i transakcji"
description: "W tym artykule wyjaśniono różne sposoby, za pomocą których można przeglądać zapisy w arkuszu i transakcje."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 825dba31a7093e9d9460f5aab59a96507dafeb8a
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="view-journal-entries-and-transactions"></a><span data-ttu-id="653dc-103">Wyświetlanie wpisów w arkuszu i transakcji</span><span class="sxs-lookup"><span data-stu-id="653dc-103">View journal entries and transactions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="653dc-104">W tym artykule wyjaśniono różne sposoby, za pomocą których można przeglądać zapisy w arkuszu i transakcje.</span><span class="sxs-lookup"><span data-stu-id="653dc-104">This article explains the various ways that you can view journal entries and transactions.</span></span> 

<span data-ttu-id="653dc-105">Użytkownicy, którzy chcą wyświetlać arkusze i transakcje, mają wiele możliwości uzyskania dostępu do tych danych.</span><span class="sxs-lookup"><span data-stu-id="653dc-105">Users who want to view journals and transactions have several ways to access the data.</span></span> <span data-ttu-id="653dc-106">Mogą korzystać ze stron zapytania, które oferują możliwość przechodzenia na bardziej szczegółowe poziomy, a także używać różnych opcji raportów w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="653dc-106">They can take advantage of inquiry pages that provide drill-down ability, or they can use various report options in the general ledger.</span></span>

## <a name="voucher-transactions"></a><span data-ttu-id="653dc-107">Transakcje na załączniku</span><span class="sxs-lookup"><span data-stu-id="653dc-107">Voucher transactions</span></span>
<span data-ttu-id="653dc-108">**Transakcje na załączniku** to strona zapytania, na której można wybierać różne tabele i pola do określenia kryteriów szukanych sald lub transakcji.</span><span class="sxs-lookup"><span data-stu-id="653dc-108">**Voucher transactions** is an inquiry page where you can select from various tables and fields to specify criteria for the balance or transaction that you're searching for.</span></span> <span data-ttu-id="653dc-109">Na przykład można wyświetlić wszystkie transakcje z określonego dnia lub konta, albo wszystkie transakcje typu **operacyjnego** znajdujące się w warstwie księgowania.</span><span class="sxs-lookup"><span data-stu-id="653dc-109">For example, you can view all transactions for a specific date or account, or all transactions of the **Operating** type that are in a specific posting layer.</span></span> <span data-ttu-id="653dc-110">Domyślnie strona ta zawiera numer arkusza, załącznik, datę i konto główne, ale można dodać kolejne tabele, pola i kryteria w celu zawężenia kryteriów wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="653dc-110">By default, the page shows the journal number, voucher, date, and main account, but you can add additional tables, fields, and criteria to narrow down your search.</span></span>

## <a name="audit-trail"></a><span data-ttu-id="653dc-111">Dziennik inspekcji</span><span class="sxs-lookup"><span data-stu-id="653dc-111">Audit trail</span></span>
<span data-ttu-id="653dc-112">**Dziennik inspekcji** to strona zapytania, która pokazuje typy transakcji, opisy, informacje o tym, kto utworzył transakcje i kiedy zostały utworzone.</span><span class="sxs-lookup"><span data-stu-id="653dc-112">**Audit trail** is an inquiry page that shows the types of transactions, descriptions, who the transactions were created by, and when they were created.</span></span> <span data-ttu-id="653dc-113">Ze strony zapytania **dziennika inspekcji** można wyświetlić transakcje na załączniku.</span><span class="sxs-lookup"><span data-stu-id="653dc-113">From the **Audit trail** inquiry page, you can view the voucher transactions.</span></span>

## <a name="financial-reports"></a><span data-ttu-id="653dc-114">Raporty finansowe</span><span class="sxs-lookup"><span data-stu-id="653dc-114">Financial reports</span></span>
<span data-ttu-id="653dc-115">Można także przeglądać i analizować transakcje księgi głównej za pomocą raportów finansowych.</span><span class="sxs-lookup"><span data-stu-id="653dc-115">You can also explore and analyze general ledger transactions by running financial reports.</span></span> <span data-ttu-id="653dc-116">Ze względu na to, że projekt raportów finansowych może być oparty na kontach, wymiarach, kategoriach kont lub kombinacji tych elementów, można wyświetlać transakcje poprzez przechodzenie na bardziej szczegółowe poziomy.</span><span class="sxs-lookup"><span data-stu-id="653dc-116">Because the design of financial reports can be based on accounts, dimensions, account categories, or a combination of the three, you can view the transactions by drilling down in various ways.</span></span> <span data-ttu-id="653dc-117">Aby wyświetlić więcej informacji o transakcjach księgi głównej, można także uwzględnić wiele właściwości transakcji w projekcie raportu.</span><span class="sxs-lookup"><span data-stu-id="653dc-117">If you require more information for general ledger transactions, you can also include multiple transaction properties as part of the report design.</span></span> <span data-ttu-id="653dc-118">Ponadto, jeśli chcesz wyświetlić transakcje składające się na saldo księgi głównej, możesz przechodzić na bardziej szczegółowe poziomy do transakcji konta, tak samo jak ze strony listy **bilansu próbnego**.</span><span class="sxs-lookup"><span data-stu-id="653dc-118">Additionally, if you want to see the transactions that make up a general ledger balance, you can drill down to account transactions, just as you can from the **Trial balance** list page.</span></span>

## <a name="ledger-reports"></a><span data-ttu-id="653dc-119">Raporty księgi</span><span class="sxs-lookup"><span data-stu-id="653dc-119">Ledger reports</span></span>
<span data-ttu-id="653dc-120">Oprócz raportów finansowych można używać następujących raportów księgowych w celu wyświetlania transakcji księgi głównej:</span><span class="sxs-lookup"><span data-stu-id="653dc-120">In addition to the financial reports, you can use the following ledger reports to view general ledger transactions:</span></span>

-   <span data-ttu-id="653dc-121">**Zestawienie wymiarów** — ten raport pokazuje transakcje według dnia i kont; można także wyświetlić transakcje według wymiaru i okresu.</span><span class="sxs-lookup"><span data-stu-id="653dc-121">**Dimension statement** – This report shows transactions by day and account, and there are also options to show transactions by dimension and period.</span></span>
-   <span data-ttu-id="653dc-122">**Lista transakcji księgi** — ten raport pokazuje transakcje w walutach transakcji, księgowania i raportowania dla danego konta.</span><span class="sxs-lookup"><span data-stu-id="653dc-122">**Ledger transaction list** – This report shows transactions in transaction, accounting, and reporting currencies for an account.</span></span>
-   <span data-ttu-id="653dc-123">**Drukowanie arkusza** — W tym raporcie widać wynik opublikowanego arkusza.</span><span class="sxs-lookup"><span data-stu-id="653dc-123">**Print journal** – This report shows the result of a posted journal.</span></span> <span data-ttu-id="653dc-124">Można wygenerować raport według typu arkusza lub arkusza z numerem partii, albo dodać nowe pola.</span><span class="sxs-lookup"><span data-stu-id="653dc-124">You can run the report by journal batch number or journal type, or add additional fields.</span></span>
-   <span data-ttu-id="653dc-125">**Transakcje zaksięgowane według arkusza** — raport ten zawiera transakcje, które zostały zaksięgowane w arkuszu, pogrupowane według załącznika.</span><span class="sxs-lookup"><span data-stu-id="653dc-125">**Posted transactions by journal** – This report shows the transactions that have been posted to a journal, grouped by voucher.</span></span>
-   <span data-ttu-id="653dc-126">**Wykaz transakcji wg daty** — ten raport zawiera wszystkie transakcje według dat, łącznie z numerem arkusza, załącznikiem i kontem księgowym.</span><span class="sxs-lookup"><span data-stu-id="653dc-126">**Transaction list by date** – This report shows all the transactions by date, together with the journal number, voucher, and ledger account.</span></span> <span data-ttu-id="653dc-127">Ponadto pokazuje transakcje w walutach transakcji, księgowania i raportowania.</span><span class="sxs-lookup"><span data-stu-id="653dc-127">It also shows the transactions in the transaction, accounting, and reporting currencies.</span></span>
-   <span data-ttu-id="653dc-128">**Podstawa transakcji** — ten raport pokazuje konta według arkusza, transakcji, księgowania i waluty raportowania.</span><span class="sxs-lookup"><span data-stu-id="653dc-128">**Transaction origin** – This transaction report shows the account by journal, and by transaction, accounting, and reporting currency.</span></span> <span data-ttu-id="653dc-129">Pokazuje także każdy wiersz arkusza, który został użyty jako konto przeciwstawne.</span><span class="sxs-lookup"><span data-stu-id="653dc-129">It also shows each line of the journal that was used as an offset.</span></span>


##<a name="see-also"></a><span data-ttu-id="653dc-130">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="653dc-130">See also</span></span>
- [<span data-ttu-id="653dc-131">Salda głównego konta księgowego</span><span class="sxs-lookup"><span data-stu-id="653dc-131">General ledger account balances</span></span>](general-ledger-account-balances.md) 
- [<span data-ttu-id="653dc-132">Eksplorator źródeł księgowania</span><span class="sxs-lookup"><span data-stu-id="653dc-132">Accounting source explorer</span></span>](..\accounts-payable\accounting-source-explorer.md)
- [<span data-ttu-id="653dc-133">Raporty finansowe</span><span class="sxs-lookup"><span data-stu-id="653dc-133">Financial reporting</span></span>](financial-reporting-getting-started.md)
- [<span data-ttu-id="653dc-134">Wyświetlanie wpisów w arkuszu</span><span class="sxs-lookup"><span data-stu-id="653dc-134">View journal entries</span></span>](tasks/view-journal-entries-or-transactions.md)




