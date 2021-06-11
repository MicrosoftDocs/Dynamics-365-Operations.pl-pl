---
title: Wywoływanie przepływów automatyzacji procesów w celu tworzenia zleceń wysokiej jakości
description: Ten temat zawiera zasoby, za pomocą których w Power Automate można automatyzować procesy biznesowe, korzystając z przykładów zleceń kontroli jakości.
author: cabeln
ms.date: 05/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f35adab3075ba810964a41899ba95ae40c115e83
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115210"
---
# <a name="invoke-process-automation-flows-to-create-quality-orders"></a><span data-ttu-id="d1544-103">Wywoływanie przepływów automatyzacji procesów w celu tworzenia zleceń wysokiej jakości</span><span class="sxs-lookup"><span data-stu-id="d1544-103">Invoke process automation flows to create quality orders</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="d1544-104">Organizacje mają coraz większe zapotrzebowanie na automatyzację standardowych procesów biznesowych, zapewnienie wygodniejszej interakcji z pracownikami oraz wykorzystanie różnych sygnałów danych i systemów do automatycznego sterowania procesami biznesowymi.</span><span class="sxs-lookup"><span data-stu-id="d1544-104">Organizations have an increasing demand to automate standard business processes, provide more convenient interactions to the staff, and utilize various data signals and systems to drive business processes automatically.</span></span> <span data-ttu-id="d1544-105">Dzięki automatyzacji procesów (RPA) i Microsoft Power Automate firmy mogą używać funkcji bez kodowania do automatyzowania powtarzalnych procesów, zyskując tym samym wydajność i dokładność.</span><span class="sxs-lookup"><span data-stu-id="d1544-105">With robotic process automation (RPA) and Microsoft Power Automate, businesses can use a no-code experience to automate repetitive processes, thus gaining efficiency and accuracy.</span></span>

<span data-ttu-id="d1544-106">Szablon rozwiązania automatyzacji do pobrania dla Supply Chain Management zawiera informacje na temat tego, jak można automatyzować procesy biznesowe w Power Automate, korzystając z przykładowych zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="d1544-106">The downloadable automation solution template for Supply Chain Management showcases how Power Automate can be used to automate business processes using quality orders as an example.</span></span>

<span data-ttu-id="d1544-107">Szablon rozwiązania automatyzacji można pobrać [tutaj](https://aka.ms/D365SCMQualityOrderRPASolution).</span><span class="sxs-lookup"><span data-stu-id="d1544-107">You can download the automation solution template [here](https://aka.ms/D365SCMQualityOrderRPASolution).</span></span>

<span data-ttu-id="d1544-108">Aby uzyskać przegląd tej funkcji i jej możliwości, zobacz następujący film: [Korzystanie z RPA do tworzenia zleceń kontroli jakości w programie Dynamics 365 Supply Chain Management](https://www.youtube.com/watch?v=LFbzJ6-H89w)</span><span class="sxs-lookup"><span data-stu-id="d1544-108">For an overview of this feature and its capabilities, see the following video: [Utilize RPA to create quality orders in Dynamics 365 Supply Chain Management](https://www.youtube.com/watch?v=LFbzJ6-H89w)</span></span>

<span data-ttu-id="d1544-109">![Opcje automatyzacji z RPA](media/rpa-automation-options.png "Opcje automatyzacji z RPA")</span><span class="sxs-lookup"><span data-stu-id="d1544-109">![Automation options with RPA](media/rpa-automation-options.png "Automation options with RPA")</span></span>

<span data-ttu-id="d1544-110">Szablon rozwiązania w Power Automate zawiera przepływ automatyzacji chmury oraz przepływ automatyzacji pulpitu, który automatyzuje tworzenie zleceń kontroli jakości w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d1544-110">The Power Automate solution template includes a cloud automation flow and a desktop automation flow that automate the creation of quality orders in Supply Chain Management.</span></span>

<span data-ttu-id="d1544-111">Automatyzację można rozpocząć w odpowiedzi na wiele zdarzeń i sygnałów, w tym sygnały wejściowe i sygnały maszynowe użytkownika (w tym internet of Things ( IoT)).</span><span class="sxs-lookup"><span data-stu-id="d1544-111">The automation can be started in response to many events and signals, including user input or machine signals (including the Internet of Things (IoT)).</span></span> <span data-ttu-id="d1544-112">Przykład w aplikacji Power Application *Q-Order* jest uwzględniony w szablonie rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="d1544-112">The *Q-Order* Power Application example is included in the solution template.</span></span> <span data-ttu-id="d1544-113">Dzięki temu użytkownik może zeskanować kod QR produktu, wprowadzić ilość i dołączyć zdjęcia za pomocą aparatu.</span><span class="sxs-lookup"><span data-stu-id="d1544-113">It allows the user to scan an item QR code, enter quantity, and attach pictures using a camera.</span></span>

<span data-ttu-id="d1544-114">Parametry rozwiązania są uwzględnione w celu skonfigurowania automatyzacji pod konkretny przypadek użycia w zakładzie produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="d1544-114">Solution parameters are included to configure the automation for a specific use case in a production facility.</span></span>

<span data-ttu-id="d1544-115">![Utwórz zlecenie kontroli jakości](media/rpa-create-quality-roder.png "Utwórz zlecenie kontroli jakości")</span><span class="sxs-lookup"><span data-stu-id="d1544-115">![Create quality order](media/rpa-create-quality-roder.png "Create quality order")</span></span>

<span data-ttu-id="d1544-116">Aby uzyskać pełny przewodnik krok po kroku dotyczący pobierania, instalowania i używania przykładowego rozwiązania do automatyzowania tworzenia zlecenia kontroli jakości, zobacz [Automatyczne tworzenie zlecenia kontroli jakości w Dynamics 365 Supply Chain Management przy użyciu automatyzacji procesów Power Automate Desktop](/power-automate/desktop-flows/dynamics365-scm-rpa).</span><span class="sxs-lookup"><span data-stu-id="d1544-116">For a complete step-by-step guide about how to download, install, and use the sample solution for automating quality order creation, see [Automate quality order creation on Dynamics 365 Supply Chain Management with Robotic Process Automation using Power Automate Desktop](/power-automate/desktop-flows/dynamics365-scm-rpa).</span></span>

