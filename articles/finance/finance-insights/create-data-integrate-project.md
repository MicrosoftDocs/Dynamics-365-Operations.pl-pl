---
title: Tworzenie projektu integratora danych (wersja zapoznawcza)
description: W tym temacie opisano sposób tworzenia projektu integratora danych.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: fb17d5e82709a34ff088774d9e9034adb714b58c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646260"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="58594-103">Tworzenie projektu integratora danych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="58594-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="58594-104">W tym temacie opisano sposób tworzenia projektu integratora danych.</span><span class="sxs-lookup"><span data-stu-id="58594-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="58594-105">Zaloguj się do programu Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="58594-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="58594-106">Przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz **Jednostki danych**.</span><span class="sxs-lookup"><span data-stu-id="58594-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="58594-107">Poczekaj, aż wszystkie jednostki danych zostaną odświeżone przed przejściem do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="58594-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="58594-108">Otwórz [portal Power Apps ](https://make.powerapps.com/)i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="58594-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="58594-109">Wybierz odpowiednie środowisko.</span><span class="sxs-lookup"><span data-stu-id="58594-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="58594-110">W okienku nawigacji po lewej stronie wybierz **Dane \> Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="58594-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="58594-111">Połącz z odpowiednimi wystąpieniami następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="58594-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="58594-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="58594-112">Dynamics 365</span></span>
        - <span data-ttu-id="58594-113">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="58594-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="58594-114">Otwórz [środowiska Power Apps ](https://admin.powerapps.com/environments)i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="58594-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="58594-115">Wybierz **Integrator danych**.</span><span class="sxs-lookup"><span data-stu-id="58594-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="58594-116">Wybierz **Zestaw połączeń**.</span><span class="sxs-lookup"><span data-stu-id="58594-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="58594-117">Wybierz **Nowy zestaw połączeń**.</span><span class="sxs-lookup"><span data-stu-id="58594-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="58594-118">Wprowadź nazwę połączenia.</span><span class="sxs-lookup"><span data-stu-id="58594-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="58594-119">Wybierz odpowiednie połączenia dla następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="58594-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="58594-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="58594-120">Dynamics 365</span></span>
        - <span data-ttu-id="58594-121">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="58594-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="58594-122">Wybierz odpowiednie mapowanie organizacji.</span><span class="sxs-lookup"><span data-stu-id="58594-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="58594-123">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="58594-123">Select **Create**.</span></span>

5. <span data-ttu-id="58594-124">Otwórz [środowiska Power Apps ](https://admin.powerapps.com/environments)i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="58594-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="58594-125">Utwórz projekty integracji danych dla następujących szablonów przy użyciu utworzonego właśnie zestawu połączeń:</span><span class="sxs-lookup"><span data-stu-id="58594-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="58594-126">Wyniki wglądu w płatności od odbiorców (CDS do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="58594-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="58594-127">Wyniki szeregów czasowych przepływów pieniężnych (CDS do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="58594-127">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="58594-128">Wyniki szeregów czasowych budżetu (CDS do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="58594-128">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="58594-129">Ustaw odpowiednie planowanie dla każdego projektu.</span><span class="sxs-lookup"><span data-stu-id="58594-129">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="58594-130">Jeśli w CDS nie są wyświetlane wymagane jednostki, przejdź do **Kredyt i windykacje > ustawienia > Finance Insights > Parametry Finance Insights**, włącz funkcję przewidywania płatności od odbiorców i kliknij przycisk **Utwórz model przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="58594-130">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="58594-131">Po ukończeniu wdrażania modelu AI (powodzenie lub niepowodzenie) jednostki CDS potrzebne do utworzenia integracji zostaną wdrożone w CDS.</span><span class="sxs-lookup"><span data-stu-id="58594-131">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="58594-132">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="58594-132">Privacy notice</span></span>

<span data-ttu-id="58594-133">Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="58594-133">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
