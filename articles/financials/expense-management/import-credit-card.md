---
title: Import i obsługa transakcji kartą kredytową
description: W tym temacie wyjaśniono sposób importowania i obsługi transakcji kartą kredytową dotyczących wydatków. Te transakcje można skonfigurować tak, aby były automatycznie importowane wg cyklicznego harmonogramu lub można je importować ręcznie w razie potrzeby.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 9674cf495b7fdd40d8672580b9d10e9ebe626bb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565120"
---
# <a name="import-and-maintain-credit-card-transactions"></a><span data-ttu-id="67ccb-104">Import i obsługa transakcji kartą kredytową</span><span class="sxs-lookup"><span data-stu-id="67ccb-104">Import and maintain credit card transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67ccb-105">Transakcje kartą kredytową dotyczące wydatków można skonfigurować tak, aby były automatycznie importowane wg cyklicznego harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="67ccb-105">Expense-related credit card transactions can be set up so that they are automatically imported on a recurring schedule.</span></span> <span data-ttu-id="67ccb-106">Alternatywnie transakcje można zaimportować ręcznie w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="67ccb-106">Alternatively, the transactions can be manually imported as they are required.</span></span> <span data-ttu-id="67ccb-107">Transakcje kartą kredytową są importowane za pośrednictwem jednostki danych Transakcje kartą kredytową.</span><span class="sxs-lookup"><span data-stu-id="67ccb-107">The credit card transactions are imported through the Credit card transactions data entity.</span></span>

<span data-ttu-id="67ccb-108">Aby uzyskać więcej informacji o jednostkach danych, zobacz [Jednostki danych](../../dev-itpro/data-entities/data-entities.md).</span><span class="sxs-lookup"><span data-stu-id="67ccb-108">For more information about data entities, see [Data entities](../../dev-itpro/data-entities/data-entities.md).</span></span>

## <a name="import-credit-card-transactions"></a><span data-ttu-id="67ccb-109">Importowanie transakcji kart kredytowych</span><span class="sxs-lookup"><span data-stu-id="67ccb-109">Import credit card transactions</span></span>

1. <span data-ttu-id="67ccb-110">Na stronie **Transakcje karty kredytowej** wybierz opcję **Importuj transakcje**.</span><span class="sxs-lookup"><span data-stu-id="67ccb-110">On the **Credit card transactions** page, select **Import transactions**.</span></span> <span data-ttu-id="67ccb-111">Jeżeli otwierasz zarządzanie danymi po raz pierwszy, przed kontynuacją system musi zaktualizować listę jednostek danych.</span><span class="sxs-lookup"><span data-stu-id="67ccb-111">If you’re opening data management for the first time, the system must update the list of data entities before you can continue.</span></span>
2. <span data-ttu-id="67ccb-112">W polu **Nazwa** wprowadź unikatowy opis zadana.</span><span class="sxs-lookup"><span data-stu-id="67ccb-112">In the **Name** field, enter a unique description of the import job.</span></span>
3. <span data-ttu-id="67ccb-113">W polu **Format danych źródłowych** wybierz format pliku zawierający transakcje karty kredytowej do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="67ccb-113">In the **Source data format** field, select the format of the file that contains the credit card transactions to import.</span></span>
4. <span data-ttu-id="67ccb-114">Wybierz opcję **Przekaż**, a następnie znajdź i wybierz plik do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="67ccb-114">Select **Upload**, and then find and select the file to import.</span></span>
5. <span data-ttu-id="67ccb-115">Po przekazaniu pliku sprawdź poprawność mapowania pliku transakcji karty kredytowej i kolumn jednostki danych Transakcje karty kredytowej, wybierając łącze **Wyświetl mapę** na kafelku.</span><span class="sxs-lookup"><span data-stu-id="67ccb-115">After the file has been uploaded, validate the mapping of the credit card transaction file and the columns of the Credit card transactions data entity by selecting the **View map** link on the tile.</span></span> <span data-ttu-id="67ccb-116">Jeżeli występują błędy mapowania lub musisz zmienić mapowanie, wprowadź zmiany w mapowaniu na karcie **Wizualizacja mapowania** lub karcie **Szczegóły mapowania**.</span><span class="sxs-lookup"><span data-stu-id="67ccb-116">If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.</span></span>
6. <span data-ttu-id="67ccb-117">Aby zautomatyzować transakcje karty kredytowej, wybierz opcję **Utwórz cykliczne zadanie danych**.</span><span class="sxs-lookup"><span data-stu-id="67ccb-117">To automate the credit card transactions, select **Create recurring data job**.</span></span> <span data-ttu-id="67ccb-118">Następnie można ustawić cykle określający częstotliwość importowania transakcji karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="67ccb-118">You can then set the recurrence that defines how often credit card transactions should be imported.</span></span> <span data-ttu-id="67ccb-119">Po zakończeniu wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="67ccb-119">When you’ve finished, select **OK**.</span></span>
7. <span data-ttu-id="67ccb-120">Aby zaimportować wybrany plik teraz wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="67ccb-120">To import the selected file now, select **Import**.</span></span>
8. <span data-ttu-id="67ccb-121">Jeżeli podczas importowania wystąpi błąd, można wyświetlić dziennik wykonania lub dane pośrednie, aby zobaczyć błędy, które można usunąć, aby zapewnić pomyślny import.</span><span class="sxs-lookup"><span data-stu-id="67ccb-121">If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help guarantee a successful import.</span></span>

> [!NOTE]
> <span data-ttu-id="67ccb-122">Jeżeli musisz zaimportować plik w więcej niż jednym formacie, należy utworzyć osobne zadania importu dla każdego typu formatu.</span><span class="sxs-lookup"><span data-stu-id="67ccb-122">If you must import more than one file format, you must create separate import jobs for each format type.</span></span>

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a><span data-ttu-id="67ccb-123">Ponowne przypisywanie transakcji karty kredytowej dla pracowników, których zatrudnienie zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="67ccb-123">Reassign the credit card transactions for terminated employees</span></span>

<span data-ttu-id="67ccb-124">Po zakończeniu zatrudnienia pracownika jego konto usług Active Directory Domain Services (AD DS) jest wyłączane.</span><span class="sxs-lookup"><span data-stu-id="67ccb-124">After an employee record is terminated, the employee’s Active Directory Domain Services (AD DS) account is disabled.</span></span> <span data-ttu-id="67ccb-125">Mogą jednak istnieć aktywne transakcje karty kredytowej, które muszą zostać zaliczone i zwrócone.</span><span class="sxs-lookup"><span data-stu-id="67ccb-125">However, there might be active credit card transactions that must still be expensed and reimbursed.</span></span> <span data-ttu-id="67ccb-126">Na stronie **Transakcje karty kredytowej** można zmienić przypisanie pracownika dla każdej transakcji kartą kredytową, której powiązany pracownik zakończył zatrudnienie.</span><span class="sxs-lookup"><span data-stu-id="67ccb-126">From the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee has been terminated.</span></span>

<span data-ttu-id="67ccb-127">Wybierz co najmniej jedną transakcję karty kredytowej, a następnie wybierz opcję **Przypisz ponownie transakcje**.</span><span class="sxs-lookup"><span data-stu-id="67ccb-127">Select one or more credit card transactions, and then select **Reassign transactions**.</span></span> <span data-ttu-id="67ccb-128">Następnie możesz wybrać innego pracownika, aby przypisać do niego transakcje karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="67ccb-128">You can then select another employee to assign the credit card transactions to.</span></span> <span data-ttu-id="67ccb-129">Po zmianie przypisania transakcji kartą kredytową transakcje można wybrać dla raportu o wydatkach i opłacić za pomocą zwykłego procesu uiszczania należności wykazanych w raporcie z wydatków.</span><span class="sxs-lookup"><span data-stu-id="67ccb-129">After the credit card transactions have been reassigned, they can be selected for an expense report and paid through the usual process for expense report reimbursement.</span></span>
