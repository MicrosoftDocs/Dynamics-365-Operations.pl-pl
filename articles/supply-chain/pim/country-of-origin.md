---
title: Kraj pochodzenia
description: Wiele organizacji wystawia certyfikaty swoim dostawcom w celu zapewnienia, że produkty spełniają określone standardy certyfikacji. Te certyfikaty często zależą od kraju pochodzenia. Ten temat zawiera informacje o funkcji kraju pochodzenia, która pozwala połączyć produkt z krajem pochodzenia i śledzić certyfikaty produktów.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: bb35770f32c21a685b21a41dc7c369ee01fe3891
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243304"
---
# <a name="country-of-origin"></a><span data-ttu-id="3d2be-105">Kraj pochodzenia</span><span class="sxs-lookup"><span data-stu-id="3d2be-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="3d2be-106">Wiele organizacji wystawia certyfikaty swoim dostawcom w celu zapewnienia, że produkty spełniają określone standardy certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="3d2be-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="3d2be-107">Te certyfikaty często zależą od kraju pochodzenia.</span><span class="sxs-lookup"><span data-stu-id="3d2be-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="3d2be-108">Funkcja kraju pochodzenia umożliwia powiązanie produktu z jego krajem pochodzenia i śledzenie jego certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="3d2be-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="turn-on-the-country-of-origin-feature"></a><span data-ttu-id="3d2be-109">Włączanie funkcji informującej o kraju pochodzenia</span><span class="sxs-lookup"><span data-stu-id="3d2be-109">Turn on the country of origin feature</span></span>

<span data-ttu-id="3d2be-110">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="3d2be-110">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="3d2be-111">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją.</span><span class="sxs-lookup"><span data-stu-id="3d2be-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="3d2be-112">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="3d2be-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="3d2be-113">**Moduł:** *Zarządzanie informacjami o produktach*</span><span class="sxs-lookup"><span data-stu-id="3d2be-113">**Module:** *Product information management*</span></span>
- <span data-ttu-id="3d2be-114">**Nazwa funkcji:** *Funkcja zarządzania krajem pochodzenia*</span><span class="sxs-lookup"><span data-stu-id="3d2be-114">**Feature name:** *Country of origin management feature*</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="3d2be-115">Konfigurowanie krajów źródłowych i docelowych</span><span class="sxs-lookup"><span data-stu-id="3d2be-115">Configure source and destination countries</span></span>

<span data-ttu-id="3d2be-116">Przed wystawieniem certyfikatu dla produktu należy połączyć produkt z krajem docelowym i krajem pochodzenia.</span><span class="sxs-lookup"><span data-stu-id="3d2be-116">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="3d2be-117">Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Zgodność produktu \> Kraj pochodzenia \> Reguły dotyczące kraju pochodzenia**.</span><span class="sxs-lookup"><span data-stu-id="3d2be-117">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="3d2be-118">Wybierz ustawienia istniejącego kraju, aby je edytować, lub wybierz opcję **Nowy** w Okienku akcji, aby utworzyć nowe ustawienia kraju.</span><span class="sxs-lookup"><span data-stu-id="3d2be-118">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="3d2be-119">Ustaw następujące wartości dla wybranego lub nowego kraju.</span><span class="sxs-lookup"><span data-stu-id="3d2be-119">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="3d2be-120">Pole</span><span class="sxs-lookup"><span data-stu-id="3d2be-120">Field</span></span> | <span data-ttu-id="3d2be-121">opis</span><span class="sxs-lookup"><span data-stu-id="3d2be-121">Description</span></span> |
    |---|---|
    | <span data-ttu-id="3d2be-122">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="3d2be-122">Item number</span></span> | <span data-ttu-id="3d2be-123">Wybierz numer pozycji produktu.</span><span class="sxs-lookup"><span data-stu-id="3d2be-123">Select the item number of the product.</span></span> |
    | <span data-ttu-id="3d2be-124">Kraj przeznaczenia</span><span class="sxs-lookup"><span data-stu-id="3d2be-124">Destination country</span></span> | <span data-ttu-id="3d2be-125">Umożliwia wybranie kraju, do którego jest wysyłany produkt.</span><span class="sxs-lookup"><span data-stu-id="3d2be-125">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="3d2be-126">Kraj pochodzenia</span><span class="sxs-lookup"><span data-stu-id="3d2be-126">Origin country</span></span> | <span data-ttu-id="3d2be-127">Umożliwia wybranie kraju, z którego jest wysyłany produkt.</span><span class="sxs-lookup"><span data-stu-id="3d2be-127">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="3d2be-128">Celem tego ustawienia jest pomoc w generowaniu raportu BOM, w którym można uwzględnić kraj pochodzenia dla każdej części, dla której określono kraje źródłowe i docelowe.</span><span class="sxs-lookup"><span data-stu-id="3d2be-128">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="3d2be-129">Ten raport pomoże Ci uzyskać całościowy obraz tego, skąd pochodzą Twoje części i dokąd zmierzają.</span><span class="sxs-lookup"><span data-stu-id="3d2be-129">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="3d2be-130">Śledź certyfikaty dostawców</span><span class="sxs-lookup"><span data-stu-id="3d2be-130">Keep track of vendor certificates</span></span>

<span data-ttu-id="3d2be-131">Strona **Certyfikaty kraju pochodzenia dostawców** służy do śledzenia certyfikatów wydawanych dostawcom.</span><span class="sxs-lookup"><span data-stu-id="3d2be-131">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="3d2be-132">Należy zdecydować, które dokumenty certyfikatów mają być wystawiane i w jaki sposób mają być zgłaszane odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="3d2be-132">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="3d2be-133">Ta funkcja ułatwia śledzenie certyfikatów użytkownika.</span><span class="sxs-lookup"><span data-stu-id="3d2be-133">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="3d2be-134">Umożliwia także określenie, czy odpowiednie numery certyfikatów mają być wyświetlane na fakturach, dokumentach dostawy i/lub potwierdzeniach zamówień.</span><span class="sxs-lookup"><span data-stu-id="3d2be-134">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="3d2be-135">Aby skonfigurować informacje o certyfikacie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3d2be-135">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="3d2be-136">Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Zgodność produktu \> Kraj pochodzenia \> Certyfikaty kraju pochodzenia dostawców**.</span><span class="sxs-lookup"><span data-stu-id="3d2be-136">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="3d2be-137">Wybierz ustawienia istniejącego certyfikatu, aby je edytować, lub wybierz opcję **Nowy** w Okienku akcji, aby utworzyć nowe ustawienia certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="3d2be-137">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="3d2be-138">Ustaw następujące ustawienia dla wybranego lub nowego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="3d2be-138">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="3d2be-139">Pole</span><span class="sxs-lookup"><span data-stu-id="3d2be-139">Field</span></span> | <span data-ttu-id="3d2be-140">opis</span><span class="sxs-lookup"><span data-stu-id="3d2be-140">Description</span></span> |
    |---|---|
    | <span data-ttu-id="3d2be-141">Konto dostawcy</span><span class="sxs-lookup"><span data-stu-id="3d2be-141">Vendor account</span></span> | <span data-ttu-id="3d2be-142">Umożliwia wybranie dostawcy, dla którego został wystawiony dany certyfikat.</span><span class="sxs-lookup"><span data-stu-id="3d2be-142">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="3d2be-143">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="3d2be-143">Item number</span></span> | <span data-ttu-id="3d2be-144">Umożliwia wybranie pozycji, dla której został wystawiony dany certyfikat.</span><span class="sxs-lookup"><span data-stu-id="3d2be-144">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="3d2be-145">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="3d2be-145">Country/region</span></span> | <span data-ttu-id="3d2be-146">Docelowy kraj lub region, w którym musisz skorzystać z tego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="3d2be-146">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="3d2be-147">Numer certyfikacji</span><span class="sxs-lookup"><span data-stu-id="3d2be-147">Certificate number</span></span> | <span data-ttu-id="3d2be-148">Umożliwia wprowadzenie numeru identyfikacyjnego wystawionego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="3d2be-148">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="3d2be-149">Obowiązują</span><span class="sxs-lookup"><span data-stu-id="3d2be-149">Effective</span></span> | <span data-ttu-id="3d2be-150">Umożliwia wybór pierwszej daty ważności bieżącego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="3d2be-150">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="3d2be-151">Data ważności</span><span class="sxs-lookup"><span data-stu-id="3d2be-151">Expiration</span></span> | <span data-ttu-id="3d2be-152">Umożliwia wybór ostatniej daty ważności bieżącego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="3d2be-152">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="3d2be-153">Drukowanie na fakturze</span><span class="sxs-lookup"><span data-stu-id="3d2be-153">Print on invoice</span></span> | <span data-ttu-id="3d2be-154">To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na fakturach, które są adresowane do określonego kraju w ciągu określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="3d2be-154">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="3d2be-155">Drukowanie na dokumencie dostawy</span><span class="sxs-lookup"><span data-stu-id="3d2be-155">Print on packing slip</span></span> | <span data-ttu-id="3d2be-156">To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na dokumencie dostawy, które są adresowane do określonego kraju w ciągu określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="3d2be-156">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="3d2be-157">Drukowanie na zamówieniach sprzedaży</span><span class="sxs-lookup"><span data-stu-id="3d2be-157">Print on sales order</span></span> | <span data-ttu-id="3d2be-158">To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na zamówieniu sprzedaży, które są adresowane do określonego kraju w ciągu określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="3d2be-158">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="3d2be-159">Uwzględnij kraj pochodzenia w raportach BOM</span><span class="sxs-lookup"><span data-stu-id="3d2be-159">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="3d2be-160">Podczas generowania raportu BOM można uwzględnić kraj pochodzenia dla każdej części, dla której określono kraje źródłowe i docelowe na stronie **Reguły dotyczące kraju pochodzenia**.</span><span class="sxs-lookup"><span data-stu-id="3d2be-160">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="3d2be-161">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="3d2be-161">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="3d2be-162">Wybierz lub utwórz produkt, aby otworzyć jego stronę **Szczegółów zwolnionego produktu**.</span><span class="sxs-lookup"><span data-stu-id="3d2be-162">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="3d2be-163">W okienku akcji na karcie **Konstruuj** w grupie **BOM** wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="3d2be-163">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="3d2be-164">Na wyświetlonej stronie listy w okienku akcji wybierz **BOM \> Drukuj**.</span><span class="sxs-lookup"><span data-stu-id="3d2be-164">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="3d2be-165">W oknie dialogowym **Wiersze listy składowej** w polu **Kraj docelowy** określ kraj docelowy, który ma być wyświetlany w raporcie.</span><span class="sxs-lookup"><span data-stu-id="3d2be-165">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="3d2be-166">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d2be-166">Select **OK**.</span></span>

<span data-ttu-id="3d2be-167">Raport zawierający informacje o kraju pochodzenia każdej części jest generowany i pokazywany.</span><span class="sxs-lookup"><span data-stu-id="3d2be-167">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="3d2be-168">Oto przykład tabeli raportu.</span><span class="sxs-lookup"><span data-stu-id="3d2be-168">Here is an example of the report.</span></span>

<span data-ttu-id="3d2be-169">![Raport kraju pochodzenia](media/country-of-origin-report.png "Raport kraju pochodzenia")</span><span class="sxs-lookup"><span data-stu-id="3d2be-169">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]