---
title: "Prospekt na gotówkę"
description: "Ten temat zawiera omówienie rozwiązania Prospekt na gotówkę działającego między programami Dynamics 365 for Finance and Operations, Enterprise Edition a Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 11/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 788e64476094e84eb4d438890776306c05b20582
ms.openlocfilehash: 762699cf68ec8a9df5db20d7dd33bc9248f0a36e
ms.contentlocale: pl-pl
ms.lasthandoff: 12/11/2017

---

# <a name="prospect-to-cash"></a><span data-ttu-id="87820-103">Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="87820-103">Prospect to cash</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="87820-104">Rozwiązanie Prospekt na gotówkę umożliwia bezpośrednią synchronizację między programami Microsoft Dynamics 365 for Finance and Operations, Enterprise edition i Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="87820-104">The Prospect to cash solution provides direct synchronization across Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, and Microsoft Dynamics 365 for Sales.</span></span> <span data-ttu-id="87820-105">Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="87820-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="87820-106">Gdy dane przepływają między programami Finance and Operations i Sales, można wykonywać działania sprzedażowe i marketingowe w programie Sales oraz i realizować zamówienia z funkcjami zarządzania zapasami w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87820-106">While data is flowing between Finance and Operations and Sales, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Finance and Operations.</span></span>

<span data-ttu-id="87820-107">W bieżącej wersji rozwiązania Prospekt na gotówkę udostępniono następujące typy synchronizacji bezpośredniej:</span><span class="sxs-lookup"><span data-stu-id="87820-107">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="87820-108">Obsługa kont klientów w programie Sales i synchronizowanie ich bezpośrednio między programem Sales a programem Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87820-108">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="87820-109">Obsługa produktów w programie Finance and Operations i synchronizowanie ich bezpośrednio z programem Sales</span><span class="sxs-lookup"><span data-stu-id="87820-109">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="87820-110">Obsługa kontaktów w programie Sales i synchronizowanie ich bezpośrednio z kontaktami lub odbiorcami w programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87820-110">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="87820-111">Synchronizowanie ofert sprzedaży bezpośrednio z rozwiązania Sales do rozwiązania Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87820-111">Synchronize sales quotation directly from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="87820-112">Synchronizowanie zamówień sprzedaży bezpośrednio z rozwiązania Finance and Operations do rozwiązania Sales</span><span class="sxs-lookup"><span data-stu-id="87820-112">Synchronize sales orders directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)
- [<span data-ttu-id="87820-113">Synchronizowanie zamówień sprzedaży bezpośrednio między rozwiązaniami Sales a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87820-113">Synchronize sales orders directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="87820-114">Synchronizowanie faktur sprzedaży bezpośrednio z rozwiązania Finance and Operations do rozwiązania Sales</span><span class="sxs-lookup"><span data-stu-id="87820-114">Synchronize sales invoice directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

<span data-ttu-id="87820-115">W starszych wersjach rozwiązania Prospekt na gotówkę funkcjonowały następujące typy synchronizacji niebezpośredniej:</span><span class="sxs-lookup"><span data-stu-id="87820-115">In earlier versions, the Prospect to cash solution provides the following types of non-direct synchronization:</span></span>

- [<span data-ttu-id="87820-116">Obsługa kont klientów w programie Sales i synchronizowanie ich z usługą Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87820-116">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
- [<span data-ttu-id="87820-117">Obsługa kontaktów w programie Sales i synchronizowanie ich z usługą Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87820-117">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
- [<span data-ttu-id="87820-118">Obsługa produktów w programie Finance and Operations i synchronizowanie ich z programem Sales</span><span class="sxs-lookup"><span data-stu-id="87820-118">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
- [<span data-ttu-id="87820-119">Tworzenie ofert sprzedaży w programie Sales i synchronizowanie ich z usługą Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87820-119">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
- [<span data-ttu-id="87820-120">Tworzenie zamówień sprzedaży w programie Finance and Operations i ich synchronizacja z programem Sales</span><span class="sxs-lookup"><span data-stu-id="87820-120">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
- [<span data-ttu-id="87820-121">Tworzenie faktur sprzedaży w programie Finance and Operations i ich synchronizacja z programem Sales</span><span class="sxs-lookup"><span data-stu-id="87820-121">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="87820-122">Wymagania systemowe dla rozwiązania Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87820-122">System requirements for Finance and Operations</span></span>

<span data-ttu-id="87820-123">Aby skorzystać z rozwiązania Prospekt na gotówkę, należy zainstalować następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="87820-123">To use the Prospect to cash solution, you must install the following components:</span></span>

### <a name="july-2017"></a><span data-ttu-id="87820-124">Lipiec 2017</span><span class="sxs-lookup"><span data-stu-id="87820-124">July 2017</span></span> 

- <span data-ttu-id="87820-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017) z aktualizacją platformy 8 (aplikacja w wersji 7.2.11792.56024 z platformą w wersji 7.0.4565.16212)</span><span class="sxs-lookup"><span data-stu-id="87820-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212)</span></span>
- <span data-ttu-id="87820-126">W rozwiązaniu Finance and Operations wprowadzono następujące poprawki:</span><span class="sxs-lookup"><span data-stu-id="87820-126">The following hotfixes for Finance and Operations:</span></span>

    - <span data-ttu-id="87820-127">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży między modułem Sales a modułem Finance and Operations za pomocą funkcji integracji danych.</span><span class="sxs-lookup"><span data-stu-id="87820-127">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Finance and Operations via the Data Integration feature.</span></span> <span data-ttu-id="87820-128">Zapewnia również kilka innych ulepszeń.</span><span class="sxs-lookup"><span data-stu-id="87820-128">It also provides several other enhancements.</span></span>
    - <span data-ttu-id="87820-129">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację wiersza zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą funkcji integracji danych.</span><span class="sxs-lookup"><span data-stu-id="87820-129">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>
    - <span data-ttu-id="87820-130">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą funkcji integracji danych.</span><span class="sxs-lookup"><span data-stu-id="87820-130">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87820-131">Należy zainstalować tylko poprawkę KB4045570, ponieważ instalacja ta obejmuje również zmiany z innych artykułów w bazie wiedzy Microsoft Knowledge Base (KB).</span><span class="sxs-lookup"><span data-stu-id="87820-131">You only have to install KB4045570, because the installation includes the changes from the other Microsoft Knowledge Base (KB) articles.</span></span>

### <a name="november-2016-version-1611"></a><span data-ttu-id="87820-132">Listopad 2016 (wersja 1611)</span><span class="sxs-lookup"><span data-stu-id="87820-132">November 2016 (Version 1611)</span></span>

- <span data-ttu-id="87820-133">Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (listopad 2016) z aktualizacją platformy 8 lub nowszą</span><span class="sxs-lookup"><span data-stu-id="87820-133">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (November 2016) with platform update 8 or higher</span></span>

- <span data-ttu-id="87820-134">W rozwiązaniu Finance and Operations wprowadzono następujące poprawki:</span><span class="sxs-lookup"><span data-stu-id="87820-134">The following hotfixes for Finance and Operations:</span></span>

    - <span data-ttu-id="87820-135">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** — umożliwia synchronizację zamówienia sprzedaży między modułem Microsoft Dynamics 365 for Finance and Operations a modułem Sales za pomocą integratora danych.</span><span class="sxs-lookup"><span data-stu-id="87820-135">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Microsoft Dynamics 365 for Finance and Operations to Sales</span></span> 
    - <span data-ttu-id="87820-136">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** — umożliwia synchronizację nagłówka i wiersza zamówienia sprzedaży między modułem Microsoft Dynamics 365 for Finance and Operations a modułem Sales za pomocą integratora danych.</span><span class="sxs-lookup"><span data-stu-id="87820-136">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Microsoft Dynamics 365 for Finance and Operations to Sales</span></span>
    - <span data-ttu-id="87820-137">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** — wymagana jest obsługa integracji rozwiązania Prospekt na gotówkę poprzez jednostki danych.</span><span class="sxs-lookup"><span data-stu-id="87820-137">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="87820-138">Po zainstalowaniu poprawek należy uruchomić poniższe zadanie wsadowe z poziomu formularza SalesPopulateProspectToCash.</span><span class="sxs-lookup"><span data-stu-id="87820-138">After installing the hotfixes you have to trigger the following batch job from the form SalesPopulateProspectToCash.</span></span> <span data-ttu-id="87820-139">Formularz ten jest ukryty, ponieważ jest on potrzebny tylko raz.</span><span class="sxs-lookup"><span data-stu-id="87820-139">This form is hidden as you only need it once.</span></span> <span data-ttu-id="87820-140">Aby do niego przejść, zaloguj się do środowiska, a następnie dodaj następujący łańcuch do adresu w przeglądarce: &mi=action:SalesPopulateProspectToCash, na przykład</span><span class="sxs-lookup"><span data-stu-id="87820-140">To access it add the following to your browser address, when logged in to the environment: &mi=action:SalesPopulateProspectToCash E.g.</span></span> <span data-ttu-id="87820-141">https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash, a w formularzu, który się otworzy, kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87820-141">https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash In the form that opens click OK.</span></span>
    <span data-ttu-id="87820-142">Spowoduje to uzupełnienie pola „LineCreationSequnceNumber” w tabelach „SalesLine”, „SalesQuotationLine” i „CustInvoiceTrans” niepowtarzalnymi wartościami i odświeżenie listy produktów.</span><span class="sxs-lookup"><span data-stu-id="87820-142">This will populate a new “LineCreationSequnceNumber” field in “SalesLine”, “SalesQuotationLine” and “CustInvoiceTrans” tables with unique values and refresh the product list.</span></span> <span data-ttu-id="87820-143">Jest to konieczne do korzystania z integracji P2C w wersji 7.1.</span><span class="sxs-lookup"><span data-stu-id="87820-143">This is needed for the P2C integration to work on 7.1</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="87820-144">Wymagania systemowe dla rozwiązania Sales</span><span class="sxs-lookup"><span data-stu-id="87820-144">System requirements for Sales</span></span>

<span data-ttu-id="87820-145">Aby skorzystać z rozwiązania Prospekt na gotówkę, należy zainstalować następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="87820-145">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="87820-146">Microsoft Dynamics 365 for Sales wersja 1612 (8.2.1.207) (DB 8.2.1.207) online</span><span class="sxs-lookup"><span data-stu-id="87820-146">Microsoft Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online</span></span>
- <span data-ttu-id="87820-147">Rozwiązanie Prospekt na gotówkę dla programu Microsoft Dynamics 365 for Sales, wersja 1.15.0.0 (v15)</span><span class="sxs-lookup"><span data-stu-id="87820-147">Prospect to cash solution for Microsoft Dynamics 365 for Sales, version 1.15.0.0 (v15)</span></span> 

   > [!NOTE]
   >
   > <span data-ttu-id="87820-148">Szablony w wersji 1.0.0.0 i 1.0.0.1 są obsługiwane rozwiązaniu Prospekt na gotówkę dla oprogramowania Microsoft Dynamics 365 for Sales, wersja 1.14.1.0</span><span class="sxs-lookup"><span data-stu-id="87820-148">Templates with version 1.0.0.0 and 1.0.0.1 are supported on Prospect to cash solution for Microsoft Dynamics 365 for Sales, version 1.14.1.0</span></span>
   >
   > <span data-ttu-id="87820-149">Szablony w wersji 2.0.0.0 i 2.1.0.0 są obsługiwane rozwiązaniu Prospekt na gotówkę dla oprogramowania Microsoft Dynamics 365 for Sales, wersja 1.15.0.0</span><span class="sxs-lookup"><span data-stu-id="87820-149">Templates with version 2.0.0.0 and 2.1.0.0 are upported on Prospect to cash solution for Microsoft Dynamics 365 for Sales, version 1.15.0.0</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="87820-150">Instalacja rozwiązania Prospekt na gotówkę dla programu Sales</span><span class="sxs-lookup"><span data-stu-id="87820-150">Install the Prospect to cash solution for Sales</span></span>

1. <span data-ttu-id="87820-151">Pobierz [Plik zip pakietu rozwiązania Prospekt na gotówkę dla programu Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) z witryny CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="87820-151">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) from CustomerSource.</span></span>
2. <span data-ttu-id="87820-152">Upewnij się, że plik .zip jest odblokowany.</span><span class="sxs-lookup"><span data-stu-id="87820-152">Make sure that the zip file is unblocked.</span></span> <span data-ttu-id="87820-153">W przeciwnym razie przy próbie zainstalowania pakietu rozwiązania pojawi się komunikat o błędzie: „Nie znaleziono pakietów importu”.</span><span class="sxs-lookup"><span data-stu-id="87820-153">Otherwise, when you try to install the solution package, you receive the following error message: "No import packages were found."</span></span> <span data-ttu-id="87820-154">Aby odblokować plik zip, kliknij go prawym przyciskiem myszy i wybierz opcję **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="87820-154">To unblock the zip file, right-click it, and select **Properties**.</span></span> <span data-ttu-id="87820-155">Następnie wybierz opcję **Odblokuj**.</span><span class="sxs-lookup"><span data-stu-id="87820-155">Then select **Unblock**.</span></span>
3. <span data-ttu-id="87820-156">Rozpakuj i uruchom plik **PackageDeployer.exe**.</span><span class="sxs-lookup"><span data-stu-id="87820-156">Unzip and run **PackageDeployer.exe**.</span></span>
4. <span data-ttu-id="87820-157">Zainstaluj rozwiązanie Prospekt na gotówkę w instancji programu Sales:</span><span class="sxs-lookup"><span data-stu-id="87820-157">Install the Prospect to cash solution on your Sales instance:</span></span>

    1. <span data-ttu-id="87820-158">Wybierz typ wdrożenia **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="87820-158">Select **Office 365** as the deployment type.</span></span>
    2. <span data-ttu-id="87820-159">Wybierz opcję **Pokaż zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="87820-159">Select **Show advanced**.</span></span>
    3. <span data-ttu-id="87820-160">W celu szybkiej instalacji wybierz region.</span><span class="sxs-lookup"><span data-stu-id="87820-160">For a quick installation, select a region.</span></span> <span data-ttu-id="87820-161">Jeżeli wybierzesz opcję **Nie wiem**, system przeszuka wszystkie regiony i instalacja potrwa dłużej.</span><span class="sxs-lookup"><span data-stu-id="87820-161">If you select **Don't know**, the system searches for all regions, and the installation will take more time.</span></span>
    4. <span data-ttu-id="87820-162">Wprowadź nazwę użytkownika i hasło administratora z uprawnieniami do instalacji.</span><span class="sxs-lookup"><span data-stu-id="87820-162">Enter the user name and password of an admin user who has installation rights.</span></span>

