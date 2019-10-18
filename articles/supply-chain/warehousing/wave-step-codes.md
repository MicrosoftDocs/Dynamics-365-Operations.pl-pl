---
title: Kody kroku grupy czynności
description: Ten temat zawiera przegląd kodów etapów grupy czynności oraz sposobu ich używania.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992364"
---
# <a name="wave-step-codes"></a><span data-ttu-id="0f95e-103">Kody kroku grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-103">Wave step codes</span></span>

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a><span data-ttu-id="0f95e-104">Kody etapów grupy czynności — informacje</span><span class="sxs-lookup"><span data-stu-id="0f95e-104">About wave step codes</span></span>

<span data-ttu-id="0f95e-105">Kody etapów grupy czynności są kodami, które użytkownicy mogą konfigurować i stosować w celu łączenia określonych wystąpień metod grupy czynności z odpowiednim szablonem.</span><span class="sxs-lookup"><span data-stu-id="0f95e-105">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="0f95e-106">Szablony te obejmują szablony uzupełniania, konteneryzacji, drukowania etykiet, kompilowania i sortowania.</span><span class="sxs-lookup"><span data-stu-id="0f95e-106">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="0f95e-107">Jeśli nie są używane kody etapów grupy czynności, użytkownicy muszą wprowadzać dowolny tekst, aby odwoływać się do określonego szablonu z instancji metody Wave.</span><span class="sxs-lookup"><span data-stu-id="0f95e-107">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="0f95e-108">Tekst niezależny jest podatny na błędy, ponieważ użytkownicy muszą upewnić się, że tekst etapu grupy czynności dodawany dla konkretnej metody w szablonie grupy czynności jest dokładnie zgodny z tekstem kroku grupy czynności w szablonie docelowym.</span><span class="sxs-lookup"><span data-stu-id="0f95e-108">Free text is prone to error, because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="0f95e-109">Kody etapów grupy czynności dla konkretnego typu kroku są konfigurowane na osobnej stronie.</span><span class="sxs-lookup"><span data-stu-id="0f95e-109">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="0f95e-110">Dla każdej instancji metody etapów grupy czynności, która wymaga kodu kroku grupy czynności, należy wybrać kod etapu grupy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="0f95e-110">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="0f95e-111">Wybór na liście rozwijanej zastępuje wprowadzanie tekstu swobodnego i pomaga zmniejszyć ryzyko i wpływ błędu człowieka.</span><span class="sxs-lookup"><span data-stu-id="0f95e-111">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="0f95e-112">Kody ustawień służą do łączenia metody kroku grupy czynności w szablonie grupy czynności z docelowym szablonem metody.</span><span class="sxs-lookup"><span data-stu-id="0f95e-112">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="0f95e-113">Użycie funkcji kodów etapów grupy czynności jest opcjonalne, a dla każdej firmy.</span><span class="sxs-lookup"><span data-stu-id="0f95e-113">Use of the wave step codes feature is optional, and uptake is per legal entity.</span></span> <span data-ttu-id="0f95e-114">Dlatego jeśli określona firma używa tej funkcji, wszystkie istniejące kody kroków grupy w tej firmie zostaną uaktualnione do nowej struktury.</span><span class="sxs-lookup"><span data-stu-id="0f95e-114">Therefore, if a specific legal entity uses the feature, all existing wave step codes in that legal entity are upgraded to the new structure.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="0f95e-115">Pokaz instalacji</span><span class="sxs-lookup"><span data-stu-id="0f95e-115">Setup demo</span></span> 

<span data-ttu-id="0f95e-116">W tym pokazie trzeba mieć zainstalowane dane demonstracyjne oraz musi być używana wersja demonstracyjna **USMF** danych firmy.</span><span class="sxs-lookup"><span data-stu-id="0f95e-116">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="0f95e-117">Włącz kody kroku grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-117">Enable wave step codes</span></span>

<span data-ttu-id="0f95e-118">Aby włączyć funkcję kodów etapów grupy czynności, należy wykonać poniższe kroki</span><span class="sxs-lookup"><span data-stu-id="0f95e-118">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="0f95e-119">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="0f95e-119">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
2. <span data-ttu-id="0f95e-120">Na karcie **Ogólne** na skróconej karcie **Zatwierdzenie dostawcy** dla opcji **Przetwarzanie grupy czynności** wybierz ustawienie **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0f95e-120">On the **General** tab, on the **Wave processing** FastTab, set the **Enable wave step codes** option to **Yes**.</span></span>

<span data-ttu-id="0f95e-121">Wszystkie istniejące teksty niezależne krokami wyjścia są uaktualniane do nowej struktury.</span><span class="sxs-lookup"><span data-stu-id="0f95e-121">All existing wave step free texts are upgraded to the new structure.</span></span> <span data-ttu-id="0f95e-122">Po ukończeniu tego uaktualnienia dla firmy nie jest już dostępna opcja **Włącz kody etapów grupy czynności** na stronie **parametrów zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="0f95e-122">After this upgrade is completed for a legal entity, the **Enable wave step codes** option is no longer available on the **Warehouse management parameters** page.</span></span>

<span data-ttu-id="0f95e-123">Sprawdzanie poprawności zostało przeprowadzone podczas uaktualniania systemu, a Jeśli uaktualnienie nie powiedzie się, zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="0f95e-123">Validations are done during the upgrade, and if the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="0f95e-124">Uaktualnienie może zakończyć się niepowodzeniem z powodu następujących konfliktów:</span><span class="sxs-lookup"><span data-stu-id="0f95e-124">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="0f95e-125">Istnieją zduplikowane teksty etapów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-125">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="0f95e-126">Dostosowania jest możliwe.</span><span class="sxs-lookup"><span data-stu-id="0f95e-126">Customizations exist.</span></span>
- <span data-ttu-id="0f95e-127">Tekst niezależny krok fazy wyjścia skojarzony z wystąpieniem metody kroku grupy czynności nie pasuje do oczekiwanego typu szablonu.</span><span class="sxs-lookup"><span data-stu-id="0f95e-127">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="0f95e-128">Po rozwiązaniu wszelkich konfliktów, które zostaną zidentyfikowane podczas sprawdzania poprawności, można ponownie uruchomić proces uaktualniania.</span><span class="sxs-lookup"><span data-stu-id="0f95e-128">After you've resolved any conflicts that are identified during the validations, you can rerun the upgrade process.</span></span>

<span data-ttu-id="0f95e-129">Po pomyślnym uaktualnieniu systemu będzie dostępna strona **Kody etapów grupy czynności** (**Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Kody etapów grupy czynności**).</span><span class="sxs-lookup"><span data-stu-id="0f95e-129">When the upgrade succeeds, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="0f95e-130">Ta strona zawiera listę kodów etapów grupy czynności, które zostały uaktualnione po włączeniu funkcji kodów etapów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-130">This page lists the wave step codes that were upgraded when the wave step codes feature was turned on.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="0f95e-131">Tworzenie nowych kodów etapów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-131">Create new wave step codes</span></span>

<span data-ttu-id="0f95e-132">Do tworzenia i usuwania **kodów etapów grupy czynności** służą strony kody etapów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-132">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="0f95e-133">Każdy nowy kod kroku grupy czynności i skojarzony z nim identyfikator musi być unikatowy we wszystkich typach etapów grupy czynności i musi być zdefiniowany dla konkretnego typu kroku grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-133">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="0f95e-134">Zastosuj kody etapów grupy czynności — informacje</span><span class="sxs-lookup"><span data-stu-id="0f95e-134">Apply wave step codes</span></span>

<span data-ttu-id="0f95e-135">Po zdefiniowaniu odpowiednich kodów etapów można je stosować do metod procesu typu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="0f95e-135">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="0f95e-136">Aby zastosować kody etapów grupy czynności, należy przejść do odpowiedniego szablonu docelowego.</span><span class="sxs-lookup"><span data-stu-id="0f95e-136">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="0f95e-137">Oto szablony docelowe, dla których mają być wskazywane kody etapów grupy czynności:</span><span class="sxs-lookup"><span data-stu-id="0f95e-137">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="0f95e-138">**Szablony uzupełniania zapasów:** Wybierz kolejno opcje Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="0f95e-138">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="0f95e-139">**Ładowanie szablonów kompilacji:** Zarządzanie magazynem \> Ustawienia \> Ładowanie \> Ładowanie szablonów kompilacji</span><span class="sxs-lookup"><span data-stu-id="0f95e-139">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="0f95e-140">**Sortowanie szablonów:** zarządzania magazynem \> Ustawienia \> Pakowanie \> Szablony sortowania wychodzącego opakowań</span><span class="sxs-lookup"><span data-stu-id="0f95e-140">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="0f95e-141">**Szablony kontenerów:** Wybierz kolejno opcje Zarządzanie magazynem \> Ustawienia \> Kontenery \> Szablony kompilacji kontenerów</span><span class="sxs-lookup"><span data-stu-id="0f95e-141">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="0f95e-142">**Szablony drukowania etykiet:** zarządzanie magazynem \> ustawienia \> Wybór trasy dokumentów \> szablony etykiet grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-142">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="0f95e-143">Szablony z tej listy są stosowane, gdy odwołują się się do metody procesu grupy czynności wybranej w szablonie grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-143">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="0f95e-144">Jeśli kod kroku grupy czynności dla metody procesu Wave w szablonie grupy czynności jest zgodny z kodem kroku grupy czynności w jednym z typów szablonów, jest stosowany szablon.</span><span class="sxs-lookup"><span data-stu-id="0f95e-144">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="0f95e-145">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="0f95e-145">Sample scenario</span></span>

<span data-ttu-id="0f95e-146">Poniższa procedura pomaga zagwarantować, że utworzony szablon uzupełnienia zapasów będzie stosowany do szablonu grupy czynności</span><span class="sxs-lookup"><span data-stu-id="0f95e-146">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="0f95e-147">Przejdź do **zarządzanie magazynem \> ustawienia \> grupy czynności \> kody grup czynności** i utwórz kod kroku grupy czynności dla typu **uzupełnienia**.</span><span class="sxs-lookup"><span data-stu-id="0f95e-147">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="0f95e-148">Wybierz **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów** i stwórz szablon.</span><span class="sxs-lookup"><span data-stu-id="0f95e-148">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="0f95e-149">W szablonie uzupełnienia wybierz kod kroku grupy czynności, który został utworzony dla typu **uzupełnienia**.</span><span class="sxs-lookup"><span data-stu-id="0f95e-149">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="0f95e-150">Przejdź do **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grup czynności** a następnie wybierz szablon grupy czynności, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="0f95e-150">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="0f95e-151">W szablonie **metody** na skróconej karcie wybierz metodę **uzupełniania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="0f95e-151">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="0f95e-152">W **Kod czynności grupowych** wybierz kod kroku grupy czynności, który został utworzony dla typu szblonu uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="0f95e-152">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>
