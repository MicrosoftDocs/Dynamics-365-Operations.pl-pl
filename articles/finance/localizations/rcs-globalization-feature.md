---
title: Usługi Regulatory Configuration Services (RCS) — funkcje globalizacji
description: W tym temacie objaśniono sposób korzystania z Microsoft Regulatory Configuration Services (RCS) i repozytorium globalnego do tworzenia i obsługiwania funkcji globalizacji.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: b701e6bfa14ac30e02bfe79666963db4ee657302
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5002801"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a><span data-ttu-id="83fd4-103">Usługi Regulatory Configuration Services (RCS) — funkcje globalizacji</span><span class="sxs-lookup"><span data-stu-id="83fd4-103">Regulatory Configuration Services (RCS) - Globalization features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83fd4-104">Za pomocą usług Microsoft Regulatory Configuration Services (RCS) można utworzyć funkcję Globalizacji, której można używać w usługach globalizacji, takich jak usługa fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="83fd4-104">You can use Microsoft Regulatory Configuration Services (RCS) to create a Globalization feature that can be used in Globalization services, such as an e-invoicing service.</span></span> <span data-ttu-id="83fd4-105">RCS umożliwia wykonywanie następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="83fd4-105">RCS lets you perform these tasks:</span></span>

- <span data-ttu-id="83fd4-106">Definiowanie powiązanych składników funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-106">Define related components of a feature.</span></span>
- <span data-ttu-id="83fd4-107">Zarządzanie cyklem życia funkcji za pomocą stanu funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-107">Manage the feature lifecycle through a feature's status.</span></span>
- <span data-ttu-id="83fd4-108">Umożliwia udostępnienie funkcji dla zdefiniowanych środowisk.</span><span class="sxs-lookup"><span data-stu-id="83fd4-108">Make a feature available for defined environments.</span></span>
- <span data-ttu-id="83fd4-109">Udostępnianie funkcji innym organizacjom.</span><span class="sxs-lookup"><span data-stu-id="83fd4-109">Share a feature with other organizations.</span></span>

<span data-ttu-id="83fd4-110">Poniższe procedury dotyczą sposobu dodawania funkcji globalizacji i związanych z nimi składników przez użytkownika z RCS, aktualizowania stanu funkcji oraz udostępniania funkcji w taki sposób, aby mogły być używane w usługach globalizacji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-110">The following procedures explain how a user in RCS can add a Globalization feature and related components, update the feature's status, and make the feature available so that it can be used in Globalization services.</span></span>

<span data-ttu-id="83fd4-111">Przed wykonaniem tych procedur należy wykonać kroki związane z następującymi zadaniami:</span><span class="sxs-lookup"><span data-stu-id="83fd4-111">Before you complete the procedures, you must complete the steps that are related to the following tasks:</span></span>

- <span data-ttu-id="83fd4-112">Uzyskanie dostępu do wystąpienia RCS.</span><span class="sxs-lookup"><span data-stu-id="83fd4-112">Accessing an RCS instance.</span></span>
- <span data-ttu-id="83fd4-113">Tworzenie i uaktywnianie dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-113">Creating and activating a configuration provider.</span></span> <span data-ttu-id="83fd4-114">Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="83fd4-114">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="83fd4-115">W wystąpieniu aplikacji Finance and Operations wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="83fd4-115">In your Finance and Operations apps instance, follow these steps.</span></span>

1. <span data-ttu-id="83fd4-116">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-116">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="83fd4-117">Jeśli w firmie nie aprowizowano środowiska RCS, wybierz pozycję **Regulatory services — Konfiguracja** i postępować zgodnie z instrukcjami w celu aprowizowania środowiska RCS.</span><span class="sxs-lookup"><span data-stu-id="83fd4-117">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration**, and follow the instructions to provision one.</span></span>

> [!NOTE]
> <span data-ttu-id="83fd4-118">Jeśli już aprowizowano środowisko RCS, należy skorzystać z adresu URL strony, aby uzyskać dostęp do środowiska, wybierając opcję logowania.</span><span class="sxs-lookup"><span data-stu-id="83fd4-118">If an RCS environment has already been provisioned for your company, use the page URL to access the environment by selecting the sign-in option.</span></span>

## <a name="turn-on-the-globalization-features"></a><span data-ttu-id="83fd4-119">Włączanie funkcji globalizacji</span><span class="sxs-lookup"><span data-stu-id="83fd4-119">Turn on the Globalization features</span></span>

1. <span data-ttu-id="83fd4-120">W wystąpieniu RCS wybierz kafelek **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-120">In your RCS instance, select the **Feature management** tile.</span></span>
2. <span data-ttu-id="83fd4-121">W obszarze roboczym **Zarządzanie funkcjami** wybierz z listy **Funkcje globalizacji**, a następnie wybierz pozycję **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-121">In the **Feature management** workspace, select **Globalization features** in the list, and then select **Enable now**.</span></span>

    ![Funkcje globalizacji w zarządzaniu funkcjami](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a><span data-ttu-id="83fd4-123">Funkcje globalizacji</span><span class="sxs-lookup"><span data-stu-id="83fd4-123">Globalization features</span></span>

<span data-ttu-id="83fd4-124">Aby skorzystać z funkcji globalizacji, należy najpierw zaimportować ją z repozytorium globalnego i utworzyć własną wersję.</span><span class="sxs-lookup"><span data-stu-id="83fd4-124">To use a Globalization feature, you must first import it from the the Global repository and create your own version of it.</span></span> <span data-ttu-id="83fd4-125">Istnieją dwa sposoby dodawania funkcji globalizacji:</span><span class="sxs-lookup"><span data-stu-id="83fd4-125">There are two ways to add Globalization features:</span></span>

- <span data-ttu-id="83fd4-126">Dodaj pochodną funkcję opartą na istniejącej funkcji, która została opublikowana lub udostępniona.</span><span class="sxs-lookup"><span data-stu-id="83fd4-126">Add a derived feature that is based on an existing feature that has been published or shared.</span></span>
- <span data-ttu-id="83fd4-127">Dodaj nową funkcję utworzoną przez użytkownika od podstaw.</span><span class="sxs-lookup"><span data-stu-id="83fd4-127">Add a new feature that you've created from scratch.</span></span>

## <a name="access-globalization-features"></a><span data-ttu-id="83fd4-128">Dostęp do funkcji globalizacji</span><span class="sxs-lookup"><span data-stu-id="83fd4-128">Access Globalization features</span></span>

1. <span data-ttu-id="83fd4-129">Należy się upewnić, że funkcja **Funkcje globalizacji** jest włączona w module Zarządzanie funkcjami, tak jak to opisano wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="83fd4-129">Make sure that the **Globalization features** feature is turned on in Feature management, as described earlier in this topic.</span></span>
2. <span data-ttu-id="83fd4-130">Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Fakturowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-130">Open the new **Globalization Features** workspace, and then, under **Features**, select the **e-Invoicing** tile.</span></span>

    ![Obszar roboczy funkcje globalne](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    <span data-ttu-id="83fd4-132">Zostanie otwarta strona **Funkcje fakturowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-132">The **e-Invoicing Features** page is opened.</span></span>

    ![Strona Funkcje fakturowania elektronicznego](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a><span data-ttu-id="83fd4-134">Dodaj pochodną funkcję globalizacji</span><span class="sxs-lookup"><span data-stu-id="83fd4-134">Add a derived Globalization feature</span></span>

<span data-ttu-id="83fd4-135">Nową funkcję globalizacji można dodać, wywodząc ją z istniejącej funkcji, która została opublikowana lub udostępniona.</span><span class="sxs-lookup"><span data-stu-id="83fd4-135">You can add a new Globalization feature by deriving it from an existing feature that has been published or shared.</span></span>

1. <span data-ttu-id="83fd4-136">Wybierz opcję **Import**, aby otworzyć stronę **Importuj funkcję z repozytorium globalnego**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-136">Select **Import** to open the **Import feature from Global repository** page.</span></span>

    ![Funkcja importu ze strony Repozytorium globalne](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. <span data-ttu-id="83fd4-138">Wybierz opcję **Synchronizuj**, aby uzyskać najnowsze funkcje.</span><span class="sxs-lookup"><span data-stu-id="83fd4-138">Select **Synchronize** to get the latest features.</span></span>

    <span data-ttu-id="83fd4-139">Zsynchronizowana lista zawiera dostępne funkcje, ponieważ zostały one opublikowane przez firmę Microsoft lub udostępnione przez innego dostawcę konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-139">The synced list includes features that are available to you either because they were published by Microsoft or because they were shared with you by another configuration provider.</span></span>

    ![Zsynchronizowana lista funkcji](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. <span data-ttu-id="83fd4-141">Z listy wybierz funkcje do zaimportowania, a następnie wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-141">In the list, select the features to import, and then select **Import**.</span></span> <span data-ttu-id="83fd4-142">Po pomyślnym zaimportowaniu wybranych funkcji zostanie wyświetlony komunikat.</span><span class="sxs-lookup"><span data-stu-id="83fd4-142">You receive a message when the selected features have been successfully imported.</span></span>

    ![Komunikat o pomyślnym importowaniu](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. <span data-ttu-id="83fd4-144">Wybierz opcję **Dodaj**, a następnie w oknie dialogowym rozwijanym wybierz opcję **Na podstawie istniejącej wersji**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-144">Select **Add**, and then, in the drop-down dialog box, select the **Based on existing version** option.</span></span>
5. <span data-ttu-id="83fd4-145">Wprowadź nazwę i opis funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-145">Enter a name and description for the feature.</span></span>
6. <span data-ttu-id="83fd4-146">Na liście dostępnych funkcji wybierz wersję podstawową tej funkcji, a następnie wybierz opcję **Utwórz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-146">In the list of available features, select the base version of the feature, and then select **Create feature**.</span></span>

    ![Dodawanie funkcji pochodnej](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    <span data-ttu-id="83fd4-148">Dodana funkcja jest tworzona i ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-148">The feature that you added is created and has a status of **Draft**.</span></span>

    ![Funkcja pochodna o stanie wersji roboczej](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. <span data-ttu-id="83fd4-150">Przejrzyj składniki funkcji, aby określić, czy aktualizacje są wymagane:</span><span class="sxs-lookup"><span data-stu-id="83fd4-150">Review the feature components to determine whether updates are required:</span></span>

    - <span data-ttu-id="83fd4-151">Przejrzyj konfiguracje, na wypadek potrzeby dostosowania formatów Raportowania elektronicznego (ER) i ich powiązania ich z mapowaniami formatu dla wersji funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-151">Review the configurations, in case you need to customize the Electronic reporting (ER) formats and their binding with format mappings for the feature version.</span></span>
    - <span data-ttu-id="83fd4-152">Przejrzyj ustawienia, jeśli chcesz dostosować kartę **Akcje**, kartę **Reguły stosowania** lub **Zmienne** dla wersji funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-152">Review the setup, in case you need to customize the **Actions** tab, **Applicability rules** tab, or **Variables** tab for the feature version.</span></span>

8. <span data-ttu-id="83fd4-153">Na karcie **Wersje** wybierz datę **Obowiązuje od** i wprowadź opis, jeśli pole **Opis** jest puste.</span><span class="sxs-lookup"><span data-stu-id="83fd4-153">On the **Versions** tab, select an **Effective from** date, and enter a description if the **Description** field is blank.</span></span>
9. <span data-ttu-id="83fd4-154">Aby zakończyć tę funkcję, wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-154">Select **Change status** to complete the feature.</span></span> <span data-ttu-id="83fd4-155">Ukończone funkcje można udostępnić dla określonego środowiska, aby mogły być używane w usługach globalizacji, lub mogą być publikowane w repozytorium globalnym.</span><span class="sxs-lookup"><span data-stu-id="83fd4-155">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="83fd4-156">Funkcje, które mają wartość **Stan wersji funkcji** jako **Opublikowano**, mogą być udostępniane organizacjom zewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="83fd4-156">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="add-a-new-globalization-feature"></a><span data-ttu-id="83fd4-157">Dodaj nową funkcję globalizacji</span><span class="sxs-lookup"><span data-stu-id="83fd4-157">Add a new Globalization feature</span></span>

<span data-ttu-id="83fd4-158">Nową funkcję globalizacji można dodać, tworząc ją od podstaw.</span><span class="sxs-lookup"><span data-stu-id="83fd4-158">You can add a new Globalization feature by creating it from scratch.</span></span>

1. <span data-ttu-id="83fd4-159">Na stronie **Importuj funkcję z repozytorium globalnego** wybierz opcję **Dodaj**, a następnie w oknie dialogowym rozwijanym wybierz opcję **Nowa funkcja**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-159">On the **Import feature from Global repository** page, select **Add**, and then, in the drop-down dialog box, select the **New feature** option.</span></span>
2. <span data-ttu-id="83fd4-160">Wprowadź nazwę i opis funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-160">Enter a name and description for the feature.</span></span>
3. <span data-ttu-id="83fd4-161">Wybierz opcję **Utwórz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-161">Select **Create feature**.</span></span>

    ![Dodawanie nowej funkcji](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. <span data-ttu-id="83fd4-163">Na karcie **Wersje** wybierz datę **Obowiązuje od**, a następnie wybierz opcję **Zmień stan**, aby zakończyć tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="83fd4-163">On the **Versions** tab, select an **Effective from** date, and then select **Change status** to complete the feature.</span></span> <span data-ttu-id="83fd4-164">Ukończone funkcje można udostępnić dla określonego środowiska, aby mogły być używane w usługach globalizacji, lub mogą być publikowane w repozytorium globalnym.</span><span class="sxs-lookup"><span data-stu-id="83fd4-164">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="83fd4-165">Funkcje, które mają wartość **Stan wersji funkcji** jako **Opublikowano**, mogą być udostępniane organizacjom zewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="83fd4-165">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="feature-component-overview"></a><span data-ttu-id="83fd4-166">Omówienie składnika funkcji</span><span class="sxs-lookup"><span data-stu-id="83fd4-166">Feature component overview</span></span>

<span data-ttu-id="83fd4-167">Funkcje globalizacji mają kilka składników:</span><span class="sxs-lookup"><span data-stu-id="83fd4-167">Globalization features have several components:</span></span>

- <span data-ttu-id="83fd4-168">**Wersja** — ten składnik obsługuje zarządzanie cyklem życia funkcji i umożliwia użytkownikom zarządzanie stanem różnych wersji tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-168">**Version** – This component supports feature lifecycle management and lets users manage the status for different versions of the feature.</span></span>
- <span data-ttu-id="83fd4-169">**Konfiguracje** — ten składnik umożliwia użytkownikom zarządzanie, wyświetlanie i edytowanie pokrewnych formatów raportowania elektronicznego i mapowaniem formatów.</span><span class="sxs-lookup"><span data-stu-id="83fd4-169">**Configurations** – This component lets users manage, view, and edit related ER formats and format mappings.</span></span>
- <span data-ttu-id="83fd4-170">**Konfiguracje** — ten składnik umożliwia użytkownikom usług globalizacji, takich jak usługa fakturowania elektronicznego, zarządzanie konfiguracją odpowiedniej wersji funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-170">**Setups** – This component lets users of Globalization services, such as an e-invoicing service, manage the setup of the related feature version.</span></span> <span data-ttu-id="83fd4-171">Z tego względu system obsługuje elastyczne konstruowanie reguł komunikacji i odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="83fd4-171">Therefore, it supports the flexible construction of communication and responses rules.</span></span>
- <span data-ttu-id="83fd4-172">**Środowisko** — ten składnik umożliwia użytkownikom usług globalizacji, takich jak usługa faktury elektroniczne, zarządzanie środowiskiem, w którym jest używana konfiguracja wersji funkcji, i udzielanie autoryzacji użytkownikom, którzy będą mieli do niego dostęp.</span><span class="sxs-lookup"><span data-stu-id="83fd4-172">**Environment** – This component lets users of Globalization services, such as an e-invoicing service, manage the environment where the feature version setup is used and grant authorization to the users who will have access to it.</span></span>
- <span data-ttu-id="83fd4-173">**Organizacje** — ten składnik umożliwia użytkownikom udostępnianie tej funkcji organizacjom zewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="83fd4-173">**Organizations** – This component lets users to share the feature with external organizations.</span></span>

## <a name="configuring-feature-components"></a><span data-ttu-id="83fd4-174">Konfigurowanie składników funkcji</span><span class="sxs-lookup"><span data-stu-id="83fd4-174">Configuring feature components</span></span>

### <a name="version-and-status"></a><span data-ttu-id="83fd4-175">Wersja i stan</span><span class="sxs-lookup"><span data-stu-id="83fd4-175">Version and status</span></span>

<span data-ttu-id="83fd4-176">Ta wersja służy do zarządzania cyklem życia funkcji globalizacji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-176">The version is used to manage the Globalization feature lifecycle.</span></span>

<span data-ttu-id="83fd4-177">Stan można zmienić w polu **Stan** na karcie **Wersja**. Dostępne są następujące stany:</span><span class="sxs-lookup"><span data-stu-id="83fd4-177">The status can be changed in the **Status** field on the **Version** tab. The following statuses are available:</span></span>

- <span data-ttu-id="83fd4-178">**Wersja robocza** — Funkcja może być edytowana tylko wtedy, gdy znajduje się w tym stanie.</span><span class="sxs-lookup"><span data-stu-id="83fd4-178">**Draft** – The feature can be edited only when it's in this status.</span></span>
- <span data-ttu-id="83fd4-179">**Pełna** — Funkcja i wszystkie powiązane składniki zostały sfinalizowane (ukończone) i nie można ich edytować.</span><span class="sxs-lookup"><span data-stu-id="83fd4-179">**Complete** – The feature and all related components have been finalized (completed) and can't be edited.</span></span>
- <span data-ttu-id="83fd4-180">**Opublikowano** — Funkcja i wszystkie powiązane składniki zostały opublikowane w repozytorium globalnym.</span><span class="sxs-lookup"><span data-stu-id="83fd4-180">**Published** – The feature and all related components have been published to the Global repository.</span></span>
- <span data-ttu-id="83fd4-181">**Udostępnione** — Funkcja i wszystkie powiązane składniki zostały udostępnione organizacjom zewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="83fd4-181">**Shared** – The feature and all related components have been shared with external organizations.</span></span>
- <span data-ttu-id="83fd4-182">**Włączone** — Funkcja i wszystkie powiązane składniki zostały włączone do użycia w usłudze globalizacji, takiej jak usługa fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="83fd4-182">**Enabled** – The feature and all related components have been enabled for use in a Globalization service, such as an e-invoicing service.</span></span>

> [!NOTE]
> <span data-ttu-id="83fd4-183">Funkcje muszą przechodzić sekwencyjnie przez niektóre z tych stanów.</span><span class="sxs-lookup"><span data-stu-id="83fd4-183">Features must move sequentially through some of these statuses.</span></span> <span data-ttu-id="83fd4-184">Z tego względu nie każdy stan może być dostępny w każdym etapie cyklu eksploatacji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-184">Therefore, not every status might be available at every lifecycle stage.</span></span>

### <a name="configurations"></a><span data-ttu-id="83fd4-185">Konfiguracje</span><span class="sxs-lookup"><span data-stu-id="83fd4-185">Configurations</span></span>

<span data-ttu-id="83fd4-186">Dla konfiguracji dostępne są następujące działania:</span><span class="sxs-lookup"><span data-stu-id="83fd4-186">The following actions are available for configurations:</span></span>

- <span data-ttu-id="83fd4-187">**Wyświetlanie** — umożliwia wyświetlenie konfiguracji funkcji, które nie wymagają aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-187">**View** – View the underlying feature configurations that don't require any update.</span></span>
- <span data-ttu-id="83fd4-188">**Edycja** — umożliwia utworzenie wersji roboczej wybranej konfiguracji, dzięki czemu można edytować format lub mapowanie formatów w Projektancie formatów.</span><span class="sxs-lookup"><span data-stu-id="83fd4-188">**Edit** – Create a draft version of a selected configuration so that you can edit the format or format mapping in the Format designer.</span></span>
- <span data-ttu-id="83fd4-189">**Usuwanie** — służy do usuwania wybranej konfiguracji z funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-189">**Delete** – Delete a selected configuration from the feature.</span></span>
- <span data-ttu-id="83fd4-190">**Zmiana podstawy** — umożliwia zmianę podstawy funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-190">**Rebase** – Rebase the feature.</span></span> <span data-ttu-id="83fd4-191">Aby uzyskać więcej informacji, zobacz sekcję [Zmiana podstawy pochodnych funkcji globalizacji](#rebase) w następnej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="83fd4-191">For more information, see the [Rebase derived Globalization features](#rebase) section later in this topic.</span></span>

### <a name="setups"></a><span data-ttu-id="83fd4-192">Konfiguracje</span><span class="sxs-lookup"><span data-stu-id="83fd4-192">Setups</span></span>

<span data-ttu-id="83fd4-193">Dostępne są następujące akcje dla konfiguracji funkcji:</span><span class="sxs-lookup"><span data-stu-id="83fd4-193">The following actions are available for feature setups:</span></span>

- <span data-ttu-id="83fd4-194">**Dodaj** — umożliwia utworzenie nowej konfiguracji funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-194">**Add** – Create a new feature setup.</span></span> <span data-ttu-id="83fd4-195">Ta funkcja może pochodzić z istniejącej konfiguracji funkcji lub utworzona od podstaw.</span><span class="sxs-lookup"><span data-stu-id="83fd4-195">This feature setup can be derived from an existing feature setup or created from scratch.</span></span>
- <span data-ttu-id="83fd4-196">**Usuwanie** — umożliwia usunięcie wybranej konfiguracji funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-196">**Delete** – Delete a selected feature setup.</span></span>
- <span data-ttu-id="83fd4-197">**Wyświetlanie** — umożliwia wyświetlenie podstawowej konfiguracji funkcji, w której nie są wymagane żadne zmiany.</span><span class="sxs-lookup"><span data-stu-id="83fd4-197">**View** – View an underlying feature setup that doesn't require any changes.</span></span>
- <span data-ttu-id="83fd4-198">**Edycja** — służy do tworzenia, usuwania i modyfikowania atrybutów trzech głównych składników konfiguracji funkcji:</span><span class="sxs-lookup"><span data-stu-id="83fd4-198">**Edit** – Create, delete, or modify the attributes of the three main components of a feature setup:</span></span>

    - <span data-ttu-id="83fd4-199">Akcje i ich parametry</span><span class="sxs-lookup"><span data-stu-id="83fd4-199">Actions and their parameters</span></span>
    - <span data-ttu-id="83fd4-200">Reguły zastosowania</span><span class="sxs-lookup"><span data-stu-id="83fd4-200">Applicability rules</span></span>
    - <span data-ttu-id="83fd4-201">Zmienne</span><span class="sxs-lookup"><span data-stu-id="83fd4-201">Variables</span></span>

![Strona ustawień wersji funkcji](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a><span data-ttu-id="83fd4-203">Środowiska</span><span class="sxs-lookup"><span data-stu-id="83fd4-203">Environments</span></span>

<span data-ttu-id="83fd4-204">Dla środowisk dostępne są następujące działania:</span><span class="sxs-lookup"><span data-stu-id="83fd4-204">The following actions are available for environments:</span></span>

- <span data-ttu-id="83fd4-205">**Włącz** — dla wybranej wersji funkcji wybierz opublikowane środowisko i wybierz datę **Obowiązuje od**, która powinna być dostępna.</span><span class="sxs-lookup"><span data-stu-id="83fd4-205">**Enable** – For a selected feature version, select a published environment, and select an **Effective from** date when it should be available.</span></span> <span data-ttu-id="83fd4-206">Aby uzyskać więcej informacji, zobacz sekcję [Skonfiguruj środowiska do włączania](#configureenvironment) w następnej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="83fd4-206">For more information, see the [Configure environments for enablement](#configureenvironment) section later in this topic.</span></span>
- <span data-ttu-id="83fd4-207">**Anuluj** — umożliwia usuwanie środowiska konfiguracji funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-207">**Cancel** – Remove an environment for a feature setup.</span></span>

### <a name="organizations"></a><span data-ttu-id="83fd4-208">Organizacje</span><span class="sxs-lookup"><span data-stu-id="83fd4-208">Organizations</span></span>

<span data-ttu-id="83fd4-209">Aby udostępnić funkcję globalizacji w organizacji zewnętrznej, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="83fd4-209">Follow these steps to share a Globalization feature with an external organization.</span></span>

1. <span data-ttu-id="83fd4-210">Na stronie **Funkcje fakturowania elektronicznego** wybierz funkcję i wersję funkcji do udostępnienia.</span><span class="sxs-lookup"><span data-stu-id="83fd4-210">On the **e-Invoicing features** page, select the feature and the feature version to share.</span></span>
2. <span data-ttu-id="83fd4-211">Na karcie **Organizacje** wybierz pozycję **Udostępnij**, a następnie w oknie dialogowym rozwijanym wprowadź nazwę domeny organizacji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-211">On the **Organizations** tab, select **Share with**, and then, in the drop-down dialog box, enter the organization's domain name.</span></span>
3. <span data-ttu-id="83fd4-212">Wybierz opcję **Udostępnij**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-212">Select **Share**.</span></span>

    ![Udostępnianie funkcji organizacji](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

<span data-ttu-id="83fd4-214">Funkcja jest udostępniana wybranej organizacji zewnętrznej i jest dostępna dla tej organizacji w repozytorium globalnym.</span><span class="sxs-lookup"><span data-stu-id="83fd4-214">The feature is shared with the selected organization and is available for that organization in the Global repository.</span></span> <span data-ttu-id="83fd4-215">Stamtąd funkcja może być zaimportowana do instancji organizacji RCS lub Dynamics 365 Finance, żeby mogła zostać użyta.</span><span class="sxs-lookup"><span data-stu-id="83fd4-215">From there, the feature can be imported into the organization's instance of RCS or Dynamics 365 Finance so that it can be used.</span></span>

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a><span data-ttu-id="83fd4-216">Zmiana podstawy pochodnych funkcji globalizacji</span><span class="sxs-lookup"><span data-stu-id="83fd4-216">Rebase derived Globalization features</span></span>

<span data-ttu-id="83fd4-217">Możesz zmienić pochodną funkcji globalizacji na nową lub zaktualizowaną podstawową wersję funkcji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-217">You can rebase a derived Globalization feature to the new or updated base feature version.</span></span> <span data-ttu-id="83fd4-218">W ten sposób można automatycznie zaktualizować zmiany, które nastąpiły w wersji podstawowej.</span><span class="sxs-lookup"><span data-stu-id="83fd4-218">In this way, changes that have occurred in the base version can be automatically updated.</span></span> <span data-ttu-id="83fd4-219">Zaktualizowana wersja podstawowa funkcji jest tworzona przez źródłowego dostawcę konfiguracji i jest następnie publikowana lub udostępniana.</span><span class="sxs-lookup"><span data-stu-id="83fd4-219">The updated base feature version is created by the originating configuration provider, and it's then published or shared.</span></span>

![Zaktualizowana wersja funkcji podstawowej](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

<span data-ttu-id="83fd4-221">Na przykład, aby można było zmienić podstawę pochodnej wersji utworzonej wcześniej funkcji, należy najpierw zaimportować ją z repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="83fd4-221">For example, if you want to rebase the derived version of a feature that you created, you first get the latest version of the feature by importing it from the Global repository.</span></span>

1. <span data-ttu-id="83fd4-222">Na stronie **Funkcje fakturowania elektronicznego** wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-222">On the **e-Invoicing features** page, select **Import**.</span></span>
2. <span data-ttu-id="83fd4-223">Wybierz opcję **Synchronizuj**, aby uzyskać najnowsze funkcje.</span><span class="sxs-lookup"><span data-stu-id="83fd4-223">Select **Synchronize** to get the latest features.</span></span>
3. <span data-ttu-id="83fd4-224">Z listy funkcji wybierz funkcje do zaimportowania, a następnie wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-224">In the list of features, select the features to import, and then select **Import**.</span></span>

    ![Importowanie najnowszej wersji funkcji](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. <span data-ttu-id="83fd4-226">Z listy funkcji wybierz funkcję do zmiany podstawy.</span><span class="sxs-lookup"><span data-stu-id="83fd4-226">In the list of features, select the feature to rebase.</span></span>
5. <span data-ttu-id="83fd4-227">Na karcie **Wersja** wybierz opcję **Nowa**, aby utworzyć wersję roboczą.</span><span class="sxs-lookup"><span data-stu-id="83fd4-227">On the **Version** tab, select **New** to create a draft version.</span></span>

    ![Utworzono nową wersję roboczą](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. <span data-ttu-id="83fd4-229">Wybierz opcję **Zmień podstawę**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-229">Select **Rebase**.</span></span>
7. <span data-ttu-id="83fd4-230">W oknie dialogowym **Zmiana podstawy** wybierz najnowszą wersję funkcji, która ma być poddana zmianie podstawy.</span><span class="sxs-lookup"><span data-stu-id="83fd4-230">In the **Rebase** dialog box, select the latest version of the feature to rebase to.</span></span>

    ![Okno dialogowe zmiana podstawy](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. <span data-ttu-id="83fd4-232">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-232">Select **OK**.</span></span>
9. <span data-ttu-id="83fd4-233">Przejrzyj składniki funkcji i wprowadź wymagane zmiany.</span><span class="sxs-lookup"><span data-stu-id="83fd4-233">Review the feature components, and make any changes that are required.</span></span>
10. <span data-ttu-id="83fd4-234">Aby zakończyć zmianę podstawy funkcji, wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-234">Select **Change status** to complete the rebased feature.</span></span> <span data-ttu-id="83fd4-235">Po zakończeniu zmiany podstawy można wykonać dodatkowe akcje.</span><span class="sxs-lookup"><span data-stu-id="83fd4-235">When the rebase is completed, you can perform additional actions.</span></span> <span data-ttu-id="83fd4-236">Można na przykład opublikować tę funkcję i udostępnić ją do użytku w usługach globalizacji.</span><span class="sxs-lookup"><span data-stu-id="83fd4-236">For example, you can publish the feature and make it available for use in Globalization services.</span></span>

    ![Stan funkcji został zaktualizowany na zakończono](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a><span data-ttu-id="83fd4-238">Konfigurowanie środowisk dla funkcji globalizacji</span><span class="sxs-lookup"><span data-stu-id="83fd4-238">Configure environments for Globalization features</span></span>

<span data-ttu-id="83fd4-239">Użytkownicy usług globalizacji mogą zarządzać środowiskiem, aby skonfigurować funkcję globalizacji i udzielić autoryzacji innym użytkownikom, którzy będą mieli do niej dostęp.</span><span class="sxs-lookup"><span data-stu-id="83fd4-239">Users of Globalization services can manage the environment to set up a Globalization feature and grant authorization to other users who will have access to it.</span></span>

1. <span data-ttu-id="83fd4-240">Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Fakturowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="83fd4-240">In the **Globalization Features** workspace, under **Environments**, select the **e-Invoicing** tile.</span></span>

    ![Obszar roboczy funkcje globalizacji](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. <span data-ttu-id="83fd4-242">Wybierz **Parametry usługi Key Vault**, a następnie wybierz opcję **Nowy**, aby utworzyć klucz tajny Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="83fd4-242">Select **Key Vault parameters**, and then select **New** to create an Azure Key Vault secret.</span></span>
3. <span data-ttu-id="83fd4-243">Wprowadź nazwę i opis magazynu kluczy, a następnie w polu **Identyfikator URI magazynu kluczy** wprowadź adres URL identyfikujący zasób Key Vault w Azure.</span><span class="sxs-lookup"><span data-stu-id="83fd4-243">Enter a name and description for the key vault, and then, in the **Key Vault URI** field, enter the URL that identifies the Key Vault resource in Azure.</span></span>
4. <span data-ttu-id="83fd4-244">Na skróconej karcie **Certyfikaty** wybierz przycisk **Dodaj**, aby dodać certyfikat, i wprowadź nazwę i opis każdego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="83fd4-244">On the **Certificates** FastTab, select **Add** to add the certificate, and enter a name and description for each certificate.</span></span>

    ![Dodano certyfikat](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. <span data-ttu-id="83fd4-246">Wybierz pozycję **Nowy**, aby utworzyć nowe środowisko.</span><span class="sxs-lookup"><span data-stu-id="83fd4-246">Select **New** to create a new environment.</span></span>
6. <span data-ttu-id="83fd4-247">Wprowadź nazwę, opis oraz poufny token podpisu dostępu współdzielonego wymagany dla magazynu.</span><span class="sxs-lookup"><span data-stu-id="83fd4-247">Enter a name, a description, and the shared access signature token secret required for the storage.</span></span>
7. <span data-ttu-id="83fd4-248">Na skróconej karcie **Użytkownicy** wybierz opcję **Nowy**, aby dodać użytkownika, który będzie miał uprawnienia dostępu do tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="83fd4-248">On the **Users** FastTab, select **New** to add a user who will have permission to access this environment.</span></span>
8. <span data-ttu-id="83fd4-249">Wprowadź identyfikator użytkownika i adres e-mail użytkownika.</span><span class="sxs-lookup"><span data-stu-id="83fd4-249">Enter the user's user ID and email address.</span></span>
9. <span data-ttu-id="83fd4-250">Powtórz kroki 7 i 8, aby dodać więcej użytkowników.</span><span class="sxs-lookup"><span data-stu-id="83fd4-250">Repeat steps 7 and 8 to add more users.</span></span>
10. <span data-ttu-id="83fd4-251">Wybierz opcję **Publikuj**, aby opublikować środowisko.</span><span class="sxs-lookup"><span data-stu-id="83fd4-251">Select **Publish** to publish the environment.</span></span>

    ![Opublikowane środowisko](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)
