---
title: Kiedy resetować składnicę danych
description: W tym temacie wymieniono okoliczności, które mogą zostać poprawione przez zresetowanie składnicy danych, i okoliczności, w których zresetowanie składnicy danych nie będzie pomocne.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988999"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="905cc-103">Kiedy resetować składnicę danych</span><span class="sxs-lookup"><span data-stu-id="905cc-103">When to reset a data mart</span></span>

<span data-ttu-id="905cc-104">Resetowanie składnicy danych może być czasochłonne.</span><span class="sxs-lookup"><span data-stu-id="905cc-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="905cc-105">W zależności od okoliczności ta akcja może nie być potrzebnym rozwiązaniem.</span><span class="sxs-lookup"><span data-stu-id="905cc-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="905cc-106">W tym temacie wymieniono okoliczności, które mogą zostać poprawione przez zresetowanie składnicy danych, a także okoliczności, w których zresetowanie składnicy danych nie będzie pomocne.</span><span class="sxs-lookup"><span data-stu-id="905cc-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a><span data-ttu-id="905cc-107">Kiedy muszę zresetować składnicę danych?</span><span class="sxs-lookup"><span data-stu-id="905cc-107">When do I need to do a data mart reset?</span></span>
<span data-ttu-id="905cc-108">Przed zresetowaniem składnicy danych należy zadać sobie poniższe pytania.</span><span class="sxs-lookup"><span data-stu-id="905cc-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="905cc-109">Odpowiedź Tak na jedno lub więcej pytań może wskazywać, że organizacja może skorzystać z zalet zresetowania składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="905cc-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="905cc-110">Czy baza danych aplikacji została przywrócona?</span><span class="sxs-lookup"><span data-stu-id="905cc-110">Was the application database restored?</span></span>
- <span data-ttu-id="905cc-111">Jeśli otworzyłeś incydent pomocy technicznej, a inżynier pomocy technicznej poinstruował Cię, aby zresetować zbiorczą bazę danych w ramach kroku rozwiązywania problemów?</span><span class="sxs-lookup"><span data-stu-id="905cc-111">If you've opened a support incident that and a support engineer has instructed you to reset the data mart as part of a troubleshooting step?</span></span>
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="905cc-112">Kiedy resetowanie składnicy danych nie jest właściwym rozwiązaniem?</span><span class="sxs-lookup"><span data-stu-id="905cc-112">When is it not appropriate to reset a data mart?</span></span>
<span data-ttu-id="905cc-113">Istnieją pewne okoliczności, w przypadku których nie zaleca się resetowania składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="905cc-113">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="905cc-114">Obejmują one następujące sytuacje.</span><span class="sxs-lookup"><span data-stu-id="905cc-114">These include the following.</span></span> 

- <span data-ttu-id="905cc-115">Występują problemy z wydajnością związane z synchronizacją danych.</span><span class="sxs-lookup"><span data-stu-id="905cc-115">You're experiencing performance issues that are associated with a data sync.</span></span> 
- <span data-ttu-id="905cc-116">Jeśli z następujących przyczyn używasz wzorca resetowania cyklicznego:</span><span class="sxs-lookup"><span data-stu-id="905cc-116">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="905cc-117">**Brak danych**</span><span class="sxs-lookup"><span data-stu-id="905cc-117">**Missing data**</span></span> 
  - <span data-ttu-id="905cc-118">**Stan integracji zatrzymany**</span><span class="sxs-lookup"><span data-stu-id="905cc-118">**Stuck integration state**</span></span> 
  - <span data-ttu-id="905cc-119">**Nieaktualne rekordy** — nieaktualne rekordy same w sobie nie stanowią uzasadnienia resetowania składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="905cc-119">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="905cc-120">Jeśli zestaw danych jest duży, proces resetowania może potrwać trochę czasu, ale może spowodować poprawę.</span><span class="sxs-lookup"><span data-stu-id="905cc-120">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="905cc-121">Co to jest reset zbiorczej bazy danych?</span><span class="sxs-lookup"><span data-stu-id="905cc-121">What is a data mart reset?</span></span>
- <span data-ttu-id="905cc-122">Resetowanie rozpocznie się tylko po ukończeniu istniejących zadań.</span><span class="sxs-lookup"><span data-stu-id="905cc-122">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="905cc-123">Dzięki temu stare dane nie będą wstawiane.</span><span class="sxs-lookup"><span data-stu-id="905cc-123">This ensures that old data is not inserted.</span></span> <span data-ttu-id="905cc-124">Na tym etapie może zostać wyświetlony następujący komunikat: „Resetowanie składnicy danych nie zostało przetworzone z powodu aktywnego zadania.</span><span class="sxs-lookup"><span data-stu-id="905cc-124">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="905cc-125">Spróbuj ponownie później”.</span><span class="sxs-lookup"><span data-stu-id="905cc-125">Please try again later.”</span></span>
- <span data-ttu-id="905cc-126">Zresetowanie spowoduje wyłączenie zadań integracji i usunięcie wszystkich danych składnicy.</span><span class="sxs-lookup"><span data-stu-id="905cc-126">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="905cc-127">Integracja została ponownie włączona.</span><span class="sxs-lookup"><span data-stu-id="905cc-127">The integration is re-enabled.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="905cc-128">Czy zresetowanie danych spowoduje utratę raportów, które już zaprojektowano?</span><span class="sxs-lookup"><span data-stu-id="905cc-128">If I reset the data mart, will I lose reports that I've already designed?</span></span> 
<span data-ttu-id="905cc-129">Nie, raporty są przechowywane w tabelach SQL, na które nie ma wpływu resetowanie danych.</span><span class="sxs-lookup"><span data-stu-id="905cc-129">No, your reports are stored in SQL tables that are not impacted by a reset of the data mart.</span></span> <span data-ttu-id="905cc-130">Jeśli chcesz przegrać wszystkie zaprojektowane raporty, możesz utworzyć kopię zapasową projektów, które nie chcesz utracić.</span><span class="sxs-lookup"><span data-stu-id="905cc-130">If you are concerned about losing any reports you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="905cc-131">Aby je schować, otwórz Konstruktora raportów i wybierz opcje **Firma > Firmy > Bloki konstruktora > Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="905cc-131">To back them up, open Report Designer and go to **Company > Companies > Building Blocks > Export**.</span></span>
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a><span data-ttu-id="905cc-132">Czy w celu zresetowania danych konieczne jest zamknięcie systemu przez wszystkich użytkowników?</span><span class="sxs-lookup"><span data-stu-id="905cc-132">Is it necessary for all users to exit the system to reset the data mart?</span></span>
<span data-ttu-id="905cc-133">Nie, użytkownicy mogą kontynuować pracę w systemie podczas resetowania danych.</span><span class="sxs-lookup"><span data-stu-id="905cc-133">No, users can continue working in the system during the data mart reset.</span></span> <span data-ttu-id="905cc-134">Do czasu zresetowania nie będą jednak mogli uzyskać dostępu do żadnych raportów utworzonych za pomocą programu Financial Reporter.</span><span class="sxs-lookup"><span data-stu-id="905cc-134">However, they won’t be able to access any reports that were created with Financial Reporter until the reset is finished.</span></span> 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
