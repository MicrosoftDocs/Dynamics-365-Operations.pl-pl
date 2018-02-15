---
title: "Prospekt na gotówkę"
description: "Ten temat zawiera omówienie rozwiązania Prospekt na gotówkę działającego między programami Dynamics 365 for Finance and Operations, Enterprise Edition a Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 1f76359878d162e93d8f8b7c11be529c43c94455
ms.openlocfilehash: 9b150bfca362303b4ac35a38ab818229082c7330
ms.contentlocale: pl-pl
ms.lasthandoff: 02/08/2018

---

# <a name="prospect-to-cash"></a><span data-ttu-id="f833d-103">Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="f833d-103">Prospect to cash</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f833d-104">Rozwiązanie Prospekt na gotówkę umożliwia bezpośrednią synchronizację między programami Dynamics 365 for Finance and Operations, Enterprise edition i Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="f833d-104">The Prospect to cash solution provides direct synchronization across Dynamics 365 for Finance and Operations, Enterprise edition, and Dynamics 365 for Sales.</span></span> <span data-ttu-id="f833d-105">Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="f833d-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="f833d-106">Gdy dane przepływają między programami Finance and Operations i Sales, można wykonywać działania sprzedażowe i marketingowe w programie Sales oraz i realizować zamówienia z funkcjami zarządzania zapasami w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f833d-106">While data is flowing between Finance and Operations and Sales, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="f833d-107">Aby uzyskać więcej informacji o integracji w procesie Prospekt na gotówkę, obejrzyj krótki film na YouTube:</span><span class="sxs-lookup"><span data-stu-id="f833d-107">For more information about the Prospect to cash integration, watch the short YouTube video:</span></span>

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

<span data-ttu-id="f833d-108">W bieżącej wersji rozwiązania Prospekt na gotówkę udostępniono następujące typy synchronizacji bezpośredniej:</span><span class="sxs-lookup"><span data-stu-id="f833d-108">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="f833d-109">Obsługa kont klientów w programie Sales i synchronizowanie ich bezpośrednio między programem Sales a programem Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f833d-109">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="f833d-110">Obsługa produktów w rozwiązaniu Finance and Operations i synchronizowanie ich bezpośrednio z rozwiązaniem Sales</span><span class="sxs-lookup"><span data-stu-id="f833d-110">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="f833d-111">Obsługa kontaktów w rozwiązaniu Sales i synchronizowanie ich bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f833d-111">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="f833d-112">Synchronizowanie ofert sprzedaży bezpośrednio między rozwiązaniem Sales a rozwiązaniem Finance and Operations (wkrótce zostanie udostępniony szablon)</span><span class="sxs-lookup"><span data-stu-id="f833d-112">Synchronize sales quotation directly from Sales to Finance and Operations (template pending release)</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="f833d-113">Synchronizowanie zamówień sprzedaży bezpośrednio z rozwiązania Finance and Operations do rozwiązania Sales</span><span class="sxs-lookup"><span data-stu-id="f833d-113">Synchronize sales orders directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)
- [<span data-ttu-id="f833d-114">Synchronizowanie zamówień sprzedaży bezpośrednio między rozwiązaniem Sales a rozwiązaniem Finance and Operations (wkrótce zostanie udostępniony szablon)</span><span class="sxs-lookup"><span data-stu-id="f833d-114">Synchronize sales orders directly between Sales and Finance and Operations (template pending release)</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="f833d-115">Synchronizowanie faktur sprzedaży bezpośrednio z rozwiązania Finance and Operations do rozwiązania Sales</span><span class="sxs-lookup"><span data-stu-id="f833d-115">Synchronize sales invoice directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

<span data-ttu-id="f833d-116">W starszych wersjach rozwiązania Prospekt na gotówkę funkcjonowały następujące typy synchronizacji niebezpośredniej:</span><span class="sxs-lookup"><span data-stu-id="f833d-116">In earlier versions, the Prospect to cash solution provides the following types of non-direct synchronization:</span></span>

- [<span data-ttu-id="f833d-117">Obsługa kont klientów w programie Sales i synchronizowanie ich z usługą Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f833d-117">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
- [<span data-ttu-id="f833d-118">Obsługa kontaktów w rozwiązaniu Sales i synchronizowanie ich z rozwiązaniem Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f833d-118">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
- [<span data-ttu-id="f833d-119">Obsługa produktów w rozwiązaniu Finance and Operations i synchronizowanie ich z rozwiązaniem Sales</span><span class="sxs-lookup"><span data-stu-id="f833d-119">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
- [<span data-ttu-id="f833d-120">Tworzenie ofert sprzedaży w rozwiązaniu Sales i synchronizowanie ich z rozwiązaniem Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f833d-120">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
- [<span data-ttu-id="f833d-121">Tworzenie zamówień sprzedaży w rozwiązaniu Finance and Operations i synchronizowanie ich z rozwiązaniem Sales</span><span class="sxs-lookup"><span data-stu-id="f833d-121">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
- [<span data-ttu-id="f833d-122">Tworzenie faktur sprzedaży w rozwiązaniu Finance and Operations i synchronizowanie ich z rozwiązaniem Sales</span><span class="sxs-lookup"><span data-stu-id="f833d-122">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="f833d-123">Wymagania systemowe dla rozwiązania Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f833d-123">System requirements for Finance and Operations</span></span>

<span data-ttu-id="f833d-124">Integracja w procesie Prospekt na gotówkę jest obsługiwana w następujących wersjach:</span><span class="sxs-lookup"><span data-stu-id="f833d-124">Prospect to cash integration is supported on the following versions:</span></span>

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a><span data-ttu-id="f833d-125">Microsoft Dynamics 365 for Finance and Operations Enterprise Edition wer. 7.3 (grudzień 2017)</span><span class="sxs-lookup"><span data-stu-id="f833d-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (December 2017)</span></span>

- <span data-ttu-id="f833d-126">Dynamics 365 for Finance and Operations Enterprise Edition (grudzień 2017) — kompilacja aplikacji 7.3.11971.56116 z aktualizacją platformy 12 (7.0.4709.41129)</span><span class="sxs-lookup"><span data-stu-id="f833d-126">Dynamics 365 for Finance and Operations, Enterprise edition (December 2017) - Application build 7.3.11971.56116 with Platform Update 12 (7.0.4709.41129)</span></span>

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="f833d-127">Układ w rozwiązaniu Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017)</span><span class="sxs-lookup"><span data-stu-id="f833d-127">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span>

- <span data-ttu-id="f833d-128">Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017) — z aktualizacją platformy 8 (aplikacja w wersji 7.2.11792.56024 z platformą w wersji 7.0.4565.16212).</span><span class="sxs-lookup"><span data-stu-id="f833d-128">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212).</span></span>
- <span data-ttu-id="f833d-129">Poniżej znajduje się lista wymaganych poprawek:</span><span class="sxs-lookup"><span data-stu-id="f833d-129">The following hotfixes are required:</span></span>

    - <span data-ttu-id="f833d-130">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży między modułem Sales a modułem Finance and Operations za pomocą funkcji integracji danych.</span><span class="sxs-lookup"><span data-stu-id="f833d-130">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Finance and Operations via the Data Integration feature.</span></span> <span data-ttu-id="f833d-131">Zapewnia również kilka innych ulepszeń.</span><span class="sxs-lookup"><span data-stu-id="f833d-131">It also provides several other enhancements.</span></span>
    - <span data-ttu-id="f833d-132">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację wiersza zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą funkcji integracji danych.</span><span class="sxs-lookup"><span data-stu-id="f833d-132">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>
    - <span data-ttu-id="f833d-133">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą funkcji integracji danych.</span><span class="sxs-lookup"><span data-stu-id="f833d-133">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f833d-134">Należy zainstalować tylko poprawkę KB4045570, ponieważ instalacja obejmuje zmiany z innych poprawek.</span><span class="sxs-lookup"><span data-stu-id="f833d-134">You only have to install KB4045570 because the installation includes the changes from other hotfixes.</span></span> 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a><span data-ttu-id="f833d-135">Wprowadzenie do rozwiązania Dynamics 365 for Finance and Operations w wersji 1611 (listopad 2016)</span><span class="sxs-lookup"><span data-stu-id="f833d-135">Dynamics 365 for Finance and Operations version 1611 (November 2016)</span></span>

- <span data-ttu-id="f833d-136">Dynamics 365 for Finance and Operations w wersji 1611 (listopad 2016) z aktualizacją platformy 8 lub nowszą</span><span class="sxs-lookup"><span data-stu-id="f833d-136">Dynamics 365 for Finance and Operations version 1611 (November 2016)  with platform update 8 or higher</span></span>

- <span data-ttu-id="f833d-137">Poniżej znajduje się lista wymaganych poprawek:</span><span class="sxs-lookup"><span data-stu-id="f833d-137">The following hotfixes are required:</span></span>

    - <span data-ttu-id="f833d-138">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** — umożliwia synchronizację zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą integratora danych.</span><span class="sxs-lookup"><span data-stu-id="f833d-138">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Finance and Operations to Sales.</span></span> 
    - <span data-ttu-id="f833d-139">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** — umożliwia synchronizację nagłówka i wiersza zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą integratora danych.</span><span class="sxs-lookup"><span data-stu-id="f833d-139">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Finance and Operations to Sales.</span></span>
    - <span data-ttu-id="f833d-140">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** — wymagana jest obsługa integracji rozwiązania Prospekt na gotówkę poprzez jednostki danych.</span><span class="sxs-lookup"><span data-stu-id="f833d-140">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f833d-141">Po zainstalowaniu poprawek należy uruchomić następujące zadanie wsadowe z formularza **SalesPopulateProspectToCash**.</span><span class="sxs-lookup"><span data-stu-id="f833d-141">After you install the hotfixes, you must trigger the following batch job from the **SalesPopulateProspectToCash** form.</span></span> <span data-ttu-id="f833d-142">Formularz ten jest ukryty, ponieważ jest on potrzebny tylko raz.</span><span class="sxs-lookup"><span data-stu-id="f833d-142">This form is hidden because you only need it once.</span></span> <span data-ttu-id="f833d-143">Aby uzyskać dostęp do formularza, zaloguj się do środowiska i dodaj następujący tekst do adresu URL w przeglądarce: &mi=action:SalesPopulateProspectToCash, na przykład, https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash.</span><span class="sxs-lookup"><span data-stu-id="f833d-143">To access the form, log in to the environment and add the following to the URL in your browser address: &mi=action:SalesPopulateProspectToCash, for example, https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash.</span></span> <span data-ttu-id="f833d-144">Po otwarciu formularza kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f833d-144">When the form opens, click OK.</span></span> <span data-ttu-id="f833d-145">Spowoduje to uzupełnienie nowego pola **LineCreationSequnceNumber** w tabelach **SalesLine**, **SalesQuotationLine** i **CustInvoiceTrans** unikatowymi wartościami i odświeżenie listy produktów.</span><span class="sxs-lookup"><span data-stu-id="f833d-145">This will populate a new **LineCreationSequnceNumber** field in the **SalesLine**, **SalesQuotationLine**, and **CustInvoiceTrans** tables with unique values, and the product list will be refreshed.</span></span> <span data-ttu-id="f833d-146">Jest to wymagane do działania rozwiązania Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="f833d-146">This is required for the Prospect to cash integration to work.</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="f833d-147">Wymagania systemowe dla rozwiązania Sales</span><span class="sxs-lookup"><span data-stu-id="f833d-147">System requirements for Sales</span></span>

<span data-ttu-id="f833d-148">Aby skorzystać z rozwiązania Prospekt na gotówkę, należy zainstalować następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="f833d-148">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="f833d-149">Dynamics 365 for Sales w wersji 1612 (8.2.1.207) (DB 8.2.1.207) online</span><span class="sxs-lookup"><span data-stu-id="f833d-149">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online</span></span>
- <span data-ttu-id="f833d-150">Rozwiązanie Prospekt na gotówkę dla programu Dynamics 365 for Sales, wersja 1.15.0.0 (v15)</span><span class="sxs-lookup"><span data-stu-id="f833d-150">Prospect to cash solution for Dynamics 365 for Sales, version 1.15.0.0 (v15)</span></span> 

   > [!NOTE]
   >
   > <span data-ttu-id="f833d-151">Szablony w wersji 1.0.0.0 i 1.0.0.1 są obsługiwane rozwiązaniu Prospekt na gotówkę dla oprogramowania Dynamics 365 for Sales, wersja 1.14.1.0</span><span class="sxs-lookup"><span data-stu-id="f833d-151">Templates with version 1.0.0.0 and 1.0.0.1 are supported on Prospect to cash solution for Dynamics 365 for Sales, version 1.14.1.0</span></span>
   >
   > <span data-ttu-id="f833d-152">Szablony w wersji 2.0.0.0 i 2.1.0.0 są obsługiwane rozwiązaniu Prospekt na gotówkę dla oprogramowania Dynamics 365 for Sales, wersja 1.15.0.0</span><span class="sxs-lookup"><span data-stu-id="f833d-152">Templates with version 2.0.0.0 and 2.1.0.0 are supported on Prospect to cash solution for Dynamics 365 for Sales, version 1.15.0.0</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="f833d-153">Instalacja rozwiązania Prospekt na gotówkę dla programu Sales</span><span class="sxs-lookup"><span data-stu-id="f833d-153">Install the Prospect to cash solution for Sales</span></span>

1. <span data-ttu-id="f833d-154">Pobierz [Plik zip pakietu rozwiązania Prospekt na gotówkę dla programu Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) z witryny CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="f833d-154">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) from CustomerSource.</span></span>
2. <span data-ttu-id="f833d-155">Upewnij się, że plik .zip jest odblokowany.</span><span class="sxs-lookup"><span data-stu-id="f833d-155">Make sure that the zip file is unblocked.</span></span> <span data-ttu-id="f833d-156">W przeciwnym razie przy próbie zainstalowania pakietu rozwiązania pojawi się komunikat o błędzie: „Nie znaleziono pakietów importu”.</span><span class="sxs-lookup"><span data-stu-id="f833d-156">Otherwise, when you try to install the solution package, you may receive the following error message, "No import packages were found."</span></span> <span data-ttu-id="f833d-157">Aby odblokować plik zip, kliknij go prawym przyciskiem myszy i wybierz opcję **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="f833d-157">To unblock the zip file, right-click it, and select **Properties**.</span></span> <span data-ttu-id="f833d-158">Wybierz opcję **Odblokuj**.</span><span class="sxs-lookup"><span data-stu-id="f833d-158">Select **Unblock**.</span></span>
3. <span data-ttu-id="f833d-159">Rozpakuj i uruchom plik **PackageDeployer.exe**.</span><span class="sxs-lookup"><span data-stu-id="f833d-159">Unzip and run **PackageDeployer.exe**.</span></span>
4. <span data-ttu-id="f833d-160">Zainstaluj rozwiązanie Prospekt na gotówkę w instancji programu Sales:</span><span class="sxs-lookup"><span data-stu-id="f833d-160">Install the Prospect to cash solution on your Sales instance:</span></span>

    1. <span data-ttu-id="f833d-161">Wybierz typ wdrożenia **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="f833d-161">Select **Office 365** as the deployment type.</span></span>
    2. <span data-ttu-id="f833d-162">Wybierz opcję **Pokaż zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="f833d-162">Select **Show advanced**.</span></span>
    3. <span data-ttu-id="f833d-163">W celu szybkiej instalacji wybierz region.</span><span class="sxs-lookup"><span data-stu-id="f833d-163">For a quick installation, select a region.</span></span> <span data-ttu-id="f833d-164">Jeżeli wybierzesz opcję **Nie wiem**, system przeszuka wszystkie regiony i instalacja potrwa dłużej.</span><span class="sxs-lookup"><span data-stu-id="f833d-164">If you select **Don't know**, the system searches for all regions, and the installation will take more time.</span></span>
    4. <span data-ttu-id="f833d-165">Wprowadź nazwę użytkownika i hasło administratora z uprawnieniami do instalacji.</span><span class="sxs-lookup"><span data-stu-id="f833d-165">Enter the user name and password of an admin user who has installation rights.</span></span>



