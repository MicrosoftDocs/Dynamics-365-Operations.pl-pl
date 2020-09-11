---
title: Zarządzanie informacjami dotyczącymi klienta dla Polski
description: W tym temacie opisano sposób obsługi informacji o klientach w programie Retail POS dla Polski.
author: sepism
manager: ''
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Poland
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2019-11-11
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: b38bb95254d5a9713f361a8dd5d9f2455471922a
ms.sourcegitcommit: fa8bc4c6fcaba870aead619f80091fb65a28d982
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "3711175"
---
# <a name="customer-information-management-for-poland"></a><span data-ttu-id="55a9a-103">Zarządzanie informacjami dotyczącymi klienta dla Polski</span><span class="sxs-lookup"><span data-stu-id="55a9a-103">Customer information management for Poland</span></span>

[!include [banner](../includes/banner.md)]


## <a name="introduction"></a><span data-ttu-id="55a9a-104">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="55a9a-104">Introduction</span></span>

<span data-ttu-id="55a9a-105">W tym temacie opisano sposób obsługi informacji o odbiorcy, takich jak numer podatku VAT, w Retail Point of Sale (POS) dla Polski.</span><span class="sxs-lookup"><span data-stu-id="55a9a-105">This topic describes how you can handle customer information, such as the customer's value-added tax (VAT) number, in Retail point of sale (POS) for Poland.</span></span>

<span data-ttu-id="55a9a-106">Numer VAT odbiorcy można określić podczas tworzenia lub edytowania głównego rekordu odbiorcy w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="55a9a-106">You can specify the customer's VAT number when you create or edit a customer master record in POS.</span></span> <span data-ttu-id="55a9a-107">Można także określić numer VAT dla transakcji sprzedaży, kopiując go z odbiorcy transakcji lub wprowadzając go ręcznie.</span><span class="sxs-lookup"><span data-stu-id="55a9a-107">You can also specify a VAT number for a sales transaction by copying it from the transaction customer or entering it manually.</span></span> <span data-ttu-id="55a9a-108">Informacje dotyczące odbiorcy mogą być następnie drukowane zarówno na stałych, jak i fiskalnych przychodach i mogą być używane do celów fakturowania.</span><span class="sxs-lookup"><span data-stu-id="55a9a-108">The customer information can then be printed on both regular and fiscal receipts, and it can be used for invoicing purposes.</span></span>

> [!NOTE]
> <span data-ttu-id="55a9a-109">Ta funkcja jest dostępna w wersjach 10.0.7 i późniejszych.</span><span class="sxs-lookup"><span data-stu-id="55a9a-109">This functionality is available in version 10.0.7 and later.</span></span>

## <a name="setup"></a><span data-ttu-id="55a9a-110">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="55a9a-110">Setup</span></span>

<span data-ttu-id="55a9a-111">Aby skorzystać z ten funkcji należy skonfigurować system w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="55a9a-111">You must complete the following configuration to use this functionality:</span></span>

- <span data-ttu-id="55a9a-112">Ustawić typ rejestracji dla numeru VAT.</span><span class="sxs-lookup"><span data-stu-id="55a9a-112">Set up a registration type for the VAT number.</span></span>
- <span data-ttu-id="55a9a-113">Dodać operację **Dodaj informacje o kliencie** do układów ekranu.</span><span class="sxs-lookup"><span data-stu-id="55a9a-113">Add the **Add customer information** operation to screen layouts.</span></span>
- <span data-ttu-id="55a9a-114">Aktywować zapytanie dotyczące informacji o odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="55a9a-114">Activate the inquiry for customer information.</span></span>
- <span data-ttu-id="55a9a-115">Konfigurować format paragonu.</span><span class="sxs-lookup"><span data-stu-id="55a9a-115">Set up receipt formats.</span></span>
- <span data-ttu-id="55a9a-116">Konfiguracja składników kanału.</span><span class="sxs-lookup"><span data-stu-id="55a9a-116">Configure channel components.</span></span>

### <a name="set-up-a-registration-type-for-the-vat-number"></a><span data-ttu-id="55a9a-117">Ustawić typ rejestracji dla numeru VAT</span><span class="sxs-lookup"><span data-stu-id="55a9a-117">Set up a registration type for the VAT number</span></span>

<span data-ttu-id="55a9a-118">Przed określeniem numerów VAT w POS należy utworzyć odpowiedni typ rejestracji numeru VAT i połączyć go z kategorią rejestracyjną identyfikatora **VAT ID**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-118">Before VAT numbers can be specified in POS, you must create an appropriate registration type for the VAT number and link it to the **VAT ID** registration category.</span></span> <span data-ttu-id="55a9a-119">Aby uzyskać więcej informacji na temat pracy z typami rejestracji i identyfikatorami rejestracji, przejrzyj [Identyfikatory rejestracji](../../finance/localizations/emea-registration-ids.md).</span><span class="sxs-lookup"><span data-stu-id="55a9a-119">For more information about how to work with registration types and registration IDs, see [Registration IDs](../../finance/localizations/emea-registration-ids.md).</span></span>

> [!WARNING]
> <span data-ttu-id="55a9a-120">Jeśli typ rejestracji nie zostanie utworzony lub nie jest połączony z kategorią rejestracji identyfikatorów **VAT ID**, w programie POS zostanie wygenerowany błąd, jeśli dla adresu odbiorcy zostanie wypełniony numer VAT.</span><span class="sxs-lookup"><span data-stu-id="55a9a-120">If a registration type isn't created or isn't linked to the **VAT ID** registration category, an error will be generated in POS when VAT number is filled in for a customer address.</span></span>

### <a name="add-the-add-customer-information-operation-to-screen-layouts"></a><span data-ttu-id="55a9a-121">Dodaj operację Dodaj informacje o kliencie do układów ekranu</span><span class="sxs-lookup"><span data-stu-id="55a9a-121">Add the Add customer information operation to screen layouts</span></span>

<span data-ttu-id="55a9a-122">Za pomocą operacji **Dodawania informacji o kliencie** można dodawać informacje o odbiorcy do transakcji sprzedaży, takie jak np. numer VAT.</span><span class="sxs-lookup"><span data-stu-id="55a9a-122">The **Add customer information** operation can be used to add customer information, such as the VAT number, to a sales transaction.</span></span> <span data-ttu-id="55a9a-123">Te informacje można skopiować z odbiorcy określonego dla transakcji lub ręcznie wprowadzić.</span><span class="sxs-lookup"><span data-stu-id="55a9a-123">This information can be copied from the customer that is specified for the transaction, or it can be manually entered.</span></span>

<span data-ttu-id="55a9a-124">Na stronie **Siatki przycisków** wybierz siatkę przycisków, na której ma się pojawić operacja, a następnie otwórz Projektanta siatki przycisków.</span><span class="sxs-lookup"><span data-stu-id="55a9a-124">On the **Button grids** page, select the button grid where the operation should appear, and open the Button grid designer.</span></span> <span data-ttu-id="55a9a-125">Dodaj nowy przycisk, nastepnie w polu **Działanie**, wybierz **Dodaj informacje o kliencie**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-125">Add a new button, and then, in the **Action** field, select **Add customer information**.</span></span> <span data-ttu-id="55a9a-126">Aby uzyskać więcej informacji na temat pracy z układami ekranu i siatkami przycisków, należy zapoznać się z [Układami ekranu dla punkt sprzedaży (POS)](../pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="55a9a-126">For more information about how to work with screen layouts and button grids, see [Screen layouts for the point of sale (POS)](../pos-screen-layouts.md).</span></span>

### <a name="activate-the-inquiry-for-customer-information"></a><span data-ttu-id="55a9a-127">Aktywuj zapytanie dotyczące informacji o odbiorcy</span><span class="sxs-lookup"><span data-stu-id="55a9a-127">Activate the inquiry for customer information</span></span>

<span data-ttu-id="55a9a-128">Jeśli dla transakcji sprzedaży nie określono informacji o odbiorcy, prośba o te informacje może zostać wyzwolona automatycznie po sfinalizowaniu transakcji.</span><span class="sxs-lookup"><span data-stu-id="55a9a-128">If the customer information isn't specified for a sales transaction, an inquiry for that information can be triggered automatically after the transaction is finalized.</span></span> <span data-ttu-id="55a9a-129">Ta metoda jest alternatywą dla operacji **Dodawania informacji o odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-129">This approach is an alternative to the **Add customer information** operation.</span></span>

<span data-ttu-id="55a9a-130">Aby uaktywnić opcję żądania informacji o odbiorcy, należy w sekcji **Umożliwienie zapytań dot. informacji o kliencie w transakcjach sprzedaży** na **Tak** w sekcji **Parametry podatkowe** na skróconej karcie pt. **Funkcje** na stronie **Funkcjonalności profili POS**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-130">To activate the inquiry for customer information, set the **Enable inquiry of customer information in sales transactions** option to **Yes** in the **Tax parameters** section on the **Functions** FastTab of the **POS functionality profiles** page.</span></span>

### <a name="set-up-receipt-formats"></a><span data-ttu-id="55a9a-131">Konfiguracja formatów paragonu</span><span class="sxs-lookup"><span data-stu-id="55a9a-131">Set up receipt formats</span></span>

<span data-ttu-id="55a9a-132">Formaty paragonów można skonfigurować w taki sposób, aby numer VAT odbiorcy był na nich drukowany.</span><span class="sxs-lookup"><span data-stu-id="55a9a-132">You can configure receipt formats so that the customer's VAT number is printed on receipts.</span></span>

> [!NOTE]
> <span data-ttu-id="55a9a-133">Domyślna firma użytkownika, który tworzy konfigurację paragonu, powinna być tą samą osobowością prawną, w której jest tworzone ustawienie tekstu w języku.</span><span class="sxs-lookup"><span data-stu-id="55a9a-133">The default company of the user who creates the receipt setup should be the same legal entity where the language text setup is created.</span></span> <span data-ttu-id="55a9a-134">Alternatywnie, można również utworzyć ten sam tekst językowy w domyślnej firmie użytkownika i dla tego samego bytu prawnego, dla którego utworzono konfigurację.</span><span class="sxs-lookup"><span data-stu-id="55a9a-134">Alternatively, the same language texts should be created in both the user's default company and the legal entity of the store that the setup is created for.</span></span>

<span data-ttu-id="55a9a-135">Na stronie **Tekst języka**, na karcie **Punkt sprzedaży** dodaj następujący rekord dla etykiety pola niestandardowego w przypadku formatów paragonów.</span><span class="sxs-lookup"><span data-stu-id="55a9a-135">On the **Language text** page, on the **POS** tab, add the following record for the label of the custom field for receipt formats.</span></span> <span data-ttu-id="55a9a-136">Należy zwrócić uwagę, że przykłady **Identyfikatora języka**, **Identyfikatora tekstu** oraz wartości **tekstowe** przedstawione w poniższej tabeli są tylko przykładami.</span><span class="sxs-lookup"><span data-stu-id="55a9a-136">Note that the **Language ID**, **Text ID**, and **Text** values that are shown in the following table are just examples.</span></span> <span data-ttu-id="55a9a-137">Można je zmienić, aby spełniały wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="55a9a-137">You can change them to meet your requirements.</span></span> <span data-ttu-id="55a9a-138">Jednak używana wartość **identyfikatora tekstu** musi być unikatowa i musi być równa lub większa niż 900001.</span><span class="sxs-lookup"><span data-stu-id="55a9a-138">However, the **Text ID** value that you use must be unique, and it must be equal to or more than 900001.</span></span>

| <span data-ttu-id="55a9a-139">Identyfikator języka</span><span class="sxs-lookup"><span data-stu-id="55a9a-139">Language ID</span></span> | <span data-ttu-id="55a9a-140">Identyfikator tekstu</span><span class="sxs-lookup"><span data-stu-id="55a9a-140">Text ID</span></span> | <span data-ttu-id="55a9a-141">Tekst</span><span class="sxs-lookup"><span data-stu-id="55a9a-141">Text</span></span>       |
|-------------|---------|------------|
| <span data-ttu-id="55a9a-142">en-US</span><span class="sxs-lookup"><span data-stu-id="55a9a-142">en-US</span></span>       | <span data-ttu-id="55a9a-143">900001</span><span class="sxs-lookup"><span data-stu-id="55a9a-143">900001</span></span>  | <span data-ttu-id="55a9a-144">Numer VAT</span><span class="sxs-lookup"><span data-stu-id="55a9a-144">VAT number</span></span> |

<span data-ttu-id="55a9a-145">Na stronie **Niestandardowe pola** dodaj następujący rekord dla pola niestandardowego w odniesieniu do formatów paragonów.</span><span class="sxs-lookup"><span data-stu-id="55a9a-145">On the **Custom fields** page, add the following record for the custom field for receipt formats.</span></span> <span data-ttu-id="55a9a-146">Należy zauważyć, że wartość **identyfikatora tekstu podpisu** musi być zgodna z wartością **identyfikatora tekstu** podaną na **stronie tekstowej języka**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-146">Note that the **Caption text ID** value must correspond to the **Text ID** value that you specified on the **Language text** page.</span></span>

| <span data-ttu-id="55a9a-147">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="55a9a-147">Name</span></span>                      | <span data-ttu-id="55a9a-148">Typ</span><span class="sxs-lookup"><span data-stu-id="55a9a-148">Type</span></span>    | <span data-ttu-id="55a9a-149">Identyfikator tekstu podpisu</span><span class="sxs-lookup"><span data-stu-id="55a9a-149">Caption text ID</span></span> |
|---------------------------|---------|-----------------|
| <span data-ttu-id="55a9a-150">FISCALCUSTOMER\_VATID\_pl</span><span class="sxs-lookup"><span data-stu-id="55a9a-150">FISCALCUSTOMER\_VATID\_PL</span></span> | <span data-ttu-id="55a9a-151">Odbiór</span><span class="sxs-lookup"><span data-stu-id="55a9a-151">Receipt</span></span> | <span data-ttu-id="55a9a-152">900001</span><span class="sxs-lookup"><span data-stu-id="55a9a-152">900001</span></span>          |

<span data-ttu-id="55a9a-153">W projektancie formatów paragonów dodaj pole niestandardowe do odpowiedniej sekcji paragonu dla każdego wymaganego formatu paragonu.</span><span class="sxs-lookup"><span data-stu-id="55a9a-153">In the Receipt format designer, add the custom field to the appropriate receipt section for every receipt format that is required.</span></span> <span data-ttu-id="55a9a-154">Aby uzyskać więcej informacji o sposobie pracy z formatami paragonów, zobacz [Szablony paragonów i drukowanie](../receipt-templates-printing.md).</span><span class="sxs-lookup"><span data-stu-id="55a9a-154">For more information about how to work with receipt formats, see [Receipt templates and printing](../receipt-templates-printing.md).</span></span>

### <a name="configure-channel-components"></a><span data-ttu-id="55a9a-155">Konfiguracja składników kanału.</span><span class="sxs-lookup"><span data-stu-id="55a9a-155">Configure channel components</span></span>

<span data-ttu-id="55a9a-156">Aby udostępnić funkcje właściwe dla Polski, należy skonfigurować rozszerzenia dla składników kanału.</span><span class="sxs-lookup"><span data-stu-id="55a9a-156">To make the functionality that is specific to Poland available, you must configure extensions for channel components.</span></span> <span data-ttu-id="55a9a-157">Aby uzyskać więcej informacji, zobacz sekcję [Wskazówki dot. wdrożenia](#deployment-guidelines) w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="55a9a-157">For more information, see the [Deployment guidelines](#deployment-guidelines) section later in this topic.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="55a9a-158">Przykładowe scenariusze</span><span class="sxs-lookup"><span data-stu-id="55a9a-158">Example scenarios</span></span>

<span data-ttu-id="55a9a-159">Poniższe przykładowe scenariusze przedstawiają sposób pracy z informacjami o odbiorcach w POS dla Polski.</span><span class="sxs-lookup"><span data-stu-id="55a9a-159">The following example scenarios show how to work with customer information in POS for Poland.</span></span>

### <a name="scenario-1-make-a-sale-to-an-anonymous-customer"></a><span data-ttu-id="55a9a-160">Scenariusz 1: dokonać sprzedaży anonimowemu odbiorcy</span><span class="sxs-lookup"><span data-stu-id="55a9a-160">Scenario 1: Make a sale to an anonymous customer</span></span>

1. <span data-ttu-id="55a9a-161">Zaloguj się w POS.</span><span class="sxs-lookup"><span data-stu-id="55a9a-161">Sign in to POS.</span></span>
1. <span data-ttu-id="55a9a-162">Dodaj pozycje do koszyka.</span><span class="sxs-lookup"><span data-stu-id="55a9a-162">Add items to the cart.</span></span>
1. <span data-ttu-id="55a9a-163">Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie wybierz **Wprowadź ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-163">Select **Add customer information**, and then select **Enter manually**.</span></span>
1. <span data-ttu-id="55a9a-164">Wprowadź numer VAT odbiorcy, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-164">Enter the customer's VAT number, and then select **OK**.</span></span>
1. <span data-ttu-id="55a9a-165">Zarejestruj płatności dla transakcji, a następnie zakończ transakcję.</span><span class="sxs-lookup"><span data-stu-id="55a9a-165">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="55a9a-166">Sprawdź, czy wydrukowany paragon zawiera numer VAT odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="55a9a-166">Verify that the printed receipt contains the customer's VAT number.</span></span>

### <a name="scenario-2-make-a-sale-to-a-new-named-customer"></a><span data-ttu-id="55a9a-167">Scenariusz 2: dokonać sprzedaży nowemu, nazwanemu odbiorcy</span><span class="sxs-lookup"><span data-stu-id="55a9a-167">Scenario 2: Make a sale to a new named customer</span></span>

1. <span data-ttu-id="55a9a-168">Zaloguj się w POS.</span><span class="sxs-lookup"><span data-stu-id="55a9a-168">Sign in to POS.</span></span>
1. <span data-ttu-id="55a9a-169">Dodaj pozycje do koszyka.</span><span class="sxs-lookup"><span data-stu-id="55a9a-169">Add items to the cart.</span></span>
1. <span data-ttu-id="55a9a-170">Wybierz opcję **Dodaj odbiorcę**, a następnie wybierz **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-170">Select **Add customer**, and then select **New**.</span></span>
1. <span data-ttu-id="55a9a-171">Ustaw atrybuty nowego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="55a9a-171">Specify the new customer's attributes.</span></span>
1. <span data-ttu-id="55a9a-172">Wybierz **Stwórz nowy adres**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-172">Select **Create a new address**.</span></span> <span data-ttu-id="55a9a-173">Następnie określ informacje kontaktowe nowego odbiorcy oraz adres.</span><span class="sxs-lookup"><span data-stu-id="55a9a-173">Then specify the new customer's contact information and an address.</span></span>
1. <span data-ttu-id="55a9a-174">W polu **Numer VAT** wprowadź numer VAT odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="55a9a-174">In the **VAT number** field, enter the customer's VAT number.</span></span>
1. <span data-ttu-id="55a9a-175">Zapisz rekord odbiorcy i rekord adresu odbiorcy, a następnie dodaj odbiorcę do transakcji.</span><span class="sxs-lookup"><span data-stu-id="55a9a-175">Save the customer record and the customer address record, and add the customer to the transaction.</span></span>
1. <span data-ttu-id="55a9a-176">Zarejestruj płatności dla transakcji, a następnie zakończ transakcję.</span><span class="sxs-lookup"><span data-stu-id="55a9a-176">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="55a9a-177">Ponieważ zostało aktywowane zapytanie o informacje o odbiorcy, ale informacje o odbiorcy nie zostały dodane do transakcji, zostanie otwarte okno dialogowe **Wprowadź informacje o odbiorcy** .</span><span class="sxs-lookup"><span data-stu-id="55a9a-177">Because the inquiry for customer information has been activated, but customer information hasn't been added to the transaction, the **Enter customer information** dialog box is opened.</span></span> <span data-ttu-id="55a9a-178">Wybierz opcję **Tak**, a następnie wybierz opcję **Kopiuj z odbiorcy transakcji**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-178">Select **Yes**, and then select **Copy from transaction customer**.</span></span>
1. <span data-ttu-id="55a9a-179">Sprawdź numer VAT odbiorcy, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-179">Verify the customer's VAT number, and then select **OK**.</span></span>
1. <span data-ttu-id="55a9a-180">Sprawdź, czy wydrukowany paragon zawiera numer VAT odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="55a9a-180">Verify that the printed receipt contains the customer's VAT number.</span></span>

> [!NOTE]
> <span data-ttu-id="55a9a-181">Jeśli trzeba określić innego odbiorcę dla transakcji, należy wyczyścić informacje o odbiorcy, a następnie skopiować je ponownie po dodaniu nowego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="55a9a-181">If you must specify a different customer for the transaction, you must clear the customer information and then copy it again after the new customer is added.</span></span>

### <a name="scenario-3-change-the-customer-information-for-a-sale-to-a-named-customer"></a><span data-ttu-id="55a9a-182">Scenariusz 3: zmiana informacji o odbiorcy sprzedaży na nazwanego odbiorcę</span><span class="sxs-lookup"><span data-stu-id="55a9a-182">Scenario 3: Change the customer information for a sale to a named customer</span></span>

1. <span data-ttu-id="55a9a-183">Zaloguj się w POS.</span><span class="sxs-lookup"><span data-stu-id="55a9a-183">Sign in to POS.</span></span>
1. <span data-ttu-id="55a9a-184">Dodaj pozycje do koszyka.</span><span class="sxs-lookup"><span data-stu-id="55a9a-184">Add items to the cart.</span></span>
1. <span data-ttu-id="55a9a-185">Wybierz **Dodaj odbiorcę**, a następnie wybierz konto odbiorcy i dodaj je do transakcji.</span><span class="sxs-lookup"><span data-stu-id="55a9a-185">Select **Add customer**, and then select a customer account to add it to the transaction.</span></span>
1. <span data-ttu-id="55a9a-186">Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie wybierz opcję **Kopiuj z odbiorcy transakcji**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-186">Select **Add customer information**, and then select **Copy from transaction customer**.</span></span>
1. <span data-ttu-id="55a9a-187">Sprawdź numer VAT odbiorcy, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-187">Verify the customer's VAT number, and then select **OK**.</span></span>
1. <span data-ttu-id="55a9a-188">Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie kliknij **Wyczyść**, aby wyczyścić informacje o odbiorcy z transakcji.</span><span class="sxs-lookup"><span data-stu-id="55a9a-188">Select **Add customer information**, and then select **Clear** to clear the customer information from the transaction.</span></span>
1. <span data-ttu-id="55a9a-189">Wybierz opcję **Dodaj informacje o odbiorcy**, a następnie wybierz **Wprowadź ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-189">Select **Add customer information**, and then select **Enter manually**.</span></span>
1. <span data-ttu-id="55a9a-190">Podaj numer VAT odbiorcy, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-190">Specify the customer's VAT number, and then select **OK**.</span></span>
1. <span data-ttu-id="55a9a-191">Zarejestruj płatności dla transakcji, a następnie zakończ transakcję.</span><span class="sxs-lookup"><span data-stu-id="55a9a-191">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="55a9a-192">Sprawdź, czy wydrukowany paragon zawiera numer VAT odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="55a9a-192">Verify that the printed receipt contains the customer's VAT number.</span></span>

## <a name="deployment-guidelines"></a><span data-ttu-id="55a9a-193">Wskazówki dotyczące wdrażania</span><span class="sxs-lookup"><span data-stu-id="55a9a-193">Deployment guidelines</span></span>

<span data-ttu-id="55a9a-194">Ta sekcja zawiera wskazówki dotyczące wdrażania umożliwiające zarządzanie informacjami o klientach w lokalizacji Dynamics 365 Commerce dla Polski.</span><span class="sxs-lookup"><span data-stu-id="55a9a-194">This section provides deployment guidance for enabling customer information management in the localization of Dynamics 365 Commerce for Poland.</span></span>

> [!NOTE]
> <span data-ttu-id="55a9a-195">Niektóre kroki opisane w tych procedurach różnią się w zależności od używanej wersji produktu.</span><span class="sxs-lookup"><span data-stu-id="55a9a-195">Some steps in these procedures vary, depending on the product version you're using.</span></span> <span data-ttu-id="55a9a-196">Aby uzyskać więcej informacji, zobacz [Nowości i zmiany w rozwiązaniu Dynamics 365 for Retail](../get-started/whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="55a9a-196">For more information, see [What's new or changed in Dynamics 365 for Retail](../get-started/whats-new.md).</span></span>
>
> <span data-ttu-id="55a9a-197">Jeśli chcesz włączyć integrację POS z drukarkami fiskalnymi w Polsce, a w szczególności, jeśli chcesz drukować numery podatku VAT od odbiorców na paragonach fiskalnych, musisz wdrożyć [próbkę integracji z drukarką fiskalną dla Polski](emea-pol-fpi-sample.md).</span><span class="sxs-lookup"><span data-stu-id="55a9a-197">If you want to enable the integration of POS with fiscal printers for Poland, and specifically if you want to print customer VAT numbers on fiscal receipts, you must deploy the [fiscal printer integration sample for Poland](emea-pol-fpi-sample.md).</span></span>

### <a name="update-customizations"></a><span data-ttu-id="55a9a-198">Dostosowanie aktualizacji</span><span class="sxs-lookup"><span data-stu-id="55a9a-198">Update customizations</span></span>

<span data-ttu-id="55a9a-199">Aby zaktualizować dostosowania, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="55a9a-199">Follow these steps to update customizations.</span></span>

# <a name="retail-1007-and-later"></a>[<span data-ttu-id="55a9a-200">Wersja 10.0.7 Retail i nowsze</span><span class="sxs-lookup"><span data-stu-id="55a9a-200">Retail 10.0.7 and later</span></span>](#tab/retail-10-0-7)

<span data-ttu-id="55a9a-201">Jeśli dowolne dostosowania zawierają obsługę żądań dla `SaveCartRequest` lub `CreateSalesOrderServiceRequest`:</span><span class="sxs-lookup"><span data-stu-id="55a9a-201">If any of your customizations include request handlers for the `SaveCartRequest` or `CreateSalesOrderServiceRequest` requests:</span></span>

1. <span data-ttu-id="55a9a-202">Znajdź obsługę żądania `SaveCartRequest`.</span><span class="sxs-lookup"><span data-stu-id="55a9a-202">Find the request handler for `SaveCartRequest`.</span></span>
1. <span data-ttu-id="55a9a-203">Znajdź wiersz kodu, w którym jest uruchomiona oryginalna obsługa żądania.</span><span class="sxs-lookup"><span data-stu-id="55a9a-203">Find the line of code that runs the original request handler.</span></span>
1. <span data-ttu-id="55a9a-204">Przed wywołaniem oryginalnego programu obsługi żądań dodaj następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="55a9a-204">Add the following lines before calling the original request handler:</span></span>

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland.Services;

    ...

    new TaxRegistrationIdFiscalCustomerService().Execute(request);
    ```

1. <span data-ttu-id="55a9a-205">Znajdź obsługę żądania `CreateSalesOrderServiceRequest`.</span><span class="sxs-lookup"><span data-stu-id="55a9a-205">Find the request handler for `CreateSalesOrderServiceRequest`.</span></span>
1. <span data-ttu-id="55a9a-206">Znajdź wiersz kodu, w którym jest uruchomiona oryginalna obsługa żądania.</span><span class="sxs-lookup"><span data-stu-id="55a9a-206">Find the line of code that runs the original request handler.</span></span>
1. <span data-ttu-id="55a9a-207">Zamień ją na następujący kod:</span><span class="sxs-lookup"><span data-stu-id="55a9a-207">Replace it with the following code:</span></span>

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland.Services;

    ...

    return new TaxRegistrationIdFiscalCustomerService().Execute(request);
    ```

# <a name="retail-10012-and-later"></a>[<span data-ttu-id="55a9a-208">Wersja 10.0.12 Retail i nowsze</span><span class="sxs-lookup"><span data-stu-id="55a9a-208">Retail 10.0.12 and later</span></span>](#tab/retail-10-0-12)

<span data-ttu-id="55a9a-209">Jeśli dostosowania mają odwołania do usługi `TaxRegistrationIdFiscalCustomerService`, muszą zostać usunięte.</span><span class="sxs-lookup"><span data-stu-id="55a9a-209">If customizations have references to the `TaxRegistrationIdFiscalCustomerService` service, they must be removed.</span></span>

---

### <a name="update-a-development-environment"></a><span data-ttu-id="55a9a-210">Aktualizacja środowiska projektowego</span><span class="sxs-lookup"><span data-stu-id="55a9a-210">Update a development environment</span></span>

<span data-ttu-id="55a9a-211">Aby zaktualizować środowisko programistyczne, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="55a9a-211">Follow these steps to update a development environment.</span></span>

#### <a name="crt-extension-components"></a><span data-ttu-id="55a9a-212">CRT komponenty rozszerzenia</span><span class="sxs-lookup"><span data-stu-id="55a9a-212">CRT extension components</span></span>

1. <span data-ttu-id="55a9a-213">Znajdź plik konfiguracji rozszerzenia dla środowiska uruchomieniowego Commerce Runtime (CRT):</span><span class="sxs-lookup"><span data-stu-id="55a9a-213">Find the extension configuration file for the Commerce runtime (CRT):</span></span>

    - <span data-ttu-id="55a9a-214">**Commerce Scale Unit:** znajdź plik **CommerceRuntime.Ext.config** w folderze **bin\\ext** w lokalizacji strony Microsoft Internet Information Services (IIS) Commerce Scale Unit site location.</span><span class="sxs-lookup"><span data-stu-id="55a9a-214">**Commerce Scale Unit:** Find the **CommerceRuntime.Ext.config** file in the **bin\\ext** folder under the Microsoft Internet Information Services (IIS) Commerce Scale Unit site location.</span></span>
    - <span data-ttu-id="55a9a-215">**Lokalne wystąpienie CRT na Modern POS:** znajdź plik **CommerceRuntime.MPOSOffline.Ext.config** w lokalizacji brokera lokalnego klienta CRT.</span><span class="sxs-lookup"><span data-stu-id="55a9a-215">**Local CRT on Modern POS:** Find the **CommerceRuntime.MPOSOffline.Ext.config** file under the local CRT client broker location.</span></span>

1. <span data-ttu-id="55a9a-216">Zarejestruj zmianę rozszerzenia CRT w pliku konfiguracji rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="55a9a-216">Register the CRT extension in the extension configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland" />
    ```

    > [!WARNING]
    > <span data-ttu-id="55a9a-217">**Nie należy** edytować plików CommerceRuntime.config i CommerceRuntime.MPOSOffline.config.</span><span class="sxs-lookup"><span data-stu-id="55a9a-217">Do **not** edit the CommerceRuntime.config and CommerceRuntime.MPOSOffline.config files.</span></span> <span data-ttu-id="55a9a-218">Pliki te nie są przeznaczone do żadnych dostosowań.</span><span class="sxs-lookup"><span data-stu-id="55a9a-218">These files aren't intended for any customizations.</span></span>

#### <a name="modern-pos-extension-components"></a><span data-ttu-id="55a9a-219">Komponenty rozszerzenia nowoczesnego POS</span><span class="sxs-lookup"><span data-stu-id="55a9a-219">Modern POS extension components</span></span>

<span data-ttu-id="55a9a-220">Aby udostępnić rozszerzenie TaxRegistrationId.PL, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="55a9a-220">Follow these steps to make the TaxRegistrationId.PL extension available.</span></span>

1. <span data-ttu-id="55a9a-221">Otwórz rozwiązanie w **RetailSdk\\POS\\ModernPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-221">Open the solution at **RetailSdk\\POS\\ModernPOS.sln**.</span></span>
1. <span data-ttu-id="55a9a-222">W **POS.Extensions\\extensions.json**, włącz rozszerzenie.</span><span class="sxs-lookup"><span data-stu-id="55a9a-222">In **POS.Extensions\\extensions.json**, turn on the extension.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.PL"
            }
        ]
    }
    ```

1. <span data-ttu-id="55a9a-223">Stwórz rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="55a9a-223">Build the solution.</span></span>
1. <span data-ttu-id="55a9a-224">Otwórz Modern POS i przetestuj te funkcje.</span><span class="sxs-lookup"><span data-stu-id="55a9a-224">Open Modern POS, and test the functionality.</span></span>

#### <a name="cloud-pos-extension-components"></a><span data-ttu-id="55a9a-225">Komponenty rozszerzenia Cloud POS</span><span class="sxs-lookup"><span data-stu-id="55a9a-225">Cloud POS extension components</span></span>

<span data-ttu-id="55a9a-226">Aby udostępnić rozszerzenie TaxRegistrationId.PL, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="55a9a-226">Follow these steps to make the TaxRegistrationId.PL extension available.</span></span>

1. <span data-ttu-id="55a9a-227">Otwórz rozwiązanie w **RetailSdk\\POS\\CloudPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-227">Open the solution at **RetailSdk\\POS\\CloudPOS.sln**.</span></span>
1. <span data-ttu-id="55a9a-228">W **POS.Extensions\\extensions.json**, włącz rozszerzenie.</span><span class="sxs-lookup"><span data-stu-id="55a9a-228">In **POS.Extensions\\extensions.json**, turn on the extension.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.PL"
            }
        ]
    }
    ```

1. <span data-ttu-id="55a9a-229">Stwórz rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="55a9a-229">Build the solution.</span></span>
1. <span data-ttu-id="55a9a-230">Otwórz Cloud POS i przetestuj te funkcje.</span><span class="sxs-lookup"><span data-stu-id="55a9a-230">Open Cloud POS, and test the functionality.</span></span>

### <a name="update-a-production-environment"></a><span data-ttu-id="55a9a-231">Zaktualizuj środowisko produkcyjne</span><span class="sxs-lookup"><span data-stu-id="55a9a-231">Update a production environment</span></span>

<span data-ttu-id="55a9a-232">Wykonaj następujące kroki, aby utworzyć możliwe do wdrożenia pakiety, które zawierają składniki Commerce i aby stosować te pakiety w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="55a9a-232">Follow these steps to create deployable packages that contain Commerce components, and to apply the packages in a production environment.</span></span>

1. <span data-ttu-id="55a9a-233">W plikach konfiguracji **CommerceRuntime.Ext.config** i **CommerceRuntime.MPOSOffline.Ext.config**, w folderze **RetailSdk\\Assets** dodaj następujący wiersz w sekcji **Kompozycja**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-233">In the **CommerceRuntime.Ext.config** and **CommerceRuntime.MPOSOffline.Ext.config** configuration files under the **RetailSdk\\Assets** folder, add the following lines to the **composition** section.</span></span>

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdPoland" />
    ```

1. <span data-ttu-id="55a9a-234">Włącz rozszerzenie POS **TaxRegistrationId.PL**.</span><span class="sxs-lookup"><span data-stu-id="55a9a-234">Turn on the **TaxRegistrationId.PL** POS extension.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.PL"
            }
        ]
    }
    ```

1. <span data-ttu-id="55a9a-235">Uruchom narzędzie **msbulid** dla całego zestawu Retail Software Development Kit (SDK), aby utworzyć pakiety do wdrożenia.</span><span class="sxs-lookup"><span data-stu-id="55a9a-235">Run **msbuild** for the whole Retail software development kit (SDK) to create deployable packages.</span></span>
1. <span data-ttu-id="55a9a-236">Zastosuj pakiety za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS) lub ręcznie.</span><span class="sxs-lookup"><span data-stu-id="55a9a-236">Apply the packages via Microsoft Dynamics Lifecycle Services (LCS) or manually.</span></span> <span data-ttu-id="55a9a-237">Aby uzyskać więcej informacji, zobacz [Pakiety Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="55a9a-237">For more information, see [Retail SDK packaging](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span></span>
