---
title: Regulatory Configuration Service (RCS) – deprekacja pamięci w Lifecycle Services (LCS)
description: Ten temat zawiera informacje o wycofaniu z użytku magazynu Microsoft Dynamics Lifecycle Services (LCS), które jest planowane w ramach wdrażania globalnego repozytorium Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 05/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: abaeb34db1d209fa8e5cc83a98c333f42e91f2d2
ms.sourcegitcommit: 7cda434becd198c1cd405e001289777ae7a24fe1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6127926"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a><span data-ttu-id="a4adc-103">Regulatory Configuration Service (RCS) — deprekacja pamięci w Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="a4adc-103">Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a4adc-104">Zrezygnowano z używania Microsoft Dynamics Lifecycle Services (LCS) jako repozytorium do przechowywania konfiguracji raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="a4adc-104">The use of Microsoft Dynamics Lifecycle Services (LCS) as a storage repository for Electronic reporting (ER) configurations is being deprecated.</span></span> <span data-ttu-id="a4adc-105">To wycofanie wymaga następujących zmian:</span><span class="sxs-lookup"><span data-stu-id="a4adc-105">This deprecation will involve the following changes:</span></span>

- <span data-ttu-id="a4adc-106">Wyprodukowane przez firmę Microsoft konfiguracje używane w Microsoft Dynamics 365 nie będą już publikowane w bibliotece udostępnionych zasobów w LCS.</span><span class="sxs-lookup"><span data-stu-id="a4adc-106">Microsoft-produced configurations that are used in Microsoft Dynamics 365 applications will no longer be published to the Shared asset library in LCS.</span></span> <span data-ttu-id="a4adc-107">Zamiast tego, będą one publikowane tylko poprzez globalne repozytorium RCS.</span><span class="sxs-lookup"><span data-stu-id="a4adc-107">Instead, they will be published only through the RCS Global repository.</span></span> <span data-ttu-id="a4adc-108">Jednakże, konfiguracje dla Dynamics AX 2012 będą nadal publikowane do biblioteki aktywów wspólnych w LCS aż do zakończenia cyklu wsparcia dla AX 2012.</span><span class="sxs-lookup"><span data-stu-id="a4adc-108">However, configurations for Dynamics AX 2012 will continue to be published to the Shared asset library in LCS until the support lifecycle for AX 2012 ends.</span></span>
- <span data-ttu-id="a4adc-109">Funkcja, która umożliwia przekazywanie konfiguracji do biblioteki aktywówprojektu w LCS z aplikacji Finance and Operations oraz z usługi RCS, zostanie dezaktywowana.</span><span class="sxs-lookup"><span data-stu-id="a4adc-109">The functionality that lets you upload configurations to the Project asset library in LCS from Finance and Operations apps, and from RCS, will be inactivated.</span></span> <span data-ttu-id="a4adc-110">Jednakże, nadal będziesz mógł używać przeglądarki w LCS do wgrywania konfiguracji do biblioteki zasobów projektu.</span><span class="sxs-lookup"><span data-stu-id="a4adc-110">However, you will still be able to use the browser in LCS to upload configurations to the Project asset library.</span></span> <span data-ttu-id="a4adc-111">W związku z tym, nadal będziesz mógł dodawać konfiguracje do LCS, aby mogły być one zawarte w pakietach rozwiązań.</span><span class="sxs-lookup"><span data-stu-id="a4adc-111">Therefore, you will still be able to add configurations to LCS so that they can be included in solution packages.</span></span>
- <span data-ttu-id="a4adc-112">Import konfiguracji z LCS będzie nadal dostępny i wspierany w aplikacjach Finance and Operations oraz w RCS, przez pewien czas.</span><span class="sxs-lookup"><span data-stu-id="a4adc-112">Import of configurations from LCS will continue to be available and supported in Finance and Operations apps, and in RCS, for some time.</span></span> <span data-ttu-id="a4adc-113">Jednakże, funkcjonalność ta zostanie w końcu wycofana.</span><span class="sxs-lookup"><span data-stu-id="a4adc-113">However, the functionality will eventually be deprecated.</span></span> <span data-ttu-id="a4adc-114">(Dokładna data wycofania zostanie ogłoszona później).</span><span class="sxs-lookup"><span data-stu-id="a4adc-114">(The exact deprecation date will be announced later.)</span></span>

## <a name="deprecation-notice"></a><span data-ttu-id="a4adc-115">Powiadomienie o wycofaniu</span><span class="sxs-lookup"><span data-stu-id="a4adc-115">Deprecation notice</span></span>

<span data-ttu-id="a4adc-116">Informacja o zaprzestaniu korzystania z LCS jako magazynu została podana w [Usunięte lub wycofane funkcje w Dynamics 365 Finance - informacja o wycofaniu LCS](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="a4adc-116">Deprecation of the use of LCS as storage was communicated in [Removed or deprecated features in Dynamics 365 Finance - LCS Deprecation notice](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="a4adc-117">Planowana data wycofania to 1 kwietnia 2022 roku.</span><span class="sxs-lookup"><span data-stu-id="a4adc-117">The planned deprecation date is April 1, 2022.</span></span>

## <a name="key-features"></a><span data-ttu-id="a4adc-118">Najważniejsze funkcje</span><span class="sxs-lookup"><span data-stu-id="a4adc-118">Key features</span></span>

- <span data-ttu-id="a4adc-119">Możesz użyć RCS do tworzenia i edycji konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a4adc-119">You can use RCS to create and edit configurations.</span></span> <span data-ttu-id="a4adc-120">Konfiguracje te można następnie przesłać bezpośrednio z projektanta do podłączonej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4adc-120">You can then push those configurations directly from the designer to a connected application.</span></span> <span data-ttu-id="a4adc-121">Dzięki temu można szybko zmieniać i testować konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="a4adc-121">Therefore, you can quickly change and test your configurations.</span></span>
- <span data-ttu-id="a4adc-122">Globalne repozytorium jest scentralizowanym miejscem przechowywania wszystkich konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="a4adc-122">The Global repository is the centralized storage for all ER configurations.</span></span>

## <a name="guidance-for-one-time-and-ongoing-actions"></a><span data-ttu-id="a4adc-123">Wytyczne dotyczące działań jednorazowych i bieżących</span><span class="sxs-lookup"><span data-stu-id="a4adc-123">Guidance for one-time and ongoing actions</span></span>

<span data-ttu-id="a4adc-124">W tej sekcji opisano zestaw czynności, które należy wykonać jednorazowo.</span><span class="sxs-lookup"><span data-stu-id="a4adc-124">This section describes a set of steps that must be completed one time.</span></span> <span data-ttu-id="a4adc-125">Opisuje również czynności, które muszą być wykonywane na bieżąco po zakończeniu pracy.</span><span class="sxs-lookup"><span data-stu-id="a4adc-125">It also describes steps that must be completed on an ongoing basis afterward.</span></span>

### <a name="one-time-action"></a><span data-ttu-id="a4adc-126">Akcja jednorazowa</span><span class="sxs-lookup"><span data-stu-id="a4adc-126">One-time action</span></span>

<span data-ttu-id="a4adc-127">Zaimportuj wszystkie wymagane konfiguracje z LCS do RCS, a następnie opublikuj je z RCS do globalnego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="a4adc-127">Import all required configurations from LCS to RCS, and then publish them from RCS to the Global repository.</span></span> <span data-ttu-id="a4adc-128">Jeśli używasz bibliotek zasobów specyficznych dla projektu do przechowywania konfiguracji pochodnych w LCS, poniższe kroki muszą być wykonane, gdy LCS jest wciąż dostępny.</span><span class="sxs-lookup"><span data-stu-id="a4adc-128">If you're using project-specific asset libraries to store derived configurations in LCS, the following steps must be completed while LCS is still accessible.</span></span>

1. <span data-ttu-id="a4adc-129">Jeśli instancja RCS nie jest jeszcze dostępna, skonfiguruj ją.</span><span class="sxs-lookup"><span data-stu-id="a4adc-129">If an RCS instance isn't already available, provision one.</span></span> <span data-ttu-id="a4adc-130">Aby uzyskać więcej informacji, zobacz [omówienie RCS](rcs-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a4adc-130">For more information, see [RCS overview](rcs-overview.md).</span></span>
2. <span data-ttu-id="a4adc-131">W udostępnionej instancji RCS, dla każdego projektu LCS w bibliotece aktywów, który zawiera pochodne konfiguracje ER, zarejestruj odpowiednie repozytorium LCS.</span><span class="sxs-lookup"><span data-stu-id="a4adc-131">In the provisioned RCS instance, for every LCS project in the Asset library that includes derived ER configurations, register the appropriate LCS repository.</span></span>
3. <span data-ttu-id="a4adc-132">Zaimportuj konfiguracje ER z repozytoriów LCS do RCS.</span><span class="sxs-lookup"><span data-stu-id="a4adc-132">Import the ER configurations from the LCS repositories to RCS.</span></span> <span data-ttu-id="a4adc-133">Aby uzyskać więcej informacji, zobacz temat [Importowanie konfiguracji z usług LCS](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="a4adc-133">For more information, see [Import configurations from LCS](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).</span></span>
4. <span data-ttu-id="a4adc-134">Jeśli globalne repozytorium nie zostało automatycznie dostarczone, zarejestruj je w RCS.</span><span class="sxs-lookup"><span data-stu-id="a4adc-134">If the Global repository isn't automatically provided, register it in RCS.</span></span>
5. <span data-ttu-id="a4adc-135">Prześlij wszystkie pochodne konfiguracje z bieżącej instancji RCS do globalnego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="a4adc-135">Upload all derived configurations from the current RCS instance to the Global repository.</span></span> <span data-ttu-id="a4adc-136">Użyj **pakietów konfiguracji, które umożliwiają użytkownikowi przekazywanie wszystkich konfiguracji do systemu GR w jednej operacji**, aby pomóc w przekazywaniu.</span><span class="sxs-lookup"><span data-stu-id="a4adc-136">Use the **Configuration packages that allows the user to upload all configurations to GR in one operation** feature to help with the upload.</span></span> <span data-ttu-id="a4adc-137">Aby uzyskać więcej informacji, zobacz [Przesyłanie do globalnego repozytorium RCS](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="a4adc-137">For more information, see [RCS global repo upload](rcs-global-repo-upload.md).</span></span>

### <a name="going-forward"></a><span data-ttu-id="a4adc-138">Przyszłość</span><span class="sxs-lookup"><span data-stu-id="a4adc-138">Going forward</span></span>

<span data-ttu-id="a4adc-139">Użyj projektantów wizualnych w RCS, aby stworzyć wszystkie nowe konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="a4adc-139">Use the visual designers in RCS to create all new configurations.</span></span> <span data-ttu-id="a4adc-140">Następnie prześlij konfiguracje do Globalnego repozytorium w celu przechowywania.</span><span class="sxs-lookup"><span data-stu-id="a4adc-140">Then upload the configurations to the Global repository for storage.</span></span> <span data-ttu-id="a4adc-141">Aby uzyskać więcej informacji, zobacz temat [Tworzenie konfiguracji ER w RCS i przekazywanie do globalnego serwera repo](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="a4adc-141">For more information, see [Create ER configuration in RCS and upload to Global repo](rcs-global-repo-upload.md).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a4adc-142">Często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="a4adc-142">Frequently asked questions</span></span>

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a><span data-ttu-id="a4adc-143">Czy ta zmiana oznacza, że LCS nie może być używany jako centralny magazyn dla konfiguracji?</span><span class="sxs-lookup"><span data-stu-id="a4adc-143">Does this change mean that LCS can't be used as central storage for configurations?</span></span>

<span data-ttu-id="a4adc-144">Tak.</span><span class="sxs-lookup"><span data-stu-id="a4adc-144">Yes.</span></span> <span data-ttu-id="a4adc-145">Funkcja, która umożliwia przekazywanie konfiguracji do biblioteki aktywów projektu w LCS z aplikacji Finance and Operations oraz z usługi RCS, zostanie wycofana.</span><span class="sxs-lookup"><span data-stu-id="a4adc-145">The functionality that lets you upload configurations to the Project asset library in LCS from Finance and Operations apps will be deprecated.</span></span> <span data-ttu-id="a4adc-146">Jednakże, nadal będziesz mógł używać przeglądarki w LCS do wgrywania konfiguracji do biblioteki zasobów projektu.</span><span class="sxs-lookup"><span data-stu-id="a4adc-146">However, you can still use the browser in LCS to upload configurations to the Project asset library as you require.</span></span>

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a><span data-ttu-id="a4adc-147">Myślałem, że RCS to zastępcze repozytorium do importowania globalnych plików szablonów.</span><span class="sxs-lookup"><span data-stu-id="a4adc-147">I thought that RCS was a replacement repository for importing global template files.</span></span> <span data-ttu-id="a4adc-148">Nie sądziłem, że jest on używany do przechowywania konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a4adc-148">I didn't think that it's used to store configurations.</span></span> <span data-ttu-id="a4adc-149">Co tu jest poprawne?</span><span class="sxs-lookup"><span data-stu-id="a4adc-149">Which is correct?</span></span>

<span data-ttu-id="a4adc-150">RCS to usługa projektowa służąca do tworzenia i edycji konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="a4adc-150">RCS is a design service for creating and editing ER configurations.</span></span> <span data-ttu-id="a4adc-151">RCS ma swoje własne repozytorium, które jest znane jako repozytorium globalne.</span><span class="sxs-lookup"><span data-stu-id="a4adc-151">RCS has its own repository that is known as the Global repository.</span></span> <span data-ttu-id="a4adc-152">To repozytorium jest używane do przechowywania konfiguracji, które są tworzone w RCS.</span><span class="sxs-lookup"><span data-stu-id="a4adc-152">This repository is used to store configurations that are created in RCS.</span></span> <span data-ttu-id="a4adc-153">Po zaprzestaniu używania LCS jako magazynu, repozytorium globalne będzie jedynym źródłem dla konfiguracji Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a4adc-153">After the use of LCS as storage is deprecated, the Global repository will be the single source for Microsoft configurations.</span></span> <span data-ttu-id="a4adc-154">Musisz wykonać jednorazową akcję, aby zaimportować wszystkie wymagane konfiguracje z LCS do RCS, a następnie opublikować je z RCS do Globalnego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="a4adc-154">You must complete a one-time action to import all the configurations that you require from LCS to RCS and then publish them from RCS to the Global repository.</span></span>

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a><span data-ttu-id="a4adc-155">Bez LCS, jaki jest sugerowany sposób przechowywania konfiguracji tak, aby konfiguracje „testowe” i „produkcyjne” mogły być łatwo zarządzane i przenoszone?</span><span class="sxs-lookup"><span data-stu-id="a4adc-155">Without LCS, what is the suggested way to store configurations so that "test" and "production" configurations can easily be managed and transferred?</span></span>

<span data-ttu-id="a4adc-156">System RCS używa koncepcji *połączonej aplikacji*.</span><span class="sxs-lookup"><span data-stu-id="a4adc-156">RCS uses the concept of a *connected application*.</span></span> <span data-ttu-id="a4adc-157">Połączona aplikacja tworzy połączenie między RCS i dowolnym wystąpieniem aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a4adc-157">A connected application forms a connection between RCS and any instance of Finance and Operations apps.</span></span> <span data-ttu-id="a4adc-158">Ponieważ za pomocą usługi RCS można edytować konfiguracje, połączona aplikacja może służyć do wypychania konfiguracji bezpośrednio od konstruktora do środowisk aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a4adc-158">Because RCS can be used to edit configurations, the connected application can be used to push the configurations directly from the designer to Finance and Operations apps environments.</span></span> <span data-ttu-id="a4adc-159">Dzięki temu można szybko zmieniać i testować konfiguracje, a nie korzystać z magazynu na poziomie projektu usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="a4adc-159">Therefore, you can quickly change and test your configurations instead of having to go through LCS project-level storage.</span></span>

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a><span data-ttu-id="a4adc-160">Czy są jakieś przykłady, które pokazują konfigurację i zarządzanie?</span><span class="sxs-lookup"><span data-stu-id="a4adc-160">Are there any examples that show the setup and management?</span></span>

<span data-ttu-id="a4adc-161">Nie ma żadnych przykładów, ale możesz wykonać kroki opisane wcześniej w tym temacie, aby migrować konfiguracje do repozytorium globalnego RCS.</span><span class="sxs-lookup"><span data-stu-id="a4adc-161">There are no examples, but you can complete the steps earlier in this topic to migrate your configurations to the RCS Global repository.</span></span>