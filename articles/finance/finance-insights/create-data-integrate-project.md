---
title: Tworzenie projektu integratora danych (wersja zapoznawcza)
description: W tym temacie opisano sposób tworzenia projektu integratora danych.
author: ShivamPandey-msft
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 9ecf6ef7b7f052ebbb1201dcd04a7431f5b72ce5
ms.sourcegitcommit: b64c52d85aa6f110f3b1959a5521637dd8631b5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867454"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="6eccb-103">Tworzenie projektu integratora danych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="6eccb-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="6eccb-104">W tym temacie opisano sposób tworzenia projektu integratora danych.</span><span class="sxs-lookup"><span data-stu-id="6eccb-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="6eccb-105">Zaloguj się do programu Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="6eccb-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="6eccb-106">Przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz **Jednostki danych**.</span><span class="sxs-lookup"><span data-stu-id="6eccb-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="6eccb-107">Poczekaj, aż wszystkie jednostki danych zostaną odświeżone przed przejściem do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="6eccb-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="6eccb-108">Otwórz [portal Power Apps ](https://make.powerapps.com/)i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="6eccb-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="6eccb-109">Wybierz odpowiednie środowisko.</span><span class="sxs-lookup"><span data-stu-id="6eccb-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="6eccb-110">W okienku nawigacji po lewej stronie wybierz **Dane \> Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="6eccb-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="6eccb-111">Połącz z odpowiednimi wystąpieniami następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="6eccb-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="6eccb-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6eccb-112">Dynamics 365</span></span>
        - <span data-ttu-id="6eccb-113">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="6eccb-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="6eccb-114">Otwórz [środowiska Power Apps ](https://admin.powerapps.com/environments)i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="6eccb-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="6eccb-115">Wybierz **Integrator danych**.</span><span class="sxs-lookup"><span data-stu-id="6eccb-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="6eccb-116">Wybierz **Zestaw połączeń**.</span><span class="sxs-lookup"><span data-stu-id="6eccb-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="6eccb-117">Wybierz **Nowy zestaw połączeń**.</span><span class="sxs-lookup"><span data-stu-id="6eccb-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="6eccb-118">Wprowadź nazwę połączenia.</span><span class="sxs-lookup"><span data-stu-id="6eccb-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="6eccb-119">Wybierz odpowiednie połączenia dla następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="6eccb-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="6eccb-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6eccb-120">Dynamics 365</span></span>
        - <span data-ttu-id="6eccb-121">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="6eccb-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="6eccb-122">Wybierz odpowiednie mapowanie organizacji.</span><span class="sxs-lookup"><span data-stu-id="6eccb-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="6eccb-123">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="6eccb-123">Select **Create**.</span></span>

5. <span data-ttu-id="6eccb-124">Otwórz [środowiska Power Apps ](https://admin.powerapps.com/environments)i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="6eccb-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="6eccb-125">Utwórz projekty integracji danych dla następujących szablonów przy użyciu utworzonego właśnie zestawu połączeń:</span><span class="sxs-lookup"><span data-stu-id="6eccb-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="6eccb-126">Wyniki wglądu w płatności od odbiorców (CDS do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="6eccb-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
            - <span data-ttu-id="6eccb-127">Jeśli używasz wersji 10.0.17 lub nowszej, musisz użyć szablonu o nazwie, Wynik analizy płatności klienta (CDS do Fin i Ops 10.0.17+).</span><span class="sxs-lookup"><span data-stu-id="6eccb-127">If you are using version 10.0.17 or later, you need to use the template named, Customer payment insights result (CDS to Fin and Ops 10.0.17+).</span></span>
        - <span data-ttu-id="6eccb-128">Wyniki szeregów czasowych przepływów pieniężnych (CDS do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="6eccb-128">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="6eccb-129">Wyniki szeregów czasowych budżetu (CDS do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="6eccb-129">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="6eccb-130">Ustaw odpowiednie planowanie dla każdego projektu.</span><span class="sxs-lookup"><span data-stu-id="6eccb-130">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="6eccb-131">Jeśli w CDS nie są wyświetlane wymagane jednostki, przejdź do **Kredyt i windykacje > ustawienia > Finance Insights > Parametry Finance Insights**, włącz funkcję przewidywania płatności od odbiorców i kliknij przycisk **Utwórz model przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="6eccb-131">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="6eccb-132">Po ukończeniu wdrażania modelu AI (powodzenie lub niepowodzenie) jednostki CDS potrzebne do utworzenia integracji zostaną wdrożone w CDS.</span><span class="sxs-lookup"><span data-stu-id="6eccb-132">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="6eccb-133">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="6eccb-133">Privacy notice</span></span>

<span data-ttu-id="6eccb-134">Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="6eccb-134">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
