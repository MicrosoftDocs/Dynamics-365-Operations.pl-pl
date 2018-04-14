---
title: "Równoległe wyświetlanie stron przy użyciu ikony Otwórz w nowym oknie"
description: "W tym artykule wyjaśniono, jak wyświetlić strony obok siebie w programie Microsoft Dynamics 365 for Finance and Operations."
author: aneesmsft
manager: AnnBe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: f19ca5e9642b5a8222ee7bf23fdd228ab75d2ed1
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="display-pages-side-by-side-using-the-open-in-new-window-icon"></a><span data-ttu-id="1109d-103">Równoległe wyświetlanie stron przy użyciu ikony Otwórz w nowym oknie</span><span class="sxs-lookup"><span data-stu-id="1109d-103">Display pages side-by-side using the Open in New Window icon</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="1109d-104">W tym artykule wyjaśniono, jak wyświetlić strony obok siebie w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1109d-104">This article explains how to display pages side-by-side in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="1109d-105">Microsoft Dynamics 365 for Finance and Operations ułatwia efektywne wykonywanie zadań.</span><span class="sxs-lookup"><span data-stu-id="1109d-105">Microsoft Dynamics 365 for Finance and Operations helps you perform tasks efficiently.</span></span> <span data-ttu-id="1109d-106">W niektórych przypadkach może być potrzebne wyświetlenie kliku stron jednocześnie, aby szybko wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="1109d-106">In some cases, you may want to view multiple pages side-by-side to complete tasks quickly.</span></span> <span data-ttu-id="1109d-107">Na przykład może być konieczne sprawdzenie poprawności lub wprowadzenie wierszy w kilku arkuszach.</span><span class="sxs-lookup"><span data-stu-id="1109d-107">As an example, you might want to validate or enter lines in more than one journal.</span></span> <span data-ttu-id="1109d-108">Zwykle w tym celu trzeba przechodzić między stroną z listą arkuszy i stroną zawierającą wiersze dla danego arkusza.</span><span class="sxs-lookup"><span data-stu-id="1109d-108">Typically, to do this you would have to go back and forth between the page that displays a list of journals, and the page that displays lines for a given journal.</span></span> <span data-ttu-id="1109d-109">Ale dzięki funkcji **Otwórz w nowym oknie** można wyświetlać te strony obok siebie i szybciej wykonywać zadania.</span><span class="sxs-lookup"><span data-stu-id="1109d-109">However, the **Open in new window** feature enables you to display these pages side-by-side so that you can perform your tasks quickly.</span></span> 

<span data-ttu-id="1109d-110">Podczas przeglądania wierszy, kliknij ikonę **Otwórz w nowym oknie**.</span><span class="sxs-lookup"><span data-stu-id="1109d-110">Continuing with the example mentioned above, when viewing the lines, you can click the **Open in new window** icon.</span></span> 

<span data-ttu-id="1109d-111">[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)</span><span class="sxs-lookup"><span data-stu-id="1109d-111">[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)</span></span> 

<span data-ttu-id="1109d-112">Kliknięcie ikony **Otwórz w nowym oknie** spowoduje wyświetlenie strony wierszy w nowym okienku wyskakującym przeglądarki, a następnie w przeglądarce powrót do strony, na której była wyświetlana lista arkuszy.</span><span class="sxs-lookup"><span data-stu-id="1109d-112">Clicking the **Open in new window** icon opens the lines page in a new, pop-up browser, and then navigates the original browser back in history to the page that displayed the list of journals.</span></span> <span data-ttu-id="1109d-113">Możesz wyświetlić obie te strony obok siebie.</span><span class="sxs-lookup"><span data-stu-id="1109d-113">You can then display both pages side-by-side.</span></span> <span data-ttu-id="1109d-114">Po zakończeniu przeglądania arkusza, możesz zmienić wybrany arkusz na stronie arkuszy, a strona wierszy w wyskakującym okienku automatycznie wyświetli wiersze nowo wybranego arkusza.</span><span class="sxs-lookup"><span data-stu-id="1109d-114">When you are done viewing a journal, you can change the selected journal on the journal list page, and the lines page in the pop-up window will automatically display the lines of the newly selected journal.</span></span> 

<span data-ttu-id="1109d-115">[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)</span><span class="sxs-lookup"><span data-stu-id="1109d-115">[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)</span></span> 

<span data-ttu-id="1109d-116">Dynamiczne łączenie i odświeżanie dokonywane jest z powodu istnienia relacji między danymi źródłowymi tych stron.</span><span class="sxs-lookup"><span data-stu-id="1109d-116">The dynamic linking and refreshing happens due to the relations that exist between the data that is backing these pages.</span></span> <span data-ttu-id="1109d-117">Jeśli system nie został powiadomiony o relacji między danymi, wyskakujące okienko nie będzie odświeżać się automatycznie w odpowiedzi na zmianę w oknie, z którego to wyskakujące okienko zostało wyświetlone.</span><span class="sxs-lookup"><span data-stu-id="1109d-117">If the system is not aware of the relation between the data, the pop-up window will not refresh automatically in response to a change in the window it originated from.</span></span> 

<span data-ttu-id="1109d-118">Niektóre strony mają wiele widoków, takich jak Widok siatki, Widok nagłówek czy i Widok szczegółów.</span><span class="sxs-lookup"><span data-stu-id="1109d-118">Some pages have multiple views such as the Grid view, Header view, and Details view.</span></span> <span data-ttu-id="1109d-119">Ikona **Otwórz w nowym oknie** powoduje, że cała strona otwiera się w nowym oknie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="1109d-119">The **Open in new window** icon causes the entire page to be opened in the new browser window.</span></span> <span data-ttu-id="1109d-120">Z tego względu nie można zachować dwóch widoków tej samej strony obok siebie za pomocą funkcji **Otwórz w nowym oknie**.</span><span class="sxs-lookup"><span data-stu-id="1109d-120">Therefore, you cannot keep two views of the same page side-by-side using the **Open in new window** feature.</span></span> <span data-ttu-id="1109d-121">Jednak prawie wszystkie takie strony mają listę nawigacji, której można używać do przełączania między rekordami i wyświetlania podobnego widoku.</span><span class="sxs-lookup"><span data-stu-id="1109d-121">However, almost all such pages have a navigation list that you can use to switch between records and achieve a similar experience.</span></span> 

<span data-ttu-id="1109d-122">Przed rozpoczęciem korzystania z funkcji **Otwórz w nowym oknie** należy tak skonfigurować blokadę wyskakujących okienek w przeglądarce, aby zezwalać na wyświetlanie wyskakujących okienek z adresu URL witryny programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1109d-122">Before using the **Open in new window** feature, you should configure your browser's pop-up blocker to allow pop-ups from the URL of the Finance and Operations site.</span></span> <span data-ttu-id="1109d-123">Na przykład można zezwolić na wyświetlanie wyskakujących okienek od „\*.dynamics.com”.</span><span class="sxs-lookup"><span data-stu-id="1109d-123">As an example, you could allow pop-ups from "\*.dynamics.com".</span></span> 

<span data-ttu-id="1109d-124">Funkcja **Otwórz w nowym oknie** jest dostępna tylko, gdy więcej niż jedna strona jest otwarta w oknie.</span><span class="sxs-lookup"><span data-stu-id="1109d-124">The **Open in new window** feature is only available when there is more than one page open in the window.</span></span> <span data-ttu-id="1109d-125">Ponadto wyskakujące okienko zostanie automatycznie zamknięte, gdy nie ma więcej otwartych stron (tj. gdy ostatnia strona w tym oknie zostanie zamknięta).</span><span class="sxs-lookup"><span data-stu-id="1109d-125">Also, the pop-up window automatically closes when there are no more pages open (that is, when the last page in that window is closed).</span></span> <span data-ttu-id="1109d-126">Program Finance and Operations zamyka również otwarte strony po przejściu do innego obszaru w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1109d-126">Finance and Operations also closes open pages when you navigate to a different area in the application.</span></span> <span data-ttu-id="1109d-127">W związku z tym jeśli masz otwarte wyskakujące okienko i przejdziesz do innego obszaru w aplikacji, wyskakujące okienka są automatycznie zamknięte, ponieważ strony w tych oknach zostały zamknięte przez system.</span><span class="sxs-lookup"><span data-stu-id="1109d-127">Therefore, if you have pop-up windows open and navigate to a different area in the application, the pop-up windows are automatically closed because the pages in those windows were closed by the system.</span></span> 

<span data-ttu-id="1109d-128">Górny pasek w wyskakujących okienkach wyświetlają informację o firmie, w której strona została otwarta, i jest tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="1109d-128">The top bar in the pop-up windows displays information about the company the page was opened in and is read-only.</span></span> <span data-ttu-id="1109d-129">Wyskakujące okienko opiera się również na głównym oknie przeglądarki programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1109d-129">The pop-up windows also rely on the main Finance and Operations browser window.</span></span> <span data-ttu-id="1109d-130">W przypadku zamknięcia lub odświeżana okna głównego, wszystkie wyskakujące okienka stają się tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="1109d-130">If the main window is closed or refreshed, all open pop-up windows will become read only.</span></span> <span data-ttu-id="1109d-131">Oznacza to, że nadal można wyświetlić informacje w tych oknach, ale dane nie są interaktywne.</span><span class="sxs-lookup"><span data-stu-id="1109d-131">This means that you can still view the information in these windows, but you will not be able to interact with it.</span></span>




