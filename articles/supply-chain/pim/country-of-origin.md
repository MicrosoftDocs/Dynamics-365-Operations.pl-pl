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
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fd234c57bf9893e9b8bcfa5ada7439a642f7a288
ms.sourcegitcommit: 70d0b4e6bdacc15ec75935550ae55fc02cb79624
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2020
ms.locfileid: "3596266"
---
# <a name="country-of-origin"></a><span data-ttu-id="746e3-105">Kraj pochodzenia</span><span class="sxs-lookup"><span data-stu-id="746e3-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="746e3-106">Wiele organizacji wystawia certyfikaty swoim dostawcom w celu zapewnienia, że produkty spełniają określone standardy certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="746e3-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="746e3-107">Te certyfikaty często zależą od kraju pochodzenia.</span><span class="sxs-lookup"><span data-stu-id="746e3-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="746e3-108">Funkcja kraju pochodzenia umożliwia powiązanie produktu z jego krajem pochodzenia i śledzenie jego certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="746e3-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="746e3-109">Konfigurowanie krajów źródłowych i docelowych</span><span class="sxs-lookup"><span data-stu-id="746e3-109">Configure source and destination countries</span></span>

<span data-ttu-id="746e3-110">Przed wystawieniem certyfikatu dla produktu należy połączyć produkt z krajem docelowym i krajem pochodzenia.</span><span class="sxs-lookup"><span data-stu-id="746e3-110">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="746e3-111">Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Zgodność produktu \> Kraj pochodzenia \> Reguły dotyczące kraju pochodzenia**.</span><span class="sxs-lookup"><span data-stu-id="746e3-111">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="746e3-112">Wybierz ustawienia istniejącego kraju, aby je edytować, lub wybierz opcję **Nowy** w Okienku akcji, aby utworzyć nowe ustawienia kraju.</span><span class="sxs-lookup"><span data-stu-id="746e3-112">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="746e3-113">Ustaw następujące wartości dla wybranego lub nowego kraju.</span><span class="sxs-lookup"><span data-stu-id="746e3-113">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="746e3-114">Pole</span><span class="sxs-lookup"><span data-stu-id="746e3-114">Field</span></span> | <span data-ttu-id="746e3-115">opis</span><span class="sxs-lookup"><span data-stu-id="746e3-115">Description</span></span> |
    |---|---|
    | <span data-ttu-id="746e3-116">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="746e3-116">Item number</span></span> | <span data-ttu-id="746e3-117">Wybierz numer pozycji produktu.</span><span class="sxs-lookup"><span data-stu-id="746e3-117">Select the item number of the product.</span></span> |
    | <span data-ttu-id="746e3-118">Kraj przeznaczenia</span><span class="sxs-lookup"><span data-stu-id="746e3-118">Destination country</span></span> | <span data-ttu-id="746e3-119">Umożliwia wybranie kraju, do którego jest wysyłany produkt.</span><span class="sxs-lookup"><span data-stu-id="746e3-119">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="746e3-120">Kraj pochodzenia</span><span class="sxs-lookup"><span data-stu-id="746e3-120">Origin country</span></span> | <span data-ttu-id="746e3-121">Umożliwia wybranie kraju, z którego jest wysyłany produkt.</span><span class="sxs-lookup"><span data-stu-id="746e3-121">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="746e3-122">Celem tego ustawienia jest pomoc w generowaniu raportu BOM, w którym można uwzględnić kraj pochodzenia dla każdej części, dla której określono kraje źródłowe i docelowe.</span><span class="sxs-lookup"><span data-stu-id="746e3-122">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="746e3-123">Ten raport pomoże Ci uzyskać całościowy obraz tego, skąd pochodzą Twoje części i dokąd zmierzają.</span><span class="sxs-lookup"><span data-stu-id="746e3-123">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="746e3-124">Śledź certyfikaty dostawców</span><span class="sxs-lookup"><span data-stu-id="746e3-124">Keep track of vendor certificates</span></span>

<span data-ttu-id="746e3-125">Strona **Certyfikaty kraju pochodzenia dostawców** służy do śledzenia certyfikatów wydawanych dostawcom.</span><span class="sxs-lookup"><span data-stu-id="746e3-125">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="746e3-126">Należy zdecydować, które dokumenty certyfikatów mają być wystawiane i w jaki sposób mają być zgłaszane odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="746e3-126">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="746e3-127">Ta funkcja ułatwia śledzenie certyfikatów użytkownika.</span><span class="sxs-lookup"><span data-stu-id="746e3-127">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="746e3-128">Umożliwia także określenie, czy odpowiednie numery certyfikatów mają być wyświetlane na fakturach, dokumentach dostawy i/lub potwierdzeniach zamówień.</span><span class="sxs-lookup"><span data-stu-id="746e3-128">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="746e3-129">Aby skonfigurować informacje o certyfikacie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="746e3-129">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="746e3-130">Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Zgodność produktu \> Kraj pochodzenia \> Certyfikaty kraju pochodzenia dostawców**.</span><span class="sxs-lookup"><span data-stu-id="746e3-130">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="746e3-131">Wybierz ustawienia istniejącego certyfikatu, aby je edytować, lub wybierz opcję **Nowy** w Okienku akcji, aby utworzyć nowe ustawienia certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="746e3-131">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="746e3-132">Ustaw następujące ustawienia dla wybranego lub nowego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="746e3-132">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="746e3-133">Pole</span><span class="sxs-lookup"><span data-stu-id="746e3-133">Field</span></span> | <span data-ttu-id="746e3-134">opis</span><span class="sxs-lookup"><span data-stu-id="746e3-134">Description</span></span> |
    |---|---|
    | <span data-ttu-id="746e3-135">Konto dostawcy</span><span class="sxs-lookup"><span data-stu-id="746e3-135">Vendor account</span></span> | <span data-ttu-id="746e3-136">Umożliwia wybranie dostawcy, dla którego został wystawiony dany certyfikat.</span><span class="sxs-lookup"><span data-stu-id="746e3-136">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="746e3-137">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="746e3-137">Item number</span></span> | <span data-ttu-id="746e3-138">Umożliwia wybranie pozycji, dla której został wystawiony dany certyfikat.</span><span class="sxs-lookup"><span data-stu-id="746e3-138">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="746e3-139">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="746e3-139">Country/region</span></span> | <span data-ttu-id="746e3-140">Docelowy kraj lub region, w którym musisz skorzystać z tego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="746e3-140">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="746e3-141">Numer certyfikacji</span><span class="sxs-lookup"><span data-stu-id="746e3-141">Certificate number</span></span> | <span data-ttu-id="746e3-142">Umożliwia wprowadzenie numeru identyfikacyjnego wystawionego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="746e3-142">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="746e3-143">Obowiązują</span><span class="sxs-lookup"><span data-stu-id="746e3-143">Effective</span></span> | <span data-ttu-id="746e3-144">Umożliwia wybór pierwszej daty ważności bieżącego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="746e3-144">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="746e3-145">Data ważności</span><span class="sxs-lookup"><span data-stu-id="746e3-145">Expiration</span></span> | <span data-ttu-id="746e3-146">Umożliwia wybór ostatniej daty ważności bieżącego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="746e3-146">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="746e3-147">Drukowanie na fakturze</span><span class="sxs-lookup"><span data-stu-id="746e3-147">Print on invoice</span></span> | <span data-ttu-id="746e3-148">To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na fakturach, które są adresowane do określonego kraju w ciągu określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="746e3-148">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="746e3-149">Drukowanie na dokumencie dostawy</span><span class="sxs-lookup"><span data-stu-id="746e3-149">Print on packing slip</span></span> | <span data-ttu-id="746e3-150">To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na dokumencie dostawy, które są adresowane do określonego kraju w ciągu określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="746e3-150">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="746e3-151">Drukowanie na zamówieniach sprzedaży</span><span class="sxs-lookup"><span data-stu-id="746e3-151">Print on sales order</span></span> | <span data-ttu-id="746e3-152">To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na zamówieniu sprzedaży, które są adresowane do określonego kraju w ciągu określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="746e3-152">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="746e3-153">Uwzględnij kraj pochodzenia w raportach BOM</span><span class="sxs-lookup"><span data-stu-id="746e3-153">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="746e3-154">Podczas generowania raportu BOM można uwzględnić kraj pochodzenia dla każdej części, dla której określono kraje źródłowe i docelowe na stronie **Reguły dotyczące kraju pochodzenia**.</span><span class="sxs-lookup"><span data-stu-id="746e3-154">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="746e3-155">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="746e3-155">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="746e3-156">Wybierz lub utwórz produkt, aby otworzyć jego stronę **Szczegółów zwolnionego produktu**.</span><span class="sxs-lookup"><span data-stu-id="746e3-156">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="746e3-157">W okienku akcji na karcie **Konstruuj** w grupie **BOM** wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="746e3-157">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="746e3-158">Na wyświetlonej stronie listy w okienku akcji wybierz **BOM \> Drukuj**.</span><span class="sxs-lookup"><span data-stu-id="746e3-158">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="746e3-159">W oknie dialogowym **Wiersze listy składowej** w polu **Kraj docelowy** określ kraj docelowy, który ma być wyświetlany w raporcie.</span><span class="sxs-lookup"><span data-stu-id="746e3-159">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="746e3-160">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="746e3-160">Select **OK**.</span></span>

<span data-ttu-id="746e3-161">Raport zawierający informacje o kraju pochodzenia każdej części jest generowany i pokazywany.</span><span class="sxs-lookup"><span data-stu-id="746e3-161">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="746e3-162">Oto przykład tabeli raportu.</span><span class="sxs-lookup"><span data-stu-id="746e3-162">Here is an example of the report.</span></span>

<span data-ttu-id="746e3-163">![Raport kraju pochodzenia](media/country-of-origin-report.png "Raport kraju pochodzenia")</span><span class="sxs-lookup"><span data-stu-id="746e3-163">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
