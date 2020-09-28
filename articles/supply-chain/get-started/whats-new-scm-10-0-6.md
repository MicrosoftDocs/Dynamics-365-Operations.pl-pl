---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.6 (listopad 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
manager: tfehr
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 9ee25036488d2f7f24c1691d36239f3f34caf0cb
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802926"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a><span data-ttu-id="ccacc-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.6 (listopad 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="ccacc-103">What's new or changed in Dynamics 365 Supply Chain Management 10.0.6 (November 2019)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccacc-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span><span class="sxs-lookup"><span data-stu-id="ccacc-104">This topic describes features that are either new or changed in Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span></span> <span data-ttu-id="ccacc-105">Ta wersja ma numer kompilacji 10.0.234.</span><span class="sxs-lookup"><span data-stu-id="ccacc-105">This version has a build number of 10.0.234.</span></span> <span data-ttu-id="ccacc-106">W czasie, gdy ogólna Data dostępności jest w listopadzie, nowe funkcje są dostępne do wczesnego wydania w październiku.</span><span class="sxs-lookup"><span data-stu-id="ccacc-106">While the general availability date is in November, the new features are available for early release in October.</span></span> <span data-ttu-id="ccacc-107">Aby uzyskać więcej informacji o 10.0.6, zobacz [Dodatkowe zasoby](whats-new-scm-10-0-6.md#additional-resources).</span><span class="sxs-lookup"><span data-stu-id="ccacc-107">For more information about version 10.0.6, see [Additional resources](whats-new-scm-10-0-6.md#additional-resources).</span></span>

## <a name="product-configuration-models-v2-data-entity"></a><span data-ttu-id="ccacc-108">Jednostka danych (wersja 2) modeli konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="ccacc-108">Product configuration models V2 data entity</span></span>

<span data-ttu-id="ccacc-109">Zostanie wydana druga wersja jednostki danych „modele konfiguracji produktu” (zwanej „modelami konfiguracji produktów wer. 2”).</span><span class="sxs-lookup"><span data-stu-id="ccacc-109">A second version for the "product configuration models" data entity is released (called "products configuration models V2").</span></span> <span data-ttu-id="ccacc-110">Szablon domyślny „418 — modele konfiguracji produktu” również musi być tak, aby korzystał z nowej jednostki danych „modele konfiguracji produktu wer. 2” w szablonach struktury importu/eksportu.</span><span class="sxs-lookup"><span data-stu-id="ccacc-110">The default template "418-product configuration models" is also needs to be so that it uses the new "product configuration models V2" data entity in the import/export framework templates.</span></span> <span data-ttu-id="ccacc-111">Szablon nie zostanie zaktualizowany automatycznie, dzięki czemu będzie konieczne ręczne załadowanie szablonu z poziomu domyślnego.</span><span class="sxs-lookup"><span data-stu-id="ccacc-111">The template will not be auto-updated so that you will have to load the template from the default manually.</span></span> <span data-ttu-id="ccacc-112">Jednostka wer. 2 eksportuje jeden wiersz jako oddzielny plik w załączniku zamiast w wierszu, rozwiązując ograniczenia rozmiaru jednostki wer.1.</span><span class="sxs-lookup"><span data-stu-id="ccacc-112">The V2 entity exports one row as separate file in an attachment instead of inline, solving the size limitations of the V1 entity.</span></span> 
 
<span data-ttu-id="ccacc-113">Co należy zrobić, aby wykonać tę zmianę?</span><span class="sxs-lookup"><span data-stu-id="ccacc-113">What do you need to do to take this change?</span></span>
-    <span data-ttu-id="ccacc-114">Ponieważ jednostka wer. 1 jest przestarzała, należy zacząć przeprowadzać migrację z wer. 1 na wer. 2.</span><span class="sxs-lookup"><span data-stu-id="ccacc-114">As the V1 entity has been deprecated, you should start migrating from V1 to V2.</span></span> <span data-ttu-id="ccacc-115">W przypadku korzystania z szablonu „418 — modele konfiguracji produktów” można kliknąć przycisk „Załaduj szablony domyślne” i ponownie załadować szablon „418 — modele konfiguracji produktów”</span><span class="sxs-lookup"><span data-stu-id="ccacc-115">If you are using the  "418-product configuration models" template, you can click on "load default templates" button and reload the template "418 – product configuration models"</span></span>
-    <span data-ttu-id="ccacc-116">Jeśli chcesz zachować zgodność z istniejącymi systemami, możesz teraz nadal używać istniejącego szablonu i jednostki (przestarzałe) wer. 1 do czasu przeniesienia integracji do nowego szablonu.</span><span class="sxs-lookup"><span data-stu-id="ccacc-116">If you need to keep compatibility with existing systems, you can for now continue using the existing template and the (deprecated) V1 entity until you move your integrations to the new template.</span></span> 

## <a name="feature-management-enhancements"></a><span data-ttu-id="ccacc-117">Poprawki zarządzania funkcjami</span><span class="sxs-lookup"><span data-stu-id="ccacc-117">Feature management enhancements</span></span>
<span data-ttu-id="ccacc-118">Zarządzanie funkcjami pozwala teraz domyślnie włączyć wszystkie nowe funkcje, wymagać potwierdzenia włączenia funkcji i włączyć wszystkie funkcje, które nie zostały jeszcze włączone.</span><span class="sxs-lookup"><span data-stu-id="ccacc-118">Feature management now allows you to enable all new features by default, require confirmation to enable a feature, and enable all features that have not already been enabled.</span></span> 


## <a name="purchase-agreement-responsible-party"></a><span data-ttu-id="ccacc-119">Strona odpowiedzialna za umowę zakupu</span><span class="sxs-lookup"><span data-stu-id="ccacc-119">Purchase agreement responsible party</span></span>
<span data-ttu-id="ccacc-120">Obecnie istnieje możliwość zdefiniowania podstawowych i drugorzędnych jednostek odpowiedzialnych w formularzu klasyfikacji umowy zakupu oraz w wynikowych umowach zakupu.</span><span class="sxs-lookup"><span data-stu-id="ccacc-120">You now have the ability to define primary and secondary responsible parties on the Purchase agreement classification form and resulting Purchase agreements.</span></span>  <span data-ttu-id="ccacc-121">Dzięki temu użytkownicy mogą uzyskać dostęp do osób, którym przewidzisz umowy.</span><span class="sxs-lookup"><span data-stu-id="ccacc-121">This provides the user access to who oversees the agreements.</span></span>

## <a name="rfq-link-on-the-purchase-order-line"></a><span data-ttu-id="ccacc-122">Łącze ZO w wierszu zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="ccacc-122">RFQ link on the Purchase order line</span></span>
<span data-ttu-id="ccacc-123">Można dodać łącze odwołania z wierszy zamówienia zakupu z powrotem do odpowiednich wierszy ZO, z których pochodzą, umożliwiając użytkownikowi łatwe udostępnienie zapytanie ofertowe dokumentu pomocniczego.</span><span class="sxs-lookup"><span data-stu-id="ccacc-123">You can add a reference link from the Purchase order lines back to the corresponding RFQ lines they originated from, allowing the user to easily be provided with the supporting request for quotation document.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ccacc-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ccacc-124">Additional resources</span></span>

### <a name="bug-fixes"></a><span data-ttu-id="ccacc-125">Poprawki błędów</span><span class="sxs-lookup"><span data-stu-id="ccacc-125">Bug fixes</span></span>
<span data-ttu-id="ccacc-126">Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.6, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span><span class="sxs-lookup"><span data-stu-id="ccacc-126">For information about the bug fixes included in each of the updates that are part of 10.0.6, sign in to Lifecycle Services (LCS) and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span></span>

### <a name="platform-update-30"></a><span data-ttu-id="ccacc-127">Aktualizacja platformy Update 30</span><span class="sxs-lookup"><span data-stu-id="ccacc-127">Platform update 30</span></span>
<span data-ttu-id="ccacc-128">Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.6 zawiera aktualizację Platform update 30.</span><span class="sxs-lookup"><span data-stu-id="ccacc-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 includes Platform update 30.</span></span> <span data-ttu-id="ccacc-129">Aby dowiedzieć się więcej o aktualizacji Platform update 30, zobacz [Nowości lub zmiany w aktualizacji Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span><span class="sxs-lookup"><span data-stu-id="ccacc-129">To learn more about Platform update 30, see [What's new or changed in Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span></span>

### <a name="dynamics-365-2019-release-wave-2-plan"></a><span data-ttu-id="ccacc-130">Dynamics 365: plan wydania 2019 aktualizacja 2</span><span class="sxs-lookup"><span data-stu-id="ccacc-130">Dynamics 365: 2019 release wave 2 plan</span></span>
<span data-ttu-id="ccacc-131">Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?</span><span class="sxs-lookup"><span data-stu-id="ccacc-131">Wondering about upcoming and recently released capabilities in any of our business apps or platform?</span></span>

<span data-ttu-id="ccacc-132">Zajrzyj do [Dynamics 365: plan wydania 2019 aktualizacja 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span><span class="sxs-lookup"><span data-stu-id="ccacc-132">Check out the [Dynamics 365: 2019 release wave 2 plan](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span></span> <span data-ttu-id="ccacc-133">Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.</span><span class="sxs-lookup"><span data-stu-id="ccacc-133">We've captured all the details, end to end, top to bottom, in a single document that you can use for planning.</span></span>

### <a name="removed-and-deprecated-supply-chain-management-features"></a><span data-ttu-id="ccacc-134">Usunięte i przestarzałe funkcje Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ccacc-134">Removed and deprecated Supply Chain Management features</span></span>

<span data-ttu-id="ccacc-135">W temacie [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ccacc-135">The [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic describes features that have been or are scheduled to be removed or deprecated for Supply Chain Management.</span></span>

- <span data-ttu-id="ccacc-136">*Usunięta* funkcja nie jest już dostępna w produkcie.</span><span class="sxs-lookup"><span data-stu-id="ccacc-136">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="ccacc-137">*Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="ccacc-137">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="ccacc-138">Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.</span><span class="sxs-lookup"><span data-stu-id="ccacc-138">Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic 12 months prior to the removal.</span></span>

<span data-ttu-id="ccacc-139">W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="ccacc-139">For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months.</span></span> <span data-ttu-id="ccacc-140">Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.</span><span class="sxs-lookup"><span data-stu-id="ccacc-140">Typically, these are functional updates that need to be made to the compiler.</span></span>
