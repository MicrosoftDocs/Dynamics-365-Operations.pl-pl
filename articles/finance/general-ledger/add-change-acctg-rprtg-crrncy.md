---
title: Zmienianie waluty rozliczeniowej lub raportowania
description: W tym temacie wyjaśniono sposób zmiany waluty rozliczeniowej lub raportowania oraz dodawania waluty raportowania do konfiguracji księgi.
author: kweekley
ms.date: 05/05/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 38b2cdb618d92dca7909a145e7fc07ddfc5f4d45
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6017062"
---
# <a name="change-the-accounting-or-reporting-currency"></a><span data-ttu-id="f2ace-103">Zmienianie waluty rozliczeniowej lub raportowania</span><span class="sxs-lookup"><span data-stu-id="f2ace-103">Change the accounting or reporting currency</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2ace-104">W tym temacie wyjaśniono sposób zmiany waluty rozliczeniowej lub raportowania oraz dodawania waluty raportowania do konfiguracji księgi.</span><span class="sxs-lookup"><span data-stu-id="f2ace-104">This topic explains how to change the accounting or reporting currency, or add a reporting currency to the setup of a ledger.</span></span>

## <a name="symptom"></a><span data-ttu-id="f2ace-105">Objaw</span><span class="sxs-lookup"><span data-stu-id="f2ace-105">Symptom</span></span>

<span data-ttu-id="f2ace-106">Istnieje konieczność zmiany waluty rozliczeniowej lub raportowania lub dodania waluty raportowania do konfiguracji księgi.</span><span class="sxs-lookup"><span data-stu-id="f2ace-106">You want to change the accounting or reporting currency, or add a reporting currency to the ledger setup.</span></span> <span data-ttu-id="f2ace-107">Tego rodzaju sytuacja ma zazwyczaj miejsce w następujących scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="f2ace-107">This typically occurs in the following scenarios:</span></span>

- <span data-ttu-id="f2ace-108">W czasie konfigurowania firmy określono niewłaściwą walutę rozliczeniową lub walutę raportowania.</span><span class="sxs-lookup"><span data-stu-id="f2ace-108">The wrong accounting or reporting currency was specified when a legal entity was set up.</span></span> <span data-ttu-id="f2ace-109">Teraz trzeba zmienić tę walutę.</span><span class="sxs-lookup"><span data-stu-id="f2ace-109">You now want to change that currency.</span></span>
- <span data-ttu-id="f2ace-110">W czasie konfigurowania firmy nie określono waluty raportowania.</span><span class="sxs-lookup"><span data-stu-id="f2ace-110">No reporting currency was specified when a legal entity was set up.</span></span> <span data-ttu-id="f2ace-111">(Waluta raportowania jest opcjonalna). Teraz okazało się, że dodanie waluty raportowania może okazać się przydatne.</span><span class="sxs-lookup"><span data-stu-id="f2ace-111">(A reporting currency is optional.) You now want to add a reporting currency.</span></span>

<span data-ttu-id="f2ace-112">Organizacja, która nie używała dotychczas funkcji obsługi dwóch walut, chce rozpocząć korzystanie z niej.</span><span class="sxs-lookup"><span data-stu-id="f2ace-112">An organization that didn't previously use the Dual currency capability wants to start to use it.</span></span> <span data-ttu-id="f2ace-113">Tego rodzaju sytuacja ma zazwyczaj miejsce w scenariuszach opisanych poniżej.</span><span class="sxs-lookup"><span data-stu-id="f2ace-113">This issue typically occurs in the following scenarios.</span></span>

- <span data-ttu-id="f2ace-114">Waluta raportowania została określona podczas konfigurowania firmy, ale organizacja chce ją teraz usunąć.</span><span class="sxs-lookup"><span data-stu-id="f2ace-114">A reporting currency was specified when a legal entity was set up, but the organization now wants to remove the reporting currency.</span></span>
- <span data-ttu-id="f2ace-115">Organizacja uaktualnia rozwiązanie Microsoft Dynamics 365 Finance lub przeprowadza migrację do niego i chce zmienić walutę rozliczeniową lub raportowania.</span><span class="sxs-lookup"><span data-stu-id="f2ace-115">The organization is upgrading or migrating to Microsoft Dynamics 365 Finance, and wants to change the accounting or reporting currency.</span></span>

## <a name="resolution"></a><span data-ttu-id="f2ace-116">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="f2ace-116">Resolution</span></span>

<span data-ttu-id="f2ace-117">Najważniejsze jest to, czy w toku konfiguracji księgi w firmie zostały zaksięgowane jakiekolwiek transakcje (rzeczywiste lub budżetowe).</span><span class="sxs-lookup"><span data-stu-id="f2ace-117">The most important consideration is whether any transactions (actual or budget) have been posted in the legal entity for the ledger setup.</span></span> <span data-ttu-id="f2ace-118">**Jeśli dla firmy zostały zaksięgowane jakiekolwiek transakcje (rzeczywiste lub budżetowe), nie można zmienić waluty rozliczeniowej ani raportowania ani dodać waluty raportowania.**</span><span class="sxs-lookup"><span data-stu-id="f2ace-118">**You can't change the accounting or reporting currency, or add a reporting currency, if any transactions (actual or budget) have been posted in the legal entity.**</span></span> <span data-ttu-id="f2ace-119">W zależności od tego, czy transakcje zostały zaksięgowane, wykonaj kroki opisane w jednej z poniższych sekcji.</span><span class="sxs-lookup"><span data-stu-id="f2ace-119">Follow the steps in one of the following sections, depending on whether transactions have been posted.</span></span>

### <a name="no-transactions-have-been-posted"></a><span data-ttu-id="f2ace-120">Nie zaksięgowano żadnych transakcji</span><span class="sxs-lookup"><span data-stu-id="f2ace-120">No transactions have been posted</span></span>

1. <span data-ttu-id="f2ace-121">W firmie, dla której aktualizowane są waluty, przejdź do ustawień **Księga główna \> Ustawienia księgi \> Księga**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-121">In the legal entity that you're updating currencies for, go to **General ledger \> Ledger setup \> Ledger**.</span></span>
2. <span data-ttu-id="f2ace-122">Na stronie **Księga** wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-122">On the **Ledger** page, select **Edit**.</span></span>
3. <span data-ttu-id="f2ace-123">Na skróconej karcie **Waluta** wybierz walutę rozliczeniową i walutę raportowania do użycia dla firmy.</span><span class="sxs-lookup"><span data-stu-id="f2ace-123">On the **Currency** FastTab, select the accounting currency and reporting currency to use for the legal entity.</span></span>
4. <span data-ttu-id="f2ace-124">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-124">Select **Save**.</span></span>

<span data-ttu-id="f2ace-125">Jeśli pola waluty rozliczeniowej i waluty raportowania nie są dostępne na stronie **Księga**, w danej firmie została zaksięgowana co najmniej jedna transakcja (rzeczywista lub budżetowa).</span><span class="sxs-lookup"><span data-stu-id="f2ace-125">If the fields for the accounting currency and the reporting currency aren't available on the **Ledger** page, one or more transactions (actual or budget) have been posted in the legal entity.</span></span> <span data-ttu-id="f2ace-126">W związku z tym nie można zmieniać walut.</span><span class="sxs-lookup"><span data-stu-id="f2ace-126">Therefore, the currencies can't be changed.</span></span> <span data-ttu-id="f2ace-127">W takim przypadku wykonaj kroki opisane w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="f2ace-127">In this case, follow the steps in the next section.</span></span>

### <a name="transactions-have-been-posted"></a><span data-ttu-id="f2ace-128">Zaksięgowano transakcje</span><span class="sxs-lookup"><span data-stu-id="f2ace-128">Transactions have been posted</span></span>

<span data-ttu-id="f2ace-129">**Jeśli w firmie zostały zaksięgowane transakcje, jedynym sposobem na zmianę lub dodanie walut księgowania lub raportowania jest utworzenie nowej firmy z poprawnymi walutami.**</span><span class="sxs-lookup"><span data-stu-id="f2ace-129">**If transactions have been posted in the legal entity, the only way to change or add accounting and reporting currencies is to create a new legal entity that has the correct currencies.**</span></span> <span data-ttu-id="f2ace-130">W celu ułatwienia tego procesu moduł Zarządzanie danymi w systemie umożliwia skopiowanie rekordów konfiguracji i rekordów głównych z bieżącej do nowej firmy.</span><span class="sxs-lookup"><span data-stu-id="f2ace-130">To help make this process easier, Data management in the system lets you copy setup records and master records from the current legal entity to a new legal entity.</span></span>

<span data-ttu-id="f2ace-131">Zmiany walut księgowania i raportowania mają zastosowanie w całym systemie.</span><span class="sxs-lookup"><span data-stu-id="f2ace-131">Changes to the accounting and reporting currencies are pervasive.</span></span> <span data-ttu-id="f2ace-132">Mają zastosowanie nie tylko do księgi głównej, ale także do wszystkich ksiąg podrzędnych (Rozrachunki z odbiorcami, Rozrachunki z dostawcami, Zapasy, Projekt itp.), wszystkich rozwiązań niezależnych dostawców oprogramowania (ISV) i wszelkich wprowadzonych przez użytkownika rozszerzeń zawierających kwoty.</span><span class="sxs-lookup"><span data-stu-id="f2ace-132">They affect not only General ledger but also every subledger (Accounts receivable, Accounts payable, Inventory, Project, and so on), every independent software vendor (ISV) solutions, and any extension that you've made that stores amounts.</span></span>

<span data-ttu-id="f2ace-133">Proces znajdowania i przeliczania poszczególnych kwot na inną walutę może wiązać się z błędami.</span><span class="sxs-lookup"><span data-stu-id="f2ace-133">The process of finding and translating each amount to a different currency is subject to error.</span></span> <span data-ttu-id="f2ace-134">W związku z tym zespół inżynierów nie zatwierdzi skryptu, który zmienia lub dodaje waluty księgowania i raportowania.</span><span class="sxs-lookup"><span data-stu-id="f2ace-134">Therefore, the engineering team won't approve a script that changes or adds accounting and reporting currencies.</span></span> <span data-ttu-id="f2ace-135">Ponadto choć narzędzie, które było dostępne dla rozwiązania Microsoft Dynamics AX 2012, umożliwiało zmienianie i dodawanie walut księgowania i raportowania, to jest ono już przestarzałe i zostało wycofane zarówno dla rozwiązania AX 2012 R3, jak i dla rozwiązania Finance.</span><span class="sxs-lookup"><span data-stu-id="f2ace-135">Additionally, although a tool that used to be available for Microsoft Dynamics AX 2012 let you change or add accounting and reporting currencies, that tool was deprecated for both AX 2012 R3 and Finance.</span></span>

<span data-ttu-id="f2ace-136">Aby skopiować dane ustawień i dane główne z bieżącej do nowej firmy, należy wykonać kroki opisane poniżej.</span><span class="sxs-lookup"><span data-stu-id="f2ace-136">Follow these steps to copy the setup and master data from the current legal entity to a new legal entity.</span></span>

1. <span data-ttu-id="f2ace-137">Kliknij kolejno opcje **Obszary robocze \> Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-137">Go to **Workspaces \> Data management**.</span></span>
2. <span data-ttu-id="f2ace-138">Wybierz **Szablony** w grupie **Import/eksport**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-138">Select **Templates** under the **Import/Export** group.</span></span>
3. <span data-ttu-id="f2ace-139">Upewnij się, że szablony są dostępne.</span><span class="sxs-lookup"><span data-stu-id="f2ace-139">Make sure that templates are available.</span></span> <span data-ttu-id="f2ace-140">Jeśli żadne szablony nie są dostępne, zaznacz opcję **Załaduj szablony domyślne** i poczekaj na wygenerowanie szablonów.</span><span class="sxs-lookup"><span data-stu-id="f2ace-140">If no templates are available, select **Load default templates**, and wait for the templates to be generated.</span></span>
4. <span data-ttu-id="f2ace-141">Wróć do obszaru roboczego **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-141">Return to the **Data management** workspace.</span></span>
5. <span data-ttu-id="f2ace-142">Wybierz pozycję **Kopiuj do firmy**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-142">Select **Copy into legal entity**.</span></span>
6. <span data-ttu-id="f2ace-143">Nadaj grupie nazwę i wprowadź jej opis.</span><span class="sxs-lookup"><span data-stu-id="f2ace-143">Enter a group name and description.</span></span>
7. <span data-ttu-id="f2ace-144">W polu **Firma źródłowa** wybierz firmę, z której chcesz skopiować dane.</span><span class="sxs-lookup"><span data-stu-id="f2ace-144">In the **Source legal entity** field, select the legal entity to copy data from.</span></span>
8. <span data-ttu-id="f2ace-145">Na skróconej karcie **Firmy docelowe** wybierz pozycję **Utwórz firmy**, aby utworzyć nową firmę, do której będzie można skopiować dane firmy źródłowej.</span><span class="sxs-lookup"><span data-stu-id="f2ace-145">In the **Destination legal entities** FastTab, select **Create legal entities** to create a new legal entity that you can copy the source legal entity data to.</span></span> <span data-ttu-id="f2ace-146">Wybierz opcję **Wybierz istniejącą**, aby skopiować dane do istniejącej firmy.</span><span class="sxs-lookup"><span data-stu-id="f2ace-146">Select **Select existing** to copy data to an existing legal entity.</span></span>
9. <span data-ttu-id="f2ace-147">Opcjonalnie: ustaw dla pola **Kopiuj sekwencje numerów** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-147">Optional: Set the **Copy number sequences** field to **Yes**.</span></span> <span data-ttu-id="f2ace-148">(Ten krok jest zalecany w przypadku kopiowania danych).</span><span class="sxs-lookup"><span data-stu-id="f2ace-148">(This step is recommended when you copy data.)</span></span>
10. <span data-ttu-id="f2ace-149">W obszarze **Wybrane jednostki** wybierz pozycję **Dodaj szablon**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-149">In the **Selected entities** area, select **Add template**.</span></span>
11. <span data-ttu-id="f2ace-150">Wybierz szablon, którego chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="f2ace-150">Select the templates to use.</span></span> <span data-ttu-id="f2ace-151">Sugerowane szablony dla nowej firmy to **025 — Księga główna** i **Finanse**.</span><span class="sxs-lookup"><span data-stu-id="f2ace-151">Suggested templates for a new legal entity include **025 - General Ledger** and **Financials**.</span></span> <span data-ttu-id="f2ace-152">Zaleca się przejrzenie wszystkich innych dostępnych szablonów w celu ustalenia, czy żaden z nich nie spełnia odpowiednich wymagań.</span><span class="sxs-lookup"><span data-stu-id="f2ace-152">We recommend that you review all the other available templates to determine whether any of them apply to your requirements.</span></span>
12. <span data-ttu-id="f2ace-153">Wybierz pozycję **Kopiuj do firmy**, aby uruchomić proces wsadowy, w ramach którego zostaną utworzone wybrane jednostki, a następnie skopiuj je do firmy docelowej.</span><span class="sxs-lookup"><span data-stu-id="f2ace-153">Select **Copy into legal entity** to start a batch process that will create the selected entities and copy them into the destination legal entity.</span></span>
13. <span data-ttu-id="f2ace-154">Po zakończeniu procesu, ale przed zaksięgowaniem dowolnej transakcji, przejdź do księgi i zaktualizuj waluty rozliczeniową i raportowania zgodnie z opisem z wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="f2ace-154">After the process is completed, but before any transaction are posted, go to the ledger, and update the accounting and reporting currencies as described earlier in this topic.</span></span>

<span data-ttu-id="f2ace-155">W przypadku utworzenia nowej firmy w celu zmiany waluty rozliczeniowej lub raportowania upewnij się, że salda początkowe są przeliczane z walut starej firmy na nowe waluty.</span><span class="sxs-lookup"><span data-stu-id="f2ace-155">If you created a new legal entity so that you can change the accounting or reporting currency, verify that the beginning balances are translated from the currencies of the old legal entity to the new currencies.</span></span>

<span data-ttu-id="f2ace-156">Aby obejrzeć film, który pokazuje powyższe czynności, zobacz temat [Kopiuj do firmy](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017).</span><span class="sxs-lookup"><span data-stu-id="f2ace-156">For a video that shows the preceding steps, see [Copy Into Legal Entity](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017).</span></span>