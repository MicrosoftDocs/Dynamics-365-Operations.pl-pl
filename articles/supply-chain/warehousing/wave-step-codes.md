---
title: Kody kroku grupy czynności
description: Ten temat zawiera przegląd kodów etapów grupy czynności oraz sposobu ich używania.
author: josaw1
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveStepCode, WHSReplenishmentTemplates, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f44d500d58dffb37b27d230b0633336eb87996a6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838065"
---
# <a name="wave-step-codes"></a><span data-ttu-id="1f488-103">Kody kroku grupy czynności</span><span class="sxs-lookup"><span data-stu-id="1f488-103">Wave step codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f488-104">Kody etapów grupy czynności są kodami, które użytkownicy mogą konfigurować i stosować w celu łączenia określonych wystąpień metod grupy czynności z odpowiednim szablonem.</span><span class="sxs-lookup"><span data-stu-id="1f488-104">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="1f488-105">Szablony te obejmują szablony uzupełniania, konteneryzacji, drukowania etykiet, kompilowania i sortowania.</span><span class="sxs-lookup"><span data-stu-id="1f488-105">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="1f488-106">Jeśli nie są używane kody etapów grupy czynności, użytkownicy muszą wprowadzać dowolny tekst, aby odwoływać się do określonego szablonu z instancji metody Wave.</span><span class="sxs-lookup"><span data-stu-id="1f488-106">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="1f488-107">Tekst niezależny jest podatny na błędy, ponieważ użytkownicy muszą upewnić się, że tekst etapu grupy czynności dodawany dla konkretnej metody w szablonie grupy czynności jest dokładnie zgodny z tekstem kroku grupy czynności w szablonie docelowym.</span><span class="sxs-lookup"><span data-stu-id="1f488-107">Free text is prone to errors because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="1f488-108">Kody etapów grupy czynności dla konkretnego typu kroku są konfigurowane na osobnej stronie.</span><span class="sxs-lookup"><span data-stu-id="1f488-108">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="1f488-109">Dla każdej instancji metody etapów grupy czynności, która wymaga kodu kroku grupy czynności, należy wybrać kod etapu grupy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="1f488-109">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="1f488-110">Wybór na liście rozwijanej zastępuje wprowadzanie tekstu swobodnego i pomaga zmniejszyć ryzyko i wpływ błędu człowieka.</span><span class="sxs-lookup"><span data-stu-id="1f488-110">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="1f488-111">Kody ustawień służą do łączenia metody kroku grupy czynności w szablonie grupy czynności z docelowym szablonem metody.</span><span class="sxs-lookup"><span data-stu-id="1f488-111">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="1f488-112">Użycie funkcji kodów kroków grupy czynności jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="1f488-112">Use of the wave step codes feature is optional.</span></span> <span data-ttu-id="1f488-113">Jest ona włączona dla całej organizacji dla wszystkich firm.</span><span class="sxs-lookup"><span data-stu-id="1f488-113">It is enabled organization-wide for all legal entities.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="1f488-114">Pokaz instalacji</span><span class="sxs-lookup"><span data-stu-id="1f488-114">Setup demo</span></span> 

<span data-ttu-id="1f488-115">W tym pokazie trzeba mieć zainstalowane dane demonstracyjne oraz musi być używana wersja demonstracyjna **USMF** danych firmy.</span><span class="sxs-lookup"><span data-stu-id="1f488-115">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="1f488-116">Włącz kody kroku grupy czynności</span><span class="sxs-lookup"><span data-stu-id="1f488-116">Enable wave step codes</span></span>

<span data-ttu-id="1f488-117">Aby włączyć funkcję kodów etapów grupy czynności, należy wykonać poniższe kroki</span><span class="sxs-lookup"><span data-stu-id="1f488-117">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="1f488-118">Przejdź do obszaru **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="1f488-118">Go to **Feature Management**.</span></span>
2. <span data-ttu-id="1f488-119">Wybierz opcję włączenia funkcji o nazwie **Kod kroku grupy czynności w całej organizacji**.</span><span class="sxs-lookup"><span data-stu-id="1f488-119">Select to enable the feature called **Organization-wide Wave Step Code**.</span></span>

<span data-ttu-id="1f488-120">Wszystkie istniejące teksty niezależne kroków grupy czynności we wszystkich firmach są uaktualniane do nowej struktury.</span><span class="sxs-lookup"><span data-stu-id="1f488-120">All existing wave step free texts in all legal entities are upgraded to the new structure.</span></span> <span data-ttu-id="1f488-121">Po ukończeniu tego uaktualniania dla wszystkich firm funkcja jest włączona.</span><span class="sxs-lookup"><span data-stu-id="1f488-121">After this upgrade is completed for all legal entities, then the feature is enabled.</span></span> <span data-ttu-id="1f488-122">Jeśli nie można włączyć tej funkcji dla co najmniej jednej firmy, funkcja nie jest włączona dla żadnych firm.</span><span class="sxs-lookup"><span data-stu-id="1f488-122">If the feature cannot be enabled for one or more legal entities, then the feature is not enabled for any legal entities.</span></span>

<span data-ttu-id="1f488-123">Podczas włączania weryfikacje są wykonywane w trakcie uaktualniania danych.</span><span class="sxs-lookup"><span data-stu-id="1f488-123">During the enablement, validations are done during the data upgrade.</span></span> <span data-ttu-id="1f488-124">Jeśli uaktualnienie nie powiedzie się, zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="1f488-124">If the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="1f488-125">Uaktualnienie może zakończyć się niepowodzeniem z powodu następujących konfliktów:</span><span class="sxs-lookup"><span data-stu-id="1f488-125">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="1f488-126">Istnieją zduplikowane teksty etapów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="1f488-126">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="1f488-127">Dostosowania jest możliwe.</span><span class="sxs-lookup"><span data-stu-id="1f488-127">Customizations exist.</span></span>
- <span data-ttu-id="1f488-128">Tekst niezależny krok fazy wyjścia skojarzony z wystąpieniem metody kroku grupy czynności nie pasuje do oczekiwanego typu szablonu.</span><span class="sxs-lookup"><span data-stu-id="1f488-128">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="1f488-129">Po rozwiązaniu wszelkich konfliktów, które zostaną zidentyfikowane podczas weryfikacji, można ponownie spróbować włączyć funkcję.</span><span class="sxs-lookup"><span data-stu-id="1f488-129">After you've resolved any conflicts that are identified during the validations, you can retry to enable the feature.</span></span>

<span data-ttu-id="1f488-130">Po włączeniu funkcji będzie dostępna strona **Kody etapów grupy czynności** (**Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Kody etapów grupy czynności**).</span><span class="sxs-lookup"><span data-stu-id="1f488-130">When the feature has been enabled, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="1f488-131">Ta strona zawiera listę kodów etapów grupy czynności, które zostały uaktualnione po włączeniu funkcji kodów kroków grupy czynności w całej organizacji.</span><span class="sxs-lookup"><span data-stu-id="1f488-131">This page lists the wave step codes that were upgraded when the Organization-wide Wave Step Code feature was enabled.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="1f488-132">Tworzenie nowych kodów etapów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="1f488-132">Create new wave step codes</span></span>

<span data-ttu-id="1f488-133">Do tworzenia i usuwania **kodów etapów grupy czynności** służą strony kody etapów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="1f488-133">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="1f488-134">Każdy nowy kod kroku grupy czynności i skojarzony z nim identyfikator musi być unikatowy we wszystkich typach etapów grupy czynności i musi być zdefiniowany dla konkretnego typu kroku grupy czynności</span><span class="sxs-lookup"><span data-stu-id="1f488-134">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="1f488-135">Zastosuj kody etapów grupy czynności — informacje</span><span class="sxs-lookup"><span data-stu-id="1f488-135">Apply wave step codes</span></span>

<span data-ttu-id="1f488-136">Po zdefiniowaniu odpowiednich kodów etapów można je stosować do metod procesu typu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="1f488-136">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="1f488-137">Aby zastosować kody etapów grupy czynności, należy przejść do odpowiedniego szablonu docelowego.</span><span class="sxs-lookup"><span data-stu-id="1f488-137">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="1f488-138">Oto szablony docelowe, dla których mają być wskazywane kody etapów grupy czynności:</span><span class="sxs-lookup"><span data-stu-id="1f488-138">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="1f488-139">**Szablony uzupełniania zapasów:** Wybierz kolejno opcje Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="1f488-139">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="1f488-140">**Ładowanie szablonów kompilacji:** Zarządzanie magazynem \> Ustawienia \> Ładowanie \> Ładowanie szablonów kompilacji</span><span class="sxs-lookup"><span data-stu-id="1f488-140">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="1f488-141">**Sortowanie szablonów:** zarządzania magazynem \> Ustawienia \> Pakowanie \> Szablony sortowania wychodzącego opakowań</span><span class="sxs-lookup"><span data-stu-id="1f488-141">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="1f488-142">**Szablony kontenerów:** Wybierz kolejno opcje Zarządzanie magazynem \> Ustawienia \> Kontenery \> Szablony kompilacji kontenerów</span><span class="sxs-lookup"><span data-stu-id="1f488-142">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="1f488-143">**Szablony drukowania etykiet:** zarządzanie magazynem \> ustawienia \> Wybór trasy dokumentów \> szablony etykiet grupy czynności</span><span class="sxs-lookup"><span data-stu-id="1f488-143">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="1f488-144">Szablony z tej listy są stosowane, gdy odwołują się się do metody procesu grupy czynności wybranej w szablonie grupy czynności</span><span class="sxs-lookup"><span data-stu-id="1f488-144">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="1f488-145">Jeśli kod kroku grupy czynności dla metody procesu Wave w szablonie grupy czynności jest zgodny z kodem kroku grupy czynności w jednym z typów szablonów, jest stosowany szablon.</span><span class="sxs-lookup"><span data-stu-id="1f488-145">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="1f488-146">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="1f488-146">Sample scenario</span></span>

<span data-ttu-id="1f488-147">Poniższa procedura pomaga zagwarantować, że utworzony szablon uzupełnienia zapasów będzie stosowany do szablonu grupy czynności</span><span class="sxs-lookup"><span data-stu-id="1f488-147">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="1f488-148">Przejdź do **zarządzanie magazynem \> ustawienia \> grupy czynności \> kody grup czynności** i utwórz kod kroku grupy czynności dla typu **uzupełnienia**.</span><span class="sxs-lookup"><span data-stu-id="1f488-148">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="1f488-149">Wybierz **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów** i stwórz szablon.</span><span class="sxs-lookup"><span data-stu-id="1f488-149">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="1f488-150">W szablonie uzupełnienia wybierz kod kroku grupy czynności, który został utworzony dla typu **uzupełnienia**.</span><span class="sxs-lookup"><span data-stu-id="1f488-150">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="1f488-151">Przejdź do **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grup czynności** a następnie wybierz szablon grupy czynności, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="1f488-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="1f488-152">W szablonie **metody** na skróconej karcie wybierz metodę **uzupełniania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="1f488-152">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="1f488-153">W **Kod czynności grupowych** wybierz kod kroku grupy czynności, który został utworzony dla typu szblonu uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="1f488-153">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>

<span data-ttu-id="1f488-154">Wykonaj następujące kroki dla każdej firmy.</span><span class="sxs-lookup"><span data-stu-id="1f488-154">You perform these steps for each legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]