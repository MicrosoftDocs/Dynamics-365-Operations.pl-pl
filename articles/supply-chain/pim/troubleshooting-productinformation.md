---
title: Rozwiązywanie problemów z informacjami o produktach
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z informacjami o produktach.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a05e9957363ef6a659e25ceba84a168507cd641a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841534"
---
# <a name="troubleshoot-product-information"></a><span data-ttu-id="b1237-103">Rozwiązywanie problemów z informacjami o produktach</span><span class="sxs-lookup"><span data-stu-id="b1237-103">Troubleshoot product information</span></span>

<span data-ttu-id="b1237-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z informacjami o produktach.</span><span class="sxs-lookup"><span data-stu-id="b1237-104">This topic describes how to fix issues that you might encounter while you work with product information.</span></span>

## <a name="i-cant-delete-a-released-product"></a><span data-ttu-id="b1237-105">Nie można usunąć zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="b1237-105">I can't delete a released product.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1237-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="b1237-106">Issue description</span></span>

<span data-ttu-id="b1237-107">Zwolniony produkt i wszystkie jego warianty można usunąć tylko w przypadku, gdy zwolniony produkt nie ma żadnych powiązanych transakcji.</span><span class="sxs-lookup"><span data-stu-id="b1237-107">You can delete a released product and all its variants only if the released product doesn't have any related transactions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1237-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="b1237-108">Issue resolution</span></span>

<span data-ttu-id="b1237-109">Aby usunąć zwolniony produkt lub produkt główny, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b1237-109">Follow these steps to delete a released product or product master.</span></span>

1. <span data-ttu-id="b1237-110">Zamknij wszystkie otwarte transakcji dla towarów.</span><span class="sxs-lookup"><span data-stu-id="b1237-110">Close all open transactions for the items.</span></span>
1. <span data-ttu-id="b1237-111">Zmniejsz ilość zapasów do 0 (zera).</span><span class="sxs-lookup"><span data-stu-id="b1237-111">Reduce the inventory to 0 (zero).</span></span>
1. <span data-ttu-id="b1237-112">Przeprowadź zamknięcie zapasów.</span><span class="sxs-lookup"><span data-stu-id="b1237-112">Perform inventory closing.</span></span>
1. <span data-ttu-id="b1237-113">Usuń wszystkie warianty produktu dla produktu głównego, który chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="b1237-113">Delete all product variants for the product master that you want to delete.</span></span>

## <a name="can-i-change-the-item-number-of-a-released-product"></a><span data-ttu-id="b1237-114">Czy można zmienić numer pozycji dla zwolnionego produktu?</span><span class="sxs-lookup"><span data-stu-id="b1237-114">Can I change the item number of a released product?</span></span>

<span data-ttu-id="b1237-115">W większości przypadków nie można edytować numerów pozycji zwolnionych produktów, ponieważ ta zmiana spowoduje uszkodzenie danych.</span><span class="sxs-lookup"><span data-stu-id="b1237-115">In most cases, you can't edit item numbers for released products, because that change will cause data to become corrupted.</span></span> <span data-ttu-id="b1237-116">Numer pozycji można edytować tylko wtedy, gdy konieczne jest naprawienie uszkodzeń danych spowodowanych przez poprzednią zmianę nazwy klucza podstawowego wydanego produktu, jak wspomniano na liście [usuniętych lub przestarzałych funkcji Finance and Operations 10.0.0 z aktualizacją Platform update 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).</span><span class="sxs-lookup"><span data-stu-id="b1237-116">You can edit the item number only if you must repair data corruption that was caused by a previous rename of the primary key of that released product, as mentioned in the list of [removed or deprecated features for Finance and Operations 10.0.0 with Platform update 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).</span></span>

<span data-ttu-id="b1237-117">Jeśli chcesz mieć możliwość edytowania numerów pozycji dla zwolnionych produktów, [zagłosuj na ten pomysł w portalu pomysłów](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).</span><span class="sxs-lookup"><span data-stu-id="b1237-117">If you want to be able to edit item numbers for released products, [vote for this idea in Ideas portal](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).</span></span>

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a><span data-ttu-id="b1237-118">Domyślna reguła usuwania z produktu nie jest wprowadzana w wierszu listy składowej.</span><span class="sxs-lookup"><span data-stu-id="b1237-118">The default flushing principle from the product isn't being entered on the bill of materials line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1237-119">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="b1237-119">Issue description</span></span>

<span data-ttu-id="b1237-120">Po dodaniu pozycji do wiersza listy składowej (BOM) system nie korzysta z domyślnej reguły usuwania ustawionej dla pozycji.</span><span class="sxs-lookup"><span data-stu-id="b1237-120">When you add an item to a bill of materials (BOM) line, the system doesn't use the default flushing principle information that is set up for the item.</span></span> <span data-ttu-id="b1237-121">Innymi słowy, reguła usuwania z pozycji nie jest wyświetlana na stronie **wiersza BOM**.</span><span class="sxs-lookup"><span data-stu-id="b1237-121">In other words, the flushing principle from the item doesn't appear on the **BOM line** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1237-122">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="b1237-122">Issue resolution</span></span>

<span data-ttu-id="b1237-123">Jeśli w wierszu BOM określono regułę usuwania, będzie ona dotyczyć tego wiersza BOM.</span><span class="sxs-lookup"><span data-stu-id="b1237-123">If you specify a flushing principle on a BOM line, it will apply to that BOM line.</span></span> <span data-ttu-id="b1237-124">Jeśli jednak reguła usuwania jest pusta lub jeśli nie została ustawiona w wierszu BOM, reguła usuwania, która jest ustawiona dla pozycji, będzie nadal stosowana do tego wiersza BOM, nawet jeśli nie jest wyświetlana w wierszu BOM.</span><span class="sxs-lookup"><span data-stu-id="b1237-124">However, if the flushing principle is blank, or if it isn't set on a BOM line, the flushing principle that is set on the item will still apply to that BOM line, even though it isn't shown on the BOM line.</span></span>

<span data-ttu-id="b1237-125">Domyślna logika dla innych funkcji w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management nie działa zwykle w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="b1237-125">The defaulting logic for other features in Microsoft Dynamics 365 Supply Chain Management doesn't usually work in this way.</span></span> <span data-ttu-id="b1237-126">Nie można jednak zmienić bieżącego zachowania.</span><span class="sxs-lookup"><span data-stu-id="b1237-126">However, the current behavior can't be changed.</span></span> <span data-ttu-id="b1237-127">W przeciwnym razie niektóre istniejące dostosowania zależne od niego mogą zostać uszkodzone.</span><span class="sxs-lookup"><span data-stu-id="b1237-127">Otherwise, some existing customizations that rely on it might be broken.</span></span>

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a><span data-ttu-id="b1237-128">System umożliwia zapisywanie duplikatów kodów kreskowych dla różnych towarów lub dla tego samego towaru o różnych wymiarach.</span><span class="sxs-lookup"><span data-stu-id="b1237-128">The system lets me save duplicate bar codes for different items or for the same item that has different dimensions.</span></span>

<span data-ttu-id="b1237-129">System nie wymusza obecnie unikatowych kodów kreskowych, a dodanie tego ograniczenia spowodowałoby zmianę powodującą niezgodność.</span><span class="sxs-lookup"><span data-stu-id="b1237-129">The system doesn't currently enforce unique bar codes, and the addition of this restriction would be a breaking change.</span></span> <span data-ttu-id="b1237-130">W rzeczywistości Microsoft ma dowody na to, że niektóre istniejące instalacje klientów zostałyby uszkodzone przez tę zmianę.</span><span class="sxs-lookup"><span data-stu-id="b1237-130">In fact, Microsoft has evidence that some existing customer installations would be broken by this change.</span></span> <span data-ttu-id="b1237-131">Jednak w przyszłości będzie rozważana zmiana projektu umożliwiająca włączenie tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="b1237-131">However, we will consider a broader design change to enable this feature in the future.</span></span>

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a><span data-ttu-id="b1237-132">Podczas edytowania szablonów rekordów pozycji zgłaszany jest następujący komunikat o błędzie: „Nie można utworzyć lokalizacji magazynu, ponieważ pozycja nie jest magazynowana.</span><span class="sxs-lookup"><span data-stu-id="b1237-132">I receive the following error message when I edit item record templates: "The warehouse location cannot be created because the item is not stocked.</span></span> <span data-ttu-id="b1237-133">W przypadku pozycji magazynowych należy wybrać opcję produktu magazynowego w grupie modeli skojarzonej pozycji”.</span><span class="sxs-lookup"><span data-stu-id="b1237-133">To stock items, the Stocked product option on the associated item model group must be selected."</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1237-134">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="b1237-134">Issue description</span></span>

<span data-ttu-id="b1237-135">Ten problem występuje w przypadku wykonania tych kroków w celu utworzenia szablonu dla towaru, który nie jest magazynowany.</span><span class="sxs-lookup"><span data-stu-id="b1237-135">This issue occurs if you follow these steps to try to create a template for an item that isn't stocked.</span></span>

1. <span data-ttu-id="b1237-136">Umożliwia otwarcie zwolnionego produktu, który nie jest magazynowany.</span><span class="sxs-lookup"><span data-stu-id="b1237-136">Open a released product that isn't stocked.</span></span>
1. <span data-ttu-id="b1237-137">W okienku akcji na karcie **Opcje** wybierz opcję **Informacje o rekordzie**.</span><span class="sxs-lookup"><span data-stu-id="b1237-137">On the Action Pane, on the **Options** tab, select **Record info**.</span></span>
1. <span data-ttu-id="b1237-138">W oknie dialogowym **Informacje o rekordzie** wybierz pozycję **Szablon kont firmy**.</span><span class="sxs-lookup"><span data-stu-id="b1237-138">In the **Record information** dialog box, select **Company accounts template**.</span></span>

<span data-ttu-id="b1237-139">W takim przypadku zostanie wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="b1237-139">In this case, you receive the following error message:</span></span>

> <span data-ttu-id="b1237-140">Nie można utworzyć lokalizacji magazynu, ponieważ pozycja nie jest magazynowana.</span><span class="sxs-lookup"><span data-stu-id="b1237-140">The warehouse location cannot be created because the item is not stocked.</span></span> <span data-ttu-id="b1237-141">W przypadku pozycji magazynowych należy wybrać opcję produktu magazynowego w grupie modeli skojarzonej pozycji.</span><span class="sxs-lookup"><span data-stu-id="b1237-141">To stock items, the Stocked product option on the associated item model group must be selected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1237-142">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="b1237-142">Issue resolution</span></span>

<span data-ttu-id="b1237-143">Proces tworzenia szablonów produktów wymaga użycia dodatkowej logiki specyficznej dla produktu.</span><span class="sxs-lookup"><span data-stu-id="b1237-143">The process of creating product templates requires extra product-specific logic.</span></span> <span data-ttu-id="b1237-144">Z tego względu nie można w tym celu wybrać ogólnego przycisku **Szablon kont firmy**.</span><span class="sxs-lookup"><span data-stu-id="b1237-144">Therefore, you can't use the generic **Company accounts template** button for this purpose.</span></span> <span data-ttu-id="b1237-145">Zamiast tego należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b1237-145">Instead, follow these steps.</span></span>

1. <span data-ttu-id="b1237-146">Otwórz zwolniony produkt.</span><span class="sxs-lookup"><span data-stu-id="b1237-146">Open a released product.</span></span>
1. <span data-ttu-id="b1237-147">W okienku akcji, na karcie **Produkt**, w grupie **Nowy** wybierz **Szablon \> Utwórz udostępniony szablon**.</span><span class="sxs-lookup"><span data-stu-id="b1237-147">On the Action Pane, on the **Product** tab, in the **New** group, select **Template \> Create shared template**.</span></span>

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a><span data-ttu-id="b1237-148">Domyślny tekst pomoc dodawany w atrybutach produktu nie został wprowadzony w zwolnionym produkcie.</span><span class="sxs-lookup"><span data-stu-id="b1237-148">Default Help text that is added in product attributes isn't entered in a released product.</span></span>

<span data-ttu-id="b1237-149">Opis i tekst pomocy dodane w atrybutach produktu nie są domyślnie widoczne lub wprowadzane w zwolnionych produktach.</span><span class="sxs-lookup"><span data-stu-id="b1237-149">A description and Help text that are added in the product attributes aren't visible or entered by default in the released products.</span></span> <span data-ttu-id="b1237-150">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="b1237-150">This behavior is by design.</span></span>

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a><span data-ttu-id="b1237-151">Domyślna ilość, która jest wprowadzana, różni się pod względem rejestracji z BOM i gdy jest rejestrowana z wersji BOM.</span><span class="sxs-lookup"><span data-stu-id="b1237-151">The default quantity that is entered differs when it's registered from a BOM and when it's registered from a BOM version.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1237-152">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="b1237-152">Issue description</span></span>

<span data-ttu-id="b1237-153">Domyślnie podczas dodawania pozycji do BOM ilość jest ustawiana na 1 zamiast ilości zdefiniowanej w polu **Min. ilość zamówiona** na stronie **Ustawienia domyślne zamówienia** dla wybranego produktu.</span><span class="sxs-lookup"><span data-stu-id="b1237-153">By default, when you add an item to a BOM, the quantity is set to 1 instead of the quantity that is defined in the **Min. order quantity** field on the **Default order settings** page for a selected product.</span></span> <span data-ttu-id="b1237-154">Jednak po dodaniu pozycji z wersji BOM i wybraniu pozycji i wariantu ilość, która została wprowadzona domyślnie, uwzględnia minimalną ilość ustawioną w domyślnych ustawieniach zamówienia dla określonych wymiarów.</span><span class="sxs-lookup"><span data-stu-id="b1237-154">However, when you add an item from a BOM version, and the item and variant are selected, the quantity that is entered by default takes into account the minimum quantity that is set in the default order settings for the specific dimensions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1237-155">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="b1237-155">Issue resolution</span></span>

<span data-ttu-id="b1237-156">To zachowanie jest oczekiwane.</span><span class="sxs-lookup"><span data-stu-id="b1237-156">This behavior is expected.</span></span> <span data-ttu-id="b1237-157">Jednak fakt, że logika różni się w BOM i w wersji BOM jest znanym problemem.</span><span class="sxs-lookup"><span data-stu-id="b1237-157">However, the fact that the logic differs in the BOM and the BOM version is a known issue.</span></span> <span data-ttu-id="b1237-158">Jednak to zachowanie nie zostanie zmienione, ponieważ zmiana może mieć wpływ na wiele różnych scenariuszy klientów.</span><span class="sxs-lookup"><span data-stu-id="b1237-158">Nevertheless, this behavior won't be changed, because a change could affect many different customer scenarios.</span></span>

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a><span data-ttu-id="b1237-159">W szczegółach zwolnionego produktu nie mogę zmienić dołączonych obrazów przekazanych z jednostki danych załączników do dokumentu produktu.</span><span class="sxs-lookup"><span data-stu-id="b1237-159">In the released product details, I can't change the attached images that were uploaded from the Product document attachments data entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1237-160">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="b1237-160">Issue description</span></span>

<span data-ttu-id="b1237-161">Ten problem może wystąpić podczas dołączania obrazu do pozycji przy użyciu jednostki danych *Załączniki do dokumentu produktu*.</span><span class="sxs-lookup"><span data-stu-id="b1237-161">This issue can occur when you attach an image to an item by using the *Product document attachments* data entity.</span></span> <span data-ttu-id="b1237-162">W takim przypadku obraz pozycji jest wyświetlany dla pozycji.</span><span class="sxs-lookup"><span data-stu-id="b1237-162">In this case, the item image is shown for the item.</span></span> <span data-ttu-id="b1237-163">Jeśli jednak zostanie wybrana opcja **Zmień obraz**, na liście przekazanych obrazów nic nie będzie widoczne.</span><span class="sxs-lookup"><span data-stu-id="b1237-163">However, if you select **Change image**, nothing is shown in the list of uploaded images.</span></span> <span data-ttu-id="b1237-164">Ponadto nie są pokazywane żadne załączniki dla pozycji.</span><span class="sxs-lookup"><span data-stu-id="b1237-164">Additionally, no attachments are shown for the item.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1237-165">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="b1237-165">Issue resolution</span></span>

<span data-ttu-id="b1237-166">Jednostka *EcoResProductDocumentAttachmentEntity* (*Załączniki do dokumentu produktu*) importuje załączniki dokumentów dla *produktów*, ale nie dla *zwolnionych produktów*.</span><span class="sxs-lookup"><span data-stu-id="b1237-166">The *EcoResProductDocumentAttachmentEntity* entity (*Product document attachments*) imports document attachments for *products* but not for *released products*.</span></span> <span data-ttu-id="b1237-167">(Zwolnione produkty są również nazywane *pozycjami*.) Aby wyświetlić załączniki dla pozycji na stronie **Szczegóły zwolnionego produktu**, należy użyć opcji *Jednostka EcoResReleasedProductDocumentAttachmentEntity* (*Załączniki do dokumentu zwolnionego produktu*).</span><span class="sxs-lookup"><span data-stu-id="b1237-167">(Released products are also known as *items*.) To view the attachments for an item on the **Released product details** page, you must use the *EcoResReleasedProductDocumentAttachmentEntity* entity (*Released product document attachments*) instead.</span></span>

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a><span data-ttu-id="b1237-168">Łącznik Microsoft Flow zawiera następujący komunikat o błędzie: „Aktualizacja jest niedozwolona dla pola ProductNumber”.</span><span class="sxs-lookup"><span data-stu-id="b1237-168">The Microsoft Flow connector shows the following error message: "Update not allowed for field 'ProductNumber'."</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1237-169">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="b1237-169">Issue description</span></span>

<span data-ttu-id="b1237-170">Ten problem występuje w przypadku próby zaktualizowania pola **Numer produktu** przy użyciu jednostki *Zwolnione produkty* w wersji V2 i Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="b1237-170">This issue occurs if you try to update the **Product number** field by using the *Released products* entity V2 and Microsoft Flow.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1237-171">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="b1237-171">Issue resolution</span></span>

<span data-ttu-id="b1237-172">To zachowanie jest oczekiwane.</span><span class="sxs-lookup"><span data-stu-id="b1237-172">This behavior is expected.</span></span> <span data-ttu-id="b1237-173">Możliwość edytowania numeru produktu dla zwolnionego produktu została usunięta w Dynamics 365 Finance and Operations 10.0.0 z aktualizacją Platform update 24, aby ułatwić zapobieganie uszkodzeniu danych.</span><span class="sxs-lookup"><span data-stu-id="b1237-173">The ability to edit the product number for a released product was removed in Dynamics 365 Finance and Operations 10.0.0 with platform update 24 to help prevent data corruption.</span></span> <span data-ttu-id="b1237-174">W wyjątkowych przypadkach, jeśli trzeba naprawić uszkodzenie danych spowodowane przez poprzednią nazwę klucza podstawowego zwolnionego produktu, można skontaktować się z pomocą techniczną firmy Microsoft, aby zażądać tymczasowego usunięcia tego ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="b1237-174">In exceptional cases, where you must repair data corruption that was caused by a previous rename of the primary key of a released product, you can ask Microsoft Support to temporarily remove this restriction.</span></span>

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a><span data-ttu-id="b1237-175">Nie można utworzyć wariantu zwolnionego produktu w innej osobie prawnej.</span><span class="sxs-lookup"><span data-stu-id="b1237-175">I can't create a released product variant in another legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1237-176">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="b1237-176">Issue description</span></span>

<span data-ttu-id="b1237-177">Jeśli użytkownik spróbuje zwolnić produkt główny bez wariantów, a następnie utworzy warianty w poszczególnych osobach prawnych (firmach) zgodnie z wymogami, nie będzie można zwolnić wariantów za pomocą sugestii wariantów.</span><span class="sxs-lookup"><span data-stu-id="b1237-177">If you try to release a product master without variants, and then create the variants in each legal entity (company) as they are required, you won't be able to release the variants by using variant suggestions.</span></span> <span data-ttu-id="b1237-178">Nie będzie również możliwe ręczne tworzenie wariantów.</span><span class="sxs-lookup"><span data-stu-id="b1237-178">You also won't be able to manually create the variants.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1237-179">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="b1237-179">Issue resolution</span></span>

<span data-ttu-id="b1237-180">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="b1237-180">This behavior is by design.</span></span> <span data-ttu-id="b1237-181">Relacje produktu głównego i wymiarów, które może wykonać produkt główny, są utrzymywane na poziomie udostępnionym.</span><span class="sxs-lookup"><span data-stu-id="b1237-181">The relations of a product master and the dimensions that the master can take are kept at a shared level.</span></span> <span data-ttu-id="b1237-182">Dlatego nie można utworzyć wymiarów dostępnych dla udostępnionego produktu głównego w określonej osobie prawnej, w której te wymiary są zwolnione, a następnie replikować proces w każdej osobie prawnej, w której są wymagane wymiary.</span><span class="sxs-lookup"><span data-stu-id="b1237-182">Therefore, you can't create the available dimensions for a shared product master in the specific legal entity where those dimensions are released and then replicate the process in each legal entity where the dimensions are required.</span></span> <span data-ttu-id="b1237-183">W takim przypadku należy zmienić proces wydania w celu dostosowania go do planowanego procesu.</span><span class="sxs-lookup"><span data-stu-id="b1237-183">Instead, you must change your release process to adapt to the designed process.</span></span>

<span data-ttu-id="b1237-184">Poniżej przedstawiono proces zwalniania produktów.</span><span class="sxs-lookup"><span data-stu-id="b1237-184">Here is the process for releasing products.</span></span>

1. <span data-ttu-id="b1237-185">Utwórz współużytkowany produkt główny i wymiary, które można zwolnić do osób prawnych.</span><span class="sxs-lookup"><span data-stu-id="b1237-185">Create the shared product master and the dimensions that can be released to the legal entities.</span></span>
1. <span data-ttu-id="b1237-186">Umożliwia zwolnienie produktów do osób prawnych przez użycie sugestii wariantów lub ręczne dodanie kombinacji, które powinny zostać zwolnione.</span><span class="sxs-lookup"><span data-stu-id="b1237-186">Release the products to the legal entities either by using variant suggestions or by manually adding the combinations that should be released.</span></span>

<span data-ttu-id="b1237-187">Można również bezpośrednio utworzyć zwolniony produkt.</span><span class="sxs-lookup"><span data-stu-id="b1237-187">Alternatively, you can directly create the released product.</span></span>

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a><span data-ttu-id="b1237-188">Po zwolnieniu wariantu w innej osobie prawnej otrzymuję następujący komunikat o błędzie: „Wariant produktu o określonych wymiarach został już utworzony”.</span><span class="sxs-lookup"><span data-stu-id="b1237-188">When I release a variant in another company, I receive the following error message: "Product variant with specified dimensions has already been created."</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1237-189">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="b1237-189">Issue description</span></span>

<span data-ttu-id="b1237-190">Jeśli wariant produktu został już wydany w firmie A i podjęto próbę zwolnienia go w firmie B za pomocą przycisku **Nowy** na stronie **Zwolnione warianty produktu**, zostanie wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="b1237-190">If a product variant has already been released in a company A, and you try to release it in company B by using the **New** button on the **Released product variants** page, you will receive the following error message:</span></span>

> <span data-ttu-id="b1237-191">Wariant produktu o podanych wymiarach został już utworzony.</span><span class="sxs-lookup"><span data-stu-id="b1237-191">Product variant with specified dimensions has already been created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1237-192">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="b1237-192">Issue resolution</span></span>

<span data-ttu-id="b1237-193">Przycisk **Nowy** na stronie **Zwolnione warianty produktu** powoduje utworzenie wariantu i zwolnienie go w kontekście firmy.</span><span class="sxs-lookup"><span data-stu-id="b1237-193">The **New** button on the **Released product variants** page creates the variant and releases it in the company context.</span></span> <span data-ttu-id="b1237-194">Jeśli wariant został już utworzony, nie można go zwolnić w innej firmie przy użyciu przycisku **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b1237-194">If the variant has already been created, you can't use the **New** button to release it in another company.</span></span>

<span data-ttu-id="b1237-195">Aby rozwiązać ten problem, otwórz stronę **Produktu głównego** i wybierz pozycję **Zwolnij produkt**, aby zwolnić istniejący wariant w wybranej firmie.</span><span class="sxs-lookup"><span data-stu-id="b1237-195">To fix the issue, open the **Product master** page, and select **Release product** to release the existing variant in the desired company.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]