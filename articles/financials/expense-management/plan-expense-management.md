---
title: "Konfigurowanie zarządzania wydatkami"
description: "W tym artykule opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed skonfigurowaniem modułu Zarządzanie wydatkami w programie Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: aa7c7bfaf4301904e1b7ae242efaf8b660fb076a
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="configure-expense-management"></a><span data-ttu-id="9254d-103">Konfigurowanie zarządzania wydatkami</span><span class="sxs-lookup"><span data-stu-id="9254d-103">Configure expense management</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="9254d-104">W tym temacie opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed skonfigurowaniem modułu Zarządzanie wydatkami w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9254d-104">This topic describes the considerations and the decisions that you must make during the planning process before you configure Expense management in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="9254d-105">W funkcji Zarządzanie wydatkami można przechowywać informacje o metodach płatności, wnioski wyjazdowe, raporty z wydatków oraz zasady itp.</span><span class="sxs-lookup"><span data-stu-id="9254d-105">In Expense management, you can store information about payment methods, travel requisitions, expense reports, policies, and so on.</span></span>

<span data-ttu-id="9254d-106">Ponieważ wiele decyzji podjętych podczas planowania konfiguracji zarządzania wydatkami jest opartych na hierarchii i strukturze finansowej organizacji, musisz konsultować się z dokumentami planowania dla tych dokumentów.</span><span class="sxs-lookup"><span data-stu-id="9254d-106">Because many of the decisions that you make when you plan your configuration for Expense management are based on your organization’s hierarchy and financial structure, you must refer to the planning documents for those areas.</span></span>

## <a name="intercompany-expenses"></a><span data-ttu-id="9254d-107">Wydatki międzyfirmowe</span><span class="sxs-lookup"><span data-stu-id="9254d-107">Intercompany expenses</span></span>

<span data-ttu-id="9254d-108">Jeśli włączysz wydatki międzyfirmowe, zezwalasz firmom i pracownikom na tworzenie wydatków lub pobieranie opłat w imieniu lub od innych zatrudniających firm w obrębie organizacji.</span><span class="sxs-lookup"><span data-stu-id="9254d-108">When you enable intercompany expenses, you allow legal entities and employees to incur expenses on behalf of another legal entity, and collect payment from the legal entity of employment within your organization.</span></span> <span data-ttu-id="9254d-109">Przykładowo pracownik w firmie A kończy projekt dla firmy B, a projekt powoduje powstanie wydatków związanych z wyjazdem.</span><span class="sxs-lookup"><span data-stu-id="9254d-109">For example, an employee in legal entity A completes a project for legal entity B, and the project incurs travel related expenses.</span></span> <span data-ttu-id="9254d-110">Jeżeli wydatki międzyfirmowe są włączone, pracownik może przesłać raport o wydatkach, który spowoduje zaksięgowanie wydatku w firmie B, a wydatek musi zostać zwrócony przez firmę A. Jeśli Twoja organizacja nie ma wielu podmiotów prawnych, nie musisz włączać wydatków międzyfirmowych.</span><span class="sxs-lookup"><span data-stu-id="9254d-110">If intercompany expenses are enabled, the employee can then file an expense report that will post the expense to legal entity B, and the expense must then be paid by legal entity A. If your organization doesn’t have multiple legal entities, you don’t have to enable intercompany expenses.</span></span>

<span data-ttu-id="9254d-111">**Decyzja:** Czy chcesz włączyć wydatki międzyfirmowe?</span><span class="sxs-lookup"><span data-stu-id="9254d-111">**Decision:** Do you want to enable intercompany expenses?</span></span>

## <a name="financial-management"></a><span data-ttu-id="9254d-112">Zarządzanie finansami</span><span class="sxs-lookup"><span data-stu-id="9254d-112">Financial management</span></span>

<span data-ttu-id="9254d-113">Zarządzanie wydatkami jest ściśle zintegrowane z zarządzaniem finansami organizacji.</span><span class="sxs-lookup"><span data-stu-id="9254d-113">Expense management is tightly integrated with the financial management of your organization.</span></span> <span data-ttu-id="9254d-114">Wiele konfiguracji zarządzania wydatkami będzie opierać się na decyzjach dotyczących finansów organizacji.</span><span class="sxs-lookup"><span data-stu-id="9254d-114">Lots of your configuration for Expense management will be based on the decisions that you’ve made about your organization’s finances.</span></span> <span data-ttu-id="9254d-115">W poniższych sekcjach opisano różne obszary, które wymagają planowania i decyzji opartych na decyzjach finansowych i wskazówkach organizacji pochodzących od zespołu kierowniczego.</span><span class="sxs-lookup"><span data-stu-id="9254d-115">The following sections describe the various areas that require planning and decisions, based on your organization’s financial decisions and guidance from your leadership team.</span></span>

### <a name="per-diems"></a><span data-ttu-id="9254d-116">Diety</span><span class="sxs-lookup"><span data-stu-id="9254d-116">Per diems</span></span>

<span data-ttu-id="9254d-117">Musisz zdefiniować pracownika dla diet oferowanych przez organizację.</span><span class="sxs-lookup"><span data-stu-id="9254d-117">You must define the employee per diems that your organization provides.</span></span> <span data-ttu-id="9254d-118">Ponieważ diety są zazwyczaj używane w celu pokrycia wydatków, takich jak wyżywienie, zakwaterowanie i inne koszty dodatkowe, można utworzyć reguły dla odpisów diet oferowanych przez organizację.</span><span class="sxs-lookup"><span data-stu-id="9254d-118">Because per diems are typically used to cover expenses such as meals, lodging, and other incidental expenses, you can create rules for the per diem allowances that your organization offers.</span></span> <span data-ttu-id="9254d-119">Stawki diet można określić na podstawie sezonu roku lub lokalizacji podróży albo ich obu.</span><span class="sxs-lookup"><span data-stu-id="9254d-119">per diem rates can be based on the time of year, the travel location, or both.</span></span> <span data-ttu-id="9254d-120">Podczas definiowania reguły obliczania diety można określić, że pewien procent stawki diety zostanie wstrzymany, jeśli pracownik otrzymuje bezpłatne posiłki lub usługi.</span><span class="sxs-lookup"><span data-stu-id="9254d-120">When you define a per diem rule, you can specify that a percentage of the per diem rate will be withheld if a worker receives complimentary meals or services.</span></span> <span data-ttu-id="9254d-121">Można także zdefiniować poziom stawek diet, aby wyznaczyć minimalną i maksymalną liczbę godzin, dla których można zastosować stawkę diety dla wyjazdu pracownika.</span><span class="sxs-lookup"><span data-stu-id="9254d-121">You can also define per diem rate tiers to set the minimum and maximum number of hours that the per diem rate can be applied to a worker’s travel.</span></span>

<span data-ttu-id="9254d-122">**Decyzje:**</span><span class="sxs-lookup"><span data-stu-id="9254d-122">**Decisions:**</span></span>

- <span data-ttu-id="9254d-123">Domyślne reguły obliczania diet dla pierwszego i ostatniego dnia:</span><span class="sxs-lookup"><span data-stu-id="9254d-123">Default per diem rules for the first and last days:</span></span>

    - <span data-ttu-id="9254d-124">Jaka jest minimalna liczba godzin, co to której pracownik może zgłosić roszczenie z dzień, i mimo to otrzymać dietę?</span><span class="sxs-lookup"><span data-stu-id="9254d-124">What is the minimum number of hours that an employee can claim for a day and still receive a per diem?</span></span>
    - <span data-ttu-id="9254d-125">Czy obowiązuje zmniejszenie kwoty, jaka jest oferowana za posiłki w pierwszym i ostatnim dniu?</span><span class="sxs-lookup"><span data-stu-id="9254d-125">Is there a reduction in the amount that is offered for meals for the first day and last day?</span></span> <span data-ttu-id="9254d-126">Czy istnieje redukcja, jaki jest procent redukcji?</span><span class="sxs-lookup"><span data-stu-id="9254d-126">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="9254d-127">Czy obowiązuje zmniejszenie kwoty, jaka jest oferowana za hotele w pierwszym i ostatnim dniu?</span><span class="sxs-lookup"><span data-stu-id="9254d-127">Is there a reduction in the amount that is offered for a hotel for the first day and last day?</span></span> <span data-ttu-id="9254d-128">Czy istnieje redukcja, jaki jest procent redukcji?</span><span class="sxs-lookup"><span data-stu-id="9254d-128">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="9254d-129">Czy obowiązuje zmniejszenie kwoty, jaka jest oferowana za inne wydatki poniesione w pierwszym i ostatnim dniu?</span><span class="sxs-lookup"><span data-stu-id="9254d-129">Is there a reduction in the amount that is offered for other expenses that are incurred on the first day and last day?</span></span> <span data-ttu-id="9254d-130">Czy istnieje redukcja, jaki jest procent redukcji?</span><span class="sxs-lookup"><span data-stu-id="9254d-130">If there is a reduction, what is the percentage of the reduction?</span></span>

- <span data-ttu-id="9254d-131">Domyślne reguły obliczania diet:</span><span class="sxs-lookup"><span data-stu-id="9254d-131">Default per diem rules:</span></span>

    - <span data-ttu-id="9254d-132">Czy obowiązuje procentowe zmniejszenie przydziału diety za każdy posiłek, jeśli na przykład posiłek jest bezpłatny?</span><span class="sxs-lookup"><span data-stu-id="9254d-132">Is there a percentage reduction in the per diem allowance for each meal if, for example, the meal is complimentary?</span></span> <span data-ttu-id="9254d-133">Czy istnieje redukcja, jaki jest procent redukcji dla każdego posiłku?</span><span class="sxs-lookup"><span data-stu-id="9254d-133">If there is a reduction, what is the reduction percentage for each meal?</span></span>
    - <span data-ttu-id="9254d-134">Obniżka za posiłek jest obliczana za dzień, za wyjazd lub według liczby posiłków dziennie?</span><span class="sxs-lookup"><span data-stu-id="9254d-134">Is the meal reduction calculated per day, per trip, or by the number of meals per day?</span></span>
    - <span data-ttu-id="9254d-135">Czy kwoty diety powinny być zaokrąglane standardowo czy w górę?</span><span class="sxs-lookup"><span data-stu-id="9254d-135">Should per diem amounts be rounded in the regular manner or rounded up?</span></span>
    - <span data-ttu-id="9254d-136">Czy diety są obliczane według cykli 24-godzinnych czy według dni kalendarzowych?</span><span class="sxs-lookup"><span data-stu-id="9254d-136">Are per diems calculated on a 24-hour period or on a calendar day?</span></span>

- <span data-ttu-id="9254d-137">Reguły obliczania diet na podstawie lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="9254d-137">Per diem rules that are based on location:</span></span>

    - <span data-ttu-id="9254d-138">Stawki diet różnią się w zależności od lokalizacji?</span><span class="sxs-lookup"><span data-stu-id="9254d-138">Do per diem rates vary according to location?</span></span> <span data-ttu-id="9254d-139">Jakie lokalizacje są uwzględnione?</span><span class="sxs-lookup"><span data-stu-id="9254d-139">What locations are included?</span></span>
    - <span data-ttu-id="9254d-140">Jeżeli stawki diet różnią się w zależności od lokalizacji, jaka kwota procentowo jest dostępna dla następujących typów wydatków w każdej lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="9254d-140">If per diem rates vary according to location, for each location, what percentage amount is provided for the following types of expenses:</span></span>

        - <span data-ttu-id="9254d-141">Posiłki</span><span class="sxs-lookup"><span data-stu-id="9254d-141">Meals</span></span>
        - <span data-ttu-id="9254d-142">Hotel</span><span class="sxs-lookup"><span data-stu-id="9254d-142">Hotel</span></span>
        - <span data-ttu-id="9254d-143">Inne wydatki</span><span class="sxs-lookup"><span data-stu-id="9254d-143">Other expenses</span></span>

### <a name="expense-management-journals-and-accounts"></a><span data-ttu-id="9254d-144">Konta i arkusze zarządzania wydatkami</span><span class="sxs-lookup"><span data-stu-id="9254d-144">Expense management journals and accounts</span></span>

<span data-ttu-id="9254d-145">Zarządzanie wydatkami wymaga użycia wielu arkuszy i kont.</span><span class="sxs-lookup"><span data-stu-id="9254d-145">Expense management requires that you use multiple journals and accounts.</span></span> <span data-ttu-id="9254d-146">Trzeba zdecydować, na przykład, czy to samo konto jest używane dla zaliczek gotówkowych i spory dotyczących kart kredytowych.</span><span class="sxs-lookup"><span data-stu-id="9254d-146">You must decide, for example, whether the same account is used for cash advances and credit card disputes.</span></span>

<span data-ttu-id="9254d-147">**Decyzje:**</span><span class="sxs-lookup"><span data-stu-id="9254d-147">**Decisions:**</span></span>

- <span data-ttu-id="9254d-148">Do którego arkusza księgi księgowane są zatwierdzone raporty wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-148">Which ledger journal are approved expense reports posted to?</span></span>
- <span data-ttu-id="9254d-149">Które konto jest używane dla zaliczek gotówkowych?</span><span class="sxs-lookup"><span data-stu-id="9254d-149">Which account is used for cash advances?</span></span>
- <span data-ttu-id="9254d-150">Czy zaliczki gotówkowe powinny być księgowane natychmiast?</span><span class="sxs-lookup"><span data-stu-id="9254d-150">Should cash advances be posted immediately?</span></span>

### <a name="payment-methods"></a><span data-ttu-id="9254d-151">Metody płatności</span><span class="sxs-lookup"><span data-stu-id="9254d-151">Payment methods</span></span>

<span data-ttu-id="9254d-152">Jeśli zezwalasz pracownikom na ponoszenie wydatków w imieniu Twojej firmy, musisz określić metody płatności, których pracownicy mogą używać.</span><span class="sxs-lookup"><span data-stu-id="9254d-152">When you allow employees to incur expenses on behalf of your business, you must define the payment methods that employees are allowed to use.</span></span> <span data-ttu-id="9254d-153">Na przykład możesz zezwolić pracownikom na używanie gotówki lub firmowej karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="9254d-153">For example, you might allow employees to use cash or a corporate credit card.</span></span> <span data-ttu-id="9254d-154">Możesz też zezwolić pracownikom na używanie osobistych kart kredytowych, a następnie zwracać im pieniądze.</span><span class="sxs-lookup"><span data-stu-id="9254d-154">You might also allow employees to use personal credit cards, and then reimburse the employees.</span></span> <span data-ttu-id="9254d-155">Należy podjąć następujące decyzje dla każdej dozwolonej metody płatności.</span><span class="sxs-lookup"><span data-stu-id="9254d-155">You must make the following decisions for each payment method that you allow.</span></span>

<span data-ttu-id="9254d-156">**Decyzje:**</span><span class="sxs-lookup"><span data-stu-id="9254d-156">**Decisions:**</span></span>

- <span data-ttu-id="9254d-157">Jakie metody płatności są dozwolone?</span><span class="sxs-lookup"><span data-stu-id="9254d-157">What payment methods are allowed?</span></span>
- <span data-ttu-id="9254d-158">Kto jest właścicielem wydatków poniesionych przy użyciu metody płatności?</span><span class="sxs-lookup"><span data-stu-id="9254d-158">Who owns the payment method expenses?</span></span>
- <span data-ttu-id="9254d-159">Czy jest dostępny typ konta przeciwstawnego?</span><span class="sxs-lookup"><span data-stu-id="9254d-159">Is there an offset account type?</span></span> <span data-ttu-id="9254d-160">Jeśli dostępne jest konto typu przeciwstawnego, co nim jest?</span><span class="sxs-lookup"><span data-stu-id="9254d-160">If there is an offset account type, what is it?</span></span>
- <span data-ttu-id="9254d-161">Jeśli dostępne jest konto przeciwstawne, co nim jest?</span><span class="sxs-lookup"><span data-stu-id="9254d-161">If there is an offset account, what is the account?</span></span>
- <span data-ttu-id="9254d-162">Jeśli metodą płatności jest karta kredytowa, czy metoda płatności powinna być używana tylko do obsługi zaimportowanych transakcji?</span><span class="sxs-lookup"><span data-stu-id="9254d-162">If the payment method is a credit card, should the payment method be used only with imported transactions?</span></span>

### <a name="expense-categories-and-shared-categories"></a><span data-ttu-id="9254d-163">Kategorie wydatków i udostępniane kategorie</span><span class="sxs-lookup"><span data-stu-id="9254d-163">Expense categories and shared categories</span></span>

<span data-ttu-id="9254d-164">Gdy pracownicy tworzą raport wydatków, każdy zarejestrowany wydatek musi być skojarzony z kategorią wydatków.</span><span class="sxs-lookup"><span data-stu-id="9254d-164">When employees create an expense report, each expense that they record must be associated with an expense category.</span></span> <span data-ttu-id="9254d-165">Kategorie wydatków pochodzą z kategorii udostępnionych, które mogą być udostępniane dla podmiotów prawnych w obrębie organizacji.</span><span class="sxs-lookup"><span data-stu-id="9254d-165">Expense categories are derived from shared categories that can be shared across the legal entities in your organization.</span></span> <span data-ttu-id="9254d-166">Kategorie te również mogą być współużytkowane w zarządzaniu projektami i księgowaniu, w zależności od sposobu zdefiniowania danej organizacji.</span><span class="sxs-lookup"><span data-stu-id="9254d-166">These categories can also be shared in Project management and accounting, depending on the way that your organization is defined.</span></span> <span data-ttu-id="9254d-167">Na podstawie definicji organizacji i wskazówek zespołu implementacji określ, czy kategorie używane w zarządzaniu wydatkami będą używane tylko w zarządzaniu wydatkami lub czy powinny być udostępnione między zarządzaniem projektem a księgowością i zarządzaniem wydatkami.</span><span class="sxs-lookup"><span data-stu-id="9254d-167">Based on the definition of your organization and guidance from the implementation team, determine whether the categories that are used in Expense management will be used only in Expense management, or whether they should be shared between Project management and accounting and Expense management.</span></span> <span data-ttu-id="9254d-168">Pamiętaj, że te kategorie mogą być współużytkowane między projektami i wydatkami lub projektami i produkcją, ale nie między wydatkami i produkcją.</span><span class="sxs-lookup"><span data-stu-id="9254d-168">Note that these categories can be shared between Project and Expense or Project and Production, but not between Expense and Production.</span></span> <span data-ttu-id="9254d-169">Należy wybrać następujące decyzje dla każdej kategorii wydatków.</span><span class="sxs-lookup"><span data-stu-id="9254d-169">You must make the following decisions for each expense category.</span></span>

<span data-ttu-id="9254d-170">**Decyzje:**</span><span class="sxs-lookup"><span data-stu-id="9254d-170">**Decisions:**</span></span>

- <span data-ttu-id="9254d-171">Jaka jest kategoria wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-171">What is the expense category?</span></span> <span data-ttu-id="9254d-172">Przykłady obejmują kategorie dla lotów, hoteli lub przebiegu.</span><span class="sxs-lookup"><span data-stu-id="9254d-172">Examples include categories for flights, hotel, or mileage.</span></span>
- <span data-ttu-id="9254d-173">Czy kategoria wydatków jest również używana w zarządzaniu projektami i księgowaniu?</span><span class="sxs-lookup"><span data-stu-id="9254d-173">Can the expense category also be used in Project management and accounting?</span></span>
- <span data-ttu-id="9254d-174">Jaki jest typ wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-174">What is the expense type?</span></span>
- <span data-ttu-id="9254d-175">Jaka jest domyśla metoda płatności dla kategorii wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-175">What is the default payment method for the expense category?</span></span>
- <span data-ttu-id="9254d-176">Czy wydatki w kategorii wydatków muszą być wyszczególnione?</span><span class="sxs-lookup"><span data-stu-id="9254d-176">Do expenses in the expense category have to be itemized?</span></span>
- <span data-ttu-id="9254d-177">Jaka jest główne konto domyślna dla kategorii wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-177">What is the main default account for the expense category?</span></span>
- <span data-ttu-id="9254d-178">Jaka jest domyślna grupa podatków dla towaru w kategorii wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-178">What is the default item sales tax group for the expense category?</span></span>
- <span data-ttu-id="9254d-179">Czy dozwolone są dodatkowe metody płatności dla kategorii wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-179">Are additional payment methods allowed for the expense category?</span></span> <span data-ttu-id="9254d-180">Jeżeli dozwolone są dodatkowe metody płatności, jakie są?</span><span class="sxs-lookup"><span data-stu-id="9254d-180">If additional payment methods are allowed, what are they?</span></span>
- <span data-ttu-id="9254d-181">Czy istnieją podkategorie w ramach tej kategorii wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-181">Are there subcategories in this expense category?</span></span> <span data-ttu-id="9254d-182">Jeżeli istnieją podkategorie, należy także pojąć następujące decyzje:</span><span class="sxs-lookup"><span data-stu-id="9254d-182">If there are subcategories, you must also make the following decisions:</span></span>

    - <span data-ttu-id="9254d-183">Czy jakakolwiek podkategorie są wykluczone ze zwrotu podatku?</span><span class="sxs-lookup"><span data-stu-id="9254d-183">Are any of the subcategories excluded from tax recovery?</span></span>
    - <span data-ttu-id="9254d-184">Jaka jest grupa podatków dla towaru dotycząca podkategorii?</span><span class="sxs-lookup"><span data-stu-id="9254d-184">What is the item sales tax group of the subcategories?</span></span>

<span data-ttu-id="9254d-185">Jeśli kategoria wydatków jest również używana w zarządzaniu projektami i ich księgowaniu, odpowiedz na następujące pytania.</span><span class="sxs-lookup"><span data-stu-id="9254d-185">If the expense category is also used in Project management and accounting, answer the remaining questions.</span></span> <span data-ttu-id="9254d-186">W przeciwnym wypadku należy przejść do następujące sekcji.</span><span class="sxs-lookup"><span data-stu-id="9254d-186">Otherwise, move on to the next section.</span></span>

- <span data-ttu-id="9254d-187">Jakie konta kosztów będą używane dla następujących wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-187">Which cost accounts will be used for the following expenses?</span></span>

    - <span data-ttu-id="9254d-188">Koszt</span><span class="sxs-lookup"><span data-stu-id="9254d-188">Cost</span></span>
    - <span data-ttu-id="9254d-189">Alokacja listy płac</span><span class="sxs-lookup"><span data-stu-id="9254d-189">Payroll allocation</span></span>
    - <span data-ttu-id="9254d-190">PWT — Wartość kosztu</span><span class="sxs-lookup"><span data-stu-id="9254d-190">WIP-cost value</span></span>
    - <span data-ttu-id="9254d-191">Element kosztu</span><span class="sxs-lookup"><span data-stu-id="9254d-191">Cost-item</span></span>
    - <span data-ttu-id="9254d-192">PWT — Wartość kosztu — Pozycja</span><span class="sxs-lookup"><span data-stu-id="9254d-192">WIP-cost value-item</span></span>
    - <span data-ttu-id="9254d-193">Naliczona strata</span><span class="sxs-lookup"><span data-stu-id="9254d-193">Accrued loss</span></span>
    - <span data-ttu-id="9254d-194">PWT — Naliczona strata</span><span class="sxs-lookup"><span data-stu-id="9254d-194">WIP-accrued loss</span></span>

- <span data-ttu-id="9254d-195">Jakie konta przychodów będą używane dla następujących elementów?</span><span class="sxs-lookup"><span data-stu-id="9254d-195">Which revenue accounts will be used for the following?</span></span>

    - <span data-ttu-id="9254d-196">Zafakturowany przychód</span><span class="sxs-lookup"><span data-stu-id="9254d-196">Invoiced revenue</span></span>
    - <span data-ttu-id="9254d-197">Naliczony przychód — Wartość sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9254d-197">Accrued revenue-sales value</span></span>
    - <span data-ttu-id="9254d-198">PWT — Wartość sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9254d-198">WIP-sales value</span></span>
    - <span data-ttu-id="9254d-199">Naliczony przychód — Produkcja</span><span class="sxs-lookup"><span data-stu-id="9254d-199">Accrued revenue-production</span></span>
    - <span data-ttu-id="9254d-200">PWT — produkcja</span><span class="sxs-lookup"><span data-stu-id="9254d-200">WIP-production</span></span>
    - <span data-ttu-id="9254d-201">Naliczony przychód — Zysk</span><span class="sxs-lookup"><span data-stu-id="9254d-201">Accrued revenue-profit</span></span>
    - <span data-ttu-id="9254d-202">PWT — zysk</span><span class="sxs-lookup"><span data-stu-id="9254d-202">WIP-profit</span></span>
    - <span data-ttu-id="9254d-203">Naliczony przychód — Subskrypcja</span><span class="sxs-lookup"><span data-stu-id="9254d-203">Accrued revenue-subscription</span></span>
    - <span data-ttu-id="9254d-204">PWT — subskrypcja</span><span class="sxs-lookup"><span data-stu-id="9254d-204">WIP-subscription</span></span>

### <a name="taxes"></a><span data-ttu-id="9254d-205">Podatki</span><span class="sxs-lookup"><span data-stu-id="9254d-205">Taxes</span></span>

<span data-ttu-id="9254d-206">W przypadku podatków związanych z podatkami trzeba określić, co jest uwzględnione lub dozwolone w raportach wydatków.</span><span class="sxs-lookup"><span data-stu-id="9254d-206">For expense-related taxes, you must determine what is included or enabled on expense reports.</span></span>

<span data-ttu-id="9254d-207">**Decyzje:**</span><span class="sxs-lookup"><span data-stu-id="9254d-207">**Decisions:**</span></span>

- <span data-ttu-id="9254d-208">Czy podatek jest uwzględniony w kwotach wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-208">Is sales tax included in the expense amounts?</span></span>
- <span data-ttu-id="9254d-209">Czy zwrot z podatku powinien być dostępny dla wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-209">Should tax recovery be enabled on expenses?</span></span>

    > [!NOTE]
    > <span data-ttu-id="9254d-210">Gdy planowano księgę główną, jeżeli zdecydowano o zastosowaniu amerykańskiego podatku i przepisów podatkowych, nie można włączyć zwrotu podatku dotyczącego wydatków.</span><span class="sxs-lookup"><span data-stu-id="9254d-210">When you were planning the general ledger, if you decided to apply U.S. sales tax and use tax rules, you can’t enable tax recovery on expenses.</span></span> <span data-ttu-id="9254d-211">(Aby zastosować amerykański podatek i zastosować przepisów podatkowych, ustaw opcję **Zastosuj zasady opodatkowania dla podatku** na **Tak**.)</span><span class="sxs-lookup"><span data-stu-id="9254d-211">(To apply U.S. sales tax and use tax rules, set the **Apply sales tax taxations rules** option to **Yes**.)</span></span>

## <a name="policies"></a><span data-ttu-id="9254d-212">Zasady</span><span class="sxs-lookup"><span data-stu-id="9254d-212">Policies</span></span>

<span data-ttu-id="9254d-213">Tworząc zasady raportu wydatków można ułatwić organizacji oszczędność czasu i pieniędzy, gdy pracownicy ponoszą koszty w jej imieniu.</span><span class="sxs-lookup"><span data-stu-id="9254d-213">By creating expense report policies, you can help your organization save time and money when employees incur expenses on its behalf.</span></span> <span data-ttu-id="9254d-214">Zasady gwarantują, że pracownicy mieszczą się w budżecie, podają wszystkie wymagane informacje i wydają pieniądze tylko wtedy, gdy jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="9254d-214">Policies help guarantee that employees stay in budget, provide all required information, and spend money only as they require it.</span></span> <span data-ttu-id="9254d-215">Należy wybrać następujące decyzje dla każdej zasady raportu wydatków i każdej zasady zatwierdzenia raportu wydatków.</span><span class="sxs-lookup"><span data-stu-id="9254d-215">You must make the following decisions for each expense report policy and each expense report approval policy that you create.</span></span>

<span data-ttu-id="9254d-216">**Decyzje:**</span><span class="sxs-lookup"><span data-stu-id="9254d-216">**Decisions:**</span></span>

- <span data-ttu-id="9254d-217">Jak nazywa się zasada?</span><span class="sxs-lookup"><span data-stu-id="9254d-217">What is the name of the policy?</span></span>
- <span data-ttu-id="9254d-218">Do czego ma służyć zasada wydatków?</span><span class="sxs-lookup"><span data-stu-id="9254d-218">What is the expense policy for?</span></span>
- <span data-ttu-id="9254d-219">Jeśli wcześniej zdecydowano o włączeniu wydatków międzyfirmowych, do jakich firm w organizacji odnosi się zasada?</span><span class="sxs-lookup"><span data-stu-id="9254d-219">If you previously decided to enable intercompany expenses, which companies in your organization will this policy apply to?</span></span>
- <span data-ttu-id="9254d-220">Kiedy zasad zaczyna obowiązywać?</span><span class="sxs-lookup"><span data-stu-id="9254d-220">When does the policy become effective?</span></span>
- <span data-ttu-id="9254d-221">Kiedy zasad wygasa?</span><span class="sxs-lookup"><span data-stu-id="9254d-221">When does the policy expire?</span></span>
- <span data-ttu-id="9254d-222">Jaka jest reguła?</span><span class="sxs-lookup"><span data-stu-id="9254d-222">What is the policy rule?</span></span>
- <span data-ttu-id="9254d-223">Jaki jest wynik reguły?</span><span class="sxs-lookup"><span data-stu-id="9254d-223">What is the outcome of the policy rule?</span></span>

