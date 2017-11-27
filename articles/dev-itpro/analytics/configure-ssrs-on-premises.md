---
title: "Konfigurowanie usług SQL Server Reporting Services dla wdrożenia lokalnego"
description: "Ten temat zawiera informacje dotyczące konfigurowania usługi SQL Server Reporting Services (SSRS) dla wdrożenia lokalnego."
author: sarvanisathish
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2a1f11641a2ec055cfaa0157ac9a40525daa4006
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---
# <a name="configure-sql-server-reporting-services-for-an-on-premises-deployment"></a><span data-ttu-id="72d6d-103">Konfigurowanie usług SQL Server Reporting Services dla wdrożenia lokalnego</span><span class="sxs-lookup"><span data-stu-id="72d6d-103">Configure SQL Server Reporting Services for an on-premises deployment</span></span>

<span data-ttu-id="72d6d-104">Kroki opisane w tym temacie umożliwiają skonfigurowanie usługi SQL Server Reporting Services (SSRS) dla lokalnego wdrożenia programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="72d6d-104">Use the steps in this topic to configure SQL Server Reporting Services (SSRS) for your Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises) deployment.</span></span>

1. <span data-ttu-id="72d6d-105">Otwórz aplikację Menedżer konfiguracji usługi Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="72d6d-105">Open the Reporting Services Configuration Manager application.</span></span>
2. <span data-ttu-id="72d6d-106">Pozostaw domyślną wartość **Nazwa serwera**, która powinna być nazwa bieżącego komputera, oraz ustawienie **Wystąpienie serwera raportów** o wartości **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="72d6d-106">Leave the default **Server name**, which should be the name of the current machine, and the **Report Server Instance**, **MSSQLSERVER**.</span></span> 
3. <span data-ttu-id="72d6d-107">Kliknij przycisk **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="72d6d-107">Click **Connect**.</span></span>
   
   <span data-ttu-id="72d6d-108">[![Połączenie konfigurowania usługi Reporting Services](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-108">[![Reporting services configuration connection](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span></span>
   
4. <span data-ttu-id="72d6d-109">Kliknij kartę **Konto usługi** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="72d6d-109">Click the **Service Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="72d6d-110">[![Karta Konto usługi](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-110">[![Service account tab](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span></span>
    
5. <span data-ttu-id="72d6d-111">Kliknij kartę **Adres URL usługi sieci Web** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="72d6d-111">Click the **Web Service URL** tab and verify that the settings match the following graphic.</span></span> 

    <span data-ttu-id="72d6d-112">[![Karta Adres URL usługi sieci Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-112">[![Web service URL tab](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span></span> 
    
6. <span data-ttu-id="72d6d-113">Kliknij kartę **Baza danych** sprawdź, czy wartości w polach **Nazwa bazy danych** i **Ustawienia poświadczeń** odpowiadają poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="72d6d-113">Click the **Database** tab and verify that the **Database Name** and **Credential settings** match the following graphic.</span></span> <span data-ttu-id="72d6d-114">**Uwaga:** Należy utworzyć nową bazę danych.</span><span class="sxs-lookup"><span data-stu-id="72d6d-114">**Note:** You will need to create a new database.</span></span> <span data-ttu-id="72d6d-115">Aby to zrobić, kliknij przycisk **Zmień bazę danych zmian**, a następnie sprawdź, czy nowa baza danych ma nazwę **DynamicsAxReportServer**.</span><span class="sxs-lookup"><span data-stu-id="72d6d-115">To do this, click **Change Database**, and then verify that the new database name is: **DynamicsAxReportServer**.</span></span>

    <span data-ttu-id="72d6d-116">[![Karta Baza danych](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-116">[![database tab](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span></span>
    
7. <span data-ttu-id="72d6d-117">Kliknij kartę **Adres URL portalu sieci Web** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="72d6d-117">Click the **Web Portal URL** tab and verify that the settings match the following graphic.</span></span> <span data-ttu-id="72d6d-118">**Uwaga:** Należy kliknąć opcję **Zastosuj**, aby utworzyć i poprawnie skonfigurować portal.</span><span class="sxs-lookup"><span data-stu-id="72d6d-118">**Note:** You must click **Apply** to create and properly configure the Portal.</span></span>

    <span data-ttu-id="72d6d-119">[![Karta Adres URL portalu sieci Web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-119">[![web portal url tab](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span></span>
    
  <span data-ttu-id="72d6d-120">Po skonfigurowaniu portalu karta **Portal sieci Web** powinna wyglądać jak na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="72d6d-120">After the Portal is configured, the **Web Portal** tab will match the following graphic.</span></span>
    <span data-ttu-id="72d6d-121">[![Karta Portal sieci Web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-121">[![web portal tab](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span></span>
    
8. <span data-ttu-id="72d6d-122">Kliknij adres URL raportów, aby wyświetlania portalu sieci Web usługi SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="72d6d-122">Click the reports URL to view the SQL Server Reporting Services web portal.</span></span> 
9.  <span data-ttu-id="72d6d-123">Po przejściu do portalu utwórz nowy folder o nazwie **Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="72d6d-123">When you are in the portal, create a new folder named **Dynamics**.</span></span>

    <span data-ttu-id="72d6d-124">[![Folder Dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-124">[![dynamics folder](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span></span>
    
10. <span data-ttu-id="72d6d-125">W **Menedżerze konfiguracji usługi SQL Reporting Services** kliknij kartę **Ustawienia poczty e-mail** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="72d6d-125">In the **Reporting Services Configuration Manager**, click the **E-mail Settings** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="72d6d-126">[![Karta Ustawienia poczty e-mail](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-126">[![email settings tab](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span></span>
    
11. <span data-ttu-id="72d6d-127">Kliknij kartę **Konto wykonywania** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="72d6d-127">Click the **Execution Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="72d6d-128">[![Karta Konto wykonywania](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-128">[![execution account tab](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span></span>
    
  <span data-ttu-id="72d6d-129">Nie należy zmieniać ustawień domyślnych na karcie **Klucze szyfrowania**. [![karta klucze szyfrowania](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-129">Don’t change the default settings on the **Encryption Keys** tab. [![encryption keys tab](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span></span>
    
12. <span data-ttu-id="72d6d-130">Kliknij kartę **Ustawienia subskrypcji** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="72d6d-130">Click the **Subscription Settings** tab, and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="72d6d-131">[![Karta Ustawienia subskrypcji](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-131">[![subscription settings tab](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span></span>
    
  <span data-ttu-id="72d6d-132">Nie należy zmieniać ustawień domyślnych na karcie **Wdrożenie skalowalne w poziomie**. [![karta wdrożenie skalowalne w poziomie](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-132">Don’t change the default settings on the **Scale-out Deployment** tab. [![scale-out deployment tab](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span></span>
    
  <span data-ttu-id="72d6d-133">Nie należy zmieniać ustawień domyślnych na karcie **Integracja usługi Power BI**. [![karta integracja usługi power bi](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-133">Don’t change the default settings on the **Power BI Integration** tab. [![power bi integration tab](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span></span> 
    
13. <span data-ttu-id="72d6d-134">Kliknij przycisk **Zakończ**, aby zamknąć **Menedżera konfiguracji usługi Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="72d6d-134">Click **Exit** to close the **Reporting Services Configuration Manager**.</span></span>

    <span data-ttu-id="72d6d-135">[![Zamykanie Menedżera konfiguracji usługi Reporting Services](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span><span class="sxs-lookup"><span data-stu-id="72d6d-135">[![close reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span></span>
    


