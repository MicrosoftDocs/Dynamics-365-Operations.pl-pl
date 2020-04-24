---
title: Importowanie katalogów dostawców
description: W tym temacie opisano proces importowania danych katalogu dostawcy.
author: mkirknel
manager: tfehr
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: mkirknel
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 35b8e2a87708c88b12c5c7605a7977712a35a0f4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207386"
---
# <a name="import-vendor-catalogs"></a><span data-ttu-id="ead6a-103">Importowanie katalogów dostawców</span><span class="sxs-lookup"><span data-stu-id="ead6a-103">Import vendor catalogs</span></span>
[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a><span data-ttu-id="ead6a-104">Importowanie katalogów dostawców</span><span class="sxs-lookup"><span data-stu-id="ead6a-104">Vendor catalogs import</span></span>

<span data-ttu-id="ead6a-105">W programie Dynamics 365 Supply Chain Management specjaliści ds. zakupów mogą tworzyć i obsługiwać katalogi, z których pracownicy firmy mogą korzystać podczas składania zamówień na towary i usługi do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="ead6a-105">In Dynamics 365 Supply Chain Management, purchasing professionals can create and maintain catalogs for company employees to use when they order items and services for internal use.</span></span> <span data-ttu-id="ead6a-106">Aby utworzyć katalog zaopatrzenia, można dodać towary i usługi, które mają być udostępnione pracownikom, importując dane katalogu produktów lub ręczne dodając dane z katalogu produktów do produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="ead6a-106">To create a procurement catalog, you can add the items and services that you want to make available to employees, either by importing the product catalog data or by manually adding the product catalog data to the product master.</span></span> 

<span data-ttu-id="ead6a-107">Można przekazać dane katalogu przesłane przez dostawcę z klienta programu Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ead6a-107">You can upload catalog data submitted by a vendor from the Microsoft Dynamics 365 client.</span></span>

<span data-ttu-id="ead6a-108">Dane produktów przesłane przez dostawcę, w postaci pliku żądania zarządzania katalogiem (CMR), muszą być w formacie pliku XML.</span><span class="sxs-lookup"><span data-stu-id="ead6a-108">The product data that a vendor submits to you, in the form of a catalog maintenance request (CMR) file, must be in XML file format.</span></span> <span data-ttu-id="ead6a-109">Plik CMR powinien zawierać szczegóły produktów dostarczanych przez dostawcę do firmy.</span><span class="sxs-lookup"><span data-stu-id="ead6a-109">The CMR file should contain the details for the products that the vendor supplies to your company.</span></span>
<span data-ttu-id="ead6a-110">''''</span><span class="sxs-lookup"><span data-stu-id="ead6a-110">''''</span></span>
## <a name="import-vendor-catalog-data"></a><span data-ttu-id="ead6a-111">Importowanie danych katalogu dostawcy</span><span class="sxs-lookup"><span data-stu-id="ead6a-111">Import vendor catalog data</span></span>
<span data-ttu-id="ead6a-112">'' Aby importować dane katalogu dostawcy, należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="ead6a-112">'' To import vendor catalog data, you must complete the following tasks:</span></span>

1.  <span data-ttu-id="ead6a-113">Skonfiguruj projekt w obszarze roboczym Zarządzanie danymi, gdzie zdefiniowano reguły mapowania danych.</span><span class="sxs-lookup"><span data-stu-id="ead6a-113">Set up a project in the Data management workspace where you have defined your data mapping rules.</span></span> <span data-ttu-id="ead6a-114">Wybierz opcję **Zarządzanie danymi**, a następnie wybierz opcję **Konfiguruj role dla projektów danych**.</span><span class="sxs-lookup"><span data-stu-id="ead6a-114">Select **Data management** and then select **Set up roles for data projects**.</span></span> 
    <span data-ttu-id="ead6a-115">''</span><span class="sxs-lookup"><span data-stu-id="ead6a-115">''</span></span>
2.  <span data-ttu-id="ead6a-116">Skonfiguruj hierarchię kategorii zaopatrzenia i przypisz dostawców do kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="ead6a-116">Set up a procurement category hierarchy, and assign your vendors to procurement categories.</span></span> <span data-ttu-id="ead6a-117">Jeśli używasz kodów asortymentu, dodaj je do kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="ead6a-117">If you use commodity codes, add the commodity codes to the procurement categories.</span></span> <span data-ttu-id="ead6a-118">Aby uzyskać informacje dotyczące konfigurowania hierarchii kategorii zaopatrzenia, zobacz [Ustawianie hierarchii kategorii zaopatrzenia](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="ead6a-118">For information about setting up a procurement category hierarchy, see [Set up a procurement category hierarchy](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span></span>
    <span data-ttu-id="ead6a-119">''</span><span class="sxs-lookup"><span data-stu-id="ead6a-119">''</span></span>
3.  <span data-ttu-id="ead6a-120">Skonfiguruj dostawcę dla importu katalogu.</span><span class="sxs-lookup"><span data-stu-id="ead6a-120">Configure the vendor for catalog import.</span></span> <span data-ttu-id="ead6a-121">Wybierz dostawcę, a następnie wybierz kolejno opcje **Zaopatrzenie** > **Konfiguracja** > **Konfigurowanie dostawcy dla importu katalogu**.</span><span class="sxs-lookup"><span data-stu-id="ead6a-121">Select a vendor, and then select **Procurement** > **Set up** > **Configure vendor for catalog import**.</span></span>
<span data-ttu-id="ead6a-122">''''</span><span class="sxs-lookup"><span data-stu-id="ead6a-122">''''</span></span>
4.  <span data-ttu-id="ead6a-123">Skonfiguruj przepływ pracy importu katalogu.</span><span class="sxs-lookup"><span data-stu-id="ead6a-123">Configure workflow for catalog import.</span></span> <span data-ttu-id="ead6a-124">Utwórz szablon pliku CMR i udostępnij go dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ead6a-124">Create a CMR file template and share this with your vendor.</span></span>

5.  <span data-ttu-id="ead6a-125">Wybierz kolejno opcje **Zaopatrzenie i sourcing** \> **Wspólne** \> **Katalogi** \> **Katalogi dostawców**, aby utworzyć katalog dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ead6a-125">Select **Procurement and sourcing** \> **Common** \> **Catalogs** \> **Vendor catalogs** to create a vendor catalog.</span></span> <span data-ttu-id="ead6a-126">W tym katalogu będą grupowane pliki żądań zarządzania katalogami (CMR) otrzymywane od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ead6a-126">The catalog maintenance request (CMR) files that you receive from your vendor are grouped in this catalog.</span></span> 

6.  <span data-ttu-id="ead6a-127">Przekaż plik CMR.</span><span class="sxs-lookup"><span data-stu-id="ead6a-127">Upload the CMR file.</span></span>

7.  <span data-ttu-id="ead6a-128">Przejrzyj i zatwierdź lub odrzuć produkty w katalogu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ead6a-128">Review, approve, or reject the products in the vendor catalog.</span></span> <span data-ttu-id="ead6a-129">Produkty zostaną automatycznie zamapowane na kategorie zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="ead6a-129">The products are automatically mapped to the procurement categories.</span></span> 
    
<span data-ttu-id="ead6a-130">Zatwierdzone produkty są dodawane do produktu głównego i zwalniane dla wybranych firm.</span><span class="sxs-lookup"><span data-stu-id="ead6a-130">Approved products are added to the product master and are released to the selected legal entities.</span></span> <span data-ttu-id="ead6a-131">Do katalogu zaopatrzenia można dodawać tylko zatwierdzone produkty.</span><span class="sxs-lookup"><span data-stu-id="ead6a-131">Only approved products can be added to the procurement catalog.</span></span>

## <a name="generate-a-catalog-import-file-template"></a><span data-ttu-id="ead6a-132">Generowanie szablonu pliku importu katalogu</span><span class="sxs-lookup"><span data-stu-id="ead6a-132">Generate a catalog import file template</span></span>

<span data-ttu-id="ead6a-133">Szablon pliku importu katalogu jest plikiem XSD służącym do utworzenia pliku CMR dla produktów dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ead6a-133">The catalog import file template is an XSD file that you use to create a CMR file for a vendor's products.</span></span> <span data-ttu-id="ead6a-134">Plik CMR można służyć do utworzenia nowego katalogu lub zastąpienia czy zmodyfikowania istniejącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="ead6a-134">You can use the CMR file to create a new catalog, replace an existing catalog, or modify an existing catalog.</span></span>

1.  <span data-ttu-id="ead6a-135">Wybierz kolejno opcje **Zaopatrzenie i sourcing** \> **Katalogi** \> **Katalogi dostawców** i kliknij dwukrotnie katalog, na którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="ead6a-135">Select **Procurement and sourcing** \> **Catalogs** \> **Vendor catalogs** and double-click the catalog that you want to work with.</span></span>

2.  <span data-ttu-id="ead6a-136">Pobierz bieżący szablon importu katalogu (plik XSD).</span><span class="sxs-lookup"><span data-stu-id="ead6a-136">Download a current catalog import template (XSD file).</span></span> <span data-ttu-id="ead6a-137">Na stronie **Aktualizowanie katalogu** w **okienku akcji** na karcie **Katalogi** w grupie **Informacje pokrewne** kliknij przycisk **Generowanie szablonu katalogu** i wybierz opcję **Kategoria zaopatrzenia**.</span><span class="sxs-lookup"><span data-stu-id="ead6a-137">On the **Update catalog** page, on the **Action Pane**, on the **Catalogs** tab, in the **Related information** group, click **Generate catalog template** and select **Procurement category**.</span></span>

    -   <span data-ttu-id="ead6a-138">Za pomocą opcji **Kategoria zaopatrzenia** można wygenerować szablon katalogu obejmujący kategorie zaopatrzenia, w przypadku których dostawca jest upoważniony do dostarczania produktów.</span><span class="sxs-lookup"><span data-stu-id="ead6a-138">With the **Procurement category** option you can generate a catalog template that includes the procurement categories in which the vendor is authorized to provide products.</span></span>

3. <span data-ttu-id="ead6a-139">W oknie dialogowym **Zapisz jako** wybierz lokalizację, gdzie ma być przechowywany szablon pliku katalogu, i zapisz plik.</span><span class="sxs-lookup"><span data-stu-id="ead6a-139">In the **Save as** dialog box, select the location where you want to store the catalog file template and save the file.</span></span>

<span data-ttu-id="ead6a-140">Aby uzyskać więcej informacji i przykłady, zobacz ten wpis na blogu: [Katalogi dostawców w systemie Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/)</span><span class="sxs-lookup"><span data-stu-id="ead6a-140">For more information and for examples, refer to this blog post: [Vendor catalogs in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span></span>
