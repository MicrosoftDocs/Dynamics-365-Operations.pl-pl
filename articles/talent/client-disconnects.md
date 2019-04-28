---
title: Klient aplikacji Talent rozłącza się
description: W tym temacie wyjaśniono, co należy zrobić, jeśli odbiorca zostaje odłączony od własnego środowiska i nie może ustalić, dlaczego.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 885e2d743cd2b01588546327840508f6f7e95958
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2019
ms.locfileid: "859927"
---
# <a name="talent-client-disconnects"></a><span data-ttu-id="57868-103">Klient aplikacji Talent rozłącza się</span><span class="sxs-lookup"><span data-stu-id="57868-103">Talent client disconnects</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="57868-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="57868-104">**Environment details**</span></span> 

<span data-ttu-id="57868-105">Ten problem może występować we wszystkich środowiskach.</span><span class="sxs-lookup"><span data-stu-id="57868-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="57868-106">**Objaw**</span><span class="sxs-lookup"><span data-stu-id="57868-106">**Symptom**</span></span> 

<span data-ttu-id="57868-107">Odbiorca zostaje odłączony od własnego środowiska i nie może ustalić, dlaczego.</span><span class="sxs-lookup"><span data-stu-id="57868-107">The customer is disconnected from his or her environment and doesn't know why.</span></span> <span data-ttu-id="57868-108">Na komputerze odbiorcy jest wyświetlany jeden z następujących komunikatów o błędach:</span><span class="sxs-lookup"><span data-stu-id="57868-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="57868-109">Twoje połączenie zostało utracone</span><span class="sxs-lookup"><span data-stu-id="57868-109">We've lost your connection.</span></span> <span data-ttu-id="57868-110">Kliknij przycisk Zamknij, aby kontynuować pracę.</span><span class="sxs-lookup"><span data-stu-id="57868-110">Click Close to continue working.</span></span>
- <span data-ttu-id="57868-111">Prawdopodobnie doszło do utraty łączności sieciowej. Kliknij przycisk Ponów próbę, aby spróbować ponownie.</span><span class="sxs-lookup"><span data-stu-id="57868-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="57868-112">**Czerwona flaga**</span><span class="sxs-lookup"><span data-stu-id="57868-112">**Red flag**</span></span>

<span data-ttu-id="57868-113">Ten problem występuje często, gdy użytkownicy są w fazie implementacji, porównują informacje między środowiskami produkcyjnymi i testowymi i zapominają, że poruszają się między sesjami.</span><span class="sxs-lookup"><span data-stu-id="57868-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="57868-114">Jeśli użytkownicy są na tym etapie, prawdopodobnie wystąpi ten problem.</span><span class="sxs-lookup"><span data-stu-id="57868-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="57868-115">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="57868-115">**Issue**</span></span> 

<span data-ttu-id="57868-116">**Typy przeglądarek:** Google Chrome, Internet Explorer oraz Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="57868-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="57868-117">Platforma Microsoft Dynamics 365 for Talent rozłączenia użytkowników, gdy są otwarte dwie różne sesje jednocześnie dla tego samego użytkownika i tego samego typu przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="57868-117">The Microsoft Dynamics 365 for Talent platform disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="57868-118">(Na przykład użytkownik A wyświetla środowisko 1 i 2 środowiska w Chrome.) Nie ma znaczenia, czy użytkownik otworzy inne okna przeglądarki lub różne karty.</span><span class="sxs-lookup"><span data-stu-id="57868-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="57868-119">Jeśli te same poświadczenia użytkownika są używane do logowania się zarówno w środowisku 1, jak i środowisku 2 w tym samym czasie w tym samym typie przeglądarki, aplikacja Talent rozłączy jedną z sesji.</span><span class="sxs-lookup"><span data-stu-id="57868-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Talent disconnects one of the sessions.</span></span>

<span data-ttu-id="57868-120">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="57868-120">**Solution**</span></span>

<span data-ttu-id="57868-121">Upewnij się, że tylko jedno środowisko jest otwarte w danej chwili dla danego typu przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="57868-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="57868-122">Użytkownicy mogą otwierać wiele sesji w tym samym środowisku (to znaczy wiele kart w tej samej przeglądarce).</span><span class="sxs-lookup"><span data-stu-id="57868-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="57868-123">Użytkownicy, którzy chcą do przechodzić między dwiema środowiskami w tym samym czasie powinni otwierać każde środowisko w innym typie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="57868-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="57868-124">(Na przykład użytkownik A może wyświetlić środowisko 1 w przeglądarce Chrome i środowisko 2 w Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="57868-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>
