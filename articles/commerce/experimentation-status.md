---
title: Sprawdzanie stanu eksperymentu
description: W tym temacie wyjaśniono, jaki stan ma eksperyment w cyklu życia eksperymentu w systemie Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: f7bdd292893ee42d49bdf977a55d8b10896ca1cd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792446"
---
# <a name="review-the-status-of-an-experiment"></a><span data-ttu-id="a7317-103">Sprawdzanie stanu eksperymentu</span><span class="sxs-lookup"><span data-stu-id="a7317-103">Review the status of an experiment</span></span>
<span data-ttu-id="a7317-104">Jest wiele kroków związanych z konfigurowaniem i uruchamianiem eksperymentu w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a7317-104">There are many steps involved in setting up and running an experiment in Dynamics 365 Commerce.</span></span> <span data-ttu-id="a7317-105">Aby uzyskać informacje na temat cyklu życia eksperymentu, zobacz temat [Eksperymentowanie w systemie Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a7317-105">For information about the experimentation lifecycle, see [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="a7317-106">Aby dowiedzieć się, gdzie eksperyment znajduje się w cyklu życia, w konstruktorze witryn Commerce wybierz **Eksperymenty** w okienku nawigacji po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="a7317-106">To learn where an experiment is in the lifecycle, in Commerce site builder select **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="a7317-107">Zostanie wyświetlona lista eksperymentów ze stanem każdego eksperymentu w module Commerce i w ramach usługi innej firmy, która jest używana do tworzenia eksperymentów, przypisywania odmian i analizowania danych.</span><span class="sxs-lookup"><span data-stu-id="a7317-107">A list of experiments is displayed with the status of each experiment in both Commerce and the third-party service that is being used to enable the creation of experiments, assign variations, and analyze data.</span></span>

<span data-ttu-id="a7317-108">W kolumnie **Stan Commerce** mogą być wyświetlane następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="a7317-108">In the **Commerce status** column, the following values may be displayed.</span></span> 
- <span data-ttu-id="a7317-109">**Wersja robocza** — eksperyment jest połączony ze stroną lub fragmentem w Commerce i jest edytowany.</span><span class="sxs-lookup"><span data-stu-id="a7317-109">**Draft** - The experiment is connected to a page or fragment in Commerce and is being edited.</span></span>
- <span data-ttu-id="a7317-110">**Opublikowany** — warianty eksperymentów są gotowe do wyświetlenia w witrynie internetowej.</span><span class="sxs-lookup"><span data-stu-id="a7317-110">**Published** - The experiment variations are ready to be displayed on your website.</span></span> <span data-ttu-id="a7317-111">Jeśli eksperyment jest uruchomiony w usłudze innej firmy, użytkownicy witryny sieci Web będą widzieli odmianę strony lub fragmentu jako wybraną przez usługę innej firmy.</span><span class="sxs-lookup"><span data-stu-id="a7317-111">If the experiment is running in the third-party service, website users will see a variation of the page or fragment as selected by the third-party service.</span></span>
- <span data-ttu-id="a7317-112">**Wycofany** — eksperyment nie jest już dostępny w serwisie WWW.</span><span class="sxs-lookup"><span data-stu-id="a7317-112">**Unpublished** - The experiment is no longer available on your website.</span></span> <span data-ttu-id="a7317-113">Użytkownicy witryny sieci Web będą widzieli tylko odmianę strony lub fragmentu jako wybraną przez usługę innej firmy nawet jeśli eksperyment jest uruchomiony w usłudze innej firmy.</span><span class="sxs-lookup"><span data-stu-id="a7317-113">Website users will only see the default version of the page or fragment even if the experiment is running in the third-party service.</span></span>
- <span data-ttu-id="a7317-114">**Zakończony** — eksperyment został przeprowadzony, a odmiana została przeniesiony do eksploatacji dla wszystkich użytkowników witryny sieci Web.</span><span class="sxs-lookup"><span data-stu-id="a7317-114">**Completed** - The experiment has run its course and a variation was promoted to live for all website users.</span></span>

<span data-ttu-id="a7317-115">Podobnie, w kolumnie **stanu firmy zewnętrznej** można wyświetlić następujące wartości wskazujące stan eksperymentów w usłudze innej firmy.</span><span class="sxs-lookup"><span data-stu-id="a7317-115">Similarly, in the **third-party status** column, the following values may be displayed to indicate what status the experiments are in the third-party service.</span></span>
- <span data-ttu-id="a7317-116">**Wersja robocza** — eksperyment jest konfigurowany w usłudze innej firmy, ale nie został uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="a7317-116">**Draft** - The experiment is set up in the third-party service but hasn't been started.</span></span>
- <span data-ttu-id="a7317-117">**Uruchomiony** — eksperyment został uruchomiony w usłudze innej firmy i gromadzi dane.</span><span class="sxs-lookup"><span data-stu-id="a7317-117">**Running** - The experiment was started in the third-party service and is collecting data.</span></span>
- <span data-ttu-id="a7317-118">**Wstrzymany** — eksperyment jest wstrzymany i nie zbiera danych.</span><span class="sxs-lookup"><span data-stu-id="a7317-118">**Paused** - The experiment is paused and not collecting data.</span></span> <span data-ttu-id="a7317-119">Aby ponownie zebrać dane, musisz wznowić eksperyment.</span><span class="sxs-lookup"><span data-stu-id="a7317-119">You must resume the experiment for it to collect data again.</span></span>
- <span data-ttu-id="a7317-120">**Zarchiwizowany** — eksperyment został przeprowadzony i skatalogowany w usłudze innej firmy do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="a7317-120">**Archived** - The experiment has run its course and has been cataloged in the third-party service for future reference.</span></span>

<span data-ttu-id="a7317-121">Poniższy diagram przedstawia oba zestawy stanów oraz sposób ich powiązania.</span><span class="sxs-lookup"><span data-stu-id="a7317-121">The diagram below shows both sets of statuses and how they relate to each other.</span></span>

<span data-ttu-id="a7317-122">[ ![Stany eksperymentów](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a7317-122">[ ![Experimentation statuses](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]