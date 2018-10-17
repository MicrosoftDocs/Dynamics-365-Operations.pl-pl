---
title: Przetwarzanie arkuszy finansowych
description: "Ten temat opisuje funkcje programu Microsoft Dynamics 365 for Finance and Operations, które mogą ułatwić przetwarzanie arkusza finansowego, a także zagwarantować rejestrowanie właściwych danych i bezpieczeństwo dla aparatu wewnętrznej kontroli."
author: ShylaThompson
manager: AnnBe
ms.date: 09/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cf744bc41ffcca6d029da5dd2031ada607a0109b
ms.openlocfilehash: e77aafafed5c972a6ad8c064107306d3ebde0b79
ms.contentlocale: pl-pl
ms.lasthandoff: 09/24/2018

---

# <a name="general-journal-processing"></a><span data-ttu-id="29ffe-103">Przetwarzanie arkuszy finansowych</span><span class="sxs-lookup"><span data-stu-id="29ffe-103">General journal processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29ffe-104">Ten temat opisuje funkcje programu Microsoft Dynamics 365 for Finance and Operations, które mogą ułatwić przetwarzanie arkusza finansowego, a także zagwarantować rejestrowanie właściwych danych i bezpieczeństwo dla aparatu wewnętrznej kontroli.</span><span class="sxs-lookup"><span data-stu-id="29ffe-104">This topic describes capabilities in Microsoft Dynamics 365 for Finance and Operations that can help make general journal processing easier, and that can also help ensure that correct data is captured and internal control isn't compromised.</span></span>  

## <a name="journal-names"></a><span data-ttu-id="29ffe-105">Nazwy arkuszy</span><span class="sxs-lookup"><span data-stu-id="29ffe-105">Journal names</span></span>

<span data-ttu-id="29ffe-106">Jednym z najważniejszych obszarów do skonfigurowania są nazwy arkuszy.</span><span class="sxs-lookup"><span data-stu-id="29ffe-106">One of the most important areas to set up is journal names.</span></span> <span data-ttu-id="29ffe-107">Dobrze jest używać określonych nazw arkusza do każdego celu, np. międzyfirmowe, korekty naliczania i korekcja błędów.</span><span class="sxs-lookup"><span data-stu-id="29ffe-107">It's a good idea to define specific journal names for each purpose, such as intercompany, accrual adjustment, and error correction.</span></span> <span data-ttu-id="29ffe-108">Można dostosować nazwę każdego arkusza, aby wprowadzanie danych dla każdego celu było łatwe i bezpieczne.</span><span class="sxs-lookup"><span data-stu-id="29ffe-108">You can tailor each journal name to help make data entry for each purpose easy and secure.</span></span> 

<span data-ttu-id="29ffe-109">Na stronie **Nazwy arkuszy** można skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="29ffe-109">On the **Journal names** page, you can set up the following elements:</span></span>

-   <span data-ttu-id="29ffe-110">**Zatwierdzanie w ramach przepływu pracy** — aby podnieść poziom kontroli wewnętrznej, można zdefiniować przepływy pracy określające limity materiałów dla poszczególnych kroków sprawdzania i zatwierdzania na podstawie takich kryteriów, jak łączna kwota debetu.</span><span class="sxs-lookup"><span data-stu-id="29ffe-110">**Workflow approval** – To increase internal control, define journal workflows that establish materiality limits for review and approval steps, based on criteria such as total debit amount.</span></span> <span data-ttu-id="29ffe-111">Można skonfigurować przepływy pracy dla arkuszy finansowych na stronie **Przepływy pracy dla księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="29ffe-111">You set up workflows for the general journals on the **General ledger workflows** page.</span></span>
-   <span data-ttu-id="29ffe-112">**Wartości domyślne** — można wybrać wartości domyślne kont przeciwstawnych, waluty i wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="29ffe-112">**Default values** – Select default values for offset accounts, currency, and financial dimensions.</span></span>
-   <span data-ttu-id="29ffe-113">**Kontrola arkusza** — można skonfigurować ograniczenia dla typu firmy i konta, a także wartości segmentów.</span><span class="sxs-lookup"><span data-stu-id="29ffe-113">**Journal control** – You can set up restrictions on the company and account type, and also the segment values.</span></span> 

<span data-ttu-id="29ffe-114">**Przykłady**</span><span class="sxs-lookup"><span data-stu-id="29ffe-114">**Examples**</span></span>

<span data-ttu-id="29ffe-115">Nazwa arkusza może być używana tylko do korekt.</span><span class="sxs-lookup"><span data-stu-id="29ffe-115">A journal name can be used only for adjustments.</span></span> <span data-ttu-id="29ffe-116">W takim przypadku można wskazać, że dla wszystkich firm ważne jest tylko konto typu **Księga**.</span><span class="sxs-lookup"><span data-stu-id="29ffe-116">In this case, you can specify that only the **Ledger** account type is valid across all companies.</span></span> 

<span data-ttu-id="29ffe-117">[![Typy kont kontroli arkusza](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span><span class="sxs-lookup"><span data-stu-id="29ffe-117">[![Journal control account types](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span></span>

<span data-ttu-id="29ffe-118">Nazwa arkusza może być używana tylko dla określonego segmentu lub w określonym zakresie dla kont głównych.</span><span class="sxs-lookup"><span data-stu-id="29ffe-118">A journal name can be used only for a specific segment or for a range for main accounts.</span></span> 

<span data-ttu-id="29ffe-119">[![Segment kontroli arkusza](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span><span class="sxs-lookup"><span data-stu-id="29ffe-119">[![Journal control segment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span></span>

<span data-ttu-id="29ffe-120">Opcja **Automatyczne stornowanie** jest dostępna w arkuszach finansowych.</span><span class="sxs-lookup"><span data-stu-id="29ffe-120">The **Automatic reversal** option is available in general journals.</span></span> <span data-ttu-id="29ffe-121">Na przykład użytkownik ma korektę naliczania, jeśli dokument nie został jeszcze przetworzony, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="29ffe-121">For example, you have an accrual adjustment where the actual document hasn't yet been processed, as shown in the following illustration.</span></span>
<span data-ttu-id="29ffe-122">[![Stornowanie arkusza finansowego](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span><span class="sxs-lookup"><span data-stu-id="29ffe-122">[![General journal reversing](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span></span> 

<span data-ttu-id="29ffe-123">Dodatek programu Microsoft Excel z funkcjonalnością wpisów arkusza oferuje dodatkowy poziom automatyzacji i ułatwia wprowadzanie danych.</span><span class="sxs-lookup"><span data-stu-id="29ffe-123">The Microsoft Excel add-in for journal entry provides an additional level of automation and makes data entry easier.</span></span> <span data-ttu-id="29ffe-124">Działanie **Otwórz wiersze w programie Excel** jest dostępne na stronach **Arkusz finansowy** i **Załącznik arkusza**.</span><span class="sxs-lookup"><span data-stu-id="29ffe-124">The **Open lines in Excel** action is available on the **General journal** and **Journal voucher** pages.</span></span> 

<span data-ttu-id="29ffe-125">Na stronie **Arkusze okresowe** można skonfigurować dzienniki cykliczne automatyzujące przetwarzanie arkuszy.</span><span class="sxs-lookup"><span data-stu-id="29ffe-125">On the **Periodic journals** page, you can set up recurring journals to automate journal processing.</span></span> 

<span data-ttu-id="29ffe-126">Możesz skorzystać z szablonów załącznika w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="29ffe-126">You can use voucher templates at any time.</span></span> <span data-ttu-id="29ffe-127">Na stronie **Arkusz finansowy** działania **Zapisz** i **Wybierz szablon załącznika** są dostępne na stronie **Załącznik arkusza** w sekcji **Funkcje** dla wierszy załącznika.</span><span class="sxs-lookup"><span data-stu-id="29ffe-127">On the **General journals** page, the **Save** and **Select voucher template** actions are found on the **Journal voucher** page, under **Functions** for the voucher lines.</span></span>

## <a name="related-setup"></a><span data-ttu-id="29ffe-128">Pokrewna konfiguracja</span><span class="sxs-lookup"><span data-stu-id="29ffe-128">Related setup</span></span>
<span data-ttu-id="29ffe-129">Następująca konfiguracja nie jest właściwa dla arkuszy finansowych, ale ułatwia prawidłowe wprowadzanie danych.</span><span class="sxs-lookup"><span data-stu-id="29ffe-129">The following setup isn't specific to general journals, but will help ensure that data entry is correct data and easy.</span></span>

### <a name="main-account"></a><span data-ttu-id="29ffe-130">Konto główne</span><span class="sxs-lookup"><span data-stu-id="29ffe-130">Main account</span></span>

<span data-ttu-id="29ffe-131">Konfiguracja konta głównego oferuje wiele opcji przetwarzania arkusza finansowego:</span><span class="sxs-lookup"><span data-stu-id="29ffe-131">The main account setup provides many options for general journal processing:</span></span>

-   <span data-ttu-id="29ffe-132">**Wymagane debet lub kredyt** — użyj tej opcji, jeśli konto główne jest ograniczone do transakcji po stronie debetowej lub kredytowej.</span><span class="sxs-lookup"><span data-stu-id="29ffe-132">**DC/CR requirement** – Use this option if a main account is limited to debit or credit transactions.</span></span> <span data-ttu-id="29ffe-133">Po zweryfikowaniu lub zaksięgowaniu arkusza następuje sprawdzenie poprawności konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="29ffe-133">The setup is verified when a journal is validated or posted.</span></span>

-   <span data-ttu-id="29ffe-134">**Domyślne konto przeciwstawne**</span><span class="sxs-lookup"><span data-stu-id="29ffe-134">**Default offset account**</span></span>
-   <span data-ttu-id="29ffe-135">**Zawieszone** — pozwala zawiesić konto główne dla wprowadzania danych we wszystkich firmach lub dla konkretnej firmy.</span><span class="sxs-lookup"><span data-stu-id="29ffe-135">**Suspended** – Suspend a main account for data entry across all companies or for a specific company/legal entity.</span></span>
-   <span data-ttu-id="29ffe-136">**Nie zezwalaj na wprowadzanie ręczne** — uniemożliwia użytkownikom ręczne wprowadzanie wartości dla konta w arkuszach.</span><span class="sxs-lookup"><span data-stu-id="29ffe-136">**Do not allow manual entry** – Prevent users from manually entering a value for the account in journals.</span></span>
-   <span data-ttu-id="29ffe-137">**Domyślna waluta/Sprawdź poprawność waluty**</span><span class="sxs-lookup"><span data-stu-id="29ffe-137">**Default/Validate currency**</span></span>
-   <span data-ttu-id="29ffe-138">**Firma zastępuje** — to ustawienie jest właściwe dla zdefiniowanej firmy/podmiotu prawnego:</span><span class="sxs-lookup"><span data-stu-id="29ffe-138">**Legal entity override** – This setup is specific to the defined company/legal entity:</span></span>
    -   <span data-ttu-id="29ffe-139">**Domyślny podatek/Sprawdź poprawność podatku**</span><span class="sxs-lookup"><span data-stu-id="29ffe-139">**Default/Validate sales tax**</span></span>
    -   <span data-ttu-id="29ffe-140">**Wymiar domyślny** — **Niestałe** lub **Stała wartość**.</span><span class="sxs-lookup"><span data-stu-id="29ffe-140">**Default dimension** – **Not fixed** or **Fixed value**.</span></span> <span data-ttu-id="29ffe-141">**Stała wartość** pomaga zagwarantować, że wszystkie księgowania dla tego konta głównego zawsze używają wartości wymiarów określonych jako **Stałe**.</span><span class="sxs-lookup"><span data-stu-id="29ffe-141">**Fixed value** will help ensure that all postings for this main account always use any dimension value that is set up as **Fixed**.</span></span>
-   <span data-ttu-id="29ffe-142">**Weryfikacja księgowania**</span><span class="sxs-lookup"><span data-stu-id="29ffe-142">**Posting validation**</span></span>
    -   <span data-ttu-id="29ffe-143">**Weryfikacja użytkownika** — ta opcja pozwala kontrolować, którzy użytkownicy mogą księgować na koncie głównym.</span><span class="sxs-lookup"><span data-stu-id="29ffe-143">**User validation** – This option controls which users are allowed to post to a main account.</span></span>
    -   <span data-ttu-id="29ffe-144">**Weryfikacja typów księgowania** — ta opcja pozwala kontrolować, które typy księgowania są dopuszczalne na koncie głównym.</span><span class="sxs-lookup"><span data-stu-id="29ffe-144">**Posting type validation** – This option controls which posting types are allowed for a main account.</span></span>

### <a name="accounting-structures-and-advanced-rules-structures"></a><span data-ttu-id="29ffe-145">Struktury księgowania i struktury reguł zaawansowanych</span><span class="sxs-lookup"><span data-stu-id="29ffe-145">Accounting structures and advanced rules structures</span></span>

<span data-ttu-id="29ffe-146">Struktury księgowania i struktury zaawansowanych reguł są bardzo ważne do zagwarantowania, że dane, które są wymagane do raportowania finansowego i śledzenia wydajności, są rejestrowane przy przetwarzaniu arkusza finansowego i wszelkich dokumentów.</span><span class="sxs-lookup"><span data-stu-id="29ffe-146">Accounting structures and advanced rules structures are extremely important for ensuring that the data that is required for financial reporting and performance tracking is captured during general journal processing and any documentation.</span></span> <span data-ttu-id="29ffe-147">Struktury księgowania i struktury reguły zaawansowanych pozwalają dostosować sposób wprowadzania danych.</span><span class="sxs-lookup"><span data-stu-id="29ffe-147">Accounting structures and advanced rules structures let you tailor the data entry experience.</span></span> <span data-ttu-id="29ffe-148">Można zezwolić na wprowadzanie danych tylko dla wymiarów finansowych, które są odpowiednie w poszczególnych sytuacjach, a można też wymuszać wymaganie, by rejestrowane były tylko dane wymagane i rzetelne.</span><span class="sxs-lookup"><span data-stu-id="29ffe-148">You can allow data entry only for financial dimensions that are relevant in each situation, and can also enforce the requirement that required and accurate data always be captured.</span></span>

<span data-ttu-id="29ffe-149">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="29ffe-149">For more information, see the following topics:</span></span>
- <span data-ttu-id="29ffe-150">[Planowanie: Obsługa planu kont](plan-chart-of-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="29ffe-150">[Planning: Chart of accounts](plan-chart-of-accounts.md).</span></span> 
- [<span data-ttu-id="29ffe-151">Tworzenie reguł zaawansowanych dla arkuszy</span><span class="sxs-lookup"><span data-stu-id="29ffe-151">Create advanced rules for journals</span></span>](tasks/create-advanced-rules-journals.md)
- [<span data-ttu-id="29ffe-152">Tworzenie wpisu w arkuszu za pomocą szablonu</span><span class="sxs-lookup"><span data-stu-id="29ffe-152">Create a journal entry using a template</span></span>](tasks/create-journal-entry-template.md)
- [<span data-ttu-id="29ffe-153">Tworzenie i sprawdzanie arkuszy</span><span class="sxs-lookup"><span data-stu-id="29ffe-153">Create and validate journals</span></span>](tasks/create-validate-journals.md)
- [<span data-ttu-id="29ffe-154">Księgowanie arkuszy okresowych</span><span class="sxs-lookup"><span data-stu-id="29ffe-154">Post periodic journals</span></span>](tasks/post-periodic-journals.md)
- [<span data-ttu-id="29ffe-155">Przetwarzanie arkusza alokacji księgi</span><span class="sxs-lookup"><span data-stu-id="29ffe-155">Process ledger allocation journal</span></span>](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a><span data-ttu-id="29ffe-156">Symuluj księgowanie</span><span class="sxs-lookup"><span data-stu-id="29ffe-156">Simulate posting</span></span>
<span data-ttu-id="29ffe-157">Opcja **Symuluj księgowanie** znajduje się w menu **Sprawdź poprawność** w większości arkuszy.</span><span class="sxs-lookup"><span data-stu-id="29ffe-157">You can find **Simulate posting** on the **Validate** menu for most journals.</span></span> <span data-ttu-id="29ffe-158">Podczas sprawdzania poprawności arkusza za pomocą funkcji **Sprawdź poprawność** system bada arkusza pod kątem określonych błędów.</span><span class="sxs-lookup"><span data-stu-id="29ffe-158">When you validate a journal using the **Validate** function, the system tests the journal for specific error conditions.</span></span> <span data-ttu-id="29ffe-159">Jeśli używasz funkcji **Symuluj księgowanie**, system uruchamia wszystkie te same procesy, które są wykonywane podczas księgowania, ale faktycznie nie księguje arkusza.</span><span class="sxs-lookup"><span data-stu-id="29ffe-159">If you use the **Simulate posting** function, the system runs all of the same processes that are run during posting without actually posting the journal.</span></span> <span data-ttu-id="29ffe-160">Następnie można przejrzeć wyświetlone komunikaty o księgowaniu oraz poprawić wszystkie znalezione błędy, po czym kliknąć menu **Księguj**, aby zaksięgować arkusz.</span><span class="sxs-lookup"><span data-stu-id="29ffe-160">You can then review the posting messages that are displayed, fix any errors that you find, and then click the **Post** menu to post the journal.</span></span> 

<span data-ttu-id="29ffe-161">Funkcja **Symuluj księgowanie** jest niedostępna dla przetwarzania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="29ffe-161">**Simulate posting** is not available for batch processing.</span></span> <span data-ttu-id="29ffe-162">Jest jednak dostępny kod źródłowy umożliwiający symulację przetwarzania wsadowego i deweloperzy mogą za jego pomocą dodać tę funkcjonalność.</span><span class="sxs-lookup"><span data-stu-id="29ffe-162">However, there is code available to simulate posting in batch and developers can extend the code to add that functionality.</span></span>  

