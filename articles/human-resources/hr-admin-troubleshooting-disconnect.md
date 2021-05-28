---
title: Klient aplikacji rozłącza się
description: W tym artykule wyjaśniono, co należy zrobić, jeśli klient zostaje odłączony od własnego środowiska i nie może ustalić, dlaczego.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: db0e8efec1a5a6f01c9b7c4d9334a959fc42886b
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027994"
---
# <a name="client-disconnects"></a><span data-ttu-id="e0de8-103">Klient rozłącza się</span><span class="sxs-lookup"><span data-stu-id="e0de8-103">Client disconnects</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e0de8-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="e0de8-104">**Environment details**</span></span> 

<span data-ttu-id="e0de8-105">Ten problem może występować we wszystkich środowiskach.</span><span class="sxs-lookup"><span data-stu-id="e0de8-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="e0de8-106">**Objaw**</span><span class="sxs-lookup"><span data-stu-id="e0de8-106">**Symptom**</span></span> 

<span data-ttu-id="e0de8-107">Odbiorca zostaje odłączony od własnego środowiska i nie może ustalić, dlaczego.</span><span class="sxs-lookup"><span data-stu-id="e0de8-107">The customer is disconnected from the environment and doesn't know why.</span></span> <span data-ttu-id="e0de8-108">Na komputerze odbiorcy jest wyświetlany jeden z następujących komunikatów o błędach:</span><span class="sxs-lookup"><span data-stu-id="e0de8-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="e0de8-109">Twoje połączenie zostało utracone</span><span class="sxs-lookup"><span data-stu-id="e0de8-109">We've lost your connection.</span></span> <span data-ttu-id="e0de8-110">Kliknij przycisk Zamknij, aby kontynuować pracę.</span><span class="sxs-lookup"><span data-stu-id="e0de8-110">Click Close to continue working.</span></span>
- <span data-ttu-id="e0de8-111">Prawdopodobnie doszło do utraty łączności sieciowej. Kliknij przycisk Ponów próbę, aby spróbować ponownie.</span><span class="sxs-lookup"><span data-stu-id="e0de8-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="e0de8-112">**Czerwona flaga**</span><span class="sxs-lookup"><span data-stu-id="e0de8-112">**Red flag**</span></span>

<span data-ttu-id="e0de8-113">Ten problem występuje często, gdy użytkownicy są w fazie implementacji, porównują informacje między środowiskami produkcyjnymi i testowymi i zapominają, że poruszają się między sesjami.</span><span class="sxs-lookup"><span data-stu-id="e0de8-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="e0de8-114">Jeśli użytkownicy są na tym etapie, prawdopodobnie wystąpi ten problem.</span><span class="sxs-lookup"><span data-stu-id="e0de8-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="e0de8-115">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="e0de8-115">**Issue**</span></span> 

<span data-ttu-id="e0de8-116">**Typy przeglądarek:** Google Chrome, Internet Explorer oraz Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e0de8-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="e0de8-117">Microsoft Dynamics 365 Human Resources rozłącza użytkowników, gdy są otwarte dwie różne sesje jednocześnie dla tego samego użytkownika i tego samego typu przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="e0de8-117">Microsoft Dynamics 365 Human Resources disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="e0de8-118">(Na przykład użytkownik A wyświetla środowisko 1 i 2 środowiska w Chrome.) Nie ma znaczenia, czy użytkownik otworzy inne okna przeglądarki lub różne karty.</span><span class="sxs-lookup"><span data-stu-id="e0de8-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="e0de8-119">Jeśli te same poświadczenia użytkownika są używane do logowania się zarówno w środowisku 1, jak i środowisku 2 w tym samym czasie w tym samym typie przeglądarki, moduł Human Resources rozłączy jedną z sesji.</span><span class="sxs-lookup"><span data-stu-id="e0de8-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Human Resources disconnects one of the sessions.</span></span>

<span data-ttu-id="e0de8-120">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="e0de8-120">**Solution**</span></span>

<span data-ttu-id="e0de8-121">Upewnij się, że tylko jedno środowisko jest otwarte w danej chwili dla danego typu przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="e0de8-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="e0de8-122">Użytkownicy mogą otwierać wiele sesji w tym samym środowisku (to znaczy wiele kart w tej samej przeglądarce).</span><span class="sxs-lookup"><span data-stu-id="e0de8-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="e0de8-123">Użytkownicy, którzy chcą do przechodzić między dwiema środowiskami w tym samym czasie powinni otwierać każde środowisko w innym typie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="e0de8-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="e0de8-124">(Na przykład użytkownik A może wyświetlić środowisko 1 w przeglądarce Chrome i środowisko 2 w Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="e0de8-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]