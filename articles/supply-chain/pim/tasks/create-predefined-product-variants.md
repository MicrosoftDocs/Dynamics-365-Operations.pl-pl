---
title: Tworzenie wstępnie zdefiniowanych wariantów produktu
description: Ta procedura prowadzi przez proces tworzenia wariantów produktu dla produktu głównego przy użyciu kombinacji wymiarów produktu.
author: t-benebo
manager: tfehr
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acd2e3f1464dfed09ee24764270b06970b747d7c
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938209"
---
# <a name="predefined-product-variants"></a><span data-ttu-id="0994b-103">Wstępnie zdefiniowane warianty produktu</span><span class="sxs-lookup"><span data-stu-id="0994b-103">Predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a><span data-ttu-id="0994b-104">Przykładowy scenariusz: tworzenie wstępnie zdefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="0994b-104">Example scenario: Create predefined product variants</span></span>

<span data-ttu-id="0994b-105">Ten przykładowy scenariusz pokazuje sposób tworzenia wariantów produktu dla produktu głównego przy użyciu kombinacji wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="0994b-105">This example scenario shows how to create product variants for a product master using a combinations of product dimensions.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="0994b-106">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="0994b-106">Make demo data available</span></span>

<span data-ttu-id="0994b-107">W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma *USMF*, aby móc użyć sugerowanych w przykładzie wartości.</span><span class="sxs-lookup"><span data-stu-id="0994b-107">To follow this scenario using the values suggested here, you must have demo data installed, and you must select the *USMF* legal entity.</span></span>

### <a name="step-1-create-a-product-master"></a><span data-ttu-id="0994b-108">Krok 1: tworzenie produktu głównego</span><span class="sxs-lookup"><span data-stu-id="0994b-108">Step 1: Create a product master</span></span>

<span data-ttu-id="0994b-109">Aby utworzyć produkt główny:</span><span class="sxs-lookup"><span data-stu-id="0994b-109">To create a product master:</span></span>

1. <span data-ttu-id="0994b-110">Wybierz kolejno opcje **Zarządzanie informacjami o produktach > Produkty > Produkty główne**.</span><span class="sxs-lookup"><span data-stu-id="0994b-110">Go to **Product information management > Products > Product masters**.</span></span>
1. <span data-ttu-id="0994b-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0994b-111">Select **New**.</span></span>
1. <span data-ttu-id="0994b-112">Jeśli pole **Numer produktu** jeszcze nie zawiera numeru, wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="0994b-112">If the **Product number** field doesn't already show a number, then enter a value.</span></span> <span data-ttu-id="0994b-113">Ten krok jest wymagany tylko wtedy, jeśli żadna sekwencja numerów nie została skonfigurowana w tym polu.</span><span class="sxs-lookup"><span data-stu-id="0994b-113">This is only required if no number sequence has been set for this field.</span></span>
1. <span data-ttu-id="0994b-114">W polu **Nazwa produktu** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="0994b-114">Enter a name in the **Product name** field.</span></span>
1. <span data-ttu-id="0994b-115">W polu **Grupa wymiarów produktu** wybierz grupę wymiarów produktu *SizeCol* (Rozmiar i Kolor).</span><span class="sxs-lookup"><span data-stu-id="0994b-115">In the **Product dimension group** field, select the product dimension group *SizeCol* (Size and Color).</span></span>
1. <span data-ttu-id="0994b-116">Wybierz przycisk **OK**, aby utworzyć i otworzyć nowy produkt główny.</span><span class="sxs-lookup"><span data-stu-id="0994b-116">Select **OK** to create and open the new product master.</span></span>

### <a name="step-2-add-product-dimensions"></a><span data-ttu-id="0994b-117">Krok 2: Dodawanie wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="0994b-117">Step 2: Add product dimensions</span></span>

<span data-ttu-id="0994b-118">W tym przykładzie pokazano, jak ręcznie wprowadzić wymiary produktu.</span><span class="sxs-lookup"><span data-stu-id="0994b-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="0994b-119">Można także wybrać grupę rozmiaru, koloru lub stylu zawierającą wartości wymiarów produktu, których chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="0994b-119">You can also choose to select a size, color, or style group that includes the product dimension values you want to use.</span></span>

<span data-ttu-id="0994b-120">Aby dodać wymiary produktu:</span><span class="sxs-lookup"><span data-stu-id="0994b-120">To add product dimensions:</span></span>

1. <span data-ttu-id="0994b-121">Gdy nowy produkt główny jest nadal otwarty, wybierz opcję **Wymiary produktu** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="0994b-121">With your new product master still open, select **Product dimensions** on the Action Pane.</span></span>
1. <span data-ttu-id="0994b-122">Otwórz kartę **Rozmiar** i wybierz pozycję **Nowy** na pasku narzędzi, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="0994b-122">Open the **Size** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="0994b-123">Dla nowego wiersza wprowadź następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="0994b-123">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="0994b-124">**Rozmiar:** wybierz wartość rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="0994b-124">**Size:** Select a size value.</span></span>
    - <span data-ttu-id="0994b-125">**Nazwa**: wprowadź nazwę rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="0994b-125">**Name:** Enter a name for the size.</span></span>
1. <span data-ttu-id="0994b-126">Wybierz pozycję **Nowy** na pasku narzędzi i dodaj drugi rozmiar do siatki z nową **nazwą** i **rozmiarem**.</span><span class="sxs-lookup"><span data-stu-id="0994b-126">Select **New** on the toolbar and add a second size to the grid with a new **Size** and **Name**.</span></span>
1. <span data-ttu-id="0994b-127">Otwórz kartę **Kolory** i wybierz pozycję **Nowy** na pasku narzędzi, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="0994b-127">Open the **Colors** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="0994b-128">Dla nowego wiersza wprowadź następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="0994b-128">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="0994b-129">**Kolor:** wybierz wartość koloru.</span><span class="sxs-lookup"><span data-stu-id="0994b-129">**Color:** Select a color value.</span></span>
    - <span data-ttu-id="0994b-130">**Nazwa**: wprowadź nazwę koloru.</span><span class="sxs-lookup"><span data-stu-id="0994b-130">**Name:** Enter a name for the color.</span></span>
1. <span data-ttu-id="0994b-131">Wybierz pozycję **Nowy** na pasku narzędzi i dodaj drugi kolor do siatki z nowym **kolorem** i **rozmiarem**.</span><span class="sxs-lookup"><span data-stu-id="0994b-131">Select **New** on the toolbar and add a second color to the grid with a new **Color** and **Name**.</span></span>
1. <span data-ttu-id="0994b-132">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0994b-132">Select **Save**.</span></span>
1. <span data-ttu-id="0994b-133">Zamknij stronę, aby powrócić do nowego produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="0994b-133">Close the page to return to your new product master.</span></span>

### <a name="step-3-generate-product-variants"></a><span data-ttu-id="0994b-134">Krok 3: generowanie wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="0994b-134">Step 3: Generate product variants</span></span>

> [!NOTE]
> <span data-ttu-id="0994b-135">W tej sekcji opisano sposób generowania wariantów produktu, gdy funkcja *Ulepszenia strony wariantów sugestii* nie jest włączona.</span><span class="sxs-lookup"><span data-stu-id="0994b-135">This section describes how to generate product variants when the *Variant suggestions page improvements* feature isn't enabled.</span></span> <span data-ttu-id="0994b-136">W następnej sekcji opisano, jak generować warianty produktów, gdy ta funkcja jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="0994b-136">See the next section for details about how to generate product variants when that feature is available.</span></span>

<span data-ttu-id="0994b-137">Aby generować warianty produktu:</span><span class="sxs-lookup"><span data-stu-id="0994b-137">To generate product variants:</span></span>

1. <span data-ttu-id="0994b-138">Gdy nowy produkt główny jest nadal otwarty, wybierz opcję **Warianty produktu** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="0994b-138">With your new product master still open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="0994b-139">W okienku akcji wybierz pozycję **Sugestie wariantów**.</span><span class="sxs-lookup"><span data-stu-id="0994b-139">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="0994b-140">System wygeneruje listę ze wszystkimi możliwymi kombinacjami rozmiarów i kolorów zdefiniowanymi dla produktu.</span><span class="sxs-lookup"><span data-stu-id="0994b-140">The system generates a list with all possible combinations of the sizes and colors you defined for the product.</span></span> <span data-ttu-id="0994b-141">Wybierz opcję **Zaznacz wszystko** na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="0994b-141">Select **Select all** on the toolbar.</span></span>
    - <span data-ttu-id="0994b-142">W tym przykładzie wybierzesz wszystkie możliwe warianty.</span><span class="sxs-lookup"><span data-stu-id="0994b-142">In this example, select all of the possible variants.</span></span> <span data-ttu-id="0994b-143">Aby użyć tylko podzbioru możliwych kombinacji wymiarów produktu, należy zaznaczyć tylko wymagane pola wyboru.</span><span class="sxs-lookup"><span data-stu-id="0994b-143">If you only want to use a subset of the possible product dimension combinations, select only the required check boxes as needed.</span></span>  
1. <span data-ttu-id="0994b-144">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="0994b-144">Select **Create**.</span></span>
1. <span data-ttu-id="0994b-145">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0994b-145">Select **Save**.</span></span>

## <a name="improved-variant-suggestions"></a><span data-ttu-id="0994b-146">Ulepszone sugestie wariantów</span><span class="sxs-lookup"><span data-stu-id="0994b-146">Improved variant suggestions</span></span>

[!INCLUDE [preview-banner-section](../../../includes/preview-banner-section.md)]

<span data-ttu-id="0994b-147">Funkcja *Ulepszenia strony sugestii wariantów* usprawnia stronę **Sugestie wariantów**, aby rozwiązać problem z wydajnością i użytecznością w firmach, które mają wiele kombinacji wymiarów produktów.</span><span class="sxs-lookup"><span data-stu-id="0994b-147">The *Variant suggestions page improvements* feature improves the **Variant suggestions** page to address performance and usability issues for companies that have a high number of product dimension combinations.</span></span> <span data-ttu-id="0994b-148">Rozszerzony proces wybierania wartości wymiarów produktu, dla których mają być generowane sugestie wariantów, ułatwia identyfikowanie i zwalnianie odpowiedniego zestawu wariantów produktów.</span><span class="sxs-lookup"><span data-stu-id="0994b-148">The enhanced process for selecting the product dimension values for which to generate variant suggestions makes it faster and easier to identify and release the relevant set of product variants.</span></span>

<span data-ttu-id="0994b-149">Ta funkcja dodaje następujące ulepszenia:</span><span class="sxs-lookup"><span data-stu-id="0994b-149">The following improvements are added by this feature:</span></span>

- <span data-ttu-id="0994b-150">**Odroczone generowanie sugestii wariantów:** strona **Sugestie wariantów** nie wyświetla już sugestii, gdy po raz pierwszy ją otwierasz.</span><span class="sxs-lookup"><span data-stu-id="0994b-150">**Deferred generation of variant suggestions:** The **Variant suggestions** page no longer shows suggestions when you first open it.</span></span> <span data-ttu-id="0994b-151">Należy jawnie wybrać wartości, które mają być potrzebne, a następnie wybrać przycisk **Sugeruj**, aby wygenerować kombinacje.</span><span class="sxs-lookup"><span data-stu-id="0994b-151">Instead, you must explicitly choose which values you will need and then select the **Suggest** button to generate the combinations.</span></span> <span data-ttu-id="0994b-152">Dzięki temu proces jest bardziej przewidywalny i interakcyjny.</span><span class="sxs-lookup"><span data-stu-id="0994b-152">This makes the process more visible and interactive.</span></span>
- <span data-ttu-id="0994b-153">**Wybór wartości wymiarów:** jeśli istnieje wiele wartości wymiarów, zazwyczaj warto wygenerować sugestie wariantów, które obejmują tylko kilka z nich (na przykład przy tworzeniu nowego zestawu kolorów lub stylów).</span><span class="sxs-lookup"><span data-stu-id="0994b-153">**Selection of dimensions values:** When you have many dimension values, you are typically interested in generating variant suggestions that include just a few of them (such as when introducing a new set of colors or styles).</span></span> <span data-ttu-id="0994b-154">Dzięki ulepszonemu działaniu można wybrać wartości wymiarów, dla których mają być generowane sugestie wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="0994b-154">With the improved design, you can select the dimension values for which you want to generate product variant suggestions.</span></span> <span data-ttu-id="0994b-155">Znacznie zwiększa to adekwatność sugerowanych wariantów oraz poprawia wydajność systemu i produktywność użytkowników.</span><span class="sxs-lookup"><span data-stu-id="0994b-155">This greatly increases the relevance of the suggested variants and improves both system performance and user productivity.</span></span>

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a><span data-ttu-id="0994b-156">Włączanie funkcji ulepszeń strony Sugestie wariantów</span><span class="sxs-lookup"><span data-stu-id="0994b-156">Turn on the Variant suggestions page improvements feature</span></span>

<span data-ttu-id="0994b-157">Aby móc używać funkcji *Ulepszenia strony sugestii wariantów*, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="0994b-157">Before you can use *Variant suggestions page improvements* feature, it must be turned on in your system.</span></span> <span data-ttu-id="0994b-158">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją.</span><span class="sxs-lookup"><span data-stu-id="0994b-158">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="0994b-159">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="0994b-159">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="0994b-160">**Moduł:** *Zarządzanie informacjami o produktach*</span><span class="sxs-lookup"><span data-stu-id="0994b-160">**Module:** *Product information management*</span></span>
- <span data-ttu-id="0994b-161">**Nazwa funkcji:** *ulepszenia strony Sugestie wariantów*</span><span class="sxs-lookup"><span data-stu-id="0994b-161">**Feature name:** *Variant suggestions page improvements*</span></span>

### <a name="work-with-the-improved-variant-suggestions"></a><span data-ttu-id="0994b-162">Praca z ulepszonymi sugestiami wariantów</span><span class="sxs-lookup"><span data-stu-id="0994b-162">Work with the improved variant suggestions</span></span>

<span data-ttu-id="0994b-163">Aby generować sugestie wariantów produktu, gdy funkcja *Ulepszenia strony wariantów sugestii* jest włączona:</span><span class="sxs-lookup"><span data-stu-id="0994b-163">To generate product variant suggestions when the *Variant suggestions page improvements* feature is enabled:</span></span>

1. <span data-ttu-id="0994b-164">Otwórz lub utwórz produkt główny i dodaj do niego wymagane wymiary produktów, zgodnie z opisem w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="0994b-164">Open or create a product master and add the required product dimensions to it, as described in the previous section.</span></span>
1. <span data-ttu-id="0994b-165">Gdy produkt główny jest nadal otwarty, wybierz opcję **Warianty produktu** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="0994b-165">With the product master open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="0994b-166">W okienku akcji wybierz pozycję **Sugestie wariantów**.</span><span class="sxs-lookup"><span data-stu-id="0994b-166">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="0994b-167">Wybierz wartości, których chcesz używać w poszczególnych wymiarach.</span><span class="sxs-lookup"><span data-stu-id="0994b-167">Select the values that you want to use for each of the dimensions.</span></span>
1. <span data-ttu-id="0994b-168">Na górnym pasku narzędzi wybierz pozycję **Sugeruj**.</span><span class="sxs-lookup"><span data-stu-id="0994b-168">On the top toolbar, select **Suggest**.</span></span>
1. <span data-ttu-id="0994b-169">System wygeneruje listę ze wszystkimi możliwymi kombinacjami wybranych rozmiarów i kolorów.</span><span class="sxs-lookup"><span data-stu-id="0994b-169">The system generates a list with all possible combinations of the sizes and colors you selected.</span></span> <span data-ttu-id="0994b-170">Na skróconej karcie **Sugerowane warianty** zaznacz pole wyboru każdej kombinacji wymiarów produktu, której chcesz użyć, lub wybierz opcję **Zaznacz wszystko** na pasku narzędzi, aby zaznaczyć wszystkie z nich.</span><span class="sxs-lookup"><span data-stu-id="0994b-170">On the **Suggested variants** FastTab, select the check box for each product dimension combination that you want to use, or select **Select all** on the toolbar to select all of them.</span></span>  
1. <span data-ttu-id="0994b-171">Wybierz opcję **Utwórz**, aby dodać warianty do bieżącego produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="0994b-171">Select **Create** to add the variants to the current product master.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
