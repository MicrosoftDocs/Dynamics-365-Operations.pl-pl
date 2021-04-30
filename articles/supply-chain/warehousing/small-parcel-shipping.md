---
title: Wysyłka małych paczek
description: Ten temat zawiera informacje dotyczące funkcji Wysyłka małych paczek (SPS). Ta funkcja umożliwia aplikacji Microsoft Dynamics 365 Supply Chain Management przesyłanie do przewoźnika szczegółów dotyczących spakowanego kontenera, a następnie odbieranie od niego etykiety wysyłkowej, stawki kosztów i numeru śledzenia.
author: Mirzaab
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3e72959d79e9b3b03e061a0f26750e3bd025219e
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910216"
---
# <a name="small-parcel-shipping"></a><span data-ttu-id="f1961-104">Wysyłka małych paczek</span><span class="sxs-lookup"><span data-stu-id="f1961-104">Small parcel shipping</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f1961-105">Funkcja wysyłki małych paczek (SPS) umożliwia aplikacji Microsoft Dynamics 365 Supply Chain Management bezpośrednią interakcję z przewoźnikami, zapewniając strukturę komunikacji za pośrednictwem interfejsów API przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="f1961-105">The small parcel shipping (SPS) feature enables Microsoft Dynamics 365 Supply Chain Management to interact directly with shipping carriers by providing a framework for communication through carrier APIs.</span></span> <span data-ttu-id="f1961-106">Ta funkcja jest przydatna w przypadku wysyłki pojedynczych zamówień sprzedaży za pośrednictwem przewoźników komercyjnych, zamiast wysyłki kontenerów lub ładunków częściowych (LTL).</span><span class="sxs-lookup"><span data-stu-id="f1961-106">This functionality is useful when you're shipping individual sales orders via commercial shipping carriers instead of using container shipping or less-than-truckload (LTL) shipping.</span></span>

<span data-ttu-id="f1961-107">Funkcja SPS współpracuje z przewoźnikiem za pośrednictwem dedykowanego *aparatu stawki*.</span><span class="sxs-lookup"><span data-stu-id="f1961-107">The SPS feature interacts with your shipping carrier through a dedicated *rate engine*.</span></span> <span data-ttu-id="f1961-108">Twoja organizacja musi opracować ten aparat stawki we współpracy z przewoźnikiem lub usługą centrum przewoźników.</span><span class="sxs-lookup"><span data-stu-id="f1961-108">Your organization must develop this rate engine in collaboration with your carrier or carrier hub service.</span></span> <span data-ttu-id="f1961-109">Aparat stawki umożliwia aplikacji Microsoft Supply Chain Management przesyłanie do przewoźnika szczegółów dotyczących spakowanego kontenera, a następnie odbieranie od niego etykiety wysyłkowej, stawki kosztów i numeru śledzenia.</span><span class="sxs-lookup"><span data-stu-id="f1961-109">The rate engine enables Supply Chain Management to submit details about a packed container to your carrier, and then receive a shipping label, shipping rate, and tracking number back from that carrier.</span></span>

<span data-ttu-id="f1961-110">Zwrócona stawka kosztów wysyłki jest dodawana do skojarzonego zamówienia sprzedaży jako opłata dodatkowa.</span><span class="sxs-lookup"><span data-stu-id="f1961-110">The shipping rate that is returned is added to the associated sales order as a miscellaneous charge.</span></span> <span data-ttu-id="f1961-111">Zwróconą etykietę wysyłkową można następnie wydrukować automatycznie za pomocą drukarki ZPL (Zebra Programming Language) i zastosować do wysyłki.</span><span class="sxs-lookup"><span data-stu-id="f1961-111">The shipping label that is returned can then automatically be printed by using a Zebra Programming Language (ZPL) printer and applied to the shipment.</span></span> <span data-ttu-id="f1961-112">Przewoźnik zeskanuje tę etykietę wysyłkową, gdy wybierze paczki w magazynie.</span><span class="sxs-lookup"><span data-stu-id="f1961-112">The carrier will scan this shipping label when it picks up the packages at your warehouse.</span></span>

## <a name="prepare-your-system-to-support-sps"></a><span data-ttu-id="f1961-113">Przygotowywanie systemu do obsługi funkcji SPS</span><span class="sxs-lookup"><span data-stu-id="f1961-113">Prepare your system to support SPS</span></span>

<span data-ttu-id="f1961-114">Aby można było rozpocząć korzystanie z funkcji SPS, należy włączyć funkcję SPS w zarządzaniu funkcjami, dodać aparat stawki oraz skonfigurować moduły **Zarządzanie transportem** i **Zarządzanie magazynem** do obsługi tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="f1961-114">Before you can start to use SPS functionality, you must turn on the SPS feature in Feature management, add your rate engine, and set up the **Transportation management** and **Warehouse management** modules to support it.</span></span>

### <a name="turn-on-the-sps-feature"></a><span data-ttu-id="f1961-115">Włączanie funkcji SPS</span><span class="sxs-lookup"><span data-stu-id="f1961-115">Turn on the SPS feature</span></span>

<span data-ttu-id="f1961-116">Aby móc używać funkcji SPS, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="f1961-116">Before you can use the SPS feature, it must be turned on in your system.</span></span> <span data-ttu-id="f1961-117">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="f1961-117">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="f1961-118">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f1961-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f1961-119">**Moduł**: *Zarządzanie transportem*</span><span class="sxs-lookup"><span data-stu-id="f1961-119">**Module:** *Transportation management*</span></span>
- <span data-ttu-id="f1961-120">**Nazwa funkcji:** *Wysyłka małych paczek*</span><span class="sxs-lookup"><span data-stu-id="f1961-120">**Feature name:** *Small parcel shipping*</span></span>

### <a name="deploy-and-set-up-rate-engines"></a><span data-ttu-id="f1961-121">Wdrażanie i konfigurowanie aparatów stawki</span><span class="sxs-lookup"><span data-stu-id="f1961-121">Deploy and set up rate engines</span></span>

<span data-ttu-id="f1961-122">Supply Chain Management nie zawiera żadnych aparatów stawki.</span><span class="sxs-lookup"><span data-stu-id="f1961-122">Supply Chain Management doesn't include any rate engines.</span></span> <span data-ttu-id="f1961-123">Musisz uzyskać lub utworzyć wszelkie wymagane aparaty stawki, a następnie dodać je do systemu.</span><span class="sxs-lookup"><span data-stu-id="f1961-123">You must obtain or create any rate engines that you require, and then add them to your system.</span></span> <span data-ttu-id="f1961-124">Microsoft dostarcza jednak pokazowy aparat stawki, który może służyć do testowania.</span><span class="sxs-lookup"><span data-stu-id="f1961-124">However, Microsoft provides a demo rate engine that you can use for testing.</span></span>

#### <a name="download-and-deploy-the-demo-rate-engine"></a><span data-ttu-id="f1961-125">Pobieranie i wdrażanie aparatu stawek demonstracyjnych</span><span class="sxs-lookup"><span data-stu-id="f1961-125">Download and deploy the demo rate engine</span></span>

<span data-ttu-id="f1961-126">Aby pobrać aparat stawek demonstracyjnych, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f1961-126">Follow these steps to get the demo rate engine.</span></span>

1. <span data-ttu-id="f1961-127">W witrynie GitHub pobierz [bibliotekę linków dynamicznych (DLL) dla aparatu stawek demonstracyjnych](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span><span class="sxs-lookup"><span data-stu-id="f1961-127">On GitHub, download the [dynamic-link library (DLL) for the demo rate engine](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span></span>
1. <span data-ttu-id="f1961-128">Na serwerze aplikacji Supply Chain Management zapisz bibliotekę DLL w folderze **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.</span><span class="sxs-lookup"><span data-stu-id="f1961-128">On your Supply Chain Management server, save the DLL in the **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin** folder.</span></span>

#### <a name="create-and-deploy-functional-rate-engines"></a><span data-ttu-id="f1961-129">Tworzenie i wdrażanie aparatów stawek funkcjonalnych</span><span class="sxs-lookup"><span data-stu-id="f1961-129">Create and deploy functional rate engines</span></span>

<span data-ttu-id="f1961-130">Aby uzyskać informacje dotyczące sposobu tworzenia i wdrażania aparatów stawek funkcjonalnych, tak aby można było ich używać w środowisku produkcyjnym lub testowym, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="f1961-130">For information about how to create and deploy functional rate engines so that they can be used in a production or test environment, see the following topics:</span></span>

- [<span data-ttu-id="f1961-131">Tworzenie nowego aparatu zarządzania transportem</span><span class="sxs-lookup"><span data-stu-id="f1961-131">Create a new transportation management engine</span></span>](../transportation/create-new-transportation-management-engine.md)
- [<span data-ttu-id="f1961-132">Ustawianie aparatów zarządzania transportem</span><span class="sxs-lookup"><span data-stu-id="f1961-132">Set up transportation management engines</span></span>](/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

<span data-ttu-id="f1961-133">Aby uzyskać więcej informacji na temat sposobu tworzenia aparatu stawek SPS, zobacz następujący wpis w blogu: [Small Parcel Shipping: How to leverage small parcel shipping functionality in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5) (Wysyłka małych paczek: jak używać funkcji wysyłki małych paczek w Microsoft Dynamics 365).</span><span class="sxs-lookup"><span data-stu-id="f1961-133">For more information about how to create an SPS rate engine, see the following blog post: [Small Parcel Shipping: How to leverage small parcel shipping functionality in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span></span>

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a><span data-ttu-id="f1961-134">Konfigurowanie aparatu stawek w aplikacji Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="f1961-134">Set up a rate engine in Supply Chain Management</span></span>

<span data-ttu-id="f1961-135">Po utworzeniu i wdrożeniu aparatu stawek dla SPS wykonaj poniższe kroki, aby go skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="f1961-135">After you've created and deployed a rate engine for SPS, follow these steps to set it up.</span></span>

1. <span data-ttu-id="f1961-136">Przejdź do obszaru **Zarządzanie transportem \> Konfiguracja \> Aparaty \> Aparat stawki**.</span><span class="sxs-lookup"><span data-stu-id="f1961-136">Go to **Transportation management \> Setup \> Engines \> Rate engine**.</span></span>
1. <span data-ttu-id="f1961-137">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="f1961-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="f1961-138">W nowym wierszu ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="f1961-138">In the new row, set the following fields:</span></span>

    - <span data-ttu-id="f1961-139">**Aparat oceniania** — umożliwia wprowadzenie unikatowej nazwy aparatu stawki.</span><span class="sxs-lookup"><span data-stu-id="f1961-139">**Rating engine** – Enter a unique name for the rate engine.</span></span> <span data-ttu-id="f1961-140">Jeśli używasz aparatu stawek demonstracyjnych, wprowadź *Aparat stawek demonstracyjnych*.</span><span class="sxs-lookup"><span data-stu-id="f1961-140">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="f1961-141">**Nazwa** — umożliwia wprowadzenie krótkiego opisu aparatu stawki.</span><span class="sxs-lookup"><span data-stu-id="f1961-141">**Name** – Enter a short description of the rate engine.</span></span> <span data-ttu-id="f1961-142">Jeśli używasz aparatu stawek demonstracyjnych, wprowadź *Aparat stawek demonstracyjnych*.</span><span class="sxs-lookup"><span data-stu-id="f1961-142">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="f1961-143">**Identyfikator metadanych oceniania** — wybierz podstawę, która ma być używana do obliczenia stawki.</span><span class="sxs-lookup"><span data-stu-id="f1961-143">**Rating metadata ID** – Select the basis that should be used to calculate your rate.</span></span> <span data-ttu-id="f1961-144">Na przykład stawka może zostać obliczona na podstawie odległości.</span><span class="sxs-lookup"><span data-stu-id="f1961-144">For example, your rate might be calculated based on distance.</span></span> <span data-ttu-id="f1961-145">Jeśli używasz aparatu stawek demonstracyjnych, możesz pozostawić to pole puste.</span><span class="sxs-lookup"><span data-stu-id="f1961-145">If you're using the demo rate engine, you can leave this field blank.</span></span>
    - <span data-ttu-id="f1961-146">**Zestaw aparatu** — umożliwia wprowadzenie nazwę wdrożonego pliku pakietu DLL.</span><span class="sxs-lookup"><span data-stu-id="f1961-146">**Engine assembly** – Enter the file name of the DLL package that you deployed.</span></span> <span data-ttu-id="f1961-147">Jeśli używasz aparatu stawek demonstracyjnych, wprowadź *TMSSmallParcelShippingEngine.dll*.</span><span class="sxs-lookup"><span data-stu-id="f1961-147">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.dll*.</span></span>
    - <span data-ttu-id="f1961-148">**Klasa aparatu** — wprowadź nazwę klasy, która została ustalona dla aparatu stawki.</span><span class="sxs-lookup"><span data-stu-id="f1961-148">**Engine class** – Enter the class name that was established for your rate engine.</span></span> <span data-ttu-id="f1961-149">Jeśli używasz aparatu stawek demonstracyjnych, wprowadź *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span><span class="sxs-lookup"><span data-stu-id="f1961-149">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="f1961-150">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="f1961-150">Example scenario</span></span>

<span data-ttu-id="f1961-151">W tym przykładowym scenariuszu pokazano, jak skonfigurować funkcję SPS i używać jej po przygotowaniu systemu zgodnie z opisem podanym wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="f1961-151">This example scenario shows how to set up and use SPS after you've prepared your system as described earlier in this topic.</span></span> <span data-ttu-id="f1961-152">W tym scenariuszu jest używany poprzednio wymieniony aparat stawek demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="f1961-152">This scenario uses the previously mentioned demo rate engine.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="f1961-153">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="f1961-153">Make demo data available</span></span>

<span data-ttu-id="f1961-154">Aby pracować z tym scenariuszem przy użyciu określonych pokazowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f1961-154">To work through this scenario by using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="f1961-155">Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="f1961-155">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="f1961-156">Konfiguracja scenariusza</span><span class="sxs-lookup"><span data-stu-id="f1961-156">Set up the scenario</span></span>

<span data-ttu-id="f1961-157">W tym przykładowym scenariuszu musisz mieć przewoźnika demonstracyjnego, grupę przewoźników, zasady pakowania i profil pakowania.</span><span class="sxs-lookup"><span data-stu-id="f1961-157">For this example scenario, you must have a demo carrier, carrier group, packing policy, and packing profile.</span></span> <span data-ttu-id="f1961-158">Poniższe podsekcje wyjaśniają, jak przygotować rekordy wymagane dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="f1961-158">The following subsections explain how to prepare the records that are required for the scenario.</span></span> <span data-ttu-id="f1961-159">W scenariuszu produkcyjnym proces konfiguracji zazwyczaj przypomina proces, który jest tutaj opisany.</span><span class="sxs-lookup"><span data-stu-id="f1961-159">In a production scenario, the setup process typically resembles the process that is described here.</span></span> <span data-ttu-id="f1961-160">Zostaną jednak określone inne wartości.</span><span class="sxs-lookup"><span data-stu-id="f1961-160">However, you will set different values.</span></span>

#### <a name="set-up-carriers"></a><span data-ttu-id="f1961-161">Konfigurowanie przewoźników</span><span class="sxs-lookup"><span data-stu-id="f1961-161">Set up carriers</span></span>

<span data-ttu-id="f1961-162">Wykonaj poniższe kroki, aby skonfigurować przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="f1961-162">Follow these steps to set up a carrier.</span></span>

1. <span data-ttu-id="f1961-163">Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Firmy przewozowe**.</span><span class="sxs-lookup"><span data-stu-id="f1961-163">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="f1961-164">W okienku akcji wybierz opcję **Nowy**, aby dodać przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="f1961-164">On the Action Pane, select **New** to add a carrier.</span></span>
1. <span data-ttu-id="f1961-165">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-165">On the header, set the following values:</span></span>

    - <span data-ttu-id="f1961-166">**Firma przewozowa:** *Przewoźnik pokazowy*</span><span class="sxs-lookup"><span data-stu-id="f1961-166">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f1961-167">**Nazwa:** *Przewoźnik pokazowy*</span><span class="sxs-lookup"><span data-stu-id="f1961-167">**Name:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f1961-168">**Tryb:** *Naziemny*</span><span class="sxs-lookup"><span data-stu-id="f1961-168">**Mode:** *Ground*</span></span>

1. <span data-ttu-id="f1961-169">Na skróconej karcie **Omówienie** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-169">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f1961-170">**Aktywowanie interfejsów firmy przewozowej:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="f1961-170">**Activate shipping carrier:** *Yes*</span></span>
    - <span data-ttu-id="f1961-171">**Aktywowanie oceny przewoźników:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="f1961-171">**Activate carrier rating:** *Yes*</span></span>

1. <span data-ttu-id="f1961-172">Na skróconej karcie **Usługi** wybierz **Nowe**, aby dodać usługę do siatki.</span><span class="sxs-lookup"><span data-stu-id="f1961-172">On the **Services** FastTab, select **New** to add a service to the grid.</span></span>
1. <span data-ttu-id="f1961-173">Dla nowej usługi ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-173">Set the following values for the new service:</span></span>

    - <span data-ttu-id="f1961-174">**Usługa przewozowa:** *Usługa przewoźnika pokazowego*</span><span class="sxs-lookup"><span data-stu-id="f1961-174">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f1961-175">**Nazwa:** *Usługa przewoźnika pokazowego*</span><span class="sxs-lookup"><span data-stu-id="f1961-175">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f1961-176">**Metoda transportu:** *Naziemny*</span><span class="sxs-lookup"><span data-stu-id="f1961-176">**Transportation method:** *Ground*</span></span>

    <span data-ttu-id="f1961-177">W razie potrzeby wprowadź dowolne wartości dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="f1961-177">Enter arbitrary values for all the other fields, as required.</span></span> <span data-ttu-id="f1961-178">(Po zapisaniu nowego rekordu firmy przewozowej zostanie utworzony nowy tryb dostawy, a pole **trybu dostawy** zostanie ustawione automatycznie).</span><span class="sxs-lookup"><span data-stu-id="f1961-178">(When you save the new shipping carrier record, a new mode of delivery will be created, and the **Mode of delivery** field will be set automatically.)</span></span>

1. <span data-ttu-id="f1961-179">Na skróconej karcie **Profile stawek** kliknij opcję **Nowy**, aby dodać profil oceny do siatki.</span><span class="sxs-lookup"><span data-stu-id="f1961-179">On the **Rating profiles** FastTab, select **New** to add a rating profile to the grid.</span></span>
1. <span data-ttu-id="f1961-180">Dla nowego profilu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-180">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="f1961-181">**Profil oceny:** *Usługa przewoźnika pokazowego*</span><span class="sxs-lookup"><span data-stu-id="f1961-181">**Rating profile:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f1961-182">**Nazwa:** *Usługa przewoźnika pokazowego*</span><span class="sxs-lookup"><span data-stu-id="f1961-182">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f1961-183">**Aparat stawki:** *Aparat stawki pokazowej*</span><span class="sxs-lookup"><span data-stu-id="f1961-183">**Rate engine:** *Demo rate engine*</span></span>

    <span data-ttu-id="f1961-184">W razie potrzeby wprowadź dowolne wartości dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="f1961-184">Enter arbitrary values for all the other fields, as required.</span></span>

1. <span data-ttu-id="f1961-185">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f1961-185">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="f1961-186">Aby uzyskać więcej informacji o ustawianiu przewoźników, zobacz [Konfigurowanie firm przewozowych](../transportation/tasks/set-up-shipping-carriers.md).</span><span class="sxs-lookup"><span data-stu-id="f1961-186">For more information about how to set up carriers, see [Set up shipping carriers](../transportation/tasks/set-up-shipping-carriers.md).</span></span>

#### <a name="set-up-carrier-service-accounts"></a><span data-ttu-id="f1961-187">Konfigurowanie kont usług przewozowych</span><span class="sxs-lookup"><span data-stu-id="f1961-187">Set up carrier service accounts</span></span>

<span data-ttu-id="f1961-188">Wykonaj poniższe kroki, aby skonfigurować konto usługi przewozowej.</span><span class="sxs-lookup"><span data-stu-id="f1961-188">Follow these steps to set up a carrier service account.</span></span>

1. <span data-ttu-id="f1961-189">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Ocena \> Konto usługi przewozowej**.</span><span class="sxs-lookup"><span data-stu-id="f1961-189">Go to **Transportation management \> Setup \> Rating \> Carrier service account**.</span></span>
1. <span data-ttu-id="f1961-190">W okienku akcji wybierz opcję **Nowy**, aby dodać konto usługi przewozowej.</span><span class="sxs-lookup"><span data-stu-id="f1961-190">On the Action Pane, select **New** to add a carrier service account.</span></span>
1. <span data-ttu-id="f1961-191">Dla nowego konta ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-191">Set the following values for the new account:</span></span>

    - <span data-ttu-id="f1961-192">**Firma przewozowa:** *Przewoźnik pokazowy*</span><span class="sxs-lookup"><span data-stu-id="f1961-192">**Shipping Carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f1961-193">**Usługa przewozowa:** *Usługa przewoźnika pokazowego*</span><span class="sxs-lookup"><span data-stu-id="f1961-193">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f1961-194">**Numer konta klienta przewoźnika:** numer konta klienta dla przewoźnika używany do weryfikacji i uwierzytelnienia połączenia z firmą przewozową.</span><span class="sxs-lookup"><span data-stu-id="f1961-194">**Carrier customer account number:** The carrier customer account number that is used to verify and authenticate the connection to the shipping carrier.</span></span> <span data-ttu-id="f1961-195">Ta wartość zostanie podana przez przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="f1961-195">Your carrier will provide this value.</span></span> <span data-ttu-id="f1961-196">Jeśli używasz usługi pokazowej, możesz wprowadzić dowolną wartość.</span><span class="sxs-lookup"><span data-stu-id="f1961-196">If you're using the demo service, you can enter an arbitrary value.</span></span>
    - <span data-ttu-id="f1961-197">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="f1961-197">**Site:** *6*</span></span>
    - <span data-ttu-id="f1961-198">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f1961-198">**Warehouse:** *62*</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1961-199">Często wartość **numeru konta klienta dla przewoźnika** jest jedyną wartością wymaganą do uwierzytelnienia połączenia.</span><span class="sxs-lookup"><span data-stu-id="f1961-199">Often, the **Carrier customer account number** value is the only value that is required to authenticate the connection.</span></span> <span data-ttu-id="f1961-200">Jeśli jednak przewoźnik wymaga dodatkowych parametrów uwierzytelniania, organizacja powinna dostosować tę stronę, aby w razie potrzeby dodawać dodatkowe pola.</span><span class="sxs-lookup"><span data-stu-id="f1961-200">However, if your carrier requires additional authentication parameters, your organization should customize this page to add extra fields as appropriate.</span></span>

#### <a name="set-up-a-container-packing-policy"></a><span data-ttu-id="f1961-201">Konfigurowanie zasad pakowania kontenerów</span><span class="sxs-lookup"><span data-stu-id="f1961-201">Set up a container packing policy</span></span>

<span data-ttu-id="f1961-202">Wykonaj poniższe kroki, aby skonfigurować zasady pakowania kontenerów.</span><span class="sxs-lookup"><span data-stu-id="f1961-202">Follow these steps to set up a container packing policy.</span></span>

1. <span data-ttu-id="f1961-203">Jeśli jeszcze nie skonfigurowano definicji drukarki ZPL, skonfiguruj ją za pomocą aplikacji agenta wyboru trasy dokumentów.</span><span class="sxs-lookup"><span data-stu-id="f1961-203">If you haven't already set up a ZPL printer definition, use the Document Routing Agent application to set it up.</span></span> <span data-ttu-id="f1961-204">Aby uzyskać więcej informacji, zobacz [Omówienie drukowania dokumentów](../../fin-ops-core/dev-itpro/analytics/print-documents.md) i pokrewne tematy.</span><span class="sxs-lookup"><span data-stu-id="f1961-204">For more information, see [Document printing overview](../../fin-ops-core/dev-itpro/analytics/print-documents.md) and related topics.</span></span>
1. <span data-ttu-id="f1961-205">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Zasady pakowania kontenera**.</span><span class="sxs-lookup"><span data-stu-id="f1961-205">Go to **Warehouse Management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="f1961-206">W okienku akcji wybierz opcję **Nowy**, aby dodać zasady pakowania kontenerów.</span><span class="sxs-lookup"><span data-stu-id="f1961-206">On the Action Pane, select **New** to add a container packing policy.</span></span>
1. <span data-ttu-id="f1961-207">W nagłówku nowych zasad określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-207">On the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="f1961-208">**Zasady pakowania kontenerów:** *Pokazowe zasady pakowania*</span><span class="sxs-lookup"><span data-stu-id="f1961-208">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="f1961-209">**Opis:** opis zasad</span><span class="sxs-lookup"><span data-stu-id="f1961-209">**Description:** A description of the policy</span></span>

1. <span data-ttu-id="f1961-210">Na skróconej karcie **Omówienie** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-210">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f1961-211">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f1961-211">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f1961-212">**Domyślna lokalizacja wysyłki końcowej:** *Brama dokowa*</span><span class="sxs-lookup"><span data-stu-id="f1961-212">**Default location for final shipment:** *Baydoor*</span></span>
    - <span data-ttu-id="f1961-213">**Jednostka wagi:** *KG*</span><span class="sxs-lookup"><span data-stu-id="f1961-213">**Weight unit:** *KG*</span></span>
    - <span data-ttu-id="f1961-214">**Zasada zamykania kontenera:** *Automatyczne zwalnianie*</span><span class="sxs-lookup"><span data-stu-id="f1961-214">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="f1961-215">**Zasady zwalniania kontenerów:** *Udostępnij w końcowej lokalizacji wysyłki*</span><span class="sxs-lookup"><span data-stu-id="f1961-215">**Container release policy:** *Make available at final shipping location*</span></span>

1. <span data-ttu-id="f1961-216">Na skróconej karcie **Manifest kontenera** możesz ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-216">On the **Container manifest** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f1961-217">**Automatyczny manifest przy zamknięciu kontenera:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="f1961-217">**Automatic manifest at container close:** *Yes*</span></span>
    - <span data-ttu-id="f1961-218">**Wymagania dotyczące manifestu dla kontenera:** *Zarządzanie transportem*</span><span class="sxs-lookup"><span data-stu-id="f1961-218">**Manifest requirements for container:** *Transportation management*</span></span>
    - <span data-ttu-id="f1961-219">**Drukuj zawartość kontenera:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="f1961-219">**Print container contents:** *No*</span></span>

1. <span data-ttu-id="f1961-220">Na skróconej karcie **Drukowanie etykiety przewoźnika** możesz ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-220">On the **Carrier label printing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f1961-221">**Drukuj etykietę wysyłkową kontenera:** *Zawsze*</span><span class="sxs-lookup"><span data-stu-id="f1961-221">**Print container shipping label:** *Always*</span></span>
    - <span data-ttu-id="f1961-222">**Nazwa drukarki:** nazwa drukarki ZPL, która powinna drukować etykiety wysyłkowe</span><span class="sxs-lookup"><span data-stu-id="f1961-222">**Printer name:** The name of the ZPL printer that should print shipping labels</span></span>

#### <a name="set-up-a-packing-profile"></a><span data-ttu-id="f1961-223">Konfigurowanie profilu pakowania</span><span class="sxs-lookup"><span data-stu-id="f1961-223">Set up a packing profile</span></span>

<span data-ttu-id="f1961-224">Wykonaj poniższe kroki, aby skonfigurować profil pakowania.</span><span class="sxs-lookup"><span data-stu-id="f1961-224">Follow these steps to set up a packing profile.</span></span>

1. <span data-ttu-id="f1961-225">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Profile pakowania**.</span><span class="sxs-lookup"><span data-stu-id="f1961-225">Go to **Warehouse Management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="f1961-226">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy profil pakowania do siatki.</span><span class="sxs-lookup"><span data-stu-id="f1961-226">On the Action Pane, select **New** to add a packing profile to the grid.</span></span>
1. <span data-ttu-id="f1961-227">Dla nowego profilu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-227">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="f1961-228">**Identyfikator profilu pakowania:** *Pokazowy profil pakowania*</span><span class="sxs-lookup"><span data-stu-id="f1961-228">**Packing profile ID:** *Demo packing profile*</span></span>
    - <span data-ttu-id="f1961-229">**Opis:** opis profilu</span><span class="sxs-lookup"><span data-stu-id="f1961-229">**Description:** A description of the profile</span></span>
    - <span data-ttu-id="f1961-230">**Zasady pakowania kontenerów:** *Pokazowe zasady pakowania*</span><span class="sxs-lookup"><span data-stu-id="f1961-230">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="f1961-231">**Tryb identyfikatora kontenera:** *Automatyczny*</span><span class="sxs-lookup"><span data-stu-id="f1961-231">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="f1961-232">**Typ kontenera:** *SmallBox*</span><span class="sxs-lookup"><span data-stu-id="f1961-232">**Container type:** *SmallBox*</span></span>

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a><span data-ttu-id="f1961-233">Konfigurowanie klienta do używania przewoźnika SPS</span><span class="sxs-lookup"><span data-stu-id="f1961-233">Set up a customer to use the SPS carrier</span></span>

<span data-ttu-id="f1961-234">Wykonaj następujące kroki, aby skonfigurować klienta do używania utworzonego przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="f1961-234">Follow these steps to set up a customer so that it can use the carrier that you created.</span></span>

1. <span data-ttu-id="f1961-235">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Klienci \> Wszyscy klienci**.</span><span class="sxs-lookup"><span data-stu-id="f1961-235">Go to **Accounts receivable \> customers \> All customers**.</span></span>
1. <span data-ttu-id="f1961-236">W siatce znajdź i zaznacz odbiorcę *US-027*.</span><span class="sxs-lookup"><span data-stu-id="f1961-236">In the grid, find and select customer *US-027*.</span></span>
1. <span data-ttu-id="f1961-237">W okienku akcji na karcie **Ogólne** w grupie **Ustawienia** wybierz opcję **Konta klienta dla przewoźnika**.</span><span class="sxs-lookup"><span data-stu-id="f1961-237">On the Action Pane, on the **General** tab, in the **Set up** group, select **Carrier customer accounts**.</span></span>
1. <span data-ttu-id="f1961-238">Na stronie **Konta klienta dla przewoźnika** w okienku akcji wybierz pozycję **Nowy**, aby dodać konto do siatki.</span><span class="sxs-lookup"><span data-stu-id="f1961-238">On the **Carrier customer accounts** page, on the Action Pane, select **New** to add an account to the grid.</span></span>
1. <span data-ttu-id="f1961-239">Dla nowego konta ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-239">Set the following values for the new account:</span></span>

    - <span data-ttu-id="f1961-240">**Firma przewozowa:** *Przewoźnik pokazowy*</span><span class="sxs-lookup"><span data-stu-id="f1961-240">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f1961-241">**Numer konta klienta dla przewoźnika:** *12345* (ta wartość nie jest ważna w tym scenariuszu, ale zostanie dodana w następnej sekcji).</span><span class="sxs-lookup"><span data-stu-id="f1961-241">**Carrier customer account number:** *12345* (The value isn't important for this scenario, but it will be referred to in the next section.)</span></span>

### <a name="go-through-the-example-scenario"></a><span data-ttu-id="f1961-242">Przejdź przez przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="f1961-242">Go through the example scenario</span></span>

<span data-ttu-id="f1961-243">Po skonfigurowaniu wszystkich przykładowych danych zgodnie z opisem w poprzedniej sekcji można przejść do przykładowego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="f1961-243">After you've set up all the sample data as described in the previous section, you're ready to go through the example scenario.</span></span>

#### <a name="create-a-sales-order-and-process-the-work"></a><span data-ttu-id="f1961-244">Tworzenie zamówienia sprzedaży i przetwarzanie pracy</span><span class="sxs-lookup"><span data-stu-id="f1961-244">Create a sales order and process the work</span></span>

<span data-ttu-id="f1961-245">Aby utworzyć zamówienie sprzedaży, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="f1961-245">Follow these steps to create a sales order.</span></span>

1. <span data-ttu-id="f1961-246">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f1961-246">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="f1961-247">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f1961-247">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="f1961-248">W oknie dialogowym **Utwórz zamówienie sprzedaży** ustaw pole **Konto klienta** na *US-027*.</span><span class="sxs-lookup"><span data-stu-id="f1961-248">In the **Create sales order** dialog box, set the **Customer account** field to *US-027*.</span></span>
1. <span data-ttu-id="f1961-249">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="f1961-249">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="f1961-250">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="f1961-250">The new sales order is opened.</span></span> <span data-ttu-id="f1961-251">Na skróconej karcie **Nagłówek zamówienia sprzedaży** ustaw w polu **Numer konta klienta dla przewoźnika** wartość wcześniej wybraną dla tego klienta (*12345*).</span><span class="sxs-lookup"><span data-stu-id="f1961-251">On the **Sales order header** FastTab, set the **Carrier customer account number** field to the value that you selected for this customer earlier (*12345*).</span></span>
1. <span data-ttu-id="f1961-252">W sekcji **Wiersze zamówienia sprzedaży** dodaj wiersz sprzedaży i ustaw dla niego następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-252">In the **Sales order lines** section, add a sales line, and set the following values for it:</span></span>

    - <span data-ttu-id="f1961-253">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="f1961-253">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="f1961-254">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="f1961-254">**Quantity:** *1*</span></span>
    - <span data-ttu-id="f1961-255">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="f1961-255">**Site:** *6*</span></span>
    - <span data-ttu-id="f1961-256">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f1961-256">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="f1961-257">Przełącz do widoku **nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="f1961-257">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="f1961-258">Na skróconej karcie **Dostawa** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-258">On the **Delivery** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f1961-259">**Firma przewozowa:** *Przewoźnik pokazowy*</span><span class="sxs-lookup"><span data-stu-id="f1961-259">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f1961-260">**Usługa przewozowa:** *Usługa przewoźnika pokazowego*</span><span class="sxs-lookup"><span data-stu-id="f1961-260">**Carrier service:** *Demo carrier service*</span></span>

1. <span data-ttu-id="f1961-261">Przełącz się z powrotem do widoku **Wiersz**.</span><span class="sxs-lookup"><span data-stu-id="f1961-261">Switch back to the **Lines** view.</span></span> <span data-ttu-id="f1961-262">Jeśli zostanie wyświetlony monit o aktualizację trybu dostawy dla wierszy sprzedaży, wybierz przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f1961-262">If you're prompted to update the mode of delivery for the sales lines, select **Yes**.</span></span>
1. <span data-ttu-id="f1961-263">W sekcji **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia, który został wcześniej ustawiony, a następnie wybierz opcję **Zapasy \> Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="f1961-263">In the **Sales order lines** section, select the order line that you set up earlier, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="f1961-264">Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="f1961-264">On the **Reservation** page, select **Reserve lot** to reserve the selected line's full quantity in the warehouse.</span></span>
1. <span data-ttu-id="f1961-265">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f1961-265">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="f1961-266">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="f1961-266">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="f1961-267">Utworzono pracę w celu przeniesienia towarów z lokalizacji pobrania do stacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="f1961-267">Work is created to move items from the picking location to the packing station.</span></span>

1. <span data-ttu-id="f1961-268">W sekcji **Wiersze zamówienia sprzedaży** wybierz opcję **Magazyn \> Szczegóły wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="f1961-268">In the **Sales order lines** section, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="f1961-269">Na stronie **Szczegóły wysyłki** zanotuj identyfikator wysyłki.</span><span class="sxs-lookup"><span data-stu-id="f1961-269">On the **Shipment details** page, make a note of the shipment ID.</span></span> <span data-ttu-id="f1961-270">Będzie on potrzebny przy pakowaniu wysyłki w stacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="f1961-270">You will need it when you pack the pack the shipment at the packing station.</span></span>
1. <span data-ttu-id="f1961-271">Zamknij stronę **Szczegóły wysyłki**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f1961-271">Close the **Shipment details** page to return to the sales order.</span></span>
1. <span data-ttu-id="f1961-272">Zanotuj numer zamówienia sprzedaży, a następnie przejdź do obszaru **Zarządzanie magazynem \> Praca \> Cała praca**.</span><span class="sxs-lookup"><span data-stu-id="f1961-272">Make a note of the sales order number, and then go to **Warehouse management \> Work \> All work**.</span></span>
1. <span data-ttu-id="f1961-273">Użyj numeru zamówienia sprzedaży, aby znaleźć i wybrać pracę utworzoną dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f1961-273">Use the sales order number to find and select the work that was created for the order.</span></span>
1. <span data-ttu-id="f1961-274">W okienku akcji na karcie **Praca** wybierz opcję **Zakończ pracę**.</span><span class="sxs-lookup"><span data-stu-id="f1961-274">On the Action Pane, on the **Work** tab, select **Complete work**.</span></span>
1. <span data-ttu-id="f1961-275">Na stronie **Zakończenie pracy** w polu **Identyfikator użytkownika** wybierz identyfikator użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f1961-275">On the **Work completion** page, in the **User ID** field, select a user ID.</span></span> <span data-ttu-id="f1961-276">Następnie w okienku akcji wybierz pozycję **Weryfikuj pracę**.</span><span class="sxs-lookup"><span data-stu-id="f1961-276">Then, on the Action Pane, select **Validate work**.</span></span>
1. <span data-ttu-id="f1961-277">Jeśli weryfikacja pracy zakończy się pomyślnie, wybierz pozycję **Zakończ pracę** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="f1961-277">If the work passes validation, select **Complete work** on the Action Pane.</span></span>

    <span data-ttu-id="f1961-278">Praca jest oznaczona jako zakończona w celu symulowania ruchu towarów do stacji pakowania.</span><span class="sxs-lookup"><span data-stu-id="f1961-278">The work is marked as completed to simulate the movement of items to the packing station.</span></span>

#### <a name="pack-the-shipment"></a><span data-ttu-id="f1961-279">Pakowanie wysyłki</span><span class="sxs-lookup"><span data-stu-id="f1961-279">Pack the shipment</span></span>

<span data-ttu-id="f1961-280">Aby zapakować wysyłkę, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="f1961-280">Follow these steps to pack the shipment.</span></span>

1. <span data-ttu-id="f1961-281">Przejdź do obszaru **Zarządzanie magazynem \> Ustawienia \> Pracownik** i upewnij się, że Twoje konto użytkownika jest skojarzone z kontem pracownika na potrzeby zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="f1961-281">Go to **Warehouse management \> Setup \> Worker**, and make sure that your user account is associated with a worker account for warehouse management.</span></span>
1. <span data-ttu-id="f1961-282">Przejdź do **Zarządzanie magazynem \> Pobieranie i konteneryzacja \> Pakunek**.</span><span class="sxs-lookup"><span data-stu-id="f1961-282">Go to **Warehouse management \> Picking and containerization \> Pack**.</span></span>
1. <span data-ttu-id="f1961-283">W oknie dialogowym **Wybieranie stacji pakowania** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="f1961-283">In the **Select packing station** dialog box, set the following values:</span></span>

    - <span data-ttu-id="f1961-284">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="f1961-284">**Site:** *6*</span></span>
    - <span data-ttu-id="f1961-285">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="f1961-285">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f1961-286">**Lokalizacja:** *Pakiet*</span><span class="sxs-lookup"><span data-stu-id="f1961-286">**Location:** *Pack*</span></span>
    - <span data-ttu-id="f1961-287">**Identyfikator profilu pakowania:** *Pokazowy profil pakowania*</span><span class="sxs-lookup"><span data-stu-id="f1961-287">**Packing profile ID:** *Demo packing profile*</span></span>

1. <span data-ttu-id="f1961-288">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1961-288">Select **OK**.</span></span>
1. <span data-ttu-id="f1961-289">Zostanie wyświetlona strona **Pakowanie**.</span><span class="sxs-lookup"><span data-stu-id="f1961-289">The **Pack** page appears.</span></span> <span data-ttu-id="f1961-290">W scenariuszu produkcji pracownik zeskanuje numer identyfikacyjny lub identyfikator wysyłki.</span><span class="sxs-lookup"><span data-stu-id="f1961-290">In a production scenario, a worker will scan a license plate or shipment ID.</span></span> <span data-ttu-id="f1961-291">Jednak w tym scenariuszu otwórz stronę **Wszystkie wysyłki** i wyszukaj numer właśnie utworzonej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="f1961-291">However, for this scenario, open the **All shipments** page, and look up the shipment number for the shipment that you just created.</span></span> <span data-ttu-id="f1961-292">Następnie wprowadź tę wartość w polu **Numer identyfikacyjny lub wysyłka** na stronie **Pakowanie**.</span><span class="sxs-lookup"><span data-stu-id="f1961-292">Then enter this value in the **License plate or shipment** field on the **Pack** page.</span></span> <span data-ttu-id="f1961-293">Możesz również wprowadzić identyfikator wysyłki zanotowany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="f1961-293">Alternatively, enter the shipment ID that you made a note of earlier.</span></span>
1. <span data-ttu-id="f1961-294">W okienku akcji wybierz opcję **Nowy kontener**.</span><span class="sxs-lookup"><span data-stu-id="f1961-294">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="f1961-295">Okno dialogowe, które zostanie wyświetlone, zawiera szczegóły dotyczące nowego kontenera.</span><span class="sxs-lookup"><span data-stu-id="f1961-295">The dialog box that appears shows details about the new container.</span></span> <span data-ttu-id="f1961-296">Pozostaw wartości domyślne, a następnie wybierz pozycję **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1961-296">Leave the default values, and then select **OK**.</span></span>
1. <span data-ttu-id="f1961-297">Na stronie **Pakowanie** na skróconej karcie **Pakowanie towarów** w polu **Identyfikator** wybierz pozycję *A0002*, aby zapakować ten towar.</span><span class="sxs-lookup"><span data-stu-id="f1961-297">On the **Pack** page, on the **Item packing** FastTab, in the **Identifier** field, select *A0002* to pack that item.</span></span> <span data-ttu-id="f1961-298">Towar jest dodawany do kontenera.</span><span class="sxs-lookup"><span data-stu-id="f1961-298">The item is added to the container.</span></span>
1. <span data-ttu-id="f1961-299">W okienku akcji wybierz pozycję **Kontenery do wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="f1961-299">On the Action Pane, select **Containers for shipment**.</span></span>

    <span data-ttu-id="f1961-300">Strona **Kontenery do wysyłki**, która zostanie wyświetlona, zawiera wiersz utworzonego właśnie kontenera.</span><span class="sxs-lookup"><span data-stu-id="f1961-300">The **Containers for shipment** page that appears has a row for the container that you just created.</span></span> <span data-ttu-id="f1961-301">Jednak pole **Identyfikator manifestu kontenera** w tym wierszu jest obecnie puste, ponieważ nie odebrano jeszcze etykiety wysyłkowej i numeru śledzenia od przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="f1961-301">However, the **Container manifest ID** field in that row is currently blank, because you haven't yet received the shipping label and tracking number from the carrier.</span></span>

1. <span data-ttu-id="f1961-302">W okienku akcji wybierz opcję **Zamknij kontener**.</span><span class="sxs-lookup"><span data-stu-id="f1961-302">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="f1961-303">W oknie dialogowym **Zamykanie kontenera** ustaw wartość pola **Waga brutto** na *1 kg*, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1961-303">In the **Close container** dialog box, set the **Gross weight** field to *1 kg*, and then select **OK**.</span></span>

    <span data-ttu-id="f1961-304">Etykieta wysyłkowa powinna zostać wydrukowana na wybranej wcześniej drukarce ZPL.</span><span class="sxs-lookup"><span data-stu-id="f1961-304">The shipping label should now be printed on the ZPL printer that you selected earlier.</span></span> <span data-ttu-id="f1961-305">Powinna ona przypominać następujący przykład.</span><span class="sxs-lookup"><span data-stu-id="f1961-305">It should resemble the following example.</span></span>

    <span data-ttu-id="f1961-306">![Przykładowa etykieta wysyłkowa](media/sps-label-example.png "Przykładowa etykieta wysyłkowa")</span><span class="sxs-lookup"><span data-stu-id="f1961-306">![Example shipping label](media/sps-label-example.png "Example shipping label")</span></span>

1. <span data-ttu-id="f1961-307">Zwróć uwagę, że wartości pól **Identyfikator manifestu kontenera** oraz **Suma frachtu** zostały dodane jako otrzymane od przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="f1961-307">Notice that the **Container manifest ID** and **Total freight** values have been added as received from the carrier.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]