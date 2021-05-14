---
title: Tworzenie konwencji nazewnictwa identyfikatorów produktów dla skonfigurowanych wariantów produktu
description: Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921018"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="facf4-103">Tworzenie konwencji nazewnictwa identyfikatorów produktów dla skonfigurowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="facf4-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="facf4-104">Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym.</span><span class="sxs-lookup"><span data-stu-id="facf4-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="facf4-105">W procedurze zademonstrowano również, jak zbudować konwencję nazewnictwa konfiguracji dla składnika modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="facf4-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="facf4-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="facf4-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="facf4-107">Nowa konwencja nazewnictwa numerów produktu jest przypisana do produktu głównego D0004.</span><span class="sxs-lookup"><span data-stu-id="facf4-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="facf4-108">Zazwyczaj zadanie wykonuje projektant produktów.</span><span class="sxs-lookup"><span data-stu-id="facf4-108">This task would typically be done by a product designer.</span></span>

## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="facf4-109">Tworzenie konwencji nazewnictwa numerów produktu</span><span class="sxs-lookup"><span data-stu-id="facf4-109">Create a product number nomenclature</span></span>

1. <span data-ttu-id="facf4-110">Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Ustawienia \> Nazewnictwo produktów**.</span><span class="sxs-lookup"><span data-stu-id="facf4-110">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="facf4-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="facf4-111">Select **New**.</span></span>
1. <span data-ttu-id="facf4-112">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="facf4-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="facf4-113">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="facf4-113">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="facf4-114">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-114">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-115">Wybierz opcję **Numer produktu głównego**.</span><span class="sxs-lookup"><span data-stu-id="facf4-115">Select **Product master number**.</span></span>
1. <span data-ttu-id="facf4-116">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-116">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-117">Wybierz **Stała tekstowa**.</span><span class="sxs-lookup"><span data-stu-id="facf4-117">Select **Text constant**.</span></span>
1. <span data-ttu-id="facf4-118">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-118">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-119">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="facf4-119">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="facf4-120">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-120">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-121">Wybierz opcję **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="facf4-121">Select **Configuration**.</span></span>
1. <span data-ttu-id="facf4-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="facf4-122">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="facf4-123">Przypisywanie konwencji nazewnictwa numerów produktu do produktu głównego</span><span class="sxs-lookup"><span data-stu-id="facf4-123">Assign the product number nomenclature to a product master</span></span>

1. <span data-ttu-id="facf4-124">Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Produkty \> Produkty główne**.</span><span class="sxs-lookup"><span data-stu-id="facf4-124">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="facf4-125">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="facf4-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="facf4-126">Na przykład ustaw filtr na pole **Numer produktu** z wartością „D”.</span><span class="sxs-lookup"><span data-stu-id="facf4-126">For example, filter on the **Product number** field with a value of 'D'.</span></span>
1. <span data-ttu-id="facf4-127">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="facf4-127">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="facf4-128">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="facf4-128">Select **Edit**.</span></span>
1. <span data-ttu-id="facf4-129">W polu **Użyj nazewnictwa** zaznacz opcję *Tak*.</span><span class="sxs-lookup"><span data-stu-id="facf4-129">Select *Yes* in the **Use nomenclature** field.</span></span>
1. <span data-ttu-id="facf4-130">W polu **Nazewnictwo numerów wariantów produktu** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="facf4-130">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
1. <span data-ttu-id="facf4-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="facf4-131">Close the page.</span></span>
1. <span data-ttu-id="facf4-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="facf4-132">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="facf4-133">Tworzenie konwencji nazewnictwa dla składnika modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="facf4-133">Create nomenclature for a product configuration model component</span></span>

1. <span data-ttu-id="facf4-134">Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.</span><span class="sxs-lookup"><span data-stu-id="facf4-134">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="facf4-135">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="facf4-135">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="facf4-136">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="facf4-136">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="facf4-137">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="facf4-137">Select **Edit**.</span></span>
1. <span data-ttu-id="facf4-138">W polu **Użyj nazewnictwa konfiguracji** wybierz opcję *Tak*.</span><span class="sxs-lookup"><span data-stu-id="facf4-138">Select *Yes* in the **Use configuration nomenclature** field.</span></span>
1. <span data-ttu-id="facf4-139">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-139">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-140">Wybierz opcję **Wartość atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="facf4-140">Select **Attribute value**.</span></span>
1. <span data-ttu-id="facf4-141">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-141">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-142">Wprowadź lub wybierz wartość w polu **Atrybut**.</span><span class="sxs-lookup"><span data-stu-id="facf4-142">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="facf4-143">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-143">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-144">Wybierz **Stała tekstowa**.</span><span class="sxs-lookup"><span data-stu-id="facf4-144">Select **Text constant**.</span></span>
1. <span data-ttu-id="facf4-145">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-145">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-146">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="facf4-146">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="facf4-147">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-147">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-148">Wybierz opcję **Wartość atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="facf4-148">Select **Attribute value**.</span></span>
1. <span data-ttu-id="facf4-149">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-149">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-150">Wprowadź lub wybierz wartość w polu **Atrybut**.</span><span class="sxs-lookup"><span data-stu-id="facf4-150">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="facf4-151">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-151">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-152">Wybierz **Stała tekstowa**.</span><span class="sxs-lookup"><span data-stu-id="facf4-152">Select **Text constant**.</span></span>
1. <span data-ttu-id="facf4-153">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-153">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-154">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="facf4-154">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="facf4-155">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-155">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-156">Wybierz opcję **Wartość atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="facf4-156">Select **Attribute value**.</span></span>
1. <span data-ttu-id="facf4-157">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-157">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-158">Wprowadź lub wybierz wartość w polu **Atrybut**.</span><span class="sxs-lookup"><span data-stu-id="facf4-158">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="facf4-159">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-159">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-160">Wybierz **Stała tekstowa**.</span><span class="sxs-lookup"><span data-stu-id="facf4-160">Select **Text constant**.</span></span>
1. <span data-ttu-id="facf4-161">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-161">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-162">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="facf4-162">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="facf4-163">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-163">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-164">Wybierz opcję **Wartość atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="facf4-164">Select **Attribute value**.</span></span>
1. <span data-ttu-id="facf4-165">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-165">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-166">Wprowadź lub wybierz wartość w polu **Atrybut**.</span><span class="sxs-lookup"><span data-stu-id="facf4-166">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="facf4-167">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-167">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-168">Wybierz **Stała tekstowa**.</span><span class="sxs-lookup"><span data-stu-id="facf4-168">Select **Text constant**.</span></span>
1. <span data-ttu-id="facf4-169">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-169">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-170">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="facf4-170">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="facf4-171">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="facf4-171">Select **Add**.</span></span>
1. <span data-ttu-id="facf4-172">Wybierz opcję **Wartość sekwencji numerów**.</span><span class="sxs-lookup"><span data-stu-id="facf4-172">Select **Number sequence value**.</span></span>
1. <span data-ttu-id="facf4-173">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="facf4-173">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="facf4-174">W polu **Sekwencja numerów** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="facf4-174">In the **Number sequence** field, enter or select a value.</span></span>
1. <span data-ttu-id="facf4-175">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="facf4-175">Close the page.</span></span>
1. <span data-ttu-id="facf4-176">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="facf4-176">Close the page.</span></span>
1. <span data-ttu-id="facf4-177">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="facf4-177">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]