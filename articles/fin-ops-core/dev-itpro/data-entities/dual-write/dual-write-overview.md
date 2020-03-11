---
title: Przegląd o podwójnym zapisie
description: Ten temat stanowi omówienie podwójnego zapisu. Podwójny zapis to infrastruktura umożliwiająca współpracę w czasie rzeczywistym między aplikacjami opartymi na modelach Microsoft Dynamics 365 i aplikacjami Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 12c6a39700a260c138fab67ed370f94b3aa04213
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "3075999"
---
# <a name="dual-write-overview"></a><span data-ttu-id="ee4ce-104">Przegląd o podwójnym zapisie</span><span class="sxs-lookup"><span data-stu-id="ee4ce-104">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a><span data-ttu-id="ee4ce-105">Co to jest podwójny zapis?</span><span class="sxs-lookup"><span data-stu-id="ee4ce-105">What is dual-write?</span></span>

<span data-ttu-id="ee4ce-106">Podwójny zapis to gotowa infrastruktura umożliwiająca współpracę w czasie rzeczywistym między aplikacjami opartymi na modelach Microsoft Dynamics 365 i aplikacjami Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-106">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between model-driven apps in Microsoft Dynamics 365 and Finance and Operations apps.</span></span> <span data-ttu-id="ee4ce-107">Gdy dane dotyczące odbiorców, produktów, osób i operacji przepływają poza granice aplikacji, wszystkie działy w organizacji zyskują możliwości.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-107">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="ee4ce-108">Podwójny zapis to ściśle sprzężona i dwukierunkowa integracja między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-108">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="ee4ce-109">Każda zmiana danych w aplikacjach Finance and Operations powoduje zapis do Common Data Service, a zmiana danych w Common Data Service powoduje zapis w aplikacjach Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-109">Any data change in Finance and Operations apps causes writes to Common Data Service, and any data change in Common Data Service causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="ee4ce-110">Ten zautomatyzowany przepływ danych umożliwia korzystanie ze zintegrowanego środowiska użytkownika w aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-110">This automated data flow provides an integrated user experience across the apps.</span></span>

![Relacja danych między aplikacjami](media/dual-write-overview.jpg)

<span data-ttu-id="ee4ce-112">Podwójny zapis ma dwie aspekty: *aspekt infrastruktury* i aspekt *aplikacji*.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-112">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="ee4ce-113">Infrastruktura</span><span class="sxs-lookup"><span data-stu-id="ee4ce-113">Infrastructure</span></span>

<span data-ttu-id="ee4ce-114">Infrastruktura podwójnego zapisu jest rozszerzalna i niezawodna i obejmuje następujące najważniejsze cechy:</span><span class="sxs-lookup"><span data-stu-id="ee4ce-114">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="ee4ce-115">Synchroniczne i dwukierunkowe przepływy danych między aplikacjami</span><span class="sxs-lookup"><span data-stu-id="ee4ce-115">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="ee4ce-116">Synchronizacja, wraz z trybami odtwarzania, wstrzymywania i doganiania, aby wspierać system w trybach online i offline/asynchronicznych.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-116">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="ee4ce-117">Możliwość synchronizowania danych początkowych między aplikacjami</span><span class="sxs-lookup"><span data-stu-id="ee4ce-117">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="ee4ce-118">Skonsolidowany widok działań i dzienników błędów dla administratorów danych</span><span class="sxs-lookup"><span data-stu-id="ee4ce-118">Consolidated view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="ee4ce-119">Możliwość konfigurowania niestandardowych alertów i progów oraz subskrybowanie powiadomień</span><span class="sxs-lookup"><span data-stu-id="ee4ce-119">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="ee4ce-120">Intuicyjny interfejs użytkownika służący do filtrowania i przekształcania</span><span class="sxs-lookup"><span data-stu-id="ee4ce-120">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="ee4ce-121">Możliwość ustawiania i wyświetlania zależności i relacji jednostek</span><span class="sxs-lookup"><span data-stu-id="ee4ce-121">Ability to set and view entity dependencies and relationships</span></span>
+ <span data-ttu-id="ee4ce-122">Rozszerzalność dla jednostek i map standardowych i niestandardowych</span><span class="sxs-lookup"><span data-stu-id="ee4ce-122">Extensibility for both standard and custom entities and maps</span></span>
+ <span data-ttu-id="ee4ce-123">Niezawodne zarządzanie cyklem życia zasobu</span><span class="sxs-lookup"><span data-stu-id="ee4ce-123">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="ee4ce-124">Korzystanie z gotowej konfiguracji wstępnej dla nowych odbiorców</span><span class="sxs-lookup"><span data-stu-id="ee4ce-124">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="ee4ce-125">Zgłoszenia</span><span class="sxs-lookup"><span data-stu-id="ee4ce-125">Application</span></span>

<span data-ttu-id="ee4ce-126">Podwójny zapis tworzy mapowanie między pojęciami w aplikacjach Finance and Operations i koncepcjami w aplikacjach opartych na modelach w Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-126">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="ee4ce-127">Ta integracja obsługuje następujące scenariusze:</span><span class="sxs-lookup"><span data-stu-id="ee4ce-127">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="ee4ce-128">Zintegrowane dane główne odbiorcy</span><span class="sxs-lookup"><span data-stu-id="ee4ce-128">Integrated customer master</span></span>
+ <span data-ttu-id="ee4ce-129">Dostęp do kart lojalnościowych odbiorcy i punktów lojalnościowych</span><span class="sxs-lookup"><span data-stu-id="ee4ce-129">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="ee4ce-130">Ujednolicone doświadczenie w zakresie opanowania produktu</span><span class="sxs-lookup"><span data-stu-id="ee4ce-130">Unified product mastering experience</span></span>
+ <span data-ttu-id="ee4ce-131">Świadomość hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="ee4ce-131">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="ee4ce-132">Zintegrowane dane główne dostawcy</span><span class="sxs-lookup"><span data-stu-id="ee4ce-132">Integrated vendor master</span></span>
+ <span data-ttu-id="ee4ce-133">Dostęp do danych finansowych i danych referencyjnych podatku</span><span class="sxs-lookup"><span data-stu-id="ee4ce-133">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="ee4ce-134">Doświadczenie aparatu cen na żądanie</span><span class="sxs-lookup"><span data-stu-id="ee4ce-134">On-demand price engine experience</span></span>
+ <span data-ttu-id="ee4ce-135">Zintegrowane doświadczenia Od prospekta do środków pieniężnych</span><span class="sxs-lookup"><span data-stu-id="ee4ce-135">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="ee4ce-136">Zdolność do obsługi zarówno zasobów wewnętrznych, jak i aktywów dla odbiorców za pomocą agentów pól</span><span class="sxs-lookup"><span data-stu-id="ee4ce-136">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="ee4ce-137">Zintegrowane korzystanie z funkcji od zapotrzebowania do płatności</span><span class="sxs-lookup"><span data-stu-id="ee4ce-137">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="ee4ce-138">Zintegrowane działania i uwagi dotyczące danych i dokumentów odbiorców</span><span class="sxs-lookup"><span data-stu-id="ee4ce-138">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="ee4ce-139">Możliwość wyszukiwania dostępnych zapasów i szczegółów</span><span class="sxs-lookup"><span data-stu-id="ee4ce-139">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="ee4ce-140">Edytuj doświadczenie Od projektu do środków pieniężnych</span><span class="sxs-lookup"><span data-stu-id="ee4ce-140">Project-to-cash experience</span></span>
+ <span data-ttu-id="ee4ce-141">Możliwość obsługi wielu adresów i ról za pośrednictwem koncepcji strony</span><span class="sxs-lookup"><span data-stu-id="ee4ce-141">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="ee4ce-142">Zarządzanie pojedynczym źródłem danych dla użytkowników</span><span class="sxs-lookup"><span data-stu-id="ee4ce-142">Single source management for users</span></span>
+ <span data-ttu-id="ee4ce-143">Zintegrowane kanały do sprzedaży detalicznej i marketingu</span><span class="sxs-lookup"><span data-stu-id="ee4ce-143">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="ee4ce-144">Widoczność dla promocji i rabatów</span><span class="sxs-lookup"><span data-stu-id="ee4ce-144">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="ee4ce-145">Funkcje Od żądania do usługi</span><span class="sxs-lookup"><span data-stu-id="ee4ce-145">Request-for-service functions</span></span>
+ <span data-ttu-id="ee4ce-146">Usprawnione operacje usług</span><span class="sxs-lookup"><span data-stu-id="ee4ce-146">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="ee4ce-147">Najważniejsze powody użycia funkcji podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="ee4ce-147">Top reasons to use dual-write</span></span>

<span data-ttu-id="ee4ce-148">Podwójny zapis dostarcza integrację danych między aplikacjami Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-148">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="ee4ce-149">To niezawodne środowisko łączy szkieletowo i umożliwia różnym aplikacjom biznesowym współdziałanie ze sobą.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-149">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="ee4ce-150">Oto najważniejsze powody, dla których należy zastosować metodę podwójnego odpisu:</span><span class="sxs-lookup"><span data-stu-id="ee4ce-150">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="ee4ce-151">Podwójny zapis umożliwia ścisłą integrację między aplikacjami Finance and Operations a aplikacjami opartymi na modelach w Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-151">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="ee4ce-152">Taka integracja stanowi Microsoft Dynamics 365 miejsce, gdzie można znaleźć wszystkie rozwiązania biznesowe.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-152">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="ee4ce-153">Klienci, którzy korzystają z Dynamics 365 Finance i Dynamics 365 Supply Chain Management, ale używają rozwiązań innych firm niż Microsoft do zarządzania relacjami z klientami (CRM), przenoszą się do Dynamics 365, aby skorzystać ze wsparcia podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-153">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="ee4ce-154">Dane pochodzące od odbiorców, produktów, operacji, projektów i Internetu rzeczy (IoT) automatycznie przepływają do Common Data Service w ramach podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-154">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Common Data Service through dual-write.</span></span> <span data-ttu-id="ee4ce-155">To połączenie jest bardzo przydatne w przypadku firm, które interesują się tymi samymi rozszerzeniami Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-155">This connection is very useful for businesses that are interested in Microsoft Power Platform expansions.</span></span>
+ <span data-ttu-id="ee4ce-156">Infrastruktura podwójnego zapisywania jest zgodna z zasadą braku kodowania/małej ilości kodowania.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-156">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="ee4ce-157">Wymagane są minimalne nakłady pracy inżynieryjnej, aby rozszerzyć standardowe mapy od tabeli do tabeli i uwzględnić mapy niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-157">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="ee4ce-158">Podwójne zapisywanie obsługuje tryb online i tryb offline.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-158">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="ee4ce-159">Firma Microsoft jest jedyną firmą, która oferuje obsługę trybów online i offline.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-159">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a><span data-ttu-id="ee4ce-160">Co podwójny zapis oznacza dla użytkowników i architektów produktów CRM?</span><span class="sxs-lookup"><span data-stu-id="ee4ce-160">What does dual-write mean for users and architects of CRM products?</span></span>

<span data-ttu-id="ee4ce-161">Podwójny odpis automatyzuje przepływ danych między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-161">Dual-write automates the data flow between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="ee4ce-162">W przyszłych wersjach, koncepty w aplikacjach opartych na modelach w Dynamics 365 (np. odbiorca, kontakt, oferta i zamówienie) będą skalowane do odbiorców rynków średnich i wyższych średnich.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-162">In future releases, concepts in model-driven apps in Dynamics 365 (for example, customer, contact, quotation, and order) will be scaled to mid-market and upper-mid-market customers.</span></span>

<span data-ttu-id="ee4ce-163">W pierwszym wydaniu większość automatyzacji jest obsługiwana przez rozwiązania podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-163">In the first release, most of the automation is handled by dual-write solutions.</span></span> <span data-ttu-id="ee4ce-164">W przyszłych wersjach te rozwiązania staną się częścią Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-164">In future releases, those solutions will become part of Common Data Service.</span></span> <span data-ttu-id="ee4ce-165">Przez poznanie nadchodzących zmian w długim okresie w Common Data Service, można zaoszczędzić wiele nakładów pracy.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-165">By understanding the upcoming changes to Common Data Service, you can save yourself effort in the long term.</span></span> <span data-ttu-id="ee4ce-166">Oto niektóre z kluczowych zmian:</span><span class="sxs-lookup"><span data-stu-id="ee4ce-166">Here are some of the crucial changes:</span></span>

+ <span data-ttu-id="ee4ce-167">Common Data Service ma nowe koncepcje, np. firmę i stronę.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-167">Common Data Service will have new concepts, such as company and party.</span></span> <span data-ttu-id="ee4ce-168">Te koncepcje mają wpływ na wszystkie aplikacje, które są zbudowane na Common Data Service, takie jak Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service i Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-168">These concepts will affect all apps that are built on Common Data Service, such as Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service.</span></span>
+ <span data-ttu-id="ee4ce-169">Działania i uwagi są zunifikowane i rozwinięte, co pozwala na obsługę zarówno C1 (użytkowników systemu), jak i C2 (odbiorców systemu).</span><span class="sxs-lookup"><span data-stu-id="ee4ce-169">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>
+ <span data-ttu-id="ee4ce-170">Oto niektóre z nadchodzących zmian w Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="ee4ce-170">Here are some of the upcoming changes in Common Data Service:</span></span>

    - <span data-ttu-id="ee4ce-171">Typ danych dziesiętnych zastąpi typ danych pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-171">The decimal data type will replace the money data type.</span></span>
    - <span data-ttu-id="ee4ce-172">Obowiązywanie dat będzie obsługiwać przeszłe, obecne i przyszłe dane w tym samym miejscu.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-172">Date effectivity will support past, present, and future data in the same place.</span></span>
    - <span data-ttu-id="ee4ce-173">Obsługa waluty i kursów wymiany będzie bardziej pomocna, a interfejs (API) programowania aplikacji **Kursu wymiany** zostanie poprawiony.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-173">There will be more support for currency and exchange rates, and the **Exchange Rate** application programming interface (API) will be revised.</span></span>
    - <span data-ttu-id="ee4ce-174">Konwersje jednostek będą obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-174">Unit conversions will be supported.</span></span>

<span data-ttu-id="ee4ce-175">Aby uzyskać więcej informacji o nadchodzących zmianach, zapoznaj się z tematem [Dane w Common Data Service – faza 1 i 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).</span><span class="sxs-lookup"><span data-stu-id="ee4ce-175">For more information about upcoming changes, see [Data in Common Data Service – phase 1 & 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).</span></span>
