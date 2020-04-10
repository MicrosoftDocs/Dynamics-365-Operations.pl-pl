---
title: (Raportowanie elektroniczne) Importowanie konfiguracji z RCS
description: Ten temat zawiera informacje o sposobach importowania przez użytkownika nowej wersji konfiguracji ER ze RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea2bfd2514be666d05165410ca27041a86464715
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143230"
---
# <a name="er-import-configurations-from-rcs"></a><span data-ttu-id="1e878-103">(Raportowanie elektroniczne) Importowanie konfiguracji z RCS</span><span class="sxs-lookup"><span data-stu-id="1e878-103">(ER) Import configurations from RCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e878-104">W poniższych krokach wyjaśniono, jak użytkownik w roli Administratora systemu lub Deweloper raportowania elektronicznego może zaimportować nową wersję konfiguracji raportowania elektronicznego (ER) z usługi Microsoft Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="1e878-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Regulatory Configuration Services (RCS).</span></span> <span data-ttu-id="1e878-105">W tym przykładzie zostanie wybrana wersja konfiguracji ER systemu, która została skonfigurowana w wystąpieniu klasy RCS i zaimportowana do bieżącego wystąpienia dla przykładowej firmy, Litware, Inc. Te kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są wspólne dla różnych firm.</span><span class="sxs-lookup"><span data-stu-id="1e878-105">In this example, you will select the version of the ER configuration that has been configured in an RCS instance and import it into the current instance for sample company, Litware, Inc. These steps can be performed in any company because ER configurations are shared among companies.</span></span> <span data-ttu-id="1e878-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze [Tworzenie dostawców konfiguracji i oznacz je jako aktywne](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1e878-106">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="1e878-107">Aby wykonać te kroki, trzeba również mieć dostęp do instancji klasy RCS zawierającej co najmniej jedną konfigurację ER albo w stanie **Wykonano**, albo **Udostępniono**.</span><span class="sxs-lookup"><span data-stu-id="1e878-107">To complete these steps, you must also have access to an RCS instance containing at least one ER configuration in either **Completed** or **Shared** status.</span></span>

1. <span data-ttu-id="1e878-108">Wybierz kolejno opcje **Administrowanie organizacją** > **Obszary robocze** > **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="1e878-108">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="1e878-109">Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny**</span><span class="sxs-lookup"><span data-stu-id="1e878-109">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="1e878-110">Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj kroki opisane w temacie [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1e878-110">If you don't see this configuration provider, complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3. <span data-ttu-id="1e878-111">Jeśli w firmie nie zainicjowano obsługi administracyjnej żadnego środowiska RCS, należy kliknąć łącze zewnętrzne **Regulatory services — Konfiguracja** i postępować zgodnie z instrukcjami w celu zapewnienia obsługi środowiska RCS.</span><span class="sxs-lookup"><span data-stu-id="1e878-111">If you have no RCS environment provisioned to your company, click **Regulatory services – Configuration** external link and follow the instructions to provision an RCS environment.</span></span> 
4. <span data-ttu-id="1e878-112">Kliknij **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="1e878-112">Click **Electronic reporting parameters**.</span></span> 
5. <span data-ttu-id="1e878-113">Kliknij kartę **RCS**.</span><span class="sxs-lookup"><span data-stu-id="1e878-113">Click the **RCS** tab.</span></span> 
6. <span data-ttu-id="1e878-114">Jeśli dla firmy została już zainicjowana obsługa środowiska RCS, w celu uzyskania dostępu do tej strony należy skorzystać z przedstawionych w adresach URL stron.</span><span class="sxs-lookup"><span data-stu-id="1e878-114">If RCS environment has been already provisioned to your company, use presented on the page URLs to access it.</span></span> 
7. <span data-ttu-id="1e878-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1e878-115">Close the page.</span></span> 

## <a name="register-a-new-er-repository"></a><span data-ttu-id="1e878-116">Rejestrowanie nowego repozytorium ER.</span><span class="sxs-lookup"><span data-stu-id="1e878-116">Register a new ER repository.</span></span> 
1. <span data-ttu-id="1e878-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="1e878-117">In the list, mark the selected row.</span></span> 
2. <span data-ttu-id="1e878-118">Zaznacz dostawcę Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="1e878-118">Select Litware, Inc. provider.</span></span> 
3. <span data-ttu-id="1e878-119">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="1e878-119">Click Repositories.</span></span> 
4. <span data-ttu-id="1e878-120">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1e878-120">Click Add to open the drop dialog.</span></span> 
5. <span data-ttu-id="1e878-121">W polu Typ repozytorium konfiguracji wpisz „RCS”.</span><span class="sxs-lookup"><span data-stu-id="1e878-121">In the Configuration repository type field, enter 'RCS'.</span></span> 
6. <span data-ttu-id="1e878-122">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="1e878-122">Click Create repository.</span></span> 
7. <span data-ttu-id="1e878-123">Wprowadź lub wybierz wartość w polu wyświetlania nazwy środowiska RCS.</span><span class="sxs-lookup"><span data-stu-id="1e878-123">In the RCS environment display name field, enter or select a value.</span></span> 
8. <span data-ttu-id="1e878-124">Wybierz żądany wartość usługi RCS.</span><span class="sxs-lookup"><span data-stu-id="1e878-124">Select the desired RCS instance.</span></span> <span data-ttu-id="1e878-125">Zwróć uwagę, że możesz mieć kilka z nich.</span><span class="sxs-lookup"><span data-stu-id="1e878-125">Note that you can have several of them.</span></span> 
9. <span data-ttu-id="1e878-126">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1e878-126">Click OK.</span></span> 

## <a name="import-er-configurations-from-rcs-based-repository"></a><span data-ttu-id="1e878-127">Importowanie konfiguracji modułu Raportowanie elektroniczne z repozytorium opartym na RCS</span><span class="sxs-lookup"><span data-stu-id="1e878-127">Import ER configurations from RCS based repository</span></span>
1. <span data-ttu-id="1e878-128">Kliknij przycisk **Pokaż filtry.**</span><span class="sxs-lookup"><span data-stu-id="1e878-128">Click **Show filters**.</span></span> 
2. <span data-ttu-id="1e878-129">Wprowadź wartość filtru „RCS” w polu **Nazwa typu**, używając operatora filtru **Zaczyna się na**.</span><span class="sxs-lookup"><span data-stu-id="1e878-129">Enter a filter value of "RCS" on the **Name** field using the **begins with** filter operator.</span></span> 
3. <span data-ttu-id="1e878-130">Po otwarciu wybranego repozytorium na stronie **Łączenie z usługami Regulatory Configuration Services**, kliknij przycisk **Kliknij tutaj, aby połączyć się z łączem usług Regulatory Configuration Services**.</span><span class="sxs-lookup"><span data-stu-id="1e878-130">When you open the selected repository, on the **Connect to Regulatory Configuration Services** page, click **Click here to connect to Regulatory Configuration Services** link.</span></span> 
4. <span data-ttu-id="1e878-131">Kliknij przycisk **Otwórz.**</span><span class="sxs-lookup"><span data-stu-id="1e878-131">Click **Open**.</span></span> 
5. <span data-ttu-id="1e878-132">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="1e878-132">Click **Close**.</span></span> 
6. <span data-ttu-id="1e878-133">Wybierz żądaną wersję konfiguracji modułu ER i kliknij przycisk **Importuj**, aby przenieść ją do bieżącego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="1e878-133">Select the desired version of ER configuration and click **Import** to bring it in the current instance.</span></span>

