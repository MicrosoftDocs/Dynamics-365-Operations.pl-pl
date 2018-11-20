---
title: "Rozliczenia księgi"
description: "W tym temacie wyjaśniono, jak na stronie Rozliczenia księgi rozliczać transakcji księgi i wycofywać rozliczenia."
author: mikefalkner
manager: aolson
ms.date: 09/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: cda5df9bec24bf8fc63ab3a5b2f3de9f84a03923
ms.openlocfilehash: b02a1a066913c9959e9a55e78789e5ff1a175c56
ms.contentlocale: pl-pl
ms.lasthandoff: 11/19/2018

---

# <a name="ledger-settlements"></a><span data-ttu-id="b114c-103">Rozliczenia księgi</span><span class="sxs-lookup"><span data-stu-id="b114c-103">Ledger settlements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b114c-104">Funkcjonalność rozliczeń księgi pozwala uzgadniać transakcje debetowe i kredytowe w księdze głównej i następnie oznaczać je jako rozliczone.</span><span class="sxs-lookup"><span data-stu-id="b114c-104">Ledger settlements let you match debit and credit transactions in the general ledger, and mark them as settled.</span></span> <span data-ttu-id="b114c-105">W ten sposób można uzyskać pewność, że powiązane transakcje zostały wzajemnie zbilansowane.</span><span class="sxs-lookup"><span data-stu-id="b114c-105">In this way, you can make sure that related transactions have been cleared.</span></span> <span data-ttu-id="b114c-106">Można również wycofywać rozliczenia, jeśli zostały dokonane przez pomyłkę.</span><span class="sxs-lookup"><span data-stu-id="b114c-106">You can also reverse settlements if they were made by mistake.</span></span>

## <a name="enable-advanced-ledger-settlements"></a><span data-ttu-id="b114c-107">Włączanie funkcjonalności zaawansowanego rozliczania księgi</span><span class="sxs-lookup"><span data-stu-id="b114c-107">Enable advanced ledger settlements</span></span>

<span data-ttu-id="b114c-108">Na stronie zaawansowanych rozliczeń księgi znajdują się dodatkowe funkcje filtrowania i wybierania transakcji.</span><span class="sxs-lookup"><span data-stu-id="b114c-108">The advanced ledger settlements page provides additional capabilities for filtering and selecting transactions.</span></span> <span data-ttu-id="b114c-109">Aby włączyć stronę zaawansowanych rozliczeń księgi, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b114c-109">To enable advanced ledger settlements page, follow these steps.</span></span>

1. <span data-ttu-id="b114c-110">Wybierz kolejno opcje **Księga główna** \> **Ustawienia księgi** \> **Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="b114c-110">Select **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span> 
2. <span data-ttu-id="b114c-111">Na karcie **Rozliczenia księgi** ustaw opcję **Zaawansowane rozliczenie księgi** na **Tak**, aby włączyć funkcjonalność zaawansowanego rozliczania księgi.</span><span class="sxs-lookup"><span data-stu-id="b114c-111">On the **Ledger settlements** tab, set the **Advanced ledger settlement** option to **Yes** to turn on the advanced ledger settlement functionality.</span></span> <span data-ttu-id="b114c-112">Strona z zaawansowanymi ustawieniami **Rozliczenia księgi** będzie używana po wybraniu opcji **Rozliczenia księgi** w oknie **Zadania okresowe**.</span><span class="sxs-lookup"><span data-stu-id="b114c-112">The advanced **Ledger settlements** page will be used when you select **Ledger settlements** in the **Periodic tasks**.</span></span> 
3. <span data-ttu-id="b114c-113">Musisz wprowadzić listę kont, które mają być używane to rozliczeń księgi dla każdego planu kont.</span><span class="sxs-lookup"><span data-stu-id="b114c-113">You must enter the list of accounts to use for ledger settlements for each chart of accounts.</span></span> <span data-ttu-id="b114c-114">Ta lista jest używana do filtrowania transakcji wyświetlanych na stronie **Rozliczenia księgi**.</span><span class="sxs-lookup"><span data-stu-id="b114c-114">This list is used to filter the list of transactions that appears on the **Ledger settlements** page.</span></span> <span data-ttu-id="b114c-115">Na liście **Plan kont** wybierz plan kont, a następnie wybierz opcję **Nowy**, aby dodać nowe konta do listy.</span><span class="sxs-lookup"><span data-stu-id="b114c-115">In the **Chart of accounts** list, select a chart of accounts, and then select **New** to add new accounts to the list.</span></span>

## <a name="settle-transactions-by-using-the-advanced-ledger-settlements-page"></a><span data-ttu-id="b114c-116">Rozliczanie transakcji za pomocą strony zaawansowanych rozliczeń księgi</span><span class="sxs-lookup"><span data-stu-id="b114c-116">Settle transactions by using the advanced ledger settlements page</span></span>

<span data-ttu-id="b114c-117">W celu rozliczenia transakcji księgi wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="b114c-117">To settle ledger transactions, follow these steps.</span></span>

1. <span data-ttu-id="b114c-118">Wybierz kolejno opcje **Księga główna** \> **Zadania okresowe** \> **Rozliczenia księgi**.</span><span class="sxs-lookup"><span data-stu-id="b114c-118">Select **General ledger** \> **Periodic tasks** \> **Ledger settlements**.</span></span>
2. <span data-ttu-id="b114c-119">Ustaw filtry w górnej części strony:</span><span class="sxs-lookup"><span data-stu-id="b114c-119">Set the filters at the top of the page:</span></span>

    - <span data-ttu-id="b114c-120">Wybierz zakres dat lub kliknij opcję **Kod zakresu dat**, aby przedział został wypełniony automatycznie.</span><span class="sxs-lookup"><span data-stu-id="b114c-120">Select a date range, or select **Date interval code** to automatically fill in the date range.</span></span>
    - <span data-ttu-id="b114c-121">W razie potrzeby zmień warstwę księgowania.</span><span class="sxs-lookup"><span data-stu-id="b114c-121">Change the posting layer as you require.</span></span>
    - <span data-ttu-id="b114c-122">Aby osobno wyświetlać konto księgowe i wymiary, wybierz zestaw wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="b114c-122">To show the ledger account and dimensions separately, select a financial dimension set.</span></span>

3. <span data-ttu-id="b114c-123">Wybierz opcję **Wyświetl transakcje**, aby wyświetlić wszystkie transakcje zgodne z ustawionymi filtrami oraz z listą kont określonych podczas konfigurowania listy planu kont w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="b114c-123">Select **Display transactions** to show all the transactions that match the filters that you set and the list of accounts that you specified when you set up the chart of accounts list in the previous section.</span></span> <span data-ttu-id="b114c-124">Jeśli zmodyfikujesz którykolwiek filtr lub zestaw wymiarów, należy ponownie kliknąć opcję **Wyświetl transakcje**.</span><span class="sxs-lookup"><span data-stu-id="b114c-124">If you change any of the filters or the dimension sets, you must select **Display transactions** again.</span></span>
4. <span data-ttu-id="b114c-125">Wybierz jeden lub więcej wierszy, które chcesz objąć rozliczeniem.</span><span class="sxs-lookup"><span data-stu-id="b114c-125">Select one or more lines that you're considering for settlement.</span></span> <span data-ttu-id="b114c-126">Wartość pola **Wybrana kwota** u góry strony zwiększy się lub zmniejszy o łączną kwotę w zaznaczonych wierszach.</span><span class="sxs-lookup"><span data-stu-id="b114c-126">The value of the **Selected amount** field at the top of the page increases or decreases by the total amount on the lines that you selected.</span></span>
5. <span data-ttu-id="b114c-127">Po zakończeniu wybierania transakcji wybierz opcję **Oznacz wybrane**.</span><span class="sxs-lookup"><span data-stu-id="b114c-127">After you've finished selecting transactions, select **Mark selected**.</span></span> <span data-ttu-id="b114c-128">Dla każdej wybranej transakcji w kolumnie **Oznaczone** pojawi się znacznik wyboru.</span><span class="sxs-lookup"><span data-stu-id="b114c-128">A check mark appears in the **Marked** column for each transaction that you selected.</span></span> <span data-ttu-id="b114c-129">Ponadto wartość pola **Oznaczona kwota** nad siatką zwiększy się lub zmniejszy o łączną kwotę w oznaczonych wierszach.</span><span class="sxs-lookup"><span data-stu-id="b114c-129">Additionally, the value of the **Marked amount** field above the grid increases or decreases by the total amount on the lines that you marked.</span></span>
6. <span data-ttu-id="b114c-130">Gdy pole **Oznaczona kwota** ma wartość **0** (zero), wybierz opcję **Rozlicz oznaczone transakcje**.</span><span class="sxs-lookup"><span data-stu-id="b114c-130">When the **Marked amount** value is **0** (zero), select **Settle marked transactions**.</span></span> <span data-ttu-id="b114c-131">Stan oznaczonych transakcji zostanie zaktualizowany na **Rozliczone**.</span><span class="sxs-lookup"><span data-stu-id="b114c-131">The status of the marked transactions is updated to **Settled**.</span></span>

## <a name="make-transactions-easier-to-find"></a><span data-ttu-id="b114c-132">Ułatwienie znajdowania transakcji</span><span class="sxs-lookup"><span data-stu-id="b114c-132">Make transactions easier to find</span></span>

<span data-ttu-id="b114c-133">Strona **Rozliczenia księgi** zawiera funkcje, które ułatwiają zobaczenie transakcji potrzebnych do rozliczenia.</span><span class="sxs-lookup"><span data-stu-id="b114c-133">The **Ledger settlements** page includes capabilities that make it easier to see the transactions that you need for settlement.</span></span>

- <span data-ttu-id="b114c-134">Przycisk **Usuń oznaczenie wybranych** czyści pole **Oznaczone** we wszystkich zaznaczonych wierszach.</span><span class="sxs-lookup"><span data-stu-id="b114c-134">The **Unmark selected** button clears the **Marked** field for all lines that are selected.</span></span>
- <span data-ttu-id="b114c-135">Filtr **Oznaczone** umożliwia filtrowanie transakcji na podstawie tego, czy ich pole **Oznaczone** jest zaznaczone, czy wyczyszczone.</span><span class="sxs-lookup"><span data-stu-id="b114c-135">The **Marked** filter lets you filter transactions based on whether the **Marked** field for them is selected or cleared.</span></span>
- <span data-ttu-id="b114c-136">Filtr **Stan** umożliwia filtrowanie transakcji w oparciu o to, czy ich stan to **Rozliczone**, czy **Nie rozliczono**.</span><span class="sxs-lookup"><span data-stu-id="b114c-136">The **Status** filter lets you filter transactions based on whether their status is **Settled** or **Not settled**.</span></span>
- <span data-ttu-id="b114c-137">Przycisk **Sortuj według kwoty bezwzględnej** pozwala sortować kwoty według wartości bezwzględnych, dzięki czemu można pogrupować pozycje debetowe i kredytowe mające te same kwoty.</span><span class="sxs-lookup"><span data-stu-id="b114c-137">The **Sort by absolute amount** button lets you sort the amounts by absolute value, so that you can group together debits and credits that have the same amount.</span></span>

## <a name="reverse-a-settlement"></a><span data-ttu-id="b114c-138">Wycofywanie rozliczenia</span><span class="sxs-lookup"><span data-stu-id="b114c-138">Reverse a settlement</span></span>

<span data-ttu-id="b114c-139">Można cofnąć rozliczenie, która nastąpiło przez pomyłkę.</span><span class="sxs-lookup"><span data-stu-id="b114c-139">You can reverse a settlement that was made by mistake.</span></span>

1. <span data-ttu-id="b114c-140">Wykonaj kroki od 1 do 3 w sekcji „Rozliczanie transakcji za pomocą strony zaawansowanych rozliczeń księgi”, aby wyświetlić żądane transakcje.</span><span class="sxs-lookup"><span data-stu-id="b114c-140">Follow steps 1 through 3 in the "Settle transactions by using advanced ledger settlements page" section to show the transactions that you're looking for.</span></span>
2. <span data-ttu-id="b114c-141">W filtrze **Stan** wybierz wartość **Rozliczone**.</span><span class="sxs-lookup"><span data-stu-id="b114c-141">In the **Status** filter, select **Settled**.</span></span>
3. <span data-ttu-id="b114c-142">Wybierz jeden lub więcej wierszy, które chcesz objąć wycofaniem.</span><span class="sxs-lookup"><span data-stu-id="b114c-142">Select one or more lines that you're considering for reversal.</span></span> <span data-ttu-id="b114c-143">Wartość pola **Wybrana kwota** u góry strony zwiększy się lub zmniejszy o łączną kwotę w zaznaczonych wierszach.</span><span class="sxs-lookup"><span data-stu-id="b114c-143">The value of the **Selected amount** field at the top of the page increases or decreases by the total amount on the lines that you selected.</span></span>
4. <span data-ttu-id="b114c-144">Po zakończeniu wybierania transakcji wybierz opcję **Oznacz wybrane**.</span><span class="sxs-lookup"><span data-stu-id="b114c-144">After you've finished selecting transactions, select **Mark selected**.</span></span> <span data-ttu-id="b114c-145">Dla każdej wybranej transakcji w kolumnie **Oznaczone** pojawi się znacznik wyboru.</span><span class="sxs-lookup"><span data-stu-id="b114c-145">A check mark appears in the **Marked** column for each transaction that you selected.</span></span> <span data-ttu-id="b114c-146">Ponadto wartość pola **Oznaczona kwota** u góry strony zwiększy się lub zmniejszy o łączną kwotę w oznaczonych wierszach.</span><span class="sxs-lookup"><span data-stu-id="b114c-146">Additionally, the value of the **Marked amount** field at the top of the page increases or decreases by the total amount on the lines that you marked.</span></span>
5. <span data-ttu-id="b114c-147">Gdy pole **Oznaczona kwota** ma wartość **0** (zero), wybierz opcję **Wycofaj oznaczone transakcje**.</span><span class="sxs-lookup"><span data-stu-id="b114c-147">When the **Marked amount** value is **0** (zero), select **Reverse marked transactions**.</span></span> <span data-ttu-id="b114c-148">Stan oznaczonych transakcji zostanie zaktualizowany na **Nie rozliczono**.</span><span class="sxs-lookup"><span data-stu-id="b114c-148">The status of the marked transactions is updated to **Not settled**.</span></span>

## <a name="update-the-list-of-accounts-that-are-included-in-the-list-of-transactions"></a><span data-ttu-id="b114c-149">Aktualizowanie listy kont uwzględnionych na liście transakcji</span><span class="sxs-lookup"><span data-stu-id="b114c-149">Update the list of accounts that are included in the list of transactions</span></span>

<span data-ttu-id="b114c-150">Wybierz opcję **Konta rozliczenia księgi**, aby otworzyć okno dialogowe służące do edytowania kont uwzględnionych na liście transakcji.</span><span class="sxs-lookup"><span data-stu-id="b114c-150">Select **Ledger settlement accounts** to open a dialog box where you can edit the accounts that are included in the list of transactions.</span></span> <span data-ttu-id="b114c-151">Kliknij przycisk **Nowy**, aby dodać nowe konta do listy.</span><span class="sxs-lookup"><span data-stu-id="b114c-151">Select **New** to add new accounts to the list.</span></span> <span data-ttu-id="b114c-152">Ta lista jest używana do filtrowania transakcji wyświetlanych na stronie **Rozliczenia księgi**.</span><span class="sxs-lookup"><span data-stu-id="b114c-152">This list is used to filter the list of transactions that appears on the **Ledger settlements** page.</span></span>

