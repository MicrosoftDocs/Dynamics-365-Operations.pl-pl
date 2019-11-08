---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (30 lipiec 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 3676a0a1fa77285d0203e8e49725cb1c1b742d39
ms.sourcegitcommit: 029c1882bef558b6a45843548e94ab8369ed9870
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2019
ms.locfileid: "2651718"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-30-2019"></a><span data-ttu-id="dc539-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (30 lipiec 2019)</span><span class="sxs-lookup"><span data-stu-id="dc539-103">What's new or changed in Dynamics 365 Talent (July 30, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dc539-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="dc539-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="dc539-105">Zmiany w Attract</span><span class="sxs-lookup"><span data-stu-id="dc539-105">Changes in Attract</span></span>
<span data-ttu-id="dc539-106">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="dc539-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="dc539-107">Zmiany w Onboard</span><span class="sxs-lookup"><span data-stu-id="dc539-107">Changes in Onboard</span></span>
<span data-ttu-id="dc539-108">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="dc539-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="dc539-109">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="dc539-109">Changes in Core HR</span></span>
<span data-ttu-id="dc539-110">Zmiany opisane w tej części dotyczą kompilacji 8.1.2409.</span><span class="sxs-lookup"><span data-stu-id="dc539-110">Changes described in this section apply to build number 8.1.2409.</span></span>


### <a name="region-support-for-canada-and-southeast-asia"></a><span data-ttu-id="dc539-111">Obsługa regionu Kanada i Południowo-Wschodnia Azja</span><span class="sxs-lookup"><span data-stu-id="dc539-111">Region support for Canada and Southeast Asia</span></span>

<span data-ttu-id="dc539-112">Mamy przyjemność poinformować o tym, że rozwiązania Talent od 1 sierpnia 2019 r. będą dostępne w regionach Kanada i Azja Południowo-Wschodnia.</span><span class="sxs-lookup"><span data-stu-id="dc539-112">We are pleased to announce that Canada and Southeast Asia regions will be available for Talent on August 1, 2019.</span></span> <span data-ttu-id="dc539-113">Dzięki tej zmianie można tworzyć środowiska w regionach Kanada i Azja, a wszystkie dane Talent będą obsługiwane wyłącznie w tych lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="dc539-113">With this change, you can create environments in the Canadian and Asian regions, and all Talent data will be maintained solely within those locations.</span></span> <span data-ttu-id="dc539-114">Środowisko w tych nowych regionach można utworzyć, wybierając lokalizację w oknie dialogowym Nowe środowisko i używając tego środowiska do inicjowania obsługi Talent w LCS, zgodnie z opisem [Inicjowanie obsługi rozwiązania Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="dc539-114">You can create an environment in these new regions by selecting the location in the New Environment dialog and use that environment to provision Talent in LCS as described in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="dc539-115">Migracja danych istniejących projektów z innych regionów do Kanady i Azji nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="dc539-115">Data migration of existing projects from other regions to the Canadian and Asian regions is not supported.</span></span> <span data-ttu-id="dc539-116">Tylko nowe projekty mogą zostać zainicjowane do tych nowych obsługiwanych regionów.</span><span class="sxs-lookup"><span data-stu-id="dc539-116">Only new projects can be provisioned to these new supported regions.</span></span>

### <a name="new-active-positions-list-page"></a><span data-ttu-id="dc539-117">Nowa strona listy aktywnych stanowisk</span><span class="sxs-lookup"><span data-stu-id="dc539-117">New Active positions list page</span></span>

<span data-ttu-id="dc539-118">Dostępne są następujące opcje dla list stanowisk: **Wszystkie stanowiska**, **Aktywne stanowiska**, **Otwarte stanowiska** i **Nieaktywne**.</span><span class="sxs-lookup"><span data-stu-id="dc539-118">The options for position-based lists now include: **All positions**, **Active positions**, **Open positions**, and **Inactive positions**.</span></span> <span data-ttu-id="dc539-119">Na nowej stronie **Aktywne stanowiska** wyświetlane są tylko te pozycje, które są otwarte lub wypełnione, które są aktywne na dzień bieżący</span><span class="sxs-lookup"><span data-stu-id="dc539-119">The new **Active positions** list page displays only those positions, open or filled, that are active as of the current date.</span></span> 

### <a name="allow-course-participants-to-be-added-to-open-courses"></a><span data-ttu-id="dc539-120">Zezwól na dodawanie uczestników kursu do otwartych kursów</span><span class="sxs-lookup"><span data-stu-id="dc539-120">Allow course participants to be added to open courses</span></span>

<span data-ttu-id="dc539-121">Zmiany w tym tygodniu są poprawiają błąd, w którym w przypadku otwartych kursów można było rejestrować tylko raporty bezpośrednie.</span><span class="sxs-lookup"><span data-stu-id="dc539-121">This week's changes correct an issue where only direct reports can be registered for open courses.</span></span>

### <a name="fte-analysis-displaying-incorrect-fte-number"></a><span data-ttu-id="dc539-122">Analiza pełnego wymiaru czasu wyświetlająca niepoprawny numer pełnego etatu</span><span class="sxs-lookup"><span data-stu-id="dc539-122">FTE Analysis displaying incorrect FTE number</span></span>

<span data-ttu-id="dc539-123">**Analiza pełnego wymiaru czasu** została poprawiona na karcie **Analizy** dla **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="dc539-123">**FTE analysis** has been corrected on the **Analytics** tab for **Personnel management**.</span></span>

### <a name="final-comments-label-translation"></a><span data-ttu-id="dc539-124">Tłumaczenie etykiety ostatecznych komentarzy</span><span class="sxs-lookup"><span data-stu-id="dc539-124">Final comments label translation</span></span>

<span data-ttu-id="dc539-125">Etykieta **Ostateczne komentarze** zostanie teraz przetłumaczona w formularzu przeglądu.</span><span class="sxs-lookup"><span data-stu-id="dc539-125">The **Final comments** label is now translated in the review form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="dc539-126">Wersja próbna</span><span class="sxs-lookup"><span data-stu-id="dc539-126">In preview</span></span>

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a><span data-ttu-id="dc539-127">Funkcje podglądu są włączone tylko w środowisku testowym</span><span class="sxs-lookup"><span data-stu-id="dc539-127">Preview features are enabled only in sandbox instances</span></span>

<span data-ttu-id="dc539-128">Podczas zastrzegania nowej instancji talentów można określić, czy typem wystąpienia jest **Produkcja**, czy **Piaskownica - środowisko testowe**.</span><span class="sxs-lookup"><span data-stu-id="dc539-128">When you provision a new instance of Talent, you can specify whether the instance type is **Production** or **Sandbox**.</span></span> <span data-ttu-id="dc539-129">Wystąpienia typu **Piaskownica** umożliwiają wczesne testowanie nowych funkcji.</span><span class="sxs-lookup"><span data-stu-id="dc539-129">Instances of the **Sandbox** type allow for early testing of new features.</span></span> <span data-ttu-id="dc539-130">Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**.</span><span class="sxs-lookup"><span data-stu-id="dc539-130">All existing Talent instances will be updated to the **Production** instance type.</span></span> <span data-ttu-id="dc539-131">Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.</span><span class="sxs-lookup"><span data-stu-id="dc539-131">If you want one of your existing instances to be updated to the **Sandbox** instance type, contact [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) to initiate the change request.</span></span>

<span data-ttu-id="dc539-132">Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="dc539-132">For more information about how changes are published, see [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

### <a name="view-extended-information-for-performance-in-manager-self-service"></a><span data-ttu-id="dc539-133">Wyświetlanie rozszerzonych informacji o wydajności w module Self-Service Manager</span><span class="sxs-lookup"><span data-stu-id="dc539-133">View extended information for performance in manager self-service</span></span>

<span data-ttu-id="dc539-134">Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych.</span><span class="sxs-lookup"><span data-stu-id="dc539-134">A new option will let managers view the performance of both their direct reports and their extended reports.</span></span> <span data-ttu-id="dc539-135">Obecnie menedżerowie liniowi mogą przypisywać i aktualizować cele wydajności oraz wystawiać nowe recenzje.</span><span class="sxs-lookup"><span data-stu-id="dc539-135">Currently, line managers can assign and update performance goals and issue new reviews.</span></span> <span data-ttu-id="dc539-136">Ponadto bezpośredni menedżerowie i ich pracownicy mogą utrzymywać i aktualizować dzienniki wydajności, aby zapewnić sprawny przebieg procesu przeglądu wydajności.</span><span class="sxs-lookup"><span data-stu-id="dc539-136">In addition, direct managers and their employees can maintain and update performance journals to help ensure that the performance review process goes smoothly.</span></span> <span data-ttu-id="dc539-137">Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie.</span><span class="sxs-lookup"><span data-stu-id="dc539-137">When this change is implemented, managers will be able to view and maintain performance-related information for their extended reports in addition to their direct reports.</span></span>
