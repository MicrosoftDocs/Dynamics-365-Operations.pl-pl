---
title: Księga Globalnego księgowania zapasów
description: Ten temat opisuje księgi Globalnego księgowania zapasów, które są zdefiniowane przez połączenie waluty, kalendarza, konwencji i powiązania z osobą prawną.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea3434675aa3b7f2304be93ef9b489747994fa9d
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273208"
---
# <a name="global-inventory-accounting-ledger"></a><span data-ttu-id="681bd-103">Księga Globalnego księgowania zapasów</span><span class="sxs-lookup"><span data-stu-id="681bd-103">Global Inventory Accounting ledger</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="681bd-104">Globalne księgowanie zapasów ma własny zestaw ksiąg.</span><span class="sxs-lookup"><span data-stu-id="681bd-104">Global Inventory Accounting has its own set of ledgers.</span></span> <span data-ttu-id="681bd-105">Za każdym razem, gdy dla danej osoby prawnej przetwarzana jest transakcja związana z inwentaryzacją, system może ją zaksięgować w dowolnej liczbie ksiąg Globalnej księgi zapasów, w zależności od potrzeb.</span><span class="sxs-lookup"><span data-stu-id="681bd-105">Each time an inventory-related transaction is processed for a relevant legal entity, the system can account for that transaction in any number of Global Inventory Accounting ledgers, as required.</span></span>

<span data-ttu-id="681bd-106">Księga główna to rejestr środków debetowych i kredytowych.</span><span class="sxs-lookup"><span data-stu-id="681bd-106">A ledger is a register of debit and credit measures.</span></span> <span data-ttu-id="681bd-107">Środki te są klasyfikowane za pomocą elementów kosztów i kont księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="681bd-107">These measures are classified by using cost elements and subledger accounts.</span></span> <span data-ttu-id="681bd-108">Księga Globalnego księgowania zapasów jest zdefiniowana przez połączenie waluty, kalendarza, konwencji i powiązania z osobą prawną.</span><span class="sxs-lookup"><span data-stu-id="681bd-108">A Global Inventory Accounting ledger is defined by its combination of a currency, a calendar, a convention, and an association with a legal entity.</span></span>

<span data-ttu-id="681bd-109">Aby skonfigurować księgi Globalnego księgowania zapasów, przejdź do **Globalnego księgowania zapasów \> Konfiguracji \> Ksiąg Globalnego księgowania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="681bd-109">To set up your Global Inventory Accounting ledgers, go to **Global inventory accounting \> Setup \> Global inventory accounting ledgers**.</span></span> <span data-ttu-id="681bd-110">Dla każdej księgi ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="681bd-110">For each ledger, set the following fields:</span></span>

- <span data-ttu-id="681bd-111">**Nazwa** — Wprowadź nazwę księgi.</span><span class="sxs-lookup"><span data-stu-id="681bd-111">**Name** – Enter the name of the ledger.</span></span>
- <span data-ttu-id="681bd-112">**Opis** – wprowadź opis księgi.</span><span class="sxs-lookup"><span data-stu-id="681bd-112">**Description** – Enter a description of the ledger.</span></span>
- <span data-ttu-id="681bd-113">**Kalendarz obrachunkowy** — umożliwia określenie kalendarza obrachunkowego księgi.</span><span class="sxs-lookup"><span data-stu-id="681bd-113">**Fiscal calendar** – Specify the fiscal calendar for the ledger.</span></span>
- <span data-ttu-id="681bd-114">**Waluta i typ kursu wymiany** — pola na tej skróconej karcie umożliwia wybór waluty rozliczeniowej używanej w księdze oraz typ kursu wymiany.</span><span class="sxs-lookup"><span data-stu-id="681bd-114">**Currency and exchange rate type** – Use the fields on this FastTab to select the accounting currency that the ledger uses, and the exchange rate type.</span></span> <span data-ttu-id="681bd-115">W wybranej walucie może być inna niż waluta używana przez podmiot prawny.</span><span class="sxs-lookup"><span data-stu-id="681bd-115">The currency that you select can differ from the currency that the legal entity uses.</span></span> <span data-ttu-id="681bd-116">W przypadku Globalnego księgowania zapasów użytkownicy mogą definiować dowolną liczbę ksiąg wyceny.</span><span class="sxs-lookup"><span data-stu-id="681bd-116">In Global Inventory Accounting, users can define as many costing ledgers as they require.</span></span> <span data-ttu-id="681bd-117">Globalne księgowanie zapasów obsługuje księgowanie zapasów w wielu walutach i w wielu cenach.</span><span class="sxs-lookup"><span data-stu-id="681bd-117">Global Inventory Accounting supports inventory accounting in multiple currencies and in multiple valuations.</span></span> <span data-ttu-id="681bd-118">Ustaw wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="681bd-118">Set the following fields:</span></span>

    - <span data-ttu-id="681bd-119">**Waluta** — umożliwia wybranie waluty wyceny, w jakiej są zachowywane wartości związane z zapasami.</span><span class="sxs-lookup"><span data-stu-id="681bd-119">**Currency** – Select the costing currency that inventory-related values are maintained in.</span></span> <span data-ttu-id="681bd-120">Te wartości obejmują wartość zapasów, koszt własny sprzedaży, zapas w drodze i wszystkie rodzaje odchylenia.</span><span class="sxs-lookup"><span data-stu-id="681bd-120">These values include the inventory value, cost of goods sold, inventory in transit, and all kinds of variance.</span></span>
    - <span data-ttu-id="681bd-121">**Typ kursu wymiany** — umożliwia wybór kursu wymiany, który system powinien użyć do konwersji kwoty transakcji w walucie transakcji oraz standardowego kosztu towarów na walutę wyceny.</span><span class="sxs-lookup"><span data-stu-id="681bd-121">**Exchange rate type** – Select the exchange rate that the system should use to convert the transaction amount in the transaction currency and the standard cost of the items into the costing currency.</span></span>

- <span data-ttu-id="681bd-122">**Nazwa konwencji** — umożliwia określenie konwencji.</span><span class="sxs-lookup"><span data-stu-id="681bd-122">**Convention name** – Specify a convention.</span></span> <span data-ttu-id="681bd-123">Konwencja jest zbiorem zasad, które ustalają sposób księgowania kosztów w tej księdze.</span><span class="sxs-lookup"><span data-stu-id="681bd-123">A convention is a collection of policies that establish how costs will be accounted in this ledger.</span></span>
- <span data-ttu-id="681bd-124">**Firma** — w księdze będą księgowane dokumenty zaksięgowane dla wybranej firmy.</span><span class="sxs-lookup"><span data-stu-id="681bd-124">**Legal entity** – The ledger will account the documents that are posted to the selected legal entity.</span></span>
- <span data-ttu-id="681bd-125">**Priming** — umożliwia określenie, czy transakcje magazynowe utworzone przed utworzeniem księgi powinny być przetwarzane zgodnie z walutą i konwencją w księdze.</span><span class="sxs-lookup"><span data-stu-id="681bd-125">**Priming** – Select whether inventory transactions that were created before the ledger was created should be processed according to the currency and convention in the ledger.</span></span> <span data-ttu-id="681bd-126">Należy wybrać jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="681bd-126">Select one of the following values:</span></span>

    - <span data-ttu-id="681bd-127">**Aktywacja** — księga powinna przetwarzać transakcje utworzone przed jej utworzeniem.</span><span class="sxs-lookup"><span data-stu-id="681bd-127">**Activated** – The ledger should process transactions that were created before the ledger was created.</span></span>
    - <span data-ttu-id="681bd-128">**Dezaktywacja** — księga powinna przetwarzać tylko transakcje utworzone po jej utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="681bd-128">**Deactivated** – The ledger should process only transactions that are created after the ledger was created.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="681bd-129">Po wprowadzeniu nowych dokumentów **nie** będzie można wrócić do tego pola i poprawić jego wartości.</span><span class="sxs-lookup"><span data-stu-id="681bd-129">You will **not** be able to come back and set this field after you enter new documents.</span></span>

- <span data-ttu-id="681bd-130">**Stan** — System automatycznie ustawia stan nowo utworzonych ksiąg na *Przygotowywanie*.</span><span class="sxs-lookup"><span data-stu-id="681bd-130">**Status** – The system automatically sets the status of newly created ledgers to *Prepare*.</span></span>
