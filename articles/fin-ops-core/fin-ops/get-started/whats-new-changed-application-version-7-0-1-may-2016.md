---
title: Nowości i zmiany w aplikacji Dynamics AX w wersji 7.0.1 (maj 2016)
description: W tym artykule opisano nowe oraz zmienione funkcje dostępne w aplikacji Microsoft Dynamics AX w wersji 7.0.1. Ta wersja została wydana w maju 2016 r. i ma numer kompilacji 7.0.1265.23014.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 7da0eba072aba08b4da655cf680af9282278f34f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564682"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a><span data-ttu-id="d3c6a-104">Nowości i zmiany w aplikacji Dynamics AX w wersji 7.0.1 (maj 2016)</span><span class="sxs-lookup"><span data-stu-id="d3c6a-104">What's new or changed in Dynamics AX application version 7.0.1 (May 2016)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3c6a-105">W tym artykule opisano nowe oraz zmienione funkcje dostępne w aplikacji Microsoft Dynamics AX w wersji 7.0.1.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-105">This article describes features that are either new or changed in Microsoft Dynamics AX application version 7.0.1.</span></span> <span data-ttu-id="d3c6a-106">Ta wersja została wydana w maju 2016 r. i ma numer kompilacji 7.0.1265.23014.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-106">This version was released in May 2016 and has a build number of 7.0.1265.23014.</span></span>

## <a name="electronic-reporting-er"></a><span data-ttu-id="d3c6a-107">Raportowanie elektroniczne (ER)</span><span class="sxs-lookup"><span data-stu-id="d3c6a-107">Electronic reporting (ER)</span></span>

| <span data-ttu-id="d3c6a-108">Co można zrobić?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-108">What can you do?</span></span> | <span data-ttu-id="d3c6a-109">Dlaczego to jest ważne?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-109">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="d3c6a-110">Konfigurowanie okna dialogowego czasu wykonywania umożliwiającego projektowanie raportów modułu Raportowanie elektroniczne (ER), dzięki czemu użytkownicy mogą wybrać żądane wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-110">Configure a run-time dialog box for designing Electronic reporting (ER) reports, so that users can select the financial dimensions that they want.</span></span> | <span data-ttu-id="d3c6a-111">W czasie wykonywania w oknie dialogowym generowania raportu aplikacji ER użytkownicy mogą wybrać wiele wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-111">At run time, in the dialog box for running an ER report, users can select multiple financial dimensions.</span></span> <span data-ttu-id="d3c6a-112">Szczegóły wybranych wymiarów finansowych będą wyświetlane w generowanym dokumencie elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-112">The details of the selected financial dimensions will be displayed in the electronic document that is generated.</span></span> |
| <span data-ttu-id="d3c6a-113">Konfigurowanie dostępu do wielu wymiarów finansowych podczas projektowania raportu ER poprzez jedno mapowanie do żądanego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-113">Configure access to multiple financial dimensions during the design of an ER report, via a single mapping to the desired data source.</span></span> | <span data-ttu-id="d3c6a-114">Ta sama konfiguracja raportu ER może służyć do generowania dokumentów elektronicznych pokazujących dane transakcyjne wraz ze szczegółami wymiarów finansowych, bez względu na liczbę wymiarów finansowych wybranych przez użytkownika lub skonfigurowanych dla bieżącej firmy lub wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-114">The same ER report configuration can be used to generate electronic documents that present transactional data together with details of financial dimensions, regardless of the number of financial dimensions that are either selected by the user or configured for the current legal entity or instance.</span></span> |
| <span data-ttu-id="d3c6a-115">Konfigurowanie raportu ER w celu wprowadzania danych w dynamicznie generowanych kolumnach dokumentu elektronicznego, który jest tworzony w formacie arkusza OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-115">Configure an ER report to enter data in dynamically generated columns of an electronic document that is created in OPENXML worksheet format.</span></span> | <span data-ttu-id="d3c6a-116">Raport ER może wprowadzać dane do generowanego arkusza OPENXML poprzez poziome replikowanie kolumn.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-116">An ER report can enter data in an OPENXML worksheet that is generated, via horizontally replicating columns.</span></span> <span data-ttu-id="d3c6a-117">W związku z tym tej samej konfiguracji raportu ER można użyć również do generowania dokumentów elektronicznych, które mają inną liczbę dynamicznie generowanych kolumn.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-117">Therefore, the same ER report configuration can be reused to generate electronic documents that have a different number of dynamically generated columns.</span></span> |
| <span data-ttu-id="d3c6a-118">Konfigurowanie miejsc docelowych aplikacji ER, tak aby dane wyjściowe w określonym formacie były kierowane do określonego miejsca docelowego: pliku, wiadomości e-mail lub archiwum (folderu programu Microsoft SharePoint lub magazynu w usłudze Microsoft Azure).</span><span class="sxs-lookup"><span data-stu-id="d3c6a-118">Configure ER destinations so that the output result of a format is directed to specific destination: file, email, or archive (Microsoft SharePoint folder or Microsoft Azure Storage).</span></span> | <span data-ttu-id="d3c6a-119">Wcześniej podczas sesji konfiguracji ER pojawiało się okno komunikatu z monitem do użytkownika, aby zapisał lub otworzył plik.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-119">Previously, when you ran an ER configuration, a message box appeared that required user action to save or open a file.</span></span> <span data-ttu-id="d3c6a-120">Teraz można wstępnie skonfigurować miejsce docelowe osobno dla każdej konfiguracji formatu i każdego składnika wyjściowego (folderu lub pliku).</span><span class="sxs-lookup"><span data-stu-id="d3c6a-120">You can now pre-configure a destination for each format configuration and for each output component (a folder or a file) separately.</span></span> <span data-ttu-id="d3c6a-121">Użytkownicy mający odpowiednie prawa dostępu mogą także modyfikować ustawienia miejsca docelowego w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-121">Users who have appropriate access rights can also modify destination settings at run time.</span></span> |

## <a name="pos--microsoft-dynamics-ax-retail"></a><span data-ttu-id="d3c6a-122">POS — moduł sprzedaży detalicznej w systemie Microsoft Dynamics AX</span><span class="sxs-lookup"><span data-stu-id="d3c6a-122">POS – Microsoft Dynamics AX Retail</span></span>

| <span data-ttu-id="d3c6a-123">Co można zrobić?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-123">What can you do?</span></span> | <span data-ttu-id="d3c6a-124">Dlaczego to jest ważne?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-124">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="d3c6a-125">Używanie przeglądarki internetowej Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-125">Use the Google Chrome browser.</span></span> | <span data-ttu-id="d3c6a-126">Sprzedawcy detaliczni mogą teraz uruchamiać aplikację Cloud POS w przeglądarce Chrome oraz korzystać ze wszystkich funkcji, które można znaleźć w aplikacji Cloud POS w wersji dla przeglądarek Microsoft Edge i Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-126">Retailers can now start Cloud POS from the Chrome browser, and can experience all the functionality that is available in the Microsoft Edge and Internet Explorer version of Cloud POS.</span></span> |

## <a name="financial-reporting"></a><span data-ttu-id="d3c6a-127">Raporty finansowe</span><span class="sxs-lookup"><span data-stu-id="d3c6a-127">Financial reporting</span></span>

| <span data-ttu-id="d3c6a-128">Co można zrobić?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-128">What can you do?</span></span> | <span data-ttu-id="d3c6a-129">Dlaczego to jest ważne?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-129">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="d3c6a-130">Odbudowa składniki danych aplikacji Raportowanie finansowe.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-130">Rebuild the Financial reporting data mart.</span></span> | <span data-ttu-id="d3c6a-131">Po przeniesieniu baz danych systemu Dynamics AX między środowiskami lub wprowadzeniu innych inwazyjnych zmian w środowisku może być konieczne odbudowanie bazy danych składnika Raporty finansowe.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-131">When you move Dynamics AX databases between environments or make other invasive changes to the environment, the Financial reporting database might have to be rebuilt.</span></span> <span data-ttu-id="d3c6a-132">Teraz jest dostępny skrypt narzędzia Windows PowerShell, który umożliwia automatyczne odbudowanie bazy danych.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-132">A Windows PowerShell script is now provided to rebuild the database for you.</span></span> |
| <span data-ttu-id="d3c6a-133">Nie można już wybierać nieprawidłowych opcji projektanta raportów.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-133">You can no longer select report designer options that aren't valid.</span></span> | <span data-ttu-id="d3c6a-134">Niektóre opcje projektanta raportów, które były używane w lokalnych wersjach programu Management Reporter, nie mają zastosowania w tej wersji systemu Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-134">Several report designer options that were used in the in-market versions of Management reporter don't apply to this version of Dynamics AX.</span></span> <span data-ttu-id="d3c6a-135">Te opcje dotyczyły projektów, danych wyjściowych i połączeń raportów finansowych.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-135">These options were related to financial report design, output, and linking.</span></span> <span data-ttu-id="d3c6a-136">Opcje zostały usunięte z projektanta raportów finansowych, aby zapobiec popełnianiu błędów przez użytkowników.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-136">These options have been removed from the financial report designer to prevent user errors.</span></span> |

## <a name="financial-management"></a><span data-ttu-id="d3c6a-137">Zarządzanie finansami</span><span class="sxs-lookup"><span data-stu-id="d3c6a-137">Financial management</span></span>

| <span data-ttu-id="d3c6a-138">Co można zrobić?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-138">What can you do?</span></span> | <span data-ttu-id="d3c6a-139">Dlaczego to jest ważne?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-139">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="d3c6a-140">Generowanie plików płatności dodatnich dla płatności w ramach rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-140">Generate positive pay files for accounts payable payments.</span></span> | <span data-ttu-id="d3c6a-141">Można generować pliki płatności dodatnich, aby ułatwić bankom walkę z oszustwami dotyczącymi czeków.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-141">Positive pay files can be generated to help prevent check fraud.</span></span> |

## <a name="warehouse-and-production"></a><span data-ttu-id="d3c6a-142">Magazyn i produkcja</span><span class="sxs-lookup"><span data-stu-id="d3c6a-142">Warehouse and production</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d3c6a-143">Co można zrobić?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-143">What can you do?</span></span></th>
<th><span data-ttu-id="d3c6a-144">Dlaczego to jest ważne?</span><span class="sxs-lookup"><span data-stu-id="d3c6a-144">Why is this important?</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d3c6a-145">Definiowanie zasady pracy magazynu, która steruje tworzeniem pracy dla zbioru produktów w określonych lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-145">Define a warehouse work policy that controls the creation of work for a set of products at specific locations.</span></span></td>
<td><span data-ttu-id="d3c6a-146">Procesy magazynowe nie zawsze obejmują pracę.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-146">Warehouse processes don't always include work.</span></span> <span data-ttu-id="d3c6a-147">Korzystając z nowych zasad pracy magazynowej, można zablokować tworzenie pracy pobierania surowców i odkładania wyrobów gotowych dla zbioru produktów w określonych lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-147">By using the new warehouse work policy, you can prevent work from being created for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d3c6a-148">Określanie, że lokalizacja wyjściowa produkcji nie ma być kontrolowana za pomocą numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-148">Specify that a production output location isn't license plate–controlled.</span></span></td>
<td><span data-ttu-id="d3c6a-149">Teraz można określić, że lokalizacja wyjściowa produktu nie ma być kontrolowana za pomocą numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-149">You can now specify that a product output location isn't license plate–controlled.</span></span> <span data-ttu-id="d3c6a-150">Na przykład ta funkcja jest użyteczna, gdy zlecenie produkcyjne bliżej dostawcy zgłasza towary jako gotowe bezpośrednio do lokalizacji, która działa jako lokalizacja wejściowa produkcji dla zlecenia produkcyjnego bliżej odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-150">For example, this feature is useful when an upstream production order reports items as finished directly to a location that acts as production input location for a downstream production order.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d3c6a-151">Obsługa BOM zawierających towary o różnych wymiarach produktów w tym samym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-151">Support BOMs that include items with different product dimensions of the same item.</span></span></td>
<td><span data-ttu-id="d3c6a-152">Podczas używania jednego lub wielu wymiarów produktu w produkcji można mieć sytuacje, gdy chcesz wytworzyć towar oparty na innym wariancie tego samego towaru.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-152">When using one or multiple of the product dimensions in production, you can have situations where you would like to produce an item, based on a different variant of the same item.</span></span> <span data-ttu-id="d3c6a-153">Aby uzyskać więcej informacji, zobacz <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">ten blog</a>.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-153">For more information, see <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">this blog</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d3c6a-154">Zlecenia produkcyjne ze strukturami rekurencyjnymi na pierwszym poziomie ich BOM są wykluczone z obliczeń poziomu BOM w planowania zasobów materiałowych.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-154">Production orders with circular structures at the first level of their BOMs are excluded from BOM level calculation for material resource planning.</span></span></td>
<td><span data-ttu-id="d3c6a-155">Nie jest możliwe przypisanie poprawnych poziomów BOM do wariantów produktu dla zleceń produkcyjnych, które powodują cykliczność w hierarchii BOM.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-155">It is not possible to assign correct BOM levels to product variants for production orders that cause circularity in the BOM hierarchy.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d3c6a-156">Obliczanie oddzielnych poziomów BOM dla planowania zasobów materiałowych i kosztów:</span><span class="sxs-lookup"><span data-stu-id="d3c6a-156">Calculate separate BOM levels for material resource planning and cost calculation:</span></span>
<ul>
<li><span data-ttu-id="d3c6a-157">W planowania zasobów materiałowych poziomy BOM są obliczane w nowej tabeli <strong>ReqItemLevel</strong>.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-157">For material resource planning, BOM levels are calculated in the new <strong>ReqItemLevel</strong> table.</span></span> <span data-ttu-id="d3c6a-158">Zakończone zlecenia produkcyjne są ignorowane w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-158">Ended production orders are ignored in the calculation.</span></span></li>
<li><span data-ttu-id="d3c6a-159">W przypadku kosztów produkcji poziomy BOM są obliczane w tabeli <strong>InventTable</strong>.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-159">For production cost calculation, BOM levels are calculated in the <strong>InventTable</strong>.</span></span> <span data-ttu-id="d3c6a-160">Zakończone zlecenia produkcyjne są uwzględniane w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-160">Ended production orders are included in the calculation.</span></span></li>
</ul>
</td>
<td>
<ul>
<li><span data-ttu-id="d3c6a-161">Podczas planowania zasobów materiałowych, na przykład tworzenia i rozwijania planu w ramach planowania głównego, konieczność ponownego obliczania istnieje tylko dla poziomów BOM używanych do planowania zasobów materiałowych.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-161">When running material resource planning, for example, master planning plan scheduling and explosion, only BOM levels used for material resource planning need to be recalculated.</span></span> <span data-ttu-id="d3c6a-162">Innymi słowy nie trzeba obliczać poziomów BOM używanych do obliczania wyceny produkcji.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-162">In other words, there is no need to calculate BOM levels used for production costing calculation.</span></span></li>
<li><span data-ttu-id="d3c6a-163">Podczas operacji wyceny, na przykład w celu zamknięcia magazynu, trzeba ponownie obliczać tylko poziomy BOM używane do obliczania wyceny produkcji.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-163">When running costing operations, for example, inventory closing, only BOM levels used for production costing calculation need to be recalculated.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="d3c6a-164">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d3c6a-164">Additional resources</span></span>

[<span data-ttu-id="d3c6a-165">Nowości i zmiany w rozwiązaniu Finance and Operations — strona główna</span><span class="sxs-lookup"><span data-stu-id="d3c6a-165">What's new or changed in Finance and Operations home page</span></span>](whats-new-changed.md)

[<span data-ttu-id="d3c6a-166">Nowe lub zaktualizowane przewodniki po zadaniach (maj 2016 r.)</span><span class="sxs-lookup"><span data-stu-id="d3c6a-166">New or updated task guides (May 2016)</span></span>](new-updated-task-guides-available-may-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]