---
title: Wyświetlanie transakcji w rozliczeniu dla Europy Wschodniej
description: Ten temat zawiera informacje o stronie Transakcje w rozliczeniu dla odbiorców i dostawców.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendTransPostingLog_RU
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 270544
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 39fb7ca05c9abfcb7ae3668e8f995fa8adcbde1a
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538232"
---
# <a name="view-transactions-on-settlement-for-eastern-europe"></a><span data-ttu-id="1e7d5-103">Wyświetlanie transakcji w rozliczeniu dla Europy Wschodniej</span><span class="sxs-lookup"><span data-stu-id="1e7d5-103">View transactions on settlement for Eastern Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1e7d5-104">Ten temat zawiera informacje o stronie Transakcje w rozliczeniu dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-104">This topic provides information about the Transactions on settlement page for customers and vendors.</span></span>

<span data-ttu-id="1e7d5-105">Na stronie **Transakcje w rozliczeniu** można obejrzeć informacje o złożonych transakcjach rozliczenia dla odbiorcy lub dostawcy.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-105">Use the **Transactions on settlement** page to view information about complex settlement transactions for a customer or a vendor.</span></span> <span data-ttu-id="1e7d5-106">Ta funkcja jest dostępna tylko dla firm, których adres podstawowy znajduje się na Litwie, na Łotwie, w Estonii, w Czechach, na Węgrzech lub w Polsce.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-106">This feature is available only for legal entities that have their primary address in Lithuania, Latvia, Estonia, Czech Republic, Hungary, or Poland.</span></span> <span data-ttu-id="1e7d5-107">Do strony **Transakcje w rozliczeniu** można przejść z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="1e7d5-107">You can find the **Transactions on settlement** page at the following locations:</span></span>

-   <span data-ttu-id="1e7d5-108">**Rozrachunki z dostawcami** &gt; **Dostawcy** &gt; **Wszyscy dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-108">**Accounts payable** &gt; **Vendors** &gt; **All vendors**.</span></span> <span data-ttu-id="1e7d5-109">W okienku akcji na karcie **Dostawca** kliknij kolejno opcje **Transakcje** &gt; **Transakcje**.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-109">On the Action Pane, on the **Vendor** tab, click **Transactions** &gt; **Transactions**.</span></span> <span data-ttu-id="1e7d5-110">Na stronie **Transakcje dostawcy** wybierz transakcję, a następnie kliknij opcję **Transakcje w rozliczeniu**.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-110">On the **Vendor transactions** page, select a transaction, and then click **Transactions on settlement**.</span></span>
-   <span data-ttu-id="1e7d5-111">**Rozrachunki z odbiorcami** &gt; **Odbiorcy** &gt; **Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-111">**Accounts receivable** &gt; **Customers** &gt; **All customers**.</span></span> <span data-ttu-id="1e7d5-112">W okienku akcji na karcie **Odbiorca** kliknij opcję **Transakcje**.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-112">On the Action Pane, on the **Customer** tab, click **Transactions**.</span></span> <span data-ttu-id="1e7d5-113">Na stronie **Transakcje odbiorcy** wybierz transakcję, a następnie kliknij opcję **Transakcje w rozliczeniu**.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-113">On the **Customer transactions** page, select a transaction, and then click **Transactions on settlement**.</span></span>

<span data-ttu-id="1e7d5-114">Informacje dotyczące rozliczenia są rejestrowane i mogą być wyświetlane na stronie **Transakcje w rozliczeniu** dla transakcji, które zostały utworzone w następujących scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="1e7d5-114">Settlement-related information is captured and can be shown on the **Transactions on settlement** page for transactions that were created in the following scenarios:</span></span>

-   <span data-ttu-id="1e7d5-115">**Różnica kursowa** — Rozliczenie faktury i płatności generuje zrealizowaną lub niezrealizowaną różnicę kursową.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-115">**Exchange adjustment** – Settlement of an invoice and a payment generates a realized or unrealized exchange rate difference.</span></span>
-   <span data-ttu-id="1e7d5-116">**Zmiana profilu księgowania** — Rozliczane są dwa wpisy, takie jak faktura i nota kredytowa, które mają różne profile księgowania.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-116">**Posting profile change** – Two entries, such as an invoice and a credit memo, that have different posting profiles are settled.</span></span>
-   <span data-ttu-id="1e7d5-117">Przedpłata jest konwertowana na płatność lub płatność jest konwertowana na przedpłatę.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-117">A prepayment is converted to a payment, or a payment is converted to a prepayment.</span></span>
-   <span data-ttu-id="1e7d5-118">**Rabat gotówkowy** — Faktura jest rozliczana płatnością, od której potrącono kwotę rabatu.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-118">**Cash discount** – An invoice is settled with a payment that a discount amount has been deducted from.</span></span>
-   <span data-ttu-id="1e7d5-119">**Różnice groszowe** — Faktura jest rozliczana płatnością, która ma nieco inną kwotę niż faktura.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-119">**Penny difference** – An invoice is settled with a payment that has a slightly different amount than the invoice.</span></span>
-   <span data-ttu-id="1e7d5-120">**Warunkowe księgowanie podatku** — Faktura jest rozliczana płatnością, do której zastosowano podatek warunkowy.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-120">**Conditional tax posting** – An invoice is settled with a payment that conditional tax has been applied to.</span></span>
-   <span data-ttu-id="1e7d5-121">**Rozliczenie międzyfirmowe** — Funkcjonalność transakcji międzyfirmowych jest używana do rozliczenia faktury płatnością z wewnątrz organizacji.</span><span class="sxs-lookup"><span data-stu-id="1e7d5-121">**Cross-company settlement** – Intercompany functionality is used to settle an invoice with a payment from an organization.</span></span>




