---
title: "Klient aplikacji Talent rozłącza się"
description: "W tym temacie wyjaśniono, co należy zrobić, jeśli odbiorca zostaje odłączony od własnego środowiska i nie może ustalić, dlaczego."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 4f96b986059c179268f8a96ea7e7725831a93524
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---

# <a name="talent-client-disconnects"></a><span data-ttu-id="c1d1b-103">Klient aplikacji Talent rozłącza się</span><span class="sxs-lookup"><span data-stu-id="c1d1b-103">Talent client disconnects</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c1d1b-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="c1d1b-104">**Environment details**</span></span> 

<span data-ttu-id="c1d1b-105">Ten problem może występować we wszystkich środowiskach.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="c1d1b-106">**Objaw**</span><span class="sxs-lookup"><span data-stu-id="c1d1b-106">**Symptom**</span></span> 

<span data-ttu-id="c1d1b-107">Odbiorca zostaje odłączony od własnego środowiska i nie może ustalić, dlaczego.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-107">The customer is disconnected from his or her environment and doesn't know why.</span></span> <span data-ttu-id="c1d1b-108">Na komputerze odbiorcy jest wyświetlany jeden z następujących komunikatów o błędach:</span><span class="sxs-lookup"><span data-stu-id="c1d1b-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="c1d1b-109">Twoje połączenie zostało utracone</span><span class="sxs-lookup"><span data-stu-id="c1d1b-109">We've lost your connection.</span></span> <span data-ttu-id="c1d1b-110">Kliknij przycisk Zamknij, aby kontynuować pracę.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-110">Click Close to continue working.</span></span>
- <span data-ttu-id="c1d1b-111">Prawdopodobnie doszło do utraty łączności sieciowej. Kliknij przycisk Ponów próbę, aby spróbować ponownie.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="c1d1b-112">**Czerwona flaga**</span><span class="sxs-lookup"><span data-stu-id="c1d1b-112">**Red flag**</span></span>

<span data-ttu-id="c1d1b-113">Ten problem występuje często, gdy użytkownicy są w fazie implementacji, porównują informacje między środowiskami produkcyjnymi i testowymi i zapominają, że poruszają się między sesjami.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="c1d1b-114">Jeśli użytkownicy są na tym etapie, prawdopodobnie wystąpi ten problem.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="c1d1b-115">**Wydaj**</span><span class="sxs-lookup"><span data-stu-id="c1d1b-115">**Issue**</span></span> 

<span data-ttu-id="c1d1b-116">**Typy przeglądarki:** Google Chrome, Internet Explorer i Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c1d1b-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="c1d1b-117">Platforma Microsoft Dynamics 365 for Talent rozłączenia użytkowników, gdy są otwarte dwie różne sesje jednocześnie dla tego samego użytkownika i tego samego typu przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-117">The Microsoft Dynamics 365 for Talent platform disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="c1d1b-118">(Na przykład użytkownik A wyświetla środowisko 1 i 2 środowiska w Chrome.) Nie ma znaczenia, czy użytkownik otworzy inne okna przeglądarki lub różne karty.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="c1d1b-119">Jeśli te same poświadczenia użytkownika są używane do logowania się zarówno w środowisku 1, jak i środowisku 2 w tym samym czasie w tym samym typie przeglądarki, aplikacja Talent rozłączy jedną z sesji.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Talent disconnects one of the sessions.</span></span>

<span data-ttu-id="c1d1b-120">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="c1d1b-120">**Solution**</span></span>

<span data-ttu-id="c1d1b-121">Upewnij się, że tylko jedno środowisko jest otwarte w danej chwili dla danego typu przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="c1d1b-122">Użytkownicy mogą otwierać wiele sesji w tym samym środowisku (to znaczy wiele kart w tej samej przeglądarce).</span><span class="sxs-lookup"><span data-stu-id="c1d1b-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="c1d1b-123">Użytkownicy, którzy chcą do przechodzić między dwiema środowiskami w tym samym czasie powinni otwierać każde środowisko w innym typie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="c1d1b-124">(Na przykład użytkownik A może wyświetlić środowisko 1 w przeglądarce Chrome i środowisko 2 w Microsoft Edge.)</span><span class="sxs-lookup"><span data-stu-id="c1d1b-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>

