---
title: "Prospekt na gotówkę"
description: "Temat zawiera omówienie rozwiązania Prospekt na gotówkę działającego między programami Dynamics 365 for Finance and Operations, Enterprise Edition a Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 2accf77c5241adff7ad1648737dde451153fde46
ms.contentlocale: pl-pl
ms.lasthandoff: 11/14/2017

---

# <a name="prospect-to-cash"></a><span data-ttu-id="d1a3c-103">Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="d1a3c-103">Prospect to cash</span></span>  

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d1a3c-104">Rozwiązanie Prospekt na gotówkę używa [integracji danych](/common-data-service/entity-reference/dynamics-365-integration) do synchronizowania danych w całych wystąpieniach usługi Microsoft Dynamics 365 for Finance and Operations Enterprise Edition a Dynamics 365 for Sales za pośrednictwem usługi Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="d1a3c-104">The Prospect to cash solution uses [Data Integration](/common-data-service/entity-reference/dynamics-365-integration) to synchronize data across Microsoft Dynamics 365 for Finance and Operations, Enterprise edition and Dynamics 365 for Sales instances via the Common Data Service (CDS).</span></span> <span data-ttu-id="d1a3c-105">Szablony Prospekt na gotówkę dostępne w funkcji integracji danych umożliwiają przepływ kont, kontaktów, produktów, ofert sprzedaży, zamówień sprzedaży i faktur sprzedaży między programami Finance a Operations and Sales.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-105">The Prospect to cash templates available with the Data Integration feature enable the flow of accounts, contacts, products, sales quotes, sales orders, and sales invoices data between Finance and Operations and Sales.</span></span> <span data-ttu-id="d1a3c-106">Gdy dane przepływają między programami Finance and Operations i Sales, można wykonywać działania sprzedażowe i marketingowe w programie Sales oraz i realizować zamówienia z funkcjami zarządzania zapasami w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-106">While the data is flowing between Finance and Operations and Sales, you can carry out sales and marketing activities in Sales and handle the order fulfillment with inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="d1a3c-107">To rozwiązanie zapewnia integrację w następujących obszarach:</span><span class="sxs-lookup"><span data-stu-id="d1a3c-107">This solution provides integration in the following areas:</span></span> 

-   [<span data-ttu-id="d1a3c-108">Obsługa kont klientów w programie Sales i synchronizowanie ich z usługą Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d1a3c-108">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
-   [<span data-ttu-id="d1a3c-109">Obsługa kontaktów w programie Sales i synchronizowanie ich z usługą Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d1a3c-109">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
-   [<span data-ttu-id="d1a3c-110">Obsługa produktów w programie Finance and Operations i synchronizowanie ich z programem Sales</span><span class="sxs-lookup"><span data-stu-id="d1a3c-110">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
-   [<span data-ttu-id="d1a3c-111">Tworzenie ofert sprzedaży w programie Sales i synchronizowanie ich z usługą Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-111">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
-   [<span data-ttu-id="d1a3c-112">Tworzenie zamówień sprzedaży w programie Finance and Operations i ich synchronizacja z programem Sales</span><span class="sxs-lookup"><span data-stu-id="d1a3c-112">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
-   [<span data-ttu-id="d1a3c-113">Tworzenie faktur sprzedaży w programie Finance and Operations i ich synchronizacja z programem Sales</span><span class="sxs-lookup"><span data-stu-id="d1a3c-113">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

<span data-ttu-id="d1a3c-114">To rozwiązanie zapewnia bezpośrednią synchronizację w następujących obszarach:</span><span class="sxs-lookup"><span data-stu-id="d1a3c-114">This solution provides direct synchronization in the following areas:</span></span>

-   [<span data-ttu-id="d1a3c-115">Obsługa kont klientów w programie Sales i synchronizowanie ich bezpośrednio między programem Sales a programem Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d1a3c-115">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
-   [<span data-ttu-id="d1a3c-116">Obsługa produktów w programie Finance and Operations i synchronizowanie ich bezpośrednio z programem Sales</span><span class="sxs-lookup"><span data-stu-id="d1a3c-116">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
-   [<span data-ttu-id="d1a3c-117">Obsługa kontaktów w programie Sales i synchronizowanie ich bezpośrednio z kontaktami lub odbiorcami w programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d1a3c-117">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
-   [<span data-ttu-id="d1a3c-118">Synchronizowanie nagłówków i wierszy ofert sprzedaży bezpośrednio w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d1a3c-118">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping-sales-fin.md)
-   [<span data-ttu-id="d1a3c-119">Tworzenie zamówień sprzedaży w programie Finance and Operations i ich synchronizacja bezpośrednio z programem Sales</span><span class="sxs-lookup"><span data-stu-id="d1a3c-119">Create sales orders in Finance and Operations and sync them directly to Sales</span></span>](sales-order-template-mapping-direct.md)
-  [<span data-ttu-id="d1a3c-120">Synchronizowanie nagłówków i wierszy zamówień sprzedaży bezpośrednio między rozwiązaniami Sales a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d1a3c-120">Synchronize sales order headers and lines directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-between-sales-fin.md)
-   [<span data-ttu-id="d1a3c-121">Synchronizowanie zamówień sprzedaży bezpośrednio między rozwiązaniami Sales a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d1a3c-121">Synchronize sales orders directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-direct-two-ways.md)
-   [<span data-ttu-id="d1a3c-122">Tworzenie faktur sprzedaży w programie Finance and Operations i ich synchronizacja bezpośrednio z programem Sales</span><span class="sxs-lookup"><span data-stu-id="d1a3c-122">Create sales invoices in Finance and Operations and sync them directly to Sales</span></span>](sales-invoice-template-mapping-direct.md)


## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="d1a3c-123">Wymagania systemowe dla rozwiązania Dynamics 365 for Finance and Operations, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d1a3c-123">System requirements for Dynamics 365 for Finance and Operations, Enterprise edition</span></span>

<span data-ttu-id="d1a3c-124">Aby użyć rozwiązania Prospekt na gotówkę, należy zainstalować następujące programy:</span><span class="sxs-lookup"><span data-stu-id="d1a3c-124">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="d1a3c-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017) z aktualizacją platformy 8 (aplikacja 7.2.11792.56024 z platformą 7.0.4565.16212)</span><span class="sxs-lookup"><span data-stu-id="d1a3c-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) with Platform update 8 (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)</span></span>

- <span data-ttu-id="d1a3c-126">Poprawki rozwiązania Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017).</span><span class="sxs-lookup"><span data-stu-id="d1a3c-126">Hotfixes for Dynamics 365 for Finance and Operations, Enterprise edition (July 2017).</span></span>
        
    -  <span data-ttu-id="d1a3c-127">[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) — Ta poprawka umożliwia obsługę synchronizacji zamówień sprzedaży z funkcją Integracja danych z programu Sales do programu Finance and Operations oraz zawiera szereg innych poprawek.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-127">[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - This hotfix enabels support for sales order synchronization with the Data Integration feature from Sales to Finance and Operations, along with a number of other enhancements.</span></span>

    -  <span data-ttu-id="d1a3c-128">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) — ta poprawka umożliwia synchronizację wiersza zamówienia sprzedaży z funkcją Integracja danych z rozwiązania Finance and Operations do programu Sales.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-128">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order line synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
        
    -  <span data-ttu-id="d1a3c-129">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) — ta poprawka umożliwia synchronizację zamówienia sprzedaży z funkcją Integracja danych z rozwiązania Finance and Operations do programu Sales.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-129">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>

<span data-ttu-id="d1a3c-130">**Uwaga**: Należy zainstalować tylko poprawkę KB4045570, ponieważ instalacja obejmuje zmiany z innych poprawek.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-130">**Note**: You only need to install KB4045570 because the installation includes the changes from the other KB's.</span></span>
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a><span data-ttu-id="d1a3c-131">Wymagania systemowe rozwiązania Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="d1a3c-131">System requirements for Dynamics 365 for Sales</span></span>

<span data-ttu-id="d1a3c-132">Aby użyć rozwiązania Prospekt na gotówkę, należy zainstalować następujące programy:</span><span class="sxs-lookup"><span data-stu-id="d1a3c-132">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="d1a3c-133">Dynamics 365 for Sales wersja 1612 (8.2.1.207) (DB 8.2.1.207) online.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-133">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online.</span></span>
- <span data-ttu-id="d1a3c-134">Rozwiązanie Prospekt na gotówkę dla programu Dynamics 365 for Sales, wersja 1.14.0.0 (v14) lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-134">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="d1a3c-135">Instalacja rozwiązania Prospekt na gotówkę dla programu Sales</span><span class="sxs-lookup"><span data-stu-id="d1a3c-135">Install the Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="d1a3c-136">Pobierz [Plik zip pakietu rozwiązania Prospekt na gotówkę dla programu Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) z witryny CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-136">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) on CustomerSource.</span></span>

- <span data-ttu-id="d1a3c-137">Upewnij się, że plik zip jest odblokowany, aby podczas instalacji pakietu rozwiązania nie został wyświetlony komunikat o błędzie „Nie znaleziono pakietów importu“.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-137">Make sure that the zip file is unblocked so that you do not get the error message "No import packages were found" when you install the solution package.</span></span> <span data-ttu-id="d1a3c-138">Aby odblokować plik, wykonaj następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="d1a3c-138">To unblock the file, do the following:</span></span>

    -  <span data-ttu-id="d1a3c-139">Kliknij plik zip prawym przyciskiem myszy.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-139">Right-click the zip file.</span></span>
    -  <span data-ttu-id="d1a3c-140">Wybierz polecenie **Właściwości**, a następnie wybierz opcję **Odblokuj**.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-140">Select **Properties** and then select **Unblock**.</span></span> 

- <span data-ttu-id="d1a3c-141">Rozpakuj i uruchom plik PackageDeployer.exe.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-141">Unzip and run PackageDeployer.exe.</span></span>

- <span data-ttu-id="d1a3c-142">Zainstaluj rozwiązanie Prospekt na gotówkę w instancji programu Sales.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-142">Install the Prospect to Cash solution in your Sales instance.</span></span>

    - <span data-ttu-id="d1a3c-143">Wybierz typ wdrożenia **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-143">Select the **Office 365** Deployment type.</span></span>
    - <span data-ttu-id="d1a3c-144">Wybierz opcję **Pokaż zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-144">Select **Show advanced**.</span></span>
    - <span data-ttu-id="d1a3c-145">W celu szybkiej instalacji wybierz **Region**.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-145">For a quick installation, select a **Region**.</span></span> <span data-ttu-id="d1a3c-146">Jeżeli wybierzesz opcję **Nie wiem**, system wyszuka wszystkie regiony i instalacja potrwa dłużej.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-146">If you select **Don’t know**, the system searches for all regions and it will take longer to install.</span></span>
    - <span data-ttu-id="d1a3c-147">Wprowadź informacje w polach **Nazwa użytkownika** i **Hasło** użytkownika administratora, który ma uprawnienia do instalacji.</span><span class="sxs-lookup"><span data-stu-id="d1a3c-147">Enter **User name** and **Password** for an admin user who has the user rights to install.</span></span>

